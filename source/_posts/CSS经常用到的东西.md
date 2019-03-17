---
title: CSS经常用到的东西
date: 2018-11-29 16:58:07
tags:
---
### 一、左右布局
##### 1.float属性实现左右布局
float属性是css中关于布局的一个关键属性，其意为将该块状区域脱离父级标签的文档流，left属性值使该区域向父级标签区域的左侧边界放置，right属性值使该区域块向父级标签的右侧边界放置。float区域块不会被父级区域块包裹，造成前端常见的高度塌陷问题，解决办法是清除浮动。
代码：
```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>two</title>
	<style>
		* {
			margin: 0;
			padding: 0;
		}
		.right {
			float: right;
			height: 500px;
			width: 200px;
			background-color: yellow;
		}
		.left {
			height: 500px;
			background-color: red;
			margin-right: 230px;
		}
	</style>
</head>
<body class="clearfix">
<div class="right">我是固定宽高</div>
<div class="left">我是自适应</div>
</body>
</html>
```
以上代码展示出来的是这样的![左右布局.png](https://upload-images.jianshu.io/upload_images/7017681-4865e60f81ca34cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
红色区域会随着浏览器的宽度而自适应，黄色则会保持固定宽高。
而为了清除浮动，需要在加了float属性的元素的父级元素上加清除浮动，比如：
```
.clearfix::after{
  content: '';
  display: block;
  clear: both;
}
```
***        
### 二、左中右布局
##### 1.float属性实现左中右布局
float属性同样也可以实现左中右布局。
代码：
```
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<title>three</title>
	<style>
		* {
			margin: 0;
			padding: 0;
		}
		.left {
			float: left;
			background: blue;
			height: 500px;
			width: 200px;
		}
		.right {
			float: right;
			background-color:yellow;
			height: 500px;
			width: 200px;
		}
		.center {
			height: 500px;
			background-color: red;
                        margin-left: 200px;
			margin-right: 200px;
		}
	</style>
</head>
<body>
<div class="left">我是固定宽高</div>
<div class="right">我是固定宽高2</div>
<div class="center">我是自适应</div>
	
</body>
</html>
```
以上代码展示出来的是这样的：![左中右布局](https://upload-images.jianshu.io/upload_images/7017681-db9b30792725b6df.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

***
### 三、水平居中
##### 1.给固定宽度的元素设置水平居中
如果是一个固定宽度的元素，只要设置好宽度，margin的左右值为auto就行了。
```
.center {
	width: 960px;
	margin-left: auto;
	margin-right: auto;
}
```
##### 2.利用inline-block实现水平居中方法
仅inline-block属性是无法让元素水平居中，他的关键之处要在元素的父容器中设置text-align的属性为“center”，这样才能达到效果：
HTML代码：
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>居中</title>
</head>
<body>
  <div class="center">
    我居中了
  </div>
</body>
</html>
```
css代码：
```
.center{
  display: inline-block;
  border:1px solid red;
}
body{
  text-align:center;
  background: yellow;
}
```
效果：![居中.png](https://upload-images.jianshu.io/upload_images/7017681-ab38c3f9c7df1c33.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
##### 3.利用绝对定位实现水平居中
HTML代码：
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>居中</title>
</head>
<body>
  <div class="center">
    <div class="inner">我居中了没有</div>
  </div>
</body>
</html>
```
CSS代码:
```
body{
  position: relative;
  background: yellow;
}
.center{
  position: absolute;
  left:50%;
}
.inner{
  border:1px solid blue;
  position: relative;
  float: left;
  right: 50%;
}
```
效果:![利用绝对定位实现居中](https://upload-images.jianshu.io/upload_images/7017681-6ee00dfe558d413b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
***

### 四、垂直居中
##### 1.利用line-height将内容垂直居中
这种方法前提在于字体大小不能大于line-height
HTML代码：
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title></title>
</head>
<body>
 <div>居中</div>
</body>
</html>
```
CSS代码：
```
div{
  border: 1px solid red;
  font-size: 16px;
  line-height: 40px;
}
```
也可以通过padding撑开上下：
```
div{
  border: 1px solid red;
  font-size: 16px;
  line-height: 30px;
  padding: 5px 0px;
}
```
效果都是这样：![垂直居中.png](https://upload-images.jianshu.io/upload_images/7017681-f6cb613dad8f57e7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

未完待续。。。
