cmake_minimum_required(VERSION 2.8.3)
project(wsg_32_simulation)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  std_srvs
  urdf
  wsg_32_common
)

catkin_package(
#   INCLUDE_DIRS include
#  LIBRARIES vh_pixelmap
  CATKIN_DEPENDS roscpp urdf std_msgs std_srvs wsg_32_common
#  DEPENDS system_lib
)

## System dependencies are found with CMake's conventions
# find_package(Boost REQUIRED COMPONENTS system)

add_executable(wsg_32_sim_keyboard_teleop src/wsg_32_keyboard_teleop.cpp)
target_link_libraries(wsg_32_sim_keyboard_teleop ${catkin_LIBRARIES})
add_executable(wsg_32_sim_driver src/wsg_32_sim_driver.cpp)
target_link_libraries(wsg_32_sim_driver ${catkin_LIBRARIES})
