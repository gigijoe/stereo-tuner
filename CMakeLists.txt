cmake_minimum_required(VERSION 2.8)
project( stereo-turner )
find_package( OpenCV REQUIRED )
find_package( PkgConfig REQUIRED )
pkg_check_modules( GTK3 REQUIRED gtk+-3.0 )

add_definitions(-std=c++11)

INCLUDE_DIRECTORIES(${OPENCV_INCLUDE_DIRS})
INCLUDE_DIRECTORIES(${GTK3_INCLUDE_DIRS})

cuda_add_executable( stereo-turner main.cpp)
set(stereo-turner stereo-turner PROPERTY CUDA_STANDARD 11)
target_link_libraries( stereo-turner ${OpenCV_LIBS} ${GTK3_LIBRARIES})

