理解矩阵的迹笔记
------------------------

资料：[如何理解矩阵的迹？](<https://www.matongxue.com/madocs/483/>) 

资料：[为什么矩阵特征值之和等于迹？](<https://zhuanlan.zhihu.com/p/39313619>) 

[TOC]

### 0 前言

线性代数中，把方阵的对角线之和称为“迹”：

![matongxue-matrix-trace-a399492f39dc6e0c4851d2e3e7ff5a8e](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-trace-a399492f39dc6e0c4851d2e3e7ff5a8e.jpg)

“迹”就是线性变换藏在矩阵中痕迹。

### 1 什么是线性变换？

函数，直观地讲就是将 $x$ 轴上的点映射到一条曲线上，如下， $y=\sin(x)$ 函数将 $x$ 轴上的点映射到正弦曲线上：

![matongxue-matrix-trace-e54ff2c6342d0a6fe8577a21ae18b52f](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-trace-e54ff2c6342d0a6fe8577a21ae18b52f.webp)

再如函数 $y=x$，将 $x$ 轴上的点映射到另一条直线上，我们称为线性函数：

![matongxue-matrix-trace-dc047e4394d43f6a08b96aad68f62cd5](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-trace-dc047e4394d43f6a08b96aad68f62cd5.webp)

现在放宽限制，不只考虑 $x$ 上的点，而是考虑整个平面，将平面上任意直线映射到另一条直线上：

![matongxue-matrix-trace-0cb6da2d57b2e52ea59797f95878881f](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-trace-0cb6da2d57b2e52ea59797f95878881f.webp)

其实也是线性函数，只是一般我们称为**线性变换**。

因为自变量不仅限于 $x$ 轴，用 $y=f(x)$ 形式不好表示，于是变成了：$\boldsymbol{y}=A \boldsymbol{x}$，或者写成更像函数的形式：$\boldsymbol{y}=A(\boldsymbol{x})$。

只需知道以下两点就能确定矩阵 $A$：

- 坐标系？线代中称为**基**
- 映射法则？线代中称为**线性变换**

综上两点，所谓矩阵就是指定基下的线性变换。

### 2 什么是相似矩阵？

下面使用网格线及一个参考点（方便观察）来示意整个平面的变换：

![matongxue-matrix-trace-14ddf14d9d61f5e1a40d7ef0fd08e46a](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-trace-14ddf14d9d61f5e1a40d7ef0fd08e46a.webp)

上述变换平面上所有点旋转了 2 弧度。那么该线性变换在不同基下的矩阵是什么样子的？

在**标准正交基**：$\{\boldsymbol{i}=\left[\begin{array}{l}{1} \\ {0}\end{array}\right], \boldsymbol{j}=\left[\begin{array}{l}{0} \\ {1}\end{array}\right]\}$下，用一个旋转矩阵 $A$ 表示此线性变换：
$$
A=\left[\begin{array}{cc}{\cos (2)} & {-\sin (2)} \\ {\sin (2)} & {\cos (2)}\end{array}\right] \approx \left[\begin{array}{cc}{-0.41615} & {-0.90930} \\ {0.90930} & {-0.41615}\end{array}\right]
$$
在另一个基：$\{\boldsymbol{i^{\prime}}=\left[\begin{array}{l}{1} \\ {0.5}\end{array}\right], \boldsymbol{j^{\prime}}=\left[\begin{array}{l}{0.5} \\ {1}\end{array}\right]\}$下，同样用一个旋转矩阵 $B$ 表示此线性变换：
$$
B=P^{-1} A P \approx \left[\begin{array}{cc}{-1.62854} & {-1.51550} \\ {1.51550} & {0.79625}\end{array}\right]
$$
同一个线性变换在不同基下的矩阵，就是相似矩阵，$A$ 和 $B$ 互为相似矩阵。

### 3 相似矩阵的迹相等

这个线性变换在两个相似矩阵 $A$ 和 $B$ 中留下了痕迹，就是两矩阵的主对角线之和相等，矩阵主对角线之和称为**迹**。

从另外一个观点来看，我们也可以认为“迹”与坐标无关，“迹”是相似不变量。

另，下面会论述为什么矩阵特征值之和等于矩阵的迹。

### 4 迹、行列式、特征值

**行列式**

由于矩阵 $A$ 和 $B$ 代表同一线性变换，根据行列式的意义——行列式是线性变换的伸缩因子，所以行列式大小也与坐标无关：$|A|=|B|$，行列式又是一个相似不变量。

**特征值**

根据特征值分解，特征值矩阵 $\Lambda$：
$$
\Lambda=Q_{A}^{-1} A Q_{A}=Q_{B}^{-1} B Q_{B}
$$
可见，$\Lambda$ 与 $A$ 和 $B$ 也互为相似矩阵。

由 $\Lambda$ 可得：$tr\left( \Lambda \right)=\sum_{i=1}^{n} \lambda_{i}=tr\left( A \right)=tr\left( B \right)$ 

不失一般性：

- $tr\left( A \right)=\sum_{i=1}^{n} \lambda_{i}$ 
- $det\left( A \right)=\prod_{i=1}^{n} \lambda_{i}$ 

其中，$\lambda_{i}$ 为矩阵 $A$ 的特征值。

### 5 特征值之和等于迹

为什么矩阵特征值之和等于迹？
$$
|\lambda I-A|=\left|\begin{array}{cccc}{\lambda-a_{11}} & {-a_{12}} & {\dots} & {-a_{1 n}} \\ {-a_{21}} & {\lambda-a_{22}} & {\dots} & {-a_{2 n}} \\ {\dots} & {\dots} & {\dots} & {\dots} \\ {-a_{n 1}} & {-a_{n 2}} & {\dots} & {\lambda-a_{n n}}\end{array}\right|=0
$$
上式是一个以 $\lambda$ 为未知数的一元 n 次方程，也称为 n 阶方阵 $A$ 的**特征方程**，显然 $A$ 的特征值就是该方程的解。

特征方程在复数范围内恒有解，其个数为方程的次数（重根按重数计算），因此 n 阶方阵 $A$ 有 n 个特征值。

将特征方程写成**多项式形式**：
$$
a_{0}+\sum_{k=1}^{n} a_{k} \lambda^{k}=0
$$
其中，$a_{k}$ 是相应 k 次项系数。由**韦达定理**（也称根与系数关系），有：
$$
\sum_{k=1}^{n} \lambda_{k}=-\frac{b_{n-1}}{b_{n}}
$$
其中，$\sum_{k=1}^{n} \lambda_{k}$ 是特征值之和。

此外，容易看出 $b_{n}=1$，进而：
$$
\sum_{k=1}^{n} \lambda_{k}=-b_{n-1}
$$
现在问题转变成求解特征多项式 n-1 项系数 $b_{n-1}$。

根据行列式定义，行列式是对应矩阵不同行不同列项的乘积之和，易知上述行列式除了对角线各项的乘积之外，其余的 $\lambda$ 次数都小于 n-1，因此所求 n-1 项系数 $b_{n-1}$ 就是 $(\lambda-a_{11}) (\lambda-a_{22}) \cdots (\lambda-a_{nn})$ 中 $\lambda^{n-1}$ 的系数，即：
$$
b_{n-1}=-\left( a_{11}+a_{22}+\cdots+a_{nn} \right)
$$
进而：
$$
\sum_{k=1}^{n} \lambda_{k}=\sum_{k=1}^{n} a_{kk}=tr \left( A \right)
$$


综上所述，**矩阵特征值之和等于矩阵的迹**。

### 6 一点补充

高次韦达定理是什么？如何证明？

**韦达定理**，也称根与系数的关系。初中阶段便学过一元二次方程的韦达定理，那么推广到高次方程又是怎样的呢？

设一元 n 次方程：
$$
\sum_{k=0}^{n} a_{k} x^{k}=0, a_n \neq 0
$$
有 n 个根分别记为 $\lambda_{1}, \lambda_{2}, \cdots , \lambda_{n}$，于是
$$
a_{n} \prod_{k=1}^{n} \left( x-\lambda_{k} \right)=0
$$
展开连乘式，写出 $x^{k}$ 的系数，即原方程系数 $a_{k}$：
$$
\frac{a_{0}}{a_{n}}=\prod_{k=1}^{n} (-\lambda_{k})=(-1)^{n} \prod_{k=1}^{n} \lambda_{k}
$$


依此类推：
$$
\frac{a_{1}}{a_{n}}=(-1)^{n-1} \sum_{j=1}^{n} \prod_{k \neq j} \lambda_{k} \\
\frac{a_{2}}{a_{n}}=(-1)^{n-2} \sum_{i \lt j} \prod_{k \neq i, k \neq j} \lambda_{k} \\
\cdots \\
\frac{a_{n-1}}{a_{n}}=-\sum_{k=1}^{n} \lambda_{k}
$$
以上。

