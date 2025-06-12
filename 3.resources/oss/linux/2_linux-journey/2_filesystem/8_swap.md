``` bash
Number  Start   End     Size    Type      File system     Flags
 5      6861MB  7380MB  519MB   logical   linux-swap(v1)
```

What is this `swap` partition? 
Well swap is what we used to allocate virtual memory to our system. 
If you are low on memory, the system uses this partition to "swap" pieces of memory of idle processes to the disk, so you're not bogged from memory.

#### Using a partition for swap space

Let's say we wanted to set our partition of `/dev/sdb2` to be used for `swap` space.

1. First make sure we don't have anything on the partition
2. Run : `mkswap /dev/sdb2` to initialize swap areas
3. Run : `swapon /dev/sdb2` this enables the swap device
4. If want the swap partition to persist on bootup, you need to add an entry to the `etc/fstab` file. `sw` is the filesystem type that you'll use.
5. To remove swap: `swapoff /dev/sdb2` 

Generally you should allocate about twice as much swap space as you have memory. 
But modern systems today are usually powerful enough and have enough RAM as it is.

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/7_etc-fstab]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/9_disk-usage]]
