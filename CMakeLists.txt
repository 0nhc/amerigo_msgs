cmake_minimum_required(VERSION 3.0.2)
project(amerigo_msgs)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rosmsg
  rospy
  std_msgs
  message_generation
)

add_message_files(
  FILES
  SetPosition.msg
)

add_service_files(
  FILES
  GetPosition.srv
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
    CATKIN_DEPENDS roscpp rosmsg rospy std_msgs
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

install(DIRECTORY msg
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
