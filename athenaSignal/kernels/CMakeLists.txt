cmake_minimum_required(VERSION 2.8.12)
project(athenasignallib)


message("PROJECT_SOURCE_DIR=${PROJECT_SOURCE_DIR}\n"
        "PROJECT_BINARY_DIR=${PROJECT_BINARY_DIR}")
message("CMAKE_CURRENT_BINARY_DIR = ${CMAKE_CURRENT_BINARY_DIR}\n")


file(GLOB_RECURSE SRC_DEMO_LIB "${CMAKE_CURRENT_SOURCE_DIR}/*.c")

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_SOURCE_DIR})

 # test lib
  add_library(
    bflib
    ${SRC_DEMO_LIB}
  )

target_link_libraries(bflib PRIVATE m)


