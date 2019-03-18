---
title: JS里的数据类型转换
date: 2018-12-13 23:22:48
tags:
---
### 一、转为字符串
1. toString()方法

数值、字符串、对象、布尔；都有`toString`方法；这个方法唯一能做的就是返回相应的字符串；其中`null`和`undefined`没有`toString()`方法。
![x.toString()](https://upload-images.jianshu.io/upload_images/7017681-3c4bd0305da99f15.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2. String(x)

`String()`属于强制转换， `null`转换的结果为`null`；`undefined`转换的结果为`undefined`；其余的如果有`toString()`方法，即调用该方法，返回相应的结果。
![String(x)](https://upload-images.jianshu.io/upload_images/7017681-1935af757f2302af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3. x + ''

还有一种比较“老司机”的方法，就是任何数据类型直接 `+` 空字符串`''`就行了。如下：
![x + ''](https://upload-images.jianshu.io/upload_images/7017681-92fc30ce62b60eb1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

注意，如果非要将number + string，会调用number的`toString`方法，如下
```
1 + '2'    相当于
(1).toString() + '2'
// '12'
```
---
### 二、转为布尔
1. Boolean()

`Boolean`函数可以将任意类型的值转为布尔值。
它的转换规则相对简单：除了以下五个值(5个falsy值)的转换结果为`false`，其他的值全部为`true`。
- `undefined`
- `null`
- `-0`或`+0`
- `NaN`
- `''`（空字符串）
```
Boolean(undefined) // false
Boolean(null) // false
Boolean(0) // false
Boolean(NaN) // false
Boolean('') // false
```
所有对象（包括空对象）的转换结果都是`true`，甚至连false对应的布尔对象`new Boolean(false)`也是`true`。

2.!!x
还有一种比较聪明的方法就是通过`!`取反，这样的话两个感叹号`!!`就是负负得正，在一个数据类型前面加上`!!`就可以返回它本身的布尔值。
```
!true // false
!!true // true
!!1 // true
!!'' // false
!!NaN // false
```
---
### 三、转为数值
1.Number()

使用`Number`函数，可以将任意类型的值转化成数值。 
```
Number('1') // 1
```

2. parseInt() （经常有人问的）

`parseInt()` 函数解析一个字符串参数，并返回一个指定基数的整数 (数学系统的基础)。能解析多少就解析多少，一旦遇到不能解析的字符串，就立马退出返回结果。
```
parseInt('1',10) // 1
```

3. parseFloat()

`parseFloat()` 函数解析一个字符串参数并返回一个浮点数。
```
parseFloat("3.14");
parseFloat("314e-2");
parseFloat("0.0314E+2");
parseFloat("3.14more non-digit characters");
```

4. x - 0 （常用也常见）

一个比较聪明的方法，也是比较骚的方法。（既有`parseInt()`的功能，也有`parseFloat()`的功能）
```
'12' - 0 // 12
'1.23' - 0 // 1.23
```

5. +x

通过取正(取它原本的值)，来得出数值。
```
+ '1.23' // 1.23
+ '.1' // 0.1
+ '-1' // -1
```