The chmod command lets you change the permissions of a file or directory.
It's short for "change mode" 

#### Assignment
The ```ls``` command has a ```-l``` flag that will print out the permissions of each file.
Run this command inside the ```worldbanc/private``` dir:
Change the permissions of the ```private``` directory and all of its contents so that:
- the owner can read,write,execute
- The group can do nothing
- Others can do nothing
``` bash
chmod -R u=rwx,g=,o= Directory
```

---
[[32CLI_Permissions]]
[[34CLI_Executables]]