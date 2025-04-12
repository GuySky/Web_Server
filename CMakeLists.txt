cmake_minimum_required(VERSION 3.25)

project(webserver)

set(CMAKE_CXX_STANDART 20)

# Creating libraries
add_library(test_lib source/test_lib.cpp)

# Connecting libraries
target_include_directories(test_lib PUBLIC ${CMAKE_SOURCE_DIR}/include)

# Creating executable
add_executable(${PROJECT_NAME} source/main.cpp)

# Connecting libraries to executable
target_link_libraries(${PROJECT_NAME} PRIVATE test_lib)
