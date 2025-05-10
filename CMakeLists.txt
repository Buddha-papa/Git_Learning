# 指定最低的CMake版本
cmake_minimum_required(VERSION 3.10)

# 设置项目名称
project(FileReader)

# 添加头文件搜索路径 
include_directories(src)

#添加库,math_utils是库的名称
add_library(math_utils STATIC src/math_utils/add.cpp) 

# 设置C++标准
set(CMAKE_CXX_STANDARD 11)

#添加可执行文件，并链接指定的库， main.cpp被编译 链接后，就会生成my_app可执行文件、
add_executable(my_app src/main.cpp) 
target_link_libraries(my_app PRIVATE math_utils)
