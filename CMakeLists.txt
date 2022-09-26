cmake_minimum_required(VERSION 3.14)

project(MyLib LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SRCS
	srcs/mylib.cpp
	)

add_library(MyLib SHARED ${SRCS})

target_include_directories(MyLib PRIVATE headers)

target_compile_definitions(MyLib PRIVATE MyLib::MyLib)
