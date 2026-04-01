# CMakeLists.txt for cpp26-examples

cmake_minimum_required(VERSION 3.14)
project(cpp26_examples LANGUAGES CXX)

# Set the C++ standard to C++26
set(CMAKE_CXX_STANDARD 26)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Compiler flags for different compilers
if(CMAKE_CXX_COMPILER_ID MATCHES "GNU")
    # GCC 14+
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++26")
elseif(CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    # Clang 17+
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++26")
elseif(MSVC)
    # MSVC 17.8+
    add_compile_options(/std:c++26)
endif()

# Add subdirectories for each feature category
add_subdirectory(features/algorithm)
add_subdirectory(features/concurrency)
add_subdirectory(features/containers)
add_subdirectory(features/formatting)
add_subdirectory(features/utility)