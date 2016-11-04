cmake_minimum_required(VERSION 3.6)
project(testingWithGoogleTest)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14")

set(SOURCE_FILES src/main.cpp)
add_executable(testingWithGoogleTest ${SOURCE_FILES})

include_directories(deps/googletest/googletest/include)
link_directories(deps/googletest/googletest)
link_libraries(gtest gtest_main)
set(TEST_SOURCE_FILES tests/unittest.cpp)
add_executable(unitTest ${TEST_SOURCE_FILES})
target_link_libraries(unitTest)

add_test(NAME PRIMARY_UNIT_TEST COMMAND unitTest)
