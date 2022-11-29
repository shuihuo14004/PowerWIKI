---
title: QT的pro文件讲解
date: 2021-12-5 15:30:29
about: 
categories: QT
tags: 
   - QT
   - pro文件
mathjax: true
---



# 相关学习资料链接

链接: [萌马工作室QT讲解](https://www.bilibili.com/video/BV1Qv411k79r).

# QT的pro文件讲解

| QT添加需要模块 |                      |
| -------------- | -------------------- |
| Qt +=          | 表示为QT中添加该模块 |
| Qt =           | QT中只有该模块       |



# 编译过程中相关

| 目标文件名称     | TARGET=appname         |
| ---------------- | :--------------------- |
| 指定程序放置目录 | DESTDIR=appdir         |
| 编译宏开关       | DEFINES+=yourdefines   |
| OBJ生成目录      | OBJECTS_DIR=yourobjdir |

# 常用文件

| 源文件   | SOURCES = appsrc.cpp    |
| -------- | ----------------------- |
| 头文件   | HEADERS = appfiles.h    |
| UI文件   | FORMS += yourwidgets.ui |
| 资源文件 | RESOURCES += youres.rc  |

# 环境配置

| 引用头文件路径 | INCLUDES = include-path   |
| -------------- | ------------------------- |
| 引用库路径     | DEENDPATH = appdependpath |
| 链接库文件     | LIBS += -L“路径”库名称    |
| 模块类型配置   | TEMPLATE = APP(lib)       |

# 远程调试

| target.path =/home/远程计算机中的目录<br/>INSTALLS +=target | 常用与远程调试（本身是复制粘贴） |
| ----------------------------------------------------------- | -------------------------------- |

