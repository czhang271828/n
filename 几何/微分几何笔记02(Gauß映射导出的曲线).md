# Gauß映射导出的曲线

### 决定曲线的方式

大多数情形下, 确定曲线(面)的方式为微分方程解的存在性与唯一性定理. 此处从略. 

##### 由曲率$\kappa (s)$决定的平面曲线

记$\theta(s)$为法方向旋转角, 则$\theta(s)=\int\kappa(s)\mathrm ds+\varphi$. 自然
$$
\gamma(s)=(\int\cos\theta(s)+a,\int\sin\theta(s)+ b)
$$
为一切符合要求之曲线. 

##### 由$b(s)$决定的空间曲线

对非零挠率曲线, $b(s)$决定了曲率与挠率的绝对值. 因为
$$
\begin{align*}
b'=&\tau n\\
b''=&\tau'n-\tau(\kappa t+ \tau b)
\end{align*}
$$
从而$|\tau| =|b'|$, $\kappa=\sqrt{\dfrac{|b'\times b''|^2-|b'|^6}{|b'|^4}}$. 

##### 由$n(s)$决定的空间曲线

对非零挠率曲线, 法向量及$\dfrac{\kappa}{\tau}$​初值决定了曲率与挠率的. 因为
$$
\begin{align*}
n'&=-\kappa t-\tau b\\
n''&=-\kappa't-\kappa^2 n-\tau' b-\tau^2 n
\end{align*}
$$
从而$|n'|^2=\kappa^2+\tau^2$, 且
$$
[n,n',n'']=[n,t,b](-\kappa\tau'+\tau\kappa')=\arctan(\dfrac{\kappa}{\tau})'\cdot(\kappa^2+\tau^2).
$$
因此$\dfrac{\kappa}{\tau}$在初值已知之情形下有解. 因此$\kappa$与$\tau$可确定. 

注: 在$\dfrac{\kappa}{\tau}$未知之情形下, 解或不唯一. 如螺旋线族
$$
\{(a\cos\theta,a\sin\theta,b\theta):a,b>0,a^2+b^2=1\}
$$
在$\theta=\theta_0$处法向量一致, 但挠率并非一致. 

##### Berstrand侣线

对有正则参数的曲线$\alpha(t)$, 记活动标架为$\{t,n,b\}$. 若存在$\beta(t)$使得$\beta(t)-\alpha(t)$与$n$始终平行, 证明对任意$t$, $\alpha$与$\beta$的挠率之积为常数, 并计算.

证明: 不妨以弧长参数记$\alpha=\alpha(s)$. 记$\beta(s)-\alpha(s)=\gamma(s)n(s)$, 则
$$
\beta'(s)-t=\gamma'n+\gamma n'.
$$
因此$n$​系数为$0$​, 即$\gamma$​为常数. 记$\beta(s)$​与$\alpha(s)$​夹角为$\theta$​, 则
$$
(\cos\theta)'=(T_\beta\cdot t)'=N_\beta \cdot t+T_\beta\cdot kn=0.
$$
从而$\theta$为定值. 注意到$\beta'(s)=t-\gamma(kt+\tau b)$, 则
$$
\cos\theta=\dfrac{\beta'(s)\cdot t}{|\beta'(s)|}=\dfrac{1-\gamma k}{\sqrt{(1-\gamma k)^2+(\gamma\tau)^2}}.
$$
不失一般性地, 记$T_\beta =t\cos\theta+b\sin\theta$​. 则
$$
B_\beta=T_\beta\times N_\beta=T_\beta\times n=b\cos\theta-t\sin\theta.
$$
从而$\tau_\beta$为$B_\beta'$中$-n$的系数, 即$k\sin\theta-\tau\cos\theta$​. 注意到$\cot\theta=\dfrac{1-\gamma k}{\gamma\tau}$, 消$k$得
$$
\tau_\alpha\tau_\beta=k\tau\sin\theta-\tau\cos\theta=\dfrac{\sin^2\theta}{\gamma^2}.
$$
注: 

1. $\alpha$具有Berstrand侣线当且仅当$\theta$为定值, 即存在$(A,B)$使得$A\kappa+B\tau\equiv1$. 
2. 若$\alpha$有两条Berstrand侣线, 则其有无穷条Berstrand侣线, 当且仅当$\alpha$为圆柱面. 

##### Jacobi的球面平分定理

定理叙述如下: 令$\gamma$可微性足够的挠率不为$0$的闭合曲线, 则$\gamma$的法向量$n$在单位球面上的轨迹将球面平分为面积相等的两部分(交叉区域需定向).

记$\gamma(s)$与$n(S)$均为弧长参数曲线, 其中$n(s)$即$n(S(s))$. 根据Gauß-Bonnet定理, $n(s)$围成面积$D$​满足
$$
\mathrm{Area(D)}=\int_DK\mathrm d\sigma=2\pi-\oint_{n}\kappa_g(s)\mathrm ds.
$$
其中$n(S)$的测地曲率满足
$$
\begin{align*}
\kappa_g(S)=&[n'',N(S),n']\\
=&[-\kappa't-\tau'b,n,-\kappa t-\tau b]\cdot \left(\dfrac{\mathrm ds}{\mathrm dS}\right)^3\\
=&(\tau\kappa'-\tau'\kappa)\cdot \dfrac{1}{\tau^2+\kappa^2}\cdot\dfrac{\mathrm ds}{\mathrm dS}\\
=&\left[\arctan\dfrac{\kappa}{\tau}\right]'\cdot\dfrac{\mathrm ds}{\mathrm dS}
\end{align*}
$$
从而$\mathrm{Area(D)}=2\pi$. 
