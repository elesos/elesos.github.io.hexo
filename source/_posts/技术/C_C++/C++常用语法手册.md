---
title: C++常用语法手册
tags:
  - C/C++
categories:
  - C/C++
date: 2021-07-02 21:17:07
---

C++98是第一个C++标准，1998年发布。

C++11，第三个C++标准，2011年

C++14，第四个C++标准，2014年

C++17，第五个C++标准，2017年

C++20 , 2020

下一代是C++23



## 关键字

https://www.runoob.com/w3cnote/cpp-keyword-intro.html





范围for

using代替typedef

用vector和迭代器代替数组和指针

用string代替c风格字符串 常量对象只能调用常成员函数


拷贝构造函数何时调用：

一个对象初始化另一个对象；函数参数；返回对象

构造函数调用顺序：先调用内嵌对象的构造函数，按定义顺序 在类外对静态数据成员定义和初始化

静态函数成员一般用于访问静态数据成员，如果要访问非静态数据，需要传递对象进来。

常对象（数据成员不能改变）只能调用常成员函数（不能改数据成员，不能调普通函数）

explicit 构造函数用来防止隐式转换

```
= default; 指示编译器自动生成函数体
建议重载的方法都加了override 关键字。防止出现不正确的继承行为
```

http://c.biancheng.net/view/400.html

# 宏

```
#表示：对应变量字符串化  

##表示：把宏参数名与宏定义代码序列中的标识符连接在一起，形成一个新的标识符
```

# namespace

匿名命名空间

```
当定义一个命名空间时，可以忽略这个命名空间的名称：
    namespce {
        char c;
        int i;
        double d;
    }
    编译器在内部会为这个命名空间生成一个唯一的名字，而且还会为这个匿名的命名空间生成一条using指令。所以上面的代码在效果上等同于：
    namespace __UNIQUE_NAME_ {
        char c;
        int i;
        double d;
    }
    using namespace __UNIQUE_NAME_;
```

在匿名命名空间中声明的名称,具有internal链接属性，这和声明为static的全局名称的链接属性是相同的，即名称的作用域被限制在当前文件中

**C++ 新的标准中提倡使用匿名命名空间,而不推荐使用static**

可以在匿名的空间里面声明很多变量和函数,这样可以省去了对每个变量和函数添加static声明. 实质上匿名空间的功能跟static声明是一样的.

# max

 int max: Value of INT_MAX is 2147483647

https://docs.microsoft.com/en-us/cpp/c-language/cpp-integer-limits?view=msvc-160

# 乘法注意

```
interval = 29LL * 24 * 3600 * 1000;
```

不加LL会在赋值之前就溢出

# 常用运算符

## %

取模运算符“%”的作用是求两个数相除的余数。

通常用来判断一个数是否能被另一个数整除。

# 文件读写

https://www.cplusplus.com/reference/cstdio/fread/

```
 fseek (pFile , 0 , SEEK_END);
 lSize = ftell (pFile);
 rewind (pFile); //Set position of stream to the beginning
```
