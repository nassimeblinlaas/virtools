CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

SET(CXX_DISABLE_WERROR TRUE)
INCLUDE(cmake/base.cmake)

SET(PROJECT_NAME virtools)
SET(PROJECT_DESCRIPTION
	"virtools path planning")
SET(PROJECT_URL "")

SET(${PROJECT_NAME}_HEADERS
  include/gepetto/virtools/virtools.hh
  include/gepetto/virtools/macros.h
)

# Activate hpp-util logging if requested
SET (HPP_DEBUG FALSE CACHE BOOL "trigger hpp-util debug output")
IF (HPP_DEBUG)
  SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -DHPP_DEBUG")
ENDIF()

SETUP_PROJECT()
ADD_REQUIRED_DEPENDENCY("hpp-core")
ADD_REQUIRED_DEPENDENCY("hpp-corbaserver >= 3")
ADD_REQUIRED_DEPENDENCY("hpp-model")



PKG_CONFIG_APPEND_LIBS(${PROJECT_NAME})
ADD_SUBDIRECTORY (src)
#ADD_SUBDIRECTORY (tests)

SETUP_PROJECT_FINALIZE()
