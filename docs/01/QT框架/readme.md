---
title: QT的pro文件讲解
date: 2021-12-5 15:30:29
about: 
categories: QT框架
tags: 
   - QT
   - main主文件
mathjax: true
---

# QT主文件框架

```c++
int main(int argc, char *argv[])
{
    QApplication a(argc, argv);     //实例化QT对象
    MainWindow w;                   //用户界面
    w.show();

    return a.exec();                //消息循环 阻塞式 不退出
}
```

# 框架说明

| 1    | 初始化：每个QT程序都有一个QApplication对象，用于QT GUI的示例化，前端QT都有这个对象 |
| ---- | ------------------------------------------------------------ |
| 2    | QT界面显示对象MainWindow                                     |
| 3    | 主事件循环：a.exec（）是每个QT应用程序都要调用的函数。程序运行停在这里等待外部事件（外部用户的任何动作） |

