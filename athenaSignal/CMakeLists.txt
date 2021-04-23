cmake_minimum_required(VERSION 2.8.12)
project(athenasignal)


message("PROJECT_SOURCE_DIR=${PROJECT_SOURCE_DIR}\n"
        "PROJECT_BINARY_DIR=${PROJECT_BINARY_DIR}")
message("CMAKE_CURRENT_BINARY_DIR = ${CMAKE_CURRENT_BINARY_DIR}\n")

set(CMAKE_C_FLAGS "-Wall -fPIC -g -O0")
set(CMAKE_C_FLAGS_RELEASE "-g -O0")
set(CMAKE_C_FLAGS_DEBUG "-g")
set(CMAKE_CXX_FLAGS "-Wall -fPIC -g -O0")
set(CMAKE_CXX_FLAGS_RELEASE "-g -O0")
set(CMAKE_CXX_FLAGS_DEBUG "-g")


file(GLOB_RECURSE SRC_DEMO_BIN "${CMAKE_CURRENT_SOURCE_DIR}/test/*.c")

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_SOURCE_DIR})
add_subdirectory(kernels)

 # test lib
  add_executable(
    mytestbin
    ${SRC_DEMO_BIN}
  )

#target_link_libraries(mytestbin PRIVATE m)
target_link_libraries(mytestbin PRIVATE bflib)


