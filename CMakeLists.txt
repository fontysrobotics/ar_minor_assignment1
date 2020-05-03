cmake_minimum_required(VERSION 2.8.3)
project(ar_minor_assignment1)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
)

## For this assignment it isn't requiered to use custom message or service FILES
## The staments are under this line and they can uncommented if the functionality is desired
## Generate messages in the 'msg' folder
# add_message_files(
#   FILES
#   Message1.msg
#   Message2.msg
# )

## Generate services in the 'srv' folder
# add_service_files(
#   FILES
#   Service1.srv
#   Service2.srv
# )

## Generate actions in the 'action' folder
# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

## Generate added messages and services with any dependencies listed here
# generate_messages(
#   DEPENDENCIES
#   std_msgs
# )

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES ar_minor_assignment1
#  CATKIN_DEPENDS rospy std_msgs
#  DEPENDS system_lib
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)