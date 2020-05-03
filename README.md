## Adaptive Robotics Minor - Assignment 1
The repository hosts the first assignment for the ROS class of Adaptive robotics minor.

#### Prerequisite setup
The assignment requires the student to have installed the turtlebot3 core and simulation packages. This is due the fact that the robot is used for the assignment is a virtual one in an empty world, capable of responding to movement commands and tracking goal commands.

*Note: In case the turtlebot3 packages aren't installed the following commands subsection can be used:*
```bash
sudo apt install ros-melodic-turtlebot3 ros-melodic-turtlebot3-simulations
sudo apt install ros-melodic-gazebo-ros
sudo apt install ros-melodic-gazebo-ros-control
sudo apt install ros-melodic-gazebo-ros-pkgs
sudo apt install ros-melodic-gazebo-plugins
sudo apt install ros-melodic-hls-lfcd-lds-driver
```
*Note: In case there are any cloned any turtlebot3 packages inside the catkin workspace it is mandatory to remove them and clean the workspace in case you wish to install them with the commands listed in the previous section*

#### Setting up the assignment
Once the prerequisites are satisfied the assignment can be cloned in the workspace with the following command relative to the workspace source folder:
```bash
git clone https://github.com/fontysrobotics/ar_minor_assignment1.git
```
**Warning:** *Cloning the repository allows you to commit and track only local changes while pushing the changes is denied. If there is a wish for pushing the changes it is recommend to use the github fork functionality and clone the repository that is created.*

The simulation will bring up gazebo, a functional robot model with transform frames and a pre-configured rviz view. To run the the simulation the command can be used:
```ros
roslaunch ar_minor_assignment1 simulation.launch
```

#### Next steps
- The assignment itself can be found in the repository as the Assignment.md file
- For a reference video made by previous students of the minor visit:
https://youtu.be/q999uX0qbeE
https://youtu.be/9w8uK_pDoiI