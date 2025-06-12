Linux Mint stores fonts in several standard directories, depending on whether the ffonts are installed system-wide or just for a specific user:

#### System-wide fonts:
- `usr/share/fonts`
- `/usr/share/fonts/truetype`
Installing fonts here requires admin privs, and the fonts are available for all users on the system. 

#### User-specific fonts:
- `~/.local/share/fonts` (recommended for new installations)
- `~/.fonts` (older method, still supported but considered deprecated on some distros)
Fonts placed in these dirs are only available to the individual user and do not require root access.

After adding new fonts to any of these dirs, you should update the font cache with:
``` bash
fc-cache -f -v
```
This ensures the system recognizes new fonts. 
