add_custom_command(OUTPUT ${CMAKE_CURRENT_BUILD_DIR}/xml/hddm_s.hpp
  COMMAND hddm-cpp ${CMAKE_CURRENT_SOURCE_DIR}/event.xml
  )
add_custom_target(hddm_s
  DEPENDS ${CMAKE_CURRENT_BUILD_DIR}/xml/hddm_s.hpp
  )
