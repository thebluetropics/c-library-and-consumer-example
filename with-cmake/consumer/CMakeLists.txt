cmake_minimum_required(VERSION 3.10)

project(example C)

find_library(LIBEXAMPLE NAMES example PATHS /usr/local/lib)

set(SOURCES src/main.c)

add_executable(example ${SOURCES})

set_target_properties(example PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/dist)

include_directories(/usr/local/include)

target_link_libraries(example PRIVATE ${LIBEXAMPLE})
