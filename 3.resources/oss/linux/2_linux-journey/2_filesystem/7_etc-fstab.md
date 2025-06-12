`/etc/fstab` 

When we wanna automatically mount filesystems at startup,
we can add them to a files called `/etc/fstab` short for filesystem table. 
This file contains a permanent list of filesystems that are mounted.

``` bash
pete@icebox:~$ cat /etc/fstab

UUID=130b882f-7d79-436d-a096-1e594c92bb76 / ext4 relatime,errors=remount-ro 0     1
UUID=78d203a0-7c18-49bd-9e07-54f44cdb5726 /home  xfs  relatime   0   2
UUID=22c3d34b-467e-467c-b44d-f03803c2c526 none   swap    sw   0    0
```

Each line represents one filesystem, the fields are:

- `UUID` - Device ID
- Mount point - Directory the filesystem is mounted to ( `/` - `/home` `/none` )
- Filesystem type - (`ext4` `xfs` `swap`)
- Options - other mount options, see manpage for more details.
- Dump - default to `0`
- Pass - Used by `fsck` to decide what order filesystems should be checked, if value=0 won't be checked

To add an entry, just directly modify the `/etc/fstab` file using the entry syntax above. 
Be careful when modifying this file, 
you could potentially make your life a little harder if you mess up.

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/6_mount-umount]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/8_swap]]
