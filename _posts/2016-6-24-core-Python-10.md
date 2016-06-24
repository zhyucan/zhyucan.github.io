---
layout: post
title: Python 核心编程 ~ 10
categories: [blog ]
tags: [Python ]
description: Python 核心编程 第十章
---

**10-4**

try-except 语句可用来检测和处理异常，try-finally 不能用来捕捉异常，无论 try 语句是否触发了异常，finally 语句都会被执行。

**10-5**

(a) 

```python
>>> if 3 < 4 then: print '3 IS less than 4!'
```
IndentationError

(b) 

```python
>>> aList = ['Hello', 'World!', 'Anyone', 'Home? ']  
>>> print 'the last string in aList is: ', aList[len(aList)]
```
IndexError

(c)

```python
>>> x
```
NameError

(d)

```python
>>> x = 4 % 0
```
ZeroDivisionError

(e)

```python
>>> import math
>>> i = math.sqrt(-1)
```
ValueError

**10-7**

（b) 可触发 statement_B 的异常