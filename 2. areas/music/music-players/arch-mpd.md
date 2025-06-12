---
id: arch-mpd
aliases: []
tags: []
---

(music player daemon)

##### Installation
sudo pacman -S mpd

##### Configuration 
MPD is able to run in per-user config or system-wide config. 

The way of setting up MPD depends onn the way it is intended to be used: a local per-user config is easier to set up an dmay prove more adapted on a desktop system. 

In order for MPD to be able to playback audio, ALSA, optionally with PulseAudio or PipeWire, must be set up and working. The Audio configuration section thereafter describes the parameters needed for ALSA, PulseAudio, or Pipewire. 

MPD is configured in the file mpd.conf which can be located in various paths depending on the setup chosen.
Common locations:
- `~/.config/mpd/mpd.conf` in per-user configuration mode, this is the first location searched, 
- `/etc/mpd.conf`  in system-wide configuration. 

These are some of the most commonly used config options:
`pid_file` - the file where MPD stores its process ID
`db_file` - The music database
`state_file` - MPD's current state is noted here
`playlist_directory` - the dir that MPD scans for music
`sticker_file` - the sticker database

##### Per-user config
running it as a normal user has the benefits of :
- regrouping into one single dir `~/.config/mpd/` 
- Avoiding unforseen directory and file permission errors. 

In user mode, the config is read from `$XDG_CONFIG_HOME/mpd/mpd.conf` assuming that's equal to default: `~/.config`. 

To build the user config, the MPD config example included in the package is a good starting point, copy it using the following lines:
``` zsh
mkdir -p ~/.config/mpd
cp /usr/share/doc/mpd/mpdconf.example ~/.config/mpd/mpd.conf
```
A good practice is to use this newly created `~/.config/mpd/` dir to store, together with the config file, other MPD related files like the database or the playlist. The user must have read write access to this dir. 

Then edit the config file in order to specify the required and optional files and dirs:
``` zsh
# Recommended location for database
db_file            "~/.config/mpd/database"

# If running mpd using systemd, delete this line to log directly to systemd.
log_file           "syslog"

# The music directory is by default the XDG directory, uncomment to amend and choose a different directory
#music_directory    "~/music"

# Uncomment to refresh the database whenever files in the music_directory are changed
#auto_update "yes"

# Uncomment to enable the functionalities
#playlist_directory "~/.config/mpd/playlists"
#pid_file           "~/.config/mpd/pid"
#state_file         "~/.local/state/mpd/state"
#sticker_file       "~/.config/mpd/sticker.sql"
```
If playlists are enabled in the configuration, the specified playlist dir must be created:
```zsh
mkdir ~/.config/mpd/playlists
```
If state_file is set, the specified directory must be created:
``` zsh
mkdir -p ~/.local/state/mpd
```
MPD can now be started (an optional custom location for the configuration file can be specified):
``` zsh
mpd [config_file]
```

In order to build the database fillle, MPD must scan into the `music_directory` defined above. To request this task, one of the MPD clients must be used. For example with mpc the command is: 
```zsh
mpc update
```
or alternatively one can set the option `auto_update` to "yes" in the config to refresh the database whenever files are changed in  "music_directory"

Added this config from fren [brodie](https://www.youtube.com/watch?v=XpzNdXtpKDc) 
```conf
# Recommended location for database
db_file            "~/.config/mpd/database"

# If running mpd using systemd, dellete this line to log directly to systemd. 
log_file           "syslog"

# The music directory is by default the XDG directory, uncomment to amend and chose a different directory
music_directory    "~/music"

# Uncomment to refresh the database whenever files in the music_directory are changed.
auto_update "yes"

# Uncomment to enable the functionalities
playlist_directory "~/.config/mpd/playlists"
# pid_file           "~/.config/mpd/pid"
state_file         "~/.local/state/mpd/state"
sticker_file       "~/.config/mpd/sticker.sql"

# Uncomment to refresh the database whenever files in the music_direcroty are changed
auto_update "yes"
auto_update_depth "0"

restore_paused "yes"
```

to check wassup with mpd:
``` zsh
sudo systemctl status mpd
```

to enable mpd:
```zsh
sudo systemctl enable mpd
```

to start mpd:
```zsh
sudo systemctl start mpd
```

I still get some errors but now I need configuration from rmpc
