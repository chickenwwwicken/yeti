In pygame, there is a base class called Sprite, 
to represent visual objects.

### Assignment
In our game, asteroids are visually represented as circles, a
and the player is a triangle.
However, detecting collisions between circles and triangles is hard.
To avoid this problem, we can cheat a little bit: 
the player will secretly be a circle. 

![[Pasted image 20240920150937.png]]

*The red circle won't be visible in the game*

Let's create a `CircleShape` class that inherits from `Sprite` to represent
objects in our game that are treated as circles (even if they aint).

Create a new `circleshape.py` file and paste in the following code: 

``` python
import pygame

# Base class for game objects
class CircleShape(pygame.sprite.Sprite):
    def __init__(self, x, y, radius):
        # we will be using this later
        if hasattr(self, "containers"):
            super().__init__(self.containers)
        else:
            super().__init__()

        self.position = pygame.Vector2(x, y)
        self.velocity = pygame.Vector2(0, 0)
        self.radius = radius

    def draw(self, screen):
        # sub-classes must override
        pass

    def update(self, dt):
        # sub-classes must override
        pass
```

`CircleShape` extends the `Sprite` class to also stores:
- position
- velocity
- radius

Later we override the `draw` and `update` methods with subclasses.

---
[[6-FPS]]
[[8-Draw-Player]]