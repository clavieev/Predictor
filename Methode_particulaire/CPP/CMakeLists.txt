project(Predictor_particular_approch_cpp)
cmake_minimum_required(VERSION 3.0)

set(CMAKE_BUILD_TYPE Debug)
set (CMAKE_CXX_STANDARD 11)

find_package(Boost 1.58.0 COMPONENTS filesystem system iostreams REQUIRED)
include_directories(${Boost_INCLUDE_DIR})
link_directories(${Boost_LIBRARY_DIRS})

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIR})
link_directories(${OpenCV_LIBRARY_DIRS})

file(GLOB SOURCES
    robot.h robot.cpp)


    
add_executable(Main Main.cpp)
target_link_libraries(Main ${SOURCES} ${OpenCV_LIBS} ${Boost_LIBRARIES})
