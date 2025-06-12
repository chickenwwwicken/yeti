We want the spaceship to be able to move; 
but what does that mean specifically?

1. If we press the left key, ship should rotate left.
2. If we press the right key, ship should rotate right.
3. If we press the up key, ship should move forward.
4. If we press the down key, ship should move backward.

### Assignment
1. Create a new constant in `constants.py` to represent the player's turn speed. I named mine `PLAYER_TURN_SPEED`, and gave it a value of `300` 
2. Add a new method to the Player class called `rotate`. It's gonna take one argument: `dt`. When it's called, it should add `PLAYER_TURN_SPEED * dt` to the player's current `rotation`. 
3. Paste in the following `update` method to the `Player` class:

``` python
    def update(self, dt):
        keys = pygame.key.get_pressed()

        if keys[pygame.K_a]:
            # ?
        if keys[pygame.K_d]:
            # ?
```

4. Update the missing lines to call the `rotate` method with the `dt` argument. To go left instead of right when `a` is pressed, you'll need to invert `dt` 
5. Hook the `update` method into the game loop by calling it on the player object each frame before rendering

Run the game and make sure `a` and `d` keys rotate the player left and right respectively.

``` python
	# just need to do it for one side and 
	def rotate(self, dt):
		self.rotation += PLAYER_TURN_SPEED * dt

	def move(self, dt):
		forward = pygame.Vector2(0, 1).rotate(self.rotation)
		self.position += forward * PLAYER_SPEED * dt

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
		if keys[pygame.K_SPACE]:
			self.shoot()
```

---
[[8-Draw-Player]]
[[10-Moving]]