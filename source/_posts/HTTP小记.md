---
title: git小记(1)
date: 2018-07-21 13:05:07
tags:
---

## curl命令
curl命令一般有三种
1. `curl -s -v -H "colin: xxx" -- "https://www.baidu.com"`这个是get
2. `curl -X POST -s -v -H "colin: xxx" -- "https://www.baidu.com"` 与get对应的post
3. `curl -X POST -d "1234567890" -s -v -H "colin: xxx" -- "https://www.baidu.com"` 添加一个上传的数据
***
##  http请求
使用`curl -X POST -d "1234567890" -s -v -H "colin: xxx" -- "https://www.baidu.com"`发送一个请求
* 请求的内容为
```
POST / HTTP/1.1
Host: www.baidu.com
User-Agent: curl/7.54.0
Accept: */*
colin: xxx
Content-Length: 10
Content-Type: application/x-www-form-urlencoded

1234567890
```
* 请求的格式为
```
1 动词 路径 协议/版本
2 Key1: value1
2 Key1: value2
2 Key3: value3
2 Content-Type: application/x-www-form-urlencoded
2 Host: www.baidu.com
2 User-Agent: curl/7.54.0
3  
4 要上传的数据
```
##### 可以看到
1. 请求最多包含四部分，最少包含三部分。（也就是说第四部分可以为空）
2. 第三部分永远都是一个回车（`\n`）
3. 动词有 GET POST PUT PATCH DELETE HEAD OPTIONS 等
4. 这里的路径包括「查询参数」，但不包括「锚点」
5. 如果你没有写路径，那么路径默认为 /
6. 第 2 部分中的 Content-Type 标注了第 4 部分的格式

##### 用 Chrome 发请求打开 Network
1. 地址栏输入网址
2. 在 Network 点击，查看 request，点击「view source」
3. 点击「view source」
4. 终于点了？可以看到请求的前三部分了
5. 如果有请求的第四部分，那么在 FormData 或 Payload 里面可以看到
***
## http响应
请求了之后，一般都会得到一个响应,除非断网或者服务器宕机了
##### 响应的格式
```
1 协议/版本号 状态码 状态解释
2 Key1: value1
2 Key2: value2
2 Content-Length: 17931
2 Content-Type: text/html
3
4 要下载的内容
```
GET 请求和 POST 请求对应的响应可以一样，也可以不一样，响应的第四部分可以很长很长很长.
1. 状态码要背，是服务器对浏览器说的话
2. 状态解释没什么用
3. 第 2 部分中的 Content-Type 标注了第 4 部分的格式
4. 第 2 部分中的 Content-Type 遵循 MIME 规范
##### 用 Chrome 查看响应
1. 打开 Network
2. 输入网址
3. 选中第一个响应
4. 查看 Response Headers，点击「view source」
5. 你会看到响应的前两部分
6. 查看 Response 或者 Preview，你会看到响应的第 4 部分
