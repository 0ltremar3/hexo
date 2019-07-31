---
title: C++基本用法
date: 2018-08-26 09:41:10
tags:
- 语言
- c++
---


[TOC]
<!--more-->

--------------------------------
## 头文件
```cpp
#include <iostream>
using namespace std;
```
--------------------------------
## 输入输出
### cin
- 可同时输入多个变量
```cpp
cin >> n >> db >> c >> str;
```
- 输入一整行数组要用getline
```cpp
//字符型数组
char str[10];
cin.getline(str,100);
//string容器
string str;
getline(cin,str);
```
- cin的结束标志:
    读入空格和回车；
    while(cin >> x)时，ctrl+z退出循环。
### cout


- 可同时输出多个变量
```cpp
cout << n << db << c << str;
```
- 加空格、字符用" "
```cpp
cout  << n << " " << db;
```
- 换行用"\n"或endl
```cpp
cout  << n << "\n" << db << endl;
```
### 注意事项
考试除非必要(如使用string时)，不建议用cin和cout，耗时过长，性能比较差。

---------------
## STL
### vector
#### 定义
- 头文件
```cpp
#include <vector>
using namespace std;
```
- 功能
 类似变长数组,大小随输入变化。
- 声明
```cpp
vector <typeName> name;
//具体例子
vector <int> vi;
vector <int> vi(100);//指定vi大小为100
```
- 类似二维数组的形式
`vector <vector<typeName> > name;//注意> >之间需要加空格，否则会是别的含意`
- vector数组
`vector <int> vi[100];//vi[0]~vi[99]每一个都是vector容器`
#### 元素访问
1.下标访问
`vi[index];`
2.迭代器访问
```cpp
vector <typeName>::iterator it;
it = vi.begin();//取首元素地址，访问vi[0]
it = vi.begin + 3;//访问vi[3]
for(it = vi.begin();it != vi.end();it++)//遍历
{···}
```
#### 常用函数
1. size();


```cpp
vector <int> vi;
cout << vi.size();//获得vi的大小
```
-------------------------


### string
#### 定义
- 头文件
```cpp
#include <string>
using namespace std;
```
#### 元素访问
1. 下标访问
像访问字符数组一样。
2. 迭代器访问
`string::iterator it;                                                 `
3. 如果要输入/输出整个字符串，只能用cin和cout.
#### 常用函数
1. compare operator
直接用>,=,<来按字典序比较字符串。
2. perator+=
字符串直接相加减

--------------------------


### set
#### 定义
- 头文件
```cpp
#include <set>
using namespace std;
```
- 功能
 set（集合），是一个内部自动有序且不含重复元素的容器。
- 声明
`set<typename> name;`
#### 元素访问
只能通过迭代器(iterator)访问：


```cpp
set<typename>::iterator it;`
只能按如下方式枚举：


​```cpp
set<int> st;
st.insert(5);
st.insert(1);
st.insert(3);
for(set<int>::iterator it=st.begin();it!=st.end();it++){
 printf("%d",*it);
}
```
输出结果：
 `1 3 5`
#### 常用函数


1. insert()
2. find()
3. erase()
4. size()
5. clear()

--------------------------
### map
#### 定义
-头文件
```cpp
#include <map>
using namespace std;
```
- 声明
  ` map<typename1,typename2> name;//1为键，2为值`
- 功能
下标和对应值的类型可以不同，如map['a']=1。
#### 元素访问
1. 下标
`map['c']=3;`
2. 迭代器
`it->first`访问下标,`it->second`访问值。
#### 常用函数

---------------------------