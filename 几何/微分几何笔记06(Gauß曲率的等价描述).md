# Gauß曲率的等价描述

### Gauß映射解释

考虑$N:U_p(\subset S\subset \mathbb R^2)\to S^2$​, 则
$$
\begin{align*}
\lim_{U_p\to \{p\}}\dfrac{\mathrm{Area}(N_p(U_p))}{\mathrm {Area}(U_p)}=&\dfrac{|-\mathrm dN_p(X_u)\wedge -\mathrm dN_p(X_v)|}{|X_u\wedge X_v|}\\
=&\dfrac{|(b_1^1X_u+b_1^2X_v)\wedge (b_2^1X_u+b_2^1X_v)|}{|X_u\wedge X_v|}\\
=&\dfrac{|K|\cdot |X_u\wedge X_v|}{|X_u\wedge X_v|}\\
=&|K|
\end{align*}
$$

### 平行移动解释

设$\gamma:[0,l]\to S$曲面上包含$p$的某一具有弧长参数的闭曲线. 记$\phi:[0,l]\to S^1$为角度函数. 记正交参数网$X(u,v)$下的两个单位向量为$e_1,e_2$, 则不妨设$\gamma$上向量场$w=e_1\cos\phi+e_2\sin\phi$, 记$w'=-e_1\sin\phi+e_2\cos\phi$为在切平面上逆时针旋转$\pi/2$​的垂直单位向量, 从而测地曲率
$$
\begin{align*}
\kappa_g=&\left< D_{\vec t}w,w'\right>\\
=&\phi'\left< w',w'\right>+\left< \cos\theta D_{\vec t}(e_1)+\sin\theta D_{\vec t}(e_2),w'\right>\\
=&\phi'+\left< D_{\vec t}e_1,e_2\right>\\
=&\phi'+\left< D_{\vec t} (X_1/\sqrt E),X_2/\sqrt{G}\right>\\
=&\phi'+\left< X_1(1/\sqrt E)_s,X_2/\sqrt{G}\right>+\dfrac{1}{\sqrt{EG}}\left< D_{\vec t}X_1,X_2\right>\\
=&\phi'+\dfrac{1}{\sqrt{EG}}\left< u_sD_1X_1+v_sD_2X_1,X_2\right>\\
=&\phi'+\dfrac{1}{\sqrt{EG}}\left< \mathrm{proj}_{T_pS}(u_sX_{11}+v_sX_{21}),X_2\right>\\
=&\phi'+\dfrac{1}{\sqrt{EG}}(-u_s\cdot E_v/2+v_s\cdot G_u/2)\\
=&\phi'-\dfrac{1}{2\sqrt{EG}}(G_u\cdot v_s-E_v\cdot u_s)
\end{align*}
$$
积分得
$$
\begin{align*}
\oint_{\gamma}\kappa_g\mathrm ds-(\phi(l)-\phi(0))=&-\int_{D}\dfrac{\sqrt G_u}{\sqrt E}\mathrm dv-\dfrac{\sqrt E_v}{\sqrt G}\mathrm du\\
=&\int_D\left(\dfrac{\sqrt G_u}{\sqrt E}\right)_u+\left(\dfrac{\sqrt E_v}{\sqrt G}\right)_v\mathrm d u\mathrm dv\\
=&-\int_D-\dfrac{1}{\sqrt{EG}}\left[\left(\dfrac{\sqrt G_u}{\sqrt E}\right)_u+\left(\dfrac{\sqrt E_v}{\sqrt G}\right)_v\right]\mathrm d\sigma\\
=&-\int_DK\mathrm d\sigma
\end{align*}
$$
特别地, 当$w$为$\gamma$上平行移动的向量场时, $\kappa_g=0$. 从而
$$
K=\lim_{D\to \{p\}}\dfrac{\phi(l)-\phi(0)}{\mathrm{Area}(D)}.
$$

### 测地坐标解释

定义$p$​点处测地线$\gamma_v(t)$​使得$\gamma_v(0)=p$​, $\gamma_v'(0)=v$​. 定义指数映射$\exp_p(v)=\gamma_v(1)$​, 其中记$\exp_p(0)=p$​. 此处可视$G=S$​为Lie群, $v$​生成的左不变向量场对应的单参数变化群为$\{\varphi_t\}$​. 指数映射满足

1. $\exp_p:T_pG\to G$, $v\mapsto \varphi_t(e)=\gamma(1,v)$.

2. $\exp(tX)=\varphi(t,e)=\varphi_t(e)$.

3. $\exp((t_1+t_2)X)=\varphi(t_1X)\cdot\varphi(t_2X)$, $t\in\mathbb R$.

4. $\exp(-tX)=\exp(tX)^{-1}$.  

5. 记$\mathfrak g=(T_pG,[,])$为有限维Lie代数, 则切映射
   $$
   \mathrm d\exp_p:T_0\mathfrak g=\mathfrak g\to T_pG=\mathfrak g
   $$
   为恒同映射. 

例如记$GL(n,\mathbb R)$的切空间为$gl(n,\mathbb R)$, 记$A\in gl(n,\mathbb R)$的左不变向量场为$X_A$, 曲线$\gamma(t,A)$从$I_n$出发. 从而据定义得:
$$
X_A(B)=\dfrac{\mathrm d}{\mathrm dt}|_{t=0}(B\circ\gamma(t,A))=B\cdot A.
$$
从而$X_A$的积分曲线$\xi_A(t)$满足$\xi_A(0)=I_n$, $\xi'_A(0)=\xi_A(t)\cdot A$. 解得$\xi_A(t)=e^{tA}$. 从而指数映照为$\exp:gl(n,\mathbb R)\to GL(n,\mathbb R),A\mapsto e^A$. 相应的Lie代数$\mathfrak g=(gl(n,\mathbb R),[,])$可如下计算(其中$\varphi_t(P)=P\cdot e^{tA}$为$A$生成的单参数变换群): 
$$
\begin{align*}
[A,B]=L_AB=&\dfrac{\mathrm d}{\mathrm dt}|_{t=0}\mathrm d\varphi_{-t}(X_B(\varphi_t(A)))\\
=&\dfrac{\mathrm d}{\mathrm dt}|_{t=0}(e^{tA}\cdot B\cdot e^{-tA})\\
=&AB-BA
\end{align*}
$$
对一般的二维正则曲面$S$​, 记$p$​点测地凸邻域由指数映射$\exp_p(\rho ,\theta)=\exp_p(\rho e^{i\theta})$​给出. 据定义, $p$​点邻域处
$$
\partial_\rho \exp_p(\rho,\theta)=\partial_\rho\gamma_{\rho e^{i\theta}}(1)=\partial_\rho\gamma_{e^{i\theta}}(\rho)
$$
为切向量(单位方向向量), 从而$E=1$. 而测地线关于$\rho$的二阶导数与平面垂直, 因此$\Gamma_{11}^2=0$. 因此
$$
0=E_\rho=2(\Gamma_{11}^1E+\Gamma_{11}^2F)=2\Gamma_{11}^1=0.
$$
进而$F_\rho=\Gamma_{11}^1F+\Gamma_{11}^2G+\dfrac{1}{2}E_\rho=0$. 由于$\rho\to 0$时$F=0$, 故$F\equiv 0$. 

从几何角度而言
$$
\|\partial_\theta\exp_p(\rho,\theta)\|=\|\partial_\theta\gamma_{e^{i\theta}}(\rho)\|=\lim_{\Delta\theta\to 0}\dfrac{\|\rho e^{i(\theta_0+\Delta\theta)}-\rho e^{i\theta_0}\|}{|\Delta\theta|}=\rho.
$$
从而$\lim_{\rho\to 0}\dfrac{\sqrt G}{\rho}=1$​. 

测地坐标下Gauß曲率
$$
K=-\dfrac{1}{\sqrt{EG}}\left[\left(\dfrac{\sqrt G_u}{\sqrt E}\right)_u+\left(\dfrac{\sqrt E_v}{\sqrt G}\right)_v\right]=\dfrac{-\sqrt{G}_{\rho\rho}}{\sqrt G}.
$$
从而常Gauß曲率曲面满足微分方程$\sqrt{G}_{\rho\rho}+K\sqrt G=0$, 列举如下:

1. $K=0$时, $\sqrt G=\rho f_1(\theta)+f_2(\theta)$. 由$\lim_{\rho\to 0}\dfrac{\sqrt G}{\rho}=1$知$G=\rho^2$. 
2. $K>0$时, $\sqrt G=A_1(\theta)\cos (\rho\sqrt K)+A_2(\theta)\sin (\rho\sqrt K)$. 由$\lim_{\rho\to 0}\dfrac{\sqrt G}{\rho}=1$知$G=\dfrac{1}{K}\sin^2(\sqrt K\rho)$.
3. $K<0$时, 同理解得$G=-\dfrac{1}{K}\sinh^2(\sqrt{-K}\rho)$.

另一方面, 当$p$点处Gauß曲率不为$0$时, 记$\sqrt G=\sum_{k=0}^\infty a_k\rho^k$, 由$\sqrt{G}_{\rho\rho}+K\sqrt G=0$得
$$
\sum_{k=0}^\infty((k+1)(k+2)a_{k+2}+Ka_k)\rho^k\equiv 0.
$$
因此
$$
\sqrt G=\dfrac{1}{\sqrt K}\sum_{k\geq 0}(-1)^{k}\dfrac{(\sqrt K\rho)^{2k+1}}{(2k+1)!}.
$$
局部来看, 记半径为$\rho=r\ll 1$的测地圆弧长为$L$, 从而
$$
L=\lim_{\varepsilon\to 0}\int_{S^1\setminus (-\varepsilon,\varepsilon)}\sqrt G\mathrm d\theta=2\pi r-\dfrac{\pi}{3}r^3K(p)+O(r^5).
$$
从而
$$
K(p)=\lim_{r\to 0}\dfrac{3}{\pi}\dfrac{2\pi r-L}{r^3}.
$$
同理, 记半径为$\rho=r\ll 1$的测地圆面积为$A$, 则
$$
K(p)=\lim_{r\to 0}\dfrac{12}{\pi}\dfrac{\pi r^2-A}{r^4}.
$$

### Gauß-Bonnet公式解释

整体的Gauß曲率可用以下公式计算.

Gauß-Bonnet公式叙述如是: 边缘分段可微的曲面$D$满足
$$
2\pi\chi(D)=\int_DK\mathrm d\sigma+\int_{\partial D}\kappa_g\mathrm ds+\sum\alpha.
$$
Euler-Poincaré定义叙述如是: 
$$
2\pi\sum_{p\in D} I_p=\int_DK\mathrm d\sigma.
$$
