# 图谱论组会讲稿 II

We shall discuss some subtle connections of spectral graph theory and classical analysis, including

* the Laplacian operator of a (simple) graph
* eigenvalue of weighted graphs
* application in theories of random walks

### The Laplacian

> On the threshold of spectral graph analysis.

##### Laplatian operator of a graph 

To begin with that, we shall review the definition of *adjacency matrix* $A(G)$ and *degree matrix* $D(G)$ for a simple graph $G$. The **Laplacian matrix** 
$$
L:=D-A=\left\{\begin{align*}
&\deg v&&u=v,\\
&-1&&u\sim v,\\
&0&&\text{else}.
\end{align*}\right.
$$
A brandnew concept named **Laplacian operator** (*Laplacian* for short) is defined as
$$
\mathcal L:=\left\{\begin{align*}
&1&&u=v,\\
&-\sqrt{\deg v\cdot\deg u}^{-1}&&u\sim v,\\
&0&&\text{else}.
\end{align*}\right.
$$
Here $\mathcal L=D^{-1/2}LD^{-1/2}$, where $D^{\alpha}$ is defined as
$$
(\lambda_1^\alpha,\lambda_2^\alpha,\ldots,\lambda_k^\alpha,0,\ldots,0).
$$
Consider the function $f:V(G)\to\mathbb R$ (or $\mathbb C $). Here we shall define the *inner product* ($\leftrightarrow$ what we done in *discrete Fourier analysis*). 
$$
\left< f,g\right>:=\sum_{v\in V} f(v)\overline {g(v)}
$$

> For simplicity, we only discuss the real functions below.

Laplacian of a function can be also defined via the theorem of *unit decomposition*. Let $\delta_v$ be *characteristic function* w.r.t. $v$, then
$$
\begin{align*}
\mathcal L f=&\sum_{v\in V}\left<\mathcal L f,\delta_v\right>\cdot \delta_v\\
=&\sum_{v\in V}\sum_{u\in V}\left(f(u)-\sum_{u'\sim u}\dfrac{f(u')}{\sqrt{\deg u\cdot\deg u'}}\right)\delta_v(u)\cdot\delta_v\\
=&\sum_{v\in V}\dfrac{1}{\sqrt{\deg v}}\sum_{u\sim v}\left(\dfrac{f(v)}{\sqrt{\deg v}}-\dfrac{f(u)}{\sqrt{\deg u}}\right)\cdot\delta_v
\end{align*}
$$
Hence $\forall v\in V$, we have
$$
(\mathcal Lf)(v)=\dfrac{1}{\sqrt{\deg v}}\sum_{u\sim v}\left(\dfrac{f(v)}{\sqrt{\deg v}}-\dfrac{f(u)}{\sqrt{\deg u}}\right).
$$
Notice that $\mathcal L\sim \sum_i\partial_{x_i}(\partial x_i)$ in the continuous case in a *uniform-densitied* and *nongradient* medium. 

##### Basic facts about eigenvalues

Suppose that $\lambda$ is a eigenvalue of $\mathcal L$ w.r.t. some eigenfunction $g$, then
$$
\dfrac{\left< g,\mathcal Lg\right>}{\left< g,g\right>}=\lambda.
$$
The L.H.S. outcomes
$$
\dfrac{\left< g,\mathcal Lg\right>}{\left< g,g\right>}=\dfrac{\sum_v\dfrac{g(v)}{\sqrt{\deg v}}\sum_{u\sim v}\left(\dfrac{g(v)}{\sqrt{\deg v}}-\dfrac{g(u)}{\sqrt{\deg u}}\right)}{\sum_v g(v)^2}=?
$$
Whoops, how so? The dawn of victory might occur whence you think back
$$
\left< f,Lf\right>=\sum_{u\sim v}(f(v)-f(u))^2.
$$
It suggests that once we substitude $g$ with $T^{1/2}f$, we have
$$
\dfrac{\left< g,\mathcal Lg\right>}{\left< g,g\right>}=\dfrac{\sum_{u\sim v}(f(u)-f(v))^2}{\sum_v f(v)^2\deg v}.
$$
Furthermore, the laplacian is semi-positive since $0$ is the smallest eigenvalue of $L$ with corresponding eigenvector $\mathbf 1_n$. Hence $T^{1/2}\mathbf 1$ be an eigenfunction s.t.
$$
\mathcal L(T^{1/2}\mathbf 1)=T^{-1/2}L\mathbf 1_n=0.
$$

> $\mathbf 1:V\to \{1\}$ is constant function.

We call eigenvalue $\lambda$ a main eigenvalue if and only if $\mathcal E_\lambda\not\subseteq \mathbf 1^\perp$. The **spectra** of $\mathcal L$ are $0\leq \lambda_0\leq\lambda_1\leq \cdots\leq \lambda_{n-1}$. We notice that the multiplicity of main eigenvalue $0$ equals the number of *components* in $G$ (trivial, but why?). 

Hence $\lambda_1$ is defined as (notice that $\left< T^{1/2} f, T^{1/2}\mathbf 1\right>=0$ while $T$ is *self-adjoint*.)
$$
\lambda_1=\inf_{f\perp T\mathbf 1}\dfrac{\sum_{u\sim v}(f(u)-f(v))^2}{\sum_v f(v)^2\deg v}.
$$
In continuous case... maybe we could steal a glance at the *Lichnerowicz–Obata theorem*. Let $M$ denotes a compact Riemannian manifold without boundary. Consider the eigenfunction satisfying the equation $-\Delta u=\lambda u$, we obtain
$$
\lambda\int_M u^2=-\int_{M}(\Delta u)u=\int_M (\nabla u)^2.
$$
Since the constant function is a trivial solution, the non-trivial solutions should be subject to $\int_M u=0$. The function $f$ s.t. $\left< T^{1/2} f, T^{1/2}\mathbf 1\right>=0$ is also known as the **harmonic eigenfunction**. 

Since $T^{1/2} f\perp T^{1/2}\mathbf 1$, we can rewrite the expression of $\lambda_1$ into
$$
\lambda_1=\inf_{f}\sup_{t\in\mathbb R}\dfrac{\sum_{u\sim v}(f(u)-f(v))^2}{\sum_v (f(v)-t)^2\deg v}.
$$
whence the maximum holds, $2\sum_v (f(v)-t)\deg v=0$. Let
$$
\overline f:=\dfrac{\sum_v f(v)\deg  v}{\sum_v\deg v},
$$
where $\sum_v\deg v=2|E|$ is the **volume** of $G$​. Notice that (why?)
$$
\sum_v (f(v)-\overline f)^2\deg v=\sum_{u,v}(f(u)-f(v))^2\deg u\deg v.
$$
Hence
$$
\lambda_1=2|E|\inf_f\dfrac{\sum_{u\sim v}(f(u)-f(v))^2}{\sum_{u\sim v}(f(u)-f(v))^2\deg u\deg v}.
$$
We can iterate the formula of *Rayleigh quotient* to get
$$
\lambda_k=\inf_{f\perp T \cdot V_k}\dfrac{\sum_{u\sim v}(f(u)-f(v))^2}{\sum_v f(v)^2\deg v}.
$$
Here $V_k=\mathrm{span}\{\oplus_{i=0}^{k-1}x_k\}$, where $x_k$ is the $k$-th eigenvector (notice that $\mathcal L$ is *diagonalisable*). 

##### Spectrum of $\mathcal L$

For $K_{m,n}$, $P_n$, $C_n$, how to evaluate their eigenvalues and corresponding eigenvectors? Hint: using *Chebyshev polynomials* to evaluate the spectra of path and circles, deducing the corresponding eigenvectors by multiplying $(\alpha,\alpha^2,\ldots,\alpha^n)$. 

As for graphs in general, some basic facts (bounds of eigenvalues) includes:

* $\sum_{i}\lambda_i\leq n$, with equality holds $\Leftrightarrow $ $G$ has no isolated points $\Leftrightarrow $ trace no less than $n$. Therefore, $\lambda_1\leq\dfrac{n}{n-1}\leq \lambda_{n-1}$. 
* $\lambda_1\leq 1$ when $G$ is not complete (why?).
* $\lambda\leq\sup_f\dfrac{\sum_{u\sim v}(f(u)-f(v))^2}{\sum_u f(u)^2\deg u}\leq\dfrac{2\sum_{u\sim v}(f(u)^2+f(v)^2)}{\sum_u f(u)^2\deg u}\leq 2$. 

The equality in the last statement holds some non-trivial case. For instance, the following statements are equivalent (Hint: proof of connected case is sufficient enough; consider the eigen function $\mathbb 1_A\cdot f(x)-\mathbb 1_B\cdot f(x)$ for any bipartite with consisting part $A$ and $B$):

1. $G$ is bipartite.
2. $\lambda_{n-j}=2$ if $G$ has $i+1$ connected components.
3. For each $\lambda_i$, the value $2-\lambda_i$ is also an eigenvalue of $G$. 

(Spectrum bounded by diameter and volume) Let $D$ denotes the *diametre*. For $f\perp T\mathbf 1$, let $v_M$ be a vertex such that $|f(v_M)|=\max_v |f(v)|$. Since $\sum_v f(v)\deg v=0$, there exists a $u_0$ such that $f(u_0)f(v_0)<0$. Let $P_{u_0,v_0}$ be the shortest *path* that connects $u_0$ and $v_0$, i.e.
$$
v_0-v_1-\cdots- v_k= u_0.
$$
Hence,
$$
\begin{align*}
\lambda_1&=\dfrac{\sum_{u\sim v}(f(u)-f(v))^2}{\sum_u f(u)^2\deg u}\\
&\geq \dfrac{\sum_{i=1}^k(f(v_i)-f(v_{i-1}))^2}{f(v_0)^2\sum_u \deg u}\\
&\geq\dfrac{k\cdot\left(\dfrac{f(v_0)-f(v_k)}{k}\right)^2}{f(v_0)^2\sum_u \deg u}\\
&\geq\dfrac{1}{D\cdot\sum_u\deg u}
\end{align*}
$$
A pure corollary deriving from $\mathcal L(\sqrt Tf)=\lambda\sqrt T f$​ is 
$$
\lambda f(v)=\dfrac{1}{\deg v}\sum_{u\sim v}(f(u)-f(v))
$$

> Hint: Proof via $\mathcal L f=\lambda\sqrt Tf$. 

##### Spectrum of the weighted graphs

Denote $w$ as a function defining *edge weights*, i.e. 
$$
w:E\to\mathbb R,(u,v)\mapsto w(u,v).
$$
Here $w(u,v)=w(v,u)=w(e)$ is the weight of edge $e$ between $u$ and $v$. 

Thence $\deg v=\sum_{u}w(u,v)$. In many cases of applications, the graph may equip with *self-loops* (any examples?). The Laplacian matrix is revised to be
$$
L:=D-A=\left\{\begin{align*}
&\deg v-w(v,v)&&u=v,\\
&-w(u,v)&&u\sim v,\\
&0&&\text{else}.
\end{align*}\right.
$$
Hence
$$
\mathcal L:=\left\{\begin{align*}
&1-\dfrac{w(v,v)}{\deg v}&&u=v,\\
&-\dfrac{w(u,v)}{\sqrt{\deg v\cdot\deg u}}&&u\sim v,\\
&0&&\text{else}.
\end{align*}\right.
$$
Similarly, some above-mentioned theorems are re-stated as:

* Here $\mathcal L=D^{-1/2}LD^{-1/2}$, where $D^{\alpha}$ is defined as
  $$
  (\lambda_1^\alpha,\lambda_2^\alpha,\ldots,\lambda_k^\alpha,0,\ldots,0).
  $$

* For $f:V\to\mathbb R$, 
  $$
  Lf(v)=\sum_{u\sim v}(f(u)-f(v))w(u,v).
  $$
  Hence $\left< f,Lf\right>=\sum_{u\sim v}(f(u)-f(v))^2w(u,v)$. $\lambda_1$

* Question: How to determine $\lambda_k$?
