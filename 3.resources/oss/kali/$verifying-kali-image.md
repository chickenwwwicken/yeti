## Verifying Your Downloaded Kali Image

Before you run Kali Linux or install it to your hard disk, 
You wanna be very sure that you got actual Kali Linux. 
Kali Linux is a professional penetration testing and forensics toolkit. 
Critical to have absolute confidence in the integrity of your tools.
If tools are not trustworthy, investigations will not be trustworthy either.

Moreover, as leading pen testing distro, Kali's strengths mean that a bogus version ...
could do a tremendous amount of damage if deployed unwittingly. 

There are plenty of people with plenty of reasons to stick very sketchy stuff into something that looks like Kali, and you dont wanna run dat. 

Avoiding: 
- Only download Kali Linux via the official download page at [kali.org](kali.org/get-kali/) you will not be able to browse to these pages without SSL;  encrypting the connection makes it much harder for an attacker to use a “man-in-the-middle” attack to modify your download.
- There are a few potential weaknesses to even these sources - see the sections on verifying the download with the SHA256SUMS file and its signature against the official Kali Development team private key for something much closer to absolute assurance.
- Once you’ve downloaded an image, and before you run it, always validate that it really is what it’s supposed to be by verifying its checksum using one of the procedures detailed below.

There are several methods for verifying your download. 
Each provides a certain level of assurance, and involves corresponding level of effort.

1. You can download an ISO image from an official Kali Linux "Downloads" mirror, calculate the ISO's SHA256 hash and compare it by inspection with the value listed on the Kali Linux site.  This is quick and easy, but potentially susceptible to subversion via a [[DNS poisoning]]: it assumes that the site to which, for example, the domain "kali.org" resolves is in fact the actual Kali Linux site. If it somehow were not, an attacker could present a "loaded" image and matching SHA256 signature on the fake web page. See the section "Manually Verify the Signature on the ISO (DirectDownload)" below. 
2. You can download an ISO image through the torrents, and it will also pull down a file - unsigned - containing the calculated SHA256 signature. You can then use the shasum command (on Linux and macOS) to automatically verify that the file's computed signature matches the signature in the second file. This is even easier than the "manual" method, but suffers from the same weakness: if the torrent you pulled down is not really Kali Linux, it could still have a good signature. See the section "Verify the Signature on the ISO Using the Included Signature File (Torrent Download)" below. 
3. To be as close to absolutely certain as possible that the Kali Linux download you've obtained is the real thing, you can download both a cleartext signature file and version of the same file that has been signed with the official Kali Linux private key and use GNU Privacy Guard (GPG) to first, verify that the computed SHA256 signature and the signature in the cleartext file match and second, verify that the signed version of the file containing the SHA256 hash has been correctly signed with the official key. 

If you use this more complicated process and successfully validate your downloaded ISO, you can proceed with pretty complete assurance that what you've got is the official image and that it has not been tampered with in any way. This method, while the most complex, has the advantage of providing independent assurance of the integrity of the image. 
The only way this method can fail is if the official Kali Linux private key is not only subverted by an attacker, but also not subsequently revoked by the Kali Linux development team. 
For this method, see the section on verification using the SHA256SUMS file. 

## Start Verification

If u running on Linux, you probably already have GPG (GNU Privacy Guard) installed. 
If you on Windows or macOS, you'll need to install the appropriate version for your platform.

- If Windows, download and install [GPG4Win](https://gpg4win.org/download.html) 
- If macOS, download and install [GPGTools](https://gpgtools.org/) 
	- or homebrew just run `brew install gnupg` 

Once installed GPG, download and import a copy of the Kali Linux official key.
Do this with this following command 

``` bash
wget -q -O - https://archive.kali.org/archive-key.asc | gpg --import
```

or the command:

``` bash
 gpg --keyserver hkps://keys.openpgp.org --recv-key 44C6513A8E4FB3D30875F758ED444FF07D8D0BF6
```

output should look like this

``` 
gpg: key ED444FF07D8D0BF6: public key "Kali Linux Repository <devel@kali.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1  (RSA: 1)
```

Verify that the key is properly installed with the command:

``` bash
gpg --fingerprint 44C6513A8E4FB3D30875F758ED444FF07D8D0BF6
```

output will look like this:

``` 
pub   rsa4096 2012-03-05 [SC] [expires: 2025-01-24]
      44C6 513A 8E4F B3D3 0875  F758 ED44 4FF0 7D8D 0BF6
uid           [ full] Kali Linux Repository <devel@kali.org>
sub   rsa4096 2012-03-05 [E] [expires: 2025-01-24]
```

### 1. Manually Verifying Signature on the ISO (Direct Download)

If you downloaded the ISO directly from the downloads page, 
verify it using the following procedure. 

##### On Linux
On Linux, or macOS, you can generate the SHA256 checksum from the ISO image you've downloaded with the following command.
(assuming  that the ISO image is named “kali-linux-2024.2-live-amd64.iso”, and is in your current directory): 

``` bash 
shasum -a 256 kali-linux-2024.2-live-amd64.iso
```

The output should look like this:

```
8ce71b16285f8871b98e3f2155386f123c2fdca9025330c0d1349f44798e65e9  kali-linux-2024.2-live-amd64.iso
```

##### On Windows
On  windows you can open the command prompt and run :

```
certutil -?
```

If certutil is available, you can run:

```
certutil -hashfile kali-linux-2024.2-live-amd64.iso sha256
```

To verify your download. 
Certain versions of Windows do not have the native ability to calculate SHA256 checksums.
If you do not have `certutil` installed, you can use a utility such as
Microsoft File Checksum Integrity Verifier or Hashtab to verify your download. 

The resulting SHA256 signature:

```
8ce71b16285f8871b98e3f2155386f123c2fdca9025330c0d1349f44798e65e9
```

Can be seen to match the signature displayed in the "sha256sum" section on the official download page for the 64-bit Intel architecture Kali Linux 2024.2 ISO image:

![[$$$/$cheats/$oss/$linux/0_resources/media/Pasted image 20240902130056.png]]


### 2. Verify Sig on the ISO w/ Included Sig File (Torrent Download)

If copy of Kali Linux ISO image downloaded via the torrents, 
In addition to the ISO file (e.g. kali-linux-2024.2-live-amd64.iso), 
there will be a second file containing the computed SHA256 sig from the ISO with extension:
 “.txt.sha256sum” (e.g. kali-linux-2024.2-live-amd64.txt.sha256sum).

You can use this file to verify the authenticity of your download on Linux or macOS with command:

``` bash
grep kali-linux-2024.2-live-amd64.iso kali-linux-2024.2-live-amd64.txt.sha256sum | shasum -a 256 -c
```

If the image is successfully authenticated, the response will look like this: 

```
kali-linux-2024.2-live-amd64.iso: OK
```

For windows, if you have certutil you can use the command above and then manually check the contents of the txt file to see if the two SHA256 sums match. If certutil is not available, any of the tools stated above would be able to provide you the SHA 256 sum of your download. 

IMPORTANT! If you are unable to verify the authenticity of the Kali Linux image you have downloaded as described in the preceding section, do NOT use it! Using it could endanger not only your own system, but any network you connect to as well as the other systems on that network. Stop, and ensure that you have downloaded the images from a legitimate Kali Linux mirror.

### 3. Verify the ISO Using the SHA256SUMS File

This is a more complex procedure, but offers a much higher level of validation:
It does not rely on the integrity of the web site you downloaded the image from, 
only the official Kali Linux development team key that you install independently.

To verify your image this way for an Intel architecture version of Kali, 
you will need to download three files from the [Kali "Live CD Image" site for the current release](https://cdimage.kali.org/current/) 
*(v2024.2, as of this writing):* 

- The ISO image itself 
- The file containing the calculated SHA256 hash for the ISO, SHA256SUMS
- The signed version of that file SHA256SUMS.gpg

Before verifying the checksums of the image, you must ensure that the SHA256SUMS file is the one generated by Kali Linux.
That's why the file is signed by Kali's official key with a detached signature in SHA256SUMS.gpg.
If you have not already done so, Kali's official key can be downloaded and imported into your keychain with this command: 

``` bash
wget -q -O - https://archive.kali.org/archive-key.asc | gpg --import
```

or this command

``` bash
gpg --keyserver hkps://keys.openpgp.org --recv-key 44C6513A8E4FB3D30875F758ED444FF07D8D0BF6
```

Your output should look like this: 

```
pub   rsa4096 2012-03-05 [SC] [expires: 2025-01-24]
      44C6 513A 8E4F B3D3 0875  F758 ED44 4FF0 7D8D 0BF6
uid           [ full] Kali Linux Repository <devel@kali.org>
sub   rsa4096 2012-03-05 [E] [expires: 2025-01-24]
```

Once you have downloaded both SHA256SUMS and SHA256SUMS.gpg, 
you can verify the signature as follows: 

``` bash
gpg --verify SHA256SUMS.gpg SHA256SUMS
```

output should look like this:

``` 
gpg: Signature made Mon Sep  2 06:42:05 2019 EDT
gpg:                using RSA key 44C6513A8E4FB3D30875F758ED444FF07D8D0BF6
gpg: Good signature from "Kali Linux Repository <devel@kali.org>" [full]
```

**If you do not get that “Good signature” message or if the key ID does not match, then you should stop and review whether you downloaded the images from a legitimate Kali Linux mirror. The failed verification strongly suggests that the image you have may have been tampered with.**

If you did get the "Good Signature" response, you can now be assured that the checksum in the SHA256SUMS file was actually provided by the Kali Linux dev team. 
All that remains to be done to complete the verification is to validate that the signature you compute from the ISO you've downloaded matches the one in the SHA256SUMS file. 
You can do that on with the following command:
(assuming that the ISO is named “kali-linux-2024.2-live-amd64.iso” and is in your working directory):

``` bash
grep kali-linux-2024.2-live-amd64.iso SHA256SUMS | shasum -a 256 -c
```

If image successfully authenticated, output will look like this: 

```
kali-linux-2024.2-live-amd64.iso: OK
```

Once you've downloaded and verified the image, you can proceed to create a [[$bootable-live]]