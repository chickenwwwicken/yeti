Let's take a look at some devices

``` bash
ls -l /dev
brw-rw----   1 root disk      8,   0 Dec 20 20:13 sda
crw-rw-rw-   1 root root      1,   3 Dec 20 20:13 null
srw-rw-rw-   1 root root           0 Dec 20 20:13 log
prw-r--r--   1 root root           0 Dec 20 20:13 fdata
```

These columns are as follows from left to right:
- permissions
- owner
- group
- major device number
- minor device number
- timestamp
- device name

Remember in the `ls` command you can see the type of file with the first bit on each line.
Device files are denoted as the following: 
- `c` - character
- `b` - block
- `p` - pipe
- `s` - socket

##### Character Device
These devicess transfer data, 
but one character at a time. 
You'll see a lot of pseudo devices `/dev/null` as char devices, 
these devices aren't physically connected to the machine, 
but they allow the operating system greater functionality.

##### Block Device
These devices transfer data, but in large fixed-size blocks.
You'll most commonly see devices that utilize data blocks as 
block devices, such as harddrives, filesystems, etc. 

##### Pipe Device
Named pipes allow two or more processes to communicate with each other, 
these are similar to character devices, 
but instead of having output sent to a device, 
it's sent to another process.

##### Socket Device
Socket devices facilitate communication between processes, 
similar to pipe devices but they can communicate with many processes at once. 

##### Device Characterization
Devices are characterized using two numbers, 
major device number and minor device number. 
You can see these numbers in the above `ls` example, 
they are separated by a comma. 
For example, let's say a device had the device numbers : 8, 0:

The major device number represents the device driver that is used, 
in this case 8, which is often the major number for `sd` block drives.

The minor number tells the kernel which unique device it is in this driver class, 
in this case 0 is used to represent the first device `a` 

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/1_devices/1_dev-directory]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/1_devices/3_device-names]]
