Hard disks can be subdivided into partitions, 
essentially making multiple block devices. 

Recall such examples as `/dev/sda1` and `/dev/sda2` 
`/dev/sda` is the whole disk, but `/dev/sda1` is the first partition on that disk.
Partitions are extremely useful for separating data and if you need a certain filesystem, 
you can easily create a partition instead of making the entire disk one filesystem type.

#### Partition Table
Every disk will have a partition table, 
this table tells the system how the disk is partitioned. 
This table tells you where partitions begin and end, which are bootable,
what sectors of the disk are allocated to what partition, etc.

There are two main partition table schemes used:
- Master Boot Record (MBR)
- GUID Partition Table (GPT)

#### Partition
Disks are compromised of partitions that help us organize our data. 
You can have multiple partitions on a disk and they can't overlap each other. 
If there is space that is not allocated to a partition, then it is known as free space.
The types of partitions depend on your partition table. 
Inside a partition, you can have filesystem or dedicate partition to other things like swap.

##### MBR
- Traditional partition table, was used as the standard
- Can have primary, extended and logical partitions
- MBR has a limit of four primary partitions
- Additional partitions can be made by making a primary partition into an extended partition (there can only be one extended partition on a disk.) Then inside the extended partition you add logical partitions. The logical partitions are used just like any other partition. 
- Supports disks up to 2 terabytes.

##### GPT
- GUID Partition Table is becoming the new standard for disk partitioning
- Has only one type of partition and you can make many of them
- Each partition has a globally unique ID (GUID) 
- Used mostly in conjunction with UEFI based booting 

#### Filesystem Structure
We know from our previous lesson that a filesystem is an organized collection of 
files and directories.
In its simplest form, it is comprised of a database to manage files and the actual files
themselves, however we're going to go into a little more detail.
- Boot Block - This is located in the first few sectors of the filesystem, and it's not really used by the filesystem. Rather, it only contains information used to boot the operating system. If you have multiple partitions, they will have boot blocks, but many of them are unused
- Super Block - This is a single block that comes after the boot block, and it contains information about the filesystem, such as the size of the inode table, size of logical blocks and the size of the filesystem.
- Inode table - Think of this as the database that manages our files. Each file or directory has a unique entry in the inode table and it has various information about the file. 
- Data Blocks - This is the actual data for the files and directories


#### MBR Partitioning Table
Let's take a look at the different partition tables. 
Below is an example of a partition using the MBR partitioning table (msdos).
You can see the primary, extended and logical partitions on the machine. 

``` bash
pete@icebox:~$ sudo parted -l

Model: Seagate (scsi)
Disk /dev/sda: 21.5GB
Sector size (logical/physical): 512B/512B
Partition Table: msdos

Number  Start   End     Size    Type      File system     Flags
 1      1049kB  6860MB  6859MB  primary   ext4            boot
 2      6861MB  21.5GB  14.6GB  extended
 5      6861MB  7380MB  519MB   logical   linux-swap(v1)
 6      7381MB  21.5GB  14.1GB  logical   xfs
```

This is example of GPT using just a unique ID for the partitions.

``` bash
Model: Thumb Drive (scsi)
Disk /dev/sdb: 4041MB
Sector size (logical/physical): 512B/512B
Partition Table: gpt

Number  Start   End     Size     File system  Name        Flags
 1      17.4kB  1000MB  1000MB                first
 2      1000MB  4040MB  3040MB                second
```

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/2_filesys-types]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/4_disk-partitioning]]
