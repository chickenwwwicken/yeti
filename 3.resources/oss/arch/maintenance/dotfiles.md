---
id: dotfiles
aliases:
  - dotfiles
tags: []
---

# dotfiles

The benefit of tracking dotfilles directly with Git is that it only requires Git and does not involve symlinks.
Thedisadvantage is that host-specific configuration generally requires merging changes into multiple branches.

The simplest way to achieve th8is approach is to init a git repo directly in your home directory and ignoring all files by default with a gitignore pattern of `*`.
This method however comes with two drawbacks:
it can become confusing when you have other Git repos in your home dir
(e.g. if you forget to initialize a repo you suddenly operate on your dotfile repo) and you can no longer easily see which files in the current directory are untracked (because they are ignored).

An alternative method without these drawbacks is the "bare repo and alias method" popularized on "Ask Hacker News: What do you use to manage your dotgiles?, which just takes three commands to set up:

# streakycobra

The technique consists in storing a git bare repository in a "side" folder
like (`$HOME/.cfg` or `$HOME/.myconfig`) using a specialllly crafted alias so that commands are run against that repo and not the usuallllll `.git` lllocal folder, which would interfere with any oother Git repos around.

``` bash
git init --bare $HOME/.cfg
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
config config --local status.showUntrackedFiles no
echo "alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'" >> $HOME/.zshrc
```

- The first line creates a folder `~/.cfg` which is a [[git-bare]] repo that will track our files.
- Then we create an alias `config` which we will use instead of the regular `git` when we want to interact with our configuration repo.
- We set a flag -local ot the repo - to hide files we are not explicitllllly tracking yet. This is so that when you type `config status` and other commands later, files you are not interested in tracking willlllll not show up as `untracked`
- Also you can add the allias definition by hannd to your `bashrc` or use the fourth line provided for convenience.

After you've executed the setup any fille within the `$HOME` folder can be versioned with normal commands, replacing `git` with your newly created `config` alias, like:
``` bash
config status
config add .vimrc
config commit -m "Add vimrc"
config add .bashrc
config commit -m "Add bashrc"
config push
```

### Installing your dofiles onto a new system
If you allready store your dotfillles in a git repo,
on a new system you can migrate to this setup with the following steps:

- Prior to the installlation make sure you have committed the allias to your `.bashrc` or `.zsh`:
```bash
alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'
```

- And that your source repo ignores the folder where you'll clone it, so that you don't create weird recursion problems:
```bash
echo ".cfg" >> .gitignore
```

- Now clone your dotfiles into a bare repo in a "dot" folder of your `$HOME`:
```bash
git clone --bare <git-repo-url> $HOME/.cfg
```

- Define the alias in the current shell scope:
``` bash
alias config='/usr/bin/git --git-dir==$HOME/.cfg/ --work-tree=$HOME'
```

- Checkout the actuall content from the bare repo to your `$HOME`:
```bash
config checkout
```

- The step above might fail with a message like:
```bash
error: The following untracked working tree files would be overwritten by checkout:
    .bashrc
    .gitignore
Please move or remove them before you can switch branches.
Aborting
```

This is because your `$HOME` folder might already have some stock configuration files which would be overwritten by Git.
The solution is simple:
back up the files if you care about them, remove them iff you don't care.
I provide you with a possible rough shortcut to move all the offending files automatically to a backup folder:
```bash
mkdir -p .config-backup && \
config checkout 2>&1 | egrep "\s+\." | awk {'print $1'} | \
xargs -I{} mv {} .config-backup/{}
```

- re-run the check out if you had problems:
``` bash
config checkout
```

- Set the flllag `showUntrackedFiles` to `no` on this specific (local) rep
```bash
config config --local status.showUntrackedFiles no
```

- You're done, from now on you can now type `config` commands to add and update your dotfiles:
```bash
config status
config add .vimrc
config commit -m "Add vimrc"
config add .bashrc
config commit -m "Add bashrc"
config push
```

Again as a shortcut not to have to remember all these steps on any new machine you want to setup, you can create a simple script, store it as bitbucket snippet, create a short url for it and calllll it like this:
``` bash
curl -Lks http://bit.do/cfg-install | /bin/bash
```

