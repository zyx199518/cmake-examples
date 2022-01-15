问题 ：

提示 "The C compiler identification is unknown -- The CXX compiler identification is unknownhe C compiler identification is unknown -- The CXX compiler identification is unknown"


解决：

1.提前配置好环境变量(C:\MinGW\bin)

2.复制C:\MinGW\bin下面的mingw32-make.exe为make.exe（这样编译makefile的时候只需要输入make即可）

3.在CMake主目录执行

```
cmake -G "MinGW Makefiles" .
```

使用的是VS编译器，则执行

```
cmake -G "NMake Makefiles" .
```
