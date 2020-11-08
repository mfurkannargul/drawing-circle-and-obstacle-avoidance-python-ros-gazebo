# Drawing a Circle and Obstacle Avoidance with Python Script on ROS and Gazebo Simulation

In the assignment, we were supposed to do a ROS Simulation on Gazebo by using Turtlebot or RosBot. The simulation requires a python script in a class file. In the python script, there must be Lider, Odometry and callbacks. It must publish a motion command to the robot. The motion commands asked are basically circling and obstacle avoidance. Lidar sensors are used for the obstacle avoidance. I carefully read the instructions and started working on it.

- The first task that must be done was to install the ROS environment on Ubuntu so you must have already had a version of Ubuntu on your computer.

- Secondly, I decided to use TurtleBot3 as a ground robot because I saw many sources on Internet about it so I thought it would be easy to search on Internet in case that I get confused implementing.
 
- Then, the first research I’ve done was writing a python script on ROS. It’s the essential issue because it surely takes time to get familiar with working on ROS. There is a beginner tutorial, http://wiki.ros.org/ROS/Tutorials, which explains the basics of ROS. The tutorial must be followed to properly install and work on ROS.

- Next, I worked on the python script after I could open the gazebo with Turtlebot3 by the “roslaunch” command.

Through the python script;

- I firstly tried coding the “circling” part. I did it by using circle.linear.x and circle.angular.z commands and imported required libraries. In this part, it was required to draw a circle with radius of 5 meters. For that, I set the linear velocity to 0.5 and the angular velocity to 0.1. However, it can surely be changed to have different circle trajectories. For instance, the radius becomes 2.5 meters if the angular velocity is set to 0.2. It depends on how large trajectory you desire.

- After that, I did the “obstacle avoidance” part in a different python script at first because I just wanted to see if it’s working. In this part, the algorithm was like that the ground robot starts moving straight and it just stops and turns with angular velocity of 0.5 when the lidar sensors has detected an obstacle near. For the detection, it’s better to check the lidar sensor data from different angles because the obstacle might be on the left or right corner. In this case, the robot cannot detect it and hits it. Hence, the robot might be damaged by this collision.

- Then, I checked the lidar sensor in three different angles at first which are 0 degree, 15 degree, and 345 degree. After the detection of an obstacle, it turns and checks again but this time it checks five different angles that are 0 degree, 15 degree, 30 degree, 330 degree, and 345 degree to be sure that there is no any obstacle around the robot. Otherwise, it may collide and get stuck there so you’d have to restart the algorithm.

- After I made sure that “obstacle avoidance” part is properly working, I tried to combine the separate circling and obstacle avoidance scripts into one python script. It was the most challenging part for me because I didn't use a class in the collision avoidance script whereas I put the functions in a class in the circling script. Hence, I got some errors by combining them but the following tutorial was really helpful to get the OOP with ROS in python: https://roboticsbackend.com/oop-with-ros-in-python/

- Then, I followed the tutorial and understood that errors occurred because I didn’t add “self.” before the variables so they only existed in the scope of the __init__() function. Thus, I fixed the errors and could run the script.

What I’ve learned from the the assignment is basically to write and run a python script in the ROS environment on Gazebo which is quite beneficial for the further works.
