# 1 Boot
Select ur USB to boot from there.
Select Arch Linux install medium

# 2 Checks
`ping archlinux.com`  - check internet connection, if response, you good
`efivar -l` - check if booted in UEFI mode, if response, you good

# 3 Prepare drive
`lsblk` - to list all blocks (sda, nvme, loop, etc.)
identify the drive on which u will install arch linux

`gdisk /dev/ur-drive` - utility to prepare the drive for install (replace with ur drive)
output: 
```
GPT fdisk (gdisk) version 1.0.10

Partition table scan:
  MBR: not present
  BSD: not present
  APM: not present
  GPT: not present

Creating new GPT entries in memory

Command (? for help): 
```
press `x`for "expert" 
press z for zap
`about to wipe out GPT on /dev/nvme0n1. Proceed?` - yes
`Blank out MBR?` - yes

# 4 Partitions
go to cgdisk partitioning util - `cgdisk /dev/nvme0n1`

`Warning! Non-GPT or damaged disk detected!` - just press any key to continue

#### first partition (boot)
- `[New]` 
- first sector: `default` - just press enter
- size in sectors: `1024MiB`
- hex code or GUID: `EF00`
- partition name: `boot`

#### second partition (swap)
- `[New]` 
- first sector: `default` - just press enter
- size in sectors: `16GiB`
- hex code or GUID: `8200` - (swap code)
- partition name: `swap`

#### third partition (root)
- `[New]` 
- first sector: `default` - just press enter
- size in sectors: `40GiB`
- hex code or GUID: `8300` - the default - u can just press enter
- partition name: `root`

#### fourth partition (home)
- `[New]` 
- first sector: `default` - just press enter
- size in sectors: `rest of it` - just press enter
- hex code or GUID: `8300` - the default - u can just press enter
- partition name: `home`

#### confirm chances
`[write]` -  to write changes and yes to confrim
`[quit]` - to quit cgdisk

#### lsblk to confirm u got those partitions ready

# 5 Formatting Partitions
boot partition needs to be in FAT32
`mkfs.fat -F32 /dev/nvme0n1p1`
output: `mkfs.fat 4.2 (2021-01-31)

make swap
`mkswap /dev/nvme0n1p2`
output: setting up swapspace version 1, size = 16GiB no label, UUID=uuid

enable swap
`swapon /dev/nvme0n1p2`

##### last to partitions (ext4)
make filesystem extended 4
`mkfs.ext4 /dev/nvme0n1p3`
`mkfs.ext4 /dev/nvme0n1p4`

# 6 Mount File Systems
mount root file system
`mount /dev/nvme0n1p3 /mnt`

make dir and mount boot partition
`mkdir /mnt/boot`
`mount /dev/nvme0n1p1 /mnt/boot`

make dir and mount home partition
`mkdir /mnt/home`
`mount /dev/nvme0n1p4 /mnt/home`

# 7 etc - mirrorlist to download
create a backup of the mirrorlist
`cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.backup`

download contributed scripts and tools for pacman - 
`sudo pacman -Sy pacman-contrib`

rankmirrors to get the top (-n 6) 6 mirrors 
`rankmirrors -n 6 /etc/pacman.d/mirrorlist.backup > /etc/pacman.d/mirrorlist`

install the base package, Linux kernel and firmware for common hardware:
base-devel: extra packages, not essential
edit: ended up not installing base-devel
edit: added amd microcode `amd-ucode`package
`pacstrap -K /mnt base linux linux-firmware base-devel`

# 8 generate fstab file
Generate an fstab file 
`genfstab -U /mnt >> /mnt/etc/fstab`
check the resulting /mnt/etc/fstab file, and edit in case of errors
`nano /mnt/etc/fstab`

# 9 change root to new system
`arch-chroot /mnt`
Here we changed from  `root@archiso`to `[root@archiso /]` - means we are already inside our system = gud

download basic utils like nano and bash completion
`sudo pacman -S nano bash-completion`
edit: we gotta download sudo as well
`pacman -S sudo`

# 10 localization
uncomment `en_US UTF-8`
`nano /etc/locale.gen`

generate locales
`locale-gen`

create `/etc/locale.conf` and add `LANG=en_US.UTF-8` variable into it
`echo LANG=en_US.UTF-8 > /etc/locale.conf`

confirm 
`export LANG=en_US.UTF-8

# 11 Set the time
`ln -sf /usr/share/zoneinfo/Region/City /etc/localtime`

Run hwclock to generate `/etc/adjtime`:
`hwclock --systohc`

This command assumes the hardware clock is set to UTC 
To prevent clock drift, set up time sync using a Network Time Protocol NTP
like systemd-timesyncd

# 12 Network Configuration
in `/etc/hostname` add *yourhostname* 
`echo gigachad > /etc/hostname`

# 13 enable fstrim.timer
The `fstrim.timer` is designed to run the `fstrim.service` once a week to discard unused blocks on filesystems listed in `/etc/fstab`.234 This helps in optimizing the performance of SSDs and other storage devices that support TRIM.

`systemctl enable fstrim.timer`

# 14 enable 32 bit support
inside /etc/pacman.conf
uncomment multilib lines
```
[multilib]
Include ....
```

# 15 Add User
`useradd -m -g users -G wheel,storage,power -s /bin/bash chicken`
and password
`passwd chicken`

# 16 Editing sudo file
enter /etc/sudoers.tmp
`EDITOR=nano visudo`

Uncomment %wheel to allow members of group wheel to execute any command. 

Add this: 
`Defaults rootpw`
will enforce use of rootpw for important stuff

---
[[arch-chicken-bootloader-installation-guide]]
[[arch-chicken-pre-installation-guide]]
