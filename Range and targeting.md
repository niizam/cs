Range and targeting | Counter Side

This guide goes into the details of how units target, how they make attacks, and how attacks connect. Its main purpose is to help explain what some of the numbers (as of 5/30 these numbers are not on the wiki yet) mean, and how to use them to compare them across different units.

This section covers terms and concepts that will be used later on. Note that the terms are used in this guide only, and do not necessarily represent the proper words used to describe the ideas.
Position and Hitbox

There are two ways units measure the gap between each other: using the position represented by the white dot, and the edges of their hitbox represented using red boxes. The length of the hitbox is equal to the size of the unit. For the rest of this guide, the terms Position Based and Hitbox Based will be used to distinguish between the two.


Types of attacks

An attack starts from the edges of a unit’s hitbox, and ends some distance away. The left and right edge can — but do not have to — have different distances for their effect. The area covered by the unit’s hitbox is usually included in the attack’s effect area. Attacks are hitbox based, and have a lifetime.

Players familiar with fighting games may recognize the hitbox as the hurtbox, and the attack’s effect area as the hitbox. This guide will not be using this convention, and will instead use hitbox to describe the bounding box around each unit.

Another way for units to attack is by spawning a game object that performs the attack. This game object does not have a hitbox, and is capable of doing a variety of tasks such as moving at a set speed, target finding using a different set of targeting rules and sight, reacting to units getting close, spawning more objects, and making attacks.

Examples of this kind of attack include Titan’s basic attack spawning an explosion on its target, and Xiao shooting a bullet that must physically travel forwards towards the enemy.

The first kind of attack will be referred to as a Direct Attack, and the second as an Indirect Attack. Generally the game object spawned by indirect attacks will make a direct attack at some point.

Before a unit can attack, it must first find a target to attack. This finding process is position based, and uses the sight stat to determine how far it can look. The unit’s targeting type determines what targets are valid, and which to select as the target in the case of multiple valid targets within sight.

Once a valid target is selected, the unit can attempt to make an attack. If the target leaves the unit’s sight range, then it will stay seen for a certain distance before they stop being seen. This extra distance is shown by the other sight stat, and is also position based.

If the unit can see at least one valid target, then it will check to see whether it is in range for any of its skills. Basic attack counts as a skill. This check is hitbox based.

This range defaults to a character specific value that this guide will call the basic range. Some units have skills that overwrite this basic range, which allows them to cast the skill at a greater or lesser range than the rest of their skills. Examples of such characters include Yen Xing Lanchester’s special skill being allowed to be cast at 8m instead of her 1.5m of basic range, and Awakened Lee Sooyeon’s melee attack being limited to a range of 3m compared to her basic range of 8m. It is also possible for them to have a minimum range, such as Awakened Lee Sooyeon’s ranged air attack requiring at least 3m of distance.

Note that some attacks need neither a valid target in range nor in sight. An example of this is Lin Xien’s ultimate where she generates DP. This can effectively be cast at any time when the unit is free to act.

When a direct attack reaches a hitbox of an allowed unit, the owner of the hitbox will be hit. The mechanics of how that plays out will not be covered by this guide.

For direct attacks with 1 valid hit, only one unit will be hit. If the valid hit is 2 or more, then all units will be hit in order of hitbox based distance.

For indirect attacks, the game object is limited to hitting a certain number of units. This is typically set to an unreachable number when this feature is not desired. An example of a unit that uses this is normal Xiao’s special skill where the object dies after hitting two units.

Indirect attacks are sometimes used to deliver buffs or debuffs. In these cases, the buff is typically delivered using a zero damage hit that has a buff or debuff effect. As a consequence of this method of delivery, some buffing and debuffing units will wake sleeping allies or enemies. It may also count as a hit for units like Ryan Ferrierneeds testing, and trigger counter attacks if the hitstun tier matches up. An example of the latter is Awakened Shiyoon’s passive countering an ally Lucrecia’s ETB effect, stopping anyone behind Awakened Shiyoon from receiving the buff.

When these aren’t applied using indirect attacks, they are position based.

Aura buffs — buff circles that follow a specific unit — can be invisible. In these cases, the range limit is typically large enough for it to cover the entire map outside of edge cases in guild coop.

For buff circles that linger on one spot, the circle is not the game object from indirect attacks. The circle is maintained through a buff held by the caster.
