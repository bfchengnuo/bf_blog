---
title: 9patch图的制作
date: 2016-05-17 22:29:15
tags: [Android]
categories: 技能Get
---
## .9.png图片的介绍

顾名思义其实就是9宫格图片，将图片分为9块patch，其中，中心的patch作为内容拉伸区域。 


与传统的png 格式图片相比，9.png 格式图片在图片四周有一圈一个像素点组成的边沿，该边沿用于对图片的可扩展区和内容显示区进行定义。 

这种格式的图片在android 环境下具有自适应调节大小的能力。例如聊天框的背景

<!-- more -->

## 图片的制作

在android sdk的tools文件夹下提供了制作该格式图片的工具 draw9patch.bat
在AS中选中图片右键就有制作9图的选项，或者直接双击打开，左下角可以选择预览或者编辑
另：网上还有专门的制作工具，自行google

## 9图片解析
编辑模式：
![](http://o6lgtfj7v.bkt.clouddn.com/9%E5%9B%BE%E7%89%87%E7%BC%96%E8%BE%91%E6%A8%A1%E5%BC%8F.png)
a. 缩放Zoom: 调整左边编辑区的大小； 
b. 宫格比例Patch scale: 调整预览视图中图像的大小； 
c. 显示锁定区域Show lock: 当鼠标在图片区域时，显示不可编辑区域； 
d. 显示宫格Show patches: 预览这个绘图区中的可延伸宫格； 
e. 显示内容Show content: 在预览图片区域显示图片的内容区域； 
f. 显示坏宫格Show bad patches: 在宫格区域四周增加一个红色边界，这可能会在图像被延伸时产生人工痕迹，显示可能会对拉伸后的图片产生变形的区域。如果你消除所有的坏宫格，延伸视图的视觉一致性将得到维护。

简化可以分为：

![](http://o6lgtfj7v.bkt.clouddn.com/9%E7%82%B9%E5%9B%BE.jpg)

四角（1,3,6,8）：不拉伸
四边（2,4,5,7）分为两种：（2,7）只横向拉伸；（4,5）只竖向拉伸
中间（9）：横竖都拉伸

如果失误可按住shift键再鼠标单击或拖动来清除。

PS：注意，如果是从APK解压后得到的*.9.png文件，注意它是已将周围的空白像素去掉的，在使用时必须再加上，不然Android Studio会报错。