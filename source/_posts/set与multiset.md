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

这是，你会碰到一个生词：insert

insert是插入的意思：
![insert.jpg](https://wailian.work/images/2018/07/20/insert.jpg)
![insert2.jpg](https://wailian.work/images/2018/07/20/insert2.jpg)
![insert3.jpg](https://wailian.work/images/2018/07/20/insert3.jpg)
![8f43cffdafba277b.jpg](https://wailian.work/images/2018/07/20/8f43cffdafba277b.jpg)

不是开玩笑！记住这个单词！如何插入到这个容器中就是只要只用（容器名称）.insert(你插入的内容）;就可以了。

这样你就学会了插入内容到容器中。那么，怎样输出呢？就像你妈问你1+1等于几，你说我知道，但我不回答。那就总少不了一阵打把，不要啊!

用人说，这不是很简单吗？向那个叫string的东西一样操作不久搞定了吗，何必这么复杂干什么？

我说，那你就试试呗O(∩_∩)O

这是，你的编译器会无情的告诉你一个错误报告：

![a429743b4751a02c.jpg](https://wailian.work/images/2018/07/20/a429743b4751a02c.jpg)

那么，我们怎么实现输出里面所有的内容呢？

这是，我们就要遇见这么一行代码
```
multiset<int>::iterator it;
```
那么，这行代码的作用是什么呢？

其实，这行代码的意思是定义一个multiset类型，里面装int的迭（die）代器，名称为it

那么，我们定义了迭代器，那么，我们怎么去使用它呢？

话不多说，先上代码：
```
#include<iostream>
#include<set> //引入set库 
using namespace std;
int main() {
	multiset<int> s;  //定义包含整数的multiset 
	multiset<int>::iterator it;	//定义迭代器 
	s.insert(8);	//插入元素 
	s.insert(6);
	s.insert(6);
	s.insert(6);  
	//循环输出set中所有元素
	for(it=s.begin();it!=s.end();it++)	 
		cout<<*it<<endl;
	return 0;
}
```

定义迭代器知道了，那么，我们现在来讲讲如何输出容器中的元素输出来。

for语句第一行，先将it这个迭代器指向容器的开始位置，当他是结束的位置时停止执行，it并不是it的数值+1，而是将指针指向下一个位置

输出*it （这里解释下** 的含义，** 是指针的含义，也就是说是说是指向这块内存中所对应的内存中所含的数值）

那么输出结果就是：
*output*
```
6
6
6
8
```
这就是输出的结果。

明天更新set的插入输出

暂时添加下做题内容
一个为flash，一个为html5
    <div id="page1"></div>
    <div id="page2"></div>
    <script>
          $("#page1").load("https://likecoding.cf/ispring/set1/index.html");
          $("#page2").load("https://likecoding.cf/ispring/set1/flash.html");
    </script>
