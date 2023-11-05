cmake_minimum_required(VERSION 3.12)

project(ShinyUWPLibBuilder)

# WinRT / UWP Compatibility
set(CMAKE_SYSTEM_NAME WindowsStore)
set(CMAKE_SYSTEM_VERSION 10.0)

# Add include directories from the 'include' folder
include_directories(${CMAKE_SOURCE_DIR}/Shiny/include)

# Collect all the .c files in the src directory to build the library
file(GLOB LIB_SOURCES ${CMAKE_SOURCE_DIR}/Shiny/src/*.c)

# Create a static library from the collected sources
add_library(ShinyUWPLib STATIC ${LIB_SOURCES})

