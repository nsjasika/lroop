# Project Information
set(PROJECT_NAME "Starter Kit - C++ Scripts")
set(SCRIPTS_DIR "Scripts")
set(LIBRARY_DIR "Library")

# Cmake Information
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_MINIMUM_REQUIRED_VERSION 3.27)


# Scripts Runner Codes
cmake_minimum_required(VERSION ${CMAKE_MINIMUM_REQUIRED_VERSION})
project(${PROJECT_NAME})

set(LIBRARY_PATH "${CMAKE_SOURCE_DIR}/${LIBRARY_DIR}")
set(SCRIPTS_PATH "${CMAKE_SOURCE_DIR}/${SCRIPTS_DIR}")

file(GLOB SCRIPT_FILES "${SCRIPTS_PATH}/*.cpp")
foreach (script_file ${SCRIPT_FILES})
    get_filename_component(script_name ${script_file} NAME_WE)
    add_executable(${script_name} ${script_file})
    target_include_directories(${script_name} PRIVATE ${LIBRARY_DIR})
endforeach ()
