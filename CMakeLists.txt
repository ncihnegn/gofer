cmake_minimum_required(VERSION 3.9)

project(gofer VERSION 2.30 LANGUAGES C)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

include_directories(${PROJECT_SOURCE_DIR}/src)

if(APPLE)
  include_directories(/usr/include/malloc)
endif()

add_executable(gofer src/gofer.c src/builtin.c src/machine.c src/output.c src/storage.c src/input.c src/static.c src/type.c src/compiler.c)
add_executable(gofc src/gofc.c src/cbuiltin.c src/cmachine.c src/storage.c src/input.c src/static.c src/type.c src/compiler.c)
