cmake_minimum_required( VERSION 2.6 )


SET(CMAKE_SYSTEM_NAME Windows)

SET(CMAKE_C_COMPILER /usr/bin/i586-mingw32msvc-gcc)
SET(CMAKE_CXX_COMPILER /usr/bin/i586-mingw32msvc-g++)
SET(CMAKE_RC_COMPILER i586-mingw32msvc-windres)

SET(CMAKE_FIND_ROOT_PATH /usr/i586-mingw32msvc/)

set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM NEVER)
set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)

project (VirtExec)


set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

include_directories(include ${BOOST_INCLUDE_DIRS})
set(Boost_LIBRARY_DIRS "/usr/lib/")
set(Boost_INCLUDE_DIR "/usr/include/")

find_package( Boost 1.46.1)# COMPONENTS date_time REQUIRED)

link_directories ( ${Boost_LIBRARY_DIRS} )

include_directories ( ${Boost_INCLUDE_DIRS} )

ADD_SUBDIRECTORY (src)
