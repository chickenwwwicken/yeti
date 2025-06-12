#### Neovim
started by removing all previous versions of neovim
`sudo apt purge neovim`
`sudo apt autoremove neovim`
delete app.image or config files manually
`rm -rf ~/.config/nvim`
`rm -rf ~/.local/state/nvim`
`rm -rf ~/.local/share/nvim`
these three are in the Uninstall from nvchad...


Now download neovim 10.0 on the .config directory.
download [neovim.appimage](https://github.com/neovim/neovim/releases/tag/v0.10.0) from repo into .config directory
then Run:
`chmod u+x nvim.appimage && ./nvim.appimage`
to run nvim after first changing permissions u just need: 
`./nvim.appimage`

#### NerdFont
Download Nerdfont (whichever u want)
We are running on kitty terminal... to see available fonts for kitty run this
`kitty +list-fonts`

to see all available fonts in system run this
`fc-list`

to search for a specific font run this
`fc-list | grep <font-name>`

When I downloaded nerdfont 0xProto family, I downloaded on 'home' dir.
I had to move it to `/usr/share/fonts/truetype`into a new dir:
`usr/share/fonts/truetype/nerd-font`

Now it's available for kitty... confirm by running `kitty +list-fonts`

Then add it to your `/.config/kitty/kitty.conf` config file like this
```
font_family 0xProto Nerd Font
bold_font auto
italic_font aauto
bold_italic_font auto
font_size 12
```

#### ripgrep

Download the package for Debian derivative
```
curl -LO https://github.com/BurntSushi/ripgrep/releases/download/14.1.0/ripgrep_14.1.0-1_amd64.deb

sudo dpkg -i ripgrep_14.1.0-1_amd64.deb
```
Verify that ripgrep is correctly downloaded
`rg --version` from the ~ dir, should give you specifics of the version u downloaded

For good practice, delete the .deb package from your system... ripgrep will still work. 


#### nvchad
Having all previous steps... now this one command should run...
`git clone https://github.com/NvChad/starter ~/.config/nvim && nvim`

Since I have nvim running with `./nvim.appimage` instead of `nvim` it ran after i independently ran `./nvim.appimage` 

Ok, this runs, but `nvim` as a command is essential... 
To be able to run `nvim` command in CLI we have to do the next steps... 
1. `mkdir -p /opt/nvim` - you can run this command from anywhere cuz its absolute path
2. `-p` flag ensures that opt directory exists
3. `sudo mv .config/nvim.appimage /opt/nvim/nvim` - here we move the appimage to the new folder we created and change its name to `nvim`.
4. add it to the PATH variable so  we can run
5. `export PATH="$PATH:/opt/nvim/"`
all done

---
[[nvchad-commands]]
