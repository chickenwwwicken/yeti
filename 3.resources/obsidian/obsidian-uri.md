---
tags:
  - rsrc
  - obsidian
aliases:
  - obsidian-terminal
  - obsidian-commands
link: https://help.obsidian.md/Extending+Obsidian/Obsidian+URI
---
Obsidian URI is custom URI protocol suypported by obsidian that 
lets you trigger actions, enables automation and cross-app work.

## URI format
URIs use the following format:
```zsh
obsidian://action?param1=value&param2=value
```
The `action` parameter is the action you wanna do. 
Available actions:
- `open` - to open a note.
- `new` - to create or add to an existing note. 
- `daily` - to create or open your daily note. 
- `search` - to open a search.

***Special Note: 
- `%20` - `space`
- `%2F` - `/`
## Open Note
The open note action opens an Obsidian Vault, or a file within. 
### Examples
`obsidian://open?vault=my%20vault` - opens the vault "my vault". 
`obsidian://open?vault=ef6ca3e3b524d22f` - opens vault ID `ef6ca3e3b524d22f`
`obsidian://open?vault=my%20caault&file=my%20note` - open specific file