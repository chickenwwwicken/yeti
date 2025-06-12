Once you have Go, install the Boot.dev CLI:
```
go install github.com/bootdotdev/bootdev@latest
```

If it says ```invalid go version, 1.22.1: must match format 1.23``` u need to remove your Go version and reinstall it. 

Make sure the Boot.dev CLI install worked:
``` bash
bootdev --version
```

If u get ```command not found``` error, its likely because Go's bin directory (where your ```bootdev``` command is) isn't in your PATH. You can add the bin directory to your PATH by modifying your shell's configuration file. For example, if you're using bash on Ubuntu, you can run the following commands to add a line to your ```~/.bashrc``` file:
``` bash
echo 'export PATH=$PATH:$HOME/go/bin' >> ~/.bashrc

# next, reload your shell configuration
source ~/.bashrc
```
//solo corri estos dos comandos y funciono

Once the ```bootdev``` command is working, log in and follow the instructions:
``` bash
bootdev login
```

#### Run vs Submit

Each lesson has a list of 'commands' it runs on your local machine, and a series of tests it will check against the results of the command. 

There are two ways to run these commands: ```run``` and ```submit```.
1. ```bootdev run```: This will run the commands and show you the results. It's to be used for debugging, but it won't tell you whether or not you've passed the tests explicitly. 
2. ```bootdev submit```: This will run the commands and give you pass/fail feedback. It will also mark the lesson as complete on the website. If you get it wrong however, you'll potentially lose your sharpshooter spree, so be sure to use ```run``` first!

---
### Dependencies
[[$go-guide]]