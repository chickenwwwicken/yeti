There are three types of asteroids:
1. Large
2. Medium
3. Small

When a large asteroid is destroyed, it should split into two medium asteroids. 
When a medium asteroid is destroyed, it should split into two small asteroids. 
When a small asteroid is destroyed, it should disappear.

For now, we'll just always make the asteroids disappear when they're destroyed.
We will handle splitting later.

### Assignment
1. Add another collision check to the game loop. Loop over each asteroid, and for each asteroid, loop over each bullet. If a bullet and an asteroid collide, call the `.kill()` method on both objects to remove them from the game. 

The `.kill()` method is a feature built-in to pygame; it will remove the object from all of its groups, so our game will stop drawing and updating it automatically.

Run the game, make sure you can destroy asteroids by shooting them.

## Collision method + kill()

inside the game loop:

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
[[15-Rate-Limit]]
[[17-Splitting]]