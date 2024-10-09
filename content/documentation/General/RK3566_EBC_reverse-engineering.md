---
title: "RK3566 EBC Reverse-Engineering"
draft: false
menu:
  docs:
    title:
    parent: "General"
    identifier: "General/RK3566_EBC_reverse-engineering"
    weight: 
---

The RK3566 SoC, used in the [Quartz64](/documentation/Quartz64) SBC by PINE64, contains an eInk interface. This is referred to as `ebc` by Rockchip apparently.

Unfortunately, the driver published for this eInk interface within the BSP kernel is an assembly dump produced by gcc. Fortunately, it contains quite a bit of debug information, which we can use to reverse engineer it.

## Sources

### Downstream

The ebc driver source is [available from the quartz-bsp repository](https://gitlab.com/pine64-org/quartz-bsp/rockchip-linux/-/tree/quartz64/drivers/gpu/drm/rockchip/ebc-dev).

The files of interest are `ebc_dev_v8.S`, which implements a DRM (Direct Rendering Manager) driver for the eInk panel, and the waveform files in the `epdlut` subdirectory.

There’s also a simple driver for u-boot: [drivers/video/rk_eink at JeffyCN/rockchip_mirrors](https://github.com/JeffyCN/rockchip_mirrors/tree/u-boot/drivers/video/rk_eink)

These two drivers show the two different programming interfaces exposed by the TCON. The U-Boot driver operates in "LUT mode": it writes the waveform LUT to registers in the TCON’s MMIO space, and passes buffers of _pixel_ data to the TCON. The Linux driver operates in "direct mode" uses the LUTs to compute waveforms in software, and passes buffers of _waveform_ data to the TCON.

Some reversing of the downstream Linux driver has been done here: https://github.com/Ralim/ebc-dev-reverse-engineering

### Reimplementation

A human-readable C reimplementation of the LUT and pixel data path [is available from smaeul here](https://gitlab.com/smaeul/ebc-dev). This provides everything needed to convert a framebuffer and a waveform data file into a series of "frames" for the panel. The new implementation includes a test suite to verify its output matches the output from the BSP assembly code. It is based on the downstream Linux driver.

### In-Development Driver

[rk356x-ebc-dev](https://github.com/smaeul/linux/commits/rk356x-ebc-dev) is the branch used for developing an upstreamable DRM driver based on mainline kernel sources. The driver currently functions well enough to get a virtual console and Xorg running, but it does not support features like multiple waveforms.

## Documentation

### Datasheets

#### EBC

The EBC TCON is documented in part 2 of the RK356x TRM.

#### TI TPS65185x

This is the PMIC used to drive the e-Ink panel, for which the downstream sources also implement a driver.

https://www.ti.com/lit/ds/symlink/tps65185.pdf

#### Waveform

The format of the waveform file is documented here:

https://www.waveshare.net/w/upload/c/c4/E-paper-mode-declaration.pdf

https://www.waveshare.net/w/upload/archive/c/c4/20190611032540!E-paper-mode-declaration.pdf

### Utilities

The [***inkwave***](https://github.com/fread-ink/inkwave) program is designed to parse waveform files. Currently it cannot fully handle the waveform files shipped with the PineNote. Adding support for this to the tool would be helpful.

### Assembly Syntax and Semantics

The Syntax is GNU Assembler (GAS) syntax. [This modexp article](https://modexp.wordpress.com/2018/10/30/arm64-assembly/) provides a good introduction to the syntax, calling convention, semantics and some often used instructions.

The [ARM Architecture Reference Manual for ARMv8](https://developer.arm.com/documentation/ddi0487/gb/) should be used as reference for any instructions.

At the very least, you should read up on the registers and calling convention used.

## Various Findings

The driver isn’t really something that can be mainlined as-is once reversed, as it makes a number of questionable design decisions.

* It’s technically a DRM subsystem driver, but doesn’t really utilise what DRM provides at all.
* It seems to register a new ioctl to set buffer attributes like width and height, despite DRM more than likely having a way for clients to tell a driver what size the framebuffer should be.
* It directly interacts with the PMIC instead of going through regulators/hwmon.

However, reverse engineering to know how it works provides a good baseline from which we can rewrite it in a more sensible manner.

## Debug Information

Quite a bit of debug info is left in the assembly dump, including function names, file names and line numbers. We can take this to our advantage.

### `.file _file-number_ _file-path_`

Specifies a number to reference a file by, and its path. All following code until the next `.file` or `.loc` statement are to be understood as originating from this file. This is particularly useful to understand which code has been inlined from other files, for which the source is available.

### `.loc _file-number_ _line-number_ 0`

Specifies that the following code is generated from `_line-number_` stemming from file number `_file-number_`. See the `.file` directive for this file number to understand which source file it came from.

### `.type _function-name_, %function`

This tells us that the following code belongs to function `_function-name_`. You’ll usually see a `.cfi_startproc`, which signifies the start of the function code, until the matching `.cfi_endproc`.

A quick grep for `%function` shows that we are dealing with 30 functions in this file.

### `.type _struct-name_, %object`

This seems to signify a definition of a C struct named `_struct-name_`.

A quick grep for `%object` shows that we are dealing with around 27 structs in this file.

### `.Ldebug_info0:`

**TODO:** This seems to contain the main bulk of the DWARF debug information, including enough info to reverse full structs and function signatures.

## Finding Structs and Function Signatures

First, we’ll need to assemble the file:

`aarch64-linux-gnu-gcc -c -o ebc_dev_v8.o ebc_dev_v8.S`

This gives us a `ebc_dev_v8.o` which we can feed into analysis tools.

For both of these, keep in mind that we’re only interested in stuff from ebc_dev.c, or any other files for which we don’t have the source. There’s no point in getting the struct description or reverse-engineering a function that we have the source code for. A lot more than ebc_dev will be in the object file due to inlining and such.

Also make sure that if you are looking up known struct accesses, that you use struct definitions from the BSP kernel, not from mainline. The kernel has no internal ABI for drivers!

### Faster and Easier - Ghidra

Import the file into Ghidra, open the code browser. After analysis, you should be able to find structs in the "Data Type Manager" marked with an S icon. You’ll also find functions in the symbol tree.

### Slow and Painful - readelf/objdump

Use this if you want to manually look up dwarf symbols for some reason.

`readelf --debug-dump ebc_dev_v8.o`

This will produce a lot of output, but we’re mainly concerned with the start of the dump. We’ll find things like:
 
 &lt;2&gt;&lt;101f8&gt;: Abbrev Number: 0
 &lt;1&gt;&lt;101f9&gt;: Abbrev Number: 79 (DW_TAG_subprogram)
    &lt;101fa&gt;   DW_AT_name        : (indirect string, offset: 0xa2b4): ebc_open
    &lt;101fe&gt;   DW_AT_decl_file   : 1
    &lt;101ff&gt;   DW_AT_decl_line   : 1377
    &lt;10201&gt;   DW_AT_prototyped  : 1
    &lt;10201&gt;   DW_AT_type        : &lt;0xc6&gt;
    &lt;10205&gt;   DW_AT_low_pc      : 0x0
    &lt;1020d&gt;   DW_AT_high_pc     : 0xc
    &lt;10215&gt;   DW_AT_frame_base  : 1 byte block: 9c 	(DW_OP_call_frame_cfa)
    &lt;10217&gt;   DW_AT_GNU_all_call_sites: 1
    &lt;10217&gt;   DW_AT_sibling     : &lt;0x1023a&gt;
 &lt;2&gt;&lt;1021b&gt;: Abbrev Number: 88 (DW_TAG_formal_parameter)
    &lt;1021c&gt;   DW_AT_name        : (indirect string, offset: 0x1153): inode
    &lt;10220&gt;   DW_AT_decl_file   : 1
    &lt;10221&gt;   DW_AT_decl_line   : 1377
    &lt;10223&gt;   DW_AT_type        : &lt;0x1c54&gt;
    &lt;10227&gt;   DW_AT_location    : 0xd63 (location list)
 &lt;2&gt;&lt;1022b&gt;: Abbrev Number: 106 (DW_TAG_formal_parameter)
    &lt;1022c&gt;   DW_AT_name        : (indirect string, offset: 0x8b06): file
    &lt;10230&gt;   DW_AT_decl_file   : 1
    &lt;10231&gt;   DW_AT_decl_line   : 1377
    &lt;10233&gt;   DW_AT_type        : &lt;0x551f&gt;
    &lt;10237&gt;   DW_AT_location    : 1 byte block: 51 	(DW_OP_reg1 (x1))

This essentially tells us the full function signature of `ebc_open`:

`DW_TAG_subprogram` tells us of a function, with `DW_AT_name` letting us know that this is `ebc_open`. `DW_AT_type` of `0xc6` let’s us know, once we jump to `&lt;c6&gt;`, that this function’s return type is a signed 32-bit integer.

The `DW_TAG_formal_parameter` that follow tell us of each of the parameter the function takes. The first one is called `inode` and is of type `0x1c54`. Referencing what this type is, we find:


    <1><1c54>: Abbrev Number: 7 (DW_TAG_pointer_type)
       <1c55>   DW_AT_byte_size   : 8
       <1c56>   DW_AT_type        : <0x1970>

which in of itself goes on to reference `0x1970`, and looking this one up, we’ll find a struct definition:


    <1><1970>: Abbrev Number: 26 (DW_TAG_structure_type)
       <1971>   DW_AT_name        : (indirect string, offset: 0x1153): inode
       <1975>   DW_AT_byte_size   : 672
       <1977>   DW_AT_decl_file   : 31
       <1978>   DW_AT_decl_line   : 611
       <197a>   DW_AT_sibling     : <0x1c4f>
    <2><197e>: Abbrev Number: 27 (DW_TAG_member)
       <197f>   DW_AT_name        : (indirect string, offset: 0x7d00): i_mode

etc.

## Reverse-Engineered Stuff

### Structs

#### ebc_info

See https://gitlab.com/smaeul/ebc-dev/-/blob/main/auto_image.h#L124, which is based on [the v1.04 BSP Linux driver](https://gitlab.com/pine64-org/quartz-bsp/linux-next/-/commits/2de5fb11a888c37f366642544e5a53ec2faae32d).

#### ebc

See https://gitlab.com/smaeul/ebc-dev/-/blob/main/auto_image.h#L200, which is based on [the v1.04 BSP Linux driver](https://gitlab.com/pine64-org/quartz-bsp/linux-next/-/commits/2de5fb11a888c37f366642544e5a53ec2faae32d).

#### rkf_waveform

{{< admonition type="note" >}}
 all known waveform data files are the "PVI" variant, not the "RKF" variant.
{{< /admonition >}}

```C
struct rkf_waveform {
    int length,
    char[16] format,
    char[16] version,
    char[16] timeandday,
    char[16] panel_name,
    char[16] panel_info,
    char[64] full_version,
    char[64] reset_temp_list,
    char[64] gc16_temp_list,
    char[64] gl16_temp_list,
    char[64] glr16_temp_list,
    char[64] gld16_temp_list,
    char[64] du_temp_list,
    char[64] a2_temp_list,
    uint[64] reset_list,
    uint[64] gc16_list,
    uint[64] gl16_list,
    uint[64] glr16_list,
    uint[64] gld16_list,
    uint[64] du_list,
    uint[64] a2_list
}
```

### Enums

#### rkf_waveform_type

```C
enum rkf_waveform_type {
    RKF_WF_RESET = 0,
    RKF_WF_DU    = 1,
    RKF_WF_GC16  = 2,
    RKF_WF_GL16  = 3,
    RKF_WF_GLR16 = 4,
    RKF_WF_GLD16 = 5,
    RKF_WF_A2    = 6
}
```
