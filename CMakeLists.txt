cmake_minimum_required(VERSION 3.16)

project(cpp_inference_lab LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_Library(
    inference_core
    src/matrix.cpp
)

target_include_directories(
    inference_core
    PUBLIC
        ${PROJECT_SOURCE_DIR}/include
)

add_executable(
    test_matmul
    tests/test_matmul.cpp
)

target_link_libraries(
    test_matmul
    PRIVATE
        inference_core
)