---
title: c++ map pair
tags:
  - C/C++
categories:
  - C/C++
date: 2021-07-02 08:06:59
---

# pair

```
#include <utility>      // std::pair, std::make_pair

pair <string,double> product1;                     // default constructor
pair <string,double> product2 ("tomatoes",2.30);   // value init
pair <string,double> product3 (product2);          // copy constructor

product1 = make_pair(string("lightbulbs"), 0.99);   // using make_pair (move)
g2 = make_pair(1, 'a');

product2.first = "shoes";                //赋值
product2.second = 39.90;        
```

https://www.cplusplus.com/reference/utility/pair/pair/

https://www.geeksforgeeks.org/pair-in-cpp-stl/

# map

map are slower than unordered_map containers to access individual elements by their key, but they allow the direct iteration迭代 on subsets based on their order.

## 特性

元素排了序

## 操作

```
mymap.insert ( pair<char,int>('a',100) );  //map_name.insert({key, element})
mymap.insert (it, pair<char,int>('b',300));
anothermap.insert(mymap.begin(),mymap.find('c'));  

map<char,int> mymap;
mymap.emplace('x',100);  //map_name.emplace(key, element)
for (auto &x: mymap)
   cout << " [" << x.first << ':' << x.second << ']';
   
   
 find
 
 删除
 mymap.erase (it);  
mymap.erase ('c');                  // erasing by key
mymap.erase ( it, mymap.end() );    // erasing by range

clear
count(key) //Count elements with a specific key


 
```

## 对比



all containers (vector, stack, queue, set, map, etc) support both insert and emplace operations.

emplace不copy of object.

```
ms.insert(make_pair('b', 25)); 
```

https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/

https://www.cplusplus.com/reference/map/map/
