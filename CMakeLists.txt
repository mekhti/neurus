cmake_minimum_required(VERSION 3.16.0)

project(neurus VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(PkgConfig REQUIRED)
pkg_search_module(gstreamer REQUIRED IMPORTED_TARGET gstreamer-1.0>=1.4)

add_subdirectory(src)

add_executable(${PROJECT_NAME}-test3 test3.cpp)
target_link_libraries(${PROJECT_NAME}-test3
        PkgConfig::gstreamer
)