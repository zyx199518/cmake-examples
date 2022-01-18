解决：

cmake替换为下面的命令 添加参数选项

```
cmake -DCMAKE_SH="CMAKE_SH-NOTFOUND"
```




```
cmake -G "MinGW Makefiles" .. -DCMAKE_SH="CMAKE_SH-NOTFOUND"
```
