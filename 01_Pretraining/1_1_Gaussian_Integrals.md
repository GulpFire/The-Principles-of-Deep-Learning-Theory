# 1.1 高斯积分

本节的目标是介绍高斯积分和高斯概率分布，并最终导出Wick’s theorem（1.45）。该定理为计算多变量高斯分布的任意时刻提供了一个运算公式，并将在全书中使用。

## 单变量高斯积分
让我们慢慢来，从最简单的单变量高斯函数开始，

$$
\begin{aligned}
e^{-\frac{z^2}{2}}
\end{aligned}
\tag{1.1}
$$

该函数的曲线图描绘了著名的钟形曲线，在 $z=0$ 时围绕峰值对称，在大 $|z| \gg 1$ 时迅速变细。(1.1) 本身不能作为概率分布，因为它没有归一化。为了找到适当的归一化，我们需要执行高斯积分

$$
\begin{aligned}
I_1 \equiv \int_{-\infty}^{\infty}dze^{-\frac{z^2}{2}}.
\end{aligned}
\tag{1.2}
$$

作为一个古老的对象函数，计算这样的积分有一个巧妙的技巧。首先，考虑一下它的平方

$$
\begin{aligned}
I^2_1 = {(\int_{-\infty}^{\infty}dz e^{-\frac{z^2}{2}})}^2 = \int^{\infty}_{-\infty}dxe^{-\frac{y^2}{2}} = \int_{-\infty}^{\infty}\int_{-\infty}^{\infty}dxdye^{-\frac{1}{2}(x^2+y^2)},
\end{aligned} 
\tag{1.3}
$$

在中间，我们只是更改了积分变量的名称。接下来，我们将变量更改为极坐标$(x,y)=(r \cos \phi，r \sin \phi)$，这将积分度量转换为 $dxdy=rdrd \phi$，并给出两个基本积分来计算：

$$
\begin{aligned}
I_1^2 = \int_{-\infty}^{\infty}\int_{-\infty}^{\infty}dxdy e^{-\frac{1}{2}(x^2+y^2)} &= \int_0^{\infty}rdr\int_0^{2\pi}d\phi e^{-\frac{r^2}{2}} \\
& = 2 \pi \int_0^{\infty} dr re^{-\frac{r^2}{2}} \\
& = 2 \pi | -e^{-\frac{r^2}{2}}|_{r=0}^{r=\infty} = 2 \pi
\end{aligned}
\tag{1.4}
$$

最后，通过取平方根，我们可以将高斯积分（1.2）计算为

$$
\begin{aligned}
I_1 = \int_{-\infty}^{\infty}dze^{-\frac{z^2}{2}} = \sqrt{2\pi}
\end{aligned}
\tag{1.5}
$$

将高斯函数除以此归一化因子，我们将单位方差的高斯概率分布定义为

$$
\begin{aligned}
p(z) \equiv \frac{1}{\sqrt{2\pi}}e^{-\frac{z^2}{2}}
\end{aligned}
\tag{1.6}
$$

其被标准化了，比如 $\int_{-\infty}^{\infty}dzp(z) = 1$，这种具有零均值和单位方差的分布有时被称为标准正态分布。

将此结果扩展到方差 $K > 0$ 的高斯分布非常容易。相应的归一化因子由下式给出
$$
\begin{aligned}
I_K \equiv \int_{-\infty}^{\infty}dze^{-\frac{z^2}{2K}} = \sqrt{K} \int_{-\infty}^{\infty}du e^{-\frac{u^2}{2}} = \sqrt{2\pi K}
\end{aligned}
\tag{1.7}
$$

在中间，我们将积分变量重新调整为 $u=z/\sqrt{K}$、 然后，我们可以将具有方差 $K$ 的高斯分布定义为

$$
\begin{aligned}
p(z) \equiv \frac{1}{\sqrt{2\pi K}}e^{-\frac{z^2}{2K}}
\end{aligned}
\tag{1.8}
$$

该分布图再次描绘了一条围绕 $z=0$ 对称的钟形曲线，但它现在配备了一个表征其宽度的刻度 $K$，在 $|z| \gg \sqrt {K}$ 时，更一般地，我们可以将钟形曲线的中心移动为

$$
\begin{aligned}
p(z) \equiv \frac{1}{\sqrt{2\pi K}}e^{-\frac{{(z-s)}^2}{2K}}
\end{aligned}
\tag{1.9}
$$

因此它现在围绕 $z＝s$ 对称。这个中心值 $s$ 被称为分布的平均值，因为它是：

$$
\begin{aligned}
\mathbb{E}[z] \equiv \int_{-\infty}^{\infty}dzp(z)z = \frac{1}{\sqrt{2 \pi K}} &= \frac{1}{\sqrt{2 \pi K}}\int_{-\infty}^{\infty}dze^{-\frac{-{(z-s)}^2}{2K}}z \\
&= \frac{1}{I_K} \int_{-\infty}^{\infty} dw e^{-\frac{w^2}{2K}}(s + w) \\
&= \frac{sI_K}{I_K} + \frac{1}{I_K}\int_{-\infty}^{\infty}dw(e^{-\frac{w^2}{2K}}w)
&= s
\end{aligned}
\tag{1.10}
$$

在中间，我们将变量转换为 $w = z-s$ 在最后一步中，注意到第二项的被积函数相对于积分变量 $w$ 的符号翻转是奇数 $w \leftrightarrow -w$，因此积分为零。

关注具有零均值的高斯分布，让我们考虑一般函数 $O(z)$ 的其他期望值，即

$$
\begin{aligned}
\mathbb{E}[O(z)] \equiv \int_{-\infty}^{\infty} dz p(z)O(z) = \frac{1}{\sqrt{2\pi K}} \int_{-\infty}^{\infty}dz e^{-\frac{z^2}{2K}}O(z)
\end{aligned}
\tag{1.11}
$$

我们通常将这些函数 $O(z)$ 称为可观测值，因为它们可以对应于实验的测量结果。一类特殊的期望值称为矩，对应于将 $z^M$ 插入任意整数 $M$ 的被积函数:

$$
\begin{aligned}
\mathbb{E}[z^M] = \frac{1}{\sqrt{2\pi K}} \int_{-\infty}^{\infty} dz \space e^{-\frac{z^2}{2K}} z^M.
\end{aligned}
\tag{1.12}
$$

注意，对于任何奇数指数 $M$，积分值都为 0，因为被积函数相对于符号翻转 $z \leftrightarrow -z$ 是奇数的，对于偶数 $M = 2m$ 的 $z$ 插入，我们需要计算以下形式的积分:

$$
\begin{aligned}
\mathbb{E}[z^M] = \frac{1}{\sqrt{2 \pi K}} \int_{-\infty}^{\infty} dz \space e^{-\frac{z^2}{K}}z^{2m}
\end{aligned}
\tag{1.13}
$$