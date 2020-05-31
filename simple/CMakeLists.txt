
cmake_minimum_required(VERSION 3.17)

project(simple
        VERSION 1.0
        LANGUAGES CXX
)

add_executable(hello_world)

target_sources(hello_world PRIVATE
        hello_world.cpp
)

target_compile_options(hello_world PRIVATE
        "-Wall"
        "-O3"
)

set_target_properties(hello_world PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin/$<CONFIG>"
)
