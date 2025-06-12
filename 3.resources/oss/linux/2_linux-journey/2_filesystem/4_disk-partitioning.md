Let's do some practical stuff with filesystems by working through the process on a USB.

First we'll need to partition our disk. 
There are many tools available to do this:

- `fdisk` - basic command-line partitioning tool
- `parted` - command line tool
- `gparted` - this is the GUI version of parted
- `gdisk` - supports only GPT

Checkout this other file on how to delete partitions

![[$$$/$cheats/$oss/$linux/0_resources/0.1_issues#0.1.2 Deleting all data in disks from a bootable USB]]

** need a more actualized version of this note

#### Partition with `parted`

Launch `parted`

``` bash
sudo parted
```

Similar to `fdisk` on `0.1.2` note
Select the device

``` bash
select /dev/sdb2
```

Replace `sdb2` with the name of the device you'll be working with.

View current partition table

``` bash
(parted) print                                                            

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

Here you will see the available partitions on the device.
The `start` and `end` points are where the partitions take up space on the harddrive,
you'll want to find a good start and end location for your partitions. 

Partition the device

``` bash
mkpart primary 123 4567
```

Now just chose a start and end point and make the partition, you'll need to specify the type of partition depending on what table you used. 

Resize a partition

``` bash
resize 2 1234 3456
```

Select the partition number and then the start and end points of where you want to resize it to.

`parted` is a very powerful tool and you should be careful when partitioning disks


---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/3_anatomy-of-a-disk]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/5_creating-filesyss]]
