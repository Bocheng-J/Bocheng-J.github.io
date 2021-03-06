---
layout:     post
title:      Markdown文本在线编辑教程
subtitle:   Markdown
date:       2020-05-27
author:     oscar
header-img: img/post_markdown_0527.jpg
catalog: true
tags:
    - 教程
    - Instruction
---



> Written with [StackEdit](https://stackedit.io/).

## 1. Markdown 文本简介
Markdown是一种可以使用普通文本编辑器编写的[标记语言](https://baike.baidu.com/item/%E6%A0%87%E8%AE%B0%E8%AF%AD%E8%A8%80/5964436)，通过简单的标记语法，它可以使普通文本内容具有一定的格式。

Markdown的语法简洁明了、学习容易，而且功能比纯文本更强，因此有很多人用它写博客。世界上最流行的博客平台[WordPress](https://baike.baidu.com/item/WordPress)和大型CMS如[Joomla](https://baike.baidu.com/item/Joomla)、[Drupal](https://baike.baidu.com/item/Drupal)都能很好的支持Markdown。完全采用Markdown编辑器的博客平台有[Ghost](https://baike.baidu.com/item/Ghost/17013737)和[Typecho](https://baike.baidu.com/item/Typecho)。

## 2. 在线编辑器
[StackEdit](https://stackedit.io/)是一款功能全面的免费在线Markdown编辑器，在StackEdit的网页客户端中可直接进行文本输入，StackEdit系统会自动将文字转为Markdown格式或HTML格式，PDF格式等。可直接插入于博客。


----------
2020/06/17更新：

国内解决方案：[Cmd Markdown][1]


## 3. 添加图片
在Markdown中添加图片，首先需要将图片上传至云端，获取图片链接再进行插入。

这里我推荐[SM.MS](https://sm.ms/)，SM.MS是一款免费的在线图床软件。使用方法如下：



 1. 打开 SM.MS，将图片拖拽至上传框内，或点击右下角上传图片。
 ![smms1.JPG](https://i.loli.net/2020/05/28/USEL5jDZKkRBp2l.jpg)
 2. 上传完成后，点击upload按钮，将图片传至云端。
 ![smms2.JPG](https://i.loli.net/2020/05/28/cBQw15qKyYP2Oex.jpg)
3. 复制Markdown格式链接，将其粘贴在StackEdit文本框内想要添加图片的位置即可。
![smms3.JPG](https://i.loli.net/2020/05/28/9PFwbmdE8ao3QxW.jpg)


----------
2020/06/17更新：

国内解决方案：[聚合图床][2]

## 4. 添加视频
在Markdown中添加视频，与添加照片一样，较为简单的办法是先将视频上传至云端，再添加链接。这里以[B站](https://www.bilibili.com/)作为视频储存端为例。


**嵌入链接格式：**

    <iframe src="http://player.bilibili.com/player.html?aid=24931813&cid=42084760&page=1" scrolling="no" width="800px" height="600px" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

**获取视频链接：**
进入视频页面，复制下面的嵌入代码，再用其替换上面链接中的视频地址。
![bilibili1.jpg](https://i.loli.net/2020/05/28/SEMDjL2PfZRVsyi.jpg)

**插入视频**
最后，和插入图片一样，在Markdown文本中直接插入上述链接就可以了。
    


  [1]: https://www.zybuluo.com/cmd/#
  [2]: https://www.superbed.cn/
