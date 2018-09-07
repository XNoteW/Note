# 理论基础

## 数学优化

**数学优化问题**或者**优化问题**可以写作如下形式

$$
\begin{aligned}
\min\; &f_0(x) \\
\text{s.t. } & f_i(x) \leq b_i, i = 1,2,\cdots,m
\end{aligned}
$$

这里, 向量 $x = (x_1,x_2,\cdots,x_n)^T\in \mathbb{R}^n$ 称为问题的**优化变量**, 函数 $f_0: \mathbb{R}^n \rightarrow \mathbb{R}$ 称为**目标函数**, 函数 $f_i: \mathbb{R}^n \rightarrow \mathbb{R}, i = 1,2,\cdots,m$, 被称为**约束函数**, 常数 $b_1,b_2,\cdots, b_m$ 被称为约束上限或约束边界. 如果在所有满足约束条件的向量中 $x^*$ 对应的目标函数值最小: 即对于任意满足约束 $f_1(z) \leq b_1, \cdots, f_m(z) \leq b_m$ 的向量 $z$, 有 $f_0(z) \geq f_0(x^*)$, 那么称 $x^*$ 为问题的**最优解**或者**解**.

对于任意 $i \in \{0,1,2, \cdots,m\}$, 若 $f_i$ 均是线性函数, 即对任意的 $x, y \in \mathbb{R}^n$ 和 $\alpha, \beta \in \mathbb{R}$ 有

$$
f_i(\alpha x + \beta y) = \alpha f_i(x) + \beta f_i(y)
$$

则此优化问题被称为**线性规划**. 若优化问题不是线性的, 称之为非线性规划.

若目标函数和约束函数均是凸函数, 即对任意的 $x, y \in \mathbb{R}^n$ 和 $\alpha, \beta \in \mathbb{R}, \alpha + \beta = 1,\alpha \geq 0, \beta \geq 0$ 有

$$
f_i(\alpha x + \beta y) \leq \alpha f_i(x) + \beta f_i(y)
$$

则称优化问题为**凸优化问题**.

![凸优化分类](../img/凸优化分类.png)

某类问题的**求解方法**是指 (以给定精度) 求解此类优化问题中的某一实例的算法. 如果某个问题中每个约束函数仅仅取决于为数不多的几个变量, 那么此问题是**稀疏**的.

## 最小二乘

最小二乘问题: $m=0$, 且

$$
f_0(x) = ||Ax-b||_2^2 = \displaystyle\sum_{i=1}^k (a_i^Tx_i - b_i)^2
$$

其中 $A \in \mathbb{R}^{k \times n}, k \geq n$, $a_i^T$ 是矩阵 $A$ 的行向量. 向量 $x \in \mathbb{R}^n$ 是优化变量.