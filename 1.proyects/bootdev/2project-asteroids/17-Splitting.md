in the original game, part of the challenge comes from the fact that larger asteroids split into smaller, faster asteroids when you shoot them. 

Instead of calling `asteroid.kill()` in our game loop, let's call `asteroid.split()`. 
This is a new method we'll be writing on the `Asteroid` class. 
To start, let's just have the split method call `self.kill()` like before.
This should keep the behavior the same as before, 
but give us the room to add our splitting logic.

### Assignment
Add a new `.split()` method to the `Asteroid` class. It should: 
1. Immediately `.kill()` itself (think about it: this asteroid is always destroyed, and maybe we'll spawn new ones)
2. If the radius of the asteroid is less than or equal to `ASTEROID_MIN_RADIUS`, just `return`, this was a small asteroid and we're done. 
3. Otherwise, we need to spawn 2 new asteroids... 

### Spawning new Asteroids

We want new asteroids to move in new random directions. 

![[Pasted image 20240920212504.png]]

The red arrow is our current velocity, and the dotted white arrows are the trajectories of the new asteroids. 

1. Import the `random` module.
2. Use [`random.uniform`](https://docs.python.org/3/library/random.html#random.uniform) to generate a random angle between `20` and `50` degrees. This will be the blue angle on the diagram.
3. Use the `rotate` method on the asteroid's `velocity` vector to create 2 new vectors, that are rotated by `random_angle` and `-random_angle` respectively (they should split into opposite directions).
4. Compute the new radius of the smaller asteroids using the formula `old_radius - ASTEROID_MIN_RADIUS` 
5. Create two new `Asteroid` objects at the current asteroid position with the new radius. 
6. Set the first's velocity to the first new vector, but make it move faster by scaling it up (multiplying) by `1.2` 
7. Do the same for the second asteroid, but with the second new vector.

Run the game, and make sure that the following logic works when a bullet hits an asteroid:

- Large asteroids split into medium asteroids
- Medium asteroids split into two small asteroids
- Small asteroids disappear when destroyed

---
[[16-Destruction]]
[[18-Submit]]