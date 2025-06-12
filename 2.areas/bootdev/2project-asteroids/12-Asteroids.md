It's arguable that a critical part of Asteroids is Asteroids.
Let's create another class to represent an asteroid.

### Assignment
1. Create a new class called `Asteroid` in a new file called `asteroid.py`.
2. Add a constructor with this signature:

``` python
def __init__(self, x, y, radius):
```

3. Override the `draw()` method to draw the asteroid as a `pygame.draw.circle`. Use its position, radius, and a width of `2` 
4. Override the `update()` method so that it moves in a straight line at constant speed. On each frame, it should add `(velocity * dt)` to its position.
5. In the initialization code in `main` (before the game loop starts), create a new `pygame.sprite.Group` which will contain all of the asteroids.
6. Like we did with the `Player` class, set the static `containers` field of the `Asteroid` class to the new asteroids group, as well as the `updatable` and `drawable` groups.

``` python
Asteroid.containers = (asteroids, updatable, drawable)
```

This ensures that every instance of the Asteroid class is automatically added to these groups upon creation. 

7. We've written an `AsteroidField` class already: it contains logic for spawning new asteroids. Create a new file called `asteroidfield.py`, and import it in your `main.py` file. Paste in this code:

``` python
import pygame
import random
from asteroid import Asteroid
from constants import *


class AsteroidField(pygame.sprite.Sprite):
    edges = [
        [
            pygame.Vector2(1, 0),
            lambda y: pygame.Vector2(-ASTEROID_MAX_RADIUS, y * SCREEN_HEIGHT),
        ],
        [
            pygame.Vector2(-1, 0),
            lambda y: pygame.Vector2(
                SCREEN_WIDTH + ASTEROID_MAX_RADIUS, y * SCREEN_HEIGHT
            ),
        ],
        [
            pygame.Vector2(0, 1),
            lambda x: pygame.Vector2(x * SCREEN_WIDTH, -ASTEROID_MAX_RADIUS),
        ],
        [
            pygame.Vector2(0, -1),
            lambda x: pygame.Vector2(
                x * SCREEN_WIDTH, SCREEN_HEIGHT + ASTEROID_MAX_RADIUS
            ),
        ],
    ]

    def __init__(self):
        pygame.sprite.Sprite.__init__(self, self.containers)
        self.spawn_timer = 0.0

    def spawn(self, radius, position, velocity):
        asteroid = Asteroid(position.x, position.y, radius)
        asteroid.velocity = velocity

    def update(self, dt):
        self.spawn_timer += dt
        if self.spawn_timer > ASTEROID_SPAWN_RATE:
            self.spawn_timer = 0

            # spawn a new asteroid at a random edge
            edge = random.choice(self.edges)
            speed = random.randint(40, 100)
            velocity = edge[0] * speed
            velocity = velocity.rotate(random.randint(-30, 30))
            position = edge[1](random.uniform(0, 1))
            kind = random.randint(1, ASTEROID_KINDS)
            self.spawn(ASTEROID_MIN_RADIUS * kind, position, velocity)
```

8. In the `main.py` file, set the static `containers` field of the `AsteroidField` class to only the `updatable` group (it's not drawable, and it's not an asteroid itself)
9. Create a new `AsteroidField` object in the initialization code. 

Run the game and make sure asteroids are spawning and moving across the screen, and that you didn't break your ship in the process.

---
[[11-Groups]]
[[13-Collisions]]