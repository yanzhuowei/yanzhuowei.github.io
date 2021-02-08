---
title: 变量提示和var、let、const
date: 2020-11-21 15:58:26
author: 慕言
img: 
top: false
summary: 变量提示的一点知识点以及var、let、const的区别
categories: JavaScript
tags:
  - 变量提示、var、let、const
---
### 变量提示

> 在当前执行上下文代码执行之前，首先会把带有var或者function关键字的声明或者定义（带var的只会提前声明，带function会提前声明+定义（赋值））import 也有变量提升
> **同名变量和函数，函数会提升到最前边，变量会被忽略**
> **同名变量，声明会被提升，后边声明会忽略**
> **同名函数会被覆盖**

- 看一道面试题
```js
console.log(a)   // a函数  
    if (a) {
        var a = 1;  
        console.log(a)   // 1
    }
    function a() {
        console.log(this);  
    }
    console.log(a);  // 1 
    a()  //  a is not a function
    -----------------------------
    预解析阶段，var 和函数都会被提升，但函数会被提到最前面var a被忽略
    打印 第一次a   // a函数  
    a  为真
    a=1  给a重新赋值为1   打印第二次a  // 1
    函数已经声明定义了不用管
    第三次打印a   // 1
    a（ ）  a调用 但是这是a为1  报错a is not a function

```

### var和let的区别

> 1、var：有变量提升；let：没有变量提升；
> 2、在全局执行上下文中用var声明一个变量，也会给全局对象GO中（window）增加一个对应的属性；但是用let声明的变量不存在这个特点,不会给全局对象（window）中增加对应属性。
> 3、带var可以重复声明（词法解析可以审核过），带let不可以重复声明（词法解析阶段都过不去）
> 4、let存在块级作用域（var没有）{} 就是一个块级作用域，对象{}除过

### let 和 const区别

> let（不可重复声明） 创建的变量可以更改指针指向（也就是可以重新赋值），但是const（不可重复声明）声明的变量是不允许改变指针指向的。