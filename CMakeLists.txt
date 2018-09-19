cmake_minimum_required (VERSION 2.8)

project (json)
include(gtest.cmake)
include_directories(SYSTEM
    ./
)

# if(CMAKE_COMPILER_IS_GNUCXX)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17 -fsanitize=address -O1 -Wall -Wextra -Wno-unused-command-line-argument -Wshadow -Wnon-virtual-dtor -pedantic")
# endif(CMAKE_COMPILER_IS_GNUCXX)
add_library (json STATIC json.cpp json.hpp)
add_executable(main main.cpp)
# enum your files
target_link_libraries(main json)
