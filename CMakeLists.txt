cmake_minimum_required(VERSION 2.8.3)
project(rosserial_stm32f7)

find_package(catkin REQUIRED)
catkin_package(
  CFG_EXTRAS ${PROJECT_NAME}-extras.cmake
)

catkin_python_setup()

if(CATKIN_ENABLE_TESTING)
  find_package(rosserial_msgs REQUIRED)
  include_directories(src ${rosserial_msgs_INCLUDE_DIRS})
endif()

install(
  DIRECTORY src/ros_lib
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/src
)

