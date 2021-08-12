---
title: 读书笔记-C++Primer
date: 2021-04-15 23:59:11
categories: 
- 读书笔记
---

指针与常量：指向常量的指针/常量指针。

```c++
const int a = 0;
const int *p = &a;//指向常量的指针，指针指的对象不能做修改
int b = 0;
int *const q = &b;//常量指针,指针本身不能做修改
如果指向对象是常量，并且本身指针也要设定不能修改
const c = 0;
const int *const r = &c; 
```

引用与常量：总结一句话：条件可更加严谨，但是不能更加松懈。

```c++
常量引用可以引用普通对象，也可以引用常量
但是普通引用不能引用常量
int i = 42;
const int &r1 = i;const int &*r2 = 42;//都可以
const j = 2;
int &q = j;//错误
```

指针与常量与类型别名

```c++
类型别名：1.typedef   2.using wage = int(c++新标准)
typedef char *pstring;
const pstring r = 0;//等价于char *const r = 0,一个常量指针
const char *r = 0;//一个指向常量的指针

```

auto类型说明符：编译器可以自动判断变量类型

```c++
auto i = v1 + v2;//编译器自动判断
auto与const的关系
const int c = 42;
auto b = c;//b没有const属性
auto &b = c;//但是引用b有const属性
auto d = &c;//指向常量整形的指针
const auto d = &c;//指向常量整形的常量指针
```

字符串比较问题：等于与不等于好理解，但是大于小于有点难理解。
字符串相加问题:string s2 = s3 + "aaa"//成立   ,   string s2 = "aaa" + s3//错误，一个是字面值一个是string对象，我的理解是左边必须是对象