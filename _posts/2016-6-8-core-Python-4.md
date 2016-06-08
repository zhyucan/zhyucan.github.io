---
layout: post
title: Python 核心编程 ~ 4
categories: [blog ]
tags: [Python ]
description: Python 核心编程 第四章
---

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


