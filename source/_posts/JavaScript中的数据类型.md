---
title: JavaScript中的数据类型
date: 2020-11-12 16:08:14
author: 慕言
img: 
top: false
summary: JavaScript中的数据类型详解
categories: JavaScript
tags:
  - 数据类型
---
### JavaScript中的数据类型

&#160;&#160;&#160;&#160;**基本数据类型：Number、String、Boolean、null、undefined、Symbol**

&#160;&#160;&#160;&#160;**应用数据类型：Object （{}、[]、/^s/......）、function**

### String
> 所有用单引号、双引号、反引号（ ES6模板字符串）包起来的都是字符串

##### 把其他类型值转换成字符串
**toString()：** null、undefined不能直接toString; 

**注意:[].toString()//'' [12].toString()//'12' [12,'ASB12',].toString()//"12,ASB12"**

**注意:普通对象.toString()结果"[object Object]" 因为：调用的是自己原型上的toString()，而这个方法是检测数据类型的**

**使用 + 号进行字符串拼接**

### Number

> 包含：常规数字、NaN

**NaN:**  非数字,不是一个数; (但它率属于数字类型)  typeof NaN // "number"  **注意：NaN和任何值（包括自己）都不相等**

**isNaN：** 检测一个值是否为非有效数字（数字和数字类型不要弄混淆了，isNaN(NaN) // true ），如果不是有效数字返回true，反之是有效数字返回false；（在使用isNaN进行检测的时候，首先会验证检测的值是否为数字类型，如果不是，先基于**Number()**这个方法，把值转换为数字类型，然后检测）

##### 把其他类型值转换成数字类型

**Number():** Number('11')//11  Number('11A')//NaN  Number(true)//1  Number(false)//0  Number(null)//0 

**注意：Number(undefined)//NaN undefined代表未定义，未定义代表没有赋值，没有赋值的值它就没有值。没有值的话它就是NaN**

**注意：在使用Number() 转换引用类型的时候，是先基于toString()转换成字符串在转换成数字类型**
例：Number({name:10}) // NaN  {name:10}.toString()//"[object Object]"  Number("[object Object]")//NaN
Number([]) //0 [].toString()//'' Number('')//0
Number([12]) //12 [12].toString()//'12' Number('12')//12

**parseInt/parseFloat([val],[进制])** 从左到右依次查找有效数字字符，知道遇到非有效数字字符，停止查找

**使用 + 号进行运算：** 如果遇到的值不是数字类型，也需要基于Number()方法转换为数字，在进行运算；

### Number

> 只有两个值 true/false

**把其它类型值转换成布尔类型**

> 只有0、NaN 、null、''、undefined 五个值转换为false，其余都转换为true（而且没有任何的特殊情况）

**Boolean()**

**!/!!**

**条件判断**

### Object

#### 普通对象

> {[key]:[value]} 
> 注意：对象的属性名一定不能是引用类型，默认会把引用类型只转换成字符串；
> 属性名不存在，获取时值为undefined；属性名为数字，则不能使用.的方式来获取值；属性名不能重复；
> delete 对象.属性名 (为真删除) 对象.属性名=null (为假删除，属性还在值为空)

#### [] 数组

> [0,1,2]
> 属性名是默认生成的数字，从0开始递增；而且代表每一项的位置
> 有一个天生的属性：length 代表数组长度

### function 函数

> 对一段代码的封装，在需要的时候执行；

**创建函数：** 1、function fn(name){....rerun} 2、var fn = function(name){....rerun} 3、(function(name){....rerun})(111) 、~ffunction(){}()
> 创建函数时，声明形参 例如：name 需要 return 返回值 **有一个参数arguments：函数内置实参集合 是类数组但不能使用数组的方法**
> 没有写 return 默认返回值为 undefined
> 函数体中代码遇到 return 不在向下执行 

**执行函数：** fn(11) 括号中传递的是实参 1、需要使用形参接收，如未接收则自动丢弃 2、未传递，形参默认值为undefined

**函数执行过程：函数是引用类型，存储在堆中；堆中存储的是函数声明时的字符串，当函数执行时，会开辟一块私有栈内存用来执行函数；所以函数内部的变量不能被外部访问，只能return出去；**











