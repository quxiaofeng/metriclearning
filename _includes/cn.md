度量学习
======================

[English](/) | [中文](/cn/)

综述
----

+ [A Survey on Metric Learning for Feature Vectors and Structured Data](http://arxiv.org/pdf/1306.6709v4.pdf) (2014) by *Aurélien Bellet, Amaury Habrard, Marc Sebban*

+ [Metric Learning: A Survey](http://web.cse.ohio-state.edu/~kulis/pubs/ftml_metric_learning.pdf) (2013) by *Brian Kulis*

+ [Distance Metric Learning: A Comprehensive Survey](http://www.cs.cmu.edu/~liuy/frame_survey_v2.pdf) (2006) by *Liu Yang*

框架
----

度量学习要解决的基本问题，就是欧式距离的问题。不同维度的权重、不同特征的相关性、数据点的空间分布，有着种种不同。都按照一个僵硬的标准来统计距离实在是不科学的。

而度量学习，就是学习一种映射（或者说是一种距离的度量方法，又或者说寻找一个新的空间及对应的投影方法），在该映射下，可以达到期望的功能。而这个功能，根据问题的不同，自然有不同的定义方式。所以度量学习，基本就是定义一个优化问题，如何从数据中学习一个距离计算的方法，让这个距离计算的方法最为符合期望的目的。



传统度量方法 - 距离
------------------------------

### 定义 ###

距离（度量）函数\\(d(\\mathbf{x},\\mathbf{y})\\)是从两个向量\\(\\mathbf{x},\\mathbf{y} \\in \\mathbf{X}\\)到一个标量的映射，需要满足如下条件。

\\[\text{1) }d(\\mathbf{x},\\mathbf{x}) = 0, \\forall \\mathbf{x} \\in \\mathbf{X}.\\]
相同向量间距离为零。

\\[\text{2) }d(\\mathbf{x},\\mathbf{y}) > 0, \\forall \\mathbf{x} \\neq \\mathbf{y} \\in \\mathbf{X}.\\]
正性：不同向量间距离为正值。

\\[\text{3) }d(\\mathbf{x},\\mathbf{y}) = d(\\mathbf{y},\\mathbf{x})， \\forall \\mathbf{x}，\\mathbf{y} \\in \\mathbf{X}.\\]
对称性：交换两向量位置，得到同样的距离。

\\[\text{4) }d(\\mathbf{x},\\mathbf{z}) \\leq d(\\mathbf{x},\\mathbf{y}) + d(\\mathbf{y},\\mathbf{z}), \\forall \\mathbf{x}，\\mathbf{y}，\\mathbf{z} \\in \\mathbf{X}.\\]
三角形不等式：两边之和大于第三边。

### 欧几里得距离 ###

也称为\\(l^2\\)度量\\(d\_{l^2}(\\mathbf{x},\\mathbf{y}) = (\\sum^n\_{i=1}(x\_i - y\_i)^2)^{\\tfrac{1}{2}}\\)
