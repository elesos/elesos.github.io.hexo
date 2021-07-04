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

# Std::atomic 用法

C++中对共享数据的存取在并发条件下可能会引起data race的undifined行为，需要限制并发程序以某种特定的顺序执行，有两种方式：使用mutex保护共享数据，原子操作

原子类型操作要不一步完成，要么不做，不可能出现操作一半被切换CPU，这样防止由于多线程指令交叉执行带来的可能错误。非原子操作下，某个线程可能看见的是一个其它线程操作未完成的数据。

atomic 原子操作支持bool、int、char等数据类型

```
std::atomic <bool>   atomic_bool_test1(false);
a.load() 返回数值a的copy
```

# Std::async

Call function asynchronously

https://www.cplusplus.com/reference/future/async/

The value returned by fn can be accessed through the future object returned (by calling its member future::get).

# Static 关键字的作用

\1. 全局静态变量

在全局变量前加上关键字static，全局变量就定义成一个全局静态变量.

静态存储区，在整个程序运行期间一直存在。

初始化：未经初始化的全局静态变量会被自动初始化为0（自动对象的值是任意的，除非被显式初始化）；

作用域：全局静态变量在声明他的文件之外是不可见的，准确地说是从定义处开始，到本文件结尾。

\2. 局部静态变量

在局部变量前加上关键字static，局部变量就成为一个局部静态变量。

内存中的位置：静态存储区

初始化：未经初始化的局部静态变量会被自动初始化为0（自动对象的值是任意的，除非被显式初始化）；

作用域：作用域仍为局部作用域，当定义它的函数或者语句块结束的时候，作用域结束。但是当局部静态变量离开作用域后，并没有销毁，而是仍然驻留在内存当中，只不过我们不能再对它进行访问，直到该函数再次被调用，并且值不变；

\3. 静态函数

函数的定义和声明默认情况下都是extern的，但静态函数只是在声明他的文件当中可见，不能被其他文件所用。

函数的实现使用static修饰，那么这个函数只可在本cpp内使用，不会同其他cpp中的同名函数引起冲突；

注：不要在头文件中声明static的全局函数，不要在cpp内声明非static的全局函数，如果你要在多个cpp中复用该函数，就把它的声明提到头文件里去，否则cpp内部声明需加上static修饰；

\4. 类的静态成员

在类中，静态成员可以实现多个对象之间的数据共享，并且使用静态数据成员还不会破坏隐藏的原则，即保证了安全性。因此，静态成员是类的所有对象中共享的成员，而不是某个对象的成员。对多个对象来说，静态数据成员只存储一处，供所有对象共用

\5. 类的静态函数

静态成员函数和静态数据成员一样，它们都属于类的静态成员，它们都不是对象成员。因此，对静态成员的引用不需要用对象名。

在静态成员函数的实现中不能直接引用类中说明的非静态成员，可以引用类中说明的静态成员（这点非常重要）。如果静态成员函数中要引用非静态成员时，可通过对象来引用。

# Sprintf

```
int sprintf ( char * str, const char * format, ... );
```

stored C string in the buffer pointed by str.

On success, the total number of characters written is returned. 否则返回负数

https://www.cplusplus.com/reference/cstdio/sprintf/

# Std::bind

```
bind (Fn&& fn, Args&&... args);
```

Returns a function object based on fn, but with its arguments bound to args.

```
std::bind(&callback);
std::bind(&aClass::callback, this);
std::bind(&aClass::callback, this， info);
```

https://www.cplusplus.com/reference/functional/bind/

```
using namespace std::placeholders;    // adds visibility of _1, _2, _3  占位
```

# Std::condition variable

https://www.cplusplus.com/reference/condition_variable/condition_variable/

block the calling thread until notified to resume.

It uses a unique_lock to lock the thread when one of its wait functions is called. The thread remains blocked until woken up by another thread that calls a notification function on the same condition_variable object.

```
wait  The execution of the current thread  is blocked until notified. 第2个参数：A callable object or function that takes no arguments and returns a value that can be evaluated as a bool. This is called repeatedly until it evaluates to true.
notify_one
notify_all
```

# Std::remove

Remove value from range

https://www.cplusplus.com/reference/algorithm/remove/
