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
       - e.g.
    
         `/13244448888/.test('1324444888'); //false`
      
         `/13244448888/.test('13244448888'); //true`
      
         `/13244448888/.test('x13244448888y'); //true ?`
      
    - 锚点 - 匹配一个位置     

        - ^ : 起始位置
            
          `/^http:/.test('http://yucan.win'); //ture`
              
          `/^http:/.test('ahttp://yucan.win'); //false`
              
          `/^http:/.test('https://yucan.win'); //false`
              
        - $ : 结尾位置
            
          `/\.jpg$/.test('1.jpg'); //true`
              
          `/\.jpg$/.test('1.png'); //false`
              
        - \b : 单词边界
            
          `/\bis\b/.test('this'); //false`
              
          `/\bis\b/.test('this is dom'); //true`
        
        - e.g.
          
          `/^13244448888$/.test('x13244448888y'); //false`
      
          `/^13244448888$/.test('13244448888'); //true`
        
          `/^13244448888$/.test('13212345678'); //false ?`
          
          
    - 字符类 - 匹配一类字符中的**一个**
    
       - `[abc]` : a or b or c
       
       - `[0-9]` : 一个数字 ; [^0-9] : 非数字的一个字符
       
       - `[a-z]` : 一个字母
       
       - `.` : 任一字符(换行除外)

    
    