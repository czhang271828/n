# Picard 小定理简介

### 定理一览

**Thm.** (开映射定理) $U$ 为 $\mathbb C$ 上开区域, 非常值函数 $f\in\mathrm{Hol}( U)$, 则 $f$ 为开映射. 

**Thm.** (Bloch 定理) 若 $f\in\mathrm{Hol}(\overline {\mathbb D})$ 满足
$$
|f'(z)|(1-|z|^2)\in C(\overline {\mathbb D}),
$$
记 $M=\sup_{z\in \overline {\mathbb D}}|f'(z)|(1-|z|^2)$, 最大值在 $z=p$ 处取达, 则
$$
D(f(p),(3/2-\sqrt 2)M)\subset f(\mathbb D).
$$
**Col.** 若 $f\in\mathrm{Hol}(\overline {\mathbb D})$ 且 $f'(0)=1$, 则 $f(\mathbb D)$ 包含半径为 $\frac{3}{2}-\sqrt 2$ 的圆. 

**Thm.** (Ahlfor) 若非常数值的全纯函数 $f\subset \mathrm{Hol}(\overline{\mathbb D})$ 满足
$$
|f'(z)|(1-|z|^2)\in C(\overline {\mathbb D}).
$$
记 $|f'(z)|(1-|z|^2)$ 在 $p\in\mathbb D$ 处取得最大值 $M$, 则 $f(\mathbb D)$ 包含一个半径为 $\dfrac{\sqrt 3}{4}M$ 的圆盘且 $f$ 与该圆盘建立双全纯映射. 

**Thm.** (Koebe $\frac{1}{4}$ 定理) 全纯函数 $f\in \mathrm{Hol}(\overline {\mathbb D})$, 则
$$
D(f(0),|f'(0)|/4)\subset f(\mathbb D).
$$
**Thm.** (Picard 小定理) 若整函数 ($\mathbb C$ 上的全纯函数) 在 $\mathbb C$ 上的值域略去两个点, 则为常函数. 

**Thm.** (Picard 大定理) 任一全纯函数在其本性奇点的邻域内无穷多次地取到 $\mathbb C$ 中几乎所有数, 至多可能除去一个例外值. 

### Bloch

**Lemma.** (弱 Bloch 定理, 将 $|z|^2$ 换做 $|z|^1$) 若非常值全纯函数 $f\subset \mathrm{Hol}(\overline{\mathbb D})$ 满足
$$
|f'(z)|(1-|z|)\in C(\overline {\mathbb D}).
$$
记 $|f'(z)|(1-|z|)$ 在 $p\in\mathbb D$ 处取得最大值 $M$, 则
$$
D(f(p),(3/2-\sqrt 2)M)\subset f(\mathbb D).
$$
*Proof.* 不失一般性地设 $f(0)=0$. 置 $A(z)=f(z)-zf'(0)$. 则 $\forall r>|z|$, 均有
$$
\begin{align*}
|A(z)|\leq&\int_0^1|f'(zt)-f'(0)|\cdot|z|\mathrm dt\\
=&\int_0^1\left|\dfrac{zt}{2\pi i}\oint_{\partial D(a;r)}\dfrac{f'(\zeta)\mathrm d\zeta}{\zeta(\zeta-zt)}\right|\cdot|z|\mathrm dt\\
\leq&\int_0^1\dfrac{|zt|\cdot|f'|_{\max_{\partial D(a;r)}}}{r-|zt|}\cdot|z|\mathrm dt\\
\leq&\dfrac{|z|^2\cdot|f'|_{\max_{\partial D(a;r)}}}{2(r-|z|)}.
\end{align*}
$$
从而 $|f(z)|\geq|f'(0)|\cdot|z|-\dfrac{|z|^2\cdot|f'|_{\max_{\partial D(a;r)}}}{2(r-|z|)}$.  记$r_0=\dfrac{1-|p|}{2}$, 则对 $\forall z\in D(p;t)$, 
$$
|f'(z)|(1-|z|)\leq M=2r_0|f'(p)|\leq2(1-|z|)\cdot|f'(p)|.
$$
等价地, $|f'(z)|\leq2|f'(p)|$. 今置 $A(z)=f(z)-(z-p)f'(p)-f(p)$, 不妨设$f(p)=0$, 则对任意 $z\in D(p;r_0)$ 均有
$$
\begin{align*}
|A(z)|\leq&\int_0^1|f'(tz+(1-t)p)-f'(p)|\cdot|z-p|\mathrm dt\\
=&\int_0^1\left|\dfrac{(z-p)t}{2\pi i}\oint_{\partial D(p;r_0)}\dfrac{f'(\zeta)\mathrm d\zeta}{(\zeta-p)(\zeta-zt-(1-t)p)}\right|\cdot|z-p|\mathrm dt\\
\leq&\int_0^1\dfrac{|z-p|\cdot t\cdot|f'|_{\max_{\partial D(p;r_0)}}}{r_0-|zt|}\cdot|z-p|\mathrm dt\\
\leq&\dfrac{|z-p|^2\cdot|f'|_{\max_{\partial D(p;r_0)}}}{2(r_0-|z-p|)}\\
\leq&\dfrac{|z-p|^2\cdot|f'(p)|}{2(r_0-|z-p|)},
\end{align*}
$$
以及
$$
|A(z)|\geq |f'(p)|\cdot|z-p|-|f(z)|.
$$
故
$$
\begin{align*}
\sup_{0\leq r\leq r_0}\inf_{|z-t|=r}|f(z)|\geq&\sup_{|z-p|\in[0,r_0)}\left(|z-p|-\dfrac{|z-p|^2}{r_0-|z-p|}\right)|f'(p)|\\
=&\small{\sup_{|z-p|\in[0,r_0)}\left[3r_0-\left(2(r_0-|z-p|)+\dfrac{r_0^2}{r_0-|r_0-r|}\right)\right]\cdot |f'(p)|}\\
=&(3-2\sqrt 2)r_0|f'(p)|,\quad |z-p|=(1-\sqrt 2^{-1})r_0\\
=&(3/2-\sqrt 2)(1-|p|)|f'(p)|\\
=&(3/2-\sqrt 2)M
\end{align*}
$$
$\square$

**Thm.** (Bloch 定理) 若 $f\in\mathrm{Hol}(\overline {\mathbb D})$ 满足
$$
|f'(z)|(1-|z|^2)\in C(\overline {\mathbb D}),
$$
记 $M=\sup_{z\in \overline {\mathbb D}}|f'(z)|(1-|z|^2)$, 最大值在 $z=p$ 处取达, 则
$$
D(f(p),(3/2-\sqrt 2)M)\subset f(\mathbb D).
$$
*Proof.* 对满足 Bloch 定理弱性质之解$f$, 下从族 $\mathcal F:=\{f\circ\varphi\mid \varphi\in\mbox{Aut}(\mathbb D)\}$ 寻找解. 

由于 $\varphi$ 具有一般形式 $\varphi(z)=\dfrac{z-z_0}{1-z\overline{z_0}}\cdot e^{i\theta}$, 其中 $|\varphi'(0)|=1-|z_0|^2$. 因此
$$
|h'(0)|=|f'(\omega)|\cdot(1-|\omega|^2),\quad \omega=-z_0 e^{i\theta}.
$$

不妨设 $f'(\omega)\cdot(1-|\omega|^2)$ 在 $\omega=q$ 时取得最大值 $M$, 今置
$$
F(z)=f\left(\dfrac{q-z}{1-z\overline q}\right),\quad (F:0\mapsto f(q)).
$$
因此对任意 $r\in(0,1)$ 均有
$$
\max_{|z|\leq r}|F'(z)|\leq\max_{|z|\leq r}\dfrac{M}{1-|z|^2}=\dfrac{M}{1-r^2}.
$$
故 $\max_{z\in\mathbb D}|F'(z)|(1-|z|^2)\leq M$. 注意到 $\max_{z\in D(0;\sqrt2/2)}|F'(z)|\leq 2|F'(0)|$, 参考若形式之证明令 $A_0(z)=F(z)-zF'(0)$. 故 $ F(D(0,\sqrt{2}/2))$ 包圆盘 $D(F(0),(3/2-\sqrt2)M)$. 注意到 $F(\mathbb D)$ 与 $f(\mathbb D)$ 有相同的相. 因此
$$
D(f(q),(3/2-\sqrt2)M)\subset f(\mathbb D).
$$
$\square$ 

**Def.** 定义 Bloch 函数族如下
$$
\mathcal B:=\{f\in \mathrm{Hol}(\mathbb D)\mid \sup_{z\in \mathbb D}|f'(z)|\cdot (1-|z|^2)<\infty\}.
$$
**Prop.** $\mathcal B$ 关于如下范数完备
$$
\|f\|:=f(0)+\sup_{z\in\mathbb D}|f'(z)|(1-|z|^2)\quad\left(\leq2\sup_{z\in\mathbb D}|f(z)|\right).
$$

### Koebe $\frac{1}{4}$ 定理

**Lemma.** (Grönwall) 若函数 $g(z)=z+\sum_{n\geq0}b_nz^{-n}$ 在单位圆盘外单叶, 则
$$
\sum_{n\geq1}n|b_n|^2\leq1.
$$
*Proof.* 对 $r>1$, 取围道 $C_r:=\{g(z):|z|=r\}$, 取 $E_r$ 为 $C_r$ 所围的紧集. 其面积为
$$
\begin{align*}
A(E_r)=&\int_{E_r}\mathrm d A
=\dfrac{1}{2i}\int_{C_r}\overline\omega\mathrm d\omega
=\dfrac{1}{2i}\int_{C_r}(\overline g\cdot g')(z)\mathrm dz\\
=&\small{\dfrac{1}{2}\int_0^{2\pi}\left(re^{-i\theta}+\sum_{n\geq0}\overline{b_n}r^{-n}e^{in\theta}\right)\cdot\left(1-\sum_{m\geq0}mb_mr^{-m-1}e^{-i(m+1)\theta}\right)re^{i\theta}\mathrm d\theta}\\
=&\pi\left(r^2-\sum_{n\geq 1}n|b_n|^2r^{-2n}\right)\\
\overset{r\to1^+}{\longrightarrow}&\pi\left(1-\sum_{n\geq 1}n|b_n|^2\right).
\end{align*}
$$
注意到 $|b_1|\leq\sum_{n\geq1}n|b_n|^2\leq1$ 取等时 $|b_1|=1$. 此时 $g(z)=z+b_0+\dfrac{b_1}{z}$. 

$\square$ 

**Def.** (Schlicht函数) 记 $\mathcal S$ 为所有Schlicht函数之集合. 任取 $f\in \mathcal S$, 有

* $f\in \mathrm{Hol}(\mathbb D)$, 且 $f$ 在 $\mathbb D$ 上为单射 (故为单叶映射), 

* $f(0)=0$, 且 $f'(0)=1$. 

**Prop.** $f(z)=z+\sum_{\geq 2}c_nz^n$ 为 $f\in\mathcal S$ 之一般形式. 

**Def.** (Koebe函数) Koebe 函数为
$$
f(z)=\dfrac{z}{(1-z)^2}=\sum_{n\geq1}nz^n.
$$
**Def.** 可通过旋转 Koebe 函数得到广义 Koebe 函数
$$
f_\alpha(z)=\dfrac{z}{(1-\alpha z)^2},\quad |\alpha|=1.
$$
**Prop.** 广义 Koebe 函数为 Schlicht函数. 

**Lemma.** (Bieberbach) 对函数 $f(z)=z+\sum_{n\geq 2}a_nz^n\in\mathcal S$, $|a_2|\leq2$ 若且仅若$f$为 Koebe 函数. 

*Proof.* 构造平方根变换 (取其中一叶即可)
$$
g(z)=\dfrac{1}{f(z^{-2})^{-1/2}}=z-\dfrac{a_2}{2}\cdot\dfrac{1}{z}+\cdots.
$$
取等时$g(z)=z-\dfrac{\alpha}{z}$, 此处 $|\alpha|=1$. 

回推得 $f(w)=\dfrac{z}{(1-\alpha z)^2}=f_\alpha(w)$ 为 Koebe 旋转函数. 

$\square$ 

**Thm.** (Koebe $\frac{1}{4}$ 定理) 全纯函数 $f\in \mathrm{Hol}(\overline {\mathbb D})$, 则
$$
D(f(0),|f'(0)|/4)\subset f(\mathbb D).
$$
*Proof.* 不妨取 $f(z)=z+\sum_{n\geq 2}a_nz^n\in\mathcal S$. 由于$f(\mathbb D)$非全空间, 任意取$\omega\in\mathbb C\setminus f(\mathbb D)$. 考虑单叶映射
$$
h_\omega(z)=\dfrac{1}{f(z)}-\dfrac{1}{\omega}=\dfrac{\omega f(z)}{\omega-f(z)}=z+(a_2+\omega^{-1})z^2+\cdots. 
$$

根据 Bieberbach 之引理, $|\omega^{-1}|\leq|a_2|+|a_2+\omega^{-1}|\leq 2+2$, 故 $|\omega|\geq 4$. 由于$\omega\in\mathbb C\setminus f(\mathbb D)$ 之任意性, $f(\mathbb D)$ 包含半径为 $1/4$ 之圆盘. 

$\square$

**Prop.** Koebe $\frac{1}{4}$ 定理中的 $1/4$ 为最佳系数. 

*Proof.* Koebe 函数 $f(z)=\dfrac{z}{(1-z)^2}$ 将 $\mathbb D$ 映射作 $\mathbb C\setminus [-\infty,1/4]$. 因此, 存在 $f$ 使得
$$
D(f(0),|f'(0)|(1/4+\varepsilon ))\not\subset f(\mathbb D)
$$
对一切 $\varepsilon>0$ 成立. 

$\square$ 

### Picard 小定理

**Thm.** (Picard 小定理) 若整函数的值域在 $\mathbb C$ 上略去两个点, 则为常函数. 

*Proof.* 下采用反证法证明 Picard 小定理. 不失一般性地, 设整函数 $f$ 在 $\mathbb C$ 上取值略过 $\pm1$, 则函数$1-f^2$无零点, 从而存在整函数 $g$ 使得 $g^2=1-f^2$. 

注意到 $(f+ig)(f-ig)=1$, 故存在整函数 $F$ 使得 $f+ig=e^{i\pi F}$. 于是
$$
f=\dfrac{1}{2}(e^{iF}+e^{-iF})=\cos \pi F.
$$
而注意到 $F$ 略去 $\{\pm 1\}$ 两点, 故
$$
\exists \varphi\in \mathrm{Hol}(\mathbb C)\text{ s.t. }f=\cos(\pi\cos(\pi \varphi)).
$$
对上述 $\varphi$, $\varphi(\mathbb C)$ 不包含某一半径之圆盘. 从而与 Bloch's 定理或 Koebe $\frac{1}{4}$ 定理矛盾. 

考虑所有整实数点在$\cos\pi z$下之原像, 构造集合
$$
A:=\mathbb Z+\{\pm i\pi^{-1}\log(n+\sqrt{n^2-1})\}.
$$
不难验证 $g(\mathbb C)\cap A=\emptyset$. 注意到 $A$ 中各点与纵向最近点相隔距离 $1$ 且与横向最近点相隔距离不超过 $2\pi^{-1}\log(2+\sqrt 3)$. 是以 $A$ 所能容纳圆盘之半径之最大值有限, 导出矛盾. Picard小定理得证. 

**Prop.** $\mathbb C$ 上的亚纯函数若略去三个取值, 则为常函数.

### 思考题

**Ex1.** 如何从 Bloch 定理或 Koebe $\frac14$ 定理得出以下推论
$$
f\in H(\mathbb C)\implies \forall r>0,\exists x_0\text{ s.t. }D(x_0,r)\subset f(\mathbb C).
$$
**Ex2.** 证明 Picard 小定理之等价形式
$$
f,g\in H(\mathbb C)\text{ and }1=e^f+e^g\Rightarrow f,g\text{ are constant}.
$$
**Ex3.** 探索 $f\in H(\mathbb C)$ 在 $\mathbb C$ 上取至所有值之充要条件.

> Hint: 考虑 $f=p\cdot e^g$, 这里$p$为多项式函数.

**Ex4.** (不动点定理) 设 $f\in H(\mathbb C)$, 则 $f\circ f$ 在 $\mathbb C$上有不动点, 反之$f$为平移变换.

> Hint: 设$f\circ f$无不动点, 考虑 $g(z)=\dfrac{f(f(z))-z}{f(z)-z}$. 

**Ex5.** (2020年丘成桐数学竞赛分析部分) 对 $\forall n\geq3$, 若整函数 $f$ 与 $g$ 满足$f^{n}+g^{n}=1$, 则$f$与$g$为常函数. 

> Hint: 本题解法较易, 与费马最后定理无关. 数学 Riemann 曲面相关知识者会认为这是到水题.

**Ex6.** (上一题加强形式) 若将全纯改至亚纯, 则 $f$ 与 $g$ 的所有pole(s)一一对应. 

**Ex7.** 证明: 存在 $\mathbb C$ 上非常值亚纯函数 $f,g$ 使得 $f^3+g^3=1$.

> Hint: 请回忆
> $$
> (\wp'(z))^2-4\wp^3(z)+60G_4\wp(z)+140 G_6=0.
> $$
> 以此验证
> $$
> \small{\left(\dfrac{\Gamma(1/3)^6}{8\pi^2}+\dfrac{\pi\wp'(z)}{\sqrt3\Gamma(1/3)^3}\right)^3+\left(\dfrac{\Gamma(1/3)^6}{8\pi^2}-\dfrac{\pi\wp'(z)}{\sqrt3\Gamma(1/3)^3}\right)^3=\wp^3(z)}.
> $$