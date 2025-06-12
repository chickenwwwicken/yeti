Throughout this course, u be using the Boot.Dev CLI to run tests (which are just CLI commands) against ur local environment. 

### Go Installation
Make sure u have Go 1.22 or greater installed. 
If u dont, here are the [official installation instructions](https://go.dev/doc/install) 

1. download on `Downloads`
2. `sudo mv Downloads/go1.23.5.linux-amd64.tar.gz /usr/local`
3. now we gotta use `sudo tar -C /usr/local -xzf /usr/local/go1.23.5.linux-amd64.tar.gz`
	- `/usr/local` - this is where you are gonna unpack it
	- `/usr/local/go1.23.5...` is the file u wanna unpack
	- u can delete `.tar.gz` file after that
	- if you already have a  go version installed, make sure to use the go official command:
		- `sudo rm -rf /usr/local/go && tar -C /usr/local -xzf go1.23.5.linux-amd64.tar.gz`
4. Add /usr/local/go/bin to the PATH environment variable.
	- `export PATH=$PATH:/usr/local/go/bin`
5. Confirm that it was added to the PATH env variable:
	- `echo $PATH` - `usr/local/go/bin` will be at the end.
6. Verify Go installation  with `go version`


Once you have Go, install the Boot.dev CLI:
```
go install github.com/bootdotdev/bootdev@latest
```
by default `go install` places the executable in the `$GOPATH/bin` directory.
if `GOBIN` is set, the executable will be placed in the dir specified by `GOBIN` instead.

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
[[1.1_Start_Here]]
[[1.2_Install_GIT]]