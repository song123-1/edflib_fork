cmake_minimum_required(VERSION 3.29)

project(edflib)

set(CMAKE_C_STANDARD 17)
set(CMAKE_C_STANDARD_REQUIRED ON)

add_library(edf SHARED edflib.c edflib.h)

#target_include_directories(edf PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_definitions(edf PRIVATE EDFLIB_SO_DLL EDFLIB_BUILD)


add_executable(testedf test_edflib.c)
target_link_libraries(testedf PRIVATE edf)