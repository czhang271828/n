# Torus上的测地线

### $\mathbb R^n$中测地线的等价定义

注意到第一基本形式为$\mathrm ds^2=\sum_{i,j=1}^n g_{ij}\mathrm du^i\mathrm du^j$. 记曲线$\gamma(t)=(u(t))$, 则记$\gamma:[t_1,t_2]\to C$, 则$C$长度为
$$
l[u,C]=\int_{t_1}^{t_2}\sqrt{\sum_{i,j=1}^n g_{ij} u^i_su^j_s}\mathrm dt.
$$
若$l[u,C]$局部极小, 即$l[u,\delta C+C]-l[u, C]=o(\delta u)$​时, 
$$
\delta\int_{t_1}^{t_2}\sum_{i,j=1}^n g_{ij} u^i_su^j_s\mathrm dt
$$
应当为$0$. 限定两端变分为$0$, 从而 
$$
\begin{align*}
0=&\delta\int_{t_1}^{t_2}\sum_{i,j=1}^n g_{ij} u^i_su^j_s\mathrm dt\\
=&\int_{t_1}^{t_2}\sum_{i,j=1}^n \left(\sum_{k=1}^n\partial_kg_{ij}\delta u^k\right) u^i_su^j_s+g_{ij}(u_s^j\delta u_s^i+u_s^i\delta u_s^j)\mathrm dt\\
=&\int_{t_1}^{t_2}\sum_{i,j=1}^n \left(\sum_{k=1}^n\partial_kg_{ij}\delta u^k\right) u^i_su^j_s\mathrm dt+\int_{t_1}^{t_2}g_{ij}(u_s^j\mathrm d\delta u^i+u_s^i\mathrm d\delta u^j)\\

=&\sum_{i,j,k=1}^n\int_{t_1}^{t_2}g_{ij,k}u_s^iu_s^j\delta u^k\mathrm dt-2\sum_{i,j,k=1}^n\int_{t_1}^{t_2}g_{ij,k}u_s^ku_s^i\delta u^j\mathrm dt\\
&-2\sum_{i,j=1}^n\int_{t_1}^{t_2}g_{ij}u_{ss}^i\delta u^j\mathrm dt\\
=&\sum_{k=1}^n\int_{t_1}^{t_2}\sum_{i=1}^n\left(-2u_{ss}^i g_{ik}+\sum_{j=1}^n(g_{ij,k}-g_{jk,i}-g_{ki,j})u_s^iu_s^j\right)\delta u^k\mathrm dt\\

\end{align*}
$$
两侧左乘$(g^{ij})_{n\times n}$, 从而对任意$k$都有
$$
u_{ss}^k+\sum_{i,j=1}^n\Gamma_{ij}^ku^i_su^j_s=0.
$$
从物理意义考虑, 以下为测地线的等价定义:

1. 若轨线$\gamma(t)$的二阶导数垂直于$\vec n$, 即弧长参数曲线$\gamma(s)$的加速度平行于$N$.
2. 测地曲率为$0$, 即$\nabla_{\gamma'}\gamma'=0$, 即切向量$\vec t$在$\gamma$上平行移动. 
3. $u_{ss}^k+\sum_{i,j=1}^n\Gamma_{ij}^ku^i_su^j_s=0$. 

根据常微分方程解的存在唯一定义, 测地线由起点与初速度唯一确定. 换言之, 同向相切的两条测地线必然相等. 

### Torus上的测地方程

考虑Torus的参数表示
$$
X(u,v)=((c+a\cos v)\cos u,(c+a\cos v)\sin u,a\sin v).
$$
从而度量$g=\mathrm{diag}((c+a\cos v)^2,a^2)$. 考虑测地线($\gamma(s)$), 从而
$$
\begin{align*}
u_{ss}^1 g_{11}+u_{ss}^2g_{21}=\sum_{i,j=1}^2\dfrac{g_{ij,1}-g_{j1,i}-g_{1i,j}}{2}u_s^iu_s^j\\
u_{ss}^1 g_{12}+u_{ss}^2g_{22}=\sum_{i,j=1}^2\dfrac{g_{ij,2}-g_{j2,i}-g_{2i,j}}{2}u_s^iu_s^j
\end{align*}
$$
即
$$
\begin{align*}
&u_{ss}=\dfrac{2a\sin v}{c+a\cos v}u_sv_s\\
&v_{ss}=-\dfrac{\sin v(c+a\cos v)}{a}u_s^2
\end{align*}
$$
从而
$$
[\dfrac{av_{ss}}{\sin v(c+a\cos v)}]_s=-2u_su_{ss}=\dfrac{-4a\sin v}{c+a\cos v}u_s^2v_s=v_sv_{ss}\dfrac{4a^2}{(c+a\cos v)^2}
$$
解得$v_s^2=\dfrac{-A^2}{a^2(c+a\cos v)^2}+B$, $u_s=\dfrac{A}{(c+a\cos v)^2}$. 令$\eta=\dfrac{A}{\sqrt B\sqrt E}$, 则
$$
\dfrac{\mathrm du}{\mathrm dv}=\pm\dfrac{\sqrt G}{ \sqrt E}\dfrac{\eta}{\sqrt {1-\eta^2}}.
$$
测地线存在时, 有
$$
u(v)-u(v_0)=\pm\int_{v_0}^{v}\dfrac{A/\sqrt B}{(c+a\cos v)\sqrt{(c+a\cos v)^2-A^2/B}}.
$$
其中$\eta$为$X_v$到$\gamma'$的角度的余弦, $\eta\cdot\sqrt E$为定值. 从而:

1. $\eta\cdot \sqrt E=0$时, 测地线为经圆.

2. $\eta\cdot \sqrt E\in(0,c-a)$时, 测地线能延伸至无穷(包含闭合情形). 若且仅若
   $$
   \dfrac{1}{2\pi}\int_{-\pi}^{\pi}\dfrac{A/\sqrt B}{(c+a\cos v)\sqrt{(c+a\cos v)^2-A^2/B}}\in\mathbb Q.
   $$
   时闭合. 

3. $\eta\cdot \sqrt E=c-a$时, 若测地线经过$v=\pi$, 则其只能为$v=\pi$. 若经过其他点, 则$v$至多含于一个$2\pi$周期. 不妨设$v_0\in(-\pi,\pi)$, 则$v\to \pi^-$或$v\to -\pi^+$时测地线逼近圈$v=\pi$.

4. $\eta\cdot \sqrt E\in(c-a,c+a)$时, 测地线族被限定于区域
   $$
   \left(\arccos(\dfrac{-A/\sqrt B-c}{a}),\arccos(\dfrac{A/\sqrt B-c}{a})\right)
   $$
   内. 注意到$v=\pm\arccos(\dfrac{-A/\sqrt B-c}{a})$时$\dfrac{\mathrm d v}{\mathrm du}=0$, $\dfrac{\mathrm d^2v}{\mathrm du^2}\neq 0$, 故测地线与两圆$v=\pm\arccos(\dfrac{-A/\sqrt B-c}{a})$​相切. 测地线可无限延伸(包含闭合情形). 测地线闭合若且仅若
   $$
   \dfrac{1}{2\pi}\int_{-\arccos(\frac{-A/\sqrt B-c}{a})}^{\arccos(\frac{-A/\sqrt B-c}{a})}\dfrac{A/\sqrt B}{(c+a\cos v)\sqrt{(c+a\cos v)^2-A^2/B}}\in\mathbb Q.
   $$

5. $\eta\cdot E=c+a$时, 仅有解$v=0$.

