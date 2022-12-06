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

作为几乎与（1.2）一样古老的对象，再次有一个巧妙的技巧来评估它们：

$$
\begin{aligned}
    I_{K,M} &= \int_{-\infty}^{\infty}dz \space e^{-\frac{z^2}{2K}}z^{2m} = {(2K^2\frac{d}{dK})}^m \int_{-\infty}^{\infty}dz e^{-\frac{z^2}{2K}} = {(2K^2 \frac{d}{dK})}^mI_K \\
    &= {(2K^2\frac{d}{dK})}^m \sqrt{2\pi}K^{\frac{1}{2}} = \sqrt{2\pi}K^{\frac{2m+1}{2}}(2m-1)(2m-3)...1,
\end{aligned}
\tag{1.14}
$$

在第二行中，我们用表达式（1.7）代替了$I_K$。因此，我们看到偶矩由简单的公式1给出

$$
\begin{aligned}
\mathbb{E}[z^{2m}] = \frac{I_{K,m}}{\sqrt{2\pi K}} = K^m (2m-1)!!,    
\end{aligned}
\tag{1.15}
$$

在这里我们引入了双阶乘

$$
\begin{aligned}
(2m-1)!! \equiv (2m-1)(2m-3)...1 = \frac{(2m)!}{2^mm!}
\end{aligned}
\tag{1.16}
$$

结果（1.15）是单变量高斯分布的 Wick’s theorem。

实际上还有另一种很好的推导方法（1.15），它可以更自然地扩展到多变量高斯分布。这个推导从考虑带有源项 $J$ 的高斯积分开始，我们将其定义为

$$
\begin{aligned}
Z_{K,J} = \int_{-\infty}^{\infty} dz \space e^{-\frac{z^2}{2K}+Jz}. 
\end{aligned}
\tag{1.17}
$$

注意，当将源设置为零时，我们恢复了高斯积分的归一化，给出了关系 $Z_{K,J}=0=I_K$。在物理学文献中，$Z_{K,J}$ 有时被称为`带源的分函数`，正如我们很快将看到的，这个积分用作矩的`生成函数`。我们可以通过完成指数的平方来计算 $Z_{K,J}$

$$
\begin{aligned}
-\frac{z^2}{2K}+Jz = -\frac{{(z-JK)}^2}{2K}+\frac{KJ^2}{2},
\end{aligned}
\tag{1.18}
$$

这允许我们将积分（1.17）重写为

$$
\begin{aligned}
Z_{K,J} =  e^{-\frac{KJ^2}{2}} \int_{-\infty}^{\infty} e^{-\frac{{(z-JK)}^2}{2K}} = e^{\frac{KJ^2}{2}}\sqrt{2\pi K}
\end{aligned}
\tag{1.19}
$$

其中，在中间等式中，我们注意到被积函数只是一个带方差 $K$ 的移位高斯函数。

现在，我们可以将带有源 $Z_{K,J}$ 的高斯积分与带有插入 $I_{K,m}$ 的高斯积分联系起来。通过将 $Z_{K,J}$ 相对于源 $J$ 进行微分，然后将源设置为零，我们观察到

$$
\begin{aligned}
I_{K, m}=\int_{-\infty}^{\infty} d z e^{-\frac{z^{2}}{2 K}} z^{2 m}=\left.\left[\left(\frac{d}{d J}\right)^{2 m} \int_{-\infty}^{\infty} d z e^{-\frac{z^{2}}{2 K}+J z}\right]\right|_{J=0}=\left.\left[\left(\frac{d}{d J}\right)^{2 m} Z_{K, J}\right]\right|_{J=0}
\end{aligned}
\tag{1.20}
$$

换句话说，积分 $I_{K,m}$ 仅与 $J＝0$ 附近的配分函数$Z_{K,J}$ 的偶泰勒系数有关。例如，当 $2m=2$ 时，有

$$
\begin{aligned}
\mathbb{E}\left[z^{2}\right]=\frac{I_{K, 1}}{\sqrt{2 \pi K}}=\left.\left[\left(\frac{d}{d J}\right)^{2} e^{\frac{K J^{2}}{2}}\right]\right|_{J=0}=\left.\left[e^{\frac{K J^{2}}{2}}\left(K+K^{2} J^{2}\right)\right]\right|_{J=0}=K,    
\end{aligned}
\tag{1.21}
$$

对于 $2m=4$ 则有

$$
\begin{aligned}
 \mathbb{E}\left[z^{4}\right]=\frac{I_{K, 2}}{\sqrt{2 \pi K}}=\left.\left[\left(\frac{d}{d J}\right)^{4} e^{\frac{K J^{2}}{2}}\right]\right|_{J=0}=\left.\left[e^{\frac{K J^{2}}{2}}\left(3 K^{2}+6 K^{3} J^{2}+K^{4} J^{4}\right)\right]\right|_{J=0}=3 K^{2} .   
\end{aligned}
\tag{1.22}
$$

注意，在设置 $J＝0$ 时，任何具有悬空源 $J$ 的项都会消失。这个观察提供了一种简单的方法来评估一般 $m$ 的相关项：泰勒展开指数 $Z_{K,J}/I_K＝\exp（\frac{KJ^2}{2}）$，并保持该项具有正确数量的源，以使表达式不会消失。正是这样，我们得到

$$
\begin{aligned}
\mathbb{E}\left[z^{2 m}\right] & =\frac{I_{K, m}}{\sqrt{2 \pi K}}=\left.\left[\left(\frac{d}{d J}\right)^{2 m} e^{\frac{K J^{2}}{2}}\right]\right|_{J=0}=\left.\left\{\left(\frac{d}{d J}\right)^{2 m}\left[\sum_{k=0}^{\infty} \frac{1}{k !}\left(\frac{K}{2}\right)^{k} J^{2 k}\right]\right\}\right|_{J=0} \\
& =\left(\frac{d}{d J}\right)^{2 m}\left[\frac{1}{m !}\left(\frac{K}{2}\right)^{m} J^{2 m}\right]=K^{m} \frac{(2 m) !}{2^{m} m !}=K^{m}(2 m-1) ! !,   
\end{aligned}
\tag{1.23}
$$

这完成了我们对单变量高斯分布 Wick 定理（1.15）的第二次推导。这个推导比第一个简单的推导要长得多，但可以很自然地扩展到多变量高斯分布，我们接下来将讨论这个问题

### 多变量高斯积分
加快速度，我们现在可以处理 $N$ 维变量 $z_μ$ 的多变量高斯积分，$μ=1,...,N$。多变量高斯函数定义为

$$
\begin{aligned}
\exp \left[-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu}\left(K^{-1}\right)_{\mu \nu} z_{\nu}\right]
\end{aligned}
\tag{1.24}
$$

其中方差或`协方差矩阵` $K_{μν}$ 是 N 乘 N 对称正定矩阵，其逆矩阵 ${(K^{−1})}_{\mu v}$ 的定义使得它们的矩阵乘积给出 N 乘 N 的单位矩阵

$$
\begin{aligned}
 \sum_{\rho=1}^{N}\left(K^{-1}\right)_{\mu \rho} K_{\rho \nu}=\delta_{\mu \nu} .   
\end{aligned}
\tag{1.25}
$$

这里我们还引入了 Kronecker 德尔塔 $\delta_{μν}$，它满足

$$
\begin{aligned}
 \delta_{\mu \nu} \equiv \begin{cases}1, & \mu=\nu, \\ 0, & \mu \neq \nu .\end{cases}   
\end{aligned}
\tag{1.26}
$$

Kronecker 德尔塔只是单位矩阵的一种方便表示

现在，为了从高斯函数（1.24）构造概率分布，我们再次需要评估归一化因子

$$
\begin{aligned}
I_{K} & \equiv \int d^{N} z \exp \left[-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu}\left(K^{-1}\right)_{\mu \nu} z_{\nu}\right] \\
& =\int_{-\infty}^{\infty} d z_{1} \int_{-\infty}^{\infty} d z_{2} \cdots \int_{-\infty}^{\infty} d z_{N} \exp \left[-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu}\left(K^{-1}\right)_{\mu \nu} z_{\nu}\right] .    
\end{aligned}
\tag{1.27}
$$

为了计算这个积分，首先从线性代数中回忆，给定一个 N 乘 N 的对称矩阵 $K_{μν}$，总是有一个正交矩阵 $O_{μν}$ 将 $K_{μν}$ 对角化为（OKOT）μν=λμδμν和特征值λμ=1，…，N，并将其逆对角化为−1OT）μν=（1/λμ）δμν。考虑到这一点，在两次插入单位矩阵为δμν=（OT O）μν之后，积分指数的和可以用特征值表示为

$$
\begin{aligned}
\sum_{\mu, \nu=1}^{N} z_{\mu}\left(K^{-1}\right)_{\mu \nu} z_{\nu} & =\sum_{\mu, \rho, \sigma, \nu=1}^{N} z_{\mu}\left(O^{T} O\right)_{\mu \rho}\left(K^{-1}\right)_{\rho \sigma}\left(O^{T} O\right)_{\sigma \nu} z_{\nu} \\& =\sum_{\mu, \nu=1}^{N}(O z)_{\mu}\left(O K^{-1} O^{T}\right)_{\mu \nu}(O z)_{\nu} \\& =\sum_{\mu=1}^{N} \frac{1}{\lambda_{\mu}}(O z)_{\mu}^{2}
\end{aligned}
\tag{1.28}
$$

为了到达最后一行，我们使用了逆协方差矩阵的对角化特性。记住，对于正定矩阵Kμν，本征值都是正的λμ>0，我们看到λμ设置了高斯函数在每个本征方向上衰减的尺度。接下来，从多变量微积分中回顾变量uμ≡ （Oz）μ与正交矩阵O保持积分度量不变，即dNz=dNu。总之，这使得我们可以将多变量高斯积分（1.27）分解为单变量高斯积分的乘积（1.7）

$$
\begin{aligned}
I_{K} & =\int_{-\infty}^{\infty} d u_{1} \int_{-\infty}^{\infty} d u_{2} \cdots \int_{-\infty}^{\infty} d u_{N} \exp \left(-\frac{u_{1}^{2}}{2 \lambda_{1}}-\frac{u_{2}^{2}}{2 \lambda_{2}}-\ldots-\frac{u_{N}^{2}}{2 \lambda_{N}}\right) \\
& =\prod_{\mu=1}^{N}\left[\int_{-\infty}^{\infty} d u_{\mu} \exp \left(-\frac{u_{\mu}^{2}}{2 \lambda_{\mu}}\right)\right]=\prod_{\mu=1}^{N} \sqrt{2 \pi \lambda_{\mu}}=\sqrt{\prod_{\mu=1}^{N}\left(2 \pi \lambda_{\mu}\right)} .    
\end{aligned}
\tag{1.29}
$$

$$
\begin{aligned}
I_{K}=\int d^{N} z \exp \left[-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu}\left(K^{-1}\right)_{\mu \nu} z_{\nu}\right]=\sqrt{|2 \pi K|},    
\end{aligned}
\tag{1.30}
$$

$$
\begin{aligned}
p(z)=\frac{1}{\sqrt{|2 \pi K|}} \exp \left[-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu}\left(K^{-1}\right)_{\mu \nu} z_{\nu}\right] .    
\end{aligned}
\tag{1.31}
$$

$$
\begin{aligned}
 K^{\mu \nu} \equiv\left(K^{-1}\right)_{\mu \nu} .   
\end{aligned}
\tag{1.32}
$$

$$
\begin{aligned}
\sum_{\rho=1}^{N} K^{\mu \rho} K_{\rho \nu}=\delta^{\mu}{ }_{\nu},    
\end{aligned}
\tag{1.33}
$$

$$
\begin{aligned}
p(z)=\frac{1}{\sqrt{|2 \pi K|}} \exp \left(-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu} K^{\mu \nu} z_{\nu}\right) \text {. }    
\end{aligned}
\tag{1.34}
$$

$$
\begin{aligned}
p(z)=\frac{1}{\sqrt{|2 \pi K|}} \exp \left[-\frac{1}{2} \sum_{\mu, \nu=1}^{N}(z-s)_{\mu} K^{\mu \nu}(z-s)_{\nu}\right]   
\end{aligned}
\tag{1.35}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} \cdots z_{\mu_{M}}\right] & \equiv \int d^{N} z p(z) z_{\mu_{1}} \cdots z_{\mu_{M}} \\
& =\frac{1}{\sqrt{|2 \pi K|}} \int d^{N} z \exp \left(-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu} K^{\mu \nu} z_{\nu}\right) z_{\mu_{1}} \cdots z_{\mu_{M}}=\frac{I_{K,\left(\mu_{1}, \ldots, \mu_{M}\right)}}{I_{K}}    
\end{aligned}
\tag{1.36}
$$

$$
\begin{aligned}
I_{K,\left(\mu_{1}, \ldots, \mu_{M}\right)} \equiv \int d^{N} z \exp \left(-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu} K^{\mu \nu} z_{\nu}\right) z_{\mu_{1}} \cdots z_{\mu_{M}}    
\end{aligned}
\tag{1.37}
$$

$$
\begin{aligned}
Z_{K, J} \equiv \int d^{N} z \exp \left(-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu} K^{\mu \nu} z_{\nu}+\sum_{\mu=1}^{N} J^{\mu} z_{\mu}\right)    
\end{aligned}
\tag{1.38}
$$

$$
\begin{aligned}
 & {\left.\left[\frac{d}{d J^{\mu_{1}}} \frac{d}{d J^{\mu_{2}}} \cdots \frac{d}{d J^{\mu_{M}}} Z_{K, J}\right]\right|_{J=0} } \\
= & \int d^{N} z \exp \left(-\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu} K^{\mu \nu} z_{\nu}\right) z_{\mu_{1}} \cdots z_{\mu_{M}}=I_{K,\left(\mu_{1}, \ldots, \mu_{M}\right)} .   
\end{aligned}
\tag{1.39}
$$

$$
\begin{aligned}
& -\frac{1}{2} \sum_{\mu, \nu=1}^{N} z_{\mu} K^{\mu \nu} z_{\nu}+\sum_{\mu=1}^{N} J^{\mu} z_{\mu} \\
= & -\frac{1}{2} \sum_{\mu, \nu=1}^{N}\left(z_{\mu}-\sum_{\rho=1}^{N} K_{\mu \rho} J^{\rho}\right) K^{\mu \nu}\left(z_{\nu}-\sum_{\lambda=1}^{N} K_{\nu \lambda} J^{\lambda}\right)+\frac{1}{2} \sum_{\mu, \nu=1}^{N} J^{\mu} K_{\mu \nu} J^{\nu} \\
= & -\frac{1}{2} \sum_{\mu, \nu=1}^{N} w_{\mu} K^{\mu \nu} w_{\nu}+\frac{1}{2} \sum_{\mu, \nu=1}^{N} J^{\mu} K_{\mu \nu} J^{\nu}    
\end{aligned}
\tag{1.40}
$$

$$
\begin{aligned}
 Z_{K, J} & =\exp \left(\frac{1}{2} \sum_{\mu, \nu=1}^{N} J^{\mu} K_{\mu \nu} J^{\nu}\right) \int d^{N} w \exp \left[-\frac{1}{2} \sum_{\mu, \nu=1}^{N} w_{\mu} K^{\mu \nu} w_{\nu}\right] \\
& =\sqrt{|2 \pi K|} \exp \left(\frac{1}{2} \sum_{\mu, \nu=1}^{N} J^{\mu} K_{\mu \nu} J^{\nu}\right),   
\end{aligned}
\tag{1.41}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} \cdots z_{\mu_{2 m}}\right] & =\frac{I_{K,\left(\mu_{1}, \ldots, \mu_{2 m}\right)}}{I_{K}}=\left.\frac{1}{I_{K}}\left[\frac{d}{d J^{\mu_{1}}} \cdots \frac{d}{d J^{\mu_{2 m}}} Z_{K, J}\right]\right|_{J=0} \\
& =\frac{1}{2^{m} m !} \frac{d}{d J^{\mu_{1}}} \frac{d}{d J^{\mu_{2}}} \cdots \frac{d}{d J^{\mu_{2 m}}}\left(\sum_{\mu, \nu=1}^{N} J^{\mu} K_{\mu \nu} J^{\nu}\right)^{m} .    
\end{aligned}
\tag{1.42}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right]=\frac{1}{2} \frac{d}{d J^{\mu_{1}}} \frac{d}{d J^{\mu_{2}}}\left(\sum_{\mu, \nu=1}^{N} J^{\mu} K_{\mu \nu} J^{\nu}\right)=K_{\mu_{1} \mu_{2}} .    
\end{aligned}
\tag{1.43}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right] & =\frac{1}{2^{2} 2 !} \frac{d}{d J^{\mu_{1}}} \frac{d}{d J^{\mu_{2}}} \frac{d}{d J^{\mu_{3}}} \frac{d}{d J^{\mu_{4}}}\left(\sum_{\mu, \nu=1}^{N} J^{\mu} K_{\mu \nu} J^{\nu}\right)\left(\sum_{\rho, \lambda=1}^{N} J^{\rho} K_{\rho \lambda} J^{\lambda}\right) \\
& =K_{\mu_{1} \mu_{2}} K_{\mu_{3} \mu_{4}}+K_{\mu_{1} \mu_{3}} K_{\mu_{2} \mu_{4}}+K_{\mu_{1} \mu_{4}} K_{\mu_{2} \mu_{3}} .    
\end{aligned}
\tag{1.44}
$$

$$
\begin{aligned}
 \mathbb{E}\left[z_{\mu_{1}} \cdots z_{\mu_{2 m}}\right]=\sum_{\text {all pairing }} K_{\mu_{k_{1}} \mu_{k_{2}}} \cdots K_{\mu_{k_{2 m-1}} \mu_{k_{2 m}}},   
\end{aligned}
\tag{1.45}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}} z_{\mu_{5}} z_{\mu_{6}}\right] & =K_{\mu_{1} \mu_{2}} K_{\mu_{3} \mu_{4}} K_{\mu_{5} \mu_{6}}+K_{\mu_{1} \mu_{3}} K_{\mu_{2} \mu_{4}} K_{\mu_{5} \mu_{6}}+K_{\mu_{1} \mu_{4}} K_{\mu_{2} \mu_{3}} K_{\mu_{5} \mu_{6}} \\
& +K_{\mu_{1} \mu_{2}} K_{\mu_{3} \mu_{5}} K_{\mu_{4} \mu_{6}}+K_{\mu_{1} \mu_{3}} K_{\mu_{2} \mu_{5}} K_{\mu_{4} \mu_{6}}+K_{\mu_{1} \mu_{5}} K_{\mu_{2} \mu_{3}} K_{\mu_{4} \mu_{6}} \\
& +K_{\mu_{1} \mu_{2}} K_{\mu_{5} \mu_{4}} K_{\mu_{3} \mu_{6}}+K_{\mu_{1} \mu_{5}} K_{\mu_{2} \mu_{4}} K_{\mu_{3} \mu_{6}}+K_{\mu_{1} \mu_{4}} K_{\mu_{2} \mu_{5}} K_{\mu_{3} \mu_{6}} \\
& +K_{\mu_{1} \mu_{5}} K_{\mu_{3} \mu_{4}} K_{\mu_{2} \mu_{6}}+K_{\mu_{1} \mu_{3}} K_{\mu_{5} \mu_{4}} K_{\mu_{2} \mu_{6}}+K_{\mu_{1} \mu_{4}} K_{\mu_{5} \mu_{3}} K_{\mu_{2} \mu_{6}} \\
& +K_{\mu_{5} \mu_{2}} K_{\mu_{3} \mu_{4}} K_{\mu_{1} \mu_{6}}+K_{\mu_{5} \mu_{3}} K_{\mu_{2} \mu_{4}} K_{\mu_{1} \mu_{6}}+K_{\mu_{5} \mu_{4}} K_{\mu_{2} \mu_{3}} K_{\mu_{1} \mu_{6}} .
\end{aligned}
$$

公式（1.45）是 Wick 定理。在它周围放一个框。花点时间反思一下。
$$
\begin{aligned}
   ... \\
   ... \\
   ... \\
\end{aligned}

$$

好了，你现在是一个高斯老师了。呼气，然后像 Neo 所说的那样说：“我知道高斯积分。”

现在这些时刻已经过去了，现在是过渡到下一节的适当时机，在那里您将了解更多的一般概率分布。