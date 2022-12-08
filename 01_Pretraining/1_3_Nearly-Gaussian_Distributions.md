# 近似高斯分布
既然我们已经根据与高斯统计的可测量偏差定义了近似高斯分布，即通过小但非零连接的相关器，那么很自然地要问我们如何将这些可观测值与分布的实际函数形式 $p(z)$ 联系起来。我们可以通过行动建立这种联系。

`作用` $S(z)$ 是通过关系定义概率分布 $p(z)$ 的函数

$$
\begin{aligned}
p(z) \propto e^{-S(z)} .
\end{aligned}
\tag{1.62}
$$

在统计学文献中，作用 $S(z)$ 有时被称为负对数概率，但我们将再次遵循物理学文献并将其称为作用。为了使（1.62）作为概率分布有意义， $p(z)$ 需要归一化，以便我们能够满足

$$
\begin{aligned}
\int d^{N} z p(z)=1 .
\end{aligned}
\tag{1.63}
$$

这就是归一化因子或配分函数

$$
\begin{aligned}
Z \equiv \int d^{N} z e^{-S(z)}
\end{aligned}
\tag{1.64}
$$

---

${ }^{9}$ 要看到这一点，请注意，如果所有较高点连接的相关器都消失，则定义为 $1.56$ 。等价于 Wick 定理 1.50，其中非零项为 $1.56$ -细分为大小为 $(2, \ldots, 2)$ 的簇-正好对应于 $1.50$ 中的不同配对。

${ }^{10}$ 正如我们在 $\$1.1$ 中所讨论的，方差设置了高斯分布的尺度。对于近似高斯分布，我们要求当与方差的适当幂（即 $\left.\left|\mathbb{E}\left[z_{\mu_{1}} \cdots z_{\mu_{2 m}}\right]\right|_{\text {connected }}|\ll| K_{\mu \nu}\right|^{m}$）相比时，所有 $2 m$ 点连接的相关器在参数上都很小。示意图。

---

进来。在计算分区函数之后，我们可以将特定动作 $S(z)$ 的概率分布定义为

$$
\begin{aligned}
p(z) \equiv \frac{e^{-S(z)}}{Z} .
\end{aligned}
\tag{1.65}
$$

相反，给定一个概率分布，我们可以将一个动作 $S(z)=-\log [p(z)]$ 与一个附加的模糊性相关联：模糊性的产生是因为动作中的恒定位移可以被分配函数中的乘法因子抵消${ }^{11}$
该操作是一种非常方便的方法来近似某些类型的统计过程，特别是那些接近高斯统计的过程。为了证明这一点，我们将首先从描述高斯分布的最简单的动作开始，然后我们将展示如何系统地扰动它，以包括各种非高斯性。

### 二次作用和高斯分布
由于我们已经知道高斯分布的函数形式，所以通过从（1.34）中的指数中读出来识别作用是很简单的

$$
\begin{aligned}
S(z)=\frac{1}{2} \sum_{\mu, \nu=1}^{N} K^{\mu \nu} z_{\mu} z_{\nu},
\end{aligned}
\tag{1.66}
$$

其中，作为提醒，矩阵 $K_{\mu \nu}$ 是方差矩阵 $K_{\mu\nu}$ 的倒数。分配函数由我们在 $1.1$ 中计算的归一化积分 $1.30$ 给出

$$
\begin{aligned}
Z=\int d^{N} z e^{-S(z)}=I_{K}=\sqrt{|2 \pi K|} .
\end{aligned}
\tag{1.67}
$$

此二次作用是最简单的可归一化作用，并作为定义其他分布的起点。

正如我们接下来将要展示的那样，高斯分布的积分是评估接近高斯分布的期望值的一个基元。因此，为了区分一般期望和高斯分布的积分，让我们引入一种特殊的braket或 $\langle\cdot\rangle$  符号来计算高斯期望值。对于可观测的 $\mathcal{O}(z)$ ，将高斯期望定义为

$$
\begin{aligned}
\langle\mathcal{O}(z)\rangle_{K} \equiv \frac{1}{\sqrt{|2 \pi K|}} \int\left[\prod_{\mu=1}^{N} d z_{\mu}\right] \exp \left(-\frac{1}{2} \sum_{\mu, \nu=1}^{N} K^{\mu \nu} z_{\mu} z_{\nu}\right) \mathcal{O}(z)
\end{aligned}
\tag{1.68}
$$

特别是，使用这种符号，我们可以将威克定理写成

$$
\begin{aligned}
\left\langle z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{2 m}}\right\rangle_{K}=\sum_{\text {all pairing }} K_{\mu_{k_{1}} \mu_{k_{2}}} \cdots K_{\mu_{k_{2 m-1}} \mu_{k_{2 m}}} .
\end{aligned}
\tag{1.69}
$$

如果我们讨论的是方差为 $K_{\mu \nu}$ 的高斯分布，那么我们可以互换地使用符号 $\mathbb{E}[\cdot]$ 和 $\langle\cdot\rangle_{K}$。相反，如果我们讨论的是近似高斯分布 $p(z)$，则$\mathbb{E}[\cdot]$ 表示相对于 $p(z)$ 的期望值，1.46。然而，在评估这种期望值时，我们经常会遇到高斯积分，为此我们将使用这个braket符号 $\langle\cdot\rangle_{K}$  来简化表达式。

---

${ }^{11}$ 一个约定是选择常量，以便在以其全局最小值求值时操作消失。

---

### 四次作用与微扰理论

现在，让我们找到一个表示近似高斯分布的动作，它有一个连接的四点相关器，它很小，但不会消失

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }}=O(\epsilon) .
\end{aligned}
\tag{1.70}
$$

在这里，我们引入了一个小参数 $\epsilon \ll 1$，并指出相关器的阶数应为 $\epsilon$。对于神经网络，我们稍后将发现，小参数 $\epsilon$ 的作用由1/width发挥。

我们应该能够通过在二次作用（1.66）上添加一个小的四次项来变形高斯分布，从而生成一个小连通的四点相关器，从而给出一个四次作用

$$
\begin{aligned}
S(z)=\frac{1}{2} \sum_{\mu, \nu=1}^{N} K^{\mu \nu} z_{\mu} z_{\nu}+\frac{\epsilon}{4 !} \sum_{\mu, \nu, \rho, \lambda=1}^{N} V^{\mu \nu \rho \lambda} z_{\mu} z_{\nu} z_{\rho} z_{\lambda},
\end{aligned}
\tag{1.71}
$$

其中四次耦合  $\epsilon V^{\mu \nu \rho \lambda}$ 是一个在其所有四个索引中完全对称的 $(N \times N \times N \times N)$ 维张量。系数为 $1/4!$ 以补偿由于索引的对称性而导致的总和的过度计数。虽然这不是连接的证明，但请注意，耦合 $\epsilon V^{\mu \nu \rho \lambda}$ 具有正确数量的分量，以忠实地再现四点连接相关器$1.70$，这也是一个 $(N \times N \times N \times N)$ 维对称张量。至少从这个角度来看，我们有了一个良好的开端。

现在让我们建立四次耦合和相连的四点相关器之间的对应关系。注意，一般情况下，不可能用非高斯函数计算任何封闭形式的期望值——这甚至包括配分函数。相反，为了计算连接的四点相关器，我们需要使用微扰理论将小参数 $\epsilon$ 中的每一项都扩展到一阶，然后可以以封闭形式计算每个项。因为这比所说的更容易，所以让我们开始计算。

首先，让我们评估分区函数：

$$
\begin{aligned}
Z & =\int\left[\prod_{\mu} d z_{\mu}\right] e^{-S(z)} \\
& =\int\left[\prod_{\mu} d z_{\mu}\right] \exp \left(-\frac{1}{2} \sum_{\mu, \nu} K^{\mu \nu} z_{\mu} z_{\nu}-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right) \\
& =\sqrt{|2 \pi K|}\left\langle\exp \left(-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right)\right\rangle_{K} .
\end{aligned}
\tag{1.72}
$$

在第二行中，我们插入了四次运算 1.71 的表达式，在最后一行中，对于方差为 $K_{\mu \nu}$。正如宣传的那样，最后一行中的高斯期望值不能以封闭形式计算。然而，由于我们的参数 $\epsilon$ 很小，我们可以泰勒展开指数，将分配函数表示为简单高斯期望值的和，可以使用 Wick 定理 1.69 计算：

$$
\begin{aligned}
Z & =\sqrt{|2 \pi K|}\left\langle 1-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}+O\left(\epsilon^{2}\right)\right\rangle_{K} \\
& =\sqrt{|2 \pi K|}\left[1-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}\left\langle z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right\rangle_{K}+O\left(\epsilon^{2}\right)\right] \\
& =\sqrt{|2 \pi K|}\left[1-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}\left(K_{\rho_{1} \rho_{2}} K_{\rho_{3} \rho_{4}}+K_{\rho_{1} \rho_{3}} K_{\rho_{2} \rho_{4}}+K_{\rho_{1} \rho_{4}} K_{\rho_{2} \rho_{3}}\right)+O\left(\epsilon^{2}\right)\right] \\
& =\sqrt{|2 \pi K|}\left[1-\frac{1}{8} \epsilon \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} K_{\rho_{1} \rho_{2}} K_{\rho_{3} \rho_{4}}+O\left(\epsilon^{2}\right)\right]
\end{aligned}
\tag{1.73}
$$

在最后一行中，我们能够通过使用四次耦合的完全对称性将三个 $K^{2}$ 项组合在一起，然后重新标记一些求和的伪索引。

同样，让我们评估两点相关器：

$$
\begin{aligned}
& \mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right]=\frac{1}{Z} \int\left[\prod_{\mu} d z_{\mu}\right] e^{-S(z)} z_{\mu_{1}} z_{\mu_{2}} \\
= & \frac{\sqrt{|2 \pi K|}}{Z}\left\langle z_{\mu_{1}} z_{\mu_{2}} \exp \left(-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right)\right\rangle_{K} \\
= & \frac{\sqrt{|2 \pi K|}}{Z}\left[\left\langle z_{\mu_{1}} z_{\mu_{2}}\right\rangle_{K}-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}\left\langle z_{\mu_{1}} z_{\mu_{2}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right\rangle_{K}+O\left(\epsilon^{2}\right)\right] \\
= & {\left[1+\frac{1}{8} \epsilon \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} K_{\rho_{1} \rho_{2}} K_{\rho_{3} \rho_{4}}\right] K_{\mu_{1} \mu_{2}} } \\
& -\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}\left(3 K_{\mu_{1} \mu_{2}} K_{\rho_{1} \rho_{2}} K_{\rho_{3} \rho_{4}}+12 K_{\mu_{1} \rho_{1}} K_{\mu_{2} \rho_{2}} K_{\rho_{3} \rho_{4}}\right)+O\left(\epsilon^{2}\right) \\
= & K_{\mu_{1} \mu_{2}}-\frac{\epsilon}{2} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} K_{\mu_{1} \rho_{1}} K_{\mu_{2} \rho_{2}} K_{\rho_{3} \rho_{4}}+O\left(\epsilon^{2}\right) .
\end{aligned}
\tag{1.74}
$$

在这里，为了从第一行到第二行，我们插入了四次作用（1.71）的表达式，并将积分改写为高斯期望。然后，在 $\epsilon$ 展开到一阶之后，在下一步中，我们用（1.73）代替分母中的配分函数 $Z$ ，并使用展开式 $1 /(1-x)=1+x+O\left(x^{2}\right)$ 将  $1 / Z$ 展开到 $\epsilon$ 的一阶。在同一步骤中，我们还注意到，在来自高斯期望值 $\left\langle z_{\mu_{1}} z_{\mu_{2}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right\rangle_{K}$ 的15个项中，有三种方法。给定完整的四点相关器 $1.75$ 和两点相关器 $1.74$，我们最终可以将连接的四点相关性 $1.54$ 评估为

$$
\begin{aligned}
& \mathbb{E}\left[z_{\mu_1} z_{\mu_2} z_{\mu_3} z_{\mu_4}\right]=\frac{1}{Z} \int\left[\prod_\mu d z_\mu\right] e^{-S(z)} z_{\mu_1} z_{\mu_2} z_{\mu_3} z_{\mu_4} \\
&=  \frac{\sqrt{|2 \pi K|}}{Z}\left[\left\langle z_{\mu_1} z_{\mu_2} z_{\mu_3} z_{\mu_4}\right\rangle_K-\frac{\epsilon}{24} \sum_{\rho_1, \ldots, \rho_4} V^{\rho_1 \rho_2 \rho_3 \rho_4}\left\langle z_{\mu_1} z_{\mu_2} z_{\mu_3} z_{\mu_4} z_{\rho_1} z_{\rho_2} z_{\rho_3} z_{\rho_4}\right\rangle_K+O\left(\epsilon^2\right)\right] \\

&=  \left.1+\frac{1}{8} \epsilon \sum_{\rho_1, \ldots, \rho_4} V^{\rho_1 \rho_2 \rho_3 \rho_4} K_{\rho_1 \rho_2} K_{\rho_3 \rho_4}\right]\left[K_{\mu_1 \mu_2} K_{\mu_3 \mu_4}+K_{\mu_1 \mu_3} K_{\mu_2 \mu_4}+K_{\mu_1 \mu_4} K_{\mu_2 \mu_3}\right] \\
& -\frac{\epsilon}{24} \sum_{\rho_1, \ldots, \rho_4} V^{\rho_1 \rho_2 \rho_3 \rho_4} \\
& \times\left(3 K_{\mu_1 \mu_2} K_{\mu_3 \mu_4} K_{\rho_1 \rho_2} K_{\rho_3 \rho_4}+12 K_{\mu_1 \rho_1} K_{\mu_2 \rho_2} K_{\mu_3 \mu_4} K_{\rho_3 \rho_4}+12 K_{\mu_3 \rho_1} K_{\mu_4 \rho_2} K_{\mu_1 \mu_2} K_{\rho_3 \rho_4}\right. \\
& +3 K_{\mu_1 \mu_3} K_{\mu_2 \mu_4} K_{\rho_1 \rho_2} K_{\rho_3 \rho_4}+12 K_{\mu_1 \rho_1} K_{\mu_3 \rho_2} K_{\mu_2 \mu_4} K_{\rho_3 \rho_4}+12 K_{\mu_2 \rho_1} K_{\mu_4 \rho_2} K_{\mu_1 \mu_3} K_{\rho_3 \rho_4} \\
& +3 K_{\mu_1 \mu_4} K_{\mu_2 \mu_3} K_{\rho_1 \rho_2} K_{\rho_3 \rho_4}+12 K_{\mu_1 \rho_1} K_{\mu_4 \rho_2} K_{\mu_2 \mu_3} K_{\rho_3 \rho_4}+12 K_{\mu_2 \rho_1} K_{\mu_3 \rho_2} K_{\mu_1 \mu_4} K_{\rho_3 \rho_4} \\
& \left.+24 K_{\mu_1 \rho_1} K_{\mu_2 \rho_2} K_{\mu_3 \rho_3} K_{\mu_4 \rho_4}\right)+O\left(\epsilon^2\right) .

\end{aligned}
\tag{1.75}
$$



为了从第一行到第二行，我们插入了四次运算的表达式（1.71），在中扩展到一阶，并重写了bra-ket符号（1.68）。在第三行，我们再次用表达式（1.73）替换配分函数Z，将1/Z扩展到中的一阶，然后使用威克定理（1.69）计算第四和第八高斯矩。（是的，我们知道对〈zμ1 zμ2 zμ3 zμ4 zρ1 zρ2 zρ3 zρ4〉K的评估并不有趣。术语的分解再次取决于μ型指数是否与ρ型指数收缩。）我们可以通过注意一些术语由于18而取消来简化这个表达式− 一旦我们通过两点相关器（1.74）的表达式注意到：

$$
\begin{aligned}
\begin{array}{l}K_{\mu_{1} \mu_{2}} K_{\mu_{3} \mu_{4}}-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}\left(12 K_{\mu_{1} \rho_{1}} K_{\mu_{2} \rho_{2}} K_{\mu_{3} \mu_{4}} K_{\rho_{3} \rho_{4}}+12 K_{\mu_{3} \rho_{1}} K_{\mu_{4} \rho_{2}} K_{\mu_{1} \mu_{2}} K_{\rho_{3} \rho_{4}}\right) \\=\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right] \mathbb{E}\left[z_{\mu_{3}} z_{\mu_{4}}\right]+O\left(\epsilon^{2}\right)\end{array}
\end{aligned}
\tag{1.76}
$$

最终得到

$$
\begin{aligned}
\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right] &= \mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}}\right] \mathbb{E}\left[z_{\mu_{3}} z_{\mu_{4}}\right] + \mathbb{E}\left[z_{\mu_{1}} z_{\mu_{3}}\right] \mathbb{E}\left[z_{\mu_{2}} z_{\mu_{4}}\right] + \mathbb{E}\left[z_{\mu_{1}} z_{\mu_{4}}\right] \mathbb{E}\left[z_{\mu_{2}} z_{\mu_{3}}\right] \\
 &-\epsilon \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} K_{\mu_{1} \rho_{1}} K_{\mu_{2} \rho_{2}} K_{\mu_{3} \rho_{3}} K_{\mu_{4} \rho_{4}}+O\left(\epsilon^{2}\right) \text {. }
\end{aligned}
\tag{1.77}
$$

给定完整的四点相关器（1.75）和两点相关器（1.74），我们最终可以将连接的四点相关性器（1.54）评估为

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }}=-\epsilon \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} K_{\mu_{1} \rho_{1}} K_{\mu_{2} \rho_{2}} K_{\mu_{3} \rho_{3}} K_{\mu_{4} \rho_{4}}+O\left(\epsilon^{2}\right) \text {. }
\end{aligned}
\tag{1.78}
$$

这使得连接的四点相关器和动作中的四次耦合之间的关系变得明确，当二者都很小时。我们看到，对于由四次作用（1.71）实现的近似高斯分布，该分布是-正如所承诺的近似高斯的：耦合的强度 $\epsilon V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}$ 直接控制分布与高斯统计的偏差，如通过连接的四点相关器测量的。这还表明，四个索引张量 $V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}$ 在分量 $z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}$ 之间创建了非平凡的相关性，否则这些相关性无法通过任何一对随机变量 $z_{\mu} z_{\nu}$ 中的相关性 $K_{\mu \nu}$ 。

最后，请注意，连接的两点相关器1.74（即，该近似高斯分布的协方差）也通过四次耦合 $\epsilon V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}$ 从其高斯值  $K_{\mu_{1} \mu_{2}}$ 。因此，近似高斯变形不仅创建了由连接的四点相关器（1.78）测量的四点相关性的复杂模式，还可以修改高斯两点相关性的细节。

现在我们看到了如何计算近似高斯分布的统计数据，让我们后退一步，思考是什么使这成为可能。我们可以在问题中存在无量纲参数  $\epsilon$ 的任何时候执行这些微扰计算，该参数是小的 $\epsilon \ll 1$，但非零的 $\epsilon>0$。这使得微扰理论成为一个非常强大的工具，可以在任何问题具有任何极端尺度（无论大小）时进行理论分析。

重要的是，这与理论上理解实践中的神经网络直接相关。正如我们将在以下章节中解释的那样，真实网络有一个参数 $n$ -一个层中神经元的数量-通常很大，但肯定不是无限的。这意味着我们可以将描述此类网络的分布扩展为 $\epsilon=1 / n$ 的大参数的倒数。事实上，当参数 $n$ 很大时（这在实践中是典型的），描述神经网络的分布几乎是高斯分布，因此理论上是可处理的。这种扩展被称为 $1 / n$ 扩展或大型-$n$ 扩展，将是我们学习深度学习理论原理的主要工具之一。

### 离题话：统计独立性和相互作用

四次作用（1.71）是相互作用理论中最简单的模型之一。我们通过将四次耦合连接到非消失连接四点相关器的非高斯统计，明确地证明了这一点。在这里，让我们尝试通过引用统计独立的概念来提供交互的直观含义。

回想一下概率论，如果两个随机变量$x$和$y$的联合分布因子为

$$
\begin{aligned}
\left|s^{\mu_{1} \cdots \mu_{2 m}}\right| \ll\left|K^{\mu \nu}\right|^{m},

p(x, y)=p(x) p(y) .
\end{aligned}
\tag{1.79}
$$

对于高斯分布，如果方差矩阵 $K_{\mu \nu}$ 是对角的，则 $z_{\mu}$ 的不同分量之间根本没有相关性；它们在统计上明显彼此独立。

即使 $K_{\mu \nu}$ 不是对角的，我们仍然可以通过旋转到右基来解除高斯分布的相关性。正如在$\$1.1$中所讨论的，始终存在一个正交矩阵$O$，它将协方差对角化为 $\left(O K O^{T}\right)_{\mu \nu}=\lambda_{\mu} \delta_{\mu \nu}$。根据变量 $u_{\mu} \equiv(O z)_{\mu}$，分布如下

$$
\begin{aligned}


p(z)=\frac{1}{\sqrt{|2 \pi K|}} \exp \left(-\sum_{\mu=1}^{N} \frac{u_{\mu}^{2}}{2 \lambda_{\mu}}\right)=\prod_{\mu=1}^{N}\left(\frac{e^{-\frac{u_{\mu}^{2}}{2 \lambda_{\mu}}}}{\sqrt{2 \pi \lambda_{\mu}}}\right)=p\left(u_{1}\right) \cdots p\left(u_{N}\right) .
\end{aligned}
\tag{1.80}
$$

因此，我们看到，在 $u$ 坐标基础上，原始的多变量高斯分布因子分解为统计独立的 $N$ 单变量高斯分布。

我们还看到，就行动而言，统计独立性的特点是行动在不同的条款上分解成一个总和。当存在非零非高斯耦合时，变量之间的相互作用一般不可能展开。例如，正交矩阵 $O_{\mu \nu}$ 的 $\sim N^{2}$ 分量要改变基，而四次耦合 $\epsilon V^{\mu \nu \rho \lambda}$ 有 $\sim N^{4}$ 成分关联随机变量，因此一般不可能将四次作用重新表示为 $N$ 不同变量的函数之和。由于该行动不能以超过 $N$ 的单独条款计算，因此联合分配不能进行因子分解，并且各组成部分将不会彼此独立。因此，不可能将近似高斯分布考虑到 $N$ 统计独立分布的乘积中。从这个意义上说，互动的含义是统计独立性的崩溃 ${ }^{12}$

### 近似高斯作用    

给出了一个具体的例子，其中我们说明了如何变形二次作用以实现最简单的近似高斯分布，现在我们给出了近似高斯分布的更一般的观点。在下文中，我们将继续要求我们的分布在取 $z_{\mu} \rightarrow-z_{\mu}$ 的奇偶对称下是不变的。在动作表示中，这对应于仅包含偶数度的项 ${ }^{13}$

---
${ }^{12}$ 一个精明的读者可能会想，当我们考虑一个$N＝1$的单变量分布时，是否存在任何交互，因为没有其他变量可以交互。对于近似高斯分布，即使 $N=1$，我们在 $1.74$ 中看到，分布的方差从其高斯值 $K$ 偏移，并且取决于四次耦合 $\epsilon V$。在物理学中，我们说这种变化是由于四次耦合引起的自相互作用，因为它修改了我们所比较的自由高斯理论的可观测值，尽管这里没有统计独立的概念。

换言之，即使作用只涉及一个项，这样的非高斯分布对其分配函数或相关器没有封闭形式的解； 例如，当 $S(z)=\frac{z^{2}}{2 K}+\frac{1}{4 !} \epsilon V z^{4}$ 时，没有技巧可以让我们精确计算形式为 $e^{-S(z)}$ 的积分。这意味着我们仍然需要利用微扰理论来分析这种分布中的自相互作用。

${ }^{13}$ 施加这样的奇偶对称性，从而在动作中缺少奇数阶项，意味着所有奇数矩以及所有奇数点连接的相关器都将消失。

---

考虑到这一点，尽管通常情况下，我们可以通过将高斯作用变形为


$$
\begin{aligned}
S(z)=\frac{1}{2} \sum_{\mu, \nu=1}^{N} K^{\mu \nu} z_{\mu} z_{\nu}+\sum_{m=2}^{k} \frac{1}{(2 m) !} \sum_{\mu_{1}, \ldots, \mu_{2 m}=1}^{N} s^{\mu_{1} \cdots \mu_{2 m}} z_{\mu_{1}} \cdots z_{\mu_{2 m}},
\end{aligned}
\tag{1.81}
$$

其中系数 $1 /(2 m)!$ 是常规的，以补偿由于系数 $\mu_{1}, \ldots, \mu_{2 m}$ 中的索引 $s^{\mu_{1} \cdots \mu_{2 m}}$ 的隐含对称性而导致的和中的过度计算，给定变量 $z_{\mu_{1}} \cdots z_{\mu_{2 m}}$ 的乘积的排列对称性。动作的非高斯部分中的项数由整数 $k$ 控制。如果 $k$ 是无界的，那么 $S(z)$ 将是任意偶函数，而 $p(z)$ 可以是任何奇偶对称分布。当扩展多项式$S(z)$ 被截断到相当小的程度 $k$ - 比如 $k=2$ 时，该作用是最有用的。

系数 $s^{\mu_{1} \cdots \mu_{2 m}}$ 通常被称为非高斯耦合，它们控制着 $z_{\mu} .{ }^{14}$ 的相互作用。特别是，在动作中一起出现的特定分量 $z_{\mu}$ 与这些变量之间存在关联相关性之间存在直接对应关系，其中（1.81）中的项的程度直接贡献于该程度的连接相关器。我们在（1.78）中看到了一个这样的例子，它将四次项连接到连接的四点相关器。通过这种方式，耦合提供了一种非常直接的方式来控制非高斯相关的程度和模式，并且作用的总体程度提供了一个系统地包括越来越复杂的这种相关模式的方式。

如果您回想一下 $\$ 1.2$，我们将近似高斯分布定义为所有这些相关器都很小的分布。等效地，从作用角度来看，近似高斯分布是一种非高斯分布，其作用形式为1.81），对于所有 $1 \leq m \leq k$ ，所有耦合 $s^{\mu_{1} \cdots \mu_{2 m}}$ 的参数都很小：

$$
\begin{aligned}
\left|s^{\mu_{1} \cdots \mu_{2 m}}\right| \ll\left|K^{\mu \nu}\right|^{m},
\end{aligned}
\tag{1.82}
$$

其中考虑到索引的失配，该方程有点示意性 ${ }^{15}$ 重要的是，比较是用逆方差或二次耦合的适当幂进行的，因为正如我们已经解释过的，方差设置了高斯分布的尺度，我们将这些近似高斯分布与之进行比较。

---

${ }^{14}$ 在类似的情况下，作用中的系数 $K^{\mu \nu}$ 有时被称为二次耦合，因为二次作用中的分量 $z_{\mu}$ 与分量 $z_{\nu}$ 的耦合导致了一个非平凡的相关性，即 $\operatorname{Cov}\left[z_{\mu}, z_{\nu}\right]=K_{\mu \nu}$ 。

然而，这个原理方程在尺寸上是一致的。为了支持这一观点，让我们简单介绍一下维度分析：让随机变量 $z_{\mu}$ 具有维度 $\zeta$，我们将其表示为 $\left[z_{\mu}\right]=\zeta^{1}$。通过维度，您应该记住类似于长度单位的内容，因此，例如，我们将表达式 $\left[z_{\mu}\right]=\zeta^{1}$ 读为“$z$的分量以 $\zeta$ 为单位测量”。特定的单位是任意的：例如，对于长度，我们可以在米、英寸或秒秒之间进行选择，只要我们使用长度单位，而不是米 ${ }^{2}$，而是面积单位。重要的是，我们不能将具有不同单位的量相加或相等：将长度加到面积上没有任何逻辑意义。这与计算机科学中的类型安全概念类似，例如，我们不应该将类型str变量添加到类型int变量中。

现在，由于动作 $S(z)$ 是指数 $p(z) \propto e^{-S(z)}$ 的自变量，所以它必须是无量纲的；否则，指数 $e^{-S}=1-S+\frac{S^{2}}{2}+\ldots$ 将违反我们刚刚描述的加法规则。根据该作用的无量纲要求，我们推测协方差矩阵的倒数

---

正如我们将在$\$ 4$ 中看到的，宽神经网络由近似高斯分布描述。特别地，我们将发现，这种网络由一种特殊类型的近似高斯分布描述，其中连接的相关器在层次上很小，缩放如下

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu_{1}} \cdots z_{\mu_{2 m}}\right]\right|_{\text {connected }}=O\left(\epsilon^{m-1}\right),
\end{aligned}
\tag{1.83}
$$

使用相同的参数 $\epsilon$ 控制每个$2百万点连接的相关器的不同标度。重要的是，随着 $\epsilon$ 变小，来自较高点连接相关器的非高斯性在参数上变得不那么重要。

这意味着，对于具有分级缩放（1.83）的近似高斯分布，我们可以通过以 $\epsilon$ 中的某个固定顺序截断动作来一致地近似该分布。具体地说，我们可以使用形式（1.81）的操作来忠实地表示直到 $O\left(\epsilon^{k-1}\right)$ 阶的所有相关性，忽略 $O\left(\epsilon^{k}\right)$ 阶和更高阶的关联相关性。只要 $\epsilon$ 足够小，$k$ 足够高， $O\left(\epsilon^{k}\right)$ 可以忽略不计，则生成的操作为感兴趣的统计过程提供了有用而有效的描述。

在实践中，截断为 $k=2$ 的四次作用（1.71）将使我们能够模拟现实的有限宽度神经网络。这种四次作用捕捉了近似高斯分布和高斯分布之间的重要质量差异，结合了随机变量不同分量之间的非平凡相互作用。此外，截断为 $O(\epsilon)$ 的近似高斯分布的统计数据（1.83）与截断为 $O\left(\epsilon^{2}\right)$ 的统计数据之间的差异主要是定量的：在这两种情况下，都存在非平凡的非高斯相关，但高阶相关的模式仅在一个小的方面有所不同，差异被抑制为 $O\left(\epsilon^{2}\right)$。以这种方式，四次作用所代表的分布足够复杂，足以捕捉神经网络中最显著的非高斯效应，同时仍然足够简单，可以分析处理。

具有维度 $\left[K^{\mu \nu}\right]=\zeta^{-2}$ ，并且协方差本身具有维度 $\left[K_{\mu \nu}\right]=\zeta^{2}$ 。类似地，1.81中的所有非高斯耦合都具有 $\left[s^{\mu_{1} \cdots \mu_{2 m}}\right]=\zeta^{-2 m}$ 的维度。因此，$1.82$的两侧具有相同的尺寸，使得该方程在尺寸上一致。

---

更具体地说，考虑四次作用1.71。如果我们让四次耦合的张量部分具有维度 $\left[V^{\mu \nu \rho \lambda}\right]=\zeta^{-4}$，那么参数 $\epsilon$ 是无量纲的，如所声称的。这意味着我们可以一致地将 $\epsilon$ 与单位进行比较，其参数小 $\epsilon \ll 1$ 意味着全四次耦合 $\epsilon V^{\mu \nu \rho \lambda}$ 远小于二次耦合的平方，并且连接的四点相关器$1.78$远小于连接的两点相关器$11.74$的平方。