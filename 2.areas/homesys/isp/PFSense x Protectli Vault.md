[Access Base](https://kb.protectli.com/?intsrc=us)

**2 Ways to do it**
- install pfSense CE using only the COM port (**Serial Version**)
- install pfSense CE by using a VGA or HDMI monitor (**VGA Version**)

The easiest is most likely to be error-free is with a HDMI or Display Port monitor 
(for this download use the **VGA version of the installer**)

If the user chooses to install pfSense CE with the serial console port on the Vault, the user MUST use the **serial version of the installer**


It is recommended to download the .iso image for the newest version of pfSense from this link:  https://sgpfiles.netgate.com/mirror/downloads/ (These are hosted on the official Netgate website). 

The same image can be used to install pfSense CE on any of the Vault platforms

**Note for the balenaEtcher users: Use the .iso image opposed to the .img image to properly burn the image to your USB.**

You can use balenaEtcher or Rufus to transfer the installation image to a USB drive. We use balenaEtcher.

### Installing on Vault

- Verify the Vault is powered off 
- Verify a Monitor is conected
- Verify the wired USB keyboard is plugged in (ignore if using serial connection)
- While powering up the Vault, hold <f11> key to open boot options
- Select USB drive (UEFI)
- Review and Accept
- Select **Install** option

