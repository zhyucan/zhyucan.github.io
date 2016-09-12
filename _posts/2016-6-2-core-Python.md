---
layout: post
title: Python 核心编程
categories: [blog ]
tags: [Python ]
description: Python 核心编程
---

### 二

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

### 三

**3.1**

Python 是动态类型编程语言，变量名和变量类型会自动声明。

**3.2**

> 因为python的type checking是在运行时发生的，不在编译时发生，所以在代码里写变量的类型是多余的。

**3.3**

变量名 \_xxx_ 对 Python 来说有特殊意义，是內建标识符所使用的符号，对普通变量应避免这种命名风格。

**3.4**

可以用「；」实现，但为了代码可读性，不提倡。

**3.5**

可以，通过使用「'''」「()[]{}」「\」 

**3.6**

(a) 1, 2, 3

(b) 3, 1, 2

**3.7**

不合法的标识符：   
40XL; $aving$; big-daddy; 2hot2touch; 0x40L; thisIsn'tAVar; counter-1

关键字：  
print; if

### 四

**4-1**

 与所有 Python 对象有关的三个属性：
   
 *身份*：对象的内存地址，可由 id() 得到  
 *类型*：对象的类型决定了该对象可以保存什么类型的值，可以进行什么操作，以及遵循什么样的规则  
 *值*：对象表达的数据项
 
 **4-2**
 
 不可更改指的是，对象的值改变时，其身份不变。  
 列表，字典可更改；数字，字符串，元组不可更改。
 
 **4-3**
 
 字符串，元组，列表可按照顺序访问容器内的元素。  
 字典内的元素无序，根据哈希值对访问。
 
 **4-4**
 
 type() 返回任意 Python 对象的类型
 
 **4-5**
 
 repr() 等价于 ``  
 str() 函数得到的字符串是给人看的，可读性好  
 repr() 函数得到的字符串是给python看的，可以通过求值运算 eval() 重新获得该对象
 
 **4-6**
 
 type(a) == type(b) 用来比较 a 对象和 b 对象是否同一类型  
 type(a) is type(b) 用来比较 a 对象和 b 对象的身份  
 函数 isinstance() 用来更简便易读地判断对象类型
 
 **4-7**
 
 
```python
>>> import types
>>> dir(types)
['BooleanType', 'BufferType', 'BuiltinFunctionType', 'BuiltinMethodType', 'ClassType', 'CodeType', 'ComplexType', 'DictProxyType', 'DictType', 'DictionaryType', 'EllipsisType', 'FileType', 'FloatType', 'FrameType', 'FunctionType', 'GeneratorType', 'GetSetDescriptorType', 'InstanceType', 'IntType', 'LambdaType', 'ListType', 'LongType', 'MemberDescriptorType', 'MethodType', 'ModuleType', 'NoneType', 'NotImplementedType', 'ObjectType', 'SliceType', 'StringType', 'StringTypes', 'TracebackType', 'TupleType', 'TypeType', 'UnboundMethodType', 'UnicodeType', 'XRangeType', '__all__', '__builtins__', '__doc__', '__file__', '__name__', '__package__']
```


 **4-8**
 
 列表和元组都按按索引顺序访问元素，元组是只读的列表
 
 **4-9**
 
```python
>>> a = 10
>>> b = 10
>>> c = 100
>>> d = 100
>>> e = 10.0
>>> f = 10.0
>>> 
>>> a is b
True
>>> c is d
True
>>> e is f
False
```
a 和 b，c 和 d，e 和 f 都应指向不同身份的对象，出现指向相同对象的假象的原因是，python 会缓存一定整型范围的整型对象

### 五

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

### 六

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

### 七

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

### 八

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

### 十

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

### 十一

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

