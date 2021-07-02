---
title: MacOS app打包问题
tags:
  - mac
categories:
  - mac
date: 2021-07-02 21:31:21
---

编译的python打包时提示:bundle format unrecognized, invalid, or unsuitable

In subcomponent lib/python3.8

需要对每一个库都签名.

```
codesign --force --verify --verbose --sign "Apple Development: xxx" xxx.app
```
