理解矩阵特征值笔记
----------------------------

资料：[如何理解矩阵特征值和特征向量？](<https://www.matongxue.com/madocs/228/>) 

[TOC]

### 一、前言

如果将矩阵看成是运动，对于运动来说，最重要的当然就是运动速度和方向，那么（后面会说明限制条件）：

- 特征值就是运动的速度
- 特征向量就是运动的方向

既然运动最重要的两方面都被描述了，特征值、特征向量自然可以称为运动（即矩阵）的特征。

### 二、几何意义

下图 $\vec{i}, \vec{j}$ 为向量空间的基，$\vec{v}$ 为空间中一向量：

![matongxue-matrix-eigenvalue-9c697544d33a102f75e33dfc1fc2bcd3](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-9c697544d33a102f75e33dfc1fc2bcd3.jpg)

将 $\vec{v}$ 左乘一矩阵 $A$：

![matongxue-matrix-eigenvalue-72998d1d940aec9a4e79fd4548cfc32b](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-72998d1d940aec9a4e79fd4548cfc32b.jpg)

看上去没有什么特殊的，那么我们调整下 $\vec{v}$ 的方向：

![matongxue-matrix-eigenvalue-d1f9c14af565b0833c07e5f009c4022d](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-d1f9c14af565b0833c07e5f009c4022d.jpg)

看上去有些特殊了，调整后的 $\vec{v}$ 和 $A \vec{v}$ 共线，只是长度发生了变化。此时，我们称 $\vec{v}$ 为矩阵 $A$ 的特征向量，而 $A \vec{v}$ 的长度是 $\vec{v}$ 的 $\lambda$ 倍，$\lambda$ 就是对应的特征值。

从而，特征值与特征向量的定义式如下：
$$
A \vec{v}=\lambda \vec{v}
$$
**向量 $\vec{v}$ 在矩阵 $A$ 的作用下，保持方向不变，进行比例为 $\lambda$ 的伸缩。**

矩阵 $A$ 的特征值可能有多个：

![matongxue-matrix-eigenvalue-251d988d7f010e199b9f8895dd4dcd43](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-251d988d7f010e199b9f8895dd4dcd43.jpg)

可以容易地从 $A \vec{v}$ 相对于 $\vec{v}$ 是伸还是缩看出特征值 $\lambda$ 是大于 1 还是小于 1。

从特征向量和特征值的定义式还可以看出，特征向量所在直线上的向量都是特征向量：

![matongxue-matrix-eigenvalue-b48642e5416d3130656ff23b7a2fc385](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-b48642e5416d3130656ff23b7a2fc385.jpg)

### 三、运动速度与方向

一般来说，矩阵我们可以看作某种运动，而二维向量可以看作平面上的一个点（或一个箭头）。点是可以观察的，但是运动是不能直接观察的。

要观察矩阵所代表的运动，需要把它附加到向量上才观察的出来：

![matongxue-matrix-eigenvalue-f190e6c5f9187211b72972c1fc7e5316](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-f190e6c5f9187211b72972c1fc7e5316.jpg)

似乎还不明显，但如果反复使用矩阵乘法的话：

![matongxue-matrix-eigenvalue-61e8b943d50f007d9ceaae98dc347671](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-61e8b943d50f007d9ceaae98dc347671.jpg)

反复运用矩阵乘法，矩阵所代表的运动的最明显的特征，即速度最大的方向，就由**最大特征值**对应的特征向量展现了出来。

除了最大的特征值之外，其他特征值代表什么速度后面进行说明，这里暂时跳过。

对于复数的特征值、特征向量，反复运用矩阵乘法的结果是围绕着原点在旋转。关于复数特征值和特征向量这里就不展开来说了。

下面我们将斐波那契数列的计算写成矩阵形式：
$$
\left[\begin{array}{c}{T_{t+1}} \\ {T_{t}}\end{array}\right]=\left[\begin{array}{ll}{1} & {1} \\ {1} & {0}\end{array}\right]\left[\begin{array}{c}{T_{t}} \\ {T_{t-1}}\end{array}\right]
$$
根据斐波那契数列，我们从 $\left[\begin{array}{l}{1} \\ {1}\end{array}\right]$ 点开始：

![matongxue-matrix-eigenvalue-612aff369f8df64b0037d477d1a12ab4](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-612aff369f8df64b0037d477d1a12ab4.jpg)

可以看到，值会沿着特征值最大的特征向量方向爆炸增长，很快突破10万、100万、1000万。

### 四、特征值分解

下面要用到矩阵乘法和相似矩阵的知识，参看：[从高斯消元法到矩阵乘法](<https://link.zhihu.com/?target=https%3A//www.matongxue.com/madocs/755.html>)、[如何理解矩阵乘法？](<https://link.zhihu.com/?target=https%3A//www.matongxue.com/madocs/555.html>) 以及 [如何理解相似矩阵？](<https://link.zhihu.com/?target=https%3A//www.matongxue.com/madocs/491.html>) 

对于矩阵 $A$，如果可以对角化的话，可以通过相似矩阵进行如下特征值分解：
$$
A=P \Lambda P^{-1}
$$
其中，对角阵 $\Lambda$ 的对角元素为 $A$ 的特征值，$P$ 的列向量为单位化的 $A$ 的特征向量。

举个栗子：

![matongxue-matrix-eigenvalue-0b4454a26a3a6ee7994f287134499807](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-0b4454a26a3a6ee7994f287134499807.jpg)

对于方阵而言，矩阵不会进行维度的升降，所以矩阵代表的运动实际上只有两种：**旋转**和**伸缩**。最后的运动结果就是两者的合成。

再来看刚刚的特征值分解，实际上将运动分解开了：

![matongxue-matrix-eigenvalue-c0adfb121cb5bbb96b7820818d1d0b1a](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-c0adfb121cb5bbb96b7820818d1d0b1a.jpg)

我们来看看几何上的表现：

![matongxue-matrix-eigenvalue-71d7badec115532054e9d598c4859001](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-71d7badec115532054e9d598c4859001.jpg)

先左乘 $P$：

![matongxue-matrix-eigenvalue-85ad14351ed296444aa2109f2c538a35](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-85ad14351ed296444aa2109f2c538a35.jpg)

如果旋转前的基不正交，旋转之后变为了标准基，那么实际会产生伸缩，所以之前说的正交很重要。

再左乘 $\Lambda$：

![matongxue-matrix-eigenvalue-1012c631dcf3dd175421c0ddfc5c29f3](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-1012c631dcf3dd175421c0ddfc5c29f3.jpg)

于是，之前的旋转是相当于指明了拉伸的方向，这就解释了：

- 特征值就是拉伸的比例
- 特征向量指明了拉伸的方向

回到我们之前说的运动上去，特征值就是运动的速度，特征向量就是运动的方向，而其余方向的运动就由特征向量方向的运动合成。所以最大的特征值对应的特征向量指明了运动速度的最大方向。

最后左乘 $P^{-1}$：

![matongxue-matrix-eigenvalue-7ac220da0a5b8c35b24fad7e3cfa2df5](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-7ac220da0a5b8c35b24fad7e3cfa2df5.jpg)

但是，再次重申，上面的推论有一个**重要**的条件，特征向量正交，这样变换后才能保证变换最大的方向在基方向。如果特征向量不正交就有可能不是变化最大的方向。

所以我们在实际应用中，都要先去找正交基。但是特征向量很可能不是正交的，那么我们就需要奇异值分解了，这里就不展开了。

### 五、特征值/向量的应用

**控制系统**

$\lambda=1$ 的系统最终会趋于稳定：

![matongxue-matrix-eigenvalue-fdb2c920b757621e2b9809e6c30bb591](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-fdb2c920b757621e2b9809e6c30bb591.jpg)

**图片压缩**

有一个 $512 \times 512$ 的图片（方阵）如下：

![matongxue-matrix-eigenvalue-f402fd85430d3b3b6672c7f2b0d7af2e](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-matrix-eigenvalue-f402fd85430d3b3b6672c7f2b0d7af2e.jpg)

将图片每个像素的颜色值填入矩阵 $A \in \mathbb{R}^{512 \times 512}$ 中，然后进行特征值分解：$A=P \Lambda P^{-1}$。对角阵 $\Lambda$ 的对角元素（特征值）按从大到小排列，只保留前 50 个，其他置为 0，重新计算矩阵后恢复成如下图片：

![matongxue-matrix-eigenvalue-146bb0a9f96aebc6a90d6fb58ef091d4](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\matongxue-quadratic-form-146bb0a9f96aebc6a90d6fb58ef091d4.jpg)

效果还阔以。其实一两百个特征值之和可能就占了所有特征值和的百分之九十了，其他的特征值都可以丢弃了。

另，以上只考虑特征值是实数的情况。若考虑虚数/复数的情况，**矩阵特征值是对特征向量进行伸缩和旋转程度的度量**，实数是只控制伸缩，虚数是只控制旋转，复数就是有伸缩有旋转。