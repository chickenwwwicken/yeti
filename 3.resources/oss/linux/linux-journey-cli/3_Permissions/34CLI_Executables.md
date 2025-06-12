You're probably familiar with the idea of reading and writing files. 
But what about executing them? 
Executable files are just programs that you can run on your computer.

Files with a ```.sh``` extension are shell scripts. 
They're just text files that contain commands.
You can run a file in your shell by just typing its filepath:

``` bash
mydir/program.sh
```

Interestingly if the program is in the current directory 
(in this example, the ```mydir``` dir), you need to prefix it with ```./```

``` bash
./program.sh
```

As far as file paths go, ```./program.sh``` and ```program.sh``` are the same.
The ```.``` is an alias for the current directory. 
We need the prefix when running executables so that the shell knows we're trying to run a 
file from a file path, not an installed command like ```ls``` ```mkdir``` etc.

#### Assignment
There seems to be a suspicious script in the ```worldbanc/private/bin``` dir called ```genids.sh``` 
It looks like it generates some type of identifier. 
First, let's remove our ability to run it . 
The ```chmod``` command has a convenient ```-x``` flag that will simply remove the executable permissions from the file.

Run the following commands in  ```worldbanc/private/bin``` :

``` bash
chmod -x genids.sh
```

Let's test those permission changes. Try this:

``` bash
./genids.sh
```

You should get an error like this:

```
permission denied
```

That error occurs because the executable permission is not set for your user (owner). 
Let's re-add the executable permission for the owner.

```
chmod +x genids.sh
```

Once you do that, run the script again.

---
[[33CLI_Changing_Perms]]
[[35CLI_RootUser]]