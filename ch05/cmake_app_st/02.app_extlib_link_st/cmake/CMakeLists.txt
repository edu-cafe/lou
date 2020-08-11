##
## CMakeLists.txt : for CMake Application Programming
##
##		Kim Soo Hyun(@")
##
PROJECT ( "CMake - Using External Library" LANGUAGES C )
CMAKE_MINIMUM_REQUIRED ( VERSION 3.10 )
SET ( CMAKE_BUILD_TYPE Debug )
SET ( CMAKE_VERBOSE_MAKEFILE true )
MESSAGE ( ${CMAKE_PROJECT_NAME} )

SET ( ELIB_PATH $ENV{HOME}/extlibs )
INCLUDE_DIRECTORIES ( ${ELIB_PATH}/include )

LINK_DIRECTORIES ( ${ELIB_PATH}/lib )
LINK_LIBRARIES ( mytest )

SET ( APP_PATH "./appSrc/" )
SET ( APP_SRCS ${APP_PATH}app.c )
ADD_EXECUTABLE ( app_static ${APP_SRCS} )
ADD_EXECUTABLE ( app_shared ${APP_SRCS} )

TARGET_LINK_LIBRARIES ( app_static mytest -static )

