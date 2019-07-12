cmake_minimum_required(VERSION 3.9)

project(cpp-throwaway)

# compiler settings
# compiler is set with CC/CXX environment variables
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -pedantic -W")

# External dependencies
# include/link directories get exported from this dependencies.cmake file
# for use in the rest of this CMakeLists.txt script
include(dependencies.cmake)

# Add libraries to the compilation/linking search paths
include_directories(
    SYSTEM
    ${CATCH_INCLUDE_DIR}
)

link_directories(
    ${ROOT_DIR}/build
)

# common source files - things that get tested basically
set(TESTED_SOURCES
    src/utils/math.cpp)

# main
add_executable(cpp-throwaway
    src/main.cpp
    ${TESTED_SOURCES}
)

# tests
add_executable(tests
    src/tests.cpp
    ${TESTED_SOURCES}
    src/utils/math_tests.cpp
)