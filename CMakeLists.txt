cmake_minimum_required(VERSION 3.18 FATAL_ERROR)

# the necessary check to avoid name collisions if the target is used in multiple places (e.g. in submodules)
if(TARGET lib_fetch_a)
    # return()
endif()

project(lib_fetch_a LANGUAGES CXX)

add_library(lib_fetch_a SHARED
    src/foo.cpp
)

set_target_properties(lib_fetch_a PROPERTIES
    CXX_STANDARD 17
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)

target_include_directories(lib_fetch_a PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)
