---
layout: post
title: Python 核心编程 ~ 2
categories: [blog ]
tags: [Python ]
description: Python 核心编程 第二章
---

### *直接写题*  

**2-1**

```python
>>> a = 'a'
>>> a
'a'
>>> print a
a

>>> print 'what is a: %s' % a
what is a: a
```

**2-2**

脚本中运行，'1 + 2 * 4' 改为 'print (1 + 2 * 4)'  

**2-3**

```python
>>> 42 + 24
66
>>> 42 - 24
18
>>> 42 * 24
1008
>>> 42 / 24
1
>>> 42 % 24
18
>>> 42 ** 24
907784931546351634835748413459499319296L
```

**2-4**

(a) 
 
```python
name = raw_input('What\'s your name?')
print name
```
(b)
  
```python
age = int(raw_input('How old are you?'))
print age
```

**2-5**

(a)

```python
>>> a = 0
>>> while a <= 10:
...     print a,
...     a += 1
... 
```
(b)  

```python
>>> for i in range(11):
...     print i,
... 
```

**2-6**

```python
a = float(raw_input('input a number: '))
if a > 0:
    print 'a is positive number'
elif a < 0:
    print 'a is negative number'
else:
    print 'a = 0'
```

**2-7**

```python
a = raw_input('input a string: ')
x = 0
while x < len(a):
    print a[x]
    x += 1
```

```python
a = raw_input('input a string: ')
for i in range(len(a)):
    print a[i]
```
---
```python
a = raw_input('input a string: ')
x = 0
while True:
    try:
        print a[x],
        x += 1
    except IndexError:
        break
print
```

```python
a = raw_input('input a string: ')
for i in a:
    print i,
```


**2-8**

```python
a = input('input a list: ')
i = 0
x = len(a)
while x > 0:
    x = x - 1  
    i = i + a[x]
print i
```

```python
a = input('input a list: ')
x = 0
for i in range(len(a)):
    x = x + a[i]
print x
```

**2-9**

```python
a = input('input a list: ')
x = 0
for i in range(len(a)):
    x = x + a[i]
print float(x) / float(len(a))
```

**2-10**

```python
x = float(raw_input('input a number between 1 and 100: '))
while True:
    if x >= 1:
        if x <= 100:
            print 'Good~'
            break
        else:
            print 'Bad~'
            x = float(raw_input('re-input a number between 1 and 100: '))
    else:
        print 'Bad~'
        x = float(raw_input('re-input a number between 1 and 100: '))
```
---
```python
while True:
    x = float(raw_input('input a number between 1 and 100: '))
    if 1 <= x <= 100:
        print 'Good~'
        break
```