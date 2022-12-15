# 3.3 波动

$$
\begin{aligned}
G_{2}^{(\ell)} \equiv G_{\alpha \alpha}^{(\ell)}=G^{(\ell)}(x, x) .    
\end{aligned}
\tag{3.17}
$$

$$
\begin{aligned}
& \mathbb{E}\left[z_{i_{1}}^{(1)} z_{i_{2}}^{(1)} z_{i_{3}}^{(1)} z_{i_{4}}^{(1)}\right] \\
= & \sum_{j_{1}, j_{2}, j_{3}, j_{4}=1}^{n_{0}} \mathbb{E}\left[W_{i_{1} j_{1}}^{(1)} W_{i_{2} j_{2}}^{(1)} W_{i_{3} j_{3}}^{(1)} W_{i_{4} j_{4}}^{(1)}\right] x_{j_{1}} x_{j_{2}} x_{j_{3}} x_{j_{4}} \\
= & \frac{C_{W}^{2}}{n_{0}^{2}} \sum_{j_{1}, j_{2}, j_{3}, j_{4}=1}^{n_{0}}\left(\delta_{i_{1} i_{2}} \delta_{j_{1} j_{2}} \delta_{i_{3} i_{4}} \delta_{j_{3} j_{4}}+\delta_{i_{1} i_{3}} \delta_{j_{1} j_{3}} \delta_{i_{2} i_{4}} \delta_{j_{2} j_{4}}+\delta_{i_{1} i_{4}} \delta_{j_{1} j_{4}} \delta_{i_{2} i_{3}} \delta_{j_{2} j_{3}}\right) x_{j_{1}} x_{j_{2}} x_{j_{3}} x_{j_{4}} \\
= & C_{W}^{2}\left(\delta_{i_{1} i_{2}} \delta_{i_{3} i_{4}}+\delta_{i_{1} i_{3}} \delta_{i_{2} i_{4}}+\delta_{i_{1} i_{4}} \delta_{i_{2} i_{3}}\right)\left(G_{2}^{(0)}\right)^{2}    
\end{aligned}
\tag{3.18}
$$

$$
\begin{aligned}
G_{2}^{(0)}=\frac{1}{n_{0}} \sum_{j=1}^{n_{0}} x_{j} x_{j} .    
\end{aligned}
\tag{3.19}
$$

$$
\begin{aligned}
& \mathbb{E}\left[z_{i_{1}}^{(\ell+1)} z_{i_{2}}^{(\ell+1)} z_{i_{3}}^{(\ell+1)} z_{i_{4}}^{(\ell+1)}\right] \\
= & \sum_{j_{1}, j_{2}, j_{3}, j_{4}=1}^{n_{\ell}} \mathbb{E}\left[W_{i_{1} j_{1}}^{(\ell+1)} W_{i_{2} j_{2}}^{(\ell+1)} W_{i_{3} j_{3}}^{(\ell+1)} W_{i_{4} j_{4}}^{(\ell+1)}\right] \mathbb{E}\left[z_{j_{1}}^{(\ell)} z_{j_{2}}^{(\ell)} z_{j_{3}}^{(\ell)} z_{j_{4}}^{(\ell)}\right] \\
= & \frac{C_{W}^{2}}{n_{\ell}^{2}} \sum_{j_{1}, j_{2}, j_{3}, j_{4}=1}^{n_{\ell}}\left(\delta_{i_{1} i_{2}} \delta_{j_{1} j_{2}} \delta_{i_{3} i_{4}} \delta_{j_{3} j_{4}}+\delta_{i_{1} i_{3}} \delta_{j_{1} j_{3}} \delta_{i_{2} i_{4}} \delta_{j_{2} j_{4}}+\delta_{i_{1} i_{4}} \delta_{j_{1} j_{4}} \delta_{i_{2} i_{3}} \delta_{j_{2} j_{3}}\right) \\
& \times \mathbb{E}\left[z_{j_{1}}^{(\ell)} z_{j_{2}}^{(\ell)} z_{j_{3}}^{(\ell)} z_{j_{4}}^{(\ell)}\right] \\
= & C_{W}^{2}\left(\delta_{i_{1} i_{2}} \delta_{i_{3} i_{4}}+\delta_{i_{1} i_{3}} \delta_{i_{2} i_{4}}+\delta_{i_{1} i_{4}} \delta_{i_{2} i_{3}}\right) \frac{1}{n_{\ell}^{2}} \sum_{j, k=1}^{n_{\ell}} \mathbb{E}\left[z_{j}^{(\ell)} z_{j}^{(\ell)} z_{k}^{(\ell)} z_{k}^{(\ell)}\right]    
\end{aligned}
\tag{3.20}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{i_{1}}^{(\ell)} z_{i_{2}}^{(\ell)} z_{i_{3}}^{(\ell)} z_{i_{4}}^{(\ell)}\right] \equiv\left(\delta_{i_{1} i_{2}} \delta_{i_{3} i_{4}}+\delta_{i_{1} i_{3}} \delta_{i_{2} i_{4}}+\delta_{i_{1} i_{4}} \delta_{i_{2} i_{3}}\right) G_{4}^{(\ell)}    
\end{aligned}
\tag{3.21}
$$

$$
\begin{aligned}
G_{4}^{(1)}=C_{W}^{2}\left(G_{2}^{(0)}\right)^{2},    
\end{aligned}
\tag{3.22}
$$

$$
\begin{aligned}
\frac{1}{n_{\ell}^{2}} \sum_{j, k=1}^{n_{\ell}} \mathbb{E}\left[z_{j}^{(\ell)} z_{j}^{(\ell)} z_{k}^{(\ell)} z_{k}^{(\ell)}\right]=\frac{1}{n_{\ell}^{2}} \sum_{j, k=1}^{n_{\ell}}\left(\delta_{j j} \delta_{k k}+\delta_{j k} \delta_{j k}+\delta_{j k} \delta_{k j}\right) G_{4}^{(\ell)}=\left(1+\frac{2}{n_{\ell}}\right) G_{4}^{(\ell)} .    
\end{aligned}
\tag{3.23}
$$

$$
\begin{aligned}
G_{4}^{(\ell+1)}=C_{W}^{2}\left(1+\frac{2}{n_{\ell}}\right) G_{4}^{(\ell)} .    
\end{aligned}
\tag{3.24}
$$

$$
\begin{aligned}
G_{4}^{(\ell)} & =C_{W}^{2 \ell}\left[\prod_{\ell^{\prime}=1}^{\ell-1}\left(1+\frac{2}{n_{\ell^{\prime}}}\right)\right]\left(G_{2}^{(0)}\right)^{2} \\
& =\left[\prod_{\ell^{\prime}=1}^{\ell-1}\left(1+\frac{2}{n_{\ell^{\prime}}}\right)\right]\left(G_{2}^{(\ell)}\right)^{2},    
\end{aligned}
\tag{3.25}
$$

$$
\begin{aligned}
G_{4}^{(\ell)}=\left(G_{2}^{(\ell)}\right)^{2},    
\end{aligned}
\tag{3.26}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{i_{1}}^{(\ell)} z_{i_{2}}^{(\ell)} z_{i_{3}}^{(\ell)} z_{i_{4}}^{(\ell)}\right]=\left(\delta_{i_{1} i_{2}} \delta_{i_{3} i_{4}}+\delta_{i_{1} i_{3}} \delta_{i_{2} i_{4}}+\delta_{i_{1} i_{4}} \delta_{i_{2} i_{3}}\right)\left(G_{2}^{(\ell)}\right)^{2} .    
\end{aligned}
\tag{3.27}
$$

$$
\begin{aligned}
G_{4}^{(\ell)}-\left(G_{2}^{(\ell)}\right)^{2} & =\left[\left(1+\frac{2}{n}\right)^{\ell-1}-1\right]\left(G_{2}^{(\ell)}\right)^{2} \\
& =\frac{2(\ell-1)}{n}\left(G_{2}^{(\ell)}\right)^{2}+O\left(\frac{1}{n^{2}}\right),    
\end{aligned}
\tag{3.28}
$$

$$
\begin{aligned}
\left.\mathbb{E}\left[z_{i_{1}}^{(\ell)} z_{i_{2}}^{(\ell)} z_{i_{3}}^{(\ell)} z_{i_{4}}^{(\ell)}\right]\right|_{\text {connected }}=\left(\delta_{i_{1} i_{2}} \delta_{i_{3} i_{4}}+\delta_{i_{1} i_{3}} \delta_{i_{2} i_{4}}+\delta_{i_{1} i_{4}} \delta_{i_{2} i_{3}}\right)\left[G_{4}^{(\ell)}-\left(G_{2}^{(\ell)}\right)^{2}\right],    
\end{aligned}
\tag{3.29}
$$

$$
\begin{aligned}
\mathbb{E}\left[\left(z_{j}^{(\ell)} z_{j}^{(\ell)}-G_{2}^{(\ell)}\right)\left(z_{k}^{(\ell)} z_{k}^{(\ell)}-G_{2}^{(\ell)}\right)\right]=G_{4}^{(\ell)}-\left(G_{2}^{(\ell)}\right)^{2}, \quad \text { for } j \neq k .    
\end{aligned}
\tag{3.30}
$$

$$
\begin{aligned}
\mathcal{O}^{(\ell)} \equiv \mathcal{O}\left(z^{(\ell)}\right) \equiv \frac{1}{n} \sum_{j=1}^{n} z_{j}^{(\ell)} z_{j}^{(\ell)}, \quad \text { for } \ell<L    
\end{aligned}
\tag{3.31}
$$

$$
\begin{aligned}
\mathbb{E}\left[\mathcal{O}^{(\ell)}\right]=\frac{1}{n} \sum_{j=1}^{n} \mathbb{E}\left[z_{j}^{(\ell)} z_{j}^{(\ell)}\right]=G_{2}^{(\ell)},    
\end{aligned}
\tag{3.32}
$$

$$
\begin{aligned}
\mathbb{E}\left[\left(\mathcal{O}^{(\ell)}-\mathbb{E}\left[\mathcal{O}^{(\ell)}\right]\right)^{2}\right] & =\frac{1}{n^{2}} \sum_{j, k=1}^{n} \mathbb{E}\left[z_{j}^{(\ell)} z_{j}^{(\ell)} z_{k}^{(\ell)} z_{k}^{(\ell)}\right]-\left(G_{2}^{(\ell)}\right)^{2} \\
& =\frac{1}{n^{2}} \sum_{j, k=1}^{n}\left(\delta_{j j} \delta_{k k}+\delta_{j k} \delta_{j k}+\delta_{j k} \delta_{k j}\right) G_{4}^{(\ell)}-\left(G_{2}^{(\ell)}\right)^{2} \\
& =\frac{2}{n} G_{4}^{(\ell)}+\left[G_{4}^{(\ell)}-\left(G_{2}^{(\ell)}\right)^{2}\right] \\
& =\frac{2 \ell}{n}\left(G_{2}^{(\ell)}\right)^{2}+O\left(\frac{1}{n^{2}}\right)    
\end{aligned}
\tag{3.33}
$$