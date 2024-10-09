---
title: "Tuning"
draft: false
menu:
  docs:
    title:
    parent: "Pinebook_Pro/Software"
    identifier: "Pinebook_Pro/Software/Tuning"
    weight: 
---

Details on how to get the most out of a [Pinebook Pro](/documentation/Pinebook_Pro).

## Customizing the Pinebook Pro's default Manjaro KDE system

### Watching DRM content (Netflix, etc.)
Most paid online streaming services use Widevine DRM to make their content more difficult to pirate. Widevine is not directly supported on Manjaro KDE, however it is still possible to watch DRM content via the "chromium-docker" package which downloads a 32-bit ARM container and installs Chromium with Widevine inside of that. While not space-efficient, or efficient in general, it’s the recommended solution for watching this content on your Pinebook Pro. You can install this package with:

    sudo pacman -Sy chromium-docker

### Checking GPU capabilities

To see what versions of OpenGL and OpenGL ES are supported by the Pinebook Pro, what driver is in use, and what version of the driver is loaded, install the "mesa-demos" package with:

    sudo pacman -Sy mesa-demos

And then run:

    glxinfo | grep OpenGL

This will give detailed information about your graphics card and driver, useful for debugging.

### Better GPU compatibility and performance

For better graphics performance, you may install the "mesa-git" package, built and supplied in the Manjaro ARM repos. This lets you bring in the latest features, optimizations, and bugfixes for the graphics driver used by the Pinebook Pro. Installation is as simple as:

    pacman -Sy mesa-git

Then you may reboot to load the newer driver.

With Mesa 20.2 there is no longer much reason to use this over the standard mesa package, and applications may occasionally break with mesa-git.

[Reporting bugs](https://docs.mesa3d.org/bugs.html) to the Mesa project will help make sure any problems are quickly fixed.

### OpenGL 3.3 support

By default, with the current state of the Panfrost GPU driver, the Pinebook Pro supports OpenGL 2.1 and OpenGL ES 3.0. If you want to use OpenGL 3.3, you need to set the system-wide environment variable, open the **/etc/environment** file with:

    kate /etc/environment

And then at the bottom of the file, on a new line, add:

    PAN_MESA_DEBUG="gl3"

Then save the file, entering your password when prompted, and reboot the system. When you check your GPU capabilities, it should report OpenGL 3.3 and applications that rely on it should function properly. Note that GL 3.3 support is incomplete and some rendering features do not work yet, notably geometry shaders.

### Install Anbox on Pinebook Pro Manjaro 20.10

[Youtube video on installing Anbox on Pienbook Pro Manjaro Build 20.10 by LivingLinux](https://www.youtube.com/watch?v=EU8_Q11dATs)

## Customizing the Pinebook Pro's previously-default Debian system

Here are some hints on what you can do to customize the Pinebook Pro’s previous factory image (aka [mrfixit2001 debian build](https://github.com/mrfixit2001/debian_desktop))

### Initial user changes, password, name, etc

When you first get your Pinebook Pro, you should consider setting strong passwords and making the default account your own.

* Reboot (this is just to ensure all background processes belong to the user are not running. There are other ways to achieve this but this way is easy)
* Once the machine reboots press Alt-Ctrl-F1 to bring up a text terminal
* Login as root (login: root, password: root)
* Set a strong password for the root user using the following command and it’s prompts:

      # passwd (and follow prompts)
* Rename the rock user to your prefered username (replace _username_ with whatever you like):

      # usermod -l _username_ -d /home/_username_ -m rock
* Rename the rock group to match your preferred username:

      # groupmod -n _username_ rock
* Put your name in the account, (replace "John A Doe" with your name):

      # chfn -f "John A Doe" _username_
* Set a strong password for the normal user:

      # passwd _username_
* Log out of the text terminal:

      # logout
* Press Alt-Ctrl-F7 to go back to the login screen and then login as the normal user
* Open text terminal to fix login error: "Configured directory for incoming files does not exist":

  ```console
  $ blueman-services
  ```

Select "Transfer" tab and set "Incoming Folder" to yourself or if adduser is in the distributions, create an user with `sudo adduser $USER` (fill out variables as required), then add the user to the groups using `sudo adduser $USER $GROUP` by adding one group at a time.

### Changing the default hostname

Debian 9 has a command to allow you to change the hostname. You can see the current settings using:

```console
$ sudo hostnamectl
   Static hostname: Debian-Desktop
         Icon name: computer
        Machine ID: dccbddccbdccbdccbdccbdccbdccbccb
           Boot ID: ea99ea99ea99ea99ea99ea99ea99ea99
  Operating System: Debian GNU/Linux 9 (stretch)
            Kernel: Linux 4.4.210
      Architecture: arm64
```

To change, use this, (with _hostname_ used as the example):

```console
$ sudo hostnamectl set-hostname _hostname_
```

Whence done, you can re-verify using the first example.

Then you should backup and edit your **/etc/hosts** entry’s name:

```console
$ sudo cp -p /etc/hosts /etc/hosts.`date +%Y%m%d`
$ sudo vi /etc/hosts
127.0.0.1	localhost
127.0.0.1	_hostname_
::1		localhost ip6-localhost ip6-loopback
fe00::0		ip6-localnet
ff00::0		ip6-mcastprefix
ff02::1		ip6-allnodes
ff02::2		ip6-allrouters
127.0.1.1       linaro-alip
```

### Disable Chromium browser's prompt for passphrase & password storage

Perform the following steps:

* On the tool bar, hover over the Chromium icon
* Using the right mouse button, select _Properties_
* In the **Command:** line section, add `--password-store=basic` before the `%U`
* Use the **x Close** button to save the change
This will of course, use basic password storage, meaning any saved passwords are not encrypted. Perfectly fine if you never use password storage.

### Changing the boot splash picture

The default boot splash picture can be replaced using the following instructions:

* Install _ImageMagick_ which will do the conversion

  ```console
  $ sudo apt-get install imagemagick
  ```
* Create a 1920 x 1080 picture. For the best results, use a PNG image (It supports lossless compression).
* From the directory in which your new image is stored run the following commands
* Convert your image to the bootsplash raw format using imagemagick convert.

  ```console
  $ convert yoursplashimage.png -separate +channel -swap 0,2 -combine -colorspace sRGB RGBO:splash.fb
  ```
* Create a backup copy of your current splash screen

  ```console
  $ sudo cp /usr/share/backgrounds/splash.fb /usr/share/backgrounds/splash_original.fb
  ```
* Copy your new splash screen into place

  ```console
  $ sudo cp splash.fb /usr/share/backgrounds/splash.fb
  ```
* Set the correct permissions on the splash.fb file

  ```console
  $ sudo chmod 644 /usr/share/backgrounds/splash.fb
  ```
* If you do not want to see kernel console text messages, make sure you don’t have _Plymouth_ installed

### Watching Amazon Prime videos with Chromium

When you create a new user, it will be necessary to launch the Chromium browswer with a specific user agent like below:

    chromium-browser --user-agent="Mozilla/5.0 (X11; CrOS armv7l 6946.63.0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.121 Safari/537.36"

There may be more tweaks needed.

### Enabling text boot time messages

By default, most Linux distributions have a boot screen with a picture. To see all the boot time messages, use one of the following:

#### Debian

* Backup and edit the U-Boot configuration file:

      cp -p /etc/default/u-boot /etc/default/u-boot.`date +%Y%m%d`
      chmod a-w /etc/default/u-boot.`date +%Y%m%d`
      vi /etc/default/u-boot

Remove the _quiet_ and _splash_ parameters. Leave everything else alone.

* Update the U-Boot configuration:

      u-boot-update
* Test and verify you get what you think you should be seeing.

#### Manjaro

* Backup and edit the U-Boot configuration file:

      cp -p /boot/extlinux/extlinux.conf /boot/extlinux/extlinux.conf.`date +%Y%m%d`
      chmod a-w /boot/extlinux/extlinux.conf.`date +%Y%m%d`
      vi /boot/extlinux/extlinux.conf
* Change **console=ttyS2,1500000** to **console=tty1**
* Remove the **bootsplash.bootfile** option and it’s parameter.
* You can add verbose logging by appending **ignore_loglevel** to the line where boot splash was.
* Leave everything else alone.
* Test and verify you get what you think you should be seeing.

## Retro Gaming on the Pinebook Pro

A retro-gaming OS named R-Cade has been made available for the Pinebook Pro, provided by [The Retro Center](https://www.retro-center.com).

R-Cade includes over 100 retro-gaming systems, a lightweight web browser, and includes the latest release of KODI to provide full 4K UHD media playback and streaming.
Streaming options in KODI are provided by various addons, such as Netflix, Disney+, and Amazon Prime.
More information can be found [here](https://www.retro-center.com/about-r-cade/).

Releases can be downloaded from their [GitHub](https://github.com/retro-center/rcade_releases).

## Improving readability

Some people find that a 14" LCD screen with 1080p, (1920 x 1080), has text and icons a bit too small. There are things you can do to make the screen easier to use and read.

* Increase the font size
* Use a font with more pronounced features
* Increase the various window manager sizes (e.g. increase the height of the tool bar)
* Change the color scheme to be easier on the eyes. Higher contrast can help usability.
* Change the window manager’s decorations (e.g. use larger icons)
* Use a workspace manager, with one application per workspace
* When at home or office, use an external monitor
* Change the X-Windows DPI. One such method that someone used successfully, is: `echo "Xft.dpi: 150" >> ~/.Xresources` Change the 150 as desired to get the size adjustment you want.

However, do not change the resolution of the LCD screen, otherwise you may end up with a blank / black screen. If that happens, see this troubleshooting section for the fix: [Blank screen after changing builtin LCD resolution](/documentation/Pinebook_Pro/Troubleshooting/#after_changing_builtin_lcd_resolution_blank_screen)

## Chromium tweaks

### Flags

From the [official Debian image](https://github.com/mrfixit2001/updates_repo/blob/v1.8/pinebook/filesystem/default):

    --disable-low-res-tiling \
    --num-raster-threads=6 \
    --profiler-timing=0 \
    --disable-composited-antialiasing \
    --test-type \
    --show-component-extension-options \
    --ignore-gpu-blacklist \
    --use-gl=egl \
    --ppapi-flash-path=/usr/lib/chromium-browser/pepper/libpepflashplayer.so \
    --ppapi-flash-version=32.0.0.255 \
    --enable-pinch \
    --flag-switches-begin \
    --enable-gpu-rasterization \
    --enable-oop-rasterization \
    --flag-switches-end

Note that in some cases, this may also decrease performance substantially, as observed when using these flags on the Manjaro KDE desktop. Feel free to experiment to find what is smoothest for you personally.

## gVim has performance issue

It appears that using GTK3 can cause very slow scrolling, while Vim in a terminal window works fine.
Simply revert back to using GTK2, (how to do so is somewhat Linux distro-specific).

Another solution may be to run gVim with

    GDK_RENDERING=image

environment variable set. It seems that this improves the performance by reverting back to software-only rendering.

## Kernel options

Here are some Pinebook Pro & its RK3399 SoC Linux specific options. If kernel version, (or version range specific), it should list that information in the description.

To see if a specific feature is enabled in the current kernel, you can use something like this:

```console
$ zgrep -i rockchip_pcie /proc/config.gz
# CONFIG_ROCKCHIP_PCIE_DMA_OBJ is not set
CONFIG_PHY_ROCKCHIP_PCIE=m
```

If it’s listed as `=m`, then it’s a module. You can see if the module is loaded with:

```console
$ lsmod | grep -i rockchip_pcie
phy_rockchip_pcie      16384  0
```

Note modules are not loaded until needed. Thus, we sometimes check the kernel configuration instead to see if a feature is configured first, then see if it’s a module.

### Hardware video decoding

Here is a method to check for hardware video decoding by the VPU. There are special Linux kernel modules that perform this function.

Older systems, such as the previously-default Debian desktop, use the Rockchip-supplied kernel module `rk-vcodec`. To check, something like this can be used:

```console
$ lsmod | grep rk-vcodec
```

or

```console
$ zgrep RK_VCODEC /proc/config.gz
CONFIG_RK_VCODEC=y
```

Note that in the above example, the Rockchip video CODEC is not built as a module, but included into the kernel. Thus, it does not show up in the list modules check.

Newer systems may use a different option as in the configuration below:

```console
$ zgrep HANTRO /proc/config.gz
CONFIG_VIDEO_HANTRO=m
CONFIG_VIDEO_HANTRO_ROCKCHIP=y
```
