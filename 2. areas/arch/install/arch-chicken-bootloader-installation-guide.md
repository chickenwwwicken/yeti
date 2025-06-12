A boot loader is a piece of software started by the firmware ([BIOS](https://en.wikipedia.org/wiki/BIOS "wikipedia:BIOS") or [UEFI](https://wiki.archlinux.org/title/UEFI "UEFI"))
It is responsible for loading the kernel with the wanted [kernel parameters](https://wiki.archlinux.org/title/Kernel_parameters "Kernel parameters") and any external initramfs images. In the case of UEFI, the kernel itself can be directly launched by the UEFI using the [EFI boot stub](https://wiki.archlinux.org/title/EFI_boot_stub "EFI boot stub"). A separate boot loader or boot manager can still be used for the purpose of editing kernel parameters before booting. Systems with [32-bit IA32 UEFI](https://wiki.archlinux.org/title/Unified_Extensible_Firmware_Interface#UEFI_firmware_bitness "Unified Extensible Firmware Interface") require a boot loader that supports mixed mode booting.

![[bootloader.arch-install.png]]

# 1 Make sure we in EFI system
`mount -t efivarfs efivarfs /sys/firmware/efi/efivars/`

to confirm:
`ls /sys/firmware/efivars/`
output: lots a stuff

# 2 Download bootloader
`bootctl install`

output: 
```
! Mount point '/boot' which backs the random seed file is world accessible, which is a security hole! ! 
! Random seed file '/boot/loader/.#bootctlrandom-seed1aa31c1875737381' is world accessible, which is a security hole! ! 
```
To fix this I did:
1. `nano /etc/fstab`
2. edited fmask code to 0137
3. edited dmask code to 0027
4. umount /boot
5. mount /boot
6. "fstab has been modified, but systemd still uses the old version; use 'systemctl daemon-reload'to reload"
7. `exit` - to go back to root
8. `systemctl daemon-reload`
9. `arch-chroot /mnt` - to go back to the system
10. `bootctl install` - no more flags!! gud
11. `nano /etc/fstab` -  to confirm changes

# 3 write boot entries
`nano /boot/loader/entries/arch.conf`
add this: 
```
title arch
linux /vmlinuz-linux
initrd /initramfs-linux.img
```
save file.

# 4 glorious eggroll arcane scrypt
`echo "options root=PARTUUID=$(blkid -s PARTUUID -o value /dev/sdb3) rw" >> /boot/loader/entries/arch.conf`

you want your file to have something like 
`options root=PARTUUID=fs9y7238sd-fhas;kh378237 rw`
that tells u ur script worked...

# 5 internet connection
install package for network connections
`sudo pacman -S dhcpcd`

enable dhcpcd - and create symlink
`sudo systemctl enable dhcpcd@enp8s0.service` 
output: `Created symlink '/etc/systemd/system/multi-user.target.wants/dhcpcd@enp8s0.service -> 'usr/lib/systemd/system/dhcpcd@.sercive

to know which to enable run this:
`ip link` - and then select the network u use, in my case enp8s0.

install networkmanager
`sudo pacman -S networkmanager`
enable networkmanager
`sudo systemctl enable NetworkManager.service`
output: `created symlink`x3 

# 6 Reboot
`exit`- to exit the chroot environment
`umount -R /mnt` - this allows noticing any "busy" partitions

`reboot`

---
[[arch-chicken-post-installation-guide]]
