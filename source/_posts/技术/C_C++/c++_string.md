---
title: c++ string
tags:
  - C/C++
categories:
  - C/C++
date: 2021-07-02 07:47:31
---

```
std::string s2 (s0); //copy 
 std::string s3 (s0, 8, 3);  // 获取子串 http://www.cplusplus.com/reference/string/string/string/
 std::string s4 ("A character sequence");
 std::string s5 ("Another character sequence", 12); 
 std::string s6a (10, 'x');   //填充x
 std::string s6b (10, 42);      // 42 is the ASCII code for '*'
 std::string s7 (s0.begin(), s0.begin()+7);
 
 str.size()跟str.length()一样返回大小
str.clear();

assign
append
str.push_back('s');
insert

find_first_of
substr (pos = 0, len = npos)
compare

判断标志npos

const char* data() const;//
```



```
char greeting[] = "Hello";//C风格 #include <cstring>
strchr(s1, ch);返回指针，指向字符串 s1 中字符 ch 第一次出现的位置，如果输出会输出剩余字符串。
strstr(s1, s2);返回指针，指向字符串 s1 中字符串 s2 第一次出现的位置，如果输出会输出剩余字符串。
```



```
#include <string>
构造函数：
string s1();         // si = ""
string s2("Hello");  // s2 = "Hello"
string s3(4, 'K');  // s3 = "KKKK"
string s4("12345", 1, 3);  //s4 = "234"，从下标 1 开始，长度为 3 的子串
长度：length 和size
```

```
子串：
s1 = "this is ok";
s2 = s1.substr(2, 4);  // s2 = "is i"

```



```
查找子串和字符，返回值都是子串或字符的位置：
find：从前往后查找子串或字符出现的位置。
rfind：从后往前查找子串或字符出现的位置。
find_first_of：从前往后查找何处出现另一个字符串中包含的字符。如：s1.find_first_of("abc");  //查找s1中第一次出现"abc"中任一字符的位置
find_last_of： 从后往前查找何处出现另一个字符串中包含的字符。
find_first_not_of：从前往后查找何处出现另一个字符串中没有包含的字符。
find_last_not_of：从后往前查找何处出现另一个字符串中没有包含的字符。
```



```
if ((n = s1.find('u')) != string::npos) //查找 u 出现的位置，查不到则返回静态常量string::npos
       cout << "1) " << n << "," << s1.substr(n) << endl;

替换：replace
删除子串：erase 
插入字符串：insert
```

用算法操作string

```
#include <iostream>
#include <algorithm>
#include <string>
using namespace std;

int main(){
    string s("afgcbed");
    string::iterator p = find(s.begin(), s.end(), 'c');
    if (p!= s.end())
        cout << p - s.begin() << endl;  //输出 3
    sort(s.begin(), s.end());
    cout << s << endl;  //输出 abcdefg  
    return 0;
}
```



http://www.cplusplus.com/reference/string/string/

https://www.geeksforgeeks.org/stdstring-class-in-c/

https://www.tutorialspoint.com/cplusplus/cpp_strings.htm
