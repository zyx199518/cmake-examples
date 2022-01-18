# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.5)

# Set the project name
project (hello_headers)

# Create a sources variable with a link to all cpp files to compile
set(SOURCES
    src/Hello.cpp
    src/main.cpp
)

# 生成项目可执行文件，可以添加头文件(不是路径)和源文件
add_executable(hello_headers ${SOURCES})

# Set the directories that should be included in the build command for this target
# when running g++ these will be included as -I/directory/path/
target_include_directories(hello_headers
    PRIVATE 
        ${PROJECT_SOURCE_DIR}/include
)

# CMake-Public-Private-Interface
# https://leimao.github.io/blog/CMake-Public-Private-Interface/
# 当前模块自己的头文件用PRIVATE，引用其他模块的头文件使用INTERFACE, 图省事就直接PUBLIC


