---
title: HTML的一些常用标签
date: 2018-11-26 14:21:07
tags:
---
HTML，超文本标记语言（英语：HyperText Markup Language，简称：HTML）是一种用于创建网页的标准标记语言。超文本标记语言，标准通用标记语言下的一个应用。
“超文本”就是指页面内可以包含图片、链接等非文字元素。
超文本标记语言的结构包括“头”部分（英语：Head）、和“主体”部分（英语：Body），其中“头”部提供关于网页的信息，“主体”部分提供网页的[具体]内容。
***

#### 一、最基本的HTML5结构
```
<!DOCTYPE html>
<html> 
<head> <!-- head标签是所有头部元素的容器。head标签内的元素可包含脚本、样式表和提供页面的元信息等等。以下标签都可以添加到 head 部分：title、base、link、meta、script 以及style。头部的内容不会显示在浏览器的。 -->
<meta charset="utf-8"> <!-- 设置字符集，如果字符集不对，可能导致乱码。一般建议utf-8国际编码 -->
<title>网页标题</title> <!-- SEO相关标签，title定义文档的标题,百度建议一般不要超过32位,meta定义页面关键词和页面的描述-->
</head>
<body> <!-- 正文部分，所有在浏览器上可见的内容必须写在body标签内部 -->
    
</body>
</html>
```
<!DOCTYPE> 声明必须是 HTML 文档的第一行，位于html标签之前。<!DOCTYPE>是指示 web 浏览器关于页面使用哪个 HTML 版本进行编写的指令，有助于浏览器中正确显示网页。其它声明方式及最新html标准可以通过以下链接学习：
HTML标准：[https://www.w3.org/TR/html51/](https://www.w3.org/TR/html51/)
MDN：[https://developer.mozilla.org/zh-CN/](https://developer.mozilla.org/zh-CN/)
***
#### 二、HTML常用标签基本用法
1.a标签定义超链接，指定页面间的跳转（HTTP get请求）。链接可以指向外部链接或者页面内部id锚点，可以在当前页面打开，新开窗口。

```
<a href="指向的链接地址或者网址#ID名" target="_blank|_self|_top|_parent">谷歌</a>
```
2.form标签定义提交方式、提交地址、表单字符集以及如何对其进行编码，需要提交的表单一定要放在form标签内。
```
<form id="form1" name="form1" method="post|get" action="提交到的地址"></form>
```
3、input标签用于为基于Web的表单创建交互式控件，以便接受来自用户的数据。通常和form标签配合使用
```
<form action="demo_form.asp">
  输入框: <input type="text" name="请输入"><br>
  按钮: <input type="button" name="按钮"><br> <!--无跳转请求-->
  <input type="submit" value="提交"> <!--有跳转请求-->
</form>
```
4、button标签定义一个按钮。在 button元素内部，您可以放置内容，比如文本或图像。这是该元素与使用 input元素（空元素）创建的按钮之间的不同之处。
```
<button type="button">点我!</button>
```
5、h1 - h6标签被用来定义 HTML 标题。h1定义重要等级最高的标题，h6定义登记最低的标题。从大到小排列就是这样的。h1>h2>h3>h4>h5>h6
```
<h1>这是标题 1</h1> 
<h2>这是标题 2</h2> 
<h3>这是标题 3</h3> 
<h4>这是标题 4</h4> 
<h5>这是标题 5</h5> 
<h6>这是标题 6</h6>
```
6、p标签定义段落
```
<p>这是一个段落。</p>
```
7、hr标签定义 HTML 页面中的主题变化（比如话题的转移），并显示为一条水平线。br标签插入一个简单的换行符。两者都是空标签，没有结束符。
```
<h1>HTML</h1>
<p>HTML 是用于描述 web 页面的一种语言。</p>

<hr>

<h1>CSS</h1>
<p>CSS 定义如何显示 HTML 元素。</p>
<p> 
使用 br 元素<br>在文本中<br>换行。 
</p>
```
8、ul标签定义无序列表。
```
<ul>
<li>Coffee</li>
<li>Tea</li>
<li>Milk</li>
</ul>
```
9、ol标签定义了一个有序列表，列表排序以数字来显示。
```
<ol>
  <li>一</li>
  <li>二</li>
  <li>三</li>
</ol>
```
10、small标签定义小型文本（和旁注）。
```
<p> runoob.com - the world's largest web development site.</p>
<p><small> Copyright 1999-2050 by Refsnes Data.</small></p>
```
11、strong标签定义重要的文本。有强调的作用色彩
```
<strong>加粗文本，强调重要性</strong>
```
12、div标签和span标签是html里没有语义的两个标签，在CSS中通常称为块级元素和内联元素，在html里边没有这样的说法。
div标签它是可用于组合其他HTML元素的容器，标签定义 HTML 文档中的一个分隔区块或者一个区域部分。通常用于文档布局，以便通过 CSS 来对这些元素进行格式化。
```
<div style="color:#0000FF">
  <h3>这是一个在 div 元素中的标题。</h3>
  <p>这是一个在 div 元素中的文本。</p>
</div>
```
13、kbd标签定义键盘文本。目前已废弃，不推荐使用，但 是可以通过CSS实现丰富的效果。
```
<kbd>键盘输入</kbd>
```
14、video标签定义视频，比如电影片段或其他视频流。目前，video元素支持三种视频格式：MP4、WebM、Ogg。可以在 <video> 和 </video> 标签之间放置文本内容，这样不支持video元素的浏览器就可以显示出该标签的信息。
```
<video width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    <source src="movie.ogg" type="video/ogg">
    您的浏览器不支持 video 标签。
</video>
```
15、audio标签，HTML5 规定了在网页上嵌入音频元素的标准。在<audio> 与 </audio> 之间你需要插入浏览器不支持的audio元素的提示文本 。
```
<audio controls>
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
您的浏览器不支持 audio 元素。
</audio>
```
16、svg标签，SVG 文件可通过以下标签嵌入 HTML 文档：<embed、object或者iframe。这样SVG的代码可以直接嵌入到HTML页面中，或您可以直接链接到SVG文件。

embed：

优势：所有主要浏览器都支持，并允许使用脚本
缺点：不推荐在HTML4和XHTML中使用（但在HTML5允许）
语法：
```
<embed src="circle1.svg" type="image/svg+xml" />
```
object：

优势：所有主要浏览器都支持，并支持HTML4，XHTML和HTML5标准
缺点：不允许使用脚本。
语法：
```
<object data="circle1.svg" type="image/svg+xml"></object>
```
iframe：

优势：所有主要浏览器都支持，并允许使用脚本
缺点：不推荐在HTML4和XHTML中使用（但在HTML5允许）
语法：
```
<iframe src="circle1.svg"></iframe>
```
在Firefox、Internet Explorer9、谷歌Chrome和Safari中，你可以直接在HTML嵌入SVG代码。
```
<svg xmlns="http://www.w3.org/2000/svg" version="1.1">
   <circle cx="100" cy="50" r="40" stroke="black" stroke-width="2" fill="red" />
</svg>
```
17、span用标签于对文档中的元素进行组合。标签没有固定的格式表现。当对它应用样式时，它才会产生视觉上的变化。提供了一种将文本的一部分或者文档的一部分独立出来的方式。
```
<p>我的母亲是 <span style="color:blue">伟大</span> 的。</p>
```
***
#### 三、HTML注意事项
1、HTML标签和属性是不区分大小写的，建议HTML标签和属性都小写，属性值必须用双引号包围。

2、HTML标签都是以开始标签起始，以结束标签终止。大部分HTML标签都是成对出现的，称为双标签，比如：p标签、div标签，也有的HTML标签在开始标签中结束的标签，称为单标签，比如：hr标签、br标签。大多数 HTML 元素可拥有属性，文本内容都是写在开始标签与结束标签之间。

3、HTML标签之间尽量缩进与换行，每行代码不要过长，方便阅读和维护。

4、HTML标签使用必须符合标签嵌套规则。禁止a标签嵌套a标签，p标签嵌套div标签。

5、建议不使用HTML已经废弃的或者不赞成使用的标签，少使用table布局、iframe框架嵌套以及flash播放器。

以上也只是讲了一部分常用标签的用法和注意事项。
