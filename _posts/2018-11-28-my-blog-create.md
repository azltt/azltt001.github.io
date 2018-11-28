
---
layout:     post
title:      "搭建博客的借鉴「」—— 。。。 "
subtitle:   "搭建"
date:       2018-11-28
author:     "Andy"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 随笔
---
> 本篇为Blog第二篇 —— 如何搭建。


## 前言

>正所谓前人栽树，后人乘凉。


## 正文

首先感谢[Huxpro][1]提供的博客模板、[qiubaiying][3]的大部分教程以及网上的各位大神
本人也不想搞太复杂，也就只是使用Github托管博客，其间也出现很多问题，，凭借着本人的乱搞能力，最终还是硬向搭建OK了。
写博客的md文件也是第一次接触，在网上一通乱搜，也还是勉勉强强写的出来。
好了话也不多说了，碰巧看到此篇博客的小主也差不多是想看看小编是如何搭建出来的，接下来讲讲github托管搭建博客的方式(ps:若有不懂可在文末评论区留言)、（大神手下留情）。  
先来看看小编的主页样式：
[![AndyBlog](https://img-blog.csdnimg.cn/2018112820115146.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FuZ2VsX2x0dA==,size_16,color_FFFFFF,t_70)][2]
心动有木有，木有请走开。。。。
## 搭建博客步骤
登录你的github账号；
点击github头像旁边的 “+” 号；
选择 Import repository克隆地址填 想要克隆的博客模板地址 （如：https://github.com/azltt/azltt.github.io），项目名填  你的用户名.github.io（像我的就填写azltt.github.io）；
克隆完成后 基本上已经完成了；
此时你可以直接用 你的用户名.github.io 到浏览器访问

此时有可能会有些小问题（访问不到页面）：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181128203452768.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FuZ2VsX2x0dA==,size_16,color_FFFFFF,t_70)
此时，有可能出现两种错误：

 - 你的仓库名有可能出错
>修改仓库名：
点击settings进入设置
![set](https://img-blog.csdnimg.cn/20181128204116751.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FuZ2VsX2x0dA==,size_16,color_FFFFFF,t_70)
修改仓库名为 `你的Github账号名.github.io`，然后 Rename
![rename](https://img-blog.csdnimg.cn/20181128204138847.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FuZ2VsX2x0dA==,size_16,color_FFFFFF,t_70)
这时你再在浏览器中输入 你的Github账号名.github.io 

 - 这个不知道该咋说往下看吧先
>点击settings进入设置，下滑， 
点击chage theme按钮，随便选择一个确定即可。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181128204507806.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FuZ2VsX2x0dA==,size_16,color_FFFFFF,t_70)

访问，成功；
接下来就是修改自己资料以及博客的时候了。
主要是编辑_config.yml的内容，主要就是把他人的信息改成自己的
在这里就不做多说了，
以下主要介绍下评论系统：
由于 Disqus 对于国内网路的支持十分糟糕，很多人反映 Disqus 评论插件一直加载不出来。咱们就直接用Gitalk 评论插件
首先来看看 Gitalk 的界面和功能：
gitalk 使用 Github 帐号登录，界面干净整洁，最喜欢的一点是支持 MarkDown语法。
原理
Gitalk 是一个利用 Github API,基于 Github issue 和 Preact 开发的评论插件，在 Gitalk 之前还有一个 gitment 插件也是基于这个原理开发的,不过 gitment 已经很久没人维护了。
可以看到在 gitalk 的评论框进行评论时，其实就是在对应的 issue 上提问题。
gitalk评论框
![评论框](https://img-blog.csdnimg.cn/20181128214343201.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FuZ2VsX2x0dA==,size_16,color_FFFFFF,t_70)
Github issue
![issue](https://img-blog.csdnimg.cn/20181128214459605.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FuZ2VsX2x0dA==,size_16,color_FFFFFF,t_70)
集成 Gitalk
到这里，你应该对 Gitalk 有个大致的了解了，现在，开始集成 gitalk 插件吧。
将这段代码插入到你的网站：
```
<!-- Gitalk 评论 start  -->
<!-- Link Gitalk 的支持文件  -->
<link rel="stylesheet" href="https://unpkg.com/gitalk/dist/gitalk.css">
<script src="https://unpkg.com/gitalk@latest/dist/gitalk.min.js"></script> 
<div id="gitalk-container"></div>     <script type="text/javascript">
    var gitalk = new Gitalk({

    // gitalk的主要参数
		clientID: `Github Application clientID`,
		clientSecret: `Github Application clientSecret`,
		repo: `存储你评论 issue 的 Github 仓库名`,
		owner: 'Github 用户名',
		admin: ['Github 用户名'],
		id: '页面的唯一标识，gitalk会根据这个标识自动创建的issue的标签',
    
    });
    gitalk.render('gitalk-container');
</script> 
<!-- Gitalk end -->
```
我们需要关心的就是配置下面几个参数(这些参数就就写在_config.yml文件中，可以按照[小编的github](https://github.com/azltt/azltt.github.io)中的去配置，当然具体的参数还是要写自己的)：
```
clientID: `Github Application clientID`,
clientSecret: `Github Application clientSecret`,
repo: `Github 仓库名`,//存储你评论 issue 的 Github 仓库名（建议直接用 GitHub Page 的仓库名）
owner: 'Github 用户名',
admin: ['Github 用户名'], //这个仓库的管理员，可以有多个，用数组表示，一般写自己,
id: 'window.location.pathname', //页面的唯一标识，gitalk 会根据这个标识自动创建的issue的标签,我们使用页面的相对路径作为标识
```
当然，还有其他很多参数，有兴趣的话可以 [点这里](https://github.com/gitalk/gitalk#options)。
## 创建 Github Application
Gitalk 需要一个 Github Application，[点击这里申请](https://github.com/settings/applications/new)。

按照下面填写自己相应参数：
![参数填写](https://img-blog.csdnimg.cn/20181128215428896.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FuZ2VsX2x0dA==,size_16,color_FFFFFF,t_70)
点击创建，会生成Client ID 和 Client Secret ，
将 Client ID 和 Client Secret 填入 Gitalk 参数中
当你参数都设置好，将代码推送到 Github 仓库后，没什么问题的话，当你点击进入你的博客页面后就会出现评论框了。
But，你用 github 帐号登录（管理员），并且第一次加载该会比较慢，因为第一次加载会自动在你 repo 的仓库下创建对应 issue。
至此，
https://你的用户名.github.io 就是你的个人博客了。

## 结语
Gitalk 需要你点开每篇文章的页面才会创建对应的 issue，对与文章多的人来说，简直是最糟糕的体验；So这篇[自动初始化 Gitalk 和 Gitment 评论](https://draveness.me/git-comments-initialize)有效的解决了这一事情的发生


参考：

>https://www.jianshu.com/p/78c64d07124d
https://github.com/qiubaiying/qiubaiying.github.io/wiki/%E5%8D%9A%E5%AE%A2%E6%90%AD%E5%BB%BA%E8%AF%A6%E7%BB%86%E6%95%99%E7%A8%8B

---

*本篇完。*


  [1]: https://github.com/huxpro
  [2]: https://azltt.github.io
  [3]:https://github.com/qiubaiying
