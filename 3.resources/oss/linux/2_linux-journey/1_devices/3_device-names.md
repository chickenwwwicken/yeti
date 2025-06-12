Here are the most common device names that you will encounter:

##### SCSI Devices
If you have any sort of mass storage on your machine, 
chances are it is using the SCSI ("scuzzy") protocol. 
SCSI stands for Small Computer System Interface, 
it is a protocol used for allow communication between disks, printers, scanners, and other peripherals in your system.
You may have heard of SCSI devices which aren't actually in use in modern systems, 
however our Linux systems correspond SCSI disks with hard disk drives in `/dev` .
They are represented by a prefix of `sd` (SCSI disk) : 

Common SCSI device files: 
- `/dev/sda` - First hard disk
- `/dev/sdb` - Second hard disk
- `/dev/sda3` - Third partition on the first hard disk

##### Pseudo Devices
Aren't really physically connected to your system,
most common pseudo devices are character devices:
- `/dev/zero` - accepts and discards all input, produces continuous stream of NULL (zero value) bytes
- `/dev/null` - accepts and discards all input, produces no output
- `/dev/random` - produces random numbers

#### PATA Devices
Sometimes in older systems you may see hard drives being referred to with an `hd` prefix:
- `/dev/hda` - First hard disk
- `/dev/hdd2` - Second partition on 4th hard disk

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/1_devices/2_device-types]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/1_devices/4_sysfs]]
