---
layout: post
title: 大创项目|选相开关 
category: 技术
tags: DSP
keywords: 
description: 
---
###参考书籍
DSP原理及应用技术-赵成
###DSP与F2812——静态定点通用微处理器
[哈佛结构](http://blog.sina.com.cn/s/blog_a44094ea01016s09.html)

[TMS320F2812LQFP封装引脚图](http://zhidao.baidu.com/link?url=9PJJL-sB49QHQdNC3ngYLL5AcPMyIhtG-ZjOtg3mUetErcbD0O2ja82t_7F2VI4B9AHJ3wentY0fqlJ0-YiKha)

[管脚描述列表](http://wenku.baidu.com/link?url=0oXYhIaxz78c1fGKDNBi4F_pczg_Hy_PiqwaoEVNPLXKANb5k-Sd-8N312OMuTN1NbZp7aw9sI5hKupeRAssjeXU63tNDzlQbl7UcRkn0Xm)

运行模式：C28X，etc

片内外设：参见ti内核架构图，包括PWM，ADC，CAP，QEP，SPI，EMIF

cpu信号线：存储器结构信号，时钟和控制信号，复位和终端信号，仿真信号

cpu内核架构：P23，cpu存储数据存储空间流程

CPU寄存器：P25，分类与功能

###TMS320F2812驱动程序设计

###算法部分
##safepoint
以safepoint代替实际过零点

三种过零点

symmetric：ac-component=dc-component

shifted（constant amplitude）：zero-crossing point in the first cycle（minor loop）

asymmetic（decreasing amplitude）：minimum ac-wave for positive dc-component，maximum ac-wave for nagetive dc-component

对采样得到的数据点数据建模，求出最佳直流交流幅值和相角。
四参数正弦拟合算法
使用MATLAB和C写出函数
##自适应自检测算法
加权最小均方算法
##半波福利叶算法
##改进半波福利叶算法

