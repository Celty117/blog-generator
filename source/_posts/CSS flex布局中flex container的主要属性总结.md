---
title: CSS flex布局中flex container的主要属性总结
date: 2018-12-19 22:35:48
tags:
---
#### 一、flex container的属性
flex-direction   方向
flex-wrap   换行
flex-flow   上面两个的简写
justify-content   主轴方向对齐方式
align-items   侧轴对齐方式
align-content   多行/列内容对齐方式（用的较少）
---

1. flex-direction:
- row:  从左向右一行排列，默认不换行。
- row-reverse:  从右向左一行排列，默认不换行。
- column:  从上到下一列排列。
- column:  从下到上一列排列。
---

2. flex-wrap:
- wrap:  开启换行，row和column都会换行。
- nowrap: 所有的元素都在一行。
- wrap-reverse: 元素自动换成逆序的多行。
---

3. justify-content：
- flex-start: 元素和容器的左端对齐。
- flex-end: 元素和容器的右端对齐。
- center: 元素在容器里居中。
- space-between:元素之间保持相等的距离。
- space-around:元素周围保持相等的距离。
---

4. align-items:
- flex-start: 元素与容器的顶部对齐。
- flex-end: 元素与容器的底部对齐。
- center: 元素纵向居中。
- baseline: 元素在容器的基线位置显示。
- stretch: 元素被拉伸以填满整个容器。
---

5. align-content:
- flex-start: 多行都集中在顶部。
- flex-end: 多行都集中在底部。
- center: 多行居中。
- space-between: 行与行之间保持相等距离。
- space-around: 每行的周围保持相等距离。
- stretch: 每一行都被拉伸以填满容器。
---

剩下属性用浏览器开发者工具来试效果。
***

#### 二、flex item的属性
flex-grow  增长比例（空间过多时）
flex-shrink  收缩比例（空间不够时）
flex-basis  默认大小（一般不用）
flex  上面三个的缩写
order  顺序（代替双飞翼）
align-self  自身的对齐方式

flex-grow 
多余的空间按数字比例给子元素，比如三个子元素分别是1,2,3就是1比2比3。