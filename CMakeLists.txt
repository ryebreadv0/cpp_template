set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

cmake_minimum_required(VERSION 3.22.0)

project(template)

add_executable(${PROJECT_NAME} main.cpp)

include(cmake/CPM.cmake)

CPMAddPackage("gh:fmtlib/fmt#10.0.0")

target_link_libraries(${PROJECT_NAME} fmt)

