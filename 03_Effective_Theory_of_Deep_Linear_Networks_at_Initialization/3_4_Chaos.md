## 3.4 混沌

$$
\begin{aligned}
& \mathbb{E}\left[z_{i_{1}}^{(1)} z_{i_{2}}^{(1)} \cdots z_{i_{2 m-1}}^{(1)} z_{i_{2 m}}^{(1)}\right] \\
= & \sum_{j_{1}, \ldots, j_{2 m}=1}^{n_{0}} \mathbb{E}\left[W_{i_{1} j_{1}}^{(1)} W_{i_{2} j_{2}}^{(1)} \cdots W_{i_{2 m-1} j_{2 m-1}}^{(1)} W_{i_{2 m} j_{2 m}}^{(1)}\right] x_{j_{1}} x_{j_{2}} \cdots x_{j_{2 m-1}} x_{j_{2 m}} \\
= & \left(\sum_{\text {all parings }} \delta_{i_{k_{1}} i_{k_{2}}} \cdots \delta_{i_{k_{2 m-1}} i_{k_{2 m}}}\right) C_{W}^{m}\left(G_{2}^{(0)}\right)^{m} \\
= & \left(\sum_{\text {all parings }} \delta_{i_{k_{1}} i_{k_{2}}} \cdots \delta_{i_{k_{2 m-1}} i_{k_{2 m}}}\right)\left(G_{2}^{(1)}\right)^{m},    
\end{aligned}
\tag{3.34}
$$

$$
\begin{aligned}
S\left(z^{(1)}\right)=\frac{1}{2 G_{2}^{(1)}} \sum_{i=1}^{n_{1}} z_{i}^{(1)} z_{i}^{(1)} \text {. }    
\end{aligned}
\tag{3.35}
$$

$$
\begin{aligned}
& \mathbb{E}\left[z_{i_{1}}^{(\ell+1)} z_{i_{2}}^{(\ell+1)} z_{i_{3}}^{(\ell+1)} z_{i_{4}}^{(\ell+1)} z_{i_{5}}^{(\ell+1)} z_{i_{6}}^{(\ell+1)}\right] \\
& =\sum_{j_{1}, j_{2}, j_{3}, j_{4}, j_{5}, j_{6}=1}^{n_{\ell}} \mathbb{E}\left[W_{i_{1} j_{1}}^{(\ell+1)} W_{i_{2} j_{2}}^{(\ell+1)} W_{i_{3} j_{3}}^{(\ell+1)} W_{i_{4} j_{4}}^{(\ell+1)} W_{i_{5} j_{5}}^{(\ell+1)} W_{i_{6} j_{6}}^{(\ell+1)}\right] \mathbb{E}\left[z_{j_{1}}^{(\ell)} z_{j_{2}}^{(\ell)} z_{j_{3}}^{(\ell)} z_{j_{4}}^{(\ell)} z_{j_{5}}^{(\ell)} z_{j_{6}}^{(\ell)}\right] \\
& =C_{W}^{3}\left(\delta_{i_{1} i_{2}} \delta_{i_{3} i_{4}} \delta_{i_{5} i_{6}}+\delta_{i_{1} i_{3}} \delta_{i_{2} i_{4}} \delta_{i_{5} i_{6}}+\delta_{i_{1} i_{4}} \delta_{i_{2} i_{3}} \delta_{i_{5} i_{6}}\right. \\
& +\delta_{i_{1} i_{2}} \delta_{i_{3} i_{5}} \delta_{i_{4} i_{6}}+\delta_{i_{1} i_{3}} \delta_{i_{2} i_{5} \delta_{5}} \delta_{i_{4} i_{6}}+\delta_{i_{1} i_{5}} \delta_{i_{2} i_{3}} \delta_{i_{4} i_{6}} \\
& +\delta_{i_{1} i_{2}} \delta_{i_{5} i_{4}} \delta_{i_{3} i_{6}}+\delta_{i_{1} i_{5}} \delta_{i_{2} i_{4}} \delta_{i_{3} i_{6} i_{6}}+\delta_{i_{1} i_{4}} \delta_{i_{3} i_{4}} \delta_{i_{2} i_{5} i_{6}} \delta_{i_{3} i_{6}} \\
& +\delta_{i_{1} i_{5}} \delta_{i_{3} i_{4}} \delta_{i_{2} i_{6}}+\delta_{i_{1} i_{3}} \delta_{i_{5} i_{4}} \delta_{i_{2} i_{6}}+\delta_{i_{1} i_{4}} \delta_{i_{5} i_{3}} \delta_{i_{2} i_{6}} \\
& \left.+\delta_{i_{5} i_{2}} \delta_{i_{3} i_{4}} \delta_{i_{1} i_{6}}+\delta_{i_{5} i_{3}} \delta_{i_{2} i_{4}} \delta_{i_{1} i_{6}}+\delta_{i_{5} i_{4}} \delta_{i_{2} i_{3}} \delta_{i_{1} i_{6}}\right) \frac{1}{n_{\ell}^{3}} \sum_{i, j, k=1}^{n_{\ell}} \mathbb{E}\left[z_{i}^{(\ell)} z_{i}^{(\ell)} z_{j}^{(\ell)} z_{j}^{(\ell)} z_{k}^{(\ell)} z_{k}^{(\ell)}\right],    
\end{aligned}
\tag{3.36}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{i_{1}}^{(\ell)} z_{i_{2}}^{(\ell)} z_{i_{3}}^{(\ell)} z_{i_{4}}^{(\ell)} z_{i_{5}}^{(\ell)} z_{i_{6}}^{(\ell)}\right] \equiv\left(\delta_{i_{1} i_{2}} \delta_{i_{3} i_{4}} \delta_{i_{5} i_{6}}+\ldots+\delta_{i_{5} i_{4}} \delta_{i_{2} i_{3}} \delta_{i_{1} i_{6}}\right) G_{6}^{(\ell)},    
\end{aligned}
\tag{3.37}
$$

$$
\begin{aligned}
\frac{1}{n_{\ell}^{3}} \sum_{i, j, k=1}^{n_{\ell}} \mathbb{E}\left[z_{i}^{(\ell)} z_{i}^{(\ell)} z_{j}^{(\ell)} z_{j}^{(\ell)} z_{k}^{(\ell)} z_{k}^{(\ell)}\right]    
\end{aligned}
\tag{3.38}
$$

$$
\begin{aligned}
\frac{1}{n_{\ell}^{3}} \sum_{i, j, k=1}^{n_{\ell}} \delta_{i i} \delta_{j j} \delta_{k k}=1    
\end{aligned}
\tag{3.39}
$$

$$
\begin{aligned}
\frac{1}{n_{\ell}^{3}} \sum_{i, j, k=1}^{n_{\ell}} \delta_{i j} \delta_{j i} \delta_{k k}=\frac{1}{n_{\ell}},    
\end{aligned}
\tag{3.40}
$$

$$
\begin{aligned}
\frac{1}{n_{\ell}^{3}} \sum_{i, j, k=1}^{n_{\ell}} \delta_{i j} \delta_{j k} \delta_{k i}=\frac{1}{n_{\ell}^{2}} .    
\end{aligned}
\tag{3.41}
$$

$$
\begin{aligned}
G_{6}^{(\ell+1)}=C_{W}^{3}\left(1+\frac{6}{n_{\ell}}+\frac{8}{n_{\ell}^{2}}\right) G_{6}^{(\ell)},    
\end{aligned}
\tag{3.42}
$$

$$
\begin{aligned}
G_{6}^{(\ell)} & =C_{W}^{3 \ell}\left[\prod_{\ell^{\prime}=1}^{\ell-1}\left(1+\frac{6}{n_{\ell^{\prime}}}+\frac{8}{n_{\ell^{\prime}}^{2}}\right)\right]\left(G_{2}^{(0)}\right)^{3} \\
& =\left[\prod_{\ell^{\prime}=1}^{\ell-1}\left(1+\frac{6}{n_{\ell^{\prime}}}+\frac{8}{n_{\ell^{\prime}}^{2}}\right)\right]\left(G_{2}^{(\ell)}\right)^{3} .    
\end{aligned}
\tag{3.43}
$$

$$
\begin{aligned}
\mathbb{E}\left[z_{i_{1}}^{(\ell)} z_{i_{2}}^{(\ell)} \cdots z_{i_{2 m-1}}^{(\ell)} z_{i_{2 m}}^{(\ell)}\right]=\left(\sum_{\text {all parings }} \delta_{i_{k_{1}} i_{k_{2}}} \cdots \delta_{i_{k_{2 m-1}} i_{k_{2 m}}}\right) G_{2 m}^{(\ell)},    
\end{aligned}
\tag{3.44}
$$

$$
\begin{aligned}
 G_{2 m}^{(\ell+1)}=c_{2 m}\left(n_{\ell}\right) C_{W}^{m} G_{2 m}^{(\ell)},   
\end{aligned}
\tag{3.45}
$$

$$
\begin{aligned}
c_{2 m}(n)=\left(1+\frac{2}{n}\right)\left(1+\frac{4}{n}\right) \cdots\left(1+\frac{2 m-2}{n}\right)=\frac{\left(\frac{n}{2}-1+m\right) !}{\left(\frac{n}{2}-1\right) !}\left(\frac{2}{n}\right)^{m} .    
\end{aligned}
\tag{3.46}
$$

$$
\begin{aligned}
G_{2 m}^{(\ell)}=\left[\prod_{\ell^{\prime}=1}^{\ell-1} c_{2 m}\left(n_{\ell}^{\prime}\right)\right]\left(G_{2}^{(\ell)}\right)^{m}     
\end{aligned}
\tag{3.47}
$$

$$
\begin{aligned}
\lim _{n \rightarrow \infty} c_{2 m}(n)=1 .    
\end{aligned}
\tag{3.48}
$$

$$
\begin{aligned}
G_{2 m}^{(L)}=\left(G_{2}^{(L)}\right)^{m},    
\end{aligned}
\tag{3.49}
$$

$$
\begin{aligned}
G_{2 m}^{(L)}=\left[c_{2 m}(n)\right]^{L-1}\left(G_{2}^{(L)}\right)^{m} .    
\end{aligned}
\tag{3.50}
$$

$$
\begin{aligned}
\lim _{n \rightarrow \infty} \lim _{L \rightarrow \infty} G_{2 m}^{(L)} \neq \lim _{L \rightarrow \infty} \lim _{n \rightarrow \infty} G_{2 m}^{(L)} .    
\end{aligned}
\tag{3.51}
$$

$$
\begin{aligned}
r \equiv \frac{L}{n} .
\end{aligned}
\tag{3.52}
$$

$$
\begin{aligned}
c_{2 m}(n)=1+\frac{1}{n}\left(\sum_{s=1}^{m-1} 2 s\right)+O\left(\frac{1}{n^{2}}\right)=1+\frac{m(m-1)}{n}+O\left(\frac{1}{n^{2}}\right),  
\end{aligned}
\tag{3.53}
$$

$$
\begin{aligned}
\lim _{L \rightarrow \infty}\left[1+\frac{a}{L}+O\left(\frac{1}{L^{2}}\right)\right]^{L}=e^{a},
\end{aligned}
\tag{3.54}
$$

$$
\begin{aligned}
G_{2 m}^{(L)} \rightarrow e^{m(m-1) r}\left(G_{2}^{(L)}\right)^{m} .  
\end{aligned}
\tag{3.55}
$$

$$
\begin{aligned}
G_{4}^{(L)}-\left(G_{2}^{(L)}\right)^{2} & =\left(e^{2 r}-1\right)\left(G_{2}^{(0)}\right)^{2} \\
& =2 r\left(G_{2}^{(0)}\right)^{2}+O\left(r^{2}\right) .    
\end{aligned}
\tag{3.56}
$$

$$
\begin{aligned}
G_{6}^{(L)}-3 G_{2}^{(L)} G_{4}^{(L)}+2\left(G_{2}^{(L)}\right)^{3} & =\left(e^{6 r}-3 e^{2 r}+2\right)\left(G_{2}^{(0)}\right)^{3} \\
& =12 r^{2}\left(G_{2}^{(0)}\right)^{3}+O\left(r^{3}\right)    
\end{aligned}
\tag{3.57}
$$