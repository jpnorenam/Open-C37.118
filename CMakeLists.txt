cmake_minimum_required(VERSION 3.6)

project(open-c37118
    LANGUAGES C CXX
)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_THREAD_PREFER_PTHREAD ON)
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(FindPkgConfig)


add_definitions(-D_POSIX_C_SOURCE=200809L -D_GNU_SOURCE)
add_compile_options(-fdiagnostics-color=auto)

find_package(PkgConfig REQUIRED)

set(ENV{PKG_CONFIG_PATH} "$ENV{PKG_CONFIG_PATH}:/usr/local/lib/pkgconfig:/usr/local/lib64/pkgconfig:/usr/local/share/pkgconfig:/usr/lib64/pkgconfig")

add_subdirectory(src)