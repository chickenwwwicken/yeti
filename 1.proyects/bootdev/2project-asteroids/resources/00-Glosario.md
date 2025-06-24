
![[2-Installation#Creating a Python Virtual Environment.]]

---
![[2-Installation#Downloading venv]]

---
![[2-Installation#Activate venv]]

---
![[2-Installation#Create requirements file and download them]]

---
### Run `main()` directly, don't if its an imported module

``` python
if __name__ == "__main__":
	main()
```

---
![[4-Modules#Importing modules]]

---
![[5-Game-Loop#init pygame in main()]]

---
![[5-Game-Loop#Create a GUI Window]]

---
![[5-Game-Loop#Creating a game loop]]

---
![[5-Game-Loop#Make close button work]]

---
![[6-FPS#Create `pygame.time.Clock` object]]

---
### Use pygame.time.Clock with .tick() with delta time

``` python
dt = clock.tick(60) / 1000
```

At the end of each iteration of the game loop, 
call the [`.tick()`](https://www.pygame.org/docs/ref/time.html#pygame.time.Clock.tick) method and pass it 60.
It will pause the game loop until 1/60th of a second has passed.

The .tick method also returns the amount of time that has passed since the last time it was called: delta time.
Divide the value by 1000 to convert from milliseconds to seconds and save it into the `dt` variable we created earlier.

Also helps use less resources from your computer.

---
### Creating a basic Circle Sprite with pygame

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

also extends the `Sprite` class to store:
- position
- velocity
- radius

---
### Creating a basic Circle Sprite (but Triangle drawn)

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

will look like a triangle, even though we'll use a circle to represent its hitbox

To draw the player, override the `draw` method of `CircleShape` . It should take the `screen` object as a parameter, and call [pygame.draw.poligon](https://www.pygame.org/docs/ref/draw.html#pygame.draw.polygon) . It takes:
- The `screen` object
- A color (use white)
- A list of points (use `self.triangle()` that we provided)
- A line width (use `2`)

[[8-Draw-Player#pygame.draw.polygon]]

---
## Rotate sprite method

``` python
	# just need to do it for one side and 
	def rotate(self, dt):
		self.rotation += PLAYER_TURN_SPEED * dt
```

---
## Move sprite method

``` python
	def move(self, dt):
		forward = pygame.Vector2(0, 1).rotate(self.rotation)
		self.position += forward * PLAYER_SPEED * dt
```

---
## Assigning Keys in `update()` for motions

``` python
	# assigning methods to keys for motion
	def update(self, dt):
		keys = pygame.key.get_pressed()
		if keys[pygame.K_a]:
			self.rotate(-dt)
		if keys[pygame.K_d]:
			self.rotate(dt)
		if keys[pygame.K_w]:
			self.move(dt)
		if keys[pygame.K_s]:
			self.move(-dt)
```

---
![[11-Groups#Creating and using groups]]

---
## Groups examples from Asteroids

this is added before the loop starts

![[06_main#creating groups]]

![[06_main#sorting sprites in groups]]

More info here [[11-Groups#pygame.sprite.Groups]]

---
## Logic for spawning Asteroids

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

---
![[01_CircleShape#Colliding method]]

---
## Shot Class

![[07_shot]]

---
## Shooting Rate-Limit

`PLAYER_SHOT_SPEED` in `constants.py` will determine the limit.
This code below is a method @ `player.py`

``` python
    def shoot(self):
        if self.shoot_timer > 0:
            return
        self.shoot_timer = PLAYER_SHOOT_COOLDOWN
        shot = Shot(self.position.x, self.position.y)
        shot.velocity = pygame.Vector2(0, 1).rotate(self.rotation) * PLAYER_SHOOT_SPEED
```

you also gotta create the `self.shoot_timer` at the Player constructor:

``` python
class Player(CircleShape):
	def __init__(self, x, y):
		super().__init__(x, y, PLAYER_RADIUS)
		self.rotation = 0 
		self.shoot_timer = 0
```

---
## Destroying Asteroids with shots

Inside the game loop: (for asteroid loop was already there.)

``` python
		for asteroid in asteroids:
			if asteroid.collides_with(player):
				print("Game over!")
				sys.exit()

			for shot in shots:
				if asteroids.collides_with(shot):
					shot.kill()
					asteroid.split()
```

---
## Splitting asteroids w/ random angle 

``` python
    def split(self):
        self.kill()

        if self.radius <= ASTEROID_MIN_RADIUS:
            return

        random_angle = random.uniform(20, 50)

        a = self.velocity.rotate(random_angle)
        b = self.velocity.rotate(-random_angle)

        new_radius = self.radius - ASTEROID_MIN_RADIUS
        asteroid = Asteroid(self.position.x, self.position.y, new_radius)
        asteroid.velocity = a * 1.2
        asteroid = Asteroid(self.position.x, self.position.y, new_radius)
        asteroid.velocity = b * 1.2
```

This code goes at `asteroid.py` Asteroid Class and creates 2 new smaller asteroids for each big one that gets .kill()ed.

---

