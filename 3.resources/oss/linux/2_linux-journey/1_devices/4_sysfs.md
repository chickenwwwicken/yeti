Sysfs was created long ago to better manage devices on our system
that the `/dev` directory failed to do.
`sysfs` is a virtual filesystem, most often mounted to the `/sys` directory.

It gives us more detailed information that what we would be able to see in the `/dev` dir.

Both dirs `/sys` and `/dev` seem to be very similar and they are in some regards,
but they do have major differences.

Basically, the `/dev` directory is simple, 
it allows other programs to access devices themselves, 
while the `/sys` filesystem is used to view information and manage the device.

The `/sys` filesystem basically contains all the information for all devices on ur system,
such as the manufacturer and model,
where the device is plugged in,
the state of the device,
the hierarchy of devices and more.

The files you see here aren't device nodes, 
so you don't really interact with devices from the `/sys` directory,
rather you are managing devices. 

Take a look at the contents of the `/sys` directory: 

``` bash
pete@icebox:~$ ls /sys/block/sda

alignment_offset  discard_alignment  holders   removable  sda6       trace
bdi               events             inflight  ro         size       uevent
capability        events_async       power     sda1       slaves
dev               events_poll_msecs  queue     sda2       stat
device            ext_range          range     sda5       subsystem
```

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/1_devices/3_device-names]]
[[$$$/$cheats/$oss/$linux/2_linux-journey/1_devices/5_udev]]
