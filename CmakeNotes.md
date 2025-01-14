## Structure
A cmake file is typically named CMakeLists.txt.
1. A typical CMakeLists.txt file contains the following parts:
```cmake
# 1. Specify the minimum version
cmake_minimum_required(VERSION 3.10)


# 2. Project information
project(ProjectName LANGUAGES CXX)

# 3. Define variables
set(MY_VAR "Value")

# 4. Add include directories
include_directories(path/to/include)

# 5. Add source files
add_executable(TargetName main.cpp other.cpp)

# 6. Set compile options
target_compile_options(TargetName PRIVATE -Wall)

# 7. Add linked libraries
target_link_libraries(TargetName PRIVATE SomeLibrary)

# 8. Define installation rules
install(TARGETS TargetName DESTINATION bin)

# 9. Logical control (optional)
if(MY_VAR STREQUAL "Value")
    message("MY_VAR is set to Value")
endif()
```

## Syntax
1. Command 指令 
	所有cmake中的操作均通过指令来完成，其格式为：
```cmake
command(arguments ...)
```
	
2. Variables 变量
	定义变量和使用变量
```cmake
set(VAR_NAME Value)   # 定义变量
message(${VAR_NAME})  # 使用变量
```

3. 全局路径变量
	
	源代码相关路径
``` cmake
CMAKE_SOURCE_DIR
# 指向顶层 CMakeLists.txt 所在的目录。
	
CMAKE_CURRENT_SOURCE_DIR
# 指向当前处理的 CMakeLists.txt 所在的目录。
# 在多级目录的项目中，适用于获取子目录的源代码路径。
```
	
	构建相关路径
	
```
CMAKE_BINARY_DIR
# 指向顶层构建目录。

CMAKE_CURRENT_BINARY_DIR
# 指向当前处理的 CMakeLists.txt 对应的构建目录。
```
	
	- 项目相关路径
	
	``` cmake
PROJECT_SOURCE_DIR
# 项目的源代码目录。
# 由 project() 定义，适用于标识当前项目的根目录。

PROJECT_BINARY_DIR
# 项目的构建目录。
# 由 project() 定义，适用于当前项目的构建文件路径。
	```

4. 安装路径变量
	
	- 默认安装路径
	
``` cmake
CMAKE_INSTALL_PREFIX
# 默认安装目标的根路径
# 默认值：
# Linux/MacOS /usr/local
# Windows C:/Program Files
```

5. 内置模块路径
	
	- 模块查找路径
	
``` cmake
CMAKE_MODULE_PATH
# 自定义模块（.cmake 文件）的搜索路径。
```
	
	
	
• CMAKE_MODULE_PATH

自定义模块（.cmake 文件）的搜索路径。

• CMAKE_ROOT

指向 CMake 的安装根目录。

  

**6. 构建工具路径**

• CMAKE_COMMAND

CMake 可执行程序的完整路径。

• CMAKE_C_COMPILER

C 编译器的路径。

• CMAKE_CXX_COMPILER

C++ 编译器的路径。