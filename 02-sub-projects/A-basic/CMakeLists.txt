cmake_minimum_required (VERSION 3.5)

project(subprojects)

# 添加多个子目录并构建、编译这些子目录。
add_subdirectory(sublibrary1)
add_subdirectory(sublibrary2)
add_subdirectory(subbinary)
