---
layout: post
title: Python 核心编程 ~ 8
categories: [blog ]
tags: [Python ]
description: Python 核心编程 第八章
---

**8-1**

都不会被执行

**8-2**

```python
def jishu(f, t, i):
	print range(f, t+1, i)

print jishu(2, 26, 4)
```

**8-3**

```python
>>> range(0, 10)
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>>
>>> range(3, 19, 3)
[3, 6, 9, 12, 15, 18]
>>>
>>> range(-20, 861, 220)
[-20, 200, 420, 640, 860]
```

**8-4**

```python
def isprime(num):
	count = num / 2
	for i in range(2, count+1):
		if num % i == 0:
			return False
			break
	else:
		return True

print isprime(int(raw_input('number is ')))
```

**8-5**

```python
def getfactors(num):
	l = []
	count = num / 2
	for i in range(1, count+1):
		if num % i == 0:
			l.append(i)
	l.append(num)
	return l

print getfactors(int(raw_input('number is '))) 
```

**8-7**

```python
def isperfect(num):
	count = num / 2
	s = 0

	for i in range(1, count+1):
		if num % i == 0:
			s += i
			
	if s == num:
		return 1
	else:
		return 0

print isperfect(int(raw_input('number = ')))  
```

**8-8**

```python
def factorial(num):
	N = 1
	for i in range(1, num+1):
		N *= i
	return N

print factorial(int(raw_input('num = '))) 
```

**8-9**

```python
def fibonacci(n):
	if n == 1 or n == 2:
		return 1

	return fibonacci(n-1) + fibonacci(n-2)

print fibonacci(int(raw_input('n = '))) 
```


















