## *De Rham* 上同调简介

#### 概念拾遗

**Lie 导数** 试回顾 Lie 导数的定义以及若干性质. 

* $k$-形式 $\omega$ 关于切向量场 $X$ 拉回之求导即 Lie 导数 $L_X\omega $, 记 $\{\phi_t\}$ 为 $X$ 生成的(局部)单参数子群, $\phi_t(p)=\phi(t,p)$ 为 $p$ 处的积分曲线, 满足 $X(\phi_{t_0}(p))=\phi (t,p)'(t_0)$. 定义 Lie 导数在切向量上 $Y_i$ 上作用为
  $$
  (L_X\omega) (Y_1,\ldots, Y_s):=\left(\dfrac{\mathrm d}{\mathrm dt}\omega_{\phi(t,p)}((\phi_t)_\ast(Y_1),\ldots (\phi_t)_\ast(Y_s))\right)_{t=0}=\left(\dfrac{\mathrm d}{\mathrm dt}(\phi_t)^\ast (\omega )\right)_{t=0}.
  $$

* 对 $M$ 上光滑函数 $f$, $L_X(f)=\left(\dfrac{\mathrm d}{\mathrm dt}f(\phi(t,p))\right)_{t=0}=Xf$. 

* 拉回映射给出 $(\phi_t)^\ast (\omega \wedge \eta )=(\phi_t)^\ast (\omega) \wedge (\phi_t)^\ast (\eta)$, 求导得 $L_X(\omega \wedge \eta)=L_X(\omega )\wedge \eta +\omega \wedge L_X(\eta)$. 

* 外微分与拉回映射可交换, 即 $f:M\to N$ 与 $M$ 上切向量 $X$ 给出 ($\forall g\in A^0(M)$)
  $$
  f^\ast (\mathrm d g)(X)=\mathrm dg(f_\ast X)= (f_\ast X)(g)=X(f^\ast g)=\mathrm d(f^\ast g) X.
  $$
  对微分形式 $g\mathrm dx^{i_1}\wedge \cdots \wedge \mathrm dx^{i_k}$ 之证明类似. 因此 $\mathrm d$ 与 Lie 导数可交换, 即, $\mathrm dL_X=L_X\mathrm d$. 

* Lie 导数与 Lie 括号可换, 即, $[L_X,L_Y]=L_{[X,Y]}$. 证明略. 

* 有恒等式 $\mathrm d\circ i_X+i_X\circ \mathrm d=L_X$. 记 $\omega =f\mathrm dx^{i_1}\wedge \cdots \wedge \mathrm dx^k=f\tau $, 则
  $$
  \begin{align*}
  \mathrm d(i_X (\omega))&=\mathrm df\wedge i_X(\tau)+f\mathrm d i_X(\tau)\\[8pt]
  &=\mathrm df\wedge i_X(\tau)+f\mathrm d\sum_{1\leq s\leq k}\mathrm d x^{i_1}\wedge \cdots \wedge {\mathrm dx^{i_{s-1}}}\wedge \mathrm d X(x^{i_s})\wedge{\mathrm dx^{i_{s+1}}}\wedge \cdots \wedge \mathrm d x^{k};\\[8pt]
  i_X(\mathrm d \omega )&=i_X(\mathrm df\wedge \mathrm d\tau)=(Xf)\mathrm d\tau-\mathrm d f\wedge i_X(\tau);\\[8pt]
  L_X(\omega )&=L_X(f)\mathrm d\tau+fL_X(\mathrm d\tau)\\[8pt]
  &=(Xf)\mathrm d\tau+f\mathrm d\sum_{1\leq s\leq k}\mathrm d x^{i_1}\wedge \cdots \wedge {\mathrm dx^{i_{s-1}}}\wedge \mathrm d X(x^{i_s})\wedge{\mathrm dx^{i_{s+1}}}\wedge \cdots \wedge \mathrm d x^{k}.
  \end{align*}
  $$
  从而得证. 

**定义** [外幂]: 给定开区域 $U\subset \mathbb R^n$ 以及光滑函数环 $R=C^\infty(U)$, 定义自由 $R$-模(不妨想象作 $R$-线性空间)
$$
M=R\mathrm dx^1\oplus R \mathrm dx^2\oplus \cdots \oplus R\mathrm dx^n.
$$
其中 $m\in M$ 形如
$$
m=\sum _{1\leq i\leq n}m_i \mathrm dx^i\qquad (m_i\in R). 
$$
定义交换环 $R$ 上的模 $\bigwedge ^k M$ 为 $k$ 个 $M$​ 的外积(wedge), 其元素形如张量积
$$
\sum _{I} f_I\cdot \mathrm dx^{i_1}\otimes_R  \cdots \otimes_R \mathrm dx^{i_k}.
$$

> 对任意 $x,y\in M$ 与 $f\in R$, $x\otimes_R fy=fx\otimes _Ry$. 同时 $(-\otimes_R -)$ 为 $R$-双线性映射. 

称张量积 $\otimes _R$ 为 $\wedge $​, 若其满足反对称性, i.e., 
$$
\mathrm d x^i\otimes \mathrm dx^j=-\mathrm d x^j\otimes \mathrm dx^i\qquad(\forall 1\leq i,j\leq n). 
$$
**定义** [外导数 $\mathrm d^k$] 记 $U$ 上微分 $r$-形式 $A^r(U):=\bigwedge^rM$, 定义外导数 
$$
\mathrm d^k:A^r(U)\longrightarrow A^{r+1}(U),\quad \textsf{元素略}.
$$
特别地, 有 $R$-模间同构 $A^0(U)\simeq R$, $A^1(U)\simeq M$ 等. 

**定义** [闭形式与恰当形式] 取 $\omega \in A^r(U)$, 其中 $1\leq r\leq n$. 

1. 称 $\omega$ 为闭形式当且仅当 $\mathrm d^r\omega=0$, 即, $\omega \in Z^r(U;\mathbb R):=\mathrm{ker}(d^r)$;
2. 称 $\omega$ 为恰当形式当且仅当存在 $g\in A^{r-1}(U)$ 使得 $\mathrm d g=\omega $, 即, $g\in B^r(U;\mathbb R):=\mathrm{im}(\mathrm d^{r-1})$. 

**定义** [(上)链复形] 姑且记 $\mathrm d^{-1}:0\to A^0(U)$ 为零映射, 对任意 $0\leq r\leq n$​ 总有链
$$
0\overset{\mathrm d^{-1}}\longrightarrow  A^0(U)\overset{\mathrm d^{0}}\longrightarrow  A^1(U)\overset{\mathrm d^{1}}\longrightarrow \cdots \overset{\mathrm d^{n-1}}\longrightarrow  A^n(U)\overset{\mathrm d^{n}}\longrightarrow 0\qquad (d^r\circ d^{r-1}=0).
$$
称之链复形. 换言之, $A^r(U)$ 中恰当形式一定是闭形式.

**问题 **闭形式与恰当形式何时等价? 目前之所学表明: 

* [Poincaré 引理] 对任意单连通区域 $U\subset \mathbb R^n$, $A^1(\mathbb R^n)$ 中闭形式与恰当形式等价.
* [链复形的基本性质] 恰当形式 $\implies $ 闭形式. 

***

#### De Rham 上同调群一瞥

**定义** [de Rham 上同调群] 定义 de Rham 上同调群为 Abel 群 $H_{\mathrm {dR}}^k(U;\mathbb R):=\dfrac{Z^k(U;\mathbb R)}{B^k(U;\mathbb R)}=\dfrac{\mathrm{ker}(\mathrm d^k)}{\mathrm{im}(\mathrm d^{k-1})}$.

> 以下记 $H^k_{\mathrm {dR}}(U):=H^k_{\mathrm {dR}}(U;\mathbb R)$; 若 $\mathrm H^k_{\mathrm{dR}}(U)\simeq \mathbb R^m$, 则可简略地记作 $\mathrm H^k_{\mathrm{dR}}(U)= \mathbb R^m$.

**例** [$U\dot\cup V\subset \mathbb R^2$ 的上同调群 $H_{\mathrm{dR}}^0(-)$] 此处 $\dot\cup$ 表示无交并. 依照定义, $\mathrm{im}(\mathrm d^{-1})=0$, 从而
$$
H_{\mathrm{dR}}^0(U\dot \cup V)\simeq \mathrm{ker}(\mathrm d^0)=\{c\cdot \mathrm {id}_{U}+c'\mathrm{id}_{V}\mid c,c'\in \mathbb R\}\simeq \mathbb R^2.
$$
**例** [$\mathbb R^2\setminus \{0\}$ 的上同调群 $H_{\mathrm{dR}}^1(-)$] 以下为证明思路. 

1. $H_{\mathrm{dR}}^1(\mathbb R^2\setminus \{0\})=\dfrac{\mathrm{ker}(\mathrm d^1)}{\mathrm{im}(\mathrm d^0)}$ 非平凡, 因为 $[0]\neq [\mathrm d\theta ]:=\left[\dfrac{x^1\mathrm dx^2-x^2\mathrm dx^1}{x^1x^1+x^2x^2}\right]$. 此处 $\mathrm d\theta $ 是定义在开集
   $$
   \mathbb R^2\setminus \{(r,0)\mid r\geq 0\}
   $$
   上的恰当 $1$-形式, 但 $\mathrm d\theta$ 在 $\mathbb R^2\setminus \{0\}$ 上非恰当形式, 因为单位圆周上的积分 $\displaystyle \oint_{S^1}\mathrm d\theta =2\pi \neq 0$. 

2. 对任意 $\omega \in A^1(\mathbb R^2\setminus \{0\})$, 存在唯一的 $\displaystyle C\quad (=\dfrac{1}{2\pi}\oint_S\omega )$ 使得 $\omega -C\mathrm d\theta$ 在 $\mathbb R^2\setminus \{0\}$ 上任意环路积分为 $0$. 

3. 从而 $g:=\displaystyle \int_{(1,0)}^{(x^1,x^2)}\big(\omega-C\mathrm d\theta\big)$ 为 $\mathbb R^2\setminus \{0\}$ 上良定义的积分, 其中 $\mathrm d g=\omega -C\mathrm d\theta$. 

4. 因此有内自同构 $\mathrm{ker}(\mathrm d^1)=\{r\mathrm d\theta \mid r\in \mathbb R\}\oplus \mathrm{im}(\mathrm d^0)\simeq \mathbb R\oplus \mathrm{im}(\mathrm d^0)$, 故 $H_{\mathrm{dR}}^1(\mathbb R^2\setminus \{0\})= \mathbb R$. 

*注* 对二维情形, $\dim_{\mathbb R}H^1_{\mathrm{dR}}(U)$ 为连通分支的数量, $\dim_{\mathbb R}H^1_{\mathrm{dR}}(U)$ 为洞的数量. 

**定理** [Poincaré 引理] 对 $1\leq k\leq n$, 总有 $H^k_{\mathrm{dR}}(\mathbb R^n)=0$; $H^0_{\mathrm{dR}}(\mathbb R^n)=\mathbb R$. 证明思路如下.

1. 对任意 $\omega :=a\mathrm dx^1\wedge \cdots \wedge \mathrm dx^n$, 有 $\displaystyle \omega:=\mathrm d\left[\int_0^{x^1}a(t,x^2,\ldots, x^n)\mathrm dt\cdot \mathrm dx^2\wedge\cdots \wedge \mathrm dx^n \right]$. 

2. 对 $1\leq k\leq n$ 以及闭 $k$-形式 $\omega$, 记 $\omega =\omega _1+\mathrm dx^1\wedge \omega _2$, 其中 $\omega_i$ 不含 $\mathrm dx^1$. 记 $\omega_2=\sum_I a_I\mathrm d x^1\wedge \mathrm dx^I$, 则
   $$
   \mathrm dx^1\wedge \omega _2=\mathrm d\left[\int_0^{x^1}a_I(t,x^I)\mathrm dt\cdot \sum _I a_I\mathrm dx^I\right]=:\mathrm d\tau .
   $$
   因此 $\omega -\tau$ 为不含 $x^1$ 的闭 $(k-1)$-形式.

3. 依照前两步进行归纳即可. 

***

#### 同伦不变性

**定义** [流形间映射之拉回诱导 de Rham 上同调群之同态] 光滑映射 $f:M\to N$​ 将闭形式拉回为闭形式, 将恰当形式拉回为恰当形式. 故有群同态
$$
f^\ast :H_{\mathrm {dR}}^k(N)\to H_{\mathrm {dR}}^k(M),\qquad [\omega ]\mapsto [f^\ast \omega]. 
$$
*注* 上链复形间的同态诱导了 $\mathrm{ker}$ 与 $\mathrm{coker}$ 构成的上链复形, 且上链复形同态自然给出. 

![diagram-20230625](https://czhang271828.github.io/z/diagram-20230625.svg)

由于 $\mathrm{im} f^\ast=\mathrm{coker}(\mathrm{ker}f^\ast)=\mathrm{ker}(\mathrm{coker}f^\ast)$, 从而 $f^\ast$ 给出的 de Rham 上同调群间同态是自然的. 

**例** 我们有理由相信, $H^1_{\mathrm{dR}}(\mathbb R^2\setminus \{0\})=H^1_{\mathrm{dR}}((\mathbb R^2\setminus \{0\})\times \mathbb R)$, 因为余维度为 $1$ 的洞决定 $H^1_{\mathrm{dR}}$. 验证略. 

**定理** 对任意微分流形 $M$ 均有 $H^k_\mathrm{dR}(M)=H^k_{\mathrm{dR}}(\mathbb R\times M)$. 其中 $0\leq k\leq n$, $M$ 局部同胚于 $\mathbb R^n$. 

> 提示: $\mathbb R\times M$ 上 $k$-形式 $\omega$ 与 $M$ 上 $k$-形式 $\omega_{t=r_0}$ (给定 $r_0\in \mathbb R$) 等价. 不妨设 $\omega =\omega _1+\mathrm dt\wedge \omega _2$, 其中 $\omega _i$ 不含 $\mathrm dt$. 考虑 $i_{\partial _t}:=\left<\partial _t,-\right>$ 在 $\omega$ 上的作用, 故 $i_{\partial _t}(\omega )=\omega _2$. 从而当 $\mathrm d\omega=0$ 时有
> $$
> \mathrm d\omega _2=\mathrm d (i_{\partial _t}(\omega))=\mathrm d (i_{\partial _t}(\omega))+i_{\partial _t}(\mathrm d\omega )=L_{\partial _t}\omega =\partial _t \omega
> $$
> (注意恒等式 $\mathrm d\circ i_X+i_X\circ \mathrm d=L_X$). 遂有
> $$
> \omega -\omega_{t=r_0}=\int_{r_0}^t\partial _t \omega =\mathrm d\int_{r_0}^t\omega _2. 
> $$
> 故 $\omega$ 为恰当形式当且仅当 $\omega_{t=r_0}$ 为恰当形式.

**定义** [同伦光滑映射] 称光滑映射 $f,g:M\to N$ 同伦, 若存在光滑映射 $F:[0,1]\times M\to N$ 使得
$$
F(0,-):M\to N,m\mapsto f(m),\qquad F(1,-):M\to N,m\mapsto g(m).
$$
可将 $F$ 光滑地延拓至 $\mathbb R\times M\to N$, 使得 $F(t,-)=f(-)$ 若 $t\leq 0$, $F(t,-)=g(-)$ 若 $t\geq 0$. 

>  取记 $\tilde F(t,-)=f(-)$, 若 $t\leq \dfrac 12$; $\tilde F(t,-)=g(-)$ 若 $t> \dfrac 12$. 考虑 $t$ 方向半径为 $\dfrac14$ 的磨光函数即可. 

**定理** [同伦映射诱导了 de Rham 上同调群间的相同态射] 根据 $f=F\circ i_0$ 与 $g=F\circ i_1$, 有
$$
f^\ast = i_0^\ast \circ F^\ast ,\qquad g^\ast =i_1^\ast \circ F^\ast. 
$$
由于 $i_0$ 与 $i_1$ 保持等价的微分形式(见 $H^k_\mathrm{dR}(M)=H^k_{\mathrm{dR}}(\mathbb R\times M)$), 从而 $f^\ast$ 与 $g^\ast$ 给出上同调群的相同态射. 

***

#### 例子杂谈

**定义** 对非紧流形 $M$, 定义 $A_c^k(M)\subset A^k(M)$ 为具有紧支撑的 $k$-形式全体. 例如 $H^0_{\mathrm{dR},c}(M)\neq 0$ 当且仅当 $M$ 紧. 

**例** 映射 $\displaystyle A_c^{k}(\mathbb R\times M)\to A_c^{k-1}(M), \quad \omega \mapsto \int_{\mathbb R}i_{\partial _t}\omega$ 给出同构 $H^q_{\mathrm{dR},c}(\mathbb R\times M)\simeq H_{\mathrm{dR},c}^{q-1}(M)$.

**例** de Rham 上同调群的若干计算方法.

1. 采用( Lie )群作用可证明 $H^k_{\mathrm{dR}}(T^n)=\mathbb R^{\binom{n}{k}}$ 等. 

2. 采用同伦不变性可真证明 Möbius 带与环 $S^1$ 有相同的 de Rham 上同调群等. 

3. 对开集覆盖 $M=U\cup V$, 短正合列 $0\to A^k(M)\to A^k(U)\oplus A^k(V)\to A^k(U\cap V)\to 0$ 给出长正合列(蛇引理)
   $$
   \cdots \to H^k_{\mathrm{dR}}(M)\to H^k_{\mathrm{dR}}(U)\oplus H^k_{\mathrm{dR}}(V)\to H^k_{\mathrm{dR}}(U\cap V)\overset {\widetilde {d^k}}\to H^{k+1}_{\mathrm{dR}}(M)\to \cdots.
   $$
   可据此归纳 $H_{\mathrm{dR}}^n(S^n)=\mathbb R$, $k< n$ 时有 $H^k_{\mathrm{dR}}(S^n)=0$.  

4. Künneth 定理表明对某些好的流形 $M$, 有
   $$
   H^k_{\mathrm{dR}}(M\times N)\simeq \bigoplus_{0\leq s\leq k}H^{k-s}_{\mathrm{dR}}(M)\otimes H^k_{\mathrm{dR}}(N).
   $$

5. 等等. 