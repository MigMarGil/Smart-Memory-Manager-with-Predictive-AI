cmake_minimum_required(VERSION 3.10)
project(SmartMemoryManager VERSION 1.0.0 LANGUAGES CXX)

# C++17 configuration
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Optimized compilation flags
if(MSVC)
    add_compile_options(/W4 /O2)
else()
    add_compile_options(-Wall -Wextra -Wpedantic -O2)
endif()

# Thread support
find_package(Threads REQUIRED)

# Main executable
add_executable(smart_memory_manager main.cpp)

# Link threads
target_link_libraries(smart_memory_manager PRIVATE Threads::Threads)

# Installation
install(TARGETS smart_memory_manager DESTINATION bin)

# Build information
message(STATUS "===========================================")
message(STATUS "Smart Memory Manager Configuration")
message(STATUS "===========================================")
message(STATUS "C++ Standard: ${CMAKE_CXX_STANDARD}")
message(STATUS "Build Type: ${CMAKE_BUILD_TYPE}")
message(STATUS "Compiler: ${CMAKE_CXX_COMPILER_ID}")
message(STATUS "===========================================")
