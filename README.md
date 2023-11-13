# Team 00 – Java bootcamp
### Console Game & Maven

Surrender, You're Surrounded | |


The program shall generate a random map with obstacles. Both player and its enemies are located on the map in a random manner. Each map element shall have a certain color.

Example of a generated map:

![map](misc/images/map.png)

**Designations**: <br>
`o` - position of a player (program user) on the map.<br>
`#` - obstacle<br>
`x` - enemy (artificial intelligence)<br>
`O` - target point the player must get to before the enemies reach the player. The player is considered to have reached the target cell if they stepped on its position.

**Game rules**:
1. Each participant (player and enemies) may make one move. Then, it's another participant's turn. The enemy is considered to have reached the player if it can step on the player's position by making the current move.
2. Available movement directions are left, right, downward, and upward.
3. If an enemy is unable to move forward (there are obstacles or other enemies around them, or a map edge has been reached), the enemy skips a move.
4. The target point is an obstacle for an enemy.
5. If the player is unable to move forward (surrounded by obstacles, enemies, or has reached an edge of the map), the player loses the game.
6. The player loses if an enemy finds them before they reach the target point.
7. The player starts the game first.

**Architecture requirements**:
1. Two projects implemented: Game (contains game logic, application entry point, output functionality, etc.) and ChaseLogic (contains pursuing algorithm implementation).
2. Both are mavenprojects, and ChaseLogic was added as a dependency to pom.xml inside Game.
3. Game.jar archive is portable:  JCommander and JCDP must be directly included in the archive. At the same time, all libraries connected to the project declared as maven-dependency. To build such archive, the following plugins used.

Created a configuration file called application-production.properties. In this file, specified application settings. The example of this file is shown below:

enemy.char = X <br>
player.char = o <br>
wall.char = \# <br>
goal.char = O <br>
empty.char= <br>
enemy.color = RED <br>
player.color = GREEN <br>
wall.color = MAGENTA <br>
goal.color = BLUE <br>
empty.color = YELLOW

This configuration file located in resources folder of the launched jar archive.
