Drawing the spaceship for the player 

## Assignment

1. Add this line to `constants.py` to define the size of the player's ship:

``` python
PLAYER_RADIUS = 20
```

2. Create a new file called `player.py` with `Player` class that inherits from `CircleShape`
3. The `Player` coonstructor should take `x` and `y` integers as input, then:
	1. Call the parent class's constructor, also passing in PLAYER_RADIUS
	2. Create a field called `rotation` initialized to `0` 
4. Paste this `triangle` method into your `Player` class: 

``` python
# in the player class
def triangle(self):
    forward = pygame.Vector2(0, 1).rotate(self.rotation)
    right = pygame.Vector2(0, 1).rotate(self.rotation + 90) * self.radius / 1.5
    a = self.position + forward * self.radius
    b = self.position - forward * self.radius - right
    c = self.position - forward * self.radius + right
    return [a, b, c]
```

A player will look like a triangle, even though we'll use a circle to represent its hitbox.
The math of drawing a triangle can be a bit fiddly.

5. To draw the player, override the `draw` method of `CircleShape` . It should take the `screen` object as a parameter, and call [pygame.draw.poligon](https://www.pygame.org/docs/ref/draw.html#pygame.draw.polygon) . It takes:
- The `screen` object
- A color (use white)
- A list of points (use `self.triangle()` that we provided)
- A line width (use `2`)

6. In your main function, instantiate a `Player` object. You can pass these values to the constructor to spawn it in the middle of the screen:
- `x = SCREEN_WIDTH / 2`
- `y = SCREEN_HEIGHT / 2` 

7. Lastly, we need to re-render the player on the screen each frame, meaning inside our game loop. Use the `player.draw(screen)` method we just added to do so.

Run the game. If everything worked, you should see a black screen with a white triangle in the middle. 

---
## pygame.draw.polygon

takes four parameters

``` python
polygon(surface, color, points, width)
```

- surface - surface to draw on
- color - color to draw with, can be RGB tuple, color or *int*
- points - a sequence of 3 or more (x,y) coordinates that make up the vertices of the polygon, each coordinate in thhe sequence must be a tuple/list/pygame.math.Vector2 of 2 ints/floats
- width - (optional) used for line thickness or to indicate that the polygon is to be filled
	- if width == 0 (default) fill the polygon
	- if width > 0 used for line thickness
	- if width < 0 nothing will be drawn

when width is used w values > 1, the edge lines will grow outside the original boundary of the polygon. 

---
[[7-Sprites]]
[[9-Moving-Around]]