Import the Tails signing key in your GnuPG keyring:
``` bash
wget https://tails.net/tails-signing.key
```
``` bash
gpg --import < tails-signing.**key**
```
Install the Debian keyring. It contains the OpenGPG keys of all Debian devs: 
``` bash
sudo apt update && sudo apt install debian-keyring
```
Import the OpenPGP key of chris lamb, former debian project leader, frrom the Debian keyring into your keyring:
``` bash
gpg --keyring=/usr/share/keyrings/debian-keyring.gpg --export chris@chris-lamb.co.uk | gpg --import
```
Verify the certifications made on the Tails signing key: 
``` bash
gpg --keyid-format 0xlong --check-sigs A490D0F4D311A4153E2BB7CADBB802B258ACD84F
```
In the output of this command, look for the following line:
``` bash
sig!2        0x1E953E27D4311E58 2020-03-19  Chris Lamb <chris@chris-lamb.co.uk>
```
Here, `sig!2` means that Chris lamb verified and certified the Tails signing key with his key and a level 2 check. 

It is also possible to verify the certifications made by other people. Their name and email address appear in the list of certification if you have their key in your keyrinng. 

The line `175 signatures not checked due to missing keys` or similar refers to the certificaations (also called signatures) made by other public keys that are nnot in your keyring. This is not a problem.

Certify the Tails signing key with your own key:
``` bash
gpg --lsign-key A490D0F4D311A4153E2BB7CADBB802B258ACD84F
```
Download tails: Download the usb image: 
``` bash
wget --continue https://download.tails.net/tails/stable/tails-amd64-6.12/tails-amd64-6.12.img
```
Verify your download:
In this step you will verify your download using the Tails signing key. 
Download the signature of the USB image: 
``` bash
wget https://tails.net/torrents/files/tails-amd64-6.12.img.sig
```
Verify tthat the USB image is signed by the Tails signing key. 
``` bash
TZ=UTC gpg --no-options --keyid-format long --verify tails-amd64-6.12.img.sig tails-amd64-6.12.img
```
The output of this command should be the following: 
``` bash
gpg: Signature made Wed 05 Feb 2025 11:34:38 UTC  
gpg:                using EDDSA key 4FDE1D065B10343FBD642A14BC8BD3DAC9CD2979  
gpg: Good signature from "Tails developers (offline long-term identity key) <tails@boum.org>" [full]  
gpg:                 aka "Tails developers <tails@boum.org>" [full]
```
Install tails using `dd`
Make sure that the usb stick on which you want to install tails is unplugged. 
Execute the follwing command:
``` bash
ls -1 /dev/sd?
```
It returns a list of the storage devices on the system. For example:
``` bash
dev/sda
```
Plug in the USB stick on which you want to install Tails. 
(All the data on this USB will be lost.)

Execute the same command:
``` bash
ls -1 /dev/sd?
```
Your usb appears as a new device in the list. 
``` bash
/dev/sda
/dev/sdb
```
Take note of the device name of your USB stick. 
In this example, the device name of the Usb stick is `/dev/sdb`. Yourrs might be differrent.
If you unsure about the device name, you shhould stop proceeding or you risk overwriting any hard disk on the system. 

Execute the following commands to copy the USB image that you downlooaded earlier to the USB stick. 

Replace:
- `tails.img` with the path to the USB image
- `device` with the device name found in step 5 
``` bash
dd if= tails.img of=device bs=16M oflag=direct status=progress
```
you should get something like this: 
``` bash
dd if=/home/user/tails-amd64-3.12.img of=/dev/sdb bs=16M oflag=direct status=progress
```
If you geet a permission denied error, try adding sudo at the beginning of the command

The installation is complete after the command prompt reappears. 

![[congrats-taails.mp4]]