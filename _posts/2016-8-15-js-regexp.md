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

> 需求 1：匹配电话号码  
> 需求 2：匹配固定邮箱

#### **regexObj.test(str)**

* **用途** - 测试正则表达式与指定字符串是否匹配
  - e.g.
    
     `/13244448888/.test('1324444888'); //false`
      
     `/13244448888/.test('13244448888'); //true`
      
     **`/13244448888/.test('x13244448888y'); //true ~不匹配为何 true~`**
      
* **锚点** - 匹配一个位置     

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
        
     **`/^13244448888$/.test('13212345678'); //false ~不能匹配任意号码~`**
          
          
* **字符类** - 匹配一类字符中的**一个**
    
  - `[abc]` : a or b or c
       
  - `[0-9]` : 一个数字 ; [^0-9] : 非数字的一个字符
       
  - `[a-z]` : 一个字母
       
  - `.` : 任一字符(换行除外)
       
  - e.g. 
       
     `/[0-9]/.test('123'); //true`
         
     `/[0-9]/.test('abc'); //false`
         
     `/[a-z]/.test('abc'); //true`
         
     `/[^0-9]/.test('abc'); //true`
         
     `/./.test('1 a#$%^&*'); //true`
         
     **`/^1[0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9]$/.test('13212345678'); //true ~我要偷懒~`**
         
* **元字符** - 具有特殊意义的字符
    
  - ^、$、\b
       
  - \d : [0-9] ; \D : [^\d]
       
  - \s : 空白符 ; \S : [^\s]
       
  - \w: [A-Za-z0-9_] ; \W : [^\w]
       
  - e.g. 
       
     `/\d/.test('123'); //true`
         
     `/\d/.test('1ab'); //true`
         
     `/\D/.test('1ab'); //true`
         
     `/\D/.test('123'); //false`
         
     **`/^1\d\d\d\d\d\d\d\d\d\d$/.test('13212345678'); //true ~再懒点好嘛~`**
         
* **量词** - 出现的次数
    
  - {m, n} : m 到 n 次
       
  - \* : {0,}
       
  - ? : {0, 1}
       
  - \+ : {1,}
       
  - e.g.
       
     `/\d*/.test('abc'); //true`
         
     `/\d+/.test('abc'); //false`
         
     `/\d+/.test('1abc'); //true`
         
     `/https?:/.test('http://yucan.win'); //true`
         
     `/https?:/.test('https://yucan.win'); //true`
         
     `/https?:/.test('httpss://yucan.win'); //false`
         
     **`/^1\d{10}&/.test('13212345678'); //true ~哇塞，好棒，成就 1 达成~`**
         
* **转义符** - 需要匹配的字符是元字符
    
  - e.g.
       
     `/http:///.test('http://yucan.win'); //what-fuck`
         
     `/http:\/\//.test('http://yucan.win'); //true`
         
     `/@gmail.com$/.test('zhyucan@gmailicom'); //true`
         
     `/@gmail\.com/.test('zhyucan@gmailicom'); //false`
     
* **多选分支** - 或

  - `/thi(c|n)k/` === `/thi[cn]k/`

  - e.g.

     `/\.(png|jpg|jpeg|gif)$/`

     **`/(.+)@(163|126|188)\.com$/.test('xyz@126.com'); //true ~只匹配网易邮箱，成就 2 达成~`**
         

> 需求 3：获取下图字符串中的每个部分  
> ![](http://o7v1v0rr4.bkt.clouddn.com/url.png)


#### **捕获**

* **用途** - 保存匹配到的字符串，日后再用

  - () : 捕获

  - (?:) : 不捕获

  - 使用
     - $1, $2, ...
     - api 参数或返回值 
      
* **str.match(regexp)**

  - 获取匹配的字符串
  
			```js
			  var url = "http://blog.163.com/album?id=1#comment";
			  var reg = /(https?:)\/\/([^\/]+)(\/[^\?]*)?(\?[^#]*)?(#.*)?/;
			  var arr = url.match(reg);
			  var protocol = arr[1];
			  var host = arr[2];
			  var pathname = arr[3];
			  var search = arr[4];
			  var hash = arr[5];
			  ```

    
    