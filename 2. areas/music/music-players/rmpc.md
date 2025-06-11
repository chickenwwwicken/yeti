rmpc is a beautiful, modern and configurable terminal based Music Player Daemon client. It was inspired by nncmpcpp and aims to provide ann alternative with support for album art through kitty image protocol without any ugly hacks. It also features ranger/lf inspired browsing of songs and other goodies. 

### Main Features
- Album cover art display if your terminal supports either of Kitty, Sixel, Iterm2, protocols, or via ueberzuggpp
- Ability to play music from youtube
- Configurable UI
	- Configure what info is displayed in header
	- Configure what columns are displayed on the queue pane
	- Completely customize which tabs are rendered and mixmatch their content
	- Create any color theme you want
	- Every keybind can be changed, vim-like by default
- Basic playlist management
- Support scripting through basic CLI mode and script hooks
![[rmpc-example.png.png]]![[rmpc-example2.png.png]]

I got these errors:
``` zsh
cannot connect to mpd
```
went and configured mpd
now i get this error:
```zsh
Failed to read config. Using default values. Check logs for information.
```
