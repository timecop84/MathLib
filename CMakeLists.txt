cmake_minimum_required(VERSION 3.16)

project(MathLib LANGUAGES CXX)

add_library(MathLib STATIC
    src/MathUtils.cpp
)

target_include_directories(MathLib
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

