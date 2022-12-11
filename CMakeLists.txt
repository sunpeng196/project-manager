cmake_minimum_required(VERSION 3.23)
project(HelloCmake)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

#add_executable(HelloCmake main.cpp)

add_library(hello_shared SHARED hello_shared.h hello_shared.cc)
target_compile_definitions(hello_shared PUBLIC HELLO_SHARED_IMPLEMENTATION)

add_library(hello_static STATIC hello_static.h hello_static.cc)


add_executable(hello hello.cc)
target_link_libraries(hello hello_shared hello_static)