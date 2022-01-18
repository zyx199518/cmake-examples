cmake_minimum_required (VERSION 3.5)
project(subprojects)
# CMAKE_BINARY_DIR是cmake命令的执行目录, 在实行目录下会自动生成lib bin文件夹
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib) # 设置静态库文件目录 
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib) # 动态库文件目录
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin) # 可执行文件目录

# 添加多个子目录(不是子CMakeList.txt的模块名)并构建、编译这些子目录。
add_subdirectory(sublibrary1)
add_subdirectory(sublibrary2)
add_subdirectory(subbinary)