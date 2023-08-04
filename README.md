# Robocode-SniperRobot
# SniperRobot - A Circular Rotation Robot for Robocode

## Installation

To use the SniperRobot in the Robocode environment, follow these steps:

1. Download and install Robocode from the official website: https://robocode.sourceforge.io

2. Clone or download the SniperRobot repository from GitHub: (https://github.com/PTshabangu/Robocode-SniperRobot.git)

3. Open Robocode and add the SniperRobot package to your robot directory by navigating to `Options > Preferences > Development Options > Add` and selecting the path to the SniperRobot package.

4. Compile the robot by clicking on the "Compile" button in the Robocode interface or by typing `robocode.compiler.Compiler -d path_to_robot_directory` in the command line.

5. Start a battle in Robocode and select the SniperRobot as one of the participants.

## Robot Design and Implementations

The SniperRobot is a simple robot that uses a circular rotation strategy and pattern matching to dodge bullets fired by opponents. It tries to maintain a distance from the enemy robot and adjusts its firepower based on the distance to the enemy.

### Movement Strategy:

The robot moves in a circular rotation with a given radius using the `moveInRotation(double radius)` method. It rotates slightly to the right and moves ahead to maintain the rotation.

### Dodging Bullets:

The robot uses pattern matching to detect when it's hit by a bullet and responds with the `dodgeBullets(HitByBulletEvent event)` method. When hit by a bullet, the robot calculates the angle between the bullet direction and its heading. Depending on the angle, it either moves back and turns right or moves ahead and turns right to dodge the bullet.

### Adjusting Firepower:

The robot adjusts its firepower based on the distance to the enemy using the `adjustFirePower(double distance)` method. It calculates the firepower as the minimum value between 3 and 400 divided by the distance. This allows the robot to fire stronger shots when the enemy is closer and weaker shots when the enemy is farther away.

### Radar Scanning:

The robot scans for enemy robots using the radar in the `onScannedRobot(ScannedRobotEvent e)` method. It updates the `scannedRobot` variable with the nearest robot scanned by the radar and calls the `adjustFirePower` method to fire at the enemy.

### Handling Collisions:

When the robot hits a wall, it executes the `onHitWall(HitWallEvent e)` method. It moves back to avoid being stuck on the wall and turns right to try to get away from the wall.

## Conclusion

The SniperRobot is a simple yet effective robot that uses circular rotation, pattern matching, and distance-based firepower adjustment to perform well in Robocode battles. Feel free to experiment with different strategies and improve upon its design to create an even more formidable Robocode competitor. Happy Robo-battling!
