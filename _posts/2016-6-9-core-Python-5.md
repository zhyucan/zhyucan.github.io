---
layout: post
title: Python 核心编程 ~ 5
categories: [blog ]
tags: [Python ]
description: Python 核心编程 第五章
---

**5-1**

Python 里，长整型是标准整型的超集，标准整型等价于 C 的（有符号）长整型。

**5-2**

(a)  
 
```python
def che(a, b):
    return a * b
```
(b)

```python
print che(5, 8)
```
**5-3**

```python
score = int(raw_input('input a score: '))

if 90 < score <= 100:
    print 'A'
elif 80 < score <= 89:
    print 'B'
elif 70 < score <= 79:
    print 'C'
elif 60 < score <= 69:
    print 'D'
else:
    print 'F'
```

---

```python
mark_value = {10:"A",9:"A",8:"B",7:"C",6:"D",
              5:"F",4:"F",3:"F",2:"F",1:"F",0:"F"}
while True:
    num1 = raw_input("please enter your mark(-1 to quit)")
    if num1 == "-1":
        break
    print "your mark is:%s" % mark_value[int(num1) / 10]
```

**5-4**

```python
year = int(raw_input('input a year: '))

if (year % 4 == 0 and year % 100 != 0) or year % 400 == 0:
    print "%d is a leap year" % year
else:
    print "%d is not a leap year" % year
```

**5-8**

(a)

```python
def areavol(l):
    return (l * l, l ** 3)
```

(b)

```python
def areacol(r):
    import math
    return (math.pi * r * r, float(4/3) * math.pi * (r ** 3))
```

**5-9**

(a)  
017（八进制）转为 15（十进制）  
032（八进制）转为 26（十进制）

**5-10**

```python
def convet(f):
    return (f - 32) * float(5./9) 
```

**5-11**

(a)

```python
for i in range(0, 21):
    if i % 2 == 0:
        print i
```
(b)

```python
for i in range(0, 21):
    if i % 2 != 0:
        print i
```

(c)  
% 2

(d)

```python
a = int(raw_input('a = '))
b = int(raw_input('b = '))

if a % b == 0 or b % a == 0:
    print True
else:
    print False
```

**5-13**

```python
def contime(h, m):
    return 60 * h + m
```
**5-15**

```python
a = int(raw_input('a = '))
b = int(raw_input('b = '))

for i in range(min(a,b), 0, -1):
    if a % i == 0 and b % i == 0:
        print i
        break

x = max(a, b)       
while x % a != 0 or x % b != 0:
    x = x + 1
print x        
```

**5-16**

```python
open = float(raw_input("Enter opening balance: "))
pay = float(raw_input("Enter monthly payment: "))

print "Pymt#" + "     " + "Amount Paid" + "     " + "Remaining Balance"
print "-----" + "     " + "-----" + "     " + "-----"

for i in range(0, 8):
    print i + "     " +   
```


