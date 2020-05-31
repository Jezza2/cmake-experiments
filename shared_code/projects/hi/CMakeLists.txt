
cmake_minimum_required(VERSION 3.17)

project(hi
        VERSION 1.0
        LANGUAGES CXX
)

add_executable(hi)

target_sources(hi PRIVATE
        hi.cpp
)

target_compile_options(hi PRIVATE
        "-Wall"
        "-O3"
)

set_target_properties(hi PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin/$<CONFIG>"
)
