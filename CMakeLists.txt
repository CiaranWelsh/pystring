cmake_minimum_required(VERSION 3.14...3.18)
set(VERSION_MAJOR 1)
set(VERSION_MINOR 1)
set(VERSION_MICRO 3)
set(VERSION "${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_MICRO}")

project(pystring
        DESCRIPTION "A string like object with python interface"
        VERSION ${VERSION}
        )

add_library(pystring-static STATIC pystring.h pystring.cpp)
target_include_directories(pystring-static PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

if (${BUILD_SHARED_LIBS})
    add_library(pystring SHARED pystring.h pystring.cpp)
    target_include_directories(pystring PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
endif ()











