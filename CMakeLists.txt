# requirement of cmake version
cmake_minimum_required(VERSION 3.5)
set(CMAKE_CXX_STANDARD 11)

# project name
PROJECT(tiny)

# set the directory of executable files
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${tiny_SOURCE_DIR}/bin)

# find required opencv
set (OpenCV_DIR /usr/local/Cellar/opencv/4.2.0_1)
find_package(OpenCV REQUIRED)

# directory of opencv headers
include_directories(${OpenCV_INCLUDE_DIRS})

aux_source_directory(./src DIR_SRCS)
# name of executable file and path of source file
add_executable(tiny ${DIR_SRCS})

# directory of opencv library
link_directories(${OpenCV_LIBRARY_DIRS})

# opencv libraries
target_link_libraries(tiny ${OpenCV_LIBS})

