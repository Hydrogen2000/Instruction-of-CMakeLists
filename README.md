# Instruction-of-CMakeLists
CMakeLists文件说明

```
cmake_minimum_required(VERSION 3.0.2)
```

用于设置CMake的最小版本要求。如果用CMake版本低于这个版本，CMake将不会继续处理项目并报错。

【本句设置CMake的最小版本要求为3.0.2。】

```
project(hello_world)
```

用于定义项目名称（功能包名）。在之后的CMakeLists代码里，可以使用`${PROJECT_NAME}`变量来引用这个包名。

【本句定义项目名称为hello_world。】

```
# add_compile_options(-std=c++11)
```

用于指定C++编译器的编译标准。

【本句指定编译器以C++2011标准来编译源代码，一般保持注释。】

```
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
)
```

用于查找ROS的catkin构建系统的组件功能包。`catkin`是ROS的构建系统，基于CMake，用于构建和管理ROS功能包。`REQUIRED`关键字表示是必须找到的，否则CMake将停止处理并报错。`COMPONENTS`后面跟需要的功能包名称，这些功能包是ROS中已经构建好的。

【本句查找了roscpp、std_msgs功能包】

```
find_package(Boost REQUIRED COMPONENTS 
  system
)
```

用于查找C++的Boost库的组件功能包。`Boost`是C++库。`REQUIRED`关键字表示是必须找到的，否则CMake将停止处理并报错。`COMPONENTS`后面跟需要的功能包名称。

【本句查找了system功能包，它通常用于系统级别的操作，如线程管理。】

```
# catkin_python_setup()
```

用于配置Python代码，并生成相应的setup.py文件，使得它们可以在ROS中正确地使用。

【一般保持注释】

```
# add_message_files(FILES
#   ${MESSAGE}.msg
# )
# add_service_files(FILES
#   ${SERVICE}.srv
# )
# add_action_files(FILES
#   ${ACTION}.action
# )
```

用于添加消息文件。`FILES`将引用当前功能包msg目录中的.msg文件，生成一个消息的.h头文件。

【需要时解注，srv和action用法与此相同】

