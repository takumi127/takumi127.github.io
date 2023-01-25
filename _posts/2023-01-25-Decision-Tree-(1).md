---
layout: post
title: Decision Tree (1)
katex: True
---


#### Gist:
1. Information Entropy & Infomration Gain
2. Application to deicision tree

------------------------

### - Information Entropy
 describes the uncertainty of the information source. 用于度量’预测随机变量Y取值‘的难度。信息熵越大说明取值的不确定性越大，即预测难度越大。Denoted as H(Y).

Information entropy has different ways of measure:

![Image](https://pic4.zhimg.com/80/v2-d5f495bb90c50dd07e89617585c926f7.png)

------------------------

### - Conditional Information Entropy
Uncertainty of $Y$ conditioned on certain value of $X$. For instance, feature $X$ may take $m$ values, and each has a corresponding $$H(Y|X_k) \ \ \ k \in [m]$$. conditional infomration entropy is then denoted as,

$$H(Y|X) = \sum_{k \in [m]}P(X_k) \cdot H(Y|X_k)$$

where $$P(X_k)$$ is the prior probability.

Conditional information entropy of $$Y$$ on $$X$$ is a weighted sum of all sub-conditional entropy of $$X_k$$.

*The above looks similiar to 'the law of total probability' $$\left(P(Y) = \sum_i P(X_i) \cdot P(Y|X_i)  \right)$$ but not necessarily the case.*



------------------------



### - Information Gain
By how much could the uncertainty be mitigated if we make decision/split on feature $$X$$.

$$Gain(X, Y) = H(Y) - H(Y|X)$$

$$H(Y)$$ is the impurity if no split (for tree) has been made. $$H(Y|X)$$ is the impurity if were to make split on $$X$$. The gain is the benefit of growing tree.




------------------

### - Application of Entropy on Decision Tree

决策树解决的是分类问题。分类问题是基于历史数据，建立预测模型，对未知数据进行分类。

#### Questions to Address :

**1. root node on which feature:** Use greedy algorithm, choose the root node to be the feature with the lowest impurity.

**2. child nodes on which feature(s)**

**3. when to stop growing the tree:** how small the entropy we are aiming for
