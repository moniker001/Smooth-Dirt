# Final Design Document  

**Note that this is sectioned off by use cases as in our Milestone 2 write-up and Iteration 1/2 design documents and discussions.**

### Functionality that is Proposed and Implemented

- **character can navigate with abilities**  
The Player Character can navigate with abilities such as sprinting, jumping, and multi-jumping (after the character has acquired the skill). In addition, the character interacts with enemy collision unique to the direction in which the character collides with the enemy and the speed at which the character collides, resulting in unique movement options for the player depending on how they desire to navigate the map.

- **character can dodge**  
Instead of implementing a dodge function, after reviewing how default movement was implemented in the Unreal Engine already, we decided that implementing a "shield" functionality would be more unique. Dodging would simply entailing adding to the velocity vector of the character, but in our implementation of a "shield" function, we change the character's battlestate such that they are invulnerable to being damaged for a time, but this invulnerability ends if the player character decides to attack or runs out of stamina.

- **character can interact with objects**  
The character has particular interactions with colliding with items (a slight bump, no damage) versus colliding with enemies (strong velocity component aligned with the normal vector against the point and direction of collision). Also, the character can pick up items now with specific effects according to what type of item the character picks up.

- **character experience is updated / level up and update stats**  
Combat works as planned. An enemy death results in a player character receiving experience if they are the one who has dealt the killing blow. If their experience reaches a certain point, then their level increases, and along with that, their stats (attack power) increases at a fixed rate. Then, they have to kill more enemies and receive more experience to get to the next level.

- **player death**  
When the player's health is depleted, the player enters a death state, in which the player is unable to perform any actions in the game. The player can then access the pause menu and select the option to start a new game, continue from the last save checkpoint, or exit the game.

- **power-up items**  
We've implemented a power-up item that boosts your attack power for a duration, and when it runs out, your attack power returns to normal.

- **healing items**  
There are two items can regenerate either your health or stamina upon pick-up.

- **menu exists**  
Pressing P allows you to pause the menu and choose from various options. Note that the menu is created in Unreal Engine and so there are no test cases for the menu states.

- **view character stats**  
We implemented a Player HUD that allows for continuous monitoring of your statistics instead. We thought this would be a more useful statistics-viewing implementation than having to go from a pause menu to view your statistics.

- **equip and remove items**
Instead of items you have to equip and use from a menu, we decided to have items that instantly affect the character when they are picked up. We decided this would fit the aesthetic and feel of the game better, as we shifted from RPG to a more platformer-style game.

- **save and load game**  
Opening the game executable will start a new game by default. The game will automatically save the player's information (level, experience, etc) and location every time the player reaches the next level as a checkpoint. Only one save file is stored at a time and the player can load this save file by accessing the menu and selecting the "Load Last Save" option. The player may also restart the game by selecting "New Game, which will transport the player to the starting position and replace their information with the basic starting information.

### Functionality that is Proposed and Not Implemented

- **character can climb ladders / swim**  
We ultimately decided against implementing climbing and swimming due to the available amount of time versus the amount of animation assets we would have to create for these simple movement options, e.g. for implementing climbing alone would require new animation graphics for getting on a ladder, getting off a ladder, and climbing itself, that couldn't simply be derived from the animation assets we already have for the player character. We decided to prioritize programming the logic of the game instead of working on assets, so we removed climbing and swimming from the goal of the iteration.

- **character can attack with special abilities**  
We decided against implementing this for similar reasons as why we did not choose to implement climbing or swimming - the functionality and game logic would be extremely similar to the attack ability we already have implemented, but it would require more assets for the ability animations.

- **crouching**  
We did not implement crouching in the game because it would require more distinct assets.

- **certain menu functionalities**  
There are certain menu functionalities that we did not implement: difficulty settings, game options (such as volume and brightness), overwrite warning. We did not implement difficulty settings because we ultimately decided to make an extremely difficult game. Furthermore, having different difficulty settings in our particular platformer would simply be adjusting certain damage numbers that enemies inflict on the character, which is fairly trivial. Game options were left out because of time constraints, we thought time would be better used in actually implementing the game versus on something that doesn't affect actual gameplay. Finally, we didn't implement an "overwrite" warning because our game ended up being more platformer, where the game state is less important to save than in something like an RPG, where you have more stats to keep track of, location to save, items, etc.

### Functionality that is Implemented and Not Proposed

- **monster uniqueness**  
We decided to implement different types of monsters to make the game more interesting - this involved designing and implementing different movement patterns and values for the monsters we have in the game. Much of the work here was in handling the collision boxes and placing the monsters on the map.

### Lessons

- **Basic game & object-oriented design concepts**  
First, we learned about important game programming patterns such as the Flyweight, State and Double Buffer models, and how they can be implemented in code. This was also an exercise in our knowledge of object-oriented programming and the benefits of using techniques like inheritance and polymorphism. Second, we learned about the different lower-level moving parts that go into a game, such as physics, graphics & assets, and handling user input, and how they all go together in code.

- **Programming skills**
We learned how to implement much of the above in C++ and also gained experience in working with an industry-standard game engine (Unreal), as well as the nuances that go into working with code developed by someone else. We also learned to use different IDEs (depending on the type of computer and setup each team member had) such as Xcode and Visual Studio. We also worked heavily with Github and became familiar with using it as our version control software. Finally, we learned how to implement object-oriented programming patterns in C++.

- **Team organization**
We learned about the different aspects that go into working as a team on a single long-term project. We learned how to use version control systems to manage several people working on a single project at once, and how to synchronize changes each person made, and also how to manage people working in different coding environments while still allowing everyone to test and compile the same code. We also learned about dividing up work and assigning particular assignments based on each team member's strengths.

- **Asset management**
We learned how to create assets and graphics for games using software like Adoboe Photoshop & Flash, and also how graphics are rendered and collision is created in a game engine like Unreal.
