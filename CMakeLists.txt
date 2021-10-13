cmake_minimum_required(VERSION 3.0)

# set the project name
project(libhddm)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_subdirectory(xml)
file(GLOB SOURCES src/*.cc)
add_library(HDDM STATIC ${SOURCES} src/hddm_r.cpp src/hddm_s.cpp)
include_directories(include ${CMAKE_SOURCE_DIR}/include/HDDM $ENV{JANA_HOME}/include $ENV{ROOTSYS}/include $ENV{XERCES_INCLUDE} $ENV{HDDM_HOME}/include $ENV{CCDB_HOME}/include)
target_compile_options(
  HDDM
  PUBLIC -fPIC
  )
add_dependencies(HDDM hddm_derived_sources)
install(
  TARGETS HDDM
  DESTINATION lib
  )
