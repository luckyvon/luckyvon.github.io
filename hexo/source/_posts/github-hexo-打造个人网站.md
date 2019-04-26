---
title: github + hexo 打造个人网站
date: 2019-04-26 21:38:25
categories: 
- Tools
tags:
- hexo
- github
---

![](./github-hexo-打造个人网站/hexo_header.jpg)

# 前言

温故而知新，可以为师矣。有一个地方能够记录平时的心得体会，总结所看所想。当遗忘的时候回头看看，能够快速回忆起来，节约时间。人的精力应该用来进行创造性的活动，而不是死记硬背。有这么多现成的网站，为什么非要自己弄？自己一手带大的才有感情，才能坚持...让我们开始吧。

经过网上查找，github pages + hexo 能够做出功能很强大的网站。使用方便，页面可以高度自定义。最终选择这个组合。

# 相关介绍

* Github & Github Pages

[Github](https://github.com)是一个免费的文件托管平台。可以直接在终端通过[Git命令](https://git-scm.com/book/zh/v2)管理文件，也可以通过[Github客户端](https://desktop.github.com/)

* Github Pages

[Github Pages](https://pages.github.com/)是Github提供的静态网站。

* Hexo

[Hexo](https://hexo.io/zh-cn/docs/)是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。能够很方便的管理文档，切换各种酷炫的主题。

* Markdown

[Markdown](https://www.w3cschool.cn/markdownyfsm/)是一种纯文本格式的标记语言。通过简单的标记语法，它可以使普通文本内容具有一定的格式。

# 搭建过程

因为已经弄完了，就不一一截图了，附上一篇前人总结的文档
[mac+github+hexo搭建网站](https://www.jianshu.com/p/cbf8ba8af532)

# 遇到的问题

## 多台电脑同时同时编辑

[多台电脑上提交和更新Hexo](https://www.jianshu.com/p/0b1fccce74e0)  

和这位博主不同，我的切分下载到本地之后，将文件全都删掉，只留.git文件（不然没法git同步。。。）然后用hexo init hexo 在分支文件夹内新建一个hexo文件夹，然后将next主题下载到themes文件夹中。需要将next文件夹中的.git删除（属于不同的仓库，不删除的话，无法用git add .添加）。然后将所有文件提交。新建hexo，会带一个gitignore忽略配置文件。将node_modules文件夹忽略了，在别的电脑下载下来这个分支之后，需要cd 到 hexo并运行npm install安装node_modules
