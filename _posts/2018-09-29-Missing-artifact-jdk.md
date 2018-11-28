---
layout:     post
title:      "Missing artifact jdk.tools:jdk.tools:jar:1.8报错"
subtitle:   "Error"
date:       2018-09-29 12:00:00
author:     "Andy"
header-img: "img/post-bg-re-vs-ng2.jpg"
header-mask: 0.3
catalog:    true
tags:
  - Error
---
## 前言
不知道怎么做,看了网上的教程，自己试了试，但都没有成功。
只能下手自作一番：
## 正文
方法一：（这个方法感觉不太好，我也不知道为啥）
首先
  pom文件中加入

'<dependency>'
    '<groupId>jdk.tools</groupId>'
    '<artifactId>jdk.tools</artifactId>'
    '<version>1.8</version>' 
'</dependency>'

然后将你电脑的JDK目录(本人：D:\worksoftware\Java\jdk1.8.0_181\lib)下的lib目录中的tools.jar复制到你的maven仓库下（\maven\maven-repository\jdk\tools\jdk.tools\1.8\），
并重命名为：jdk.tools-1.8.jar。至此成功

*本篇完。*
