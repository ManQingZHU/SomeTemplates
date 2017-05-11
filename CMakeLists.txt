cmake_minimum_required(VERSION 3.6)

#设置项目名称
project(library)

set(CMAKE_C_STANDARD 99)

#添加头文件搜索路径
set(INC_DIR /usr/local/mysql/include)
#添加库文件搜索路径
set(LINK_DIR /usr/local/mysql/lib)

include_directories(${INC_DIR})
link_directories(${LINK_DIR})

#用于将当前目录下的所有源文件的名字保存在变量 DIR_SRCS 中
aux_source_directory(. DIR_SRCS)

add_executable(library ${DIR_SRCS})

#根据名字去寻找libxxx.a文件
target_link_libraries(library mysqlclient)
