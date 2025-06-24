Video games are generally built using a game loop.

The simplest game loop has 3 steps:

1. Check for Player inputs
2. Update the game world
3. Draw the game to the screen

To create a good UX these need to happen many times per second.

## init pygame in main()
1. `import pygame` at the top of your `main.py` file
2. initialize [pygame](https://www.pygame.org/docs/ref/pygame.html#pygame.init) at the beginning of your `main.()` function 

``` python
def main():
	pygame.init()
```

now file looks like this
# 

``` python
import pygame
from constants import *

def main():
	pygame.init()
	print("Starting asteroids!")
	print(f"Screen width: {SCREEN_WIDTH}")
	print(f"Screen height: {SCREEN_HEIGHT}")

if __name__ == "__main__":
	main()
```

### Create a GUI Window

``` python
screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
```

### Creating a game loop

- Use an [infinite while loop](https://realpython.com/python-while-loop/#infinite-loops) . At each iteration it should:
	- Use the screen's [fill](https://www.pygame.org/docs/ref/surface.html#pygame.Surface.fill) method to fill the screen with a solid "black" color.
	- Use pygame's [`display.flip()`](https://www.pygame.org/docs/ref/display.html#pygame.display.flip) method to refresh the screen.

``` python
# Infinite while loop for game loop
while True: 
	# pygame.Surface.fill method to fill GUI Window with black color
	pygame.Surface.fill( screen, (0,0,0) )
	# pygame.display.flip() to update the full display Surface to the screen
	pygame.display.flip()
```
### Test your game

``` python
main.py
```

You should see a black window open and stay open.
To close do `Ctrl` `C` on the terminal.

### Make close button work

Add the following code to the beginning of each iteration of the game loop:

``` python
for event in pygame.event.get():
    if event.type == pygame.QUIT:
        return
```

This will make the the close button work

### Create a .gitignore

``` 
venv/
__pycache__/
```

---
[[4-Modules]]
[[6-FPS]]
