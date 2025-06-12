Install a tagged release fro the arch packages: 
```
sudo pacman -S hyprland
```
or install from the AUR, which compiles the latest source: 
```
yay -S hyprland-git
```
Alternatively, install the `hyprland-meta`package to automatically fetch and compile the latest git versions of all components within the hypr* ecosystem. 
```
yay -S hyprland-meta-git
```
If you decide to use the `git`version from the AUR, you can use the Chaotic Aur to get pre-built binaries. 

## CMake (recommended) 
```bash
git clone --recursive https://github.com/hyprwm/Hyprland
cd Hyprland
make all && sudo make install
```
*CMake is always recommended as it's the intended way Hyprland should be installed*

