---
title: JS一些常用的API
date: 2018-12-20 21:35:48
tags:
---
1. setTimeout()
```
setTimeout(function () {
  enter.classList.remove('active')
}, 2000)
```
2秒之后执行括号里的代码。

---
2. window.onscroll
window.scrollY
```
    window.onscroll = function () {
      if (window.scrollY > 0) {
        topNavBar.classList.add('sticky')
      } else {
        topNavBar.classList.remove('sticky')
      }
    }
```
window.onscroll：在用户滑动浏览器窗口的时候触发一个函数。
window.scrollY：获取到浏览器窗口滚动的高度。

---
3.document.querySelectorAll()
```
let liTags = document.querySelectorAll('nav.menu>ul>li')
```
接受一个选择器，返回选择器对应的所有元素。

---
4. .onmouseenter
.onmouseleave
```
      liTags[i].onmouseenter = function (x) {
        x.currentTarget.classList.add('active')
      }
      liTags[i].onmouseleave = function (x) {
        x.currentTarget.classList.remove('active')
      }
```
.onmouseenter：当鼠标进入一个元素的时候，会触发一个函数。
.onmouseleave：当鼠标离开一个元素的时候，会触发一个函数。

---
5. .preventDefault()
.getAttribute()
document.querySelector()
.offsetTop
window.scrollTo()

```
    for(let i=0;i<aTags.length;i++){
      aTags[i].onclick = function(x){
        x.preventDefault()  
        let a = x.currentTarget   
        let href = a.getAttribute('href')  
        let element = document.querySelector(href) 
        let top = element.offsetTop   
        window.scrollTo(0,top-70)   
      }
    }
```
.preventDefault()：阻止默认动作。
.getAttribute()：获取到这个标签上写的原文，而不是浏览器修改（比如加了http协议的东西）。
document.querySelector()：与加了All相比，只会返回一个元素，而不是一个数组。
.offsetTop：获取一个元素距离到页面顶部的像素数（不是浏览器窗口顶部）。
window.scrollTo()：让浏览器窗口滑动到某个位置，括号里是左右方向和上下方向滑动的位置的值。
