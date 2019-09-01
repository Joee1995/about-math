二次型的意义笔记
-------------------------

资料：[如何理解二次型？](<https://www.matongxue.com/madocs/271/>) 

[TOC]

### 一、二次函数（方程）的特点

二次函数：

![matongxue-quadratic-form-1269517998d6a434999ead02cc8fdcb9](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-1269517998d6a434999ead02cc8fdcb9.webp)

二次方程：

![matongxue-quadratic-form-21b6e595b744ca7efefcc4c5fda9cd23](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-21b6e595b744ca7efefcc4c5fda9cd23.webp)

对于二次函数或者二次方程，二次部分是主要部分，往往研究二次这部分就够了。

### 二、通过矩阵研究二次方程

我们将含有 $n$ 个变量的二次齐次函数称为**二次型**：
$$
f\left(x_{1}, x_{2}, \cdot, x_{n}\right)=a_{11} x_{1}^{2}+a_{22} x_{2}^{2}+\cdots+a_{n n} x_{n}^{2}+2 a_{12} x_{1} x_{2}+2 a_{13} x_{1} x_{3}+\cdots+2 a_{n-1, n} x_{n-1} x_{n}
$$
可以通过**二次型矩阵**来表示二次型：
$$
x^{2}+y^{2}-x y=1 \\
\left[\begin{array}{ll}{\boldsymbol{x}} & {\boldsymbol{y}}\end{array}\right]\left[\begin{array}{cc}{1} & {-0.5} \\ {-0.5} & {1}\end{array}\right]\left[\begin{array}{l}{\boldsymbol{x}} \\ {\boldsymbol{y}}\end{array}\right]=\mathbf{1}
$$


更一般的：
$$
a x^{2}+2 b x y+c y^{2}=1 \\
\left[\begin{array}{ll}{\boldsymbol{x}} & {\boldsymbol{y}}\end{array}\right]\left[\begin{array}{ll}{\boldsymbol{a}} & {\boldsymbol{b}} \\ {\boldsymbol{b}} & {\boldsymbol{c}}\end{array}\right]\left[\begin{array}{l}{\boldsymbol{x}} \\ {\boldsymbol{y}}\end{array}\right]=\mathbf{1}
$$
写成更线代的形式：
$$
\boldsymbol{X}^{T} \boldsymbol{A} \boldsymbol{X}
$$
有如下对应关系：
$$
对称矩阵 \Longleftrightarrow 二次型矩阵 \Longleftrightarrow 二次型
$$
通过矩阵来研究二次型有什么好处？

考虑如下圆及对应的二次型矩阵：

![matongxue-quadratic-form-9cebb201788a3f28c5124237f7427c15](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-9cebb201788a3f28c5124237f7427c15.jpg)

现在改变一下二次型：

![matongxue-quadratic-form-702effd53c980e191b53dd549ddb7770](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-702effd53c980e191b53dd549ddb7770.jpg)

可以看到，椭圆和圆之间是线性关系（可以通过线性变换进行转换）。

继续改变：

![matongxue-quadratic-form-979407d3adbe4ae4683839076a5385ee](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-979407d3adbe4ae4683839076a5385ee.jpg)

双曲线和圆之间也是线性关系。

其实圆、椭圆、双曲线之间关系很紧密的，统称为圆锥曲线，都是圆锥体和平面的交线：

![matongxue-quadratic-form-5f8d17a5235be0ed100b1163b83cb0bb](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-5f8d17a5235be0ed100b1163b83cb0bb.webp)

可以看到，一个平面在圆锥体上运动得到了圆、椭圆、双曲线，这也是它们之间具有线性关系的来源（平面的运动实际上是线性的）。

**什么是二次型的规范化？**

考虑如下椭圆及对应二次型矩阵：

![matongxue-quadratic-form-618a807b6d61dd60afe77ae7c533bfed](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-618a807b6d61dd60afe77ae7c533bfed.jpg)

这个椭圆看起来有点歪，不太好处理，我们来把它扶正，这就叫做**规范化**。

往下读之前可以先参看 [如何理解特征值？](./matongxue-matrix-eigenvalue.md)。

首先，矩阵代表运动，包含：旋转、伸缩、投影。

对于方阵，由于没有维度改变，所以没有投影运动，只包含：旋转、伸缩。

具体到以上栗子：

![matongxue-quadratic-form-e97c0dfe201263e9ffc85817b91a8403](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-e97c0dfe201263e9ffc85817b91a8403.jpg)

将矩阵进行特征值分解：
$$
A=\left[\begin{array}{cc}{2} & {-1} \\ {-1} & {2}\end{array}\right]=
\left[\begin{array}{cc}{-\frac{\sqrt{2}}{2}} & {\frac{\sqrt{2}}{2}} \\ {\frac{\sqrt{2}}{2}} & {\frac{\sqrt{2}}{2}}\end{array}\right]
\left[\begin{array}{cc}{3} & {0} \\ {0} & {1}\end{array}\right]
\left[\begin{array}{cc}{-\frac{\sqrt{2}}{2}} & {\frac{\sqrt{2}}{2}} \\ {\frac{\sqrt{2}}{2}} & {\frac{\sqrt{2}}{2}}\end{array}\right]
$$
实际上我们是将运动分解成了**伸缩部分**和**旋转部分**，那么我们只需保留伸缩部分就相当于把矩阵扶正了：

![matongxue-quadratic-form-5abd5b651832797d1b74922e635f98dd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-5abd5b651832797d1b74922e635f98dd.jpg)

所以，用二次型矩阵进行规范化是非常轻松的事情。

**什么是二次型的正定？**

正定是对二次型函数有效的一个定义，对方程无效。

对于二次型函数 $f(x)=x^{T} A x$：

- $\forall x \neq 0, x \in \mathbb{R}, s.t. f(x) \gt 0$，$f$ 为正定二次型，$A$ 为正定矩阵
- $\forall x \neq 0, x \in \mathbb{R}, s.t. f(x) \ge 0$，$f$ 为半正定二次型，$A$ 为半正定矩阵
- $\forall x \neq 0, x \in \mathbb{R}, s.t. f(x) \lt 0$，$f$ 为负定二次型，$A$ 为负定矩阵
- $\forall x \neq 0, x \in \mathbb{R}, s.t. f(x) \le 0$，$f$ 为半负定二次型，$A$ 为半负定矩阵

- 以上都不是就叫做不定

从图像来看：

正定：

![matongxue-quadratic-form-ebdfb7c7510ac85a582d6e79c1ef37b3](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-ebdfb7c7510ac85a582d6e79c1ef37b3.jpg)

半正定：

![matongxue-quadratic-form-99b76aece0306301d4b983bf4a30f048](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-99b76aece0306301d4b983bf4a30f048.jpg)

不定：

![matongxue-quadratic-form-374e0eef3c259af60bef57c22beb937e](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-374e0eef3c259af60bef57c22beb937e.jpg)

既然二次型能够用矩阵表示，那么能否用矩阵来判断正负定呢？答案显然是肯定的。

这里只简单说一下结论，**若矩阵 $A$ 的所有特征值都大于 0 则为正定矩阵**。

### 三、总结

在很多学科里，二次型都是主要研究对象，很多问题都可以转为二次型。线代作为一门数学工具，在二次型的研究中也发挥了很好的作用。