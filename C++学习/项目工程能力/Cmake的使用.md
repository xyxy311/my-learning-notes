从源文件到程序：预处理 -> 编译 -> 汇编 -> 链接

# 基本语法


```CMakeLists.txt
# 单行注释

#[[这是一个块注释
块注释
块注释]]
```

```CMakeLists.txt
cmake_minimum_required(VERSION 3.0)  # 要求的最低版本（非必须）

project(<PROJECT-NAME>)  # 定义工程的名字，也可以定义版本等信息

add_executable(可执行程序名字 源文件名 源文件名 ......)  # 源文件名之间也可以用;分隔 
```

# 设置变量

```CMakeLists.txt
SET(VAL [VALUE])  # 设置字符串类型的变量
# 使用变量：${VAL}
```

例子：

```CMakeLists.txt
SET(SRC_LIST main.cpp add.cpp sub.cpp)
add_executable(calc ${SRC_LIST})
```

## 应用

-----------------1-----------------

**可以通过设置宏来指定C++版本**

```CMakeLists.txt
SET(CMAKE_CXX_STANDARD 11)   # 标准为C++11
```

也可以在执行cmake命令时指定版本

`cmake .. -DCMAKE_CXX_STANDARD=11`  -D表示设置宏


-----------------2-----------------

**可以设置输出路径**

```CMakeLists.txt
set(HOME /home/Documents/project1/)   # 储存一个绝对路径
set(EXECUTABLE_OUTPUT_PATH ${HOME}/bin)  # 设置输出路径
```

注意
- 如果使用相对路径，`./`表示`makefile`文件所在的目录
- 如果目录不存在，会自动创建

