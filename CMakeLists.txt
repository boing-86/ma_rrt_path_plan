cmake_minimum_required(VERSION 2.8.3)
project(ma_rrt_path_plan)

find_package(catkin REQUIRED COMPONENTS
  std_msgs
  sensor_msgs
  geometry_msgs
  message_filters
  message_generation
  vehicle_msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES 
#  CATKIN_DEPENDS roscpp rospy std_msgs vehicle_msgs
#  DEPENDS system_lib
)


include_directories(
  include
  ${CMAKE_CURRENT_SOURCE_DIR}/src/
  ${catkin_INCLUDE_DIRS}
)


install(DIRECTORY
    launch
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})

install(PROGRAMS
    src/main.py
    src/MaRRTPathPlanNode.py
    src/ma_rrt.py
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
