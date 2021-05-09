set(C37118_SRC
    c37118.cpp
    c37118command.cpp
    c37118configuration.cpp
    c37118data.cpp
    c37118header.cpp
    c37118pmustation.cpp
)

list(APPEND C37118_INCLUDE_DIRS
    ${PROJECT_SOURCE_DIR}/include
)

set(C37118_LIBRARIES
    stdc++
)

if(CMAKE_CXX_COMPILER_ID STREQUAL GNU)
	list(APPEND C37118_LIBRARIES "-lstdc++fs")
endif()

add_library(open-c37118 SHARED ${C37118_SRC})
target_include_directories(open-c37118 PUBLIC ${C37118_INCLUDE_DIRS})

install(
    DIRECTORY ${PROJECT_SOURCE_DIR}/include/open-c37118/
    DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/open-c37118
    COMPONENT devel
    FILES_MATCHING
        PATTERN "*.h"
        PATTERN "*.hpp"
)