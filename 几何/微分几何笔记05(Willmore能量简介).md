# Willmore能量简介

### 定义

本文定义曲面$S$的Willmore能量为
$$
\mathcal W:=\int_S(H^2-K)\mathrm d\sigma.
$$
其中$H^2-K=\dfrac{(\kappa_1-\kappa_2)^2}{4}$. 对闭曲面而言, 有
$$
\mathcal W=\int_SH^2\mathrm d\sigma-2\pi\chi(S).
$$

### 内蕴几何下的Willmore能量

##### $\mathbb R^n$下内蕴几何记号注释

度量: $(g_{i,j})_{n\times n}$. 第一基本形式
$$
I(\vec t)=\left(\sum_{i=1}^n X_i\cdot (u^i)_s\right)\cdot \left(\sum_{i=1}^n X_i\cdot (u^i)_s\right)=\sum_{i,j=1}^n g_{ij}(u^i)_s(u^j)_s.
$$
方向$\vec t$上的截面曲率为定义了第二基本形式
$$
II(\vec t)=\kappa\cos\theta(\vec t)=\kappa_n(\vec t)=\dot{\vec t}\cdot \vec n=\\\sum_{i,j=1}^n X_{ij}\cdot n \cdot (u^i_s u^j_s)\left[+\sum_{i=1}^n X_i\cdot n\cdot u_{ss}^{i}\right]=\sum_{i,j=1} b_{ij}u^i_su^j_s.
$$
相应的测地曲率为$\kappa\sin\theta$. 对非单位切向量$\vec u$, 截面曲率即$\dfrac{II(\vec u)}{I(\vec u)}$. 

考虑常截面曲率之条件, 即使得$(b_{ij})-\kappa_n(g_{ij})$不满秩的$\kappa_i$. 定义Gauss曲率
$$
K:=\prod_{i=1}^n\kappa_i=\det[(b_{ij})\cdot (g_{ij})^{-1}]=\dfrac{\det (b_{ij})}{\det(g_{ij})}.
$$
平均曲率(记$(g^{ij})=(g_{ij})^{-1}$). 
$$
nH:=\prod_{i=1}^n\kappa_i=\mathrm{trace}[(b_{ij})\cdot (g_{ij})^{-1}]=\sum_{i,j=1}^nb_{ij}g^{ji}.
$$
引入记号
$$
\begin{align*}
\partial_jX_{i}&=\left(\sum_{k=1}^n \Gamma_{ij}^k X_k\right)+b_{ij}\vec n\\
\partial_i\vec n&=-\sum_{j=1}^nb_i^j X_j
\end{align*}
$$
其中$\Gamma_{ij}^k$与$b_{ij}$关于指标$ij$对称. 注意到
$$
\partial_k g_{ij}=\sum_{l=1}^n\left(\Gamma_{ik}^l g_{lj}+\Gamma_{jk}^l g_{li}\right)
$$
从而$\sum_{l=1}^n\Gamma_{ij}^lg_{lk}=\dfrac{\partial_ig_{jk}+\partial_jg_{ki}-\partial_k g_{ij}}{2}$. 写作矩阵($i,j$)固定即
$$
(\Gamma_{ij}^l)_{1\times n}(g_{lk})_{n\times n}=\left(\dfrac{\partial_ig_{jk}+\partial_jg_{ki}-\partial_k g_{ij}}{2}\right)_{1\times n}.
$$
从而
$$
\Gamma_{ij}^k=\sum_{l=1}^n \left(g^{kl}\cdot \dfrac{\partial_ig_{jl}+\partial_jg_{li}-\partial_l g_{ij}}{2}\right)
$$
考虑$X_{ijk}=X_{ikj}$, 左侧等于
$$
\begin{align*}
X_{ijk}=&\left(b_{ij}\vec n+\sum_{m=1}^n\Gamma_{ij}^m X_m\right)_k\\
=&\partial_kb_{ij}\vec n-\sum_{l=1}^n b_{ij}b_{k}^lX_l+\sum_{l=1}^n\partial_k\Gamma_{ij}^l X_l+\sum_{m,l=1}^n\Gamma_{ij}^m\Gamma_{mk}^l X_l+\sum_{l=1}^n\Gamma_{ij}^l b_{lk}\vec n\\
=&\left(\partial_k b_{ij}+\sum_{l=1}^n\Gamma_{ij}^l b_{lk}\right)\vec n+\sum_{l=1}^n\left(\sum_{m=1}^n\Gamma_{ij}^m\Gamma_{mk}^l+\partial_k\Gamma_{ij}^l-b_{ij}b_k^l\right)X_l
\end{align*}
$$
保持各分量一致, 得
$$
\begin{align*}
\partial_k b_{ij}-\partial_j b_{ik}=&\sum_{m=1}^n\Gamma_{ij}^mb_{mj}-\Gamma_{ik}^mb_{mj}\\
b_{ij}b_k^l-b_{ik}b_j^l=&R_{ijk}^l=\partial_k\Gamma_{ij}^l-\partial_j\Gamma_{ik}^l+\sum_{m=1}^n(\Gamma_{ij}^m\Gamma_{mk}^l-\Gamma_{jk}^m\Gamma_{mj}^l)
\end{align*}
$$
注意到$(b_i^j)=(b_{ij})\cdot(g^{ij})$, 从而$\sum_{l=1}^nb_i^l g_{lj}=b_{ij}$​. 记
$$
R_{ijkl}=\sum_{m=1}^n R_{ijk}^m g_{ml}=\sum_{m=1}^n (b_{ij}b_k^m-b_{ik}b_j^m)g_{ml}=b_{ij}b_{kl}-b_{ik}b_{jl}.
$$
是故高斯曲率为$\dfrac{\det (b_{ij})}{\det (g_{ij})}=\dfrac{R_{1212}}{\det g}$. 

特别地, 记
$$
R_{ij}:=\sum_{l=1}^n R_{ilj}^l=\sum_{l,m=1}^nR_{ilkm} g^{ml}.
$$
##### 二维曲面的Willmore能量

二维情形下, $R_{ij}=Kg_{ij}$​. 从而
$$
Kg_{ij}=\sum_{l=1}^2R_{ilj}^l=\sum_{l=1}^2(b_{ij}b_l^l-b_{il}b_j^l)=2Hb_{ij}-\sum_{l=1}^2 b_j^lb_{il}.
$$
定义Ricci曲率$R:=\sum_{i,j=1}^n g^{ij}R_{ij}$, 从而二维情形下
$$
R=\sum_{i,j=1}^2 g^{ij}g_{ij}K=2K.
$$
因此
$$
R_{ijkl}=\dfrac{R}{2}(g_{ik}g_{jl}-g_{jk}g_{il})=K\det\begin{pmatrix}g_{ik}&g_{jk}\\g_{il}&g_{jl}\end{pmatrix}.
$$
与Gauss曲率公式相合. 再如
$$
\sum_{i,j=1}^2b_i^jb_j^i=\sum_{i,j,k=1}^2g^{ij}b_{jk}b^k_i=\sum_{i,j=1}^2g^{ij}(2H b_{ij}-Kg_{ij})=4H^2-2K.
$$

因此二维闭曲面的Willmore能量为
$$
\mathcal W=\dfrac{1}{4}\int_S\mathrm{trace}((\mathrm d N_p)^2)\mathrm d\sigma_p-\pi\chi(S).
$$
