cmake_minimum_required(VERSION 2.8)
project(nxjson C)

option(BUILD_TEST "Builds the test program." ON)

add_library(nxjson STATIC
    ${CMAKE_CURRENT_LIST_DIR}/nxjson.h
    ${CMAKE_CURRENT_LIST_DIR}/nxjson.c
)

if(BUILD_TEST)
    add_subdirectory(test)
endif()

install(TARGETS nxjson ARCHIVE DESTINATION lib)
install(FILES ${CMAKE_CURRENT_LIST_DIR}/nxjson.h DESTINATION include)
