---
layout: post_item
title:  'Bottle+CherryPy+R(ggplot2)构建轻量Web统计运营系统'
date:   2014-05-02
author: 薛笛
categories : [技术分析]
tags: [系统开发]
---

![R-Logo](http://t2.qpic.cn/mblogpic/331772cba0eccf0f4b28/2000 "R-Logo")

近期有个轻量Web运营系统的搭建工作，系统展示的内容很重要，但只是内部少数人使用不会有高并发，所以在选型方面我倾向于使用更灵活的Python而不是很熟悉但比较重的JSP/Servlet。在图表展示方面python有很多选择，不过我更倾向于使用更专业一些的R(ggplot2)或者Google chart API。但后者没有Local的库，所以我倾向于使用R(ggplot2)。

<!--more-->
##Python3
在几乎所有运营机都是2.7.x的情况下、在全世界2to3都甚为缓慢的情况下，折腾v3的决定是否正确？我的理由是，至少我们在这个项目里没什么损失，不是吗？

##Bottle+CherryPy
Bottle本身很简单，并且支持用Python的模板解析，内置单线程WCGI Server也足够调试用了。如果正式上线启用，CherryPy用来做多线程框架，Bottle用于实现基础功能，搭配还是不错的。

##R(ggplot2)
[R.Graphics.Cookbook(2012.12)]很棒的绘图分析工具，所有想要的图几乎都有


未完待续。。。


