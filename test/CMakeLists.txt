project(nxjson-test C)

enable_testing()

add_executable(nxjson-test ${CMAKE_CURRENT_LIST_DIR}/test.c)
target_link_libraries(nxjson-test nxjson)

add_custom_command(TARGET nxjson-test POST_BUILD COMMAND ${CMAKE_COMMAND} -E copy_directory ${CMAKE_CURRENT_LIST_DIR}/tests ${CMAKE_CURRENT_BINARY_DIR}/tests)

add_test(testNxJson nxjson-test)
