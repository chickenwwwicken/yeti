Probably noticed that the weapon is OP as fuck

### Assignment
1. Create a new variable on the `Player` object to act as a timer. It should start with a value of `0` 
2. When the player shoots, set the timer equal to a new constant. I called mine `PLAYER_SHOOT_COOLDOWN` and used `0.3` 
3. Prevent the player from shooting if the timer is greater than `0` 
4. Decrease the timer by `dt` every time `update` is called on the player.

Rerun your game. You should now be only able to shoot every 0.3 seconds.

*Bullets should still pass through without any consequences.* 

---
[[14-Shooting]]
[[16-Destruction]]