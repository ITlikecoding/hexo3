---
title: set与multiset
date: 2018-07-06 10:50:10
tags:
---


# c++标准stl之set与multiset

今天呢，likecoding组和大家一起分享set和multiset

set和multiset以及后面我们索要介绍的map和multimap都是容器，而set和multiset可以很简单的进行插入、删除、查找、计数、去重、排序、找最小最大。更重要的雨点是这个容器是十分的快速的，后面我们会讲到他的优点

首先，set和multiset有什么区别呢？

multiset 容器允许元素的重复出现，而set 保证元素唯一性，不允许元素重复，也就是说，插入三个三，multiset中里有三个3，而set中只有3。

那么，我么来讲一下set如何插入

先上代码：
```
#include<iostream>
#include<set> //引入set库 
using namespace std;
int main() {
	multiset<int> s;  //定义包含整数的multiset 
	s.insert(8);	//插入元素 
	s.insert(6);
	s.insert(6);
	s.insert(6);  
	return 0;
}
```
