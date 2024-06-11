cmake_minimum_required(VERSION 3.10)
project(MyProject)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Find all subdirectories in the include directory
file(GLOB_RECURSE INCLUDE_DIRS RELATIVE ${CMAKE_SOURCE_DIR}/include ${CMAKE_SOURCE_DIR}/include/*)

# Add each subdirectory to the include path
foreach(dir ${INCLUDE_DIRS})
    if(IS_DIRECTORY ${CMAKE_SOURCE_DIR}/include/${dir})
        include_directories(${CMAKE_SOURCE_DIR}/include/${dir})
    endif()
endforeach()
