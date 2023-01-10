cmake_minimum_required(VERSION 2.8.3)
project(competicion_gazebo_sim)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS    
    roslaunch 
    roslint 
    roscpp 
    std_msgs
    sensor_msgs
    geometry_msgs
    tf2 
    tf2_ros
)
catkin_package(
  CATKIN_DEPENDS roscpp sensor_msgs
#   DEPENDS Boost
)


#############
## Install ##
#############

roslaunch_add_file_check(launch)

install(
  DIRECTORY launch 
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
