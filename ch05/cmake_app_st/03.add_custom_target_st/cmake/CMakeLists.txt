##
## CMakeLists.txt : for CMake Application Programming
##
##		Kim Soo Hyun(@")
##
PROJECT ( "CMake - Add Custom Target" LANGUAGES C )
CMAKE_MINIMUM_REQUIRED ( VERSION 3.10 )
SET ( CMAKE_BUILD_TYPE Release )
#SET ( CMAKE_BUILD_TYPE Debug )
SET ( CMAKE_VERBOSE_MAKEFILE true )

SET (SRCS test1.c test2.c test3.c)
ADD_EXECUTABLE ( mytest ${SRCS} )
MESSAGE ( ${CMAKE_PROJECT_NAME} )

SET (HSRCS a.h b.h c.h)
ADD_CUSTOM_TARGET ( backup
        COMMENT "Backup App. Files"
        COMMAND -mkdir ${CMAKE_HOME_DIRECTORY}/backup
        COMMAND -cp ${CMAKE_HOME_DIRECTORY}/*.c  ${CMAKE_HOME_DIRECTORY}/backup
        COMMAND -cp ${CMAKE_HOME_DIRECTORY}/*.h  ${CMAKE_HOME_DIRECTORY}/backup
        COMMAND -cp mytest ${CMAKE_HOME_DIRECTORY}/backup
)

