cmake_minimum_required(VERSION 3.5)

project(hello_world LANGUAGES CXX)

add_executable(hello_world hello_world.cpp)
target_link_libraries(hello_world
    PRIVATE
        formatter_ex
        formatter
        solver_lib
        stdc++
)

target_include_directories(hello_world PRIVATE
    ${CMAKE_SOURCE_DIR}/formatter_ex_lib
    ${CMAKE_SOURCE_DIR}/formatter_lib
    ${CMAKE_SOURCE_DIR}/solver_lib
)
