---
layout:     post
title:      Ubuntu系统安装搜狗中文输入法
subtitle:   Ubuntu 安装中文输入法
date:       2020-04-28
author:     oscar
header-img: img/post_20200427_bg.jpg
catalog: true
tags:
    - Ubuntu
    - Linux 
    - 教程
    - Instruction
---

# Ubuntu系统下安装中文输入法
Ubuntu 系统原生的输入法为英文输入法，虽然不影响我们敲代码，但当我们想用到中文字符的时候就很受影响，因此本文将介绍如何在Ubuntu系统下安装中文输入法。

## **step1：安装fcitx**
进入Ubuntu系统后打开命令窗口，输入：

    sudo apt install fcitx

![安装fcitx](https://i.loli.net/2020/04/28/sEUk1cozDAHy9ST.jpg)
在提示进行选择的时候输入y，fcitx就安装成功了。
## **step2：下载搜狗输入法**
首先，点击系统右上角的设置选项：

![系统设置](https://i.loli.net/2020/04/28/KABSjUIYVw1fhOz.jpg)

进入about，查看系统的OS类型，是64位或32位：

![OS类型](https://i.loli.net/2020/04/28/VmFWpqrivZNMtYX.jpg)


接着进入搜狗输入法Linux版的[官网](https://pinyin.sogou.com/linux/?r=pinyin)，下载对应的安装包。

![下载搜狗输入法](https://i.loli.net/2020/04/28/Vrow3GMRuSIUNOH.jpg)


注意，在这一步，选择保存文件而不是运行打开：

![保存文件](https://i.loli.net/2020/04/28/hzQwOF5HXgM8LBR.jpg)

在此推荐新建单独的文件夹，将安装包放于其中。打开命令窗口，进入该文件夹，运行：

    sudo dpkg -i sogoupinyin_2.2.0.0108_amd64.deb
    
   
**注意：此处dpkg后面的参数应该为你下载的安装包的名称，需要进行单独更改。**
![安装搜狗输入法](https://i.loli.net/2020/04/28/gIz8MiNH6W5vnZJ.jpg)

可以看到，我一开始没有更改安装包的名字，安装报了错。

修复依赖关系：

    sudo apt-get install -f

![安装完成](https://i.loli.net/2020/04/28/4xOR986MgXHEvjV.jpg)

到此，搜狗输入法就安装完成了。

接着我们重启系统，进行下一步的设置操作。

## **step3：设置系统输入法**

在系统桌面使用 win + a 打开应用界面，选择所有应用，搜索打开fcitx configuration。
![打开设置](https://i.loli.net/2020/04/28/V6DNjZ9EH3AeJqC.jpg)

点击左下角加号，添加新输入法。
![添加输入法](https://i.loli.net/2020/04/28/sqc26d3iHnGCVB7.jpg)

取消左下角勾选
![取消勾选](https://i.loli.net/2020/04/28/rHC6sOBuZSD2teA.jpg)

搜索Sougou Pinyin (**要匹配大小写**)。
或者直接列表拉到最底也能找到搜狗输入法。
![搜索搜狗输入法](https://i.loli.net/2020/04/28/JV6uDtUNHhcgFWQ.jpg)

点击OK添加。

可以选择将其为系统第一输入法：
![置顶](https://i.loli.net/2020/04/28/HXRVDkfOUn9AvB4.jpg)

重启系统即可正常输入中文文字。
![设置成功](https://i.loli.net/2020/04/28/jZ3JYwUvnlLtD6q.jpg)



这是我的第一篇博文，希望对看到这篇的你有所帮助！
