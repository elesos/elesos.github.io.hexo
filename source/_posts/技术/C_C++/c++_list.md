---
title: c++ list
tags:
  - C/C++
categories:
  - C/C++
date: 2021-07-02 07:50:13
---

```
std::list<int> first;                                // empty list of ints
 std::list<int> second (4,100);                       // four ints with value 100
 std::list<int> third (second.begin(),second.end());  // iterating through second
 std::list<int> fourth (third);                       // a copy of third
 
 
 mylist.push_back(77);
mylist.front()


std::list< std::pair<int,char> > mylist;
 mylist.emplace_front(10,'a');
 
  mylist.emplace_back(10,'a');
 mylist.emplace_back(20,'b');
 
 first.assign (7,100);                      // 7 ints with value 100
 second.assign (first.begin(),first.end()); // a copy of first
 
 
 std::list< std::pair<int,char> > mylist;
 mylist.emplace ( mylist.begin(), 100, 'x' );
 
 erase根据位置删除
remove根据值删除
double mydoubles[]={ 12.15,  2.72, 73.0,  12.77,  3.14,  12.77, 73.35, 72.25, 15.3,  72.25 };
 std::list<double> mylist (mydoubles,mydoubles+10);
```

https://www.cplusplus.com/reference/list/list/
