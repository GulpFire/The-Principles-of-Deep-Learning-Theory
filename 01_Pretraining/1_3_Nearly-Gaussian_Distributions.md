# 近似高斯分布
$$
\begin{aligned}
p(z) \propto e^{-S(z)} .
\end{aligned}
\tag{1.62}
$$

$$
\begin{aligned}
\int d^{N} z p(z)=1 .
\end{aligned}
\tag{1.63}
$$

$$
\begin{aligned}
Z \equiv \int d^{N} z e^{-S(z)}
\end{aligned}
\tag{1.64}
$$

$$
\begin{aligned}
p(z) \equiv \frac{e^{-S(z)}}{Z} .
\end{aligned}
\tag{1.65}
$$

$$
\begin{aligned}
S(z)=\frac{1}{2} \sum_{\mu, \nu=1}^{N} K^{\mu \nu} z_{\mu} z_{\nu},
\end{aligned}
\tag{1.66}
$$

$$
\begin{aligned}
Z=\int d^{N} z e^{-S(z)}=I_{K}=\sqrt{|2 \pi K|} .
\end{aligned}
\tag{1.67}
$$

$$
\begin{aligned}
\langle\mathcal{O}(z)\rangle_{K} \equiv \frac{1}{\sqrt{|2 \pi K|}} \int\left[\prod_{\mu=1}^{N} d z_{\mu}\right] \exp \left(-\frac{1}{2} \sum_{\mu, \nu=1}^{N} K^{\mu \nu} z_{\mu} z_{\nu}\right) \mathcal{O}(z)
\end{aligned}
\tag{1.68}
$$

$$
\begin{aligned}
\left\langle z_{\mu_{1}} z_{\mu_{2}} \cdots z_{\mu_{2 m}}\right\rangle_{K}=\sum_{\text {all pairing }} K_{\mu_{k_{1}} \mu_{k_{2}}} \cdots K_{\mu_{k_{2 m-1}} \mu_{k_{2 m}}} .
\end{aligned}
\tag{1.69}
$$

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }}=O(\epsilon) .
\end{aligned}
\tag{1.70}
$$

$$
\begin{aligned}
S(z)=\frac{1}{2} \sum_{\mu, \nu=1}^{N} K^{\mu \nu} z_{\mu} z_{\nu}+\frac{\epsilon}{4 !} \sum_{\mu, \nu, \rho, \lambda=1}^{N} V^{\mu \nu \rho \lambda} z_{\mu} z_{\nu} z_{\rho} z_{\lambda},
\end{aligned}
\tag{1.71}
$$

$$
\begin{aligned}
Z & =\int\left[\prod_{\mu} d z_{\mu}\right] e^{-S(z)} \\
& =\int\left[\prod_{\mu} d z_{\mu}\right] \exp \left(-\frac{1}{2} \sum_{\mu, \nu} K^{\mu \nu} z_{\mu} z_{\nu}-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right) \\
& =\sqrt{|2 \pi K|}\left\langle\exp \left(-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right)\right\rangle_{K} .
\end{aligned}
\tag{1.72}
$$

$$
\begin{aligned}
Z & =\sqrt{|2 \pi K|}\left\langle 1-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}+O\left(\epsilon^{2}\right)\right\rangle_{K} \\
& =\sqrt{|2 \pi K|}\left[1-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}\left\langle z_{\rho_{1}} z_{\rho_{2}} z_{\rho_{3}} z_{\rho_{4}}\right\rangle_{K}+O\left(\epsilon^{2}\right)\right] \\
& =\sqrt{|2 \pi K|}\left[1-\frac{\epsilon}{24} \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}}\left(K_{\rho_{1} \rho_{2}} K_{\rho_{3} \rho_{4}}+K_{\rho_{1} \rho_{3}} K_{\rho_{2} \rho_{4}}+K_{\rho_{1} \rho_{4}} K_{\rho_{2} \rho_{3}}\right)+O\left(\epsilon^{2}\right)\right] \\
& =\sqrt{|2 \pi K|}\left[1-\frac{1}{8} \epsilon \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} K_{\rho_{1} \rho_{2}} K_{\rho_{3} \rho_{4}}+O\left(\epsilon^{2}\right)\right]
\end{aligned}
\tag{1.73}
$$

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

$$
\begin{aligned}

\end{aligned}
\tag{1.75}
$$

$$
\begin{aligned}

\end{aligned}
\tag{1.76}
$$

$$
\begin{aligned}

\end{aligned}
\tag{1.77}
$$

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu_{1}} z_{\mu_{2}} z_{\mu_{3}} z_{\mu_{4}}\right]\right|_{\text {connected }}=-\epsilon \sum_{\rho_{1}, \ldots, \rho_{4}} V^{\rho_{1} \rho_{2} \rho_{3} \rho_{4}} K_{\mu_{1} \rho_{1}} K_{\mu_{2} \rho_{2}} K_{\mu_{3} \rho_{3}} K_{\mu_{4} \rho_{4}}+O\left(\epsilon^{2}\right) \text {. }
\end{aligned}
\tag{1.78}
$$

$$
\begin{aligned}
\left|s^{\mu_{1} \cdots \mu_{2 m}}\right| \ll\left|K^{\mu \nu}\right|^{m},

p(x, y)=p(x) p(y) .
\end{aligned}
\tag{1.79}
$$

$$
\begin{aligned}


p(z)=\frac{1}{\sqrt{|2 \pi K|}} \exp \left(-\sum_{\mu=1}^{N} \frac{u_{\mu}^{2}}{2 \lambda_{\mu}}\right)=\prod_{\mu=1}^{N}\left(\frac{e^{-\frac{u_{\mu}^{2}}{2 \lambda_{\mu}}}}{\sqrt{2 \pi \lambda_{\mu}}}\right)=p\left(u_{1}\right) \cdots p\left(u_{N}\right) .
\end{aligned}
\tag{1.80}
$$

$$
\begin{aligned}
S(z)=\frac{1}{2} \sum_{\mu, \nu=1}^{N} K^{\mu \nu} z_{\mu} z_{\nu}+\sum_{m=2}^{k} \frac{1}{(2 m) !} \sum_{\mu_{1}, \ldots, \mu_{2 m}=1}^{N} s^{\mu_{1} \cdots \mu_{2 m}} z_{\mu_{1}} \cdots z_{\mu_{2 m}},
\end{aligned}
\tag{1.81}
$$

$$
\begin{aligned}
\left|s^{\mu_{1} \cdots \mu_{2 m}}\right| \ll\left|K^{\mu \nu}\right|^{m},
\end{aligned}
\tag{1.82}
$$

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{\mu_{1}} \cdots z_{\mu_{2 m}}\right]\right|_{\text {connected }}=O\left(\epsilon^{m-1}\right),
\end{aligned}
\tag{1.83}
$$