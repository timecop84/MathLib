cmake_minimum_required(VERSION 3.16)

project(cloth_math LANGUAGES CXX)

add_library(cloth_math STATIC
    src/MathUtils.cpp
)

target_include_directories(cloth_math
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

