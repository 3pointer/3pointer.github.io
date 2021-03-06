---
layout: post
title: Merry Christmas
---

今天就是圣诞节了，不过昨晚还是熬到两点，因为看到了一篇Least squares approximations的论文，就花时间研究了研究。
之前在看Andrew Ng的机器学习课程时，里面提到了linear regression的第二种方法--normal equation，也有人叫最小二乘法，有一个关键问题我一直不得理解，搞懂之后决定把它贴出来，留个纪念。

首先问题一，以AX=b为例，A是m×n的矩阵，规定m>n,Andrew Ng在正则化一课中提到，如果样例m小于特征n的话，程序会报错，就要用到正则化来解决，或者delete一些特征来解决。
那么为什么会这样，要解决这个问题，可以从两个方面来理解，一个是向量空间，另一个是矩阵的秩，其实本质是一样的。

第一个让我们来看一张图。

![gg]({{site.baseurl}}/images/1.png)

注意，AX = b 是不可能的，A由a1, a2组成，而b的的维度比A要高，无论a1,a2,如何取值，都不会合出一个b来，但是我们可以取到b‘，就是b在A空间的投影。
而e是垂直于A空间的，我们求出一个令e最小的值就好了， e = b - AX，求出e的模，令其最小的x，就是我们要得近似值。

至于说为什么m>n，似乎还没有解释。
Andrew Ng给出的公式，theta = （X^T*X)^-1*X^T*y
因为m<=n时，矩阵（X^T*X)不可逆，为什么不可逆呢，我们可以从矩阵的秩来解释。
