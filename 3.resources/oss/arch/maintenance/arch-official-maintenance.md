---
id: arch-official-maintenance
aliases: []
tags: []
---

Regular system maintenance is necessary for the proper functioning of Arch over a period of time. 
Timely maintenance is a practice many users get accustomed to. 

# 1 Check for errors
--- 
### 1.1 Failed systemd services
Check if any systemd services have failed:
```
systemctl --failed
```
See systemd#Using units for more information. 

### 1.2 Log files
Look for errors in the log files located in `/var/log/`, as well as messages logged in the systemd journal:
```
journalctl -b
```
See systemd/Journal for more information and filtering options. 

# 2 Backup
---
Having backups of important data is a necessary measure to take, since human and machine processing errors are very likely to generate corruption as time passes, and also the physical media where the data is stored is inevitably destined to fail. 

## 2.1 Configuration files
Before editing any configuration files, vreate a backup so that you can revert to a working version in case of problems. 
Editors like vim and emacs can do this automatically.
On a larger scale, consider using a [[configuration-manager.md|configuration manager]]

For dotfiles (config files in the home directory, see [[dotfiles.md|dotfiles]]
