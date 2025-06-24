Let's add the ability to shoot

Bullets:
- Are small circles
- Move at a constant speed in a straight line
- Split up asteroids when they collide with them
- Are spawned by player input (spacebar) and move in the direction the player is facing. 

### Assignment
1. Create a new `Shot` class to represent a bullet. It should also inherit from `CircleShape` so that it can use our collision detection code. If you need inspiration, it should look very similar to our `Asteroid` class. Use a new `SHOT_RADIUS` constant and set it to `5`.
2. Set up a new group in your initialization code that contains all of your shots.
3. Add `PLAYER_SHOOT_SPEED` to your constants file, with a value of `500` 
4. In your `Player` class, add a new method called `shoot`. This method should:
	1. Create a new shot at the position of the player
	2. Set the shot's `velocity`:
		1. Start with a `pygame.Vector2` of `(0, 1)` 
		2. `.rotate()` it in the direction the player is facing. 
		3. scale it up (multiply by the `PLAYER_SHOOT_SPEED`) to make it move faster
5. Inside your `Player` class, handle the spacebar (`pygame.K_SPACE`) and call the `shoot` method when it is pressed.

Run your game, make sure bullets are being created and moving in the correct direction. 
- It's expected that holding the spacebar will create a constant stream of bullets
- It's expected that bullets pass through asteroids without any consequences. 

``` python
import pygame
from constants import *
from circleshape import CircleShape
```

``` python
class Shot(CircleShape):
    def __init__(self, x, y):
        super().__init__(x, y, SHOT_RADIUS)

    def draw(self, screen):
        pygame.draw.circle(screen, 'white', self.position, self.radius, 2)

    def update(self, dt):
        self.position += self.velocity * dt
```

---
[[13-Collisions]]
[[15-Rate-Limit]]