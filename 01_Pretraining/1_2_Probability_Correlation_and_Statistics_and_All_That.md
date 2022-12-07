# 1.2 概率、相关性和统计等

在上一节中介绍高斯分布时，我们简要介绍了期望和矩的概念。这些都是为非高斯概率分布定义的，所以现在让我们重新引入这些概念并扩展其定义，着眼于理解描述广泛神经网络的近似高斯分布。

给定 $N$ 维随机变量 $z_{\mu}$ 的`概率分布` $p(z)$，我们可以通过测量 $z_{\mu}$ 的函数来了解其统计信息。我们将在一般意义上将此类可测量函数称为可观测函数，并将其表示为 $\mathcal{O}(z)$。可观察值的`期望值`

$$
\begin{aligned}
\mathbb{E}[\mathcal{O}(z)] \equiv \int d^{N} z p(z) \mathcal{O}(z) 
\end{aligned}
\tag{1.46}
$$

表示随机函数 $\mathcal{O}(z)$ 的平均值。请注意，可观测的 $\mathcal{O}(z)$ 不需要是标量值函数，例如，分布的第二个矩是由 $\mathcal{O}(z)=z_{\mu} z_{\nu}$ 给出的矩阵值可观测值。

在操作上，可观察量是我们通过进行实验来测量的一个量，以便与描述 $z_{\mu}$ 的基本概率分布的理论模型相联系。特别是，我们反复测量我们作为实验者自然可以接触到的可观测值，收集它们的统计数据，然后将它们与根据 $p(z)$ 的某些理论模型计算的那些可观测值的期望值的预测进行比较。

考虑到这一点，我们很自然地会问：通过测量一个可观测的 $\mathcal{O}(z)$，我们可以了解到什么样的关于基础分布 $p(z)$ 的信息？对于先验未知分布，是否有一组可观测值可以作为 $p(z)$ 的充分探测，从而我们可以使用该信息来预测所有涉及 $z_{\mu}$ 的未来实验的结果？

考虑我们已经遇到的一类可观测值，即 $z_{\mu}$ 的`矩`或 $M$ 点`相关函数`，由期望值给出 ${ }^{5}$

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{M}}\right]=\int d^{N} z p(z) z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{M}} .    
\end{aligned}
\tag{1.47}
$$

原则上，知道一个分布的 $M$ 点相关函数可以让我们通过泰勒展开来计算任何分析可观测 $\mathcal{O}(z)$ 的期望值

$$
\begin{aligned}
\mathbb{E}[\mathcal{O}(z)] & =\mathbb{E}\left[\left.\sum_{M=0}^{\infty} \frac{1}{M !} \sum_{\mu_{1}, \ldots, \mu_{M}=1}^{N} \frac{\partial^{M} \mathcal{O}}{\partial z_{\mu_{1}} \cdots \partial z_{\mu_{M}}}\right|_{z=0} z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{M}}\right] \\
& =\left.\sum_{M=0}^{\infty} \frac{1}{M !} \sum_{\mu_{1}, \ldots, \mu_{M}=1}^{N} \frac{\partial^{M} \mathcal{O}}{\partial z_{\mu_{1}} \cdots \partial z_{\mu_{M}}}\right|_{z=0} \mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{M}}\right],    
\end{aligned}
\tag{1.48}
$$

其中在最后一行，我们通过使用期望的线性特性(继承自(1.46)中积分的线性特性)，将泰勒系数从期望中取出。因此，很明显，所有 $M$ 点相关函数的集合完全表征了所有意图和目的的概率分布 ${ }^{6}$

然而，关于所有相关函数的这种描述有些麻烦，并且在操作上不可行。为了获得 $M$ 点相关函数的可靠估计，我们必须同时测量每个绘制的随机变量的 $M$ 分量，并重复多次这样的测量。随着 $M$ 的增长，这项任务很快变得不切实际。事实上，如果我们可以轻松地对所有$M$进行这样的测量，那么我们的 $p(z)$ 理论模型将不再是有用的抽象；从(1.48)我们已经知道了我们可以进行的所有可能实验的结果，没有什么可供我们预测的。

在这一点上，基本上所有有用的分布都可以有效地用有限数量的量来描述，给它们一个简约的表示。例如，考虑具有方差 $K_{\mu \nu}$ 的零均值 $n$ 维高斯分布。Wick定理 $1.45$ 给出了非零 $20m$ 点相关函数

在本书的其余部分中，我们将经常使用物理术语$M$点相关函数，而不是统计术语矩，尽管它们的含义相同，可以互换使用。

事实上，矩通过拉普拉斯变换或傅里叶变换提供了概率分布的双重描述。例如，概率分布 $p(z)$ 的拉普拉斯变换由下式给出：

$$
\begin{aligned}
Z_{J} \equiv \mathbb{E}\left[\exp \left(\sum_{\mu} J^{\mu} z_{\mu}\right)\right]=\int\left[\prod_{\mu} d z_{\mu}\right] p(z) \exp \left(\sum_{\mu} J^{\mu} z_{\mu}\right) .    
\end{aligned}
\tag{1.49}
$$

与高斯情况一样，该积分为 $p(z)$ 的 $M$ 点相关函数提供了一个生成函数，这意味着 $Z_{J}$ 可以从这些相关函数重构。然后可以通过逆拉普拉斯变换获得概率分布。

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{2 m}}\right]=\sum_{\text {all pairing }} K_{\mu_{k_{1}} \mu_{k_{2}}} \cdots K_{\mu_{k_{2 m-1}} \mu_{k_{2 m}}},    
\end{aligned}
\tag{1.50}
$$

并且完全由方差 $K_{\mu \nu}$ 的独立变量参数 $N(N+1) / 2$ 决定。方差本身可以通过测量两点相关函数来估计

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu} z_{\nu}\right]=K_{\mu \nu} .    
\end{aligned}
\tag{1.51}
$$

这与我们将分布本身描述为“零均值 $N$ 维高斯分布，方差 $K_{\mu \nu}$。对于零均值高斯分布，没有理由测量或跟踪任何较高点相关函数，因为它们完全受(1.50)方差的约束。

更一般地说，如果有一种系统的方法来学习非高斯概率分布，而不需要进行无限数量的实验，那将是很好的。对于近似高斯分布，统计学家称之为`累积量`，物理学家称之为`连通相关函数`，这是一组有用的可观测值 ${ }^{7}$ 由于这些量的正式定义有些繁琐和不直观，让我们从几个简单的例子开始。

第一累积量或连接的单点相关函数与完整的单点相关函数相同

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu}\right]\right|_{\text {connected }} \equiv \mathbb{E}\left[z_{\mu}\right] \text {. }    
\end{aligned}
\tag{1.52}
$$

这只是分布的平均值。第二累积量或连接的两点相关函数由下式给出：

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu} z_{\nu}\right]\right|_{\text {connected }} & \equiv \mathbb{E}\left[z_{\mu} z_{\nu}\right]-\mathbb{E}\left[z_{\mu}\right] \mathbb{E}\left[z_{\nu}\right] \\
& =\mathbb{E}\left[\left(z_{\mu}-\mathbb{E}\left[z_{\mu}\right]\right)\left(z_{\nu}-\mathbb{E}\left[z_{\nu}\right]\right)\right] \equiv \operatorname{Cov}\left[z_{\mu}, z_{\nu}\right],    
\end{aligned}
\tag{1.53}
$$

这也称为分布的协方差。请注意，在获取连接版本中的平方之前，如何从随机变量 $z_{\mu}$ 中减去平均值。数量 $\widehat{\Delta z}_{\mu} \equiv z_{\mu}-\mathbb{E}\left[z_{\mu}\right]$ 表示随机变量围绕其平均值的波动。直观地说，这种波动既有可能产生积极影响，也有可能产生消极影响， $\mathbb{E}\left[\widehat{\Delta z}_{\mu}\right]=\mathbb{E}\left[z_{\mu}\right]-\mathbb{E}\left[z_{\mu}\right]=0$ ，因此有必要对平方进行计算，以估计这种波动的幅度。

在这一点上，让我们将注意力局限于在符号翻转对称 $z_{\mu} \rightarrow-z_{\mu}$ 下不变的分布，这适用于零均值高斯分布(1.34)。重要的是，这种奇偶性对称性也适用于我们将研究的近高斯分布，以便描述神经网络。对于具有这种对称性的所有这种偶分布，所有奇矩和所有奇点连接的相关函数都消失。

${ }^{7}$ 在本章之外，正如我们将经常使用术语 $M$ 点相关函数而不是术语矩一样，我们将使用术语$M点连接相关函数而非术语累积量。当我们想引用矩而不是累积量时，我们有时可能会使用全相关函数来与连接相关函数进行对比。

在这种限制下，下一个最简单的可观测值是第四累积量或连接的四点相关函数，由以下公式给出

$$
\begin{aligned}
& \left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }} \\
= & \mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right] \\
& -\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right] \mathbb{E}\left[z_{\mu_{3}} z_{\mu_{4}}\right]-\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{3}}\right] \mathbb{E}\left[z_{\mu_{2}} z_{\mu_{4}}\right]-\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{4}}\right] \mathbb{E}\left[z_{\mu_{2}} z_{\mu_{3}}\right] .    
\end{aligned}
\tag{1.54}
$$

对于高斯分布，回想Wick定理$1.50$，最后三个项精确地减去用于计算第一个项的三对Wick收缩，这意味着

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }}=0 .    
\end{aligned}
\tag{1.55}
$$

本质上，通过设计，对于高斯分布，连接的四点相关函数消失，非零值表示偏离高斯统计$事实上，连接的四点相关函数可能是非高斯性的最简单度量。

现在我们有了一点直觉，我们已经准备好讨论第$M$累积量或$M$点连接相关函数的定义。为了完整起见，我们将给出一般定义，然后再次限制在奇偶校验 $z_{\mu} \rightarrow-z_{\mu}$ 下对称的分布。该定义是归纳的，有点违反直觉，用从1到$M$的关联相关函数表示$M$时刻：

$$
\begin{aligned}
& \mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{M}}\right] \\
\equiv & \left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{M}}\right]\right|_{\text {connected }} \\
& +\left.\left.\sum_{\text {all subdivisions }} \mathbb{E}\left[z_{\mu_{k_{1}^{[1]}}} \cdots z_{\mu_{k_{\nu 1}[1]}}\right]\right|_{\text {connected }} \cdots \mathbb{E}\left[z_{\mu_{k_{1}^{[s]}}} \cdots z_{\mu_{k_{\nu s}[s]}}\right]\right|_{\text {connected }},    
\end{aligned}
\tag{1.56}
$$

其中，总和是 $M$ 变量的所有可能细分为大小为 $\left(\nu_{1}, \ldots, \nu_{s}\right)$ as $\left(k_{1}^{[1]}, \ldots, k_{\nu_{1}}^{[1]}\right), \ldots,\left(k_{1}^{[s]}, \ldots, k_{\nu_{s}}^{[s]}\right)$。通过将第 $M$ 时刻分解为 $M$ 和更低阶的连接相关函数的乘积之和，我们可以看到，连接的 $M$ 点相关函数对应于一种新的相关类型，该类型不能由更低阶的关联相关函数表示。我们在讨论连接的四点相关函数作为非高斯性的简单度量时看到了上面的一个例子。

为了了解这个抽象定义是如何实际工作的，让我们重新查看这些示例。首先，我们简单地恢复均值和单点连接相关函数之间的关系，因为$M=1$变量没有细分为任何更小的部分。对于$M=2$，定义$1.56$给出


$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu}\right]\right|_{\text {connected }}=\mathbb{E}\left[z_{\mu}\right],    
\end{aligned}
\tag{1.57}
$$


${}^{8}$在统计学中，当用方差的平方归一化时，单个随机变量$z$的连接四点相关函数被称为过量峰度。与高斯分布相比，它是分布尾部的自然度量，也是异常值可能性的度量。特别是，正值表示尾巴更粗，而负值表示尾巴更细。

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right] & =\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right]\right|_{\text {connected }}+\left.\left.\mathbb{E}\left[z_{\mu_{1}}\right]\right|_{\text {connected }} \mathbb{E}\left[z_{\mu_{2}}\right]\right|_{\text {connected }} \\
& =\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right]\right|_{\text {connected }}+\mathbb{E}\left[z_{\mu_{1}}\right] \mathbb{E}\left[z_{\mu_{2}}\right] .    
\end{aligned}
\tag{1.58}
$$

重新排列以根据矩来求解连接的两点函数，我们看到这与我们先前的协方差定义(1.53)等效。

此时，让我们再次限制在 $z_{\mu} \rightarrow-z_{\mu}$ 下不变的奇偶对称分布，记住这意味着所有奇数点连接的相关函数都将消失。对于这样的分布，评估$M=4$的定义$1.56$给出

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]= & \left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }} \\
& +\left.\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right]\right|_{\text {connected }} \mathbb{E}\left[z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }} \\
& +\left.\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{3}}\right]\right|_{\text {connected }} \mathbb{E}\left[z_{\mu_{2}} z_{\mu_{4}}\right]\right|_{\text {connected }} \\
& +\left.\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{4}}\right]\right|_{\text {connected }} \mathbb{E}\left[z_{\mu_{2}} z_{\mu_{3}}\right]\right|_{\text {connected }} .   
\end{aligned}
\tag{1.59}
$$

由于 $\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right]=\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right]\right|_{\text {connected }}$ 当平均值消失时，这也只是我们之前的表达式(1.54)的重新排列，用于此类零平均值分布的连通四点相关函数。

为了看到新的东西，让我们继续 $M=6$：

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}} z_{\mu_{5}} z_{\mu_{6}}\right]= & \left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}} z_{\mu_{5}} z_{\mu_{6}}\right]\right|_{\text {connected }} \\
& +\left.\left.\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right]\right|_{\text {connected }} \mathbb{E}\left[z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }} \mathbb{E}\left[z_{\mu_{5}} z_{\mu_{6}}\right]\right|_{\text {connected }} \\
& +[14 \text { other }(2,2,2) \text { subdivisions }] \\
& +\left.\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }}\left[z_{\mu_{5}} z_{\mu_{6}}\right]\right|_{\text {connected }} \\
& +[14 \text { other }(4,2) \text { subdivisions }],    
\end{aligned}
\tag{1.60}
$$

其中，我们用连接的两点、四点和六点相关函数的乘积之和表示了完整的六点相关。重新排列上述表达式，并根据其定义1.53和1.54来表达两点和四点连接相关函数，我们获得了连接六点相关函数的表达式：

$$
\begin{aligned}
& \left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}} z_{\mu_{5}} z_{\mu_{6}}\right]\right|_{\text {connected }} \\
= & \mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}} z_{\mu_{5}} z_{\mu_{6}}\right] \\
& -\left\{\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right] \mathbb{E}\left[z_{\mu_{5}} z_{\mu_{6}}\right]+[14 \text { other }(4,2) \text { subdivisions }]\right\} \\
& +2\left\{\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right] \mathbb{E}\left[z_{\mu_{3}} z_{\mu_{4}}\right] \mathbb{E}\left[z_{\mu_{5}} z_{\mu_{6}}\right]+[14 \text { other }(2,2,2) \text { subdivisions }]\right\} .    
\end{aligned}
\tag{1.61}
$$

重新排列对于计算目的很有用，因为首先计算分布的矩，然后组织结果表达式以评估连接的相关函数很简单。回到(1.60)，很容易看到，对于高斯分布，连接的六点相关函数消失了。记住，对于高斯分布，连接的四点相关函数也消失了，我们看到，十五个 $(2,2,2)$  细分项正好等于由Wick收缩产生的十五个项，Wick收缩是由评估方程左侧的完整相关函数产生的。事实上，将连通相关函数(1.56)的一般定义应用于零均值高斯分布，我们可以归纳地看到，对于$M>2$，所有$M$点连通相关函数都将消失${}^{9}$因此，连接的相关函数是分布如何偏离高斯性的非常自然的度量。

考虑到这一点，我们最终可以将近似高斯分布定义为 $M>2$ 的所有相关函数都很小的分布$事实上，描述神经网络的非高斯分布通常具有这样的特性，即当网络变宽时，连接的四点相关函数变小，而较高点连接的相关函数变得更小。对于这些近似高斯分布，几个领先的相关函数给出了分布的简洁和准确描述，就像几个领先的泰勒系数可以给出扩展点附近函数的良好描述一样。