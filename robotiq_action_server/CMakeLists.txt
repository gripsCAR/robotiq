cmake_minimum_required(VERSION 2.8.3)
project(robotiq_action_server)

find_package(catkin REQUIRED COMPONENTS
  actionlib
  actionlib_msgs
  control_msgs
  message_generation
  robotiq_c_model_control
  robotiq_s_model_control
  rospy
)

## Generate actions in the 'action' folder
add_action_files(
  FILES
  CModelCommand.action
)

generate_messages(DEPENDENCIES actionlib_msgs control_msgs)

catkin_package(CATKIN_DEPENDS 
  actionlib 
  actionlib_msgs 
  control_msgs 
  message_runtime
  robotiq_c_model_control 
  robotiq_s_model_control 
  rospy
)


include_directories(
  ${catkin_INCLUDE_DIRS}
)
