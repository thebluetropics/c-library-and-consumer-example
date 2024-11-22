cmake_minimum_required(VERSION 3.10)

project(example C)

set(SOURCES src/lib.c)

add_library(example STATIC ${SOURCES})

set_target_properties(example PROPERTIES ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/dist)

target_include_directories(example PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

install(TARGETS example ARCHIVE DESTINATION lib)
install(FILES ${CMAKE_CURRENT_SOURCE_DIR}/include/lib.h DESTINATION include/example)
