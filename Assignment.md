# Assignment 1
The purpose of this assignment is to investigate how to steer a mobile robot towards a goal pose by using the point-and-shoot and servoing methods.

### Getting Ready
It is assumed you have completed all ROS "Getting Started" [tutorials](http://www.ros.org/wiki/ROS/Tutorials). If you did not, do it now.
Follow the installation instructions in the Readme file in the same repository. You will be controlling the TurtleBot 3 directly with velocity commands in an empty world (there is not obstacle avoidance in place).

### The Task
In this task you are going to develop a couple of ‘steering nodes’. A ‘steering node’ makes the robot drive to the goal pose which it receives as a [geometry_msgs/PoseStamped](http://docs.ros.org/melodic/api/geometry_msgs/html/msg/PoseStamped.html) message on the topic ‘/move_base_simple/goal’. It also subscribes to the topic ‘/odom’ to receive robot pose updates in the form of [nav_msgs/Odometry](http://docs.ros.org/melodic/api/nav_msgs/html/msg/Odometry.html) messages and steers the robot to the goal via [geometry_msgs/Twist](http://docs.ros.org/melodic/api/geometry_msgs/html/msg/Twist.html) messages which it publishes on ‘/cmd_vel’.

![Figure 1](https://raw.githubusercontent.com/fontysrobotics/ar_minor_assignment1/master/doc/figure1.png) 

Extend the ar_minor_assignment1 package by adding your code in the src folder. This folder will contain the source code for your ROS nodes. Write the following steering nodes in python or C++:

- **‘pointshoot_node’**: This node must rotate the robot (turtlebot3) in place to point towards the goal, then drive in a straight line towards the goal and finally rotate to comply with the goal orientation.
- **‘servoing_node’**: This node uses servoing (control laws) to reach the goal: linear speed proportional to remaining distance to goal, and angular speed proportional to alfa and beta angles (see slides in the ar_minor_assignment1_info.pdf file inside the doc folder)

#### Hints:
- You will find that representing the robot position error, i.e. the difference between its current pose and the goal pose, in polar coordinates facilitates the problem. You can represent the robot’s position in terms of a distance and an angle to the goal.
- Note that the orientation is defined in terms of a Quaternion, i.e. do not expect values in degrees or radians. Convert the Quaternion to Yaw if you need an angle representation.
- ROS has support for datatypes such as [Quaternions](http://wiki.ros.org/tf2/Tutorials/Quaternions) These classes (e.g. C++: tf::Quaternion, Python: tf.transformations) and helper functions, e.g. C++ tf::getYaw, Python: euler_from_quaternion and C++: tf::createQuaternionFromYaw, Python: quaternion_from_euler. To use any of these put the following line in your code: (C++: #include <tf/transform_datatypes.h>), (Python: from tf.msg import tfMessage)
- ROS has support for calculations involving angles ([wiki](http://wiki.ros.org/angles), [Code API](https://docs.ros.org/api/angles/html/))

#### Research recommendation
- Investigate and compare the performance of both steering nodes

#### What to submit
Your submission for this assignment will have two parts:
1. The source code, i.e. a zip (or rar) file containing the package
2. A document which should:
  1. explain how everything works and include computation graph
  2. describe test scenario’s, and include test vectors (using rostopic pub on topic /goal)
  3. describe the results of your tests and include screen dumps of trails in Stage and/or Rviz
3. A video showing the virtual turtlebot3 (Rviz) performing the two steering.

#### After this Assignment
Please follow the [TF2 Tutorials](http://wiki.ros.org/tf2/Tutorials) (Python) and the [Stage tutorials](http://wiki.ros.org/stage/Tutorials) (no needed if you did the Navigation Challenge)