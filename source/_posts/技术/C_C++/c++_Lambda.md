---
title: c++ Lambda
tags:
  - C/C++
categories:
  - C/C++
date: 2021-07-02 08:04:02
---

方便定义匿名函数

```
[capture list] (params list) mutable exception-> return type { function body }
[capture list] (params list) -> return type {function body}
[capture list] (params list) {function body}
[capture list] {function body}
```

capture list：捕获外部变量列表 , &, a, b除a和b按值进行传递外，其他参数都按引用进行传递。 a, &b 将a按值进行传递，b按引用进行传递。 =，&a, &b 除a和b按引用进行传递外，其他参数都按值进行传递。

params list：形参

mutable指示符：用来说明是否可以修改捕获的变量

exception：异常设定

return type：返回类型

function body：函数体



```
int a = 123;
  auto f = [a]()mutable { cout << ++a; }; // 不会报错
  cout << a << endl; // 输出：123
  f(); // 输出：124
```

# 可调用对象

对于一个对象或者一个表达式，如果可以对其使用调用运算符，则称为可调用对象，如果类定义了调用运算符，则该类的对象称作函数对象

一个 lambda 表达式表示一个可调用的代码单元
