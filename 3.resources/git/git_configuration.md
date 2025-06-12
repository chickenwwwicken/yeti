First things first, Git uses a series of configuration files that control how it behaves.

When I designed Git, I made it so you can configure it at three different levels:
1. System Level (/etc/gitconfig) - applies to every user on the system
2. Global level (~/.gitconfig or ~/.config/git/config) - specific to your user account
3. Local level (.git/config) - specific to a single repo

Each level overrides the previous one, so local settings trump global settings, which trump system settings.

### Fixing your Git config
##### Check your Current configuration
First, let's see what Git thinks it knows about your setup: 
``` bash
git config --list --show-origin
```
This will show you where each configuration value is coming from. Look for any paths that point to locations that no longer exist.

##### Check for multiple config Files
Git might be reading from multiple config files. Check both possible locations for your global config:
``` bash
cat ~/.gitconfig
cat ~/.config/git/config
```
### Using the GIT_CONFIG Env Variable
The simplest solution is to set the GIT_CONFIG environment variable to point to your custom .gitconfig location:

If you are using a custom .gitconfig location:
``` bash
export GIT_CONFIG=/path/to/your/dotfiles/.gitconfig
```

### Using includeif 
This approach is better than GIT_CONFIG Variable

This is the approach I personally prefer because it's more robust than environment variables. 

##### Creating a proper Git Include Config
1. create a standard .gitconfig file in your home dir
2. inside the file add this exact lines - 
``` bash
[include]
    path = /home/chicken/___dot___files/.gitconfig
```
This actually worked , gud shit