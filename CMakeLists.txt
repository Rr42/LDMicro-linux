cmake_minimum_required (VERSION 2.6)
project (LDMicro)
set (LDMicro_VERSION_MAJOR 1)
set (LDMicro_VERSION_MINOR 0)

MESSAGE ( STATUS "Searching for X11..." )
FIND_PACKAGE ( X11 REQUIRED )
IF ( X11_FOUND )
      INCLUDE_DIRECTORIES ( ${X11_INCLUDE_DIR} )
      LINK_LIBRARIES ( ${X11_LIBRARIES} )
      MESSAGE ( STATUS " X11_INCLUDE_DIR: " ${X11_INCLUDE_DIR} )
      MESSAGE ( STATUS " X11_LIBRARIES: " ${X11_LIBRARIES} )
ENDIF ( X11_FOUND )

add_executable (LDMicro ldmicro.cpp miscutil.cpp draw_outputdev.cpp)
include_directories ("${PROJECT_SOURCE_DIR}/include")
install (TARGETS LDMicro DESTINATION bin)
