---
title: 开关电源中的“右半平面零点问题（RHPZ）
date: 2021-11-29 23:18:54
about: 
categories: 开关电源
tags: 
   - 开关电源
   - 学习笔记
   - 拓扑类
   - 推挽拓扑
mathjax: true
---



开关电源中的“右半平面零点问题（RHPZ）

在小信号频率补偿中，极点和零点通常位于复数s平面的左半部分左半平面极点会使增益下降、相位滞后，而零点则相反，会使增益上升、相位超前。RHPZ的问题在于它的效果是让增益增加（类似于一个传统的零点），但是相位滞后。这个特性即使给予补偿的话也是很麻烦的（实际上一般也很难补偿），并且它通常会使整个环路增益在相对较低的频率时滚降。

在Buck系列电路中不会出现 RHPZ，它只会出现在 Boost和Flyback拓扑结构中，且只有在电路工作在连续导通模式（CCM）和恒定开关频率时才会出现。不出现在DCM中是因为DCM的起始状态是确定的（电流为0）。这是由输入到输出的能量传递的半周期延迟引起的（需要先储能再释放）

下图为相关解释

![QQ截图20211129224720.png](https://tva1.sinaimg.cn/large/005Q1GhGly1gwwemtvactj30f70b9q5h.jpg)

​                                                                                             图1





在图1两种拓扑结构中，当开关管导通时，能量是首先存储在电感中，此时间为$D\times T$。当开关管关闭时，能量传输到输出端（和输出电容器），此时间为$(1-D)\times T$。考虑CCM工作情况，电感电流连续。如果我们负载电流突然增加，那么第一个响应就是输入端要增加能量，这会使占空比D变大，如图2所示。







![QQ截图20211129224917.png](https://tva1.sinaimg.cn/large/005Q1GhGly1gwweop0wfoj30fr0fdwjd.jpg)

虽然占空比的增加将在开始的几个开关周期内