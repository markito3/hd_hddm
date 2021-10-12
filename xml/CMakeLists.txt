add_custom_command(
  OUTPUT ${CMAKE_SOURCE_DIR}/include/hddm_s.hpp
  COMMAND hddm-cpp ${CMAKE_CURRENT_SOURCE_DIR}/event.xml
  COMMAND mv -v ${CMAKE_CURRENT_BINARY_DIR}/hddm_s.hpp ${CMAKE_SOURCE_DIR}/include/HDDM
  )
add_custom_command(
  OUTPUT ${CMAKE_SOURCE_DIR}/include/hddm_r.hpp
  COMMAND hddm-cpp ${CMAKE_CURRENT_SOURCE_DIR}/rest.xml
  COMMAND mv -v ${CMAKE_CURRENT_BINARY_DIR}/hddm_r.hpp ${CMAKE_SOURCE_DIR}/include/HDDM
  )
add_custom_target(
  hddm_hpp
  DEPENDS ${CMAKE_SOURCE_DIR}/include/hddm_s.hpp ${CMAKE_SOURCE_DIR}/include/hddm_r.hpp
  )
