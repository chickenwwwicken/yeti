https://wiki.hyprland.org/Configuring/Monitors/

To list all available monitors (active and inactive):
```bash 
hyprctl monitors all
```
Setting up my monitors:
One flipped right/270 degrees
One normal
```
monitor = DP-2,     2560x1080, auto, 1, transform, 3 #flipr
monitor = HDMI-A-1, 2560,1440, auto, auto
```

---
To list all the devices
```
hyprctl devices
```
Select your mouse: `instant-usb-gaming-mouse-`
```hyprland.conf
device {
    name = instant-usb-gaming-mouse-
    sensitivity = -1.0
}
```
