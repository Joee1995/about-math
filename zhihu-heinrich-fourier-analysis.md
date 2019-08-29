傅里叶分析笔记
------------------

教程：[傅里叶分析之掐死教程（完整版）](<https://zhuanlan.zhihu.com/p/19763358>) 

[TOC]

### 一、什么是频域

从我们出生开始，我们看到的世界都是以时间贯穿，所有的一切都会随着时间而改变。这种以时间为参照来观察动态世界的方法称为时域分析。我们也理所当然地认为世界就应该是动态的，永远不会静止。然而事实上当从另一个角度来观察世界的时候，我们会发现**世界是永恒不变的**，这个静止的世界叫做**频域**。

举一个**公式上不准确**但意义上非常贴切的栗子：

我们普通人对一段音乐最普遍的理解：一个随着时间变化的震动。

![2ca39677363c65a305207a5491b75825_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_2ca39677363c65a305207a5491b75825.jpg)

对于学音乐的人来说，更直观的理解：很多在时间上离散的频率。

![8e1fce9d7607d97cebf73e1f36f03f06_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_8e1fce9d7607d97cebf73e1f36f03f06_hd.jpg)

将以上两图简化后：

时域：

![d4fa1de0327eb491a6941ac84a56e432_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_d4fa1de0327eb491a6941ac84a56e432_hd.jpg)

频域：

![1ca366b593d877a16c8a49773774b5b9_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_1ca366b593d877a16c8a49773774b5b9_hd.jpg)

在时域，我们看到的是钢琴上的琴键不停地跳动，而在频域，却只是一个静止的音符。

傅里叶告诉我们，**任何周期函数，都可以看作是不同振幅，不同相位正弦波的叠加**。

而贯穿时域与频域的方法之一，就是传中说的**傅里叶分析**。傅里叶分析可分为傅里叶级数（Fourier Serie）和傅里叶变换（Fourier Transformation）。

### 二、傅里叶级数

> 关键词：从侧面看！！！

举个栗子，用正弦曲线波叠加出一个带90度角的矩形波：

![055bf33bb84555a952804c5dbeb75dd9_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_055bf33bb84555a952804c5dbeb75dd9_hd.jpg)

第一幅图是1个正弦波： $\cos(t)$ 

第二幅图是2个正弦波的叠加： $\cos(t)$ + $a\cdot\cos(3t)$ 

第三幅图是4个正弦波的叠加

第四幅图是10个正弦波的叠加

随着正弦波数量逐渐的增长，最终会叠加成一个标准的矩形。但是要多少个正弦波叠加起来才能形成一个标准90度角的矩形波呢？答案是无穷个。

不仅仅是矩形，你能想到的任何波形都是可以如此方法用正弦波叠加起来的。

现在换个角度来看：

![563deb4a6599d052b3ba108661872c57_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_563deb4a6599d052b3ba108661872c57_hd.jpg)

前面黑线是正弦波叠加而成的波形，后面依次是参与叠加的不同频率的正弦波（图中的直线是振幅为0的正弦波，即为组成某些特定波形，有些频率的正弦波成分是不需要的），称为频率分量。

对于有理数轴，数字“1”是基本单元。

而在这里，我们将第一个频率最低的分量看作“1”，就有了构建频域的基本单元。

如果我们将一个角频率为 $\omega_{0}$ 的正弦波 $\cos(\omega_{0}t)$ 看作基础，那么频域的基本单元就是 $\omega_{0}$ 。

有了“1”还要有“0”，频域的“0”，$\cos(0t)$ 是一个周期无限大的正弦波，也就是一条直线！所以在频域，0频率也被称为直流分量，在傅里叶级数的叠加中，它仅仅影响全部波形相对于数轴整体向上或是向下而不改变波的形状。

如何定义正弦波：

![zhihu-heinrich-fourier-analysis_81ca9447d6c45c162c2d76df75a6690a](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_81ca9447d6c45c162c2d76df75a6690a.jpg)

正弦波就是一个圆周运动在一条直线上的投影。所以频域的基本单元也可以理解为一个始终在旋转的圆：

![Fourier_series_square_wave_circles_animation](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_841476e8e15e1d08114b65c50b741930.gif)

所以，一个矩形波在频域里的模样：

![e2e3c0af3bdbcba721c5415a4c65da9e_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_e2e3c0af3bdbcba721c5415a4c65da9e.jpg)

很难理解？那就看看相应的频域图像，也就是俗称的频谱：

![zhihu-heinrich-fourier-analysis_19679c871bd33d94e2fc8b174f0d14ab](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_19679c871bd33d94e2fc8b174f0d14ab.jpg)

再清楚一点：

![40cf849e55ed95732a60b52d4019d609_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_40cf849e55ed95732a60b52d4019d609.jpg)

动态图：

![zhihu-heinrich-fourier-analysis_h4bd765he25e2d0h214b65c50b742i30.gif](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_h4bd765he25e2d0h214b65c50b742i30.gif.gif)

### 三、傅里叶级数的相位谱

> 关键词：从下面看！！！

傅里叶分析究竟是干什么用的？滤波，求微分方程，等等。很多在时域看似不可能做到的数学操作，在频域相反很容易。这就是需要傅里叶变换的地方。

下面说相位谱。

从侧面看的频率谱并没有包含时域中全部的信息。因为频谱保存了振幅和频率信息，而没有提及相位信息。在基础正弦波 $A\cdot\sin(\omega_{t}+\theta)$ 中，振幅、频率、相位缺一不可，相位决定了波的位置。

![zhihu-heinrich-fourier-analysis_07199fc0250791d768771b50c098e26a](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_07199fc0250791d768771b50c098e26a.jpg)

鉴于正弦波是周期的，需要设定一个用来标记正弦波位置的东西。在图中就是那些小红点。小红点是距离频率轴最近的波峰。

![zhihu-heinrich-fourier-analysis_e1985fe86283a7b14d1fc7e11d322fcb](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_e1985fe86283a7b14d1fc7e11d322fcb.jpg)

这里需要纠正一个概念：时间差并不是相位差。如果将整个周期看作 $2\pi$ 的话，相位差则是时间差在一个周期中所占的比例，即 $2\pi\frac{t}{T}$。人为定义相位谱的值域为 $(-\pi，\pi]$。

最后来张大合集：

![4695ce06197677bab880cd55b6846f12_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_4695ce06197677bab880cd55b6846f12.jpg)

### 四、傅里叶变换

傅里叶级数的本质是将一个连续的周期信号分解成无限个离散的正弦波，在时域是一个周期连续的函数，而在频域是一个非周期离散的函数。

但是宇宙似乎并不是周期的。

那么是否有一种数学工具能将连续非周期信号变换为周期离散信号呢？答案是没有。

比如傅里叶级数，在时域是一个**周期连续**的函数，而在频域是一个**非周期离散**的函数。

下面的傅里叶变换，可以将一个时域**非周期连续**的信号转换为一个在频域**非周期连续**的信号。

上图：

![zhihu-heinrich-fourier-analysis_419cd0b2e965aca25d5f8a5a6362d728](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_419cd0b2e965aca25d5f8a5a6362d728.jpg)

换一个角度理解：傅里叶变换实际上是对一个周期无限大的函数进行傅里叶级数分解。

如上图，傅里叶变换在频域上就从离散谱变成了连续谱。

第一节提到，关于乐谱的栗子是**公式错误但概念典型**的，那么公式错误在哪里呢？

错误就在于，乐谱其实并非一个连续的频谱，而是很多在时间轴上离散的频率。

离散谱：

![a185be412974fd73a7925cf1f1cc5372_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_a185be412974fd73a7925cf1f1cc5372.jpg)

连续谱：

![ece53f825c6de629befba3de12f929a7_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_ece53f825c6de629befba3de12f929a7.jpg)

原来离散谱的叠加，变成了连续谱的累积。所以在计算上也从求和符号变成了积分符号。

### 五、第一耍帅公式：欧拉公式

前置，虚数的意义，$i^2=-1$：

![42e1f6dc43e8868b4962f5ba389a5df4_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_42e1f6dc43e8868b4962f5ba389a5df4.jpg)

数轴上红色的线段长度是1。当它乘以3的时候，变成了蓝色的线段；而当它乘以-1的时候，变成了绿色的线段，或者说在数轴上围绕原点旋转了180度。

我们知道，乘-1其实就是乘了两次 i，线段旋转了180度，那么乘一次 i 呢？答案就是旋转了90度。

![3e88e9463e4667e50ebdda51dee88358_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_3e88e9463e4667e50ebdda51dee88358.jpg)

由此，我们了解到乘虚数 i 的一个功能，**旋转**。

接下来，欧拉公式登场：
$$
e^{i x}=\cos x+i \sin x
$$
欧拉公式在数学领域的意义远不止于傅里叶分析。

但在傅里叶分析中，这个公式关键的作用，是将正弦波统一成了简单的指数形式。

图像含义：

![974efc6a99e06dcd623193e960ccbe93_hd](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_974efc6a99e06dcd623193e960ccbe93.jpg)

欧拉公式所描绘的是一个随时间变化，在复平面上做圆周运动的点，在时间轴上成了一条螺旋线。如果只看它的实数部分，即左侧的投影，就是一个余弦函数，而右侧的投影，则是一个正弦函数。

关于复数更深的理解，可以参考：[复数的物理意义是什么？](<http://www.zhihu.com/question/23234701/answer/26017000>)。

### 六、指数形式的傅里叶变换

在欧拉公式的帮助下我们知道：**正弦波的叠加**也可以理解为**螺旋线的叠加**在实数空间的投影。

可以用两种方式来理解正弦波：

第一种就是螺旋线在实轴的投影。

第二种要借助欧拉公式的另一种形式去理解：
$$
\begin{aligned} e^{i t} &=\cos (t)+i . \sin (t) \\ e^{-i t} &=\cos (t)-i . \sin (t) \end{aligned}
$$
将以上两式相加再除2，得到：
$$
\cos (t)=\frac{e^{i t}+e^{-i t}}{2}
$$
如何理解这个式子？

$e^{it}$ 可以理解为一条逆时针旋转的螺旋线，而 $e^{-it}$ 则可以理解为一条顺时针旋转的螺旋线。而 $\cos(t)$ 是这两条旋转方向不同的螺旋线叠加的一半，因为这两条螺旋线的虚数部分相互抵消掉了！

这里，逆时针旋转的称为正频率，而顺时针旋转的称为负频率。

至此，想象一下，连续的螺旋线会是什么样子：

![zhihu-heinrich-fourier-analysis_f116ae26859bdc80b28ea0f8f894ccc0](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_f116ae26859bdc80b28ea0f8f894ccc0.jpg)

猜猜这个图形在时域是什么样子？

![zhihu-heinrich-fourier-analysis_0fdfa0a9b6eea036703ab2499381080c](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_0fdfa0a9b6eea036703ab2499381080c.jpg)

最后，用一张图总结以下：

![zhihu-heinrich-fourier-analysis_097c9051af221c171730d4bc8f436a72](C:\Users\Joee\Desktop\github\homepage\about-math\static\images\zhihu-heinrich-fourier-analysis_097c9051af221c171730d4bc8f436a72.jpg)