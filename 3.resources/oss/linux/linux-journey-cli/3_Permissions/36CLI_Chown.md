The ```chown``` command allows you to change the owner of a file or dir, and it requires root privileges.

#### Assignment
Navigate into the ```worldbanc/private``` directory. 
Take a look at the contents.
You should see a directory called ```contacts``` 
Take a look
You should see a file called ```emergency.txt``` 
Take a look with ```cat```
Let's change the owner of the entire ```contacts``` dir to ```root```:

``` bash
sudo chown -R root contacts
```

```sudo```: run as super user root
```chown```: change owner
```-R```: recursively along directory
```root```: the name of the new owner
```contacts```: the dir to change the owner of 

run ```ls -l``` to checkout the changes.

---
[[35CLI_RootUser]]
[[4.1_CompiledxInterpreted]]