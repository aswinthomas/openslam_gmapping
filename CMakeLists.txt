cmake_minimum_required(VERSION 2.8)
project(gmapping)

set(CMAKE_INSTALL_PREFIX "/usr")
set(CMAKE_INSTALL_LIBDIR "lib" CACHE PATH "object code libraries (${_LIBDIR_DEFAULT})")
set(CMAKE_INSTALL_INCLUDEDIR "include" CACHE PATH "C header files (include)")

#find_package(catkin)

#catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES gridfastslam scanmatcher sensor_base sensor_range sensor_odometry utils
#)

include_directories(include)

add_subdirectory(gridfastslam)
add_subdirectory(scanmatcher)
add_subdirectory(sensor)
add_subdirectory(utils)

install(DIRECTORY include/
  DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
  FILES_MATCHING PATTERN "*.h"
                 PATTERN "*.hxx"
  PATTERN ".svn" EXCLUDE
)
