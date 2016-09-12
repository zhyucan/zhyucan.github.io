---
layout: post
title: JavaScript 正则表达式
categories: [blog ]
tags: [Front-end ]
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
         
     **`/^1\d{10}$/.test('13212345678'); //true ~哇塞，好棒，成就 1 达成~`**
         
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
         

> ![](http://o7v1v0rr4.bkt.clouddn.com/url.png)
> 需求 3：捕获上图字符串中的每个部分  
> 需求 4：替换字符串的某部分 e.g : "The price of tomato is 5." → "The price of tomato is 5.00."


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
var reg = /^(https?:)\/\/([^\/]+)(\/[^\?]*)?(\?[^#]*)?(#.*)?$/;
var arr = url.match(reg);

/*
上面的正则表达式可简写为：
/(https?:)\/\/([^\/]+)([^\?]*)([^#]*)(.*)/
*/

var protocol = arr[1];
var host = arr[2];
var pathname = arr[3];
var search = arr[4];
var hash = arr[5];

/*
reg = /(http: or https:)//("至少1个 非/")("/" + "任意个 非?")可有可无("?" + "任意个 非#")可有可无("#" + "任意个 任意字符")可有可无/;
> "http://blog.163.com/album?id=1#comment".match(/(https?:)\/\/([^\/]+)(\/[^\?]*)?(\?[^#]*)?(#.*)?/);
< ["http://blog.163.com/album?id=1#comment", "http:", "blog.163.com", "/album", "?id=1", "#comment"]
*/
```


* str.replace(regexp/substr, replacement)

  - 替换一个子串
  
```js
var str1 = "The price of tomato is 5.";
str1.replace(/(\d+)/, "$1.00"); // 把"()"捕获的数字保存在$1里

var str2 = "The price of tomato is 5, the price of apple is 10.";
str2.replace(/(\d+)/, "$1.00"); // 只替换了"5"，因为正则表达式每次只做一次匹配

var str3 = "The price of tomato is 5, the price of apple is 10.";
str3.replace(/(\d+)/g, "$1.00"); // gobal 属性，全局匹配
```

```js
// 标签转义
var html = "<label>网址:</label><input placeholder='以 http://起始'>";
// 函数的输入值，是正则表达式匹配到的内容(< or >)；函数的返回值，则是用来替换匹配到的内容
html = html.replace(/[<>]/g, function(m0){
  switch(m0){
    case "<":
      return "&lt;";
    case ">":
      return "&gt;";
  }
});
```

* regexpObj.exec(str)

  - 更强大的检索
     - 更详尽的结果：index
     - 过程的状态：lastIndex
     
```js
var reg = /(.)(\d+)/g;
var scores = "Tom $88, Nicholas ￥100, jack £38.";
var result;
while (result = rag.exec(scores)) {
  console.log(result);
  console.log(reg.lastIndex);
  // reg.lastIndex += 10;
}
```