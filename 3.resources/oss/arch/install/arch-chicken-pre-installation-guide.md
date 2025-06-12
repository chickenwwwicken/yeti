# 1 Download .iso from any http mirror
I used usa -> constant
if it takes more than one minute use another one...

# 2 Download iso pgp signature + sha256
From the cheksums part in the official arch install guide, download:
- ISO PGP signature
- sha256 

# 3 Create sha.txt
1. make new text file in /Downloads (or whatever dir contains .sig and .iso) 
2. copy the sha256 from official Arch website and paste it in sha.txt
3. paste the complete name of the .iso file after the sha256 , separated by two spaces

# 4 Verify sha.txt
``` bash
sha256 -c sha.txt
```
Expected output: `archlinux-version-x86_64.iso: OK`

# 5 Verify the signature
``` bash
gpg --keyserver-options auto-key-retrieve --verify archlinux-_version_-x86_64.iso.sig
```
Expected output: 
``` bash
good signature from "Pierre Schmitz <pierre@archlinux.org>" [unkown]
WARNING: The key's User ID is not certified with a trusted signature!
There is no indication that the signature belongs to the owner. 
```

# 6 Install to USB
There are several ways to flash the image into the USB...
##### Using basic command line utilities
This method is recommended due to its simplicity and universal availability, since these tools are part of coreutils. 

Note: This will delete all data on USB
1. Find the name of your USB drive with `ls -l /dev/disk/by-id/usb-*`
2. Check if it is mounted with `lsblk`
3. if mounted, `sudo umount /dev/sdx` - replace x with ur name

if problems with mount/unmount: [[___738___1/$cheats/$oss/$linux/2_linux-journey/2_filesystem/6_mount-umount|6_mount-umount]]

4. Run one of the following commands:
replace `/dev/disk/by-id/usb-My_Flash_Drive` with ur drive
example: `/dev/disk/by-id/usb-Kingston_DataTraveler_3.0_2CFDA15C4C131841E90E04E1-0:0`

a. using cat
``` bash
cat path/to/archlinux-version-x86_64.iso > /dev/disk/by-id/usb-My_Flash_Drive
```
in my case this is the command
``` bash
cat /Downloads/archlinux-2025.05.01-x86_64.iso > /dev/disk/by-id/usb-Kingston_DataTraveler_3.0_2CFDA15C4C131841E90E04E1-0\:0
```
takes a while... 

If you need to format the USB because it's not in vfat... (u need dosfstools package)
``` bash
sudo mkfs.vfat -I -F32 -n R118250$ /dev/sda
```

b. using dd
``` bash
sudo dd bs=4M if=/home/chicken/Downnloads/archlinux-version-x86_64.iso of=/dev/disk/by-id/usb-Kingston...0:0 conv=fsync oflag=direct status=progress
```

done with pre installation...

[[arch-chicken-installation-guide]]
