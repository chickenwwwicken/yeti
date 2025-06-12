It would be pain if all our code in a single file. 

## Importing modules
In Python, each `.py` file is a module, 
and we can import functions, variables, and classes from one into another with `import`
The name of a module is the filename (without the `.py`)

example: 

``` python
# import the function_hello function
# and the variable_player variable
# into the current file
from module import function_hello, variable_player
```

If you wanna import everything from a module, you can use the `*` character.

``` python
# import everything from a module
# into the current file
from module import *
```

## Constants
Games often have a lot of magic numbers to represent things like player speeds,
item costs, and attack damage. 
We will use this file as a place to store those kind of constant values.

## Assignment
1. Create a new file in your project called `constants.py` (in same folder as `main.py`)
2. Paste this inside

``` python
SCREEN_WIDTH = 1280
SCREEN_HEIGHT = 720

ASTEROID_MIN_RADIUS = 20
ASTEROID_KINDS = 3
ASTEROID_SPAWN_RATE = 0.8  # seconds
ASTEROID_MAX_RADIUS = ASTEROID_MIN_RADIUS * ASTEROID_KINDS
```

3. Import everything from the `constants.py` file into `main.py` 
4. Print out the `SCREEN_WIDTH` and `SCREEN_HEIGHT` values when `main.py` is run 

Use this format for step 4

``` python
Starting asteroids!
Screen width: 1280
Screen height: 720
```

---

![[asteroids3.png]]

---
[[3-Pygame]]
[[5-Game-Loop]]