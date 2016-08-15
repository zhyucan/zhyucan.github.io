---
layout: post
title: JavaScript 正则表达式
categories: [blog ]
tags: [NetEase-Frontend ]
description: js 正则
---

### 定义

* 描述字符串规则的表达式
    - `/pattern/attrs`
    - `new RegExp(pattern, attrs)`

### 方法

* regexObj.test(str)
    - 测试正则表达式与指定字符串是否匹配
    
      `/13244448888/.test('1324444888'); //false`
      
      `/13244448888/.test('13244448888'); //true`
    
    