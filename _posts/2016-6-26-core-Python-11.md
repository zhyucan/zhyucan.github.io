---
layout: post
title: Python 核心编程 ~ 11
categories: [blog ]
tags: [Python ]
description: Python 核心编程 第十一章
---

**11-1**

|Input |countToFour1|countToFour2|countToFour3|
|:---:|:---:|:---:|:---:|
|2|ERROR|2 3 4|2 3 4|
|4|ERROR|4|4|
|5|ERROR|NONE|NONE|
|(nothing)|0 1 2 3 4|ERROR|1 2 3 4|

**11-3**

(a)

```python
def max2(x, y):
	if x > y:
		return x
	else:
		return y

def min2(x, y):
	if x < y:
		return x
	else:
		return y
```

**11-7**

```python
map(lambda x, y: (x, y), [1, 2, 3], ['abc', 'def', 'ghi'])

zip([1, 2, 3], ['abc', 'def', 'ghi'])
```

**11-8**

```python
filter(lambda n: ((n % 4 == 0 and n % 100 != 0) or n % 400 == 0), range(1, 2051))

[n for n in range(1, 2051) if (n % 4 == 0 and n % 100 != 0) or n % 400 == 0]
```

**11-9**

```python
list = [1, 54, 5, 6, 98, 54, 20]
print float(reduce(lambda x, y: x + y, list) / len(list))
```

**11-13**

(a)

```python
def mult(x, y):
	return x * y
```

(b)

```python
def mult(x, y):
	return x * y

n = int(raw_input('n = ')) 
print reduce(mult, range(1, n+1))
```

(c)

```python
n = int(raw_input('n = ')) 
print reduce(lambda x, y: x * y, range(1, n+1))
```

**11-14**

```python
def fibonacci(n):
	if n == 1 or n == 2:
		return 1

	return fibonacci(n-1) + fibonacci(n-2)

print fibonacci(int(raw_input('n = ')))
```
