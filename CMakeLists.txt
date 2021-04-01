cmake_minimum_required(VERSION 3.11)

set(CMAKE_C_STANDARD   11)
set(CMAKE_C_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD   14)
set(CMAKE_CXX_EXTENSIONS OFF)

set(CMAKE_C_FLAGS   "-Wall -Wextra")
set(CMAKE_CXX_FLAGS "-Wall -Wextra -Weffc++")
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
PROJECT(CyclicTestCpp CXX)
ENABLE_LANGUAGE(C)

message("configuration: ${CMAKE_CONFIGURATION_TYPES}")
message("type: ${CMAKE_BUILD_TYPE}")

add_subdirectory(src)
add_subdirectory(platforms)
