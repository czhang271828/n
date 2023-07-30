**Ex.1** 使用球平均法解决Cauchy问题
$$
\left\{\begin{align*}
&\partial_{tt}u-\sum_{i=1}^{2n+3}\partial_{x_jx_j}u=0\\
&t=0:u=\varphi(x),u_t=\psi(x)
\end{align*}\right.
$$
解: 记
$$
M_u(t,x,r)=\int_{\partial B_{2n+3}(x,r)}u(t,y)\mathrm dS_y
$$
由于$\mathbb R^{2n+3}$中径向函数之Laplacian满足$\Delta=r^{-(2n+2)}\partial_r(r^{2n+2}\partial_r)$, 故原问题转化为
$$
\left\{\begin{align*}
&\partial_{tt}M_u=r^{-(2n+2)}\partial_r(r^{2n+2}\partial_r)M_u\\
&t=0:M_u=\int_{\partial B_{2n+3}(x,r)}\varphi(y)\mathrm dS_y\\
&t=0:\partial_tM_u=\int_{\partial B_{2n+3}(x,r)}\psi(y)\mathrm dS_y\\
\end{align*}\right.
$$
下仅需证明, 存在算子$\mathcal A_n(r,\partial_r)$使得$\mathcal A_n r^{-{(2n+2)}}\partial_r(r^{2n+2}\partial_r)\mathcal A_n^{-1}=\partial_{rr}$. 

设$\mathcal B_nr^{2n+1}=\mathcal A_n$, 则$\mathcal B_n(\partial_{rr}-2n/r\cdot\partial_r)\mathcal B_n^{-1}=\partial_{rr}$. 注意到递推式
$$
(r^{-1}\partial_r)(\partial_{rr}-2(n+2)/r\cdot\partial_r)=(\partial_{rr}-2n/r\cdot \partial_r)(r^{-1}\partial_r)
$$
从而
$$
[(r^{-1}\partial_r)^n r^{2n+1}](r^{-(2n+2)}\partial_r(r^{2n+2}\partial_r))[(r^{-1}\partial_r)^n r^{2n+1}]^{-1}=\partial_{rr.}
$$
令$[(r^{-1}\partial_r)^n r^{2n+1}]M_u=v$, 则PDE化为
$$
\left\{\begin{align*}
&\partial_{tt}v=\partial_{rr}v\\
&t=0:v=[(r^{-1}\partial_r)^n r^{2n+1}]\int_{\partial B_{2n+3}(x,r)}\varphi(y)\mathrm dS_y\\
&t=0:\partial_tv=[(r^{-1}\partial_r)^n r^{2n+1}]\int_{\partial B_{2n+3}(x,r)}\psi(y)\mathrm dS_y\\
\end{align*}\right.
$$
解得(不妨限定$r< t$)
$$
\begin{align*}
v=&\dfrac{[((t+r)^{-1}\partial_{t+r})^n (t+r)^{2n+1}]\int_{\partial B_{2n+3}(x,r+t)}\varphi(y)\mathrm dS_y}{2}\\
&-\dfrac{[((t-r)^{-1}\partial_{t-r})^n (t-r)^{2n+1}]\int_{\partial B_{2n+3}(x,r-t)}\varphi(y)\mathrm dS_y}{2}\\
&+\dfrac{1}{2}\int_{t-r}^{t+r}(\xi^{-1}\partial_{\xi})^n\xi^{2n+1}\int_{\partial B_{2n+3}(x,\xi)}\psi(y)\mathrm dS_y\mathrm d\xi\\
\end{align*}
$$
当$r\ll 1$​时有
$$
v=r^{2n+1}\partial_t((t^{-1}\partial_t)^n t^{2n+1}\int_{\partial B_{2n+3}(x,t)}\varphi(y)\mathrm dS_y)+r^{2n+1}(t^{-1}\partial_t)^nt^{2n+1}\int_{\partial B_{2n+3}(x,t)}\psi(y)\mathrm d S_y.
$$
注意到在小范围内, $v\sim kr^{2n+1}$, 且$(r^{-1}\partial _r)^n r^{2n+1}:\dfrac{k}{(2n+1)!!}\mapsto kr^{2n+1}$. 从而
$$
\begin{align*}
u=&\lim_{r\to 0}\dfrac{1}{|\partial B_{2n+3}(x,r)|}M_u(t,x,r)\\
=&\lim_{r\to0}\dfrac{1}{|\omega_{2n+3}|r^{2n+2}}\cdot\dfrac{1}{(2n+1)!!}\cdot\partial_t((t^{-1}\partial_t)^n t^{2n+1}\int_{\partial B_{2n+3}(x,r)}\varphi(y)\mathrm dS_y)\\
&+\dfrac{1}{|\omega_{2n+3}|r^{2n+2}}\cdot\dfrac{1}{(2n+1)!!}\cdot (t^{-1}\partial_t)^nt^{2n+1}\int_{\partial B_{2n+3}(x,r)}\psi(y)\mathrm d S_y\\
=&\dfrac{1}{(2n+1)!!|\omega_{2n+3}|}\partial_t((t^{-1}\partial_t)^n t^{2n+1}\int_{\partial B_{2n+3}(0,1)}\varphi(x+t\xi)\mathrm dS_\xi)\\
&+\dfrac{1}{(2n+1)!!|\omega_{2n+3}|}(t^{-1}\partial_t)^nt^{2n+1}\int_{\partial B_{2n+3}(0,1)}\psi(x+t\xi)\mathrm d S_\xi\\
\end{align*}
$$
其中$(2n+1)!!|\omega_{2n+3}|=2^{n+2}\pi^{n+1}$. 综上
$$
\begin{align*}
u=&\dfrac{1}{2^{n+2}\pi^{n+1}}\left[\partial_t((t^{-1}\partial_t)^n t^{2n+1}\int_{\partial B_{2n+3}(0,1)}\varphi(x+t\xi)\mathrm dS_\xi)\right.\\
&+\left.(t^{-1}\partial_t)^nt^{2n+1}\int_{\partial B_{2n+3}(0,1)}\psi(x+t\xi)\mathrm d S_\xi\right]\\
\end{align*}.
$$
