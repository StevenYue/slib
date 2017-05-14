cmake_minimum_required(VERSION 2.8.9)
project (slib)
set(CMAKE_CXX_FLAGS_DEBUG)
set(LOCAL_LIB "/usr/local/lib")
set(LOCAL_INCLUDE "/usr/local/include")
add_definitions(-std=c++11)

#Directories
include_directories("${PROJECT_BINARY_DIR}")
include_directories("/usr/lib/x86_64-linux-gnu/")
#include_directories("/home/s/workspace/cpp/SimpleJSON/src/")

#source files
file(GLOB SOURCES  "*.c" "*.cpp")

#header files
file(GLOB HEADERS "*.h")

#executable
add_library(slib  ${SOURCES})

#Adding LIBS
target_link_libraries(slib curl)

#install
install(TARGETS slib  DESTINATION ${LOCAL_LIB})
install(FILES ${HEADERS}  DESTINATION ${LOCAL_INCLUDE})

