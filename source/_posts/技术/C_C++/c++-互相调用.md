---
title: c++ 互相调用
tags:
  - C/C++
categories:
  - C/C++
date: 2021-07-02 08:13:01
---

# C++调C

```
#ifdef __cplusplus
extern "C" {               // 告诉编译器下列代码要以C链接约定的模式进行链接
#endif
 
//c头文件或函数
 
#ifdef __cplusplus
}
#endif
```

# C++中调用C库

做一个C动态库：

```
#include <stdio.h>
void hello(){  
 
}
gcc -shared -fPIC -o libhello.so hello.c
```

C++程序调用它：

```
g++ test.cpp  -lhello
```

# C中调用C++库

将 C++ 函数声明为extern "C"（在你的 C++ 代码里做这个声明）

```
#include <iostream>
void world()
{  

  std::cout << "world" << std::endl;
}
```

编译并copy到系统库目录下:

```
g++ -shared -fPIC -o libworld.so world.cpp 
cp libworld.so /lib/
```

做一个中间接口库，对C++库进行二次封装：

```
// mid.cpp
#include <iostream>
void world();
 
#ifdef __cplusplus
extern "C" {  // 即使这是一个C++程序，下列这个函数的实现也要以C约定的风格！
#endif  
 
void m_world()  
{    

  world();  

}
 

#ifdef __cplusplus
}
#endif
```

其中m_world为libworld库中world方法的二次封装， 编译并copy到系统库目录下:

```
g++ -shared  -fPIC -o libmid.so mid.cpp -lworld
cp libmid.so /lib/
```

在C程序中通过链接**二次接口库**去调用C++库：

```
#include <stdio.h>
int main()
{
  m_world(); 
  return 0;
}

gcc test.c -lmid -o test
```

注：对于C++库中含有类的，可以在二次接口函数中生成临时对象来调用对应的功能函数。

http://www.cppblog.com/wolf/articles/77828.html

