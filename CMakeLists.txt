cmake_minimum_required(VERSION 3.3)
project(tinyaes)

######################################################

set (AES_LIBRARY_HEADER_FILES
    aes.h)

set (COMMON_HEADER_FILES
    ${AES_LIBRARY_HEADER_FILES})

set (SOURCE_FILES
    aes.c
    ${COMMON_HEADER_FILES})

set (TEST_SOURCE_FILES
    test.c
    ${COMMON_HEADER_FILES})

######################################################

add_library(${PROJECT_NAME} SHARED ${SOURCE_FILES})
link_libraries(${PROJECT_NAME})
add_executable(aes_test ${TEST_SOURCE_FILES})

add_custom_target(buildtest COMMAND ./aes_test)

######################################################

install(TARGETS ${PROJECT_NAME} DESTINATION lib)
install(FILES ${AES_LIBRARY_HEADER_FILES} DESTINATION include/${PROJECT_NAME})