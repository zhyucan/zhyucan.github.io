---
layout: post
title: Python 核心编程 ~ 7
categories: [blog ]
tags: [Python ]
description: Python 核心编程 第七章
---

**7-1**

s.union(t)

**7-2**

```python
>>> s = {[1, 2]: 'love'}
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
>>> s = {{1: 'a', 2: 'b'}}
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'dict'
>>> s = {(1, 2)}
>>> s
set([(1, 2)])
```
键必须是可哈希的；像列表和字典这样的不可变类型，由于它们是不可哈希的，所以不能作为键。

**7-3**

```python
>>> dic = {'a':31, 'bc':5, 'c':3, 'asd':4, '33':56, 'd':0}
>>>
>>> print sorted(dic.keys())
['33', 'a', 'asd', 'bc', 'c', 'd']
>>> print sorted(dic.items())
[('33', 56), ('a', 31), ('asd', 4), ('bc', 5), ('c', 3), ('d', 0)]
```

**7-4**

```python
l1 = [1, 2, 3]
l2 = ['abc', 'def', 'ghi']

dic = {}

for i in range(len(l1)):	
	dic.setdefault(l1[i], l2[i])

print dic
```

**7-7**

```python
dict1 = {'name': 'earth', 'port': 80}
dict2 = {}

key_list = dict1.keys()

for i in range(len(dict1)):
	dict2.setdefault(dict1[key_list[i]], key_list[i])

print dict2
```
