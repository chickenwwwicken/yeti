Let's use a previous example of inode information: 

``` bash
pete@icebox:~$ ls -li
140 drwxr-xr-x 2 pete pete 6 Jan 20 20:13 Desktop
141 drwxr-xr-x 2 pete pete 6 Jan 20 20:01 Documents
```

You may have notices that we've been glossing over the third field in this command, 
that field is the link count. 

The link count is the total number of hard links a file has, 
well that doesn't mean anything to you right now, 
So let's discuss links first. 

#### Symlinks
In the Windows operating system, 
there are things known as shortcuts, 
shortcuts are just aliases to other files.
If you do something to the original file, 
you could potentially break the shortcut. 
In Linux, the equivalent of shortcuts are symbolic links or symlinks or softlinks.

Symlinks allow us to link to another file by its filename. 
Another type of links found in Linux are hardlinks, 
these are actually another file with a link to an inode. 
Let's see waht we mean in practice starging with symlinks. 

``` bash
pete@icebox:~/Desktop$ echo 'myfile' > myfile

pete@icebox:~/Desktop$ echo 'myfile2' > myfile2

pete@icebox:~/Desktop$ echo 'myfile3' > myfile3

pete@icebox:~/Desktop$ ln -s myfile myfilelink

pete@icebox:~/Desktop$ ls -li

total 12
  151 -rw-rw-r-- 1 pete pete 7 Jan 21 21:36 myfile
93401 -rw-rw-r-- 1 pete pete 8 Jan 21 21:36 myfile2
93402 -rw-rw-r-- 1 pete pete 8 Jan 21 21:36 myfile3
93403 lrwxrwxrwx 1 pete pete 6 Jan 21 21:39 myfilelink -> myfile

```

You can see that we made a symbolic link named `myfilelink` that points to `myfile` .
Symbolic links are denoted by -> . 
Notice how i got a new inode number though,
symlinks are just files that point to filenames. 
When you modify a symlink, 
the file also gets modified. 

Inode numbers are unique to filesystems, 
you can't have two of the same inode number in a single filesystem, 
meaning you can't reference a file in a different filesystem by its inode number. 

However, if you use symlinks they do not use inode numbers, 
they use filenames, 
so they can be references across different filesystems. 

#### Hardlinks
Example of a hardlink : 

``` bash
pete@icebox:~/Desktop$ ln myfile2 myhardlink

pete@icebox:~/Desktop$ ls -li

total 16
  151 -rw-rw-r-- 1 pete pete 7 Jan 21 21:36 myfile
93401 -rw-rw-r-- 2 pete pete 8 Jan 21 21:36 myfile2
93402 -rw-rw-r-- 1 pete pete 8 Jan 21 21:36 myfile3
93403 lrwxrwxrwx 1 pete pete 6 Jan 21 21:39 myfilelink -> myfile
93401 -rw-rw-r-- 2 pete pete 8 Jan 21 21:36 myhardlink

```

A hardlink just creates another file with a link to the same inode.
So if I modified the contents of `myfile2` or `myhardlink` ,
the change would be seen on both, 
but if I deleted `myfile2` ,
the file would still be accessible through `myhardlink` .
Here is where our link count in the `ls` command comes into play. 
The link count is the number of hardlinks that an inode has, 
when you remobe a file, 
it will decrease that link count. 
The inode only gets deleted when all hardlinks to the inode have been deleted. 
When you create a file, 
it's link count is 1 because it is the only file that is pointing to that inode. 
Unlike symlinks, hardlinks do not span filesystems because inodes are unique to the filesystem.

#### Creating a symlink

``` bash
ln -s myfile mylink
```

`:ln -s ~/.dotfiles/awesome <path to awesome >`

#### Creating a hardlink

``` bash 
ln somefile mylink
```

---
[[$$$/$cheats/$oss/$linux/2_linux-journey/2_filesystem/11_inodes]]
[[$$$/$cheats/$oss/$linux/0_resources/0.2_contents]]
