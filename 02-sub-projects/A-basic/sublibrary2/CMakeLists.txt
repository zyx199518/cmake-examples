# 仅含头文件的库编译，实际上不会生成静态库或者动态库，而是添加头文件引用给需要的模块
project (sublibrary2)

add_library(${PROJECT_NAME} INTERFACE)
add_library(sub::lib2 ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME}
    INTERFACE
        ${PROJECT_SOURCE_DIR}/include
)
