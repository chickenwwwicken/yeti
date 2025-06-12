Currently, we manually call `.update()` and `.draw()` on the `player` object, 
which means our game loop is going to get more and more cluttered as we add additional objects to the game. 
Fortunately, pygame has a solution!

The Group class is a container that holds and manages multiple game objects.
We can organize our objects into various groups to track them more easily.

You can think of them as a sort of Venn Diagram. 
An object can be in multiple groups at the same time!
Eventually, our game's groups will look something like this.

![[Pasted image 20240920192537.png]]

### Creating and using groups
You can create a new empty group like this: 

``` python
my_group =pygame.sprite.Group()
```

To add all instances of a `Player` to two groups,
`group_a` and `group_b` in this example, 
we add a static field called `containers` to the class:

``` python
Player.containers = (group_a, group_b)
```

Note: after changing a static field like containers, 
make sure to create all Player objects after the change.
This way, they will be correctly added to the groups.

You can iterate over objects in a group just like any other collection in Python:

``` python
for thing in group:
    # do stuff with 'thing'
```

### Assignment
Before the game loop starts:
1. Create two groups in `main.py`
	1. `updatable` - all the objects that can be updated
	2. `drawable` - all the objects that can be drawn
2. Add the player to both groups.
3. Change game loop to use the new groups instead of the `Player` object directly.
	1. iterate over all "updatables" and `.update()` them 
	2. iterate over all "drawables" and `.draw()` them 

---
[[10-Moving]]
[[12-Asteroids]]

---
## pygame.sprite.Groups

A container class to hold and manage multiple Sprite objects.

`pygame.sprite.Group.sprites`
list of the Sprites this Group contains

`pygame.sprite.Group.copy`
duplicate the Group

`pygame.sprite.Group.add`
add Sprites to this Group

`pygame.sprite.Group.remove`
remove Sprites from the Group

`pygame.sprite.Group.has`
test if a Group contains Sprites

`pygame.sprite.Group.update`
call the update method on contained Sprites

`pygame.sprite.Group.draw`
blit the Sprite images

`pygame.sprite.Group.clear`
draw a background over the Sprites

`pygame.sprite.Group.empty`
remove all Sprites

### More info on groups

Groups are a collection of Sprites: 
- Just like a list can hold a collection of items, a `pygame.sprite.Group` holds a collection of sprites. It's used to organize and manage multiple sprite objects together.

Group Operations:
- Like lists you can add to your 'updatable' group like this: `updateable.add(sprite)` 
- You can also remove from 'updateable' group like this: `updateable.remove(sprite)`

Difference from Lists:
- While you could manage your sprites using a regular list, using `pygame.sprite.Group` makes it easier to call methods on all its member sprites at once. For example, you can update all sprites in the group by calling `updateable.update()` 

Specifics:
	- Groups are specifically designed to work with `pygame` . They provide helpful methods, like `draw()` and `update()` to handle common tasks on all contained sprites, which you wouldn't get with a regular list. cax2345