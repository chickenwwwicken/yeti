#### imports

``` python
import pygame
from constants import *
from player import Player
from asteroid import Asteroid
from asteroidfield import AsteroidField
```

#### init pygame + screen and clock

``` python
def main():
	pygame.init()
	screen = pygame.display.set_mode((SCREEN_WIDTH, SCREEN_HEIGHT))
	clock = pygame.time.Clock()
```

#### creating groups

``` python
	updatable = pygame.sprite.Group()
	drawable = pygame.sprite.Group()
	asteroids = pygame.sprite.Group()
	shots = pygame.sprite.Group()
```

#### sorting sprites in groups

``` python
	Asteroid.containers = (asteroids, updatable, drawable)
	AsteroidField.containers = updatable
	asteroid_field = AsteroidField()

	Player.containers = (updatable, drawable)

	Shot.containers = (shots, updatable, drawable)
```

#### player start position

``` python
	player = Player(SCREEN_WIDTH / 2, SCREEN_HEIGHT / 2)
```

#### delta time

``` python
	dt = 0
```

#### game loop

``` python
	while True: 
		for event in pygame.event.get():
			if event.type == pygame.QUIT:
				return

		for obj in updatable:
			obj.update(dt)

		# check for collision + game over exit
		for asteroid in asteroids:
			if asteroid.collides_with(player):
				print("Game over!")
				sys.exit()

			for shot in shots:
				if asteroids.collides_with(shot):
					shot.kill()
					asteroid.split()

		# screen color
		screen.fill("black")

		# drawing sprites
		for obj in drawable:
			obj.draw(screen)

		pygame.display.flip()

		dt = clock.tick(60) / 1000

if __name__ == "__main__":
	main()
```
