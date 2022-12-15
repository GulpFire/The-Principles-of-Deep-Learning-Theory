# 2.3 整合
正如我们在$\$2.1$中所讨论的。神经网络是经过训练而不是编程的。实际上，为了开始训练函数逼近的神经网络，我们需要设置偏差$b_｛i｝^｛（\ell）｝$和权重$W_｛i j｝^｝（\el）｝的初始值。由于这些模型参数的学习值几乎总是从其初始值迭代建立的，因此初始化策略可能会对函数逼近的成功或失败产生重大影响。

也许最简单的策略是将所有偏差和权重设置为零，$b_｛i｝^｛（\ell）｝=W_｛i j｝^｝（\eell）｝=0$。然而，此初始化未能打破隐藏层$\ell$中$n_{\ell}$不同神经元之间的排列对称性。如果这种对称性没有被打破，那么我们就无法区分一层中的不同神经元，因为所有这些神经元都执行完全相同的计算。实际上，网络的行为就像在每个隐藏层中只有一个神经元$n_。因此，为了在更广泛的网络中利用偏差和权重的所有不同分量，我们需要以某种方式打破排列对称性。

也许打破这种排列对称性的最简单策略是独立于某些概率分布对每个偏差和权重进行采样。从理论上讲，我们应该选择这种初始化分布，以便生成的网络集合在函数逼近任务方面表现良好。本节对我们自己进行初始化，以分析这样的集合。

## 偏差和权重的初始分布
在初始化分布的许多潜在合理选择中，明显的选择是高斯分布$正如我们所讨论的，高斯分布仅根据其均值和方差来定义，因此在理论上很容易指定和使用。它们也非常容易采样，这也是在实践中选择采样分布时的一个重要考虑因素。

特别是，为了初始化MLP，我们将从零均值高斯分布中独立地采样每个偏差和每个权重，方差如下

$$
\begin{aligned}
    
\end{aligned}
\tag{2.19}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{}
$$

$$
\begin{aligned}
    
\end{aligned}
\tag{2.35}
$$