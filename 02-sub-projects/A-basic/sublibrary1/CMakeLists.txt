# 设置当前文件的 PROJECT_NAME 为 sublibrary1，后续直接使用变量PROJECT_NAME即可
project (sublibrary1)

# 创建库文件，这里只需要添加源文件即可
add_library(${PROJECT_NAME} src/sublib1.cpp)

# 添加工程所需的头文件，如果是生成库，则对应的是库的头文件
target_include_directories( ${PROJECT_NAME}
    PUBLIC ${PROJECT_SOURCE_DIR}/include
)

# 给库文件定义别名
add_library(sub::lib1 ALIAS ${PROJECT_NAME})

# 生成实际库时会在工程名前自动加上lib前缀，但是在CMakeList中引用库模块是不需要lib前缀的。

# 关键词 生成库 别名 工程名变量 PROJECT_NAME add_library