add_library(xpl SHARED
	xpl.c
)

if (WINDOWS)
	set(WIN_EXTRA_LIBS hulamemmgr)
endif(WINDOWS)

target_link_libraries(xpl
	${WIN_EXTRA_LIBS}
	${ALL_LIBS}
)

SET_TARGET_PROPERTIES(
	xpl
	PROPERTIES
	VERSION 1.0.0
	SOVERSION 1
	INSTALL_NAME_DIR "${LIB_DEST_DIR}"
)

install(TARGETS xpl LIBRARY DESTINATION ${LIB_DEST_DIR})
