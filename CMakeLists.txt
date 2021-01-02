cmake_minimum_required(VERSION 2.8.12 FATAL_ERROR)

project(opencad_demo)

set(src_root_path ${CMAKE_CURRENT_SOURCE_DIR})
message("get src path : ${src_root_path}")

file(GLOB libopencad_dwg_source "${src_root_path}/libopencad/dwg/*.cpp")
file(GLOB libopencad_source "${src_root_path}/libopencad/*.cpp")

set(source_files ${libopencad_dwg_source} ${libopencad_source} ${src_root_path}/cadinfo.cpp)

include_directories(${src_root_path}/libopencad/dwg/)
include_directories(${src_root_path}/libopencad/)
add_executable(cadinfo ${source_files})
