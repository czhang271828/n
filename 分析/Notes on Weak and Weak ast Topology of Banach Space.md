# Notes on Weak and Weak$^\ast$ Topology

[toc]

## Weak Topology

**Definition 1-1.** The **weak topology** on Banach space $X$ is defined is the coarsest topology such that each $\varphi\in X^\ast$ is continuous on $X$. Henceforth we assume $X$ is always a Banach space, and denote its weak topology by $\sigma(X,X^\ast)$. 

**Proposition 1-1.** $(X,\sigma(X,X^\ast))$ is always *Hausforff*. 

**Proof.** For each $x\neq y$ in this topology space, *Hahn-Banach's theorem* illustrates that there exists $\ell \in X^\ast$ such that $\ell(x-y)\neq 0$. Therefore, there exist two open neighbourhoods  $U_x,U_y$ such that $\ell^\to (U_x)\cap \ell^{\to }(U_y)=\empty$. 

> Here $\ell^\to $ is defined  $\mathcal P(X)$, $\ell^\to :A(\subset X)\mapsto \{\ell(x):x\in A\}$. 

$\square$

**Definition 1-2.** The sequence $\{x_n\}_{n\geq 1}\subset X$ is weakly convergent to $x_0\in X$ whence $\ell(x_n)\to \ell(x_0)$ for each $\ell\in X^\ast$. Henceforth we denote the **weak convergence** by $x_n\rightharpoonup x_0$. 

> Here, weak convergence also means **convergence in the weak topology** $(X,\sigma(X,X^\ast))$. 

**Proposition 1-2.** As a result, we have the following propositions:

**(a)** Weak convergence is a direct result of **strong convergence**, that is, convergence in $(X,\|\cdot \|_X)$. 

**(b)** Weak convergent sequence is bounded.

**(c)** If a sequence $\{x_n\}_{n\geq 1}\subset X$ converges to $x_0$ weakly, then $\|x_0\|\leq \liminf_{n\to\infty}\|x_n\|$.

**(d)** If $x_n\rightharpoonup x_0$ in $X$ and $f_n\to f_0$ in $X^\ast$, then $f_n(x_n)\to f_0(x_0)$. 

**Proof.** **(a)** Since $|\ell (x)-\ell(y)|\leq \|\ell\|\cdot \|x-y\|$ for each $\ell\in X^\ast$ and $x,y\in X$, it directly follows that $x_n\to x_0$ implies $x_n\rightharpoonup x_0$. 

**(b)** Consider the canonical imbedding $J:X\to X^{\ast\ast}, x\mapsto (\ell\mapsto \ell(x))$. We claim it isomertric since
$$
\|J(x)\|=\sup_{\|\ell\|=1} \|(J(x))(\ell)\|=\sup_{\|\ell\|=1}|\ell(x)|=\|x\|.
$$

> The final inequality is a corollary of *Hahn-Banach's theorem*. 

The *Banach-Steinhaus theorem* reveals that if $\{(J(x_n))(\ell)\}_{n\geq 1}$ is bounded for each $\ell\in X^\ast$, then $\sup_{n\geq 1}\|J(x_n)\|<\infty$. As a result, $\|x_n\|<\infty$. 

**(c)** Via *Hahn-Banach's theorem*, there exists $\ell_0\in X^\ast$ such that $\ell_0(x_0)=\|x_0\|$ and $\|\ell_0\|=1$​. Then
$$
\|x_0\|=\lim_{n\to\infty}|\ell_0(x_n)|=\liminf_{n\to\infty}|\ell_0(x_n)|\leq\|\ell_0\|\cdot \liminf_{n\to\infty}\|x_n\|.
$$
**(d)** Indeed, when $x^{(k)}_n\rightharpoonup x_0^{(k)}$ in $X^{k\ast}$ ($X^{\ast \cdots\ast}$ with $k$ $\ast$'s) for $k=0,1,\ldots,m-1$ and $x_n^{(m)}\to x_0^{(m)}$. We have $x_n^{(m)}x_n^{(m-1)}\cdots x_n^{(0)}\to x_0^{(m)}x_0^{(m-1)}\cdots x_0^{(0)}$. Then 
$$
\begin{align*}
&\quad\,\,|x_n^{(m)}x_n^{(m-1)}\cdots x_n^{(0)}-x_0^{(m)}x_0^{(m-1)}\cdots x_0^{(0)}|\\
&=\sum_{k=0}^{m-1}|x_n^{(m)}\cdots x_n^{(k+1)}x_0^{(k)}\cdots x_0^{(0)}-x_n^{(m)}\cdots x_n^{(k)}x_0^{(k-1)}\cdots x_0^{(0)}|\\
&\overset{n\to\infty}{=}0.
\end{align*}
$$

$\square$

**Proposition 1-3.** For finite dimensional space $V$, the weak topology coincides the topology induced by norm. 

**Proof. ** Indeed, the weak topology coincides strong topology in $V$. Let $\{x_n=(x_n^1,x_n^2,\ldots, x_n^d)\}_{n\geq 1}\subset V$ be a sequence converging to $x_0=(x_0^1,\ldots, x_0^d)$ weakly. Then $x_n\rightharpoonup x_0$​ implies that
$$
e_k(x_n)\to e_k(x_0),\quad e_k(\in V^\ast):x\mapsto x^k.
$$
Thus $\|x_n-x_0\|\leq \sum_{i=1}^d |e_k(x_n-x_0)|\to 0$ as $n\to\infty$.  

$\square$

**Proposition 1-4.** Let $S\subset X$ be convex and closed (in norm sense) subset in Banach space $X$, then $S$ is weakly closed. 

**Proof.** For each $x\notin S$, there exists linear map that seperates the compact convex set $\{x\}$ and closed convex set $S$, i.e., $\exists f\in X^\ast$ such that $\inf f^\to (\{x\})\geq \alpha >\beta\geq \sup f^\to (S)$. 

Hence $x$ is an exterior point of $S$ in sense of weak topology. 

$\square$

## Lower Semi-continuity

**Definition 2-1.** $f:X\to\mathbb R$ is called **lower semi-continuous** whence 
$$
f^{\leftarrow}((-\infty,\alpha]):=\{x\in X\mid f(x)\leq \alpha\}
$$
is closed in $X$ for each $\alpha \in\mathbb R$. 

If follows that $f(x_0)\leq\lim\inf_{n\to\infty} f(x_n)$ as $x_n\to x_0$ while $f$​ is semi-continuous. As shown in previous, norm function is also semi-continuous in the weak topology, i.e., 
$$
\|x_0\|\leq \liminf_{n\to\infty}\|x_n\|\quad\text{as }x_n\rightharpoonup x_0.
$$
**Definition 2-2.** The **Shur condition** is that each sequence converges in norm topology whence it converges in weak topology. For instanse, the $\ell^1$ space satisfies such condition as follows.

**Shur's lemma.** In $\ell^1$ space, convergence in norm topology coincides the convergence in weak topology.

**Proof.** The convergence in norm topology implies weak convergence directly. 

Conversely, we denote $x^k$ by the $k$-th entry of $x$. $\{e_k\}_{k\geq 1}$ be such that $e_i^j=\delta_{ij}$. If $x_n\not \to 0$ in $\ell ^1$, then there exists a subsequence $\{x_{n_k}\}_{k\geq 1}$ such that $\|x_{n_k}\|_{\ell^1}\geq \varepsilon_0$ for some $\varepsilon_0>0$. Without the loss of generality, let $\{x_{n_k}\}_{k\geq 1}$ be $\{x_n\}_{n\geq 1}$ itself.

Let $n_0$ be such that $\|(x_1^{n_0+1},x_1^{n_0+2},\ldots)\|_{\ell^1}<\varepsilon_0/6$. Then let $T_0(e^i)= \mathrm{sgn}(x_1^i)$ for each $i\leq n_0$ and $T_0(e^i)=0$ for the rest. There exists $m_1>1$ such that $\|(x_{m_1}^1,x_{m_1}^2,\ldots, x_{m_1}^{n_0})\|_{\ell^1}<\varepsilon_0/6$. We can take $n_1>n_0$ such that $\|(x_{m_1}^{n_1+1},x_{m_1}^{n_1+2},\ldots)\|_{\ell^1}<\varepsilon_0/6$. Let $T_1(e^i)=\mathrm{sgn}(x_{m_1}^i)$ for each $n_0<i\leq n_1$. 

Let $m_0=1$, $n_{-1}=0$. Then for each $p\in\mathbb N\cup\{0\}$ we can construct $\{(n_p,m_p,T_p)\}$ such that

* $\|(x_{m_p}^1,\ldots, x_{m_p}^{n_{p-1}+1})\|_{\ell^1}<\varepsilon_0/6$, $\|(x_{m_p}^{n_p+1},\ldots)\|_{\ell^1}<\varepsilon_0/6$. 
* $T_p(e_i)=\mathrm{sgn}(x_{m_p}^i)$ whence $n_{p-1}+1\leq i\leq n_p$, $T_p(e_i)=0$ for the rest.

Therefore $T_p(x_{m_p})\geq -2\cdot (\varepsilon_0/6)+\varepsilon_0=2\varepsilon_0/3$. Since $T:=\sum_{p\geq 0}T_p\in \ell^\infty$, it reveals that $T(x_{m_p})>\varepsilon_0/2$ for each $p$, which contradicts the definition of weak convergence. 

$\square$

## Weak Continuity

**Definition 3-1.** We say the linear mapping $T:X\to Y$​ is **weakly continuous** whenever $T$​ is a continuous map in sense of weak topology, i.e., 
$$
T:(X,\sigma(X,X^\ast))\to (Y,\sigma(Y,Y^\ast))\quad \text{is continuous}.
$$
**Proposition 3-1.** The linear map $T:X\to Y$ is weakly continuous whenever 
$$
f\circ T:X\to \mathbb F,x\mapsto f\circ T(x)
$$
is weakly continuous for each $f\in Y^\ast$. 

**Proof.** Let $I$ denote any open set in $\mathbb F$. 

* If $T$ is weakly continuous, then $f^{\leftarrow}(I)$ is weakly open in $Y$. Thus $T^{\leftarrow}(f^\leftarrow (I))=(f\circ T)^{\leftarrow}(I)$ is weakly open. It yields that $f\circ T$ is weakly continuous. 

* If $f\circ T$ is weakly continuous, then $T^{\leftarrow}(f^\leftarrow (I))=(f\circ T)^{\leftarrow}(I)$ is weakly open in $X$. By definition of weak open sets, the weakly open set in $Y$ is a finite intersection of $f_j^\leftarrow (I_j)$ for $j\in J<\infty$. Since the preimage of weakly open sets are weakly open in $X$, $T$ is weakly continous. 

$\square$

**Proposition 3-2.** The linear maps $T:X\to Y$ is continuous whenever it is weakly continuous. 

**Proof.** $\Rightarrow:$ If $T\in \mathcal L(X,Y)$, then $f\circ T$ is weakly continuous for each $y\in Y^\ast$. Hence $T$ is weakly continuous due to the previous lemma. 

$\Leftarrow:$ Let $T$ be weakly continuous. Since the weak topology in Hausdorff, $G(T)$ is closed in $X\times Y$ in the weak topology (the diagonal under the map $\mathrm{Id}\times T$ is closed in Hausdorff space). The continuity of $T$ is a consequence of closed graph theorem. 

$\square$ 

## Weak$^\ast$ Topology

Dual space $X^\ast$ is also endowed with the weak topology, which is coarsest topology such that each $f\in X^{\ast\ast}$ is continuous on $X^\ast$​. Consider the *canonical imbedding* 
$$
J:X\to X^{\ast\ast},x\mapsto J_x,\quad J_x:\ell (\in X^\ast)\mapsto \ell(x).
$$
Whenever $X$ is not reflexive, the new topology of $X^\ast$ that each $f\in J^\to (X)\cong x$ is continuous on $X^\ast$ is coarser than $(X^\ast,\sigma(X^\ast,X^{\ast\ast}))$. Hence we can define a new topology as follows.

**Definition 4-1.** The **weak$^\ast$ topology** on the dual space $X^\ast $ is defined is the coarsest topology such that each $f\in J^\to (X^{\ast\ast})\cong X$ is continuous on $X^\ast $. Henceforth we denote the weak$^\ast$ topology of $X^\ast$ by $\sigma(X^\ast,X)$. 

**Proposition 4-1.** When $X^\ast$ is reflexive, the weak and weak$^\ast$ topology coincides. 

**Proof.** When $X^\ast$ is reflexive, the *canonical imbedding* $J_\ast :X^\ast\to X^{\ast\ast\ast }$ is an isomorphism, thus $J_{\ast \ast}=(J_\ast^\ast)^{-1}=(J_\ast^{-1})^\ast$ is also an isomorphism. Hence $X^{\ast\ast}$ is reflexive. Then $J:X\to X^{\ast\ast}$ is an isomorphism. It yields that the the weak and weak$^\ast$ topology coincides. 

$\square$ 

Albeit coarser, the $(X^\ast, \sigma(X^\ast, X))$ is still Hausdorff. 

**Proposition 4-2.** For dual space $X^\ast$ of each Banach space $X$, $(X^\ast ,\sigma(X^\ast,X))$ is always *Hausforff*. 

**Proof.** For each $f_1\neq f_2$ in $X^\ast$, there exists $x\in X$ such that $\|f_1(x)-f_2(x)\|=3\varepsilon _0>0$. We choose $r=\dfrac{\varepsilon_0}{\|x\|}$. Let
$$
U_i:=\{g\in X^\ast\mid \|g-f_i\|\leq r\},\quad i=1,2/ 
$$
Then $J_x(U_1)\cap J_x(U_2)=\emptyset$. As a result, $(X^\ast ,\sigma(X^\ast,X))$ is always *Hausforff*. 

$\square$

**Definition 4-2.** The sequence $\{f_n\}_{n\geq 1}\subset X^\ast$ is said to be **weakly$^\ast$ convergent** whenever $f_n(x)\to f(x)$ for each $x\in X$. We write weak$^\ast$ convergence as $f_n\overset{\ast}{\rightharpoonup} f$ in $X^\ast$. 

**Proposition 4-3.** $f_n\to f\implies f_n\rightharpoonup f\implies f_n\overset{\ast}{\rightharpoonup} f$. 

**Proof.** This equivalents that normed topology is finer than weak topology, and much finer than weak$^\ast$ topology. $f_n\to f\implies f_n\rightharpoonup f$​ is already shown in the previous proposition. The latter is due to 
$$
[g(f_n)\to g(f)\quad \forall g\in X^{\ast\ast}]\\
\implies [J_x(f_n)\to J_x(f)\quad \forall x\in X].
$$
$\square$

**Banach-Alaoglu Theorem.** The closed unit ball in $X^\ast$ is weak$^\ast$ compact. 

**Proof.** By virture of *Tychonoff's theorem*, the product space
$$
Y:=\prod_{x\in X}[-\|x\|,\|x\|]
$$
with usual topology inherited from $\mathbb R$ is compact. For each $f$ in $B_1^\ast$, the closed unit ball in $X^\ast$, the map 
$$
\varphi:f\mapsto \varphi(f)=(f(x))_{x\in X}
$$
leads a homeomorphism from $B_1^\ast$ to $\varphi(B_1^\ast)\subset Y$ when the unit ball in $X$ is endowed with the topology induced by the weak$^\ast$ topology of $X^\ast$. The boundedness of $f$ shows that whenever $f$ is linear, $\varphi(B_1^\ast)$ is closed, thus $\varphi(B^\ast_1)$ and $B_1^\ast$ are compact. 

We show that $f(x+cy)=f(x)+c f(y)$ for each $x,y,c$. For arbitrarily small $\varepsilon=\varepsilon(x,y,c)>0$ There exists $g\in B_1^\ast$ such that 
$$
\small{|g(x)-f(x)|,|c|\cdot|g(y)-f(y)|,|g(x+cy)-f(x+cy)|\leq\dfrac{\varepsilon}{3}}. 
$$
Thus $|f(x+cy)-f(x)-cf(y)|\leq\varepsilon$. It yields that $f$ is linear. 

$\square$

## Weak Completeness

**Definition 5-1.** We say a topological space $(X,\tau)$ is **metrisable** whenever there exists a metric $d$ that the induced topology of $d$ coincides with $(X,\tau)$. 

**Proposition 5-2.** The weak topology $\sigma(X,X^\ast)$ is not metrisable whenever $\dim X=\infty$. 

**Proof. ** It is clear that $X^\ast$ is metrisable when $\dim X<\infty$ since the weak topology coincides strong topology. When $X$ is infinite dimensional, we assume there exists a metric $d$ in $(X,\sigma(X,X^\ast))$ for the sake of contradiction. 

Let $B_k:=\{x\in X\mid d(x,0)<k^{-1}\}$ be a weak open neighbourhood of the origin. Then there exists a finite collection $\mathscr  F_k\subset X^\ast$ and $\varepsilon_k>0$ such that 
$$
W_k:=\{x\in X\mid \|f(x)\|<\varepsilon_k,\forall f\in \mathscr F_k\}\subset B_k.
$$
Let $\mathscr F:=\cup_{k\geq 1}\mathscr F_k$ be a countable subset of $X^\ast$. Take any $g\in X^\ast$ such that $W=\{x\in X\mid \|g(x)\|<1\}$. Then there exists $N\in\mathbb N$ such that $B_k\subset W$ for each $k\geq 1$. As a consequence, $W_k\subset W$. 

Now consider $x\in \cap _{f\in \mathscr F_k}\ker f$. Then $\lambda x\in W_k$ for each $\lambda\in\mathbb R$. Since $\lambda x\in W_k\subset W$, $\|g(\lambda x)\|=|\lambda |\|g(x)\|<1$. It yields that $x\in \ker g$. 

We notice that $f$ is a linear combination of $\{f_i\}_{i=1}^m$ whenever $\cap _{i=1}^n\ker f_i\subset \ker f$. Therefore, we deduce that $X^\ast=\mathrm{span}(\mathscr F)$. Since $\mathscr F$ is consists countable union of finite dimensional spaces which is nowhere dense in $X^\ast$, it contradicts that $X^\ast$ is in category II. 

$\square$

Due to the lack of metric for weak topology, the Cauchy sequences fail to illustrates the weak topology fully. This is why  we utilise Cauchy net to study the weak completeness. 

**Definition 5-2.** We say $(X,\sigma(X,X^\ast))$ is **weakly complete** (weakly sequentially complete, respectively) when the **Cauchy net** $\{x_\alpha\}_{\alpha\in A}\rightharpoonup x$ (Cauchy sequence $\{x_n\}_{n\geq 1}\rightharpoonup x$, respectively). 

**Proposition 5-3.** Weak completeness implies weakly sequential completeness. There exists a normed linear space which is weakly sequentially complete yet not weakly complete. 

**Proof.** Since each sequence is a web, it directly follows that weak completeness implies weakly sequential completeness.

Conversely, the Banach space $L([a,b])$ is weakly sequentailly complete yet not weakly complete. We claim that $\{x_n\}_{n\geq 1}\rightharpoonup x$ whenever 

* $\sup_{n\geq 1}\|x_n\|<\infty$,
* For each Lebesgue measurable set $E\subset [a,b]$, the limit $\lim_{n\to\infty}\int_Ex_n $ exists. 

This is due to each $f\in L^\infty$ can be approximated by step functions in $L^\infty$ sense. Equivalently, step functions are dense in $L^\infty$.  

Take $f\in L^\infty([a,b])$. The limit $\lim_{n\to\infty}f(x_n)$ exists. Then Banach-Steinhaus theory illustrates that $\|x_n\|$ is bounded. Hence $x_n\rightharpoonup x$ by the claim above. 

Since the weak topology of $L([a,b])$ no longer satisfies first axiom of countability, it is not weakly complete. 

$\square$ 

**Proposition 5-4.** There exists a Banach space which is not weakly sequentially complete. 

**Proof. ** Let $C_0$ denotes all sequences converging to $0$. We claim that $(C_0)^\ast =\ell_1$. It follows directly that $\ell^1\subset C_0^\ast$. Since $C_0\subset \overline{\mathrm{span}\{e_k\}_{k\geq 1}}$, $T\in C_0^\ast$ is in form of
$$
T:x=\sum_{k\geq 1}c_ke_k\mapsto \sum_{k\geq 1}T(e_k)c_k.
$$
Then we claim that $\{T(e_k)\}_{k\geq 1}\in \ell^1$. If not, then $\sum_{k\geq 1}|T(e_k)|=\infty$. The following lemma proves the existence of $x\in C_0$ such that $T(c)=\infty$. 

> **Lemma.** There is no slowest rate of divergence of a sequence. 
>
> **Proof of the lemma.** Let $\{D_k\}_{k\geq 1}$ be a positive series such that $\sum_{k\geq 1}D_k=\infty$. We claim the existence of $\{d_k\}_{k\geq 1}$ such that $\sum_{k\geq 1}d_k=\infty$ while $\lim_{k\to\infty}\dfrac{d_k}{D_k}=0$. 
>
> Indeed, $d_k=\dfrac{D_k}{D_1+\cdots D_{k-1}}$ is what we desired. This is due to
>
> * $\displaystyle{\lim_{k\to\infty}\dfrac{d_k}{D_k}=\lim_{k\to\infty}\dfrac{1}{D_1+\cdots D_{k-1}}=0}$,
> * $\displaystyle{\sum_{k\geq 1}d_k>\sum_{k\geq 1}\int_{D_1+\cdots D_{k-1}}^{D_1+\cdots +D_k}\dfrac{\mathrm dx}{x}=\infty}$. 
>
> $\square$ 

It yields that $C_0^\ast=\ell^1$. 

Take $\ell^1\ni T=(a_1,a_2,\ldots)$, $x_n=\sum_{k=1}^n e_k$. Then 
$$
|T(x_m)-T(x_n)|\leq \sum_{i=m+1}^n |a_i|,\quad n>m.
$$
Since $T\in \ell^1$, $\{T(x_n)\}_{n\geq 1}$ is Cauchy sequence. However, $x_n\rightharpoonup (1,1,\ldots)\notin C_0$, thus $C_0$ is not weakly sequentially complete. 

$\square$

Even though normed topology and weak topology distincts in each infinite dimensional normed linear space, the following propositon always holds. 

**Proposition 5-5.** The space of linear continuous functionals always coincides in normed topology and weak topology. 

**Proof.** By definition of weak topology, it is clear that each $f\in X^\ast$ is continuous in $(X,\sigma(X,X^\ast))$. Conversely, Let $f\neq 0$ be continuous in $(X,\sigma(X,X^\ast))$. There exists a weak neighbourhood of $0$, defined by
$$
V=\{x\in X\mid |f_i(x)|<\varepsilon ,i=1,2,\ldots, n\}\subset \{x\mid |f(x)|<1\}. 
$$
For each $x_0\in \cap _{i=1}^n\ker f_i$, $\lambda x_0\in V$ for each $\lambda\in\mathbb R$. As a consequence, $f(\lambda x_0)\equiv 0$. It reveals that $f$ is a linear conbination of $f_i$'s.

$\square$

<div style="page-break-after: always"></div>

## References

[Ker09] S. Kesavan. *Weak and Weak Topologies\**, pages 132–161. Hindustan Book Agency, Gurgaon, 2009.

[Ram20] G. Ramesh. *Weak topologies*, 2020.

[Wan14] L. Wang. *Functional analysis of counter-examples*. The foundation of modern mathematics -40(Chinese Edition). Higher Education Press, 1 2014
