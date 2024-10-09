---
title: "External flash partitioning"
draft: false
menu:
  docs:
    title:
    parent: "PineTime/Flashing"
    identifier: "PineTime/Flashing/External_flash_partitioning"
    weight: 
---

## The partition table

Partitions on a storage (disk of flash memory) have different sizes depending on the type of data they contain. Size and location for those partitions could vary along the time, specially if the operating systems ("firmware" on embedded systems) are changed or the same OS is upgraded and it has the need of reestructuring the partitions. In any case, an index has to describe the partition structure somewhere.

What is the basic info to know about a storage partitions?

* The offset address: indicates where the partion starts on the storage.
* The partition size: how long is the partition from its offset address.
* The partition type: identifies what is the usage of the data contents.

### Where to store the partition entries

To put that index of partitions hardcoded with the firmware is a bad idea. How to know if those partitions are initializaded with the expected data type? What if the user decides to try another OS and it initializates the the partitions just like the developer has decided to do so? Installed OS has to check the rightness of the storage on every boot? Definitely, the index of partitions must be out of the own OS code in order to keep organized the data on the flash memory.

#### PC

Nowadays, personal computers use partition tables on every disk (see [GPT](https://en.wikipedia.org/wiki/GUID_Partition_Table) and [MBR](https://en.wikipedia.org/wiki/Master_boot_record#PT)). This partitions tables are located very close to the beginning of the disk (reserving some initial sector of bytes for old bootloaders). However, this partition tables are designed for very large disks and they have some complexity related to PC and its computer history, not really needed for flash memories.

#### SBC

Single board computers and embedded systems with the [U-Boot bootloader](https://en.wikipedia.org/wiki/Das_U-Boot) store the partition index as parameters in the _mtdparts_ environment variable and it is passed to the OS as argument. This environment is hardcoded or stored in a defined partition as text. More recently, they use [Device tree](https://en.wikipedia.org/wiki/Device_tree) but this is also stored in a partition.

#### ESP32

[ESP32](https://en.wikipedia.org/wiki/ESP32) is a MCU managing partitions without hardcoded information and it is a good example to examine. It defines a [partition table](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-guides/partition-tables.html) of 3Kb length at a fixed position with capacity to define 95 partitions. Maybe some excessive but the interesting thing is that partition table follow the pattern "offset-size-type" as basic information.

The summing-up is that every system using partion index and not hardcoded stores the partition entries in some storage space and, this partition table, can be considered a little partition too. It is located in a well-know offset address of the flash storage.

### Paper

PineTime is a device under open development and it offers undreamed possibilities to develop and to flash several firmwares by users. It might be convenient that external storage (SPI flash) can be accessed by using a partition table so, different firmwares will be able to share partitions with user information, settings, bluetooth bindings, calibration parameters.

For example, it is possible to organize the flash to save a logo shown by the bootloader. And it doesn’t mean a mandatory requirement at the moment but bootloader or application can be changed and they will be able to found the logo to show or save a customized one.

What is the cost of managing a partition table? In this case, community (developers) should be discuss and publish a paper with a proposal for the partition table structures and implement in their firmware for the Pinetime. It must be simple and suitable in order to organize the flash storage in partitions without more overhead than read the partition table, look for the partitions those are interested in and use them.

## Partition table draft-#0

Location of partition table: first page of external flash (256 bytes).

### C structures

C code:

```
	#define OFFSET_T uint32_t
	#define SIZE_T   uint32_t

	/* bits 0-7 is type, bits 8-15 is subtype, bits 16-31 are flags */
	#define TYPE_T   uint32_t

	struct partition_entry_t {
	    OFFSET_T offset;
	    SIZE_T size;
	    TYPE_T type;   
	};

	struct partition_table_t {
	    uint32_t magic_bytes;           /* always 0x50494e45 ("PINE") */
	    uint32_t reserved[2];           /* reserved, do not use */
	    partition_entry_t entries[20];  /* 20*sizeof(partition_entry_t) == 240 */
	    uint32_t checksum;              /* CRC-32 MPEG2 variant (used by MCU bootloader) */
	};

	#define PARTITION_TYPE_NOT_USED		0x00
	#define PARTITION_TYPE_BOOT_LOGO 	0x01
	#define PARTITION_TYPE_FACTORY_IMG 	0x02
	#define PARTITION_TYPE_LITTLE_FS 	0x03

```
