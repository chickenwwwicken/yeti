### Installing Zellij
There was no `sudo apt install zellij` , so we download a prebuilt Binary.
1. Download the latest Zellij binary:
``` bash
wget https://github.com/zellij-org/zellij/releases/latest/download/zellij-x86_64-unknown-linux-musl.tar.gz
```
1. Extract the downloaded file: 
``` bash
tar -xvf zellij-x86_64-unknown-linux-musl.tar.gz
```
1. Make the binary executable: 
``` bash
chmod +x zellij
```
1. Move it to a directory in your $PATH 
``` bash
sudo mv zellij /usr/local/bin/
```
1. Verify installation by running: 
``` bash
zellij
```
![[$$$/$cheats/$clis/$kitty/zellij-initialized.png]]

### Navegacion + Paneles Zellij

- `ctrl p` - modo paneles
- `ctrl p n` - new panel
- `ctrl p d` - new down panel
-  `alt` + flechas - navegacion entre paneles
- `ctrl p x` - eliminar panel

### Tabs Zellij

- `ctrl t` - modo tab
- `ctrl t n` - new tab
- `ctrl t r` - rename tab
- `ctrl t x` - close tab

### For Remote Systems
remote systems in zellij
- `ctrl s` - sync mode in zellij

### Quit Zellij

- `ctrl q` - quit zellij

### Sessions 
To open previous sessions from zellij
- `zellij list-seessions` - lists sessions
- `zellij attach session-name` - enter 'session-name' session
- `ctrl o` - session mode
- `ctrl o d` - detach session, closes but doesn't quit the session
- `ctrl o w` - session manager

### Layouts
Layouts are a way to create a template for a set of tabs/panes for apps/dirs/commands that you can modify to just open a Layout and have everything ready for any activity. 

#### Creating and Running a Layout file
1. create a dir for Zellij, I made it on ~
2. create a file in `~/zellij` called `layout.kdl`
3. run `zellij layout.kdl` from `~/zellij`

#### Example of a layout file
``` 
layout {
	# adds the top visualizer of tabs
	default_tab_template{
		pane size=1 borderless=true {
			plugin location"zellij:compact-bar"
		}
	# adds the above plugin for our tabs to 'children'
	children
	}

	# tab for system with btop command initialized instantly
	tab name="system" {
		pane {
			command "btop"
		}	
	}

	# tab for boot.dev with a 3 split terminal, one with a git log command waiting
	# to be initialized and 2 terminals already initialized on the boot.dev dir
	tab name="bot.dev" {
		pane split_direction="vertical" {
			# two terms inside one of the big vertical divisions (left)
			pane split_direction="horizontal" {
				pane {
					cwd "~/boot.dev"
				}
				pane {
					cwd "~/boot.dev"
				}
			}
			pane {
				cwd "~/boot.dev"
				# you can use any command
				command "git"
				args "log" "--oneline"
				# custom for initializing when you enter
				start_suspended true
			}
		}
	}
}
```
---
### custom layout.kdl file
this file is inside ~/zellij which I created and then aliased it to `firecenter` which is the same as running this command to fire zellij - `zellij --layout ~/zellij/layout.kdl`

also created alias for `zellij --layout ~/zellij/sidelayout.kdl` - `fireside`

- 