There are many different filesystem implementations available. 
Different filesystems have different ways of organizing their data.
Apps need a way to deal with the different operations. 
So there is something called the Virtual File System (VFS) abstraction layer.
It's a layer between applications and the different filesystem types, 
so no matter what filesystem you have, your apps will be able to work with it.

You can have many filesystems on your disks, depending on how they are partitioned.

#### Journaling
Journaling comes by default on most filesystem types, 
but just in case it doesn't, you should know what it does. 
Let's say yyou're copying a large file and all of a sudden you lose power. 
Well if you on a non-journaled filesystem, 
the file would be inconsistent and then when you boot back up, 
your system would perform a filesystem check to make sure everything is ok. 
However the repairs would take a while depending on how large it was. 

If you were on a journaled system, before your machine even begins to copy the file,
it will write what you're going to be doing in a log file (journal).
Now when you actually copy the file, 
once it completes, the journal marks that task as complete. 
The filesys is always in a consistent state because of this, 
so it will know exactly where you left off if your machine shutdown suddenly.
This also decreases the boot time because instead of checking the entire filesys,
it just looks at your journal. 

#### Common Desktop Filesystem Types
- `ext4` - This is the most current version of the native Linux filesystems. It is compatible with the older `ext2` and `ext3` versions. It supports disk volumes up to 1 exabyte and file sizes up to 16terabytes and much more. It is the standard choice for Linux filesystems.
- `Btrfs` - "Better on Butter FS" it is a new filesystem for Linux that comes with snapshots, incremental backups, performance increase and much more. It is widely available, but not quite stable and compatible yet.
- `XFS` - High performance journaling file system, great for a system with large files such as a media server. 
- `NTFS` and `FAT` - Windows filesystems
- `HFS+` - Macintosh filesystem

#### To checkout what filesystems are on your machine

``` bash
df -T
```

![[$$$/$cheats/$oss/$linux/0_resources/media/Pasted image 20240912140009.png]]
The `df` command reports file system disk space usage and other details about your disk.

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/1_filesys-hierarchy]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/3_anatomy-of-a-disk]]
