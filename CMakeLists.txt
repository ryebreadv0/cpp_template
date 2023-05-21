set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

cmake_minimum_required(VERSION 3.22.0)

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Debug" CACHE STRING "Default build type is Debug" FORCE)
endif()

if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    add_compile_definitions(_DEBUG)
endif()

project(template)
add_executable(${PROJECT_NAME} main.cpp)

include(cmake/CPM.cmake)

CPMAddPackage("gh:fmtlib/fmt#10.0.0")

find_package(fmt CONFIG REQUIRED)
target_link_libraries(${PROJECT_NAME} 
    fmt::fmt
)
target_include_directories(${PROJECT_NAME} 
    PRIVATE ${fmt_SOURCE_DIRS}/include
)

