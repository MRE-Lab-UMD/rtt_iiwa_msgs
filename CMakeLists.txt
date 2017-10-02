cmake_minimum_required(VERSION 2.8.3)
project(rtt_iiwa_msgs)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages

find_package(catkin REQUIRED COMPONENTS
  iiwa_msgs
  rtt_diagnostic_msgs
  rtt_geometry_msgs
  rtt_roscomm
  rtt_rosnode
  rtt_sensor_msgs
  rtt_std_msgs
)

ros_generate_rtt_typekit(iiwa_msgs)
ros_generate_rtt_service_proxies(iiwa_msgs)

orocos_generate_package(
  DEPENDS iiwa_msgs
  DEPENDS_TARGETS rtt_roscomm rtt_std_msgs rtt_sensor_msgs rtt_geometry_msgs rtt_diagnostic_msgs )
