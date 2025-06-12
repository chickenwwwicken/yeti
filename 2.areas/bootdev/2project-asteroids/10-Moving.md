Now instead of rotating,
we need the ship to move back and forth with the W and S keys.

### Assignment
1. Create a new constant in `constants.py` to represent the player speed. `PLAYER_SPEED` and give it a `230` value
2. Add a new method to the `Player` class called `.move()` . It takes one argument: `dt`. We want o modify the player's `position` ; but first, we need to do a little math.
	1. We start with a unit vector pointing straight up from `(0,0)` to `(0,1)`.
	2. We rotate that vector by the player's rotation, so it's pointing in the direction the player is facing. 
	3. We multiply by `PLAYER_SPEED * dt`. A larger vector means faster movement.
	4. Add the vector to our position to move the player.

![[Pasted image 20240920183932.png]]

All those words boil down to these two lines of code:

``` python
forward = pygame.Vector2(0, 1).rotate(self.rotation)
self.position += forward * PLAYER_SPEED * dt
```

3. Modify the `update` method in the `Player` class to call the `move` method when the W or S keys are pressed. 

Run the game. you should now be able to fly around the screen with the WASD keys

---
[[9-Moving-Around]]
[[11-Groups]]