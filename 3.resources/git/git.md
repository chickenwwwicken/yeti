### 1.1 Global variables 

``` bash
git config --global user.email "chickenwwwicken@gmail.com"
git config --global user.name "chickenwwwicken"
```

### 1.2 Create a `.dotfiles` repo 

1. Create a `dotfiles` repo on Github 
2. Create a `.dotfiles` directory on your home dir 
3. Clone it to your PC into `.dotfiles` directory

``` bash
git clone https://github.com/chickenwwwicken/dotfiles.git ~/.dotfiles
```

4. Add your `.gitconfig` to `.dotfiles` directory 
5. This will break your `.gitconfig` because it lookin for it in the home directory

### 1.3 Create a symlink for `.gitconfig` 

``` bash
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```

- `ln` - link command
- `-s` - symbolic link
- `~/.dotfiles/.gitconfig` - location where we moved it
- `~/.gitconfig` - location where its expected to live

Now there won't be an issue with committing 'added .gitconfig'

### 1.4 Full `.gitconfig` dotfile

``` 
[user]
	email = chickenwwwicken@gmail.com
	name = chickenwwwicken
```

---

