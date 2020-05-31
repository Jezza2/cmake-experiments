
cmake_minimum_required(VERSION 2.17)

project(shared_code
        LANGUAGES CXX
)

add_library(say_something OBJECT
        say_something.cpp
)

# Users of this target will need to include this directory
target_include_directories(say_something INTERFACE
        ${CMAKE_CURRENT_SOURCE_DIR}
)

target_compile_options(say_something PRIVATE
        "-Wall"
        "-O3"
)

export(TARGETS say_something
        NAMESPACE shared_code::
        FILE say_something.cmake
)
