Filesystems can vary with how they are structured, 
but for the most part they should conform to the Filesystem Hierarchy Standard.

Do an `ls -l /` to see the directories listed under the root directory,
yours may look different than mine, 
but the directories should for the most part look like the following:

- `/` - root directory of the entire filesystem hierarchy , everything nested here
- `/bin` - Essential ready-to-run programs (binaries), includes `ls` `cp`
- `/boot` - Contains kernel boot loader files. 
- `/dev` - Device files
- `/etc` - Core system configuration dir, should only hold config files and not binaries
- `/home` - personal dirs for users, holds ur documents, files, settings.
- `/lib` - holds library files that binaries can use
- `/media` - used as an attachment point for removable media like USB drives
- `/mnt` - Temporarily mounted filesystems
- `/opt` - Optional application software packages.
- `/proc` - information about currently running processes
- `/root` - the root user's home directory
- `/run` - information about the running system since the last boot
- `/sbin` - contains essential binaries, usually can only be ran by root
- `/srv` - site-specific data which are served by the system.
- `/tmp` - storage for temporary files
- `/usr` - meant for user installed software and utilities like `/usr/bin` `/usr/local`
- `/var` - Variable directory, used for system logging, user tracking, caches. Basically anything that is subject to change all the time

---
[[$$$/$cheats/$oss/$linux/0_resources/0.2_contents]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/2_filesys-types]]
