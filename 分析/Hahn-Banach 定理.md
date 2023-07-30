### Hahn-Banach 定理

注: 本章讨论一般的度量空间, 从而使用序列刻画连续性及紧致性等足矣, 暂不大动干戈.

##### Banach 空间与范数

**Def.** 称 $X$ 为域 $\mathbb F\in \{\mathbb R,\mathbb C\}$ 上的线性空间, 若且仅若满足 "八条规则".

**Def.** 称 $p$ 为线性空间 $X$ 上的一个半范数, 若且仅若

* $p:X\to \mathbb R_{\geq 0}$.
* $\forall a>0, x\in X:p(ax)=a p(x)$.
* $\forall x,y\in X:p(x+y)\leq p(x)+p(y)$. 

特别地, 若 $p(x)=0\Leftrightarrow x=0$, 则称 $p$ 为范数.

**Example.** 范数为半范数. 线性算子的绝对值也为半范数, 其为范数当且仅当算子的余维度为 $0$ (即在任意一维空间上不是零算子). 

**Example.** 范数直接导出度量. 半范数不一定导出度量, 因为缺失自反性. 

**Def.** 称 $(X,\|\cdot \|)$ 为 Banach 空间, 若且仅若其为完备的范数空间.

**Example.** 有限维线性空间一定为 Banach 空间. 无穷维线性空间不一定为 Banach 空间: 例如内积空间 $(\mathrm{span}(e_1,e_2,\ldots ),\|\cdot\|)$ 不为 Banach 空间, 因为 Cauchy 列 $\{\sum_{k=1}^n k^{-1}e_k\}_{n\geq 1}$ 的极限不在原空间中. 

**Def.** 称 $\ell$ 为 $X$ 上的线性泛函, 若且仅若

* $\ell:X\to \mathbb F$, $\mathbb F=\mathbb R$ 或 $\mathbb C$ 取决于 $X$ 所在的域.
* $\ell$ 为线性映射, 即 $\ell(x+cy)=\ell (x)+c\ell(y)$, $\forall  x,y\in X$, $\forall c\in\mathbb F$. 

**Def.** 称 $T$ 为线性空间 $X$ 到线性空间 $U$ 上的 $\mathbb F$-线性算子, 若且仅若 $T:X\to U$ 为线性映射, 即 $T(x+cy)=T (x)+c T(y)$, $\forall  x,y\in X$, $\forall c\in\mathbb F$. 

> 特别地, $T:\mathbb C\to \mathbb C,z\mapsto \overline z$ 为 $\mathbb R$-线性算子 , 但在 $\mathbb C$ 上不再线性. $\mathbb C$-线性算子一定为 $\mathbb R$-线性算子. 

**Example.** 线性泛函即某一 $X$ 到 $\mathbb F$ 上的线性算子. 

**Def.** 记 $X$ 到 $Y$ 的线性算子空间为 $\mathcal L(X,Y)$. 

**Def.** 算子 $T\in \mathcal L(X,Y)$ 的范数为 $\|T\|:=\sup\dfrac{\|Tx\|}{\|x\|}=\sup_{\|x\|=1}\|Tx\|$. 

**Example.** $\mathcal L(X,Y)$ 不一定为范数空间, 因为算子范数可能达到无穷. 

**Def.** 取 $\mathcal B(X,Y):=\{T\mid \|T\|<\infty\}$ 为 $\mathcal L(X,Y)$ 的线性子空间, 即有界算子空间. 

**Prop.** 对 $T\in\mathcal L(X,Y)$, 以下概念等价: 

1. $T$ 在某一点 $x_0\in X$ 连续. 
2. $T$ 在 $X$ 上连续.
3. $T$ 在 $X$ 上一致连续.
4. $T\in\mathcal B(X,Y)$. 

*Proof.* 前三条等价是因为算子的线性性. 

**3.** 与 **4.** 等价是因为
$$
\forall \varepsilon >0,\exists \delta >0,\forall \|x-x'\|<\delta:\|T(x)-T(x')\|<\varepsilon
$$
等价于 $\|T\|=\sup_{\|x\|=1}\|Tx\|\leq \dfrac{\varepsilon }{\delta}$. 

$\square$

**Example.** $\mathcal B(X,Y)$ 为 Banach 空间, 因为任意 Cauchy 列 $\{T_n\}_{n\in \mathbb N}$ 的逐点极限恰导出某一有界线性算子, 记作 $\{T_n\}_{n\in \mathbb N}$ 之极限. 

##### 原始定理

**Thm.** (Hahn-Banach) 设 $X$ 为 $\mathbb F$ 上的线性空间, $Y$ 为 $X$ 的线性子空间, $p$ 为 $X$ 上的半范数, $\ell$ 为 $Y$ 上的范数. 若 $p(y)\geq \ell(y)$ 对一切 $y\in Y$ 成立, 则存在 $X $ 上的线性泛函 $\tilde \ell (:X\to \mathbb F)$ 使得

* $\tilde \ell (y)=\ell(y)$, $\forall y\in Y$.
* $p(x)\geq \ell(x)$, $\forall x\in X$. 

*Proof.* 

**Step 1.** 当 $\mathbb F=\mathbb R$ 时, 假设 $Y\subsetneq X$, 取 $z_0\in X\setminus Y$. 对任意 $y,y'\in Y$, 总有
$$
\ell(y+y')\leq p(y+y')\leq p(y+z_0)+p(y'-z_0).
$$
从而 $\ell(y')-p(y'-z_0)\leq p(y+z_0)-\ell (y)$, $\forall y,y'\in Y$. 记

* $m=\sup_{y'\in Y}(\ell(y')-p(y'-z_0))$,
* $M=\inf _{y\in Y}(p(y+z_0)-\ell (y))$. 

显然 $m\leq M$. 取 $\tilde \ell(z_0)=a\in[m,M]$ 即可得 $\ell$ 在 $\mathrm{span}(Y,z_0)$ 上的延拓. 

**Step 2.** 当 $\mathbb F=\mathbb C$ 时, $\ell$ 为 $\mathbb C$ 上的线性泛函, $\mathrm{Re}(\ell )$ 为 $\mathbb R$ 上的线性泛函. 取 $\ell (x)=\mathrm{Re}(\ell (x))-i\mathrm{Re}(\ell (ix))$ 即可. 

**Step 3.** 记作 $(Z^\#,\ell^\#)$ 为 $(Y,\ell)$ 在 $Z^\#$ 上的一种延拓. 考虑 $P$ 为 $(Y,\ell)$ 在某一线性子空间上的延拓所构成的偏序集, 记 $(Z^\#,\ell^\#)\leq (Z^\$,\ell^\$)$ 当且仅当 $Z^\#\subset Z^\$$ 且 $\ell^\$|_{Z^\#}=\ell^\#$. 对任意 $P$ 中的链 $\{(Z_i,\ell_i)\}_{i\in I}$, 存在极大元 
$$
(Z_0,\ell_0),\quad Z_0=\cup_{i\in I}Z_i,\ell_0|_{Z_i}=\ell_i.
$$
若极大元 $(Z_0,\ell_0)$ 满足 $Z_0\subsetneq X$, 则存在 $z_0\in X\setminus Z_0$ 使得 $(Z_0,\ell_0)$ 可扩张为更大的元, 矛盾! 因此只能有 $Z_0=X$. 

$\square$

> 注: Hanh-Banach 定理未涉及 Banach 空间, 连续线性泛函等限定.

**Col.** 对任意 $x_0\in X$, 存在 $X$ 上连续线性泛函 $\ell$, 使得 $|\ell (x_0)|=\|x_0\|$. 

*Proof.* 只需考虑 $x_0\neq 0$ 时情形. 对 $X$ 上的半范数 $\|\cdot\|$ 与一维空间 $\mathrm{span}(x_0)$ 上的连续线性泛函 $\ell(\lambda x_0)=\lambda\|x_0\|$ 采用 Hahn-Banach 定理即可. 

$\square$

**Col.** $\ell$ 为 $X$ 上的连续线性泛函, 则 $\|x_0\|=\sup_{\|\ell\|=1}|\ell(x_0)|$. 

*Proof.* 只需考虑 $x_0\neq 0$ 时情形. 一方面, $\sup_{\|\ell\|=1}|\ell(x_0)|\leq \sup_{\|\ell\|=1}\|x_0\|=\|x_0\|$. 另一方面, 存在使得 $|\ell(x_0)|=\|x_0\|$ 且 $\|\ell\|=1$ 的连续线性泛函, 因此不等式可取等. 

$\square$

**Col.** 对 $X$ 的线性子空间 $Y$ 与任意 $x_0\in X\setminus Y$, 记 $d_0:=\inf_{y\in Y}\|x_0-y\|$ 为 $x_0$ 到 $Y$ 的距离, 则存在 $X$ 上的连续线性泛函 $\ell$ 使得 $\ell$ 在 $Y$ 上恒为 $0$ 且 $\ell(x_0)=d_0$. 

*Proof.* 定义半范数 $p(x):=\inf_{y\in Y}\|x-y\|$ 即可. 

**Example.** 连续线性泛函延拓并非显然事实. 例如取 $X$ 为 $[0,1]$ 上的 $\mathrm{span}(1,x,x^2,\ldots)$, 范数 $\|f\|:=(\int_{[1,2]}|f|^2)^{1/2}$, 则存在线性泛函 $\ell$ 使得 $\ell(x)=\ell(x^2)=\cdots =0$. 若定义 $\ell(1)$ 使得 $\ell$ 仍连续, 则只能有 $\ell(1)=0$. 因为 $\{(x-1)^k\}_{k\geq 1}$ 收敛至 $0$, 从而 $\ell((x-1)^k)=(-1)^k \ell(1)$ 只能收敛至 $0$, 故 $\ell(1)=0$. 

##### 应用: 凸集分离定理

**Def.** 称 $S$ 为 $X$ 中的凸集, 若且仅若 $\forall x,y\in S$, $\forall \theta\in[0,1]$, 总有 $\theta x+(1-\theta) y\in S$. 

**Thm.** 设 $A$ 为凸开集, $B$ 为凸集, $A\cap B=\emptyset $, 则存在 $\mathbb R$-连续线性泛函 $\ell$ 使得 
$$
\sup_{x\in A}\ell(x)\geq \inf_{y\in B} \ell(y),
$$
即超平面 $\ell(z)=\sup_{x\in A}\ell(x)$ 分离 $A$ 与 $B$.  

*Proof.* 

**Step 1.** 取 $A-B:=\{x-y\mid x\in A,y\in B\}$, 任取 $x_0\in A-B$, 记 $C:=\{x-y-x_0\mid x\in A,y\in B\}$. 显然 $C$ 为开集且包含原点. 

**Step 2.** 作 $X$ 上的半范数 $p(z):=\min\{\lambda\in\mathbb R_{\geq 0}\mid z\in \lambda\cdot C\}$, 则 $p$ 在 $C$ 边界上取值为 $1$. 取 $\mathrm{span}(x_0)$ 上的线性泛函 $f$ 满足 $f(x_0)=p(x_0)$, 则存在延拓 $\tilde f$ 使得 $\tilde f$ 在 $X$ 上取值不超过 $p$. 

**Step 3.** 注意到 $x_0\notin C$, 从而 $\forall x\in A$, $y\in B$,  
$$
\tilde f(x-y-x_0)=\tilde f(x)-\tilde f(y)-p(x_0)\leq \tilde f(x)-\tilde f(y).
$$
从而 $\tilde f(y)\leq \tilde f(x)$ 恒成立. 

$\square$ 

**Col.** $A$ 为凸开集, $B$ 为与 $A$ 不相交的凸集, 则存在 $\mathbb R$-连续线性泛函 $\ell$ 与 $c\in\mathbb R$ 使得 $\sup_{x\in A}\ell(x)> c\geq \inf_{y\in B} \ell(y)$. 

**Col.** $A$ 为紧凸集, $B$ 为与 $A$ 不相交的闭凸集, 则存在 $\mathbb R$-连续线性泛函 $\ell$ 使得 $(\sup_{x\in A}\ell(x),\inf_{y\in B} \ell(y))$ 为区间. 

*Proof.* 注意到 $A$ 上连续函数 $d_B(x)=\inf_{y\in B}d(x,y)$ 在紧集 $A$ 上取达正的最小值, 从而存在 $\varepsilon>0$ 使得 $A+t\varepsilon$ 为与 $B$ 不交的凸开集 ($t\in (0,1)$). 

$\square$

##### 应用: 二次对偶的典范嵌入

**Def.** 记 $X$ 为 $\mathbb F$ 上线性空间, 定义对偶空间为 $X^\ast:=\mathcal B(X,\mathbb F)$. 

**Thm.** 存在等距嵌入 $J:X\to X^{\ast\ast},x\mapsto J_x$, 等距即 $\|x\|\equiv \|J_x\|$. 

*Proof.* 一方面, $J_x:X^\ast \to \mathbb F, \ell\mapsto J_x(\ell)=\ell(x)$ 为良定义的线性映射, 从而 $J$ 为线性空间的嵌入. 另一方面, 由 Hahn-Banach 定理之推论得
$$
\|J_x\|=\sup_{\|\ell\|=1}|J_x(\ell)|=\sup_{\|\ell\|=1}|\ell(x)|=\|x\|. 
$$
从而为等距嵌入. 

$\square$

**Def.** 称 $X$ 为自反的, 若且仅若 $J:X\to X^{\ast\ast}$ 为同构. 

**Example.** 空间
$$
\ell^p:=\{x=\{x_n\}_{n\geq 1}\mid \|x\|_{\ell^p}=\sqrt[p]{\sum_{n\geq 1}|x_n|^p}<\infty\}
$$
为反射的, 若 $p\in (1,+\infty)$. 特别地, $(\ell^p)^\ast =\ell^q$, 其中 $p^{-1}+q^{-1}=1$. 

*Proof.* 不难验证 $(\ell^p)^\ast$ 包含 $\ell^{q}$ 中一切元素, 因为任意 $f\in \ell^q$, 总有
$$
\|f\|=\sup_{\|x\|_{\ell^p}=1}|f(x)|\leq \|f\|_{\ell^q}\cdot \|x\|_{\ell^p}<\infty.
$$
另一方面, 由于 $\mathrm{span}(\{e_n\}_{n\geq 1})$ 在 $\ell^p$ 中稠密, 从而 $\forall f\in (\ell^p)^\ast$ 可记作
$$
\sum_{n\geq 1} a_ne_n\mapsto  \sum_{n\geq 1}a_n c_n.
$$
由于对任意 $\{a_n\}_{n\geq 1}\in \ell^p$, 总存在 $\{c_n\}_{n\geq 1}$ 使得 
$$
|\sum_{n\geq 1}a_n c_n|=\|a\|_{\ell^p}\cdot \| c\|_{\ell^q}
$$
因此 $\|f\|_{\ell^q}<\infty$ 是必要的. 证毕. 

$\square$

**Prop.** 对某些 $\ell\in X^\ast$, 或不存在 $x\in X$ 使得 $\dfrac{|\ell(x)|}{\|x\|}=\|\ell\|$, 此时空间不自反. 

*Proof.* 根据 Hahn-Banach 定理, 存在 $\varphi\in X^{\ast\ast}$ 使得 $\dfrac{\|\varphi (\ell)\|}{\|\varphi\|}$. 若 $J:X\to X^{\ast\ast}$ 为同构, 则存在唯一的 $x\in X$ 使得 $J_x=\varphi$. 这与 $\dfrac{|\ell(x)|}{\|x\|}=\|\ell\|$ 矛盾!

$\square$

职是之故, $\ell^1$, $(C([0,1]),\|\cdot\|_\infty)$, $\ell^\infty$, $c_0$, 以及非自反空间的对偶空间等均非自反. 

**Example.** $c_0$ 表示一切收敛至 $0$ 的数列, 则 $(c_0)^\ast=\ell^1 $. 

*Proof.* 注意到 $\mathrm{span}\{e_k\}_{k\geq 1}$ 在 $c_0$ 中稠密, 则 $f\in (c_0)^\ast$ 可写作
$$
f:x=\sum_{k\geq 1}c_ke_k\mapsto \sum_{k\geq 1}f(e_k)c_k.
$$
根据 Abel-Dirichlet 判别法, 显然 $\ell^1$ 中一切元素均在 $(c_0)^\ast$ 中. 反之若存在 $f$ 使得 $\sum_{k\geq 1}|f(e_k)|=\infty$, 下证明 $f$ 无解, 即存在 $x\in c_0$ 使得 $f(x)=\infty$. 

换言之, 需找到比 $\sum_{k\geq 1}|f(e_k)|=\infty$ 发散速度更慢的级数 $\sum_{k\geq 1}|x_n|\cdot |f(e_k)|=\infty$, 其中 $x_n\to 0$. 实际上, 取正项序列 $\{D_k\}_{k\geq 1}$ 使得 $\sum_{k\geq 1}D_k=\infty$. 记 $d_k=\dfrac{D_k}{D_1+\cdots D_{k-1}}$, 则

* $\displaystyle{\lim_{k\to\infty}\dfrac{d_k}{D_k}=\lim_{k\to\infty}\dfrac{1}{D_1+\cdots D_{k-1}}=0}$,
* $\displaystyle{\sum_{k\geq 1}d_k>\sum_{k\geq 1}\int_{D_1+\cdots D_{k-1}}^{D_1+\cdots +D_k}\dfrac{\mathrm dx}{x}=\infty}$. 

得证.

$\square$ 

**Example.** 证明 $(\ell^1)^\ast=\ell^\infty$. 

*Proof.* 显然 $\ell^\infty \subset (\ell^1)^\ast$. 注意到 $\mathrm{span}\{e_k\}_{k\geq 1}$ 在 $\ell^1$ 中稠密, 则 $f$ 可写作
$$
f:x=\sum_{k\geq 1}c_ke_k\mapsto \sum_{k\geq 1}f(e_k)c_k.
$$
若存在 $\{e_{n_k}\}_{k\geq 1}$ 使得 $|f(e_{n_k})|\to \infty$, 则 $\ell^1$ 中收敛至 $0$ 的序列 $\{e_{n_k}\cdot \sqrt{|f(e_{n_k})|}^{-1}\}$ 在 $f$ 下发散, 与 $f$ 之连续性矛盾. 

$\square$

**Example.** $\ell^1$ 不自反, 即存在无法在 $\ell^1$ 中表示的 $\ell^\infty$ 中的泛函. 

*Proof.* 记 $c$ 为收敛数列之全体, 显然 $c_0\subsetneq c\subsetneq \ell^\infty$. 显然, $c$ 上泛函 $\lim_{n\to\infty}$ 无法用 $\ell^1$ 表示. 下证明 $\lim_{n\to \infty}$ 的某种延拓可在 $\ell^\infty$ 中定义. 

记 $p(x)=\limsup_{n\to\infty}|x_n|$ 为 $\ell^\infty$ 上的半范数, $f(x)=\lim_{n\to\infty} x_n$ 为真子空间 $c\subsetneq \ell^\infty$ 上的连续线性泛函. 根据 Hahn-Banach 定理, 存在延拓 $\tilde f$ 使得

* $\tilde f(x)=f(x)$, $\forall x\in c$. 
* $|\tilde f(x)|\leq p(x)$. 

$\square$

**Thm.** $(\ell^\infty)^\ast$ 等距同构于 $\beta\mathbb N$ 上有限 Borel 测度. 

*Proof.* 留作 Stone–Čech compactification 的补充内容. 

$\square$ 

##### 应用: Banach 极限

**Thm.** (Generalised Hahn-Banach theorem, Agnew & Morse) 记 $\mathcal A\subset \mathcal L(X,X)$ 为一族两两可交换的线性映射 (即 $\mathcal A$ 为交换算子半群), $X$ 上的半范数 $p$ 满足 $p(A x)\leq p(x)$, $\forall A\in\mathcal A$. 若存在线性子空间 $Y\subset X$ 上的线性泛函 $\ell$ 使得

* $\ell(y)\leq p(y)$, $\forall y\in Y$. 
* $\mathcal A|_Y\subset \mathcal L(Y,Y)$. 
* $\ell(A y)=\ell(y)$, $\forall y\in Y$, $\forall A\in\mathcal A$. 

从而存在延拓 $\tilde \ell$ 使得

* $\tilde \ell(x)\leq p(x)$, $\forall x\in X$. 
* $\tilde \ell(Ax)=\tilde \ell(x)$, $\forall A\in \mathcal A$, $\forall x\in X$. 

*Proof.* 略, 自行查看 Lax 的泛函分析. 

$\square$

此时可定义 $\ell^\infty$ 上的某种极限 $\mathrm{LIM}_{n\to\infty}$ 使得

* $\mathrm{LIM}_{n\to\infty}\in (\ell^\infty)^\ast$. 
* $\mathrm{LIM}_{n\to\infty} x_n=\lim_{n\to\infty}x_n$, $\forall x\in c\subsetneq \ell^\infty$. 
* $\liminf_{n\to\infty} x_n\leq \mathrm{LIM}_{n\to\infty} x_n\leq \limsup _{n\to\infty}x_n$, $\forall x\in \ell^\infty$. 
* $\mathrm{LIM}_{n\to\infty}$ 在左平移算子与右平移算子下不变. 

**Def.** 称满足以上性质的 $\mathrm{LIM}_{n\to\infty}$ 为 Banach 极限. 

**Prop.** 可定义有界函数空间上的 Banach 极限. 

##### 应用: Tauberian 理论

Tauberian 理论研究一类单参数变换的函数族对所在空间的刻画, 例如证明了平移算子在 $f\in L^2(\mathbb R^n)$ 上作用的轨道在 $L^2(\mathbb R^n)$ 中稠密的充要条件. 

**Lemma.** $\forall f\in L^1(\mathbb R^n)$, $\forall t\in \mathbb R^n$, $\exists \varepsilon>0$ , $\exists h\,( \|h\|_{L^1(\mathbb R^n)}<\varepsilon )$ 使得 $\hat h(s)=\hat f(t)-\hat f(s)$ 对一切 $s\in U$ 成立, $U$ 为某一 $t$ 的邻域. 

*Proof.* 取 $g\in L^1(\mathbb R^n)$ 使得 $\hat g\equiv 1$ 在原点附近成立. 任取 $\forall \lambda >0$, 置
$$
\begin{align*}
g_\lambda (x)&:=e^{it\cdot x}\lambda^{-n}g(x/\lambda),\\
h_\lambda(x)&:= \hat f(t)g_\lambda (x)-(f\ast g_\lambda)(x). 
\end{align*}
$$
此处 $g_\lambda$ 为缩放后的 Fourier 变换之积分项, $h_\lambda$ 用于导出 $g$ 与之平移的积分差. 注意到 $\hat g_\lambda (s)=1$ 在 $t$ 的某邻域 $U_\lambda$ 中成立, 则对 $s\in V_\lambda$ 总有 $\hat h(s)=\hat f(t)-\hat f(s)$. 注意到
$$
h_\lambda (x)=\int_{\mathbb R^n} f(y)[e^{-it\cdot y}g_\lambda (x)-g_\lambda (x-y)]\mathrm dy.
$$
从而据控制收敛定理有
$$
\begin{align*}
\|h_\lambda\|_{L^1(\mathbb R^n)}&=\int_{\mathbb R^n}|h_\lambda|\\
&\leq \int_{\mathbb R^n}|f|\cdot \int_{\mathbb R^n}|g(\xi)-g(\xi-\lambda^{-1}y)|\\
&\overset{\lambda\to 0}= 0.
\end{align*}
$$
$\square$

**Thm.** 取 $\phi\in L^\infty(\mathbb R^n)$, 取子空间
$$
Y\subset [ L^1(\mathbb R^n)\cap \{f\mid f\ast \phi=0\}].
$$
则 $Z(Y):=\cap _{f\in Y}\{s\in\mathbb R^n\mid \hat f(s)=0\}$ 包含 $\hat \phi$ 的紧支撑. 

*Proof.* 选定 $t\in Z(Y)^c$, 则存在 $f\in Y$ 使得 $\hat f(t)=1$. 根据引理, 存在 $h\in L^1(\mathbb R^n)$ 使得 $\|h\|_{L^1(\mathbb R^n)}<1$, 使得 $\hat h(s)=1-\hat f(s)$ 在 $t$ 的某一邻域 $U$ 中成立. 下仅需证明 $\hat \phi=0$ 对 $U$ 中元素成立. 等价地, $\hat \phi\cdot \hat \psi $ 对一切速降空间中在 $U$ 中有紧支撑的 $\psi\in\mathscr S(\mathbb R^n )$ 成立, 再等价地, $\psi\ast \phi=0$. 

置 $g_0=\psi$, $g_m=h\ast g_{m-1}$, 由 Young 不等式知 $\|g_m\|_{L^1(\mathbb R)}\leq \|h\|_{L^1(\mathbb R^n)}^m\cdot \|\psi\|_{L^1(\mathbb R^n)}$. 注意到 $(1-\hat h(s))\hat \psi(s)=\hat\psi(s)\hat f(s)$, 故 $\hat \psi =\sum_{m=1}^\infty\hat h^m\hat\psi \hat f$. 由于 $\|h\|_{L^1(\mathbb R^n)}<1$, 故 $\sum_{n\geq 1}\hat h^m\in L^1(\mathbb R^n)$​. 从而得 
$$
\psi\ast \phi =(\sum_{n\geq 1} g_m)\ast f\ast \phi =0. 
$$
$\square$

**Thm.** (Wiener) 记 $\mathcal L_0$ 为平移算子群, $Y\subset L^1(\mathbb R^n)$ 为 $\mathcal L_0$ 的不变子空间, 则 $Y=L^1(\mathbb R^n)$. 

*Proof.* $\forall f\in Y$, $\forall x_0\in \mathbb R^n$, 平移算子 $ L_{x_0}:Y\to Y,f(x)\mapsto f(x+x_0)$. 若存在 $\phi\in L^\infty (\mathbb R^n)$ 使得 $\int f\check\phi=0$ 对一切 $f\in Y$ 恒成立, 则 $f\ast \phi =0$. 根据上一定理, $\hat \phi$ 的支撑为空集, 从而 $\hat \phi=0$. 注意到 Fourier 变换在 $\mathscr S(\mathbb R^n)$ 上一一对应, 从而 $\phi =0$ a.e. in $L^\infty(\mathbb R^n)$. 

由于 $T^\perp =0$, 根据 Hahn-Banach 定理知 $Y= L^1(\mathbb R^n)$. 

$\square$

**Col.** 取 $K\in L^1(\mathbb R^n)$, $Y$ 为 $L^1(\mathbb R^n)$ 上包含 $K$ 的最小闭子空间, 则 $Y= L^1(\mathbb R^n)$ 若且仅若 $\hat K(t)\neq 0$ 对任意 $t\in \mathbb R$ 成立. 

*Proof.* 注意到 $Z(Y)=\{t\in\mathbb R^n\mid \hat K(t)=0\}$. 根据 Wiener 定理, $Z(Y)$ 空当且仅当 $Y= L^1(\mathbb R^n)$. 

$\square$