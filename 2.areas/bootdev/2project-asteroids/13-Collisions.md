You may have noticed that you can fly through asteroids without any consequences.

We need [collision detection](https://en.wikipedia.org/wiki/Collision_detection) . 
Now this is a fairly deep topic,
but we gonna keep things simple:
we'll treat everything including ship, as a circle  when it comes to collisions.

Detecting a collision between two circles is simple:

1. We calculate the distance between the center of the two circles, let's call it `distance` 
2. Let's call the radius of one circle `r1`, and the radius of other circle `r2`
3. If `distance` is less than or equal to `r1 + r2`, the circles are colliding, if not, they aren't

![[Pasted image 20240920210206.png]]

### Assignment
Everything that collides inherits from `CircleShape`, so that seems like a good place to put collision logic.

1. Add another method to that class to check for collisions. It should take 1 argument (another `CircleShape` object) and return `True` or `False`. 
2. Each `CircleShape`'s `position` property is a [`pygame.Vector2`](https://www.pygame.org/docs/ref/math.html#pygame.math.Vector2). Use its [`distance_to`](https://www.pygame.org/docs/ref/math.html#pygame.math.Vector2.distance_to) method to calculate the distance between the two shapes. 
3. After the update step in your game loop, iterate over all of the objects in your asteroids group. Check if any of them collide with the player. If a collision is detected, the program should print `Game Over!` and [immediately exit the program.](https://docs.python.org/3/library/sys.html#sys.exit) 

---
[[12-Asteroids]]
[[14-Shooting]]