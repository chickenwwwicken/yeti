## Download

links:
- [installation guide](https://linuxmint-installation-guide.readthedocs.io/en/latest/)


---
## Instrucciones

 [SomeOrdinaryGamers](https://www.youtube.com/@SomeOrdinaryGamers) 
1. Download Cinnamon on linuxmint.com 

---
#### Integrity Chick

1. Download sha256.txt + sha256.txt.gpg (rightclick save)
2. go to [GNUPG](https://www.gnupg.org/download/index.html)
3. Download this
![[Pasted image 20240626144410.png]]

5. find folder where u saved .txt + .gpg files > right click > open in terminal
6. Type this command (replace filename with ur filename)
- example linuxmint-21.3-cinnamon-64bit.iso
```
CertUtil -hashfile filename.iso SHA256
```

7. copy the result
```
5aa24abbc616807ab754a6a3b586f24460b0c213b6cacb0bf8b9a80b65013ecc
```

8. use this command with your result to check if the key *is* inside sha256sum.txt
```
find "5aa24abbc616807ab754a6a3b586f24460b0c213b6cacb0bf8b9a80b65013ecc" sha256sum.txt
```

9. If you get this , you good, if it did not find it... download another mirror and repeat these steps
```
---------- SHA256SUM.TXT
5aa24abbc616807ab754a6a3b586f24460b0c213b6cacb0bf8b9a80b65013ecc *linuxmint-21.3-cinnamon-64bit.iso
```

---
#### Authenticity Chick

1. c&p this command into the command window and press Enter
```
gpg --keyserver hkps://keyserver.ubuntu.com:443 --recv-key 27DEB15644C6B3CF3BD7D291300F846BA25BAE09
```

![[Pasted image 20240626192321.png]]
(note: change terminal to [[WSL Ubuntu]] terminal)

2. Verify the authenticity of sha256sum.txt

```
gpg --verify sha256sum.txt.gpg sha256sum.txt
```

at this location

```
/mnt/c/Escritorio/mint
```

outuput should say that signature is good and signed with ```A25BAE09``` key

![[Pasted image 20240626193716.png]]

Note: GPG might warn you that the Linux Mint signature is not trusted by ur computer, this is normal.

---

## Create the Bootable Media

easiest way to install Linux Mint is with a USB stick. 

### How to make a bootable USB stick

#### In Linux Mint
Right-click the ISO file and select Make Bootable USB Stick, or launch Menu ‣ Accessories ‣ USB Image Writer.

![[mintstick.webp]]

#### In Windows

- Download [Balena Etcher](https://etcher.balena.io/) 
- Select image
- Select Drive
- Flash

---
# Configuration

1. Install Linux (CD Icon)
2. Reboot
3. MOKey for GPU Nvidia Driver 
4. Reboot
5. Update Manager
6. Update packages
7. Reboot

---
# Installing Software

1. CTRL + ALT + T Open a terminal, 
```

```