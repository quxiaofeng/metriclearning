[English](/) | [中文](/cn/)

Surveys
-------

+ [A Survey on Metric Learning for Feature Vectors and Structured Data](http://arxiv.org/pdf/1306.6709v4.pdf) (2014) by *Aurélien Bellet, Amaury Habrard, Marc Sebban*

+ [Metric Learning: A Survey](http://web.cse.ohio-state.edu/~kulis/pubs/ftml_metric_learning.pdf) (2013) by *Brian Kulis*

+ [Distance Metric Learning: A Comprehensive Survey](http://www.cs.cmu.edu/~liuy/frame_survey_v2.pdf) (2006) by *Liu Yang*

Framework
---------

### Pairwise Constraints ###

Let \\(\\mathcal{C} = \{x\_1, x\_2,\\ldots,x\_n\}\\) be a collection of data points, where \\(n\\) is the number of samples in the collection. Each \\(x\_i \\in \\mathbb{R}^m\\) is a data vector where \\(m\\) is the number of features. Let the set of equivalence constraints denoted by

\\[
\\mathcal{S} = \\{(x\_i, x\_j) | x\_i\\text{ and }x\_j\\text{ belong to the same class}\\}
\\]

and the set of inequivalence constraints denoted by

\\[
\\mathcal{D} = \\{(x\_i, x\_j) | x\_i\\text{ and }x\_j\\text{ belong to different classes}\\}
\\]

Let the distance metric denoted by matrix \\(\\mathbf{A} \\in \\mathbb{R}^{m \times m}\\), and the distance between any two data points \\(\\mathbf{x}\\) and \\(\\mathbf{y}\\) expressed by

\\[
d^2\_{\\mathbf{A}}(\\mathbf{x},\\mathbf{y}) = \\|\\mathbf{x} - \\mathbf{y}\\|^2\_{\\mathbf{A}} = (\\mathbf{x} - \\mathbf{y})^T \\mathbf{A} (\\mathbf{x} - \\mathbf{y}) 
\\]

### Global Distance Metric Learning by Convex Progamming ###

Given the equivalence constraints in S and the inequivalence constraints in D, [11] formulated the problem of metric learning into the following convex programming problem [14]:

\\[
\\min\_{\\mathbf{A} \\in \\mathbb{R}^{m \\times m}} \\sum\_{(\\mathbf{x}\_i, \\mathbf{x}\_j) \\in \\mathcal{S}} \\|\\mathbf{x}\_i - \\mathbf{x}\_j\\|^2\_{\\mathbf{A}}
\\]

\\[
\\text{s.t.} \\quad \\mathbf{A} \\succeq 0, \\sum\_{(\\mathbf{x}\_i, \\mathbf{x}\_j) \\in \\mathcal{D}} \\|\\mathbf{x}\_i - \\mathbf{x}\_j\\|^2\_{\\mathbf{A}} \\geq 1
\\]

Traditional Metrics - Distance
------------------------------

### Definition ###

Distance is function \\(d(\\mathbf{x},\\mathbf{y})\\).

1) \\(d(\\mathbf{x},\\mathbf{x}) = 0, \\forall \\mathbf{x} \\in \\mathbf{X}.\\)

2) \\(d(\\mathbf{x},\\mathbf{y}) > 0, \\forall \\mathbf{x} \\neq \\mathbf{y} \\in \\mathbf{X}.\\)

3) \\(d(\\mathbf{x},\\mathbf{y}) = d(\\mathbf{y},\\mathbf{x}), \\forall \\mathbf{x}, \\mathbf{y} \\in \\mathbf{X}.\\)

4) \\(d(\\mathbf{x},\\mathbf{z}) \\leq d(\\mathbf{x},\\mathbf{y}) + d(\\mathbf{y},\\mathbf{z}), \\forall \\mathbf{x}, \\mathbf{y}, \\mathbf{z} \\in \\mathbf{X}.\\)
