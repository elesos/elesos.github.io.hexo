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

http://www.cplusplus.com/reference/string/string/

https://www.geeksforgeeks.org/stdstring-class-in-c/

https://www.tutorialspoint.com/cplusplus/cpp_strings.htm
