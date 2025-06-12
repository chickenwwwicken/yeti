There are a few tools you can use to see the utilization of your disks:

``` bash 
df -h

Filesystem     1K-blocks    Used Available Use% Mounted on
/dev/sda1       6.2G  2.3G  3.6G  40% /
```

`df` command shows you the utilization of your currently mounted filesystems.
`-h` flag gives you a human readable format.
You can see what the device is, 
and how much capacity is used and available. 

Let's say your disk is getting full and you wanna know what files or dirs are taking up that space, 
for that you can use the `du` command.

``` bash
du -h
```

This shows you the disk usage of the current directory you are in, 
you can take a peek at the rood directory with `du -h / ` but that can get a lil cluttered. 

Both of these commands are so similar in syntax it can be hard to remember which to use,

`df` - disk free
`du` - disk usage

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/8_swap]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/10_filesys-repair]]
