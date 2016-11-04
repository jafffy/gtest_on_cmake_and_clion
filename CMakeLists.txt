cmake_minimum_required(VERSION 3.6)
project(testingWithGoogleTest)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14")

set(SOURCE_FILES src/main.cpp)
add_executable(testingWithGoogleTest ${SOURCE_FILES})

enable_testing()

set(gtest_SOURCE_DIR deps/googletest/googletest)
include_directories(${gtest_SOURCE_DIR}/include)
link_directories(${gtest_SOURCE_DIR})

set(TEST_SOURCE_FILES tests/unittest.cpp)
add_executable(unitTest ${TEST_SOURCE_FILES})
target_link_libraries(unitTest gtest gtest_main)

