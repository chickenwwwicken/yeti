This guide will cover the basic install 
with the option of encrypting the partition.
At times you may have snsitive data you would prefer to encrypt using Full Disk Encryption *FDE* 
You can initiate an LVM encrypted install on either Hard Disk or USB

You need compatible computer hardware. 
 Where possible recommended to use x86_64/64-bit amd64 images. 
## System Requirements

The installation requirements for Kali Linux will vary depending on what you would like to install and your setup. For system requirements:

- On the low end, you can set up Kali Linux as a basic Secure Shell (SSH) server with no desktop, using as little as 128 MB of RAM (512 MB recommended) and 2 GB of disk space.
- On the higher end, if you opt to install the default Xfce4 desktop and the kali-linux-default metapackage, you should really aim for at least 2 GB of RAM and 20 GB of disk space.
	- When using resource-intensive applications, such as Burp Suite, they recommend at least 8 GB of RAM (and even more if it is a large web application!) or using simultaneous programs at the same time.

## Installation Prerequisites

This guide will make also the following assumptions when installing Kali:
- Using the amd64 installer image. 
- CD/DVD drivd / USB boot support
- Single disk to install to.
- Connected to a network (with DHCP & DNS) which has outbound Internet Access.

## Preparing for the Installation. 

1. [Download Kali Linux](https://www.kali.org/docs/introduction/download-official-kali-linux-images/)  ->  [[$verifying-kali-image]]