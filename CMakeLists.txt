cmake_minimum_required(VERSION 3.5)
project(dlib_ros)

# enable C++11 standard (current directory scope)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON) # prevent fallback

if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
  set(CMAKE_BUILD_TYPE Release CACHE STRING "Choose the type of build." FORCE)
  set_property(CACHE CMAKE_BUILD_TYPE PROPERTY STRINGS "Debug" "Release"
    "MinSizeRel" "RelWithDebInfo")
endif()

set(CMAKE_CXX_FLAGS "-Wall -Wextra")
# set(CMAKE_CXX_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")

# This should come before any other packages
find_package(catkin REQUIRED)
catkin_package(
	INCLUDE_DIRS DLib/include
	LIBRARIES DLib # this is needed to include library names into ${PROJECT_NAME}Config.cmake
	# CATKIN_DEPENDS
    # DEPENDS
    # CFG_EXTRAS
	)

add_subdirectory(DLib)

