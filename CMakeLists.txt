cmake_minimum_required(VERSION 3.0)

# set the project name
project(libhddm)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_subdirectory(xml)
file(GLOB SOURCES src/*.cc)
add_library(HDDM STATIC ${SOURCES})
include_directories(include $ENV{JANA_HOME}/include $ENV{ROOTSYS}/include $ENV{XERCES_INCLUDE})
