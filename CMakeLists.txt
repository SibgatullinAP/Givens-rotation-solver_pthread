cmake_minimum_required(VERSION 3.5)

project(QR_solver_parallel LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set (CMAKE_CXX_FLAGS "-O3 -lm -mfpmath=sse -fsignaling-nans -pthread")

add_executable(QR_solver_parallel main.cpp solver.cpp matrix.cpp thread_functions.cpp)
