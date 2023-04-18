# Set minimum CMake version
cmake_minimum_required(VERSION 3.16.3)

# Declare project
project(sgp4 LANGUAGES CXX)

# Set compiler flags
set(CMAKE_CXX_FLAGS                "")
set(CMAKE_CXX_FLAGS_DEBUG          "-Wall")
set(CMAKE_CXX_FLAGS_RELEASE        "-O3 -march=native")
set(CMAKE_CXX_FLAGS_RELWITHDEBINFO "${CMAKE_Fortran_FLAGS_DEBUG} ${CMAKE_CXX_FLAGS_RELEASE}")
set(CMAKE_CXX_FLAGS_MINSIZEREL     "")

# Set output directories
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

# Add source directory
add_subdirectory(src)