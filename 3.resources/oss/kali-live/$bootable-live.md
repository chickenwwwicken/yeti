The fastest method, for getting up and running with Kali Linux is to run it "live" from a USB drive.
This method has several advantages:

- Non-destructive - it makes no changes to the host system's hard drive or installed OS, and to go back to normal operations, you simply remove the "Kali Live" USB drive and restart system.
- Portable - you can carry Kali Linux in your pocket and have it running in minutes on a system.
- Customizable - you can [roll your own custom Kali Linux ISO image](https://www.kali.org/docs/development/live-build-a-custom-kali-iso/) and put it in USB
- Potentially persistent - with a bit of extra effort, you can configure your Kali Linux "live" USB drive to have [persistent storage](https://www.kali.org/docs/usb/usb-persistence/)  so the data you collect is saved across reboots.

In order to do this, we need to create a bootable USB drive which has been set up from an ISO image of Kali Linux.

### What you Need

1. A verified copy of the appropriate ISO image of the latest Kali build image for the system you'll be running it on
2. If you're running under Linux, you can use the `dd` command, which is pre-installed, or use Etcher.
3. A USB thumb drive, 4GB or larger. Systems with a direct SD card slot can use an SD card with similar capacity and the procedure is identical.


### Kali Linux Live USB Install Procedure

#### Creating a Bootable Kali Linux Drive on Linux (DD)

Once you've downloaded and verified your Kali ISO file, 
You can use the `dd` command to copy it over to your USB drive using the following procedure.
Note that you'll need to be running as root, or to execute the `dd` command with `sudo` .
Following example assumes a Linux Mint 17.1 desktop.

**WARNING: Although the process of imaging Kali Linux onto a USB drive is very easy, you can just as easily overwrite a disk drive you didn’t intend to with dd if you do not understand what you are doing, or if you specify an incorrect output path. Double-check what you’re doing before you do it, it’ll be too late afterwards.**

1. Identify the device path to use to write the image to your USB drive. Without the USB dirve inserted into a port, execute the command 

``` bash
sudo fdisk -l
```

![[$$$/$cheats/$oss/$linux/0_resources/media/Pasted image 20240902141849.png]]

You'll get the output that will look something like this, showing a single drive - "/dev/sda" - containing three partitions (/dev/sda1, /dev/sda2, and /dev/sda5)

2. Now, plug your USB drive into an available USB port on your system, and run the same command, `sudo fdisk -l` a second time. Now, the output will look something like this, showing an additional device which wasn't there previously, in this example "/dev/sdb" a 16GB USB drive. 

![[$$$/$cheats/$oss/$linux/0_resources/media/Pasted image 20240902142144.png]]


3. Proceed to CAREFULLY  image the Kali ISO file on the USB device. The example command below assumes that the ISO image you're writing is named "kali-linux-2024.2-live-amd64.iso" and is in your current working directory. The blocksize parameter can be increased, and while it may speed up the operation of the dd command, it can occasionally produce unbootable USB drives, depending on your system and a lot of different factors. The reommended value, "bs=4M" is conservative and reliable. Additionally, the parameter "conv=fsync" makes sure that the data is physically written to the USB drives before the command returns: 

``` bash
kali@kali:~$ dd if=kali-linux-2024.2-live-amd64.iso of=/dev/sdX conv=fsync bs=4M
```

Can take time, over 10 min or more is not unusual.

**While ‘/dev/sdX’ is used in the command, the ‘/dev/sdX’ should be replaced with the proper device label. ‘/dev/sdX’ will not overwrite any devices, and can safely be used in documentation to prevent accidental overwrites. Please use the correct device label.**

The `dd` command provides no feedback until it's completed, but if your drive has an access indicator, you'll probably see it flickering from time to time. 
The time to `dd` the image across will depend on the speed of the system used, USB drive itself, and USB port it's inserted to. 
Once `dd` has finished imaging the drive, it will output something like this:

```
893+1 records in
893+1 records out
3748147200 bytes (3.7 GB, 3.5 GiB) copied, 998.442 s, 3.8 MB/s
```

