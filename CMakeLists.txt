cmake_minimum_required(VERSION 3.14)

project(MyLib LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(MyLib SHARED
  MyLib_global.h
  mylib.cpp
  mylib.hpp
)

target_compile_definitions(MyLib PRIVATE MYLIB_LIBRARY)
