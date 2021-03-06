---
title: 从输出URL到页面展示发生了什么
date: 2017-07-22 16:22:48
tags:
---
## URL是什么
- **URL**是统一资源定位符（Uniform Resource Locator）的简称。统一资源定位符是对可以从互联网上得到的资源的位置和访问方法的一种简洁的表示，是互联网上标准资源的地址。互联网上的每个文件都有一个唯一的URL，它包含的信息指出文件的位置以及浏览器应该怎么处理它。
- 模式/协议（scheme）：它告诉浏览器如何处理将要打开的文件。最常用的模式是超文本传输协议（Hypertext Transfer Protocol，缩写为HTTP），这个协议可以用来访问网络。

## 域名解析
**IP**地址是什么：IP地址被用来给Internet上的电脑一个编号。大家日常见到的情况是每台联网的PC上都需要有IP地址，才能正常通信。我们可以把“个人电脑”比作“一台电话”，那么“IP地址”就相当于“电话号码”。
**DNS**是什么：DNS（Domain Name System，域名系统），因特网上作为域名和IP地址相互映射的一个分布式数据库，能够使用户更方便的访问互联网，而不用去记住能够被机器直接读取的IP数串。通过主机名，最终得到该主机名对应的IP地址的过程叫做域名解析。
- 浏览器缓存 – 浏览器会缓存DNS记录一段时间。
- 系统缓存 - 从 Hosts 文件查找是否有该域名和对应 IP。
- 路由器缓存 – 一般路由器也会缓存域名信息。
- ISP DNS 缓存 – 比如到电信的 DNS 上查找缓存。
- 如果都没有找到，则向根域名服务器查找域名对应 IP，根域名服务器把请求转发到下一级，直到找到 IP。

## 服务器处理
服务器是一台安装系统的机器，常见的系统如Linux、windows server 2012。系统里安装的处理请求的应用叫 Web server。
Web服务器可以解析(handles)HTTP协议。当Web服务器接收到一个HTTP请求(request)，会返回一个HTTP响应(response)，例如送回一个HTML页面。为了处理一个请求(request)，Web服务器可以响应(response)一个静态页面或图片，进行页面跳转(redirect)，或者把动态响应(dynamic response)的产生委托(delegate)给一些其它的程序例如CGI脚本，JSP(JavaServer Pages)脚本，servlets，ASP(Active Server Pages)脚本，服务器端(server-side)JavaScript，或者一些其它的服务器端(server-side)技术。无论它们(译者注：脚本)的目的如何，这些服务器端(server-side)的程序通常产生一个HTML的响应(response)来让浏览器可以浏览。

## 网站处理流程
![](http://upload-images.jianshu.io/upload_images/7017681-b013a59beffbf8b7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


##浏览器处理
- HTML字符串被浏览器接受后被一句句读取解析。
- 解析到link 标签后重新发送请求获取css。
- 解析到 script标签后发送请求获取 js，并执行代码。
- 解析到img 标签后发送请求获取图片资源。

##绘制网页
浏览器根据 HTML 和 CSS 计算得到渲染树，绘制到屏幕上js 会被执行。