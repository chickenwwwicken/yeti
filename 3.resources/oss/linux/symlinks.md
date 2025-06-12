#### How to dotfiles

### GNU Stow
A symlink farm manager which takes distinct packages of software and /or data llocated in separate directories on the filesystem, and makes them appear to be installed in the same place. 

For example:

`/usr/local/bin` could contain symlinks to files within -> 
`/usr/local/stow/nvim/bin`, `/usr/local/stow/kitty/bin`, 
and likewise recursively for any other subdirs such as `.../share` `.../man` and so on.

Useful for keeping track of system-wide and per-user installations of software built from source.
Can also facilitate more controlled approach to management of config files in the user's home directory, 
especially when coupled with version controlled systems. 


Stow manages the creation and deletion of symlinks

---
### Symlinks

The equivalent of shortcuts are symbolic links or symlinks.
Allow us to link to another file by its filename.

They are just files that point to filenames.

![[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/12_symlinks#Creating a symlink]]

This allows you to access data without having to duplicate that data

Typically we use them to move executables from a deep directory in filesystem
to a more convenient path that allows you to access easier

##### List Symlinks

To be able to see your links:

``` bash
# l flag is for "links"
ls -l
```

your link will have this `l` tag also -> `lrwxrwxrwx` 

#### Symlink Behavior
If you modify a symlink, for example `mylink` ->
The file its linked to `myfile` will also be modified in the same way.

---
### `stow` Repo

create  a new repo for config files

``` bash
mkdir dotfiles
```

inside `dotfiles`

``` bash
mv ~/.config/nvim nvim/.config
mv ~/.config/kitty kitty/.config
mv ~/.config/awesome awesome/.config
mv ~/.bashrc bashrc/.config
mv ~/.config/rofi rofi/.config
mv ~/.config/picom picom/.config

```
