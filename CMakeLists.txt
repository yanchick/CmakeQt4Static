cmake_minimum_required(VERSION 2.8)

set(CMAKE_TOOLCHAIN_FILE "/opt/mxe/usr/i686-w64-mingw32.static/share/cmake/mxe-conf.cmake")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
#set(CMAKE_C_COMPILER_INIT g++)


find_package(Qt4  REQUIRED)

IF(Qt_FOUND)
    add_executable(qt4static main.cpp)

    INCLUDE_DIRECTORIES(${QT_INCLUDES})
    LINK_DIRECTORIES(${QT_LIBRARY_DIR})

    target_link_libraries(qt4static
		      Qt4::QtGui Qt4::QtCore
		      jpeg  png tiff
		     lzma z
		    
		    )
ENDIF(Qt_FOUND)