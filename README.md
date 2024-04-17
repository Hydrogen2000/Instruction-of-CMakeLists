# Instruction-of-CMakeLists
CMakeLists文件说明

```
cmake_minimum_required(VERSION 3.0.2)
```
用于设置CMake的最小版本要求。如果用CMake版本低于这个版本，CMake将不会继续处理项目，并显示错误消息。

```
project(hello_world)
```
用于定义项目名称（功能包名）。在之后的CMakeLists代码里，可以使用`${PROJECT_NAME}`变量来引用这个包名。

