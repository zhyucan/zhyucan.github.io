---
layout: post
title: Python 核心编程 ~ 6
categories: [blog ]
tags: [Python ]
description: Python 核心编程 第六章
---

**6-1**

in & not in

**6-2**

```python
#!usr/bin/env python

import string
import keyword

alphas = string.letters + '_'
nums = string.digits

print 'Welcome to the Identifier Checker v1.0'
print 'Testees must be at least 2 chars long.'
myInput = raw_input('Identifier to test? ')

if myInput in keyword.kwlist:
	print "myInput is keyword"


if len(myInput) == 1:

	if myInput not in alphas:
		print 'invalid: first symbol must be alphabetic'
	else:
		print "okey as an identifier"

if len(myInput) > 1:

	if myInput[0] not in alphas:
		print 'invalid: first symbol must be alphabetic'

	else:
		for otherChar in myInput[1:]:

			if otherChar not in alphas + nums:
				print '''invalid: remaining
				  symbols must be alphanumeric'''
				break
		else:
			print "okey as an identifier"
```

**6-3**

```python
l = [num1, num2, num3, num4, num5]
print sorted(l)
```

**6-4**

```python
a = input('input a list: ')

l = []

for i in a:
    if 90 < i <= 100:
        l.append([i, 'A'])
    elif 80 < i <= 90:
        l.append([i, 'B'])
    elif 70 < i <= 80:
        l.append([i, 'C'])
    elif 60 <= i <= 70:
        l.append([i, 'D'])
    else:
        l.append([i, 'E'])


x = 0
for i in range(len(a)):
    x = x + a[i]
l.append(float(x) / float(len(a)))

print l
```

**6-6**

```python
st = raw_input('input a string: ')
print st[1:-1]
```

**6-7**

```python
# coding:utf-8 

#!/usr/bin/env/python

# 输入一个数的字符串显示
num_str = raw_input('Enter a number: ')

# 把字符串显示的数转为整数
num_num = int(num_str)

# 构建一个列表
fac_list = range(1, num_num + 1)
print "BEFORE:", repr(fac_list)

# 计数器 i
i = 0

# 删除列表首尾数
while i < len(fac_list):

	# 取余		
	if num_num % fac_list[i] == 0 and (i == 0 or (i == len(fac_list)-1)):
		del fac_list[i]

	# 计数器
	i = i + 1

# 变后列表
print "AFTER:", repr(fac_list)
```
**6-8**

```python
dict1 = {'1':'one', '2':'two', '3':'three', '4':'four',
         '5':'five', '6':'six', '7':'seven', '8':'eight',
         '9':'nine', '0':''}
dict2 = {'1':'ten', '2':'twenty', '3':'thirty', '4':'fourty',
         '5':'fifty', '6':'sixty', '7':'seventy', '8':'eighty',
         '9':'ninety', '0':''}
dict3 = {'1':'one hundred', '2':'two hundres', '3':'three hundred',
         '4':'four hundred', '5':'five hundred', '6':'six hundred',
         '7':'seven hundred', '8':'eight hundred', '9':'nine hundred',
         '0':''}

dictAll = {1:dict1, 2:dict2, 3:dict3}

def fun1(strNum):
    if int(strNum) > 1000 or int(strNum) < 0:
        return 'error number'
    length = len(strNum)
    strTemp = ''
    if length == 4:
        strTemp = 'one thousand'
        return strTemp
    else:
        for i in range(length):
            strTemp += dictAll[length - i][strNum[i]] + ' '
        return strTemp

if __name__ == '__main__':
	while True:
		strNum = raw_input('please enter the num(q to quit): ')
		if strNum.lower() == 'q':
			break
		print 'the num is: %s' % (fun1(strNum))
```

