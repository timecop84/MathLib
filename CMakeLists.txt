cmake_minimum_required(VERSION 3.16)

project(MathLib LANGUAGES CXX)

add_library(MathLib STATIC
    src/MathUtils.cpp
)

target_include_directories(MathLib
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

if(NOT DEFINED MATHLIB_GLM_INCLUDE_DIR AND EXISTS "${CMAKE_SOURCE_DIR}/external/glm")
    set(MATHLIB_GLM_INCLUDE_DIR "${CMAKE_SOURCE_DIR}/external/glm" CACHE PATH "" FORCE)
endif()
if(DEFINED MATHLIB_GLM_INCLUDE_DIR AND EXISTS "${MATHLIB_GLM_INCLUDE_DIR}")
    target_include_directories(MathLib PUBLIC ${MATHLIB_GLM_INCLUDE_DIR})
endif()

