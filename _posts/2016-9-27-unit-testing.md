---
layout: post
title: 单元测试
categories: [blog ]
tags: [Front-end ]
description: 单元测试
---

### 从一个例子开始

**原始代码**

```js
var sum = function(array) {
    var s = 0
    for(var i = 0; i < array.length; i++) {
        var n = array[i]
        s = s + n
    }
  	return s
}

var a = [1, 2, 3, 4]
console.log('sum', sum(a))
```

**加入单元测试后**

```js
var sum = function(array) {
    var s = 0
    for(var i = 0; i < array.length; i++) {
        var n = array[i]
        s = s + n
    }
  	return s
}

var ensure = function(condition, message) {
    if (!condition) {
        console.log(message)
    }
}

var testSum = function() {
    ensure(sum([1, 2, 3, 4] === 10), 'sum 错误')
    ensure(sum([1] === 1), 'sum 1 错误')
}

testSum()
```

> 我们写了一个函数 sum，现在要验证这个函数是否正确。怎么验证呢？在原始代码中，我们直接调用了 sum，想看看执行的结果和我们所想的是否一致。现在加入测试，我们通过另一个函数 testSum 调用 sum，来自动化验证。

### 几个例子

**1**

```js
// 参数是一个只包含数字的 array
// 求 array 的乘积
var product = function(array) {
    var s = 1
    for (var i = 0; i < array.length; i++) {
        var n = array[i]
        s *= n
    }
    return s
}

var testProduct = function() {
    ensure(product([1, 2, 3]) === 6, 'test product 1')
    ensure(product([1, 2, 0]) === 0, 'test product 2')
}

testProduct()
```

**2**

```js
// 返回一个数的绝对值
var abs = function(n) {
    if (n < 0) {
        return -n
    } else {
        return n
    }
}

var testAbs = function() {
    ensure(abs(0) === 0, 'abs 0 错误')
    ensure(abs(-6) === 6, 'abs 6 错误')
    ensure(abs(5) === 5, 'abs 5 错误')
}

testAbs()
```