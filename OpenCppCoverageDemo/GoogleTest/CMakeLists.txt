#
# This file was generated by VS2CMake tool (internal-only)!
# You probably need to modify the generated files to meet your requirements.
#

cmake_minimum_required(VERSION 2.8)

IF(EXISTS "${PROJECT_SOURCE_DIR}/${PROJECT_NAME}.common.cmake")
    INCLUDE("${PROJECT_SOURCE_DIR}/${PROJECT_NAME}.common.cmake")
ENDIF()

INCLUDE("GoogleTest.cmake")

SOURCE_GROUP("Source Files" FILES 
            "gtest_main.cc" 
            "gtest-all.cc" 
            )

INCLUDE_DIRECTORIES("${CMAKE_CURRENT_SOURCE_DIR}/../imports/googletest/googletest/include"
					"${CMAKE_CURRENT_SOURCE_DIR}/../imports/googletest/googletest"
        )
        
#IF(CMAKE_BUILD_TYPE STREQUAL "Debug")
#    SET(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin/Debug)
#ELSEIF(CMAKE_BUILD_TYPE STREQUAL "Release")
#    SET(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin/Release)
#ELSE()
    SET(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
#ENDIF()



ADD_LIBRARY(${MY_TARGET_NAME} STATIC
            ${GoogleTest_SRC})

IF(BINARY_BITS EQUAL 64)
    IF(CMAKE_BUILD_TYPE STREQUAL "Debug")
        INSTALL(TARGETS ${MY_TARGET_NAME} ARCHIVE DESTINATION ${PROJECT_SOURCE_DIR}/../build/x64/debug)
    ELSE()
        INSTALL(TARGETS ${MY_TARGET_NAME} ARCHIVE DESTINATION ${PROJECT_SOURCE_DIR}/../build/x64/release)
    ENDIF()
ENDIF()
IF(BINARY_BITS EQUAL 32)
    IF(CMAKE_BUILD_TYPE STREQUAL "Debug")
        INSTALL(TARGETS ${MY_TARGET_NAME} ARCHIVE DESTINATION ${PROJECT_SOURCE_DIR}/../build/x86/debug)
    ELSE()
        INSTALL(TARGETS ${MY_TARGET_NAME} ARCHIVE DESTINATION ${PROJECT_SOURCE_DIR}/../build/x86/release)
    ENDIF()
ENDIF()
