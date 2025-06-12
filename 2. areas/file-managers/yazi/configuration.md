---
id: configuration
aliases: []
tags: []
---

# configuration
recommended and also added this to my zshrc
```zsh
function y() {
	local tmp="$(mktemp -t "yazi-cwd.XXXXXX")" cwd
	yazi "$@" --cwd-file="$tmp"
	IFS= read -r -d '' cwd < "$tmp"
	[ -n "$cwd" ] && [ "$cwd" != "$PWD" ] && builtin cd -- "$cwd"
	rm -f -- "$tmp"
}
```

created .config/yazi directory
inside created this files:
- yazi.toml
- theme.toml
- keymap.toml

Inside yazi.toml:
copied default config from this [website](https://github.com/sxyazi/yazi/blob/shipped/yazi-config/preset/yazi-default.toml) into yazi.toml

Inside keymap.toml:
copied default config from their keymap-default.toml and pasted on keymap.toml

didnt do nothin for theme.toml

### shout out your configuration
```zsh
yazi --clear-cache
```

