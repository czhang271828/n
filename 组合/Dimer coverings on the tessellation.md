# Dimer covering and Kasteleyn Matrix

<center>张陈成 519071910091</center>

***

### Introduction

In this article, we mainly discuss the dimer covering problems on the tessellation of squares and introduce the Kasteleyn matrix. One simple question is to determined the number of schemes to cover a chess board ($8\times 8$ square) with a collection of dimers ($1\times 2$ rectangles) without overlaps. The classical dimer covering problem is discussed in section I, which ends up with the approximation that the number of dimer configurations on $m\times n$ chess board reaches $e^{(G/\pi)mn}$. 

Some of the properties of Kasteleyn matrix is discussed in Section II. Our main goal is to evaluate the approximation of inverse Kasteleyn matrix. 

### The Classical Dimer Covering Problem

##### Counting the dimer configurations

Let $G_{m,n}$ denotes the number of schemes to cover the $m\times n$  board with non-overlapping dimers, equivalently, $G_{m,n}$ is the number of perfect matching on the $m\times n$ grid graph. We assume $m$ is multiple of $2$ and denotes $N$ as $\dfrac{mn}{2}$. 

One notice that such $m\times n$ grid graph is a bipartite, as is it shown in the chess board that each pair of squares (vertices in the graph) under the same colour is non-adjacent. Let $\mathscr W=\{W_k\}_{k=1}^N$, $\mathscr B=\{B_k\}_{k=1}^N$ be the set of white and black vertices respectively in the given $m\times n$ grid graph. We also make the graph directed under the following construction.

<img src="https://files.mdnice.com/user/12571/07fa58af-122e-4af8-a3a4-6babbd507af5.png" alt="img" style="zoom:33%;" />

Let $K$ be a $N\times N$​ matrix such that 
$$
k_{ij}=\left\{\begin{align*}
&+w(W_i,B_j),&&\text{if }W_i\to B_j,\\
&-w(W_i,B_j),&&\text{if }W_i\leftarrow B_j,\\
&0,&&\text{otherwise.}
\end{align*}\right.
$$
Here $w(W_i,B_j)$ is the weight of edge $W_i-B_j$ in the given grid graph. For simplicity (while giving consideration to phisical significance), we assume that all vertical edges are of the same weight, so are all horizontal edges. 

Let $E'$ be a subset of edges in the grid graph. Whenever $E'$ is a dimer configuration, there exists a permutation $\sigma\in S_N$ such that $E'=\{W_i,B_{\sigma(i)}\}_{i=1}^N$. One notices that
$$
\det K=\sum_{\sigma\in S_N}\mathrm{sgn}(\sigma)\prod_{i=1}^N k_{i,\sigma(i)},
$$
where $E'$ runs over all possible dimer configuartion. 

Under the given direction, we claim that for each dimer configuration $E'_1=\{W_i,B_{\sigma_1(i)}\}_{i=1}^N$ and $E'_2=\{W_i,B_{\sigma_2(i)}\}_{i=1}^N$, we have
$$
\mathrm{sgn}(\sigma_1)\prod_{i=1}^N \mathrm{sgn}(k_{i,\sigma_1(i)})=\mathrm{sgn}(\sigma_2)\prod_{i=1}^N \mathrm{sgn}(k_{i,\sigma_2(i)}).
$$
For simplicity, we assume all edges are weighted $1$ and to prove that
$$
\mathrm{sgn}(\sigma_1\sigma_2)\prod_{i=1}^N \mathrm{sgn}(k_{i,\sigma_1(i)}k_{i,\sigma_2(i)})=1.
$$
One notices the (adjoint) union of any two dimer configuration is the disjoint union of double edges and even circles. 

<img src="https://files.mdnice.com/user/12571/544c30b1-5591-4728-9e8a-4bfc8646a67d.png" alt="img" style="zoom:33%;" />

One notice that

* For each multiple edge $\{W_i,B_{\sigma_\ell(i)} \}_{\ell=1,2}$, we have $k_{i,\sigma_1(i)}=k_{i,\sigma_2(i)}$. 

* For each even loop with length $2l$, $\sigma_1^{-1}\circ \sigma_2$ restricted in this loop is a rotation with sign $(-1)^{l+1}$. One observe that each square contains exaxtly odd number of $B\to W$ edges. Thus the sign of the product of $k_{i,\sigma_1(i)}k_{i,\sigma_2(i)}$ equals the number of square inside the loop (the area under the curve) in the sense of modulus $2$. Since there are exactly even number of inner points in the loop, the picks's lemma illustrates that 
  $$
  \text{Area}=\text{Inner points}+\dfrac{\text{Boundary points}}{2}-1.
  $$
  Thus 
  $$
  \mathrm{sgn}(\sigma_1^{-1}|_c\circ \sigma_2|_c)\prod_{\text{some circle }  c}\mathrm{sgn}(k_{i,\sigma_1(i)}k_{i,\sigma_2(i)})\\
  =(-1)^{l+1}\cdot\mathrm{sgn}(\dfrac{2l}{2}-1)=1.
  $$

We conclude that for $w\equiv 1$, $|\det K|$ is the number of possible dimer configuration, i.e., $|\det K|=G_{m,n}$. 

##### Determinant of Kasteleyn matrix

Let $\delta_{k}^l$ be $0$ whence $l\neq k$, $\delta_l^l=1$ for each $l$ in the given index set. Thus 
$$
k_{(x_1,y_1),(x_2,y_2)}=(\delta_{x_1}^{x_2-1}-\delta_{x_1}^{x_2+1})\delta_{y_1}^{y_2}+(-1)^{x_1}(\delta_{y_1}^{y_2-1}-\delta_{y_1}^{y_2+1})\delta_{x_1}^{x_2}.
$$
One notices that $K$ is $\dfrac{mn}{2}\times \dfrac{mn}{2}$, we define the complement of $K$ as 
$$
\tilde K=\begin{pmatrix}O&K\\-K^T&O\end{pmatrix}.
$$
Here $|\det\tilde K|=|\det K|^2$. Let
$$
\begin{align*}
Q_{m\times m}&=(-1)^{x_1}(\delta_{x_1}^{x_2-1}-\delta_{x_1}^{x_2+1}),\\
R_{n\times n}&=(\delta_{y_1}^{y_2-1}-\delta_{y_1}^{y_2+1}),\\
S_{m\times m}&=\mathrm{diag}((-1)^{x_1}).
\end{align*}
$$
Then
$$
\tilde K=(S\otimes\mathbf 1_n)(z_1Q\otimes\mathbf 1_n+z_2\mathbf 1_m\otimes R). 
$$
Here $z_1$ and $z_2$ are the weight for horizontal and vertical weight, respectively. 

Via the knowledge of Чебышёв polynomials, it directly follows that the eigenvalues of $R$ and $Q$ are $\{2i\cos(\pi k/(n+1))\}_{k=1}^n$, $\{2\cos(\pi k/(m+1))\}_{k=1}^m$, respectively. Hence
$$
\begin{align*}
|\det \tilde K|&=\prod_{p=1}^n\prod_{q=1}^m|z_1\lambda_q(Q)+z_2\lambda_p(R)|\\
&=\prod_{p=1}^n\prod_{q=1}^{m/2}|(z_1\lambda_q(Q))^2-(z_2\lambda_p(R))^2|\\
&=2^{mn}\prod_{p=1}^n\prod_{q=1}^{m/2}|(z_1\cos\dfrac{\pi q}{m+1})^2+(z_2\cos\dfrac{\pi p}{n+1})^2|.\\
\end{align*}
$$
As a result, 
$$
\begin{align*}
&\quad \,\,G_{m,n}=|\det \tilde K|_{z_1=z_2=1}\\
&=2^{mn/2}\prod_{p=1}^n\prod_{q=1}^{m/2}\sqrt{\cos^2\dfrac{\pi q}{m+1}+\cos^2\dfrac{\pi p}{n+1}}.
\end{align*}
$$
The number for dimer configurations on a $8\times 8$ chess board is $12988816$. 

##### The approximation formula

Let $Z_{m,n}$ be $|\det(\tilde K)|$. We define the average free energy as 
$$
f(z_1,z_2):=\lim_{m,n\to\infty}\dfrac{1}{mn}\log Z_{m,n}.
$$
We shall prove such limit exists as $m,n\to\infty$. 

By definition of Riemann's integration, we have
$$
\begin{align*}
f(z_1,z_2)&=-\lim_{m,n\to\infty}\dfrac{\log 2^{mn/2}}{mn}\log\prod_{p=1}^n\prod_{q=1}^{m/2}\sqrt{(z_1\cos\dfrac{\pi q}{m+1})^2+(z_2\cos\dfrac{\pi p}{n+1})^2}\\
&=-\dfrac{1}{\pi^2}\int_0^{\pi/2}\mathrm d\theta\int_0^{\pi/2}\log[4(z_1^2\cos^2\theta+z_2^2\cos^2\phi)]\mathrm d\phi\\
&=-\dfrac{1}{\pi}\int_0^{\pi/2}\mathrm d\theta\left[\dfrac{1}{2}\log^2(2z_2\cos\theta)+\dfrac{1}{\pi}\int_0^{\pi/2}\log\left(1+\dfrac{\cos^2\phi}{(\frac{z_2}{z_1})^2\cos^2\theta}\right)\mathrm d\phi\right]\\
&=-\dfrac{1}{\pi}\int_0^{\pi/2}\mathrm d\theta\left[\log(2z_2\cos\theta)+\log\dfrac{1+\sqrt{1+\dfrac{z_1^2}{z_2^2\cos^2\theta}}}{2}\right]\\
&=-\dfrac{1}{\pi}\int_0^{\pi/2}\mathrm d\theta(\log z_1+\log(\frac{z_2}{z_1}\cos\theta+\sqrt{1+(\frac{z_2}{z_1})^2\cos^2\theta})\\
&=-\dfrac{1}{2}\log z_1
-\dfrac{1}{\pi}\int_0^{\pi/2}g(\frac{z_2}{z_1}\cos\theta)\mathrm d \theta.
\end{align*}
$$
Here 
$$
g(x)=\log(x+\sqrt{1+x^2})=\sum_{j=0}^\infty\binom{2j}{j}\dfrac{(-1)^j}{(2j+1)2^{2j}}x^{2j+1}.
$$
It follows that
$$
\begin{align*}
&\quad\,\,\int_0^{\pi/2}g(z_2/z_1\cos\theta)\mathrm d \theta\\
&=\sum_{j=0}^\infty\int_0^{\pi/2}\binom{2j}{j}\dfrac{(-1)^j(z_2/z_1)^{2j+1}}{(2j+1)2^{2j}}\cos^{2j+1}\theta\mathrm d\theta\\
&=\sum_{j=0}^\infty\dfrac{(-1)^j}{(2j+1)^2}(z_2/z_1)^{2j+1}\\
&=\int_0^{z_1/z_1}\dfrac{\arctan t}{t}\mathrm dt\\
&=\dfrac{1}{2i}(\mathrm{Li}_2(iz_1/z_2)-\mathrm{Li}_2(-iz_1/z_2)).
\end{align*}
$$
Especially, let $z_1=z_2=1$​, we deduce that
$$
f(1,1)=-\dfrac{1}{\pi}\int_0^1\dfrac{\arctan t}{t}-\mathrm dt=\dfrac{G}{\pi}.
$$
Here $G$ is the Catalan constant. 

### Dimer configuration on toroidal boundary conditions

Furthermore, one may consider the dimer covering problem under the toroidal boundary conditions, that is, the square chess board embedded into a torus with its opposite sides identified. 

The previous proof fails on the $m\times n$ torus torus, since two matchings may differ on a loop which goes around the torus, thus is not null-homologous. Indeed, the change of signs in $K$ from one dimer configuration to the other one is a function in $H_1(T,\mathbb Z/2\mathbb Z)$. 

In fact, we can obtain the desired result in the the following orientations:

![image-20220526195951136](https://s2.loli.net/2022/05/26/GQ7SiqxDYvHwRTc.png)

As shown in the previous section, some circles occurs in the union of any two dimer configurations. Here $\mathcal D_{++}$ gives perseves the sign of circles that homotopy to a single point, while fails to perserve the other cases. 

Let

* $Z_{00}$ denote the class of dimer configuration wrapping both the horizontal and vertical directions even number of times, 
* $Z_{10}$ denote those wrapping horizontal and vertical directions odd and even number of times respectively, 
* so are $Z_{01}$ and $Z_{11}$. 

Therefore, we have
$$
\left\{\begin{align*}
\det K_{++}&=Z_{00}-Z_{10}-Z_{01}-Z_{11},\\
\det K_{+-}&=Z_{00}-Z_{10}+Z_{01}+Z_{11},\\
\det K_{-+}&=Z_{00}+Z_{10}-Z_{01}+Z_{11},\\
\det K_{--}&=Z_{00}+Z_{10}+Z_{01}-Z_{11}.
\end{align*}\right.
$$
It yields that 
$$
\begin{align*}&\quad \,\,Z_{m,n}'=Z_{00}+Z_{01}+Z_{10}+Z_{11}\\
&=\dfrac{1}{2}(-\det K_{++}+\det K_{+-}+\det K_{--}+\det K_{++}).
\end{align*}
$$
It is also clear that $f(z_1,z_2)$ has the same limit as the planar case. 

### Height functions

The height function of a dimer configuration maps the vertices to $\mathbb Z$, which is uniquely defined by the following rules:

* When encircling in an black area counterclockwisely, the height ascends $1$ when the edge lies in the boundary of some dimer; descends $3$ otherwise.
* When encircling in an white area clockwisely, the height ascends $1$ when the edge lies in the boundary of some dimer; descends $3$ otherwise.
* Assume one given vertices is of zero height for reference. 

<img src="https://s2.loli.net/2022/05/26/rGC3e19x8BzotgV.png" alt="image-20220526204621116" style="zoom:33%;" />

Such function is well-defined for any possible scheme of dimer configuration. The height function on the boundary of the region is independent of the covering. One can see the boundary of $m\times n$ chess board is flat than that in a Aztec diamond, which leaves corners blank for some random dimer configurations. 

<img src="https://s2.loli.net/2022/05/26/eF1X6R9sNck2vPj.png" alt="image-20220526210035530" style="zoom:33%;" />

### The discrete analysis on dimer coverings

Under some subtle change in the previous proof, the number of dimer configurations on $m\times n$ square is the absolute value of the determinant of the adjacency matrix of the grid graph, where with horizontal edges weighted $1$ and vertical edges weighted $i(=\sqrt{-1})$. For instance, the adjacency matrix of the following weighted $2\times 3$ chess board is 

​                         $\small{A(G)=\begin{pmatrix}0&0&0&i&1&0\\0&0&0&1&i&1\\0&0&0&0&1&i\\i&1&0&0&0&0\\1&i&1&0&0&0\\0&1&i&0&0&0\\\end{pmatrix}}$       <img src="https://s2.loli.net/2022/05/27/BswDJn8f1vNq7Mr.png" alt="image-20220527142036661" style="zoom:33%;" />

We call such adjacency matrix the Kasteleyn matrix (denoted by $K$) thenceforth. 

##### $K$ as dirac operator

Since $K$ is the adjacency matrix of a bipartite, the $v_1,v_2$-th entry in $K^{-1}$ is zero whenever $v_1$ and $x_2$ has different colours. For any black vertex $w\in\mathscr W$, we define
$$
Kf:= f(w+1)-f(w-1)+i(f(w+i)-f(w-i)).
$$
Then $Kf\equiv 0$ whenever $(\partial _x +i\partial _y f)\equiv 0$. Here $\partial_x$ and $\partial_y$ are discrete derivatives, such $f$ is called as discrete analytic. 

One may observe that $K^\ast K$ is a Laplacian, i.e., 

![image-20220527143941516](C:\Users\czhan\AppData\Roaming\Typora\typora-user-images\image-20220527143941516.png)

As a consequence, $4f(b)=\sum_{\varepsilon =0}^3f(b+2 i^\varepsilon )$, which is called the discrete mean value theorem. 

The Green function is defined as $\Delta G(u,v)=\delta_u^v$. Since
$$
\Delta K^{-1}(w,\cdot)=K^\ast KK^{-1}(w,\cdot)=(K^\ast\delta_w)(\cdot)\\
=\overline {\sum_{\varepsilon=0}^3i^\varepsilon \delta_{w+i^\varepsilon}}=\sum_{\varepsilon=0}^3(-i)^\varepsilon \delta_{w+i^\varepsilon},
$$
$K^{-1}$ is the sum of $4$ Green functions. 

##### $K^{-1}$ on bounded domains

Let $2\epsilon \mathbb Z^2$ be the discrete approximations of a Jordan domain $\Omega$. Let $\Omega_\epsilon :=\epsilon \mathbb Z^2\cap \Omega$. The revised $\Omega_\epsilon '$ is obtained from $\Omega_\epsilon $ by deleting the black vertices in $\Omega_\epsilon$ lying in the outer face of $\Omega_{2\epsilon}$. Therefore, $\Omega_\epsilon$ has the same number of black and white vertices. 

> Other constructions can also be utilised while ensuring the discretisation of $\Omega$ has the same number of black and white vertices. 

Let $G(u,v)$ be the continuous Dirichlet Freen's function on $\Omega$, $\tilde G(u,\cdot)$ be the (analytic) complexification of $G(u,\cdot)$ such that $\mathrm{Re}(\tilde G(u,\cdot))=G(u,\cdot)$​. Then
$$
\begin{align*}
K^{-1}&=2\epsilon \mathrm d\tilde G(u,v)+o(\epsilon)\\
&=:\dfrac{1}{2}(F_0(u,v)\mathrm d u_x+iF_1(u,v)\mathrm du_y)\\
&=:\dfrac{1}{4}(F^+(u,v)\mathrm d u+F^-(u,v)\mathrm d\overline u).
\end{align*}
$$
Let $\mathscr B_0$ ($\mathscr B_1$) be the set black vertices with vertices in even (odd) coordinates, $\mathscr W_i$ be the $1$-grid shift vertically of $\mathscr B_i$ for $i=1,2$. Therefore, for $|w-b|\gg 1$ we have
$$
K^{-1}(w,b)=\left\{\begin{align*}
&\epsilon \cdot \mathrm{Re} F_0(w,b)+o(\epsilon)&& (w,b)\in \mathscr W_0\times \mathscr B_0,\\ 
&\epsilon \cdot i\mathrm{Im} F_0(w,b)+o(\epsilon)&& (w,b)\in \mathscr W_0\times \mathscr B_1,\\ 
&\epsilon \cdot \mathrm{Re} F_1(w,b)+o(\epsilon)&& (w,b)\in \mathscr W_1\times \mathscr B_0,\\ 
&\epsilon \cdot i\mathrm{Im} F_1(w,b)+o(\epsilon)&& (w,b)\in \mathscr W_1\times \mathscr B_1.
\end{align*}\right.
$$
For $w\in\mathscr W, b\in \mathscr B$ such that $|w-b|\gg \epsilon $, we shall compare the Green function on $\mathbb R^2$ (for instance), i.e., 
$$
\begin{align*}
\tilde G(u,v)&=-\dfrac{1}{2\pi}\log(v-u),\\ \mathrm d\tilde G(u,v)&=\dfrac{1}{2\pi}\dfrac{\mathrm du_x+i\mathrm du_y}{v-u}. 
\end{align*}
$$
Here $F_0=F_1=\dfrac{1}{\pi(v-u)}$. For the comformal mapping $\phi:U\to V$, then $\tilde G_V(u,v)=\tilde G_U(\phi(u),\phi(v))$. As a consequence, 
$$
\left\{\begin{align*}
F_V^+(u,v)&=F^+_U(\phi(u),\phi(v))\phi'(v),\\
F_V^-(u,v)&=F^-_U(\phi(u),\phi(v))\overline {\phi'(v)}.
\end{align*}\right.
$$
For instance, for rectangle we have $K^{-1}(v_1,v_2)=\sum \lambda_k^{-1}f_k(v_1)f_k(v_2)$. Here $K=\sum\lambda_k f_k\cdot f_k^T$ is the polar decomposition with orthonormalised eigenvectors $\{f_k\}$. Then
$$
\begin{align*}
K^{-1}(v_1,v_2)&=\sum_{s=1}^m\sum_{t=1}^n\dfrac{\sin \frac{\pi s \Delta x}{m+1}\cdot \sin\frac{\pi t\Delta y}{n+1}}{2\cos\frac{\pi s}{m+1}+2i\cos\frac{\pi t}{n+1}}\\
&=\dfrac{1}{4\pi^2}\iint_{S^1\times S^1}\dfrac{e^{i\Delta x\theta +i\Delta y \phi}}{2i\sin \theta-2\sin\phi}\mathrm d\theta\mathrm d\phi.
\end{align*}
$$
Here $(\Delta x,\Delta y)=(v_2-v_1)\in\mathbb Z^2$​. As a result, 
$$
K^{-1}(w,b)=\left\{\begin{align*}
& \mathrm{Re} \dfrac{1}{\pi(b-w)}+o(|b-w|^{-1})&& (w,b)\in \mathscr W_0\times \mathscr B_0,\\ 
&i\mathrm{Im} \dfrac{1}{\pi(b-w)}+o(|b-w|^{-1})&& (w,b)\in \mathscr W_0\times \mathscr B_1,\\ 
&\mathrm{Re} \dfrac{1}{\pi(w-b)}+o(|b-w|^{-1})&& (w,b)\in \mathscr W_1\times \mathscr B_0,\\ 
& i\mathrm{Im} \dfrac{1}{\pi(w-w)}+o(|b-w|^{-1})&& (w,b)\in \mathscr W_1\times \mathscr B_1.
\end{align*}\right.
$$
Which coincides the Schwarz-Christoffel transformation. 

### Reference

[Bou16] Cédric Boutillier. Around planar dimer models: *Schur processes and integrable statistical mechanics on isoradial graphs*. Habilitationà diriger des recherches, UPMC - Université Paris 6 Pierre et Marie Curie, December 2016.

[Ken03] Richard Kenyon. An introduction to the dimer model, 2003.

[SZ94] Horst Sachs and Holger Zernitz. Remark on the dimer problem. *Discrete Applied Mathematics*, 51(1):171–179, 1994.