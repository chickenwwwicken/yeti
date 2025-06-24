We are gonna be using [pygame](https://www.pygame.org/news) and a [virtual environment](https://docs.python.org/3/library/venv.html) 

### Pygame
module for developing games using Python. 
Provides simple functions and methods for us to easily draw images within a GUI
window and handle user input.

### Virtual Environment (venv) 
Virtual Environments are Python's way to keep dependencies (eg. pygame module) separate from other projects on our machine. 
For example we need `pygame` version 2 for this project,
but another project on your computer might require version 1.

As a best practice, each Python project on your machine should have its own virtual environment to keep them isolated from each other. 

### Assignment
1. Create a new dir and Git repo for this project
2. Create a virtual environment at the top level of your project dir:

![[asteroids1.png]]

## Creating a Python Virtual Environment. 

``` bash
python3 -m venv venv
```

## Downloading venv

``` bash
sudo apt install python3.12-venv
```

installed it on asteroids dir

## Activate venv

``` bash
source venv/bin/activate
```

you should see som like this

```
(venv) sof7fork@MSI1 asteroids $
```

## Create requirements file and download them

``` bash
# at the top of asteroids directory
nvim requirements.txt

# add this to the file
pygame==2.6.0
```

``` bash
pip install -r requirements.txt
```

pip is python's package manager, it will install pygame module into the venv you created.

---
[[1-Build-an-Asteroids-Game]]
[[3-Pygame]]