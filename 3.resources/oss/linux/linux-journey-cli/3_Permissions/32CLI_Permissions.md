Permissions control who can do what to which files and dirs.
The permissions of an individual file or dir are visually represented as a 10-char string

```
drwxrwxrwx
```

The first one tells you whether it's a file or a dir
```-``` : Regular file (```-rwxrwxrwx```)
```d```: Directory (```drwxrwxrwx```)

The next 9 chars are broken up into sets of ```rwx``` and represent permissions themselves.
"Owner" - "Group" - "Others" in that order. 
Each group of 3 represents the permissions for reading writing and executing.
```rwx```: All permissions
```rw-```: Read n Write
```r-x```: Read n Execute

some examples:\
```-rwxrwxrwx```: a file where you can do everything
```-rwxr-xr-x```: a file you can read + execute but only owner can write.
```drwxr-xr-x```: A dir where everyone can read(```ls``` contents) + execute (```cd``` into) but only owner can write (modify the comments) 
```drwx------```: A dir where only the owner can read write and execute.

---
[[31CLI_Users]]
[[33CLI_Changing_Perms]]