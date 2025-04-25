cmake_minimum_required(VERSION 3.10)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
project(lab03 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Включаем необходимые политики
cmake_policy(SET CMP0002 NEW)
cmake_policy(SET CMP0079 NEW)

# Подключаем подпроекты в правильном порядке
add_subdirectory(formatter_lib)
add_subdirectory(formatter_ex_lib)
add_subdirectory(solver_lib)  # Добавляем solver_lib
add_subdirectory(hello_world_application)
add_subdirectory(solver_application)
find_package(Threads REQUIRED)
foreach(target_name formatter formatter_ex hello_world solver solver_lib)
  if(TARGET ${target_name})
    target_link_libraries(${target_name} PRIVATE Threads::Threads stdc++fs)
  endif()
endforeach()
