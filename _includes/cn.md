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

1) \\(d(\\mathbf{x},\\mathbf{x}) = 0, \\forall \\mathbf{x} \\in \\mathbf{X}.\\) 相同向量间距离为零。

2) \\(d(\\mathbf{x},\\mathbf{y}) > 0, \\forall \\mathbf{x} \\neq \\mathbf{y} \\in \\mathbf{X}.\\) 正性：不同向量间距离为正值。

3) \\(d(\\mathbf{x},\\mathbf{y}) = d(\\mathbf{y},\\mathbf{x}), \\forall \\mathbf{x}, \\mathbf{y} \\in \\mathbf{X}.\\) 对称性：交换两向量位置，得到同样的距离。

4) \\(d(\\mathbf{x},\\mathbf{z}) \\leq d(\\mathbf{x},\\mathbf{y}) + d(\\mathbf{y},\\mathbf{z}), \\forall \\mathbf{x}, \\mathbf{y}, \\mathbf{z} \\in \\mathbf{X}.\\) 三角形不等式：两边之和大于第三边。

### 欧几里得度量 ###

也称为欧式距离、 \\(l^2\\) 或者 \\(l\_2\\) 度量。\\(\\forall \\mathbf{x}, \\mathbf{y} \\in \\mathbb{R}^n, n \\in \\mathbb{N}\\),

\\[d\_{l^2}(\\mathbf{x},\\mathbf{y}) = \\sqrt{\\sum^n\_{i=1}(x\_i - y\_i)^2}\\]

### 出租车度量 ###

也称为曼哈顿距离、 \\(l^1\\) 或者 \\(l\_1\\) 度量。\\(\\forall \\mathbf{x}, \\mathbf{y} \\in \\mathbb{R}^n, n \\in \\mathbb{N}\\),

\\[d\_{l^1}(\\mathbf{x},\\mathbf{y}) = \\sum^n\_{i=1}\\|x\_i - y\_i\\|\\]

### 上确界范数度量 ###

也称为 \\(l^\\infty\\) 或者 \\(l\_{\\infty}\\) 度量。\\(\\forall \\mathbf{x}, \\mathbf{y} \\in \\mathbb{R}^n, n \\in \\mathbb{N}\\),

\\[d\_{l^{\\infty}}(\\mathbf{x},\\mathbf{y}) = \\sup^n\_{i=1}\\|x\_i - y\_i\\|\\]

### 切比雪夫距离 ###

\\(\\forall \\mathbf{x}, \\mathbf{y} \\in \\mathbb{R}^n, n \\in \\mathbb{N}\\),

\\[d\_{Chebyshev}(\\mathbf{x},\\mathbf{y}) = \\max^n\_{i=1}\\|x\_i - y\_i\\|\\]

### 明可夫斯基距离 ###

\\(\\forall \\mathbf{x}, \\mathbf{y} \\in \\mathbb{R}^n, n \\in \\mathbb{N}\\),

\\[d\_{Minkowski}(\\mathbf{x},\\mathbf{y}) = \\left(\\sum^n\_{i=1}\\|x\_i - y\_i\\|\\right)^{\\frac{1}{p}}\\]

