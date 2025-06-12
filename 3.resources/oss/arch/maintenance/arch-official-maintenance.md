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
