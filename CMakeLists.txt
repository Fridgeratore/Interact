cmake_minimum_required(VERSION 3.15)
project(Interact LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(Interact SHARED
    dllmain.cpp
    Game.cpp
    minhook/src/buffer.c
    minhook/src/hook.c
    minhook/src/trampoline.c
    minhook/src/hde/hde32.c
    minhook/src/hde/hde64.c
)

target_include_directories(Interact PRIVATE
    ${CMAKE_SOURCE_DIR}
    minhook/include
    minhook/src
)

set_target_properties(Interact PROPERTIES
    OUTPUT_NAME "Interact"
    PREFIX ""
)
