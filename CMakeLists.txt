cmake_minimum_required(VERSION 3.3)
project(tinyaes_c)

######################################################

set (COMMON_HEADER_FILES
    aes.h)

set (SOURCE_FILES
    aes.c
    ${COMMON_HEADER_FILES})

set (TEST_SOURCE_FILES
    test.c
    ${COMMON_HEADER_FILES})

######################################################

add_library(tinyaes SHARED ${SOURCE_FILES})
link_libraries(tinyaes)
add_executable(aes_test ${TEST_SOURCE_FILES})
