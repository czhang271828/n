# 从Riemann曲面到Poincaré引理

### 前言

由于笔者将在下学期修读微分几何(differential geometry), 故最近在阅览相关书籍. 本文承接单复变函数课程, 以介绍Riemann曲面为主, 最终证明Poincaré引理(并非某猜想). 

### Riemann曲面: 一类特殊的微分流形

#### 微分流形之引入

研究曲面总是复杂的工作.  例如许多人不知道, 北京到纽约的最近航线是经由北极的, 即便在地图上看来很不直观; 但宁波栎社到上海虹桥的航线(确实有过)大致是一条合乎直觉的小线段, 因为华东地区可近似看作一块平地($\mathbb R^2$中区域), $\mathbb R^2$上的Euclidean度量还是比较直观的. 试想, 能否借用若干组映射, 使得其将复杂曲面的局部"较好地"映射到相对简单的$\mathbb R^n$上? 同时, 度量函数也就可一并转移了.

对所研究的空间$M$(例如球面$S^2$), 我们必须规定其是Hausdorff的(T2). 唯有空间可分, 才能定义度量于其上; 或等价地, $M$有可数个拓扑基. 若$\forall x\in M$, 存在$x$的邻域$U_x$使得$U_x$同胚于$\mathbb R^m$中某一开集, 则称$M$为$m$维流形.

这里的同胚映射指$\varphi_x:U_x\to \varphi_x(U_x)$, 其中同胚要求$\varphi_x$, $\varphi_x^{-1}$均为连续双射. 称$(U_x,\varphi_x)$为一个坐标卡, 因此, 流形可用一组由至多可数的坐标卡所组成的图册来描述. 应当注意, $\varphi_x$之连续性业已道明$U_x$为开集, 从而极可能存在不同坐标卡之交集, 即存在非空开集$U_{x,y}:=U_x\cap U_y$. 是故$\varphi_x$与$\varphi_y$应当在某些方面保持兼容, 该兼容方式于Riemann曲面上之展现可参见以下定义.

#### Riemann曲面之定义

Riemann曲面定义如是: 对满足Hausdorff性之拓扑空间$\Sigma$, 若存在$\Sigma$之开覆盖$\{U_\alpha\}_{\alpha\in\Gamma}$以及相应的同胚映射$\varphi_\alpha:U_\alpha\to\varphi_\alpha(U_\alpha)\subset \mathbb C$, 同时

* 若$U_{\alpha,\beta}:=U_\alpha\cap U_\beta\neq\emptyset$, 则$\varphi_\alpha\circ \varphi_\beta^{-1}:\varphi_\beta(U_{\alpha,\beta})\to \varphi_\alpha(U_{\alpha,\beta})$为$\mathbb C$内的全纯映射.

则$\Sigma$为Riemann曲面.

Riemann曲面之案例不胜枚举, 如$\mathbb C$中一切区域均为Riemann曲面. 下证明$S^2$亦为Riemann曲面. 这里采用直角坐标表示$S^2$, 其中
$$
S^2:=\{(x,y,z)\in\mathbb R^3:x^2+y^2+z^2=1\}.
$$
整个$S^2$自然无法与$\mathbb C$同胚, 毕竟挖去一点的$S^2$与$\mathbb C$同胚, 而挖去一点的$\mathbb C$确不再是单连通的; 但可以由此选取$U_1=S^2-\{(0,0,-1)\}$, $U_2=\{(0,0,1)\}$. 令
$$
\begin{align*}
\varphi_1: U_1\to \mathbb C,&(x,y,z)\mapsto \dfrac{x-iy}{1+ z},\\
\varphi_2: U_2\to \mathbb C,&(x,y,z)\mapsto \dfrac{x+iy}{1- z}.\\
\end{align*}
$$
则$\varphi_2\circ\varphi_1^{-1}:\mathbb C^*\to\mathbb C^*,\zeta\mapsto\dfrac{1}{\zeta}$为区域$\mathbb C^*$上的全纯映射.

$\mathbb C$中的全纯映射容易理解, 但Rieamnn曲面间的全纯映射何以判别? 细端详下交换图表

![](https://files.mdnice.com/user/12571/b9f94b71-11cb-46cc-b335-5eb3ab0275de.png)

若对一切满足$U_2\cap f(U_1)\neq\empty$之坐标卡, $(\varphi_2\circ f\circ\varphi_1^{-1})|_{\varphi_1(U_1)}$均为$\mathbb C$中的全纯映射, 则$f$为$\Sigma_1$至$\Sigma_2$间之全纯映射. 

若存在全纯映射$f:\Sigma_1\to \Sigma_2$, $g:\Sigma_2\to \Sigma_1$使得$f\circ g=\mathscr I_{\Sigma_2}$与$g\circ f=\mathscr I_{\Sigma_1}$成立, 则$M$与$N$全纯同构. 例如, $\mathbb CP^1$表示$\mathbb C$中所有方向, 则其与$S^1$同构. 下给出Riemann环面(torus)间的同构关系.

#### Riemann环面之分类

对$\mathbb C$中的秩为$2$的$\mathbb R$线性无关量$w_1,w_2$, 考虑具有双周期的点列
$$
\Lambda:=\left< w_1,w_2\right>:=\{mw_1+nw_2:m,n\in\mathbb Z\}
$$
则商空间
$$
\pi:\mathbb C\to\mathbb C/\Lambda,\zeta\mapsto \zeta+\Lambda=:[\zeta]
$$
同胚于$S^1\times S^1$(逆命题暂未论证), 即某一形似游泳圈的图形. 通过仿射变换可知$\mathbb C/\left< w_1,w_2\right>$, $\mathbb C/\left< 1,w_2/w_1\right>$, $\mathbb C/\left< w_1/w_2,1\right>$三者全纯同构. 为对Riemann环面进行分类, 下仅需考虑$\mathbb C/\left< 1,\tau_1\right>$与$\mathbb C/\left< 1,\tau_2\right>$同构之情形. 

全纯同构$f:\mathbb C/\left< 1,\tau_1\right>\to \mathbb C/\left< 1,\tau_2\right>$有一般形式$f([\zeta]_1)=[C\zeta ]_2$, $\forall \zeta\in\mathbb C$. 特别地,
$$
[C]_2=f([1]_1)=[0]_2=f([\tau_1]_1)=[C\tau_1]_2
$$
从而存在系数矩阵$P$使得$P(1,\tau_2)=(C,C\tau_1)=C(1,\tau_1)$. 同理, 考虑$f^{-1}$知存在整系数矩阵$Q$使得$Q(1,\tau_1)=(1,\tau_2)/c$. 相乘得$PQ(1,\tau_1)=(1,\tau_1)$. 由于$1,\tau_1$线性无关, 故$|\det P|=|\det Q|=1$. 

由$Q(1,\tau_1)=(1,\tau_2)/c$知存在$a,b,c,d\in\mathbb Z$使得$\tau_2=\dfrac{a+b\tau_1}{c+d\tau_1}$. 同时$ad-bc\in\{\pm 1\}$. 计算得$\Im(\tau_2)=(ad-bc)|c+d\tau_1|^{-2}\Im(\tau_1)$. 这里可利用模形式中"$\Im$权为$2$"的结论. 据假设, $\Im(\tau_1),\Im(\tau_2)>0$, 从而$ad-bc=1$, 或曰, $\begin{pmatrix}a&b\\c&d\end{pmatrix}\in SL(2,\mathbb Z)$. 

由于$\tau$可取遍$\mathbb H$, 是故有推论: 上半平面$\mathbb H$之全纯自同构有一般形式$\zeta\mapsto \dfrac{a+b\zeta }{c+d\zeta }$, 其中$\begin{pmatrix}a&b\\c&d\end{pmatrix}\in SL(2,\mathbb Z)$. 

#### 切空间与余切空间

考虑(光滑)流形中一点$x\in M$, 定义$C^\infty(p)$为$M$上$p$邻域内光滑函数全体的商空间(或称函数芽, 英文为germ), $f\sim g$若且仅若$f$与$g$在某一更小邻域内相同(为便于理解故, 读者可姑妄认同$f\sim g\Leftrightarrow \nabla(f-g)|_{x=p}=0$). 定义切向量$V_p$为线性算子$V_p:C^\infty(p)\to\mathbb R$, 满足
$$
V_p(fg)=f(p)V_p(g)+V_p(f)g(p).
$$
定义切空间$T_pM$为流形$M$上$p$处全体切向量生成之线性空间(基域$\mathbb R$). 而依直觉有 
$$
T_pM=\mathrm{span}(\partial _{x_1}|_p,\partial_{x_2}|_p,\ldots,\partial _{x_m}|_p), \quad m=\dim M.
$$
下以步骤验证之:

1. $\partial_{x_i}|_px_j=\delta_i^j$. 从而诸$\partial _{x_i}$线性独立.

2. 对一切满足$\partial_{x_i}|_p(f)\equiv0(\forall i)$之函数$f$, $V_p(f)\equiv 0$. 实际上, 不妨设$(U_p,\varphi_p)$为覆盖$p$某一邻域的坐标卡, $\varphi_p$光滑. 任取$x\in(\varphi_p(U_p))^*$, 有
   $$
   \begin{align*}
   f\circ\varphi_p^{-1}(x)-f\circ\varphi_p^{-1}(0)=&\int_0^1\dfrac{\mathrm d}{\mathrm dt}(f\circ\varphi_p^{-1}(tx))\mathrm dt\\
   =&\int_0^1\sum_{k=1}^mx_k\partial_{x_k}(f\circ\varphi_p^{-1}(tx))\mathrm dt\\
   =&\sum_{k=1}^mx_kh_k\\
   \end{align*}.
   $$
   此处$h_k$为$U_p$内的某光滑函数. 将$\partial _{x_k}|_p$作用于左式知$h_k(p)\equiv 0$. 从而$p$处任意切向量作用于$f$上亦为$0$.

3. 对一般切向量$V_p$, 考虑$V_p-\sum_{k=1}^mV_p(x_k)\partial _{x_k}|_p$即可. 

实际上, 我们于上式第三步考察$\partial_{x_k}|_p$之分量时, 自然希望存在某一泛函$L_k$使得$L_k(V_p)=V_p(x_k)$. 此处记$L_k$为$\mathrm dx_k|_p$, 可见$\{\mathrm d x_k|_p\}$构成切空间对偶空间之基底, 称之余切空间($T^*_pM$).

记$\phi:M\to N$为光滑流形间的光滑映射, 定义$\phi$在$p$处切映射之微分为
$$
\phi_{*p}:T_pM\to T_{f(p)}N,V_p\mapsto\phi_{*p}(V_p).
$$
其中, $\forall g\in C^\infty(f(p))$, $\phi_{*p}(V_p)(g)=V_p(g\circ \phi)$. 容易验证链式法则: 

对光滑映射链$M_0\overset {\phi_1}\to M_1\overset {\phi_2}\to \cdots\overset {\phi_k}\to M_k$, 有
$$
(\phi_k\circ\cdots\phi_2\circ \phi_1)_{*p_0}=\phi_{k,*p_k}\circ\cdots\circ\phi_{2,*p_2}\circ\phi_{1,*p_1}.
$$
其中$M_0\ni p_0\overset {\phi_1}\to p_1\overset {\phi_2}\to \cdots\overset {\phi_k}\to p_k$.

对Riemann曲面而言, 记$z=x+iy$在$p$的某邻域内, 记$w=f(z)=x'+iy'$, $f=u+iv$. 则
$$
\phi_{*p}\begin{pmatrix}\partial_x|_p\\\partial_y|_p\end{pmatrix}=\begin{pmatrix}u_x&v_x\\u_y&v_y\end{pmatrix}\begin{pmatrix}\partial_{x'}|_{f(p)}\\\partial_{y'}|_{f(p)}\end{pmatrix}
$$

其中, 当$f$为全纯映射时, 转换矩阵行列式值为$u_xv_y-u_yv_x=\nabla^2 u=0$. 从而$\phi_{*p}$或为$0$, 或线性同构.

#### de Rham上同调群引入

本节所讲并非系统化的de Rham上同调群, 仅为Poincaré引理证明用, 徒代数拓扑学之一隅尔.

前文所提及的切空间$T_pM$与余切空间$T_p^* M$均为局部定义. 对于光滑流形者, 可定义切丛$TM:=\cup_{p\in M}T_pM$为$M$上一切其空间之并集, 余切丛$T^*M:=\cup_{p\in M}T^*_pM$为$M$上一切余切空间之并集. 

记$f:U\to \mathbb R$为定义于$U\subset M$上的光滑函数. 则对任意$p\in U$, $\mathrm df(p)\in T_p^*M$存在. 定义余切丛后, 方可议论有一次微分形式$\mathrm df$. 其中$(\mathrm df)(p)=\mathrm d(f(p))$. 对任意的$f\in V_p$, 总有$\mathrm df(p)(V_p)=V_p(f)$. 此处$\mathrm df$亦可视作$f$之外微分.

而后可推广有多次微分形式. 由于Riemann曲面上的三次及以上微分形式均为$0$(因为$\dim_{\mathbb R}\mathbb C=2$), 下仅给出二次微分形式之介绍.
$$
\wedge^2T^*_pM:=\{\psi:T_pM\times T_pM\to\mathbb R:\psi\text{反对称且偏线性}\}
$$
即可. 其中$(\omega_p\wedge\eta_p)(V_p,W_p)=\omega_p(V_p)\eta_p(W_p)-\omega_p(W_p)\eta_p(V_p)$. 外积(wedge)运算也可定义在一次微分形式上, 如$(\omega_1+\omega_2)\wedge\eta=\omega_1\wedge\eta+\omega_2\wedge\eta$, $\omega\wedge\eta=-\eta\wedge\omega$ .

设$f:M\to N$为Riemann曲面间的光滑映射, 定义拉回映射$f^*:N\to M$使得

* $f^*$将$N$中的$k$形式转为$M$中$k$形式.
* $f ^*$作用在$0$形式上无非复合, 如$f^*g=g\circ f$. 
* $f^*$作用在$k$形式$\omega$上为$f^*\omega_p(V_p^{(1)},\ldots,V_p^{(k)})=\omega_{f(p)}(f_{*p}V_p^{(1)},\ldots,f_{*p}V_p^{(k)})$.
* $f^*(\omega\wedge \eta)=f^*(\omega)\wedge f^*(\eta)$.
* $\mathrm d(f^*(\omega))=f^*(\mathrm d\omega)$.

由外微分运算可知$\mathrm d^2=0$. 称$\omega$为闭形式若且仅若$\mathrm d\omega =0$, 称$\omega$为恰当形式若且仅若存在$\eta$使得$\omega=\mathrm d\eta$. 容易见得对任意$k$, $k$次闭形式为向量空间, $k$次恰当形式亦然. 从而定义de Rham上同调群为商空间
$$
H_{\mathrm {dR}}^q=\{\text{$q$次闭形式}\}/\{\text{$q$次恰当形式}\}.
$$
从而$f^*$在商空间下诱导的映射$\tilde{f^*}\in\hom(H_{\mathrm {dR}}^q,H_{\mathrm {dR}}^q)$. 

Poincaré引理如是说: $\mathbb C$上的闭形式必为恰当形式.

1. $\omega$为$2$形式时, 不妨设$\omega=F(x,y)\mathrm dx\wedge\mathrm dy$. 注意到
   $$
   \mathrm d\left[\left(\int_0^x F(t,y)\mathrm dt\right)\mathrm dy\right]=\omega.
   $$

2. $\omega$为$1$形式时, 不妨设$\omega=P(x,y)\mathrm d x+Q(x,y)\mathrm dy$. 由于$\mathrm d\omega=0$, 故
   $$
   \dfrac{\partial P}{\partial y}=\dfrac{\partial Q}{\partial x}.
   $$
   考虑$\eta=\int_0^xP(t,y)\mathrm dt+\int_0^yQ(x,t)\mathrm dt$即可得$\mathrm d\eta=\omega$.

另一个有趣的结论是$H_{\mathrm{dR}}^1(\mathbb C^*)=\mathbb R$, 或同理地, $H_{\mathrm{dR}}^1(\mathbb D^*)=\mathbb R$. 证明如下:

对任意$[\omega]\in H_{\mathrm{dR}}^1(\mathbb C^*)$, 由于恰当形式在环路积分下为$0$, 故有良定义的映射
$$
\phi:H_{\mathrm{dR}}^1(\mathbb C^*)\to\mathbb R,[\omega]\mapsto\int_{S^1}\omega.
$$
注意到$\int_{S^1}\mathrm d\theta=2\pi\neq 0$, 从而$\phi$为满射. 此处$\theta$在$\mathbb C^*$上未能够整体定义, 但$\mathrm d\theta=\dfrac{x\mathrm dy-y\mathrm dx}{x^2+y^2}$确乎为闭形式. 下证明$\phi$为单射.

直觉告诉我们$H_{\mathrm{dR}}^1(\mathbb C^*)\cong\{c[\mathrm d\theta]:c\in\mathbb R\}\cong\mathbb R$, 因此我们只需尝试将一切含$\mathrm dr$之项化作恰当形式即可. 不妨设闭形式$\omega=f\mathrm dr+g\mathrm d\theta$. 据闭形式之定义, $\dfrac{\partial f}{\partial \theta}=\dfrac{\partial g}{\partial r}$. 故
$$
\omega=\mathrm d\int_1^r f(t,\theta)\mathrm dt-\left(\int_1^r\dfrac{\partial f(t,\theta)}{\partial\theta}\mathrm dt\right)\mathrm d\theta=\mathrm d\int_1^r f(t,\theta)\mathrm dt+g(1,\theta)\mathrm d\theta.
$$
从而由$\int_{S^1}\omega=0$可推得$\int_0^{2\pi}g(1,\theta)\mathrm d\theta=0$. 从而
$$
\omega=\mathrm d\left(\int_1^rf(t,\theta)\mathrm dt+\int_0^\theta g(1,s)\mathrm ds\right)
$$
为恰当形式. 最后, 结论$H_{\mathrm{dR}}^1(\mathbb C^*)=H_{\mathrm{dR}}^1(\mathbb C^*)=0$是显然的.
