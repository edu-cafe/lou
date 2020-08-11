#project ( "CMake Test Project" )
project ( "CMake Test Project" LANGUAGES C)
cmake_minimum_required(VERSION 3.10)
message(STATUS ${CMAKE_PROJECT_NAME} )

set ( SRCS test1.c test2.c test3.c )
add_executable (mytest ${SRCS})

set ( CMAKE_BUILD_TYPE release )
#set ( CMAKE_VERBOSE_MAKEFILE TRUE )
set ( CMAKE_VERBOSE_MAKEFILE false )  # build.make -> VERBOSE

install ( TARGETS mytest 
	  DESTINATION bin )   # /usr/local/bin
#	  RUNTIME DESTINATION bin )

#set ( CMAKE_INSTALL_PREFIX /usr/bin )
#install ( TARGETS mytest 
#	  DESTINATION soo )   # /usr/bin/soo
