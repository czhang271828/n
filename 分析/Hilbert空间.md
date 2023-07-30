# Hilbert空间

注: 文中统一使用$(\cdot,\cdot)$表示内积, $^*$表示共轭转置(对单变元则为退化为共轭运算).

> 本片笔记整理Hilbert空间的部分内容, 不乏若干值得深入探讨之内容:
>
> * 赋范空间上加以平行四边形法则, 能否导出内积空间?
> * 如何定义Hilbert空间上的线性无关? 换言之, 线性无关组中元素是否不可删减?
> * 加权内积空间与Legendre多项式, Чебышёв多项式之联系
> * Hilbert空间上的有界(无穷)序列是否包含聚点/收敛子列? 若不然, 则如何给出新的收敛定义?

目录如下:

1. 相关定义及性质
   1. Hilbert空间
   2. 内积恒等式与不等式
      1. 平行四边形法则: 赋范空间$\longrightarrow$内积空间
   3. 凸集
2. 线性空间
   1. 线性算子
      1. 常见算子举隅
      2. $H\cong H^*$
   2. 标准正交基
   3. 线性无关与秩
      1. 极大线性无关组
      2. 正交基维度
      3. 反直觉的例子
   4. 正交化
   5. 加权正交基
3. 弱收敛性

[TOC]

## 相关定义及性质

### Hilbert空间

Hilbert空间$H$指完备内积空间, 即实或复的内积空间且其导出的度量空间是完备.

定义Hilbert空间之内积$(\cdot, \cdot):H\times H\to\mathbb C$, 使得其满足

* 半双线性(Sesquilinear), 即
  $$
  (a+xb,c+yd)=(a,c)+x(b,c)+y^*(c,d)+x y^*(b,d)
  $$

* 共轭对称, 即$(x,y)^*=(y,x)$.
* 范数$\|\cdot\|:H\to\mathbb C,x\mapsto \|x\|=\sqrt{(x,x)}$. $\|x\|=0$若且仅若$x=0$.

注: 半双线性(Sesquilinear)一词中, 拉丁文前缀Sesqui之本意为"一个半". 此处应理解为: 内积对首一索引线性, 对次者共轭线性.

### 内积恒等式与不等式

(Hölder) $\|fg\|_r\leq\|f\|_p\|g\|_q$, 其中$\dfrac{1}{r}=\dfrac1p+\dfrac1q$. 取$p=q=2$, $|(x,y)|\leq\|x\|\|y\|$.

(Minkovski) $\|f+g\|_p\geq\|f\|_p+\|g\|_p$, $p\in[1,\infty]$. 取$p=2$即可.

(Hanner) 设$p\geq1$, $\|f+g\|^p_p+\|f-g\|^p_p\overset?\to(\|f\|_p+\|g\|_p)^p+|\|f\|_p-\|g\|_p|^p$.

* $p\geq 2$取$\leq$, $p\leq 2$取$\geq$.
* $p=2$时$\|f+g\|^2_2+\|f-g\|^2_2=(\|f\|_2+\|g\|_2)^2+|\|f\|_2-\|g\|_2|^2$

(Hanner) 设$p\geq1$, $2^p(\|f\|_p^p+\|g\|_p^p)\overset?\to(\|f+g\|_p+\|f-g\|_p)^p+|\|f+g\|_p-\|f-g\|_p|^p$.

* $p\geq 2$取$\leq$, $p\leq 2$取$\geq$.
* $p=2$时$\|f+g\|^2_2+\|f-g\|^2_2=(\|f\|_2+\|g\|_2)^2+|\|f\|_2-\|g\|_2|^2$

据此有内积平行四边形法则
$$
\|x+y\|^2+\|x-y\|^2=2(\|x\|^2+\|y\|^2)
$$
极化恒等式
$$
(x,y)=\dfrac{1}{4}(\|x+y\|^2-\|x-y\|^2+i\|x+iy\|^2-i\|x-iy\|^2)
$$

#### 平行四边形法则: 赋范空间$\to$内积空间

赋范空间中的平行四边形法则能导出内积空间及范数: 这点极其不显然.

证明: 若平行四边形法则$\|x+y\|^2+\|x-y\|^2=2(\|x\|^2+\|y\|^2)$对一切$(X,\|\cdot\|)$中$x$与$y$成立, 则对选定的$x$与$y$形式定义$\Re (x,y)$与$\Im(x,y)$, 如
$$
\begin{align*}
2\Re(x,y)&=\|x+y\|^2-\|x\|^2-\|y\|^2\\
-2\Re(x,y)&=\|x-y\|^2-\|x\|^2-\|y\|^2\\
\end{align*}
$$
从而
$$
\begin{align*}
4\Re(x,y)&=\|x+y\|^2-\|x-y\|^2\\
4\Im(x,y)&=\|x+iy\|^2-\|x-iy\|^2\\
\end{align*}
$$
故$(x,y)=\dfrac{1}{4}\sum_{k=0,1,2,3}i^k\|x+i^ky\|$, 从而可验证$(x,x)=\|x\|^2$与$(x,y)=(y,x)^*$

对任意$x,y,z\in X$, 由平行四边形法则导出恒等式
$$
\|x+y+z\|^2=\|y+z\|^2+\|x+y\|^2-\|x-z\|^2+\|x\|^2+\|z\|^2-\|y\|^2
$$
从而有线性加法
$$
\begin{align*}
4\Re(x+z,y)&=\|x+z+y\|^2-\|x+z-y\|^2\\
&=\cdots\\
&=4\Re(x,y)+4\Re(z,y)
\end{align*}
$$
由$(x,y)=\dfrac{1}{4}\sum_{k=1,2,3,4}i^k\|x+i^ky\|$知$(i^kx,y)=i^k(x,y)$, 由线性加法知$(nx,y)=n(x,y)$对$n\in\mathbb Z$成立, 从而$((n+im)x,y)=(n+im)(x,y)$对$m,n\in\mathbb Z$成立. 再由$\dfrac{1}{(n+im)}((n+im)x,y)=(x,y)$知$(rx,y)=r(x,y)$, $r\in\mathbb Q[i]$. 

由于平行四边形法则内蕴连续性, $(\lambda x,y)=\lambda(x,y)$对任意$\lambda\in\mathbb C$成立. 结合$(x,y)=(y,x)^*$, 因此半双线性性自然成立.

### 凸集

凸组合: 设$\{f_i\}_{i\in I}\subset H$, 若$\{c_i\}_{i\in I}$满足$\sum_{i\in I}=1$, $c_i\in(0,1)$, 则称$\sum_{i\in I}c_if_i$为$\{f_i\}_{i\in I}$之凸组合. 显然$I$至多可数.

凸集: 若$\mathcal C$中任意元素之凸组合仍在原集合内, 则$\mathcal C$凸.

Prop. (变分引理) 点$x$到完备凸集$M$距离的等价定义: 存在唯一的$y\in M$使得
$$
d(x,M)=\|x-y\|=\inf_{z\in M}\|x-z\|
$$
证明: 不妨设$x=0$. 记$\delta= d(x,M)$, 存在$\{y_k\}_{k\geq 1}$使得$\|y_k\|:=\delta_k\to\delta$. 据平行四边形法则有$\delta_m^2+\delta_n^2\geq \delta^2+\|y_m-y_n\|^2$. 从而$\{y_k\}$为Cauchy列. 由$M$闭知存在极限$y_k\to y_0$. 因此$\|y_0\|=d(x,M)=\delta$. 再由平行四边形法知其唯一性.

Prop. (凸集分离定理) 设Hilbert空间上的紧凸集$K$与闭凸集$C$不相交, 则存在分离它们的超平面(证明见一般凸分析教程, 此处从略).

***

## 线性空间

### 线性算子

#### 常见算子举隅

(共轭) 设有界线性算子$A:H\to H$, 则存在唯一的共轭$A^*:H\to H$且$(x,Ay)=(A^*x,y)$. 称$A$为自伴随的若且仅若$A=A^*$. 

(幺正) $U:H\to K$为线性双射, 且$\|x\|_H=\|Ux\|_K$恒成立. 幺正变换性质如下

* $UU^*=id_H$, $U^*U=id_K$, 即$U^{-1}=U^*$.
* $(Ux,Uy)_K=(x,y)_H$.

(投影) 设$M$为$H$之闭子空间, 则投影$P_M:H\to M$使得$(x-P_M(x))\perp M$.

* $P_M$为良定义的线性映射.
* (幂等) $P_M^2=P_M$.
* (共轭) $P_M=P_M^*$.
* $\ker P_M=M^\perp$.

由是可知, 对$H$的真闭子空间$M$, 都有分解$H=M\oplus M^\perp$.

(闭包) 设$A\subset H$, 则$A$之闭包为包含$A$之最小闭子空间, 即$(A^{\perp})^\perp$.

* 应当注意$A^\perp$闭, 因为$A^\perp$中的Cauchy列$\{x_n\}$对一切$y\in A$均有
  $$
  \lim_{n\to\infty} (x_n,y)=0
  $$

* 记$\mbox{span}(A)$为$A$生成之空间(故完备), 则$(\mbox{span}(A))^\perp=A^\perp$.

应当注意, 有限维Hilbert空间之子空间均完备; 无限维Hilbert空间之子空间未必完备, 其一反例为$[0,1]$上全体多项式.

#### $H\cong H^*$

(Riesz) $j:H\to H^*, z\mapsto (\cdot, z)$为共轭线性同构.

证明: $\|jz\|_{H^*}=\sup_{\|x\|=1}|(x,z)|=\|z\|$是自然的. 因此$\ker j=\{0\}$, 即$j$为单射. 下证明$j$为满射. 对任意非零的$f\in H^*$, $M:=\ker f$为$H$的闭子空间. 故$H=M\oplus M^\perp$. 而
$$
f: H/M\cong M^\perp\to\mathbb F
$$
为线性映射, 因此$\dim M^\perp=1$. 故存在$x_0\in M^\perp$使得$H\cong M\oplus x_0\mathbb F$. 取$\lambda_0\in\mathbb F$使得$f(x_0)=(x_0,\lambda_0 x_0)$(计算得$\lambda=\dfrac{f(x_0)}{\|x_0\|^2}$). 因此对任意$m\in M$与$\lambda\in\mathbb F$都有
$$
f(m+\lambda x_0)=(\lambda x_0,\lambda_0 x_0)=(m+\lambda x_0,\lambda_0 x_0)
$$
因此$j^{-1}(f)=\dfrac{f(x_0)x_0}{\|x_0\|^2}$. $j$为双射.

### 标准正交基

定义: $\{e_i\}$为$H$中标准正交基若且仅若$(e_i,e_j)=\delta_{ij}$. 且$\{e_i\}$在集合包含之偏序下极大.

由可分性易知每一非零的Hilbert空间均有标准正交基. 实际上, 由Zorn引理知标准正交基之存在性并非可分性所内蕴, 即不依照可分性之条件, 仍能推出标准正交基之存在性.

由于$H$可分, $H$有至多可数的标准正交基. 由正交分解知$H$同构于某一序列空间, 因此可建立$H$中元素与至多可数的指标对应. 特别地, $L^2(\Omega)\cong l^2(T)$为等距同构.

稠密性: $\{e_i\}$之有限线性组合在$H$中稠密. 下有等价叙述:

* $\forall i,(e_i,f)=0$则$f=0$.
* 记$a_i=(e_i,f)$, $S_N(f)=\sum_{i=1}^N a_ie_i$, 则$\|S_N(f)-f\|\to 0$.
* Parseval恒等式成立: $\|f\|^2=\sum_i|a_i|^2$.

Pythagorean定理. 对$H$中任意一组正交基$S$都有
$$
\|\sum_{x\in S}x\|^2\leq\sum_{x\in S}\|x\|^2
$$
注: $\|x+y\|^2=\|x\|^2+\|y\|^2+2\Re(x,y)$. 故$\mathbb R$上$\|x+y\|^2=\|x\|^2+\|y\|^2$等价于$x\perp y$, 而$\mathbb C$上非然, 例如$1$与$i$显然不正交.

取等若且仅若$S$中基底两两正交. 因此对任意$y\in H$都有Parseval恒等式
$$
\sum_{x\in S}|(x,y)|^2=\|y\|^2
$$
若$S$不能张成$H$, 则有Bessel不等式$\sum_{x\in \Gamma\subset S}|(x,y)|^2\leq\|y\|^2$.

若$H$中一组标准正交基的部分($\{u_i\}$)张成某一子空间$M$, 则$\forall x,y\in H$均有

* 正交分解: $P_M x=\sum_{i}(x,u_i)u_i$.
* Parseval恒等式: $\|P_Mx\|^2=\sum_i|(x,u_i)|^2$.
* Parseval恒等式: $(P_Mx,y)=(P_M^2x,y)=(P_Mx,P_My)=\sum_{i}(x,u_i)(u_i,y)$.

### 线性无关与秩

#### 极大线性无关组

称$\{x_i\}$线性相关若且仅若对有限个$\{x_{n_k}\}$, 存在$\mathbb F$中非恒零常数组$(c_k)$使得$\sum_i c_i x_i=0$. 特别地, 标准正交基$\{e_i\}$为特殊的线性无关组. 值得强调: 无穷维空间中不可通过$\sum_{i}a_ix_i=0\Leftrightarrow a_i\equiv 0$以定义线性无关. 实际上, 从无穷维空间中的线性无关组中移除若干者, 剩余者仍可能生成全空间(后文将给出例子).

由Zorn引理知任一Hilbert空间(或其子空间)有极大的线性无关组. 实际上, 有如下命题.

#### 正交基维度

Prop. 空间$M\subset H$之极大线性无关组有相同之序数(基数). 

证明: 由于$M$与$\mbox{span}(M)$之极大线性无关组可等同, 故不失一般性地设$M$完备. 由后文所提及的Gram-Schmidt正交化知子空间之极大线性无关组与对应的正交化基有相同的序数(基数). 因此只需证明$M$之任意标准正交基均有相应之序数(基数). 

不妨设$B_1$, $B_2$为任意两组标准正交基, 则当任一者有限时, 其序数等于$M$之维度. 因此$|B_1|=|B_2|=\dim_{\mathbb F}M$是显然的. 

若$|B_1|$与$|B_2|$无穷, 设$\mbox{span}_{\mathbb Q}(B_1)$为$B_1$于域$\mathbb Q$下的扩张, 因此$\mbox{span}_{\mathbb Q}(B_1)$于$\mbox{span}_{\mathbb R}(B_1)$中稠密. 若$M$为实Hilbert空间则$\mbox{span}_{\mathbb Q}(B_1)$于$M$中稠密, 若$M$为复Hilbert空间, 则$\mbox{span}_{\mathbb Q[i]}(B_1)$与$H$中稠密. 

因此存在$M$中的稠密集$X$使得$|X|=|B_1|$. 对任意$B_2$中元$y$, 取$x\in X$使得$\|x-y\|\leq\varepsilon_0$, 其中$\varepsilon_0$充分小(如可取$\varepsilon_0=\dfrac{\sqrt 2-1}{2}$). 对任意$y_1,y_2\in B_2$, 由Pythagorean定理知
$$
\sqrt2=\|y_1-y_2\|\leq\|y_1-x_1\|+\|x_1-x_2\|+\|y_2-x_2\|\leq2\varepsilon_0+\|x_1-x_2\|
$$
因此$\varepsilon_0$充分小时总有$x_1\neq x_2$, 即$y_i\mapsto x_i$为单射对应. 从而$|B_2|\leq|X|=|B_1|$. 同理可证$|B_1|\leq|B_2|$. 综上, $|B_1|=|B_2|$.

是故可由此定义Hilbert空间之正交维度, 即任一正交基之序数(基数). 两个Hilbert空间拥有相同之正交维度若且仅若其间存在双射(亦等价于存在幺正变换).

#### 反直觉的例子

承上, 可以利用$|\mathbb Z|=|n\mathbb Z|$之事实构造反直觉的例子: $H=L^2([-1,1])$之线性无关组为$\{x^n\}_{n\geq 0}$, 同时也可以为
$$
\{x^{(2k+1)n}\}_{n\geq 0}=\{1,x^{2k+1},x^{4k+2},\ldots\},\quad k\in\mathbb N
$$
(理工科群体内)众所周知, 有限维线性空间中任一极大线性无关组均无法在保证张成空间不变之情形下再删减元素; 而对无穷维的极大线性无关组或非然.

证明: 以$k=3$为例. (已知)$[-1,1]$上的多项式空间于$L^2([-1,1], \mathrm dm)$中完备. 定义$\mu$使得$\mu(y)=y^{1/3}$, 则对$f\in C[-1,1]$均有
$$
\int_{[-1,1]}|f(x)|^2\mathrm dx=\int_{[-1,1]}|f(y^{1/3})|^2\mathrm d\mu(y)
$$
再由$\mu([-1,1])=m([-1,1])=2$知$[-1,1]$上的多项式空间于$L^2([-1,1], \mathrm d\mu)$中稠密. 故存在多项式$p(y)$使得对$\forall \varepsilon>0$均有
$$
\int_{[-1,1]}|f(y^{1/3})-p(y)|^2\mathrm d\mu(y)<\varepsilon^2
$$
从而
$$
\int_{[-1,1]}|f(x)-p(x^3)|^2\mathrm dx<\varepsilon^2
$$
从而$\{x^{3n}\}_{n\geq 0}$在$C([-1,1])$中稠密, 因此在$L^2([-1,1])$中稠密.

若将极大线性无关组中可去之元素定义为"冗余的", 则$L^2([-1,1])$中极大线性无关组$\{x^n\}_{n\geq 0}$中任一元素均为"冗余的": 初视之甚反直觉!

为寻找一组其内元素"不可或缺"之基底, 标准正交化的基底为一极佳选择.

### 正交化

由上文知, 任一有限维Hilbert空间同构于相应的欧式空间($\mathbb R^n$或$\mathbb C^n$). 同时, 完备空间之标准正交基与任一线性无关组等价, 自然有将一般线性无关组标准正交化之途径. 其中Gram-Schmidt方法颇具用场: 取$\{x_n\}$为其一组线性无关量, 则标准正交化步骤如下

1. $e_1:=\dfrac{x_1}{\|x_i\|}$为模长为$1$之向量.
2. $y_2:=x_2-(x_2,e_1)e_1$, $e_2:=\dfrac{y_2}{\|y_2\|}$.
3. 如是递推, $y_n:=x_n-\sum_{i=1}^{n-1}(x_n,e_i)e_i$, $e_n:=\dfrac{y_n}{\|y_n\|}$.
4. 得标准正交化的基底$\{e_n\}$.

应特别注意, 正交化线性无关组较线性无关组的另一好处是其导出了$L^2$空间至$l^2$空间之双射. 在正交化线性无关组中, 任一基均不能由其他所有基表示: 这并非显然的结论!

### 加权正交基

由于并未规定测度$\mu$, 测度间的转化等同于同一测度下权之变化(可理解为换元法). 设$-\infty<a<b<\infty$, 定义$L_w^2([a,b])$中的加权内积
$$
(x,y)=\int_a^bx(t){y(t)}^*w(t)\mathrm dt
$$
以及范数$\|x\|=\sqrt{\int_a^b |x(t)|^2 w(t)\mathrm dt}$. 对线性无关组$\{t^n\}_{n\geq 0}$依加权内积标准正交化, 则相应结果如下

| $a,b$            | $w(t)$                                       | $e_n(t)$名称        |
| ---------------- | -------------------------------------------- | ------------------- |
| $-1,1$           | $1$                                          | Legendre多项式      |
| $-1,1$           | $\dfrac{1}{\sqrt{1-t^2}}$                    | 第一类Чебышёв多项式 |
| $-1,1$           | $\sqrt{1-t^2}$                               | 第二类Чебышёв多项式 |
| $-1,1$           | $(1-t)^\alpha(1+t)^\beta$, $\alpha,\beta>-1$ | Jacobi多项式        |
| $0,\infty$       | $t^\alpha e^{-t}$, $\alpha>-1$               | Laguerre多项式      |
| $-\infty,\infty$ | $e^{-t^2}$                                   | Hermite多项式       |

例如, 对于一种(正交)三角多项式上的内积运算
$$
\int_{-\pi}^\pi\cos n\theta\cos m\theta\mathrm d\theta=\pi\delta_{mn}
$$
置$\theta=\arccos x$即得Чебышёв多项式组($T_n(x)=\cos(n\arccos x)$). 其合理性基于测度$\mu$与$m$之转换, 其中
$$
\mathrm d\theta=\mathrm d\mu(x)=\dfrac{1}{-\sqrt{1-x^2}}\mathrm dx
$$
且$m([-\pi,\pi])=\mu([-1,1])<\infty$.

***

## 弱收敛性

在标准正交基$\{e_n\}_{n\geq 1}$下, 单位开球$B(0,1)=\{x:\|x\|\leq 1\}$非紧, 因为$\{e_n\}$于$B(0,1)$无聚点. 职是之故, 应当考虑引入$X$中较弱之拓扑结构使得$B(0,1)$紧. 自然的想法是找到一组线性映射使$H$映入某一紧空间.

设$X^*$为上述连续对偶映射之集合, $\tau_w$为$X^*$生成的拓扑空间. 记$x_n\overset w\to x$为$x_n$在弱拓扑空间中趋向$x$. 即
$$
\forall \phi\in X^*:x_n\overset w\to x_0\Leftrightarrow \phi(x_n)\to\phi(x_0)
$$
Hahn Banach定理指出一般的$(X,\tau _w)$可分. 对Hilbert空间而言, 取任意$x,y\in H$且$z:=x-y\neq 0$. 取$\phi_t=(\cdot,t)\in H^*$, 则
$$
0<\|z\|^2_H=\phi_z(z)=\phi_z(x)-\phi_z(y)=:3\varepsilon
$$
因此$\{t:|\phi_z(x)-\phi_z(t)|<\varepsilon\}$与$\{t:|\phi_z(y)-\phi_z(t)|<\varepsilon\}$不相交, 即$H$可分.

以Alaoglu定理为例, 设$\{e_n\}$为$H$的一组标准正交基, 定义度量
$$
\rho(x,y)=\sum_{n=1}^\infty\dfrac{|(x-y,e_n)|}{2^n}
$$
则$(B(0,1),\rho)$为紧度量空间. 相应地有$\rho(e_n,0)\to 0$, 即$e_n\overset w\to 0$.

其中并未见得$\|e_n\|_H\to 0$; 但对$x_n\overset n\to x$有如下结论:
$$
\|x\|^2=\lim_{n\to\infty}(x_n,x)\leq\liminf_{n\to\infty}\|x_n\|\|x\|=\|x\|\liminf_{n\to\infty}\|x_n\|
$$
因此$\|\liminf_{n\to\infty}x_n\|\leq\liminf_{n\to\infty}\|x_n\|$. 可比较Fatou引理
$$
{\displaystyle \int _{S}\liminf _{n\to \infty }f_{n}\,d\mu \leq \liminf _{n\to \infty }\int _{S}f_{n}\,d\mu .}
$$
由于$\{e_i\}$生成全空间, 以下叙述等价:

* $x_n\overset w\to x,n\to\infty$.
* $\forall y\in H:(x_n,y)\to (x,y),n\to\infty$.
* $\forall e_m:(x_n,e_m)\to (x,e_m),n\to\infty$.

类比欧式空间中的Weierstrass定理. 可以在完备Hilbert空间中的任意无穷序列$\{x_n\}$中找出弱收敛之子序列$\{x_{n_k}\}$. 类似Ascoli引理之证明, 只需不断寻找子序列使得$(x^{(m)}_n,e_m)$收敛, 再取$x_{n_k}=x^{(k)}_k$即可.

***


