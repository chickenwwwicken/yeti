Before you can view the contents of your filesystem, 
you will have to mount it. 
To do that I'll need the device location, the filesystem type and a mount point, 
the mount point is a directory on the system where the filesystem is going to be attached.
So we basically want to mount our device to a mount point. 

First create the mount point, in our case `mkdir/mydrive`

``` bash
sudo mount -t ext4 /dev/sdb2 /mydrive
```

When we go to `/mydrive` we can see our filesystem contents, 
`-t` specifies the type of filesystem, then device location, then the mount point. 

To unmount a device from a mount point:

``` bash
sudo umount /mydrive
# or
sudo umount /dev/sdb2
```

The kernel will name devices in the order it finds them. 
What if our devvice name changes for some reason after we mount it?
Well fortunately , you can use a device's universally unique ID (UUID) instead of a name.

To view the UUIDS on your system for block devices: 

``` bash
sudo blkid

/dev/sda1: UUID="130b882f-7d79-436d-a096-1e594c92bb76" TYPE="ext4" 
/dev/sda5: UUID="22c3d34b-467e-467c-b44d-f03803c2c526" TYPE="swap" 
/dev/sda6: UUID="78d203a0-7c18-49bd-9e07-54f44cdb5726" TYPE="xfs" 
```

We can see our device names, their corresponding filesystem types and their UUIDs.
Now when we want to mount something, we can use:

``` bash
sudo mount UUID=130b882f-7d79-436d-a096-1e594c92bb76 /mydrive
```

Most of the time you won't need to mound devices via their UUIDs,
it's much easier to use the device name and often times the OS
will know to mount common devices like USB drives. 
If you need to automatically mount a filesystem at startup though, 
like if you added a secondary hard drive, 
you'll want to use the UUID.

--- 
had problems mounting and umounting a usb:
When naming USB is sbetter not to use special characters:

This error occurred because of not using ""  
command: ``` sudo mount /dev/sdb1 /media/user1/'R\x24\x24\x24' ``` 
output: ``` mount: /media/chicken/R\x24\x24\x24: mounnt point does not exist. dmesg(1) may have more information after failed mount system call. ```

The error occurs because the mount directory `/media/chickn/R\x24\x24\x24` doesn't exist. 
Here's how to fix it 
1. Create the mount point with the correct name. Since `\x24` represents `$` in hex, use quotes to handle special characters:
``` bash
sudo mkdir -p "/media/chicken/R$$$"
```
(The -p flag creates parent directories if needed.)
2. Mount the USB drive to the newly created directory:
``` bash 
sudo mount /dev/sdb1 "/media/chicken/R$$$"
```
The mount command requires the target directory to exist beforehand. 
Special chaaracters like $ must be  properly escaped or enclosed in quotes to avoid shell iterpretation. 

Foir some reason it's mounted on /media/chicken/R1118250$
Linux changed the name based on some auto-mounting settings... anyway...

It didn't give me access to the usb contents, and the user was set to root instead of chicken, like the other usb i have connected, `ls -la /media/chicken` outputs:
``` 
drwxr-x---+ 4 root    root     4096  .
drwxr-xr-x  4 root    root     4096  ..
drwxr-xr-x  3 chicken chicken 32768  CHICKEN (usb1)
drwxr-xr-x  9 root    root    32768 'R118250$'
```
##### to change the user of a drive:
unmount the drive
``` bash
sudo umount /dev/sdb1 
```
mount again with uid and umask options:
``` bash
sudo mount -o uid=chicken,umask=000 /dev/sdb1 /media/chicken/R118250$
```


---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/5_creating-filesyss]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/7_etc-fstab]]
