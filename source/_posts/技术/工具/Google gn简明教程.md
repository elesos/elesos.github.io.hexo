---
title: Google gn简明教程
tags:
  - gn
categories:
  - gn
date: 2021-07-04 13:30:10
---

https://gn.googlesource.com/gn/

generates build files for [Ninja](https://ninja-build.org/).

## 重要文件

.gn : Defines root of GN build tree

共享的变量放在gni文件中，通过 import导入

查有哪些targets

```
gn ls out/Default “//base/*”

```

查看变量的值

```
gn args out/Default
gn args --list out/Default

```

## 快速入门

https://gn.googlesource.com/gn/+/main/docs/quick_start.md

先下载示例代码 

`git clone https://gn.googlesource.com/gn`

我的在 https://github.com/elesos/gn

