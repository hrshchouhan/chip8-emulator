cmake_minimum_required(VERSION 3.10)
project(chip8-emulator)

set(CMAKE_CXX_STANDARD 17)

find_package(SDL2 REQUIRED)

include_directories(${SDL2_INCLUDE_DIRS})

add_executable(chip8-emulator
    src/main.cpp
    src/chip8.cpp
    src/Platform.cpp
)

target_link_libraries(chip8-emulator ${SDL2_LIBRARIES})