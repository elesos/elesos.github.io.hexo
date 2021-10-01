---
title: windows常用操作
tags:
  - windows
categories:
  - 不好分类
date: 2021-08-06 13:55:03
---





1,右键打开cmd

https://www.jianshu.com/p/f1568aaaa845

1.win+R 输入 regedit 打开注册表
 2.找到路径 HKEY_CLASSES_ROOT\Directory\Background\shell，
 3.在此目录下右键新建项openCMD，在openCMD目录新建项command
 4.在openCMD右键新建 DWORD(32位)值，
 名称为：ShowBasedOnVelocityId
 值为：639bc8

![img](https:////upload-images.jianshu.io/upload_images/6932643-200ecc793848b4d8.png?imageMogr2/auto-orient/strip|imageView2/2/w/513/format/webp)





![img](https:////upload-images.jianshu.io/upload_images/6932643-43b19a2135fd0629.png?imageMogr2/auto-orient/strip|imageView2/2/w/399/format/webp)




 5.在openCMD双击里面的 “默认” 设置值为：在此处打开CMD
 6.点击command双击里面的 “默认” 设置值为：cmd.exe /s /k pushd "%V"



或可以在路径中直接输入cmd， 当前目录可以直接打开cmd命令行

