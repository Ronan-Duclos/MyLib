cmake_minimum_required(VERSION 3.14)

project(MyLib LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SRCS
	srcs/mylib.cpp
	)

add_library(MyLib SHARED ${SRCS})

target_include_directories(MyLib PRIVATE include)

target_compile_definitions(MyLib PRIVATE MyLib)

file(COPY include
    DESTINATION ${CMAKE_CURRENT_BINARY_DIR}
    FILES_MATCHING
	PATTERN *.h
	)

file(COPY include
    DESTINATION ${CMAKE_CURRENT_BINARY_DIR}
    FILES_MATCHING
	PATTERN *.hpp
	)