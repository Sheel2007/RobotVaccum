## Requirements

**1. Obstacle Detection:** The computer vision system should be able to detect obstacles in the environment. This involves identifying objects such as furniture, walls, and other obstacles that the vacuum cleaner needs to navigate around.

**2. Object Classification:** Once an obstacle is detected, the computer vision system should classify the type of obstacle. For example, it should distinguish between a chair, a table, or a wall. This information can help the robot make decisions about how to navigate around the obstacle.

**3. Distance Estimation:** The computer vision system should be able to estimate the distance to obstacles. This information is crucial for the robot to plan its path effectively and avoid collisions.

**4. Path Planning:** Based on the detected obstacles and their distances, the computer vision system should generate a path for the robot to follow. This path should navigate the robot around obstacles while efficiently covering the entire cleaning area.

**5. Real-Time Updating:** The computer vision system should continuously update the robot's path as the environment changes. If new obstacles appear or existing obstacles move, the robot needs to adjust its path accordingly to avoid collisions.

**6. Integration with Robot Control:** Finally, the computer vision system needs to communicate with the robot's control system, typically through the Raspberry Pi, to send commands for navigation. This includes commands to move forward, backward, turn, etc., based on the planned path and obstacle avoidance strategy.

## Solutions

We will use the JetBot's **collision avoidance**. To accomplish this task we will need to take pictures of the classroom, train a neural network, and then optimize and run the model. **Distance estimation** and **real time updating** will be automatically accounted for by the JetBot's processing.

Additionally, the JetBot software automatically controls the motors which eliminates the need for any form of **integration with robot control**.

**Path Planning:** In order to have the Robot Vaccum map out the entire classroom and travel across the room, a LIDAR sensor will be needed.

## References

[JetBot](https://jetbot.org/master/examples/collision_avoidance.html)\
[Mobile Robot](https://articulatedrobotics.xyz/mobile-robot-1-project-overview/)\
[Mobile Robot GitHub](https://github.com/joshnewans/my_bot/tree/main)
