---
layout:     post
title:      Jekyll github page博客本地调试
subtitle:   github博客本地调试
date:       2020-06-06
author:     oscar
header-img: img/bg_20200606_1.jpg
catalog: true
tags:
    - 教程
    - Instruction
---
# Jekyll github page博客本地调试教程

相信大家在调试博客时都有这样的烦恼，将更改commit到github进行调试，效率太低，操作太复杂。

**在本地调试博客, 能极大提升工作效率！！！** 

（本教程所有操作全部在linux系统本地git仓库内完成）



## 方法一：

 
  安装 `jekyll`和 `jekyll bundler`：
 
    $ gem install jekyll
    $ gem install jekyll bundler

cd进入博客所在目录

```ruby
$ jekyll s
```
接着就可以在 http://127.0.0.1:4000/ 看到博客，任何本地git仓库中的修改，只需刷新一次就能更新显示在这个页面中。

使用`ctrl+c`来停止本地博客调试。

参考：[简书-BYQiu](https://www.jianshu.com/p/e68fba58f75c)


## 方法二:
之前在国外的时候一直使用方法一，回国之后不知道怎么方法一就不好用了，挂了VPN也还是不行，后来发现了方法二，重新实现了本地调试。


首先安装bundler包管理器

     gem install bundler

在github-page的git本地仓库主目录下创建`Gemfile`：

    gedit Gemfile

该文件内的具体内容如下:
```
source 'https://rubygems.org'      
gem 'github-pages'
```
执行bundle：

    bundle install

在git仓库主目录下启动本地调试：

    bundle exec jekyll serve
    
默认访问地址为：`http://localhost:4000`

至此就大功告成啦。

当然也可以手动更新本地jekyll：

    bundle update

同样，使用`ctrl+c`来停止本地博客调试。

参考：[安装Jekyll本地调试环境--lazybios](http://lazybios.com/2014/09/install-jekyll-in-locate/)
