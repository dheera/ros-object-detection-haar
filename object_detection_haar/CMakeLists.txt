cmake_minimum_required(VERSION 2.8.3)
project(object_detection_haar)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES roboteq_transfer_command
#  CATKIN_DEPENDS roboteq_msgs roscpp rospy std_msgs
#  DEPENDS system_lib
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

catkin_install_python(PROGRAMS
  nodes/object_detection_haar_node
  nodes/cv_bridge.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY
  nodes/haar
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

