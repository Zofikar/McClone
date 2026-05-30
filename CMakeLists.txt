cmake_minimum_required(VERSION 3.28)
project(McClone)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_C_STANDARD 20)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

option(WARNINGS_AS_ERRORS "Treat warnings as errors" ON)

add_library(ProjectWarnings INTERFACE)
target_compile_options(ProjectWarnings INTERFACE
        -Wall
        -Wextra
        -Wpedantic
        -Wshadow
        -Wconversion
        -Wsign-conversion
        -Wnull-dereference
        -Wold-style-cast
        -Woverloaded-virtual
        -Wformat=2
        -Wduplicated-cond
        -Wduplicated-branches
        -Wlogical-op
)
if (CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    target_compile_options(ProjectWarnings INTERFACE
            -Wno-unknown-warning-option
    )
endif ()
if (WARNINGS_AS_ERRORS)
    target_compile_options(ProjectWarnings INTERFACE -Werror)
endif ()

add_subdirectory(Apps)
add_subdirectory(Libs)