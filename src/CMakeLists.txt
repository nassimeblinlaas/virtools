MESSAGE(STATUS ${PROJECT_NAME})
SET(LIBRARY_NAME ${PROJECT_NAME})
ADD_LIBRARY(${LIBRARY_NAME}
  SHARED
	virtools.cc
  )


# Create and install executable running the corba server
ADD_EXECUTABLE (virtoolsexe
	  main.cc
		)

TARGET_LINK_LIBRARIES(virtoolsexe ${LIBRARY_NAME})
#TARGET_LINK_LIBRARIES(virtoolsexe virtools-corba)

INSTALL(TARGETS ${LIBRARY_NAME} DESTINATION lib)

INSTALL(TARGETS virtoolsexe DESTINATION ${CMAKE_INSTALL_BINDIR})
