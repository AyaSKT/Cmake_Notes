## 基础构建示例
#### 单源文件编译
- hw1.cpp
``` cpp
#include <stdio.h>

int main(){
	std::cout<<"Hello, world!"<<std::endl;
	return 0;
}
```

- CMakeLists.txt
``` cmake
cmake_minimum_required (VERSION 3.10)
 
project (Hw1)
# 项目名

add_executable(hw1 hw1.cpp)
# 生成可执行二进制文件hw1
```
