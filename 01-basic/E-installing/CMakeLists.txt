cmake_minimum_required(VERSION 3.5)

project(cmake_examples_install)

############################################################
# Create a library
############################################################

#Generate the shared library from the library sources
add_library(cmake_examples_inst SHARED
    src/Hello.cpp
)

target_include_directories(cmake_examples_inst
    PUBLIC 
        ${PROJECT_SOURCE_DIR}/include
)

############################################################
# Create an executable
############################################################

# Add an executable with the above sources
add_executable(cmake_examples_inst_bin
    src/main.cpp
)

# link the new hello_library target with the hello_binary target
target_link_libraries( cmake_examples_inst_bin
    PRIVATE 
        cmake_examples_inst
)

############################################################
# Install
############################################################

# 设置install输出路径
set(CMAKE_INSTALL_PREFIX "D:/cmake_output")

# Binaries
install (TARGETS cmake_examples_inst_bin
    DESTINATION bin)

# Library
install (TARGETS cmake_examples_inst
    LIBRARY DESTINATION lib)

# Header files(将目录下的所有头文件文件夹全部拷贝)
install(DIRECTORY ${PROJECT_SOURCE_DIR}/include/ 
    DESTINATION include)

# Config
install (FILES cmake-examples.conf
    DESTINATION etc)
