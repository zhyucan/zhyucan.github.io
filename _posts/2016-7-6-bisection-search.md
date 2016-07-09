---
layout: post
title: 二分法
categories: [blog ]
tags: [Python ]
description: 二分查找的几个例子
---

**1**

x > 1，x 的平方根？

```python
x = float(raw_input('x = '))
epsilon = 0.01
low = 0.0
high = x
ans = (high + low) / 2.0

while abs(ans ** 2 - x) >= epsilon:
    if ans ** 2 > x:
        high = ans
    else:
        low = ans
    ans = (high + low) / 2.0

print ans
```

**对上面代码的优化**

```python
def findRoot1(x, power, epsilon):
    if x < 0 and power % 2 == 2: # 负数不能开偶数次方
        return None 
    low = min(-1, x)
    high = max(1, x) # 考虑到 x < 0 or |x|<1 的情况
    ans = (high + low) / 2.0
    while abs(ans ** power - x) > epsilon:
        if ans ** power < x:
            low = ans 
        else:
            high = ans
        ans = (high + low) / 2.0
    return ans
            
```




**2**

心里想一个数，我能猜到它~

```python
print "Please think of a number between 0 and 100!"
low = 0
high = 100
ans = (low + high) / 2
ch = "Enter 'h' to indicate the guess is too high. Enter 'l' to indicate the guess is too low. Enter 'c' to indicate I guessed correctly."
while True:
    print "Is your secret number " + str(ans) + '?'
    che = raw_input(ch)
    if che == 'h':
        high = ans
    elif che == 'l':
        low = ans
    elif che == 'c':
        print "Game over. Your secret number was: ", ans
        break
    else:
        print "Sorry, I did not understand your input."
    ans = (low + high) / 2
```