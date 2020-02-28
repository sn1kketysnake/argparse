cmake_minimum_required(VERSION 3.5.1)
project(argparse)

# If using msbuild do multi-process compile
if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "MSVC")
    ADD_COMPILE_OPTIONS(/MP)
endif()

set(SOURCES argparse.c)
add_library(${PROJECT_NAME} STATIC ${SOURCES})

# Create INCLUDE_DIRS variable that dependent projects can use
set(${PROJECT_NAME}_INCLUDE_DIRS ${PROJECT_SOURCE_DIR}
    CACHE INTERNAL "${PROJECT_NAME}: Include Directories" FORCE)
