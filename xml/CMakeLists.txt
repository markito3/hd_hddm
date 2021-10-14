add_custom_command(
  OUTPUT ${CMAKE_SOURCE_DIR}/include/hddm_s.hpp ${CMAKE_SOURCE_DIR}/src/hddm_s++.cpp
  COMMAND hddm-cpp ${CMAKE_CURRENT_SOURCE_DIR}/event.xml
  COMMAND mv -v ${CMAKE_CURRENT_BINARY_DIR}/hddm_s.hpp ${CMAKE_SOURCE_DIR}/include/HDDM
  COMMAND mv -v ${CMAKE_CURRENT_BINARY_DIR}/hddm_s++.cpp ${CMAKE_SOURCE_DIR}/src
  DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/event.xml
  )
add_custom_command(
  OUTPUT ${CMAKE_SOURCE_DIR}/include/hddm_r.hpp ${CMAKE_SOURCE_DIR}/src/hddm_r++.cpp
  COMMAND hddm-cpp ${CMAKE_CURRENT_SOURCE_DIR}/rest.xml
  COMMAND mv -v ${CMAKE_CURRENT_BINARY_DIR}/hddm_r.hpp ${CMAKE_SOURCE_DIR}/include/HDDM
  COMMAND mv -v ${CMAKE_CURRENT_BINARY_DIR}/hddm_r++.cpp ${CMAKE_SOURCE_DIR}/src
  DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/rest.xml
  )
message(STATUS "add depends on ${CMAKE_CURRENT_SOURCE_DIR}/rest.xml")
add_custom_target(
  hddm_derived_sources
  DEPENDS ${CMAKE_SOURCE_DIR}/include/hddm_s.hpp ${CMAKE_SOURCE_DIR}/include/hddm_r.hpp
  )
