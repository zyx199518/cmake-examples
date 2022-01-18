# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.5)

# Set a default build type if none was specified
if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
  message("Setting build type to 'RelWithDebInfo' as none was specified.")

  # 将下列信息存入CACHE域中
  # 设置CMAKE_BUILD_TYPE的值为RelWithDebInfo
  # 设置CMAKE_BUILD_TYPE的类型为STRING
  # 设置CMAKE_BUILD_TYPE的变量描述为 "Choose the type of build."
  # FORCE强制覆盖CACHE中原有值
  set(CMAKE_BUILD_TYPE RelWithDebInfo CACHE STRING "Choose the type of build." FORCE)

  # Set the possible values of build type for cmake-gui
  set_property(CACHE CMAKE_BUILD_TYPE PROPERTY STRINGS "Debug" "Release" "MinSizeRel" "RelWithDebInfo")

  # set命令设置的变量能从父目录传递到子目录，同级目录之间无法传递
  # set_property 设置的变量一般使用GLOBAL 可以在全局CMakeList中传递
endif()

# Set the project name
project (build_type)

# Add an executable
add_executable(cmake_examples_build_type main.cpp)
