cmake_minimum_required(VERSION 3.1)
project(game.libretro.mame2016)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(MAME2016_LIB NAMES mame2016_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(MAME2016_CUSTOM_BINARY ${MAME2016_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} MAME2016 "")

include(CPack)
