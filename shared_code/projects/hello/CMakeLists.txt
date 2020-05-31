
cmake_minimum_required(VERSION 3.17)

project(hello
        VERSION 1.0
        LANGUAGES CXX
)

add_executable(hello)

target_sources(hello PRIVATE
        hello.cpp
)

target_compile_options(hello PRIVATE
        "-Wall"
        "-O3"
)

set_target_properties(hello PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY "${PROJECT_SOURCE_DIR}/bin/$<CONFIG>"
)

# Add the shared_code::say_something object library and link it
add_subdirectory("../../shared_code/say_something" "shared_code/say_something")

target_link_libraries(hello PRIVATE
        say_something
)
