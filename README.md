## Requirements

**1. Obstacle Detection:** The computer vision system should be able to detect obstacles in the environment. This involves identifying objects such as furniture, walls, and other obstacles that the vacuum cleaner needs to navigate around.

**2. Object Classification:** Once an obstacle is detected, the computer vision system should classify the type of obstacle. For example, it should distinguish between a chair, a table, or a wall. This information can help the robot make decisions about how to navigate around the obstacle.

**3. Distance Estimation:** The computer vision system should be able to estimate the distance to obstacles. This information is crucial for the robot to plan its path effectively and avoid collisions.

**4. Path Planning:** Based on the detected obstacles and their distances, the computer vision system should generate a path for the robot to follow. This path should navigate the robot around obstacles while efficiently covering the entire cleaning area.

**5. Real-Time Updating:** The computer vision system should continuously update the robot's path as the environment changes. If new obstacles appear or existing obstacles move, the robot needs to adjust its path accordingly to avoid collisions.

**6. Integration with Robot Control:** Finally, the computer vision system needs to communicate with the robot's control system, typically through the Raspberry Pi, to send commands for navigation. This includes commands to move forward, backward, turn, etc., based on the planned path and obstacle avoidance strategy.

## Solutions

We will use the JetBot's **collision avoidance**. To accomplish this task we will need to take pictures of the classroom, train a neural network, and then optimize and run the model. **Distance estimation** and **real time updating** will be automatically accounted for by the JetBot's processing.

![NVIDIA JetBOT](https://www.nvidia.com/content/dam/en-zz/Solutions/intelligent-machines/embedded-systems/embedded-jetbot-ai-kits-fabo-2c50-d@2x.jpg)

Additionally, the JetBot software automatically controls the motors which eliminates the need for any form of **integration with robot control**.

**Path Planning:** In order to have the Robot Vaccum map out the entire classroom and travel across the room, a LIDAR sensor will be needed.

![Lidar Sensor](https://m.media-amazon.com/images/I/515P0yY+uxL.jpg)

### Goal Specification:

#### Sheel Shah:
1. **Goal**: Implement Collision Avoidance System
   - **Specific**: Develop and integrate a collision avoidance system into the robot's programming using NVIDIA JetBot's collision avoidance capabilities.
   - **Measurable**: Achieve at least 90% accuracy in detecting and avoiding obstacles in simulated and real-world environments.
   - **Achievable**: Utilize OpenCV and TensorFlow libraries to train the neural network for obstacle detection and avoidance.
   - **Relevant**: Ensure that the collision avoidance system aligns with the project's objective of enabling the robot to navigate safely in the classroom environment.
   - **Time-bound**: Complete the implementation and testing phase within two weeks.

![Collision Avoidance](https://i.ytimg.com/vi/mwOVFXkc1WI/maxresdefault.jpg)

#### Fikir Reta:
2. **Goal**: Develop Path Planning Algorithm
   - **Specific**: Design and implement a path planning algorithm using data from the lidar sensor to enable the robot to navigate along a designated path in the classroom.
   - **Measurable**: Achieve smooth and efficient path traversal with minimal deviations from the planned path, verified through simulated and real-world testing.
   - **Achievable**: Utilize ROS (Robot Operating System) and SLAM (Simultaneous Localization and Mapping) techniques to process lidar data and generate an accurate map of the environment.
   - **Relevant**: Ensure that the path planning algorithm supports the overall objective of optimizing the robot's navigation efficiency while avoiding collisions.
   - **Time-bound**: Complete the development and testing of the path planning algorithm within four weeks.


## Lidar Sensor Plan
### Data Acquisition:

Initialize LiDAR Sensor: Begin by initializing the LiDAR sensor in your Python script. This typically involves setting up the communication interface (e.g., UART, USB) and configuring any required parameters such as baud rate or scan frequency.
Start Data Acquisition: Once the sensor is initialized, start acquiring LiDAR data. This may involve sending commands to the sensor to begin scanning and continuously receiving scan data packets.
Read LiDAR Scan Data: Continuously read LiDAR scan data packets from the sensor. Each packet contains information about the distance measurements at various angles around the sensor's rotation.
Data Processing:

Parse Scan Data: Parse the raw LiDAR scan data packets to extract distance measurements and corresponding angles. This involves unpacking the data and converting it into a usable format for further processing.
Coordinate Transformation: If necessary, perform coordinate transformation to align the LiDAR data with the coordinate system of the JetBot. This ensures consistency between the LiDAR data and the JetBot's motion.
Data Filtering and Noise Reduction: Apply any necessary filtering or noise reduction techniques to the LiDAR data to improve its quality. This may include outlier removal, median filtering, or averaging over multiple scans.
Mapping/Path Planning:

Occupancy Grid Mapping: Implement an occupancy grid mapping algorithm to create a map of the robot's environment based on the LiDAR data. This involves dividing the environment into grid cells and updating the occupancy status of each cell based on the presence of obstacles detected by the LiDAR.
SLAM (Simultaneous Localization and Mapping): Alternatively, if real-time localization is also required, implement a SLAM algorithm to simultaneously localize the robot within its environment while mapping the surroundings using LiDAR data.
Path Planning Algorithms: Implement path planning algorithms such as A* (A-star) or Dijkstra's algorithm to generate a path for the robot to navigate through the mapped environment. These algorithms take into account the map created from LiDAR data and plan a path that avoids obstacles while reaching the desired goal.

## Action Plan:

#### Sheel Shah:
1. **Week 1**: Research and understand the functionality of the NVIDIA JetBot collision avoidance system. Gather training data for obstacle detection.
2. **Week 2**: Implement and test the collision avoidance system using OpenCV and TensorFlow. Optimize the neural network for improved accuracy.
3. **Week 3**: Integrate the collision avoidance system with the robot's control software. Conduct extensive testing in simulated environments.
4. **Week 4**: Fine-tune the collision avoidance system based on real-world testing results. Document the implementation process and results for future reference.

#### Fikir Reta:
1. **Week 1**: Familiarize with ROS and SLAM techniques for path planning. Set up the lidar sensor and collect data for mapping.
2. **Week 2**: Develop and test the path planning algorithm using simulated environments. Optimize the algorithm for efficient path generation.
3. **Week 3**: Integrate the path planning algorithm with the robot's control software. Conduct testing to validate the accuracy of the planned paths.
4. **Week 4**: Refine the path planning algorithm based on real-world testing feedback. Document the algorithm implementation and performance metrics.

## Learning Objectives:

### Sheel Shah:
- **Objective 1**: Gain proficiency in utilizing NVIDIA JetBot's collision avoidance capabilities.
- **Objective 2**: Develop skills in training neural networks for obstacle detection and avoidance.
- **Objective 3**: Enhance knowledge of OpenCV and TensorFlow for implementing computer vision algorithms.

### Fikir Reta:
- **Objective 1**: Acquire expertise in ROS and SLAM techniques for robot path planning.
- **Objective 2**: Develop proficiency in processing lidar data for environment mapping.
- **Objective 3**: Improve skills in integrating path planning algorithms with robot control systems.

By incorporating these detailed goal specifications, action plans, and learning objectives, Sheel Shah and Fikir Reta will have a clearer roadmap for achieving their respective tasks within the project.

## References

[JetBot](https://jetbot.org/master/examples/collision_avoidance.html)\
[Mobile Robot](https://articulatedrobotics.xyz/mobile-robot-1-project-overview/)\
[Mobile Robot GitHub](https://github.com/joshnewans/my_bot/tree/main)
