Sometimes our filesystem isn't always in the best condition, 
if we have a sudden shutdown, our data can become corrupt. 
It's up to the system to try to get us back in a working state( although we sure can try ourselves).

`fsck` - file system check command is used to check the connsistency of a filesystem.
It can even try to repair it for us. 

Usually when you boot up a disk, `fsck` will run before your disk is mounted to make sure ev ok.
Sometimes though, your disk is so bad that you'll need to manually do this. 
However, be sure to do this while you are in a rescue disk or somewhere where you can access your filesystem without it being mounted. 

``` bash
sudo fsck /dev/sda
```

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/9_disk-usage]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/11_inodes]]
