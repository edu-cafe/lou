##
## CMakeLists.txt : for CMake Application Programming
##
##		Kim Soo Hyun(@")
##
PROJECT ( "CMake App_1" LANGUAGES C )
CMAKE_MINIMUM_REQUIRED ( VERSION 3.10 )
SET ( CMAKE_BUILD_TYPE Debug )
SET ( CMAKE_VERBOSE_MAKEFILE true )
MESSAGE ( ${CMAKE_PROJECT_NAME} )

SET ( INC_PATH "./include/" )
INCLUDE_DIRECTORIES ( ${INC_PATH} )

SET ( LIB_PATH "./libs/" )
SET ( LIB_SRCS ${LIB_PATH}min.c ${LIB_PATH}max.c )
#ADD_LIBRARY ( mytest ${LIB_SRCS} )
ADD_LIBRARY ( mytest SHARED ${LIB_SRCS} )
LINK_LIBRARIES ( mytest )

SET ( APP_PATH "./appSrc/" )
SET ( APP_SRCS ${APP_PATH}app.c )
ADD_EXECUTABLE ( app ${APP_SRCS} )
#TARGET_LINK_LIBRARIES ( app mytest )
