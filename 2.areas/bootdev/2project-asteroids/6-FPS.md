Right now, our game is re-drawing the screen as fast as it possibly can. 
This causes it to use a lot more CPU than it actually needs.

### Delta Time
In math, the Greek letter Delta is often used to represent a change in a value.
In game dev, we use 'delta time' to represent the amount of time that has 
passed since the last frame was drawn. 
This value is useful to decouple the game's speed from the speed it's being drawn into the screen.

If your computer speeds up, 
the asteroids shouldn't also speed up. 
Conversely, if your computer slows down, the asteroids shouldn't also slow down:
they would just move less smoothly.

### Assignment
FPS stands for Frames Per Second. 
We gonna restrict our game to draw a maximum of 60 FPS

1. After initializing pygame, but before the gameloop starts, create:
	1. A new [`pygame.time.Clock`](https://www.pygame.org/docs/ref/time.html#pygame.time.Clock) object.
	2. A `dt` variable set to `0`
2. At the end of each iteration of the game loop, call the [`.tick()`](https://www.pygame.org/docs/ref/time.html#pygame.time.Clock.tick) method and pass it `60`. It will pause the game loop until 1/60th of a second has passed.
3. The `.tick()` method also returns the amount of time that has passed since the last time it was called: the delta time. Divide the return value by `1000` (to convert from milliseconds to seconds) and save it into the `dt` variable we created earlier. We're not using `dt` yet, but we will later.
4. Re-run the game. You should still see the same black screen, but this time it should use less of your system's resources!

## Create `pygame.time.Clock` object

``` python
clock = pygame.time.Clock()
```



---
[[5-Game-Loop]]
[[7-Sprites]]