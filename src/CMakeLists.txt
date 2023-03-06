# The Flutter tooling requires that developers have CMake 3.10 or later
# installed. You should not increase this version, as doing so will cause
# the plugin to fail to compile for some customers of the plugin.
cmake_minimum_required(VERSION 3.10)

project(ffinative_library VERSION 0.0.1 LANGUAGES C)

add_library(ffinative SHARED
  "ffinative.c"
)

set_target_properties(ffinative PROPERTIES
  PUBLIC_HEADER ffinative.h
  OUTPUT_NAME "ffinative"
)

target_compile_definitions(ffinative PUBLIC DART_SHARED_LIB)
