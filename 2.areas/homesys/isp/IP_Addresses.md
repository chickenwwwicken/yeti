kind of like phone numbers but for devices
without IP address = no communication

---
to find IP address:

```shell
windows : ipconfig
apple linux : ifconfig
```

---
```shell
Connection-specific DNS Suffix . : localdomain
Link-local IPv6 Address  . . . . : fe80::413b:ba6a:5eb:1c00%66
IPv4 Address . . . . . . . . . . : 192.168.1.67
Subnet Mask. . . . . . . . . . . : 255.255.255.0
Default Gateway. . . . . . . . . : 192.168.1.254
```

subnet mask aka netmask (on linux)

---
## IP Address

each of sets of numbers  192 . 168 . 1 . 67 (four sets) are called **octets** 

- if octet on subnet mask = 255 = octet cannot be changed
- if octet on subnet mask = 0 = octet can be changed

192.168.1 = Network Portion
.67 = Host Portion = a device is called a Host *(ex. computer , nintendo , tv , etc*.)


### Subnetting Classes

| Class | Range                       | Subnet Mask   |
| ----- | --------------------------- | ------------- |
| A     | 1.0.0.0 - 126.255.255.255   | 255.0.0.0     |
| B     | 128.0.0.0 - 191.255.0.0     | 255.255.0.0   |
| C     | 192.0.0.0 - 233.255.255.0   | 255.255.255.0 |
| D     | 224.0.0.0 - 239.255.255.255 |               |
| E     | 240.0.0.0 - 255.255.255.255 |               |
Class A = Companies having entire number (*ex. General Electrics has 3.0.0.0*)
That is a 16,777,000 networks available for them

**IANA** = Internet Assign Number Authority
 




