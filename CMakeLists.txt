project(cpp-throwaway)

# compiler settings
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -pedantic -W")

# cpp-throwaway
add_executable(cpp-throwaway
    src/main.cpp)
