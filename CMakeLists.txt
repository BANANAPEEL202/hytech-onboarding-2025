cmake_minimum_required(VERSION 3.10)
project(Lab3)

# Define the library
add_library(hello_lib STATIC src/hello_lib.cpp)

# Specify include directories for this library
target_include_directories(hello_lib PUBLIC include)

# Define the executable
add_executable(Lab3 src/main.cpp)

# Link the hello_world library to the executable
target_link_libraries(Lab3 PRIVATE hello_lib)

include(GNUInstallDirs)

install (TARGETS Lab3 DESTINATION ${CMAKE_INSTALL_BINDIR})