---
title: iOS Crash Log 解析
date: 2019-04-30 18:20:33
categories:
- Xcode
tags:
- Xcode
---

# 1、将错误日志符号化

我们知道，如果是自己的测试机，在调整的时候发生崩溃，会在Xcode->Window->Devices and Simulators->View Device Logs中产生已经符号化的Crash Log，如果是测试的测试机发生崩溃，将crash log导出在自己电脑上看是没有符号化的，我们需要将crash符号化才能查找出崩溃原因。以下步骤就是将别的测试机中的crash log在自己的测试机中符号化。

其实之前的organizer之所以能自动解析你设备上的crash log，是因为它能根据spotlight的索引来找到对应的.app和dSYM文件，对于这一点，我的猜测是在自己的Mac电脑上编译生成应用时，系统自动对其进行了索引。这个索引应该是根据app uuid来索引的。这个uuid可以执行下面的命令得到：

>dwarfdump —uuid YourApp.app/YourApp 
>dwarfdump —uuid YourApp.app.dSYM

如果要能解析出crash log，crash log中携带的uuid与dSYM文件的uuid必须与app uuid一致。
既然spotlight能自动进行索引，那是不是也可以手动进行索引呢？答案是能，这正是自动解析的关键。手动索引的命令是mdimport

具体步骤：

1. 新建一个文件夹（如crash），将crash log对应版本的ipa和dSYM文件放入其中。
2. 打开crash文件夹所在的目录，执行命令mdimport crash。
3. 将crash log文件夹拖动到Xcode->Window->Devices and Simulators->View Device Logs->Devices->This Device中（xcode需要连接测试机）。

