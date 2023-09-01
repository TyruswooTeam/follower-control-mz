## WARNING: This is an older version!
It lacks the features and improvements of this plugin's later versions.
To get the latest version for free, visit
[Tyruswoo.com](https://www.tyruswoo.com).

# Tyruswoo Follower Control v1.0.1 for RPG Maker MZ

Provides greater control of party follower movement!

Allows event commands targeting the “player” to affect any follower of your choosing!

Plus, unlimited followers!

## Plugin commands
| Command               |  Action                    |
|-----------------------|----------------------------|
| Leader                |  Selects the party leader. (Default.) |
| Follower 1            |  Selects the 1st follower. |
| Follower 2            |  Selects the 2nd follower. |
| Follower 3            |  Selects the 3rd follower. |
| Follower 4            |  Selects the 4th follower. |
| Follower 5            |  Selects the 5th follower. |
| Follower 6            |  Selects the 6th follower. |
| Follower 7            |  Selects the 7th follower. |
| Follower 8            |  Selects the 8th follower. |
| Follower 9            |  Selects the 9th follower. |
| Follower by Position  |  Select any follower, based on marching order. |
| Follower by Name      |  Select follower by name of actor in database. |
| Follower by Actor ID  |  Select follower by actor ID. |
| Stop Chase             | Prevent followers from chasing the leader. |
| Chase                  | Allow followers to chase the leader. (Default.) |
| Pose                   | Change a party member's character image to pose. |
| Reset Pose             | Change a party member to their default pose. |

## Plugin parameters

| Parameter | Meaning |
|-----------|---------|
| Max Party Members        | Set how many party members can be in battle at a time. The current battle party will also be visible in the follower lineup. Default 4. |
| Search Limit              | Set the pathfinding search limit. Default 12. |

## Script calls
*(Advanced. Use these within the Set Move Route command.)*

| Script | Action |
|--------|--------|
| `this.path(x, y)`          | Pathfind to the absolute coordinates indicated. |
| `this.path('event', id)`   | Pathfind to the event of ID number id. |
| `this.path('e', id)`       | Same as this.path('event', id). May use 'E'. |
| `this.path('follower', i)` | Pathfind to the follower of position i. |
| `this.path('f', i)`        | Same as this.path('follower', i). May use 'F'. |
| `this.path('leader')`      | Pathfind to the party leader. |
| `this.path('L')`           | Same as this.path('leader'). May use 'l'. |
| `this.moveToward(x, y)`    | Move toward the absolute coordinates indicated. |
| `this.moveToward('e', id)` | Move toward the event of ID number id. |
| `this.moveToward('f', i)`  | Move toward the follower of position i. |
| `this.moveToward('L')`     | Move toward the party leader. May use 'l'. |

## Basics of how to use this plugin
1. First, select the desired party member. This may be the leader, for
   default RPG Maker behavior. To control followers, select a follower.
2. Next, use an event command on the "player", and the selected party member
   will be affected! This works for many commands, including:
    - Set Move Route
    - Show Balloon Icon
    - Show Animation
    - Transfer Player
    - Conditional Branch
3. Note that if you are moving the party leader, the followers by default
   will chase the leader. If you want the leader to move independently,
   without the followers chasing, you will need to use the "Stop Chase"
   plugin command.
4. After you are done with the eventing, remember to use the "Leader" and
   "Chase" plugin commands to return to default RPG Maker behavior, if
   desired.

## Advanced uses for this plugin
 - Make common events with preset movement patterns for the party. Then,
   use these movement patterns for cutscenes throughout the game!
 - You can make a follower that looks transparent, like a ghost! Select a
   follower, then using the Set Move Route command to change the follower's
   opacity, and/or to turn off (or on) the follower's walking animation,
   stepping animation, or direction fix.
 - You can make a follower turn toward the party leader. First, select a
   follower. Then, use the Set Move Route command and use the move route
   "turn toward player". (If you also want the party leader to turn
   toward the follower: Use conditional branches to check the direction
   faced by the follower; then, inside the conditional branch, select the
   leader, and use Set Move Route to make the leader face the opposite
   direction.)
 - If followers are on the same tile as the leader, you can make them
   face the same direction as the leader. Select a follower, then use the
   Set Move Route command and use the move route "turn toward player".
   (This also works for events that are on the same tile as the leader.)
 - Poses! These allow you to change an actor's character image, without
   needing to know which actor is being affected. Based on the follower
   you choose, the follower's actor's character image will change to the
   pose you choose. Example: If you have an actor named Tyruswoo with
   character image "Tyruswoo.png", then you can use the Pose plugin command
   with the argument "wounded" to change the character's image to
   "Tyruswoo_wounded.png". Most importantly, this affects the chosen
   follower, without needing to know which actor ID is being affected, and
   without needing to know the current graphic of the actor. To change the
   pose back to default, use the Reset Pose plugin command.
 - Pathfinding! You can make any character (party leader, follower, or
   event) take a step toward coordinates, or a step toward any other
   follower or event! Within the Set Move Route command, use this script:
   this.path(x, y) and the character will step toward coordinates x,y.
   To make the character step toward a follower, use the script
   this.path('follower', i) where i is the position (marching order) of the
   follower. To make the character step toward the party leader, use the
   script this.path('leader'). To make the character step toward an event,
   use the script this.path('event', i) where i is the ID number of the
   event. If you don't want pathfinding, but want the character to attempt
   to take a step without trying to avoid walls, you can use the script
   this.moveToward(x,y), this.moveToward('follower',id),
   this.moveToward('event',i), or this.moveToward('leader'). In all these
   scripts, you can also abbreviate 'follower' to 'f', 'leader' to 'l', and
   'event' to 'e'. Using abbreviations can make it easier to read the
   scripts inside the Set Move Route window. Note that by default, followers
   have Through On, so if you want the followers to pathfind around
   solid obstacles, you will need to use Set Move Route on the follower to
   set Through Off.

### For more help using the Follower Control plugin, see [Tyruswoo.com](https://www.tyruswoo.com).

## Version History:
**v1.0** - 8/22/2020
- Follower Control released for RPG Maker MZ!

**v1.0.1** - 8/31/2023
- This older plugin is now free and open source under the [MIT license](https://opensource.org/license/mit/).

> **Remember, only you can build your dreams!**
> 
> *Tyruswoo*
