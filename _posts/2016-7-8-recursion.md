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

**5**

回文字符串

*s 是否回文？*

```python
def palin(s):
    if len(s) == 0 or len(s) == 1:
        return True
    else:
        if s[0] == s[-1]:
            s = s[1:-1]
            return palin(s)
        else:
            return False
```

```python
import string 

def palin(s):

    # 去掉字符串中的空格和符号
    def toChars(s):
        s = s.lower()
        ans = ''
        for c in s:
            if c in string.lowercase:
                ans = ans + c
        return ans
    
    def isPal(s):
        if len(s) <= 1:
            return True
        else:
            return s[0] == s[-1] and isPal(s[1:-1]) # 1行代码抵我5行...
            
    return isPal(toChars(s))
```

---

*s1 & s2 互为回文串？*





**6**

字符串长度

```python
def lenRecur(aStr):
    if aStr == '':
        return 0
    return 1 + lenRecur(aStr[1:])
```

**7**

字母是否存在于，一个「元素按字母顺序排列」的字符串中

```python
def isIn(char, aStr):
    if aStr == '':
        return False
    if len(aStr) == 1:
        return aStr == char
    
    minum = len(aStr) / 2
    micha = aStr[minum]
    
    if micha == char:
        return True
    elif micha > char:
        return isIn(char, aStr[:minum])
    else:
        return isIn(char, aStr[minum:])
    return False
```