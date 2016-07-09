---
layout: post
title: 递归
categories: [blog ]
tags: [Python ]
description: 递归的几个例子
---

**1**

a * b

```python
def recurMul(a, b):
    if b == 1:
        return a
    else:
        return a + recurMul(a, b-1)  

# b = 1, a * b = a
# recurMul(a, b) = a * b = a + (a * (b-1)) = a + recurMul(a, b-1)
```

**2**

a ** b

```python
def recurPower(a, b):
    if b == 0:
        return 1
    else:
        return a * recurPower(a, b-1)
        
# b = 0, a ** b = 1; b = 1, a ** b == a
# recurPower(a, b) = a ** b = a * (a ** (b-1)) = a * recurPower(a, b-1) 
```

**3**

n!

```python
def recurFac(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * recurFac(n-1)
        
# n = 0, n! = 1; n = 1, n! = 1
# recurFac(n) = n! = n * (n-1)! = n * recurFac(n-1)
```

**4**

斐波拉契数列

```python
def Fibo(n):
    assert type(n) == int and n >= 0
    if n == 0 or n == 1:
        return 1
    else:
        return Fibo(n-1) + Fibo(n-2)
        
# n = 1, 1; n = 2, 1
# Fibo(n) = (n-1) + (n-2) = Fibo(n-1) + Fibo(n-2)
```


