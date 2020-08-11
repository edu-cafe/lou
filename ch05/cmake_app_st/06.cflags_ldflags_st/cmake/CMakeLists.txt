##
## CMakeLists.txt : for CMake Application Programming
##
##		Kim Soo Hyun(@")
##
PROJECT ( "CMake - Compile and Link Option Setting" LANGUAGES C )
CMAKE_MINIMUM_REQUIRED ( VERSION 3.10 )
#SET ( CMAKE_BUILD_TYPE Debug )
SET ( CMAKE_BUILD_TYPE Release )
SET ( CMAKE_VERBOSE_MAKEFILE true )
MESSAGE ( ${CMAKE_PROJECT_NAME} )

ADD_COMPILE_OPTIONS ( -Wall )
SET ( CMAKE_C_FLAGS_RELEASE -O2 )
SET ( CMAKE_C_FLAGS_DEBUG "-g -O0" )
SET ( CMAKE_EXE_LINKER_FLAGS_DEBUG -static )

SET ( ELIB_PATH $ENV{HOME}/extlibs )
INCLUDE_DIRECTORIES ( ${ELIB_PATH}/include )

LINK_DIRECTORIES ( ${ELIB_PATH}/lib )
#LINK_LIBRARIES ( mytest )

SET ( APP_PATH "./appSrc/" )
SET ( APP_SRCS1 ${APP_PATH}app.c )
ADD_EXECUTABLE ( app ${APP_SRCS1} )

SET ( APP_SRCS2 ${APP_PATH}threadTest.c )
ADD_EXECUTABLE ( threadTest ${APP_SRCS2} )

TARGET_LINK_LIBRARIES ( app mytest )
TARGET_LINK_LIBRARIES ( threadTest pthread )
