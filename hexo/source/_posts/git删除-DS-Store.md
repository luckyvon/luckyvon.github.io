---
title: git删除.DS_Store
date: 2019-05-07 10:50:04
categories:
- git
tags:
- git 
---

### 一、未提交的项目执行下面的操作，提交文件时候则不提交.DS_Store文件 
#### 1. 添加忽略 
* cd到git目录下新建.gitignore文件并配置忽略文件 
  * 1、vim .gitignore 
  * 2、输入以下内容后保存 
    * .DS_Store 
    * */.DS_Store 
#### 2. 提交项目

### 二、如果包含.DS_Store的项目已经提交，那么需要先删除本地的.DS_Store文件 并 配置完忽略后，再次提交

* 删除当前目录下的所有的.DS_Store 
  * 1.find . -name '*.DS_Store' -type f -delete 
  * 2.git add –all 
  * 3.git commit -m '.DS_Store banished!' 
  * 4.git push origin dev(推送到远端dev分支)


