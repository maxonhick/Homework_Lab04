cmake_minimum_required(VERSION 3.5)
project(solver_app LANGUAGES CXX)

add_executable(solver equation.cpp)
target_link_libraries(solver
    PRIVATE
        solver_lib
        formatter_ex
        formatter
        m
)
