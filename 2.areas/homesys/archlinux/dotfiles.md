---
id: dotfiles
aliases: []
tags: []
---

### config files archlinux
from ~
- .oh-my-zsh/
- .npm/
- .gitconfig
- .p10k.zsh
- .zshrc

from .config
- hypr/
- kitty/
- mpd/
- nvim/
- yay/
- dolphinrc

from yeti
- .obsidian/
- .obsidian.vimrc

commands:

```bash
# /home/chicken
ln -s /home/chicken/dotfiles/.oh-my-zsh/ /home/chicken
ln -s /home/chicken/dotfiles/.npm/ /home/chicken
ln -s /home/chicken/dotfiles/.gitconfig /home/chicken
ln -s /home/chicken/dotfiles/.p10k.zsh /home/chicken
ln -s /home/chicken/dotfiles/.zshrc /home/chicken

# /home/chicken/.config
ln -s /home/chicken/dotfiles/hypr/ /home/chicken/.config
ln -s /home/chicken/dotfiles/kitty/ /home/chicken/.config
ln -s /home/chicken/dotfiles/mpd/ /home/chicken/.config
ln -s /home/chicken/dotfiles/nvim/ /home/chicken/.config
ln -s /home/chicken/dotfiles/yay/ /home/chicken/.config
ln -s /home/chicken/dotfiles/dolphinrc /home/chicken/.config

# /home/chicken/yeti (obsidian)
ln -s /home/chicken/dotfiles/.obsidian/ /home/chicken/yeti
ln -s /home/chicken/dotfiles/.obsidian.vimrc /home/chicken/yeti
```

















