---
layout: post
title: Merry Christmas
---

今天就是圣诞节了，不过做完还是熬到两点，因为看到了一篇Least squares approximations的论文，就花时间研究了研究。
之前在看Andrew Ng的机器学习课程时，里面提到了linear regression的第二种方法--normal equation，也有人叫最小二乘法，有一个关键问题我一直不得理解，搞懂之后决定把它贴出来，留个纪念。

首先问题一，以AX=b为例，A是m×n的矩阵，规定m>n,Andrew Ng在正则化一课中提到，如果样例m小于特征n的话，程序会报错，就要用到正则化来解决，或者delete一些特征来解决。
那么为什么会这样，要解决这个问题，可以从两个方面来入手。

第一个让我们来看一张图。

![gg]({{site.imageOne}})
