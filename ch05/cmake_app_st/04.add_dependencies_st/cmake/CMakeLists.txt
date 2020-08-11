##
## CMakeLists.txt : for CMake Application Programming
##
##		Kim Soo Hyun(@")
##
PROJECT ( "CMake - Sync. Dependent Files" LANGUAGES C )
CMAKE_MINIMUM_REQUIRED ( VERSION 3.10 )
SET ( CMAKE_BUILD_TYPE Release )
#SET ( CMAKE_BUILD_TYPE Debug )
#SET ( CMAKE_VERBOSE_MAKEFILE true )

SET (SRCS test1.c test2.c test3.c)
ADD_EXECUTABLE ( mytest ${SRCS} )
MESSAGE ( ${CMAKE_PROJECT_NAME} )

SET (HSRCS a.h b.h c.h)
ADD_CUSTOM_TARGET ( mybackup
        COMMENT "Backup App. Files"
        COMMAND -mkdir ${CMAKE_HOME_DIRECTORY}/backup
        COMMAND -cp mytest ${CMAKE_HOME_DIRECTORY}/backup
	DEPENDS mytest
)

