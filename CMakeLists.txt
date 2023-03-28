cmake_minimum_required(VERSION 3.10)

project(bundle_adjustment)
set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_FLAGS "-O0 -std=c++14")

find_package(Eigen3 REQUIRED)
find_package(Sophus REQUIRED)
find_package(Ceres REQUIRED)
include_directories(${PROJECT_SOURCE_DIR}/include)
include_directories(${PROJECT_SOURCE_DIR} ${EIGEN3_INCLUDE_DIR} ${Ceres_INCLUDE_DIR})
include_directories("/usr/include/eigen3")

add_library(bal_common common/common.cpp)
add_library(backend_lib
src/edge.cc
src/problem.cc
src/vertex.cc
src/vertex_pose.cc)

add_subdirectory(test)


