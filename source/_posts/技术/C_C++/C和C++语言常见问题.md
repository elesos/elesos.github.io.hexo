---
title: C和C++语言常见问题
tags:
  - C/C++
categories:
  - C/C++
date: 2021-07-04 10:52:49
---

- \#pragma pack(push,1)

结构体字节对齐方式设置，把原来对齐方式压栈，并将新的对齐方式设置为一个字节对齐

```
#pragma pack(pop)            恢复对齐状态
```

https://blog.csdn.net/vbLittleBoy/article/details/6935165

- enum不要将变量写在后面

正确的是enum test{}; 而不是enum {} test;

- cpp编译时：error: use of undeclared identifier 'memcpy'

```
#include <string.h>
```
