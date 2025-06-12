## yay
`git clone https://aur.archlinux.org/yay.git`
`cd yay`
`makepkg -si`

yay (nothing else) -- updates repos and system  + AUR packs

yay (search terms) -- searches for packages in the repos and AUR

yay -S or -U -R same as the pacman equivalents, but with AUR support 

##### Useful commands:
yay -Syu -- updates the entire system like pacman, but also updates AUR
yay-c 0-- Cleans unused packages
yay -Sc Cleans pacman & AUR package caches

yay --noconfirm -- skips al yn and other checks

yay -G Downloads PKGBuilds for an AUR package
yay -P --stats -- list useful statistics regarding system packages
