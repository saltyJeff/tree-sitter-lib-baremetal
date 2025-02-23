cmake_minimum_required(VERSION 3.10)
project(tree-sitter-lib-baremetal)

set(CMAKE_CXX_STANDARD 11)

add_library(tree-sitter-lib-baremetal STATIC tree-sitter-javascript/parser.c
    inc/tree_sitter/parser.h)
target_include_directories(tree-sitter-lib-baremetal PUBLIC "inc")
target_compile_options(tree-sitter-lib-baremetal PRIVATE "-nostdlib")

add_executable(test-tree-sitter-lib-baremetal test.cpp)
target_link_libraries(test-tree-sitter-lib-baremetal PUBLIC tree-sitter-lib-baremetal)