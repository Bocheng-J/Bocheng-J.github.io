---
layout:     post
title:      UGC PGC OGC之间的区别
subtitle:   UGC PGC OGC介绍
date:       2020-06-04
author:     oscar
header-img: img/bg_0604_2.jpg
catalog: true
tags:
    - 产品
    - 学习笔记 
    - study notes
---

# oracle VM virtualbox ubuntu虚拟机系统磁盘扩容

当初安装时，分配给了虚拟机25G空间，想着完全够用了，没想到两个月下来系统就被占满了。这里吐血推荐大家在第一次分配空间时就多分配点，最好按照预想空间的两倍来分配，否则日后再拓展会很麻烦，还容易丢失数据。

今天把系统拓展的步骤记录一下，避免以后再踩坑。

## 1. 为虚拟机拓展空间，并进入分区工具GParted

**[教程](https://segmentfault.com/a/1190000004990372)点这里。**

感谢原作者的整理。

（**注意**：下载GParted时要看好系统的版本，i686是32位系统的，amd64是64位系统的。）


## 2. 进入GParted，进行内存分配
为虚拟机拓展了空间后，这一部分空间并不能立即被我们使用，我们还必须进行内存分配，才能真正激活这一部分磁盘空间。

**[教程](https://www.cnblogs.com/yuanlibin/p/9207671.html)点这里。**
感谢原作者的整理。
