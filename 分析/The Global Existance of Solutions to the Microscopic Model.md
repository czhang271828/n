## The Global Existance of Solutions to the Microscopic Model

### Symbols and Definitions

1. $G(V,E)$ is a graph with vertex set $V$ and edge set $E$. 
2. The adjacency matrix of $E$ is denoted by $A=(a_{ij})_{n\times n}$, where $n:=|V|$.
3. The neighbour of node/vertex $i\in V$ is defined as $N(i):=\{j:j\sim i\}$.
4. The conductivity and length of edge $i\to j$ are denoted by $C_{ij}$ and $L_{ij}$ correspondingly, where $C_{ij}\geq0$ and $L_{ij}>0$.
5. The pressure of the vertex $i\in V$ is denoted by $P_i$. Thus we can define the pressure drop $(\Delta P)_{ij}:=P_j-P_i$ by definition.
6. The flow rate of an oriented flux in $i\to j$ is denoted by $Q_{ij}:=\dfrac{C_{ij}(\Delta P)_{ij}}{L_{ij}}$. 
7. The strength of $i$, denoted by $S_i$, is defined as the negative summation of $Q_{ij}$ for all $j\in N(i)$.
8. $H^k(\Omega):= W^{k,2}(\Omega)$ is a kind of Соболев space, that is, the subset of functions $f$  in $L^2(\Omega)$ such that $f$ and its weak derivatives up to order $k$ have a finite $L^2$ norm.
9. $H_0^1(\Omega)$ is a subset of functions $g$ in $H^1(\Omega)$ such that $g$ has a compact support on $\Omega$.

***

### Formulae

1. Kirchhoff's first law is that the algebraic sum of currents in a network of conductors meeting at a point (or node) is zero. Thus
   $$
   S_i=\sum_{j\in N(i)}C_{ij}\dfrac{(\Delta P)_{ji}}{L_{ij}}=-\sum_{j\in N(i)}C_{ij}\dfrac{(\Delta P)_{ij}}{L_{ij}}
   $$

2. The global mass conservation reveals that
   $$
   \sum_{i\in V}S_i=0
   $$

3. The Joule’s law illustrates that the kinetic energy is in proportion to both pressure drop and flow rate. Thus 
   $$
   \mathcal E_1[C_{ij}]:=(\Delta P)_{ij}Q_{ij}=\dfrac{Q_{ij}^2}{C_{ij}}L_{ij}
   $$

4. The metabolic consumption (in energy form) is in proportion to its length and a power of its conductivity. Thus
   $$
   \mathcal E_2[C_{ij}]:=\dfrac{\nu}{\gamma}C_{ij}^\gamma L_{ij}
   $$

5. The entire energy consumption functional is given by
   $$
   \tilde{\mathcal E}[C]:=\sum_{(i,j)\in E}\left(\dfrac{Q_{ij}^2}{C_{ij}}+\dfrac{\nu}{\gamma}C_{ij}^\gamma\right)L_{ij}
   $$

***

### Analysis of Discrete Model

#### The gradient of energy consumption functional w.r.t. $C_{ij}$.

We notice that $Q=Q[C]$, while $\nu$ and $L_{ij}$ is independent from $C_{ij}$. The partial derivetive of $\tilde{\mathcal E}[C]$ 
$$
\begin{align*}
\dfrac{\partial}{\partial C_{ij}}\tilde{\mathcal E}[C]:=&\dfrac{\partial}{\partial C_{ij}}\sum_{(i,j)\in E}\left(\dfrac{Q_{ij}^2}{C_{ij}}+\dfrac{\nu}{\gamma}C_{ij}^\gamma\right)L_{ij}\\
:=&\nu C_{ij}^{\gamma-1}L_{ij}-\dfrac{Q_{ij}^2}{C_{ij}^2}L_{ij}+2\sum_{(i,j)\in E}\dfrac{Q_{ij}}{C_{ij}}\dfrac{\partial Q_{ij}}{\partial C_{ij}}L_{ij}
\end{align*}
$$
We notice that $S_i$ are fixed constants. Hence
$$
\begin{aligned}
2 \sum_{(i, j) \in E} \frac{Q_{i j}}{C_{i j}} \frac{\partial Q_{i j}}{\partial C_{k l}} L_{i j} &=\sum_{i=1}^{n} \sum_{j=1}^{n} a_{i j}\left(\frac{P_{j}-P_{i}}{L_{i j}} \frac{\partial Q_{i j}}{\partial C_{k l}}\right) L_{i j} \\
&=\sum_{j=1}^{n} P_{j} \sum_{i=1}^{n} a_{i j} \frac{\partial Q_{i j}}{\partial C_{k l}}-\sum_{i=1}^{n} P_{i} \sum_{j=1}^{n} a_{i j} \frac{\partial Q_{i j}}{\partial C_{k l}} \\
&=-2 \sum_{i=1}^{n} P_{i} \sum_{j=1}^{n} a_{i j} \frac{\partial Q_{i j}}{\partial C_{k l}} \\
&=-2 \sum_{i=1}^{n} P_{i} \frac{\partial}{\partial C_{k l}} \sum_{j \in N(i)} Q_{i j}\\
&=-2 \sum_{i=1}^{n} P_{i} \frac{\partial}{\partial C_{k l}} S_i\\
&=0
\end{aligned}
$$
Thus we deduce the gradient
$$
\nabla\tilde{\mathcal E}[C]=\left(\cdots,\nu C_{ij}^{\gamma-1}L_{ij}-\dfrac{Q_{ij}^2}{C_{ij}^2}L_{ij},\cdots\right)
$$

#### The gradient descent flow

In general case, the gradient flow is introduced to find the decreasing streamline. Let $f:\mathbb R^n\to\mathbb R$ be a differentiable function with a given initial point $(x_0,f(x_0))$. There exists a streamline $\eta(x,t)$ such that $\eta(x,t)=f\circ x(t)$ descends when $t$ is increasing.

The general formulation of a gradient flow of the functional $\tilde{\mathcal E}\circ C(t)$ is of the form
$$
\dfrac{\mathrm d C}{\mathrm d t}=- \mathcal H[C]\cdot\nabla\tilde{\mathcal E}[C]
$$
We denote the space of tanent and cotangent vectors at $C\in\mathcal C$ by $\mathcal T_C\mathcal C$ and$\mathcal T^*_C\mathcal C$ respectively. Therefore $\mathcal H[C]$ can be regarded as a duality map 
$$
\mathcal H[C]:\mathcal T^*_C\mathcal C\to\mathcal T_C\mathcal C
$$
For any positive difinite duality map $\mathcal H[C]$, we have
$$
\dfrac{\mathrm d\tilde{\mathcal E}[C]}{\mathrm dt}= \nabla\tilde{\mathcal E}[C]\cdot\dfrac{\mathrm dC}{\mathrm dt}=\left <\nabla\tilde{\mathcal E}[C],\nabla\tilde{\mathcal E}[C]\right>_{\mathcal H[C]}<0
$$
which implies the dissipation of the energy along the solutions to gradient of energy consumption functional coupled with the Kirchhoff law.

The gradient flow of energy function coupled with the Kirchhoff law with respect to the unweighted Euclidean distance is given by the identical map $\mathcal H$. Thus
$$
\dfrac{\mathrm dC}{\mathrm dt}=-\nabla\tilde{\mathcal E[C]}
$$
Based on this general formulation, we consider the gradient flow with respect to a weighted Euclidean distance and introduce a duality map resulting in the ODE system, given by
$$
\mathcal H[C]=\mathcal H_1[C]\otimes\cdots\otimes\mathcal H_{|E|}[C]
$$
Here
$$
\mathcal H_{ij}[C]:\partial_{C_{ij}}|_{C}\mapsto C_{ij}^\alpha \cdot d C_{ij}
$$
Thus
$$
\dfrac{\mathrm dC_{ij}}{\mathrm dt}=\left(\dfrac{Q_{ij}}{C_{ij}^2}L_{ij}-\nu C_{ij}^{\gamma}L_{ij}\right)C_{ij}^{\alpha-1}
$$

#### The non-singularity of $\tilde C$

The global existance of the solutions hinges on the the non-singularity of the Kirchhoff matrix $\tilde C'$. Consider the matrix $\tilde C$ such that $\tilde C\cdot\mathbf P=\mathbf S$, where
$$
\tilde C\cdot\mathbf P=\mathbf S\Leftrightarrow
\begin{pmatrix}
\sum_{j\neq1}\dfrac{C_{1j}}{L_{1j}}&-\dfrac{C_{12}}{L_{12}}&\cdots&-\dfrac{C_{1n}}{L_{1n}}\\
-\dfrac{C_{21}}{L_{21}}&\sum_{j\neq2}\dfrac{C_{2j}}{L_{2j}}&\cdots&-\dfrac{C_{2n}}{L_{2n}}\\
\vdots&\ddots&\ddots&\vdots\\
-\dfrac{C_{n1}}{L_{n1}}&\cdots&-\dfrac{C_{n\,n-1}}{L_{n\,n-1}}&\sum_{j\neq n}\dfrac{C_{nj}}{L_{nj}}
\end{pmatrix}
\begin{pmatrix}
P_1\\P_2\\\vdots\\P_n
\end{pmatrix}=
\begin{pmatrix}
S_1\\S_2\\\vdots\\S_n
\end{pmatrix}
$$
Given that the all-one vector space is a trivial kernel of $\tilde C$, we shall consider the array-deleted matrix $C'$, i.e.
$$
\tilde C':=\begin{pmatrix}
\sum_{j\neq2}\dfrac{C_{2j}}{L_{2j}}&-\dfrac{C_{23}}{L_{23}}&\cdots&-\dfrac{C_{2n}}{L_{2n}}\\
-\dfrac{C_{32}}{L_{32}}&\sum_{j\neq3}\dfrac{C_{3j}}{L_{3j}}&\cdots&-\dfrac{C_{3n}}{L_{3n}}\\
\vdots&\ddots&\ddots&\vdots\\
-\dfrac{C_{n2}}{L_{n2}}&\cdots&-\dfrac{C_{n\,n-1}}{L_{n\,n-1}}&\sum_{j\neq n}\dfrac{C_{nj}}{L_{nj}}
\end{pmatrix}
$$
which seems promising to be non-singular.

Theorem. The matrix $A$ is non-singulat if $A$ is weakly diagonally dominant and irreducable.

* $A$ is reducable iff the graph with respect to $A$ is connected. An equivalnet statement states that there exists a permutation matrix $P$ such that 
  $$
  P^{-1}AP=P^TAP=
  \begin{pmatrix}
  A_1&A_2\\O&A_3\\
  \end{pmatrix}
  $$

* $A$ weakly diagonally dominant iff there for all diagonal element $a_{ii}$ the inequality $|a_{ii}|\geq\sum_{j\neq i}|a_{ij}|$ holds, among which at least one of the equalities do not hold.

*Proof.* For contradiction, suppose that $\det A=0$, then $\dim\ker A\geq 1$, i.e. there exists a non zero vector $v=(v_1,\ldots,v_{n})$ such that $Av=0$. We define $Y$ by 
$$
Y:\{k:\inf_{i}|v_i|<|v_k|=\|v\|_\infty\}
$$

1. If $Y$ is empty, then $|v_i|-|v_j|\equiv0$. Thus for any $k$
   $$
   |a_{kk}||v_k|=|\sum_{l\neq k}a_{kl}v_l|\leq\sum_{l\neq k}|a_{kl}||v_l|
   $$
   Thus $|a_{kk}|\leq\sum_{l\neq k}|a_{kl}|$, which contradicts the weakly diagonally dominance of $A$.

2. When $Y$ is non-empty. Notice that 
   $$
   |a_{kk}|\leq\sum_{j\neq k} |a_{kl}|\dfrac{|v_l|}{|v_k|}
   $$
   and 
   $$
   |a_{kk}|\geq\sum_{j\neq k} |a_{kl}|
   $$
   Thus for all $i\in Y$ and $j\notin Y$, we have $a_{ij}= 0$, which contradicts the reducability of $A$.

The proof is completed and thence we shall shift to the proof of connectivity of $C$ and the non-vanishment of all $C_{ij}\in C$. The proof of the global existance of solutions to the formulae
$$
\dfrac{\mathrm dC_{ij}}{\mathrm dt}=\left(\dfrac{Q_{ij}}{C_{ij}^2}L_{ij}-\nu C_{ij}^{\gamma}L_{ij}\right)C_{ij}^{\alpha-1}L_{ij}
$$
is presented below.

#### The global existance of $C_{ij}(t)$

We shall proof the global existance of the ODE system
$$
\dfrac{\mathrm dC_{ij}}{\mathrm dt}=\left(\dfrac{Q_{ij}}{C_{ij}^2}L_{ij}-\nu C_{ij}^{\gamma}L_{ij}\right)C_{ij}^{\alpha-1}L_{ij}
$$
coupled with the Kirchhoff law. Firstly we notice that the graph generated by all non-zero initial datum of $C_{ij}(t_0)$ is connected. WLOG assume $t_0=0$, then we shall prove that $0<C_{ij}(t)<F_{ij}(t)$ on $\mathbb R_+$, where $F_{ij}(t)$ is a continuous dominance function defined on $(0,\infty)$. Here $\alpha\in\mathbb R$, $\gamma>0$ and $\gamma+\alpha-1>0$.

If $\alpha+\gamma\geq 2$, then
$$
\dfrac{\mathrm dC_{ij}}{\mathrm d t}\geq-\nu L_{ij}C_{ij}^{\gamma+\alpha-1}
$$
Since the exponent $\gamma+\alpha-1\geq1$ and $C_{ij}(0)>0$, the solution of $C_{ij}(t)$ remains positive for all $t>0$. Moreover, $C_{ij}(t)$ remains bounded since the dissipation of the energy along the solutions.

If $\alpha+\gamma\in(1,2)$, then we can divide $V$ in to $V_1$ and $V_2$ such that the sources and sinks induce a net flux between them. We shall prove that the connections between $V_1$ and $V_2$ maintains along the corresponding solutions.

Let $\tilde E$ be the set of edges connecting $V_1$ and $V_2$. By definition of $V_1$ and $V_2$, we have
$$
\Delta S:=\sum_{i\in V_1}S_i=-\sum_{j\in V_2}S_j\neq 0
$$
Assume that $\sum_{(i,j)\in\tilde E}C_{ij}(t_0)>0$. We shall prove that
$$
\sum_{(i,j)\in\tilde E}C_{ij}(t)>0,\quad\forall t>t_0
$$
In light of the local existance of the solutions of $C$, we suppose that there exists $T>t_0$ such that
$$
\lim_{t\to T^-}\sum_{(i,j)\in\tilde E}C_{ij}(t)=0
$$
for contradiction. Since $\alpha-2< 0$ and $\gamma+\alpha-1>0$, for all $t\in(t_0,T)$ we have
$$
\begin{align*}
\dfrac{\mathrm d}{\mathrm d t}\sum_{(i,j)\in\tilde E}C_{ij}(t)=&\sum_{(i,j)\in\tilde E}(Q_{ij}^2C_{ij}^{\alpha-2}-\nu C_{ij}^{\gamma+\alpha-1})L_{ij}\\
=&\sum_{(i,j)\in\tilde E}Q_{ij}^2C_{ij}^{\alpha-2}L_{ij}-\sum_{(i,j)\in\tilde E}\nu C_{ij}^{\gamma+\alpha-1}L_{ij}\\
\geq&\left(\sum_{(i,j)\in\tilde E}C_{ij}\right)^{\alpha-2}\sum_{(i,j)\in\tilde E}Q_{ij}^2L_{ij}-\left(\sum_{(i,j)\in\tilde E}C_{ij}\right)^{\gamma+\alpha-1}\sum_{(i,j)\in\tilde E}\nu L_{ij}\\
\end{align*}
$$
Since
$$
\begin{align*}
\sum_{(i,j)\in\tilde E}Q_{ij}^2L_{ij}&\geq\sum_{(i,j)\in\tilde E}Q_{ij}^2\inf_{(i,j)\in\tilde E}L_{ij}\\
&\geq\dfrac{|\Delta S|^2}{|\tilde E|}\inf_{(i,j)\in\tilde E}L_{ij}
\end{align*}
$$
Denote $\sum_{(i,j)\in\tilde E}C_{ij}(t)$ by $u(t)$. We have
$$
\begin{align*}
\dfrac{1}{|\tilde E|}\dfrac{\mathrm d}{\mathrm d t}u(t)\geq&u^{\alpha-2}(t)\cdot\dfrac{|\Delta S|^2}{|\tilde E|}\inf_{(i,j)\in\tilde E}L_{ij}-u^{\gamma+\alpha-1}(t)\sum_{(i,j)\in\tilde E}\nu L_{ij}\\
\overset{\mbox{def}}{=}&u^{\alpha-2}(t)A+u^{\alpha+\gamma-1}(t)B
\end{align*}
$$
Here $A$ and $B$ are positive constants.

Since the derivation of $u(t)$ remains positive when $t$ is large enough, the minimum of $u$ is $\min(\{u(t_0)\}\cup\{u(t):u'(t)=0\})=\min\{u(t_0),\sqrt[\gamma+1]{A/B}\}>0$, which contradicts the assumption that $\lim_{t\to T^-}\sum_{(i,j)\in\tilde E}C_{ij}(t)=0$.

If $V$ can be partitioned into two balanced subgraphs $V_1$ and $V_j$, then we can continue to deduct separately for each of the subgraphs (until the eventual step). 

Via the graph partirioning method above, we deduce the global existence of the solutions. 

## Analysis of the Macroscopic Model

### The energy consumption functional  on $\mathbb R^d$

For all $i\in V$, denote the left and right neighbours of vertex  $i$ on the $k$-th spatial dimension (if exist) by $(i-1)_k$ and $(i-1)_k$ respectively. Thus the Kirchhoff law is then written as
$$
-\sum_{k=1}^dC_{(i-1)_k,i}\dfrac{(\Delta P)_{(i-1)_k,i}}{L_{(i-1)_k,i}}-C_{i,(i+1)_k}\dfrac{(\Delta P)_{i,(i+1)_k}}{L_{i,(i+1)_k}}=S_i
$$
When the points in the set $V$ are arranged as a set of parallelotopes or rectangular tessellation, that is, with the equal length $h_k$ to the left or right neighbour with respect to the $k$-th spatial dimension. The Kirchhoff law is written as
$$
-\sum_{k=1}^dC_{(i-1)_k,i}\dfrac{(\Delta P)_{(i-1)_k,i}}{h_k}-C_{i,(i+1)_k}\dfrac{(\Delta P)_{i,(i+1)_k}}{h_k}=S_i
$$
In the rescaling of the energy functional, some (abstract) weights are applied to scale linearly with the grid spacing, i.e.
$$
\tilde{\mathcal E}[C]=\sum_{(i,j)\in E}\left(\dfrac{Q_{ij}^2}{C_{ij}}+\dfrac{\nu}{\gamma}C_{ij}^\gamma\right)W_{ij}^{(d)}
$$
Via the deduction of the gradient of energy consumption functional as shown above, we conclude that the formal gradient flow (with respect to the Euclidean distance) of the energy functional constrained by the rescaled Kirchhoff law is of the type, i.e.
$$
\dfrac{\mathrm d C_{ij}}{\mathrm d t}=\left(\dfrac{Q_{ij}^2}{C^2_{ij}}+\nu C_{ij}^{\gamma-1}\right)W_{ij}^{(d)}
$$
if and only if all the weights $W_{ij}^{(d)}$ are equal. Here one of the natural way to choose $W_{ij}^{(d)}$ is letting $W_{ij}^{(d)}\equiv W^{(d)}=\prod_{k=1}^d h_k^{(d)}$. 

### The Discrete Approximation of the Poisson Equation

One can notice that the Kirchhoff law is a finite difference discretization of the Poisson equation per se. Furthermore, the approximation is the Riemann sum of the integral-type funcitonal. 

Consider the solution $p(x)$ of the Poisson equation
$$
-\nabla\cdot(c\nabla p)=S
$$
Here $c=\mbox{diag }(c_1,c_2,\cdots,c_d)$ is a diagonal permeabwhility tensor field with scalar non-negative functions $c_k\in C(\Omega)$. The global mass balance lies that
$$
\int_{\partial \Omega}S(x)\mathrm dx=0
$$
We as ssume that the solution $p(x)$ is at least $C^2$ on $\Omega$ and $c$ are $C^1$ on $\Omega$. Since $c(x)=\mbox{diag }(c_1,c_2,\ldots,c_n)$ is diagonal, the finite difference approximation of $S$ is
$$
\begin{align*}
S=&-\nabla \cdot(c\nabla p)\\
=&-\sum_{k=1}^d\partial_{x_k} (c_k\partial_{x_k}p)\\
=&-\sum_{k=1}^d\dfrac{c_k(x_{(i+1/2)_k})\partial_{x_k}p(x_{(i+1/2)_k})-c_k(x_{(i-1/2)_k})\partial_{x_k}p(x_{(i-1/2)_k})}{h^{(d)}_k}+O(h^{(d)}_k)\\
=&-\sum_{k=1}^d\dfrac{c_k{(x_{(i+1/2)_k})}\cdot\dfrac{p(x_{(i+1)_k})-p(x_{(i)_k})}{h^{(d)}_k}-c_k{(x_{(i-1/2)_k})}\cdot\dfrac{p(x_{(i)_k})-p(x_{(i-1)_k})}{h^{(d)}_k}}{h^{(d)}_k}+O(h^{(d)}_k)\\
=&\cdots\\
=&-\sum_{k=1}^dC_{(i-1)_k,i}\dfrac{(\Delta P)_{(i-1)_k,i}}{L_{(i-1)_k,i}}-C_{i,(i+1)_k}\dfrac{(\Delta P)_{i,(i+1)_k}}{L_{i,(i+1)_k}}+O(h^{(d)}_k)
\end{align*}
$$
When we equal ${c_k(x_{(i\pm 1/2)_k})}$ with $C_{i,(i\pm1)_k}$, $S_i$ with $S(X_i)$, $P_i$ with $p(X_i)$ and $P_{i\pm1}$ with $p(X_{i\pm 1})$, the rescaled Kirchhoff's law is concluded to be the discrete approximation of the Poisson function.

Moreover, we can estimate
$$
\int_\Omega |c_k|^\gamma\mathrm dx=W^{(d)}\sum_{i\in V}|c_k(X_{(i+1/2)_k})|^\gamma+O(h^{(d)}_k)
$$
and
$$
\int_\Omega c_k(\partial_{x_k}p)^2\mathrm dx=W^{(d)}\sum_{i\in V}c_k(X_{(i+1/2)_k})\left(\dfrac{p(X_{(i+1)_k})-p(X_i)}{h^{(d)}_k}\right)^2+O(h^{(d)}_k)
$$
Thus the energy functional with respect to rectangular grid parallelotopes can be written as
$$
\tilde{\mathcal E}[C]=\dfrac{1}{2}\sum_{k=1}^d\sum_{i\in V}\sum_{j\in N(i;k)}\left(\dfrac{Q_{ij}^2[C]}{C_{ij}}+\dfrac{\nu}{\gamma}C_{ij}^\gamma\right)h_k^{(d)}
$$
Here $N(i;k)$ denotes $N(i)\cap\{(i\pm1)_k\}$, that is, the neighbour in the $k$th spatial dimension.

Via the notation we applied in the discrete approximation, we have
$$
\tilde{\mathcal E}[C]+O(W^{(d)})=\mathcal E[c]=\int_\Omega\nabla p\cdot c\nabla p+\dfrac{\nu}{\gamma}|c|^\gamma\mathrm dx
$$
Here $|c|:=\sum_{k=1}^d|c_k|^\gamma$.

### The formal $L^2$ -Gradient Flow of the Energy

In retrospect to how we have deducted $\dfrac{\mathrm dC}{\mathrm dt}$, we shall estimate the the formal $L^2$-gradient flow of the continuum energy functional coupled with the Poisson equation. The relation between the discrete and continuum model is presented below.
$$
\begin{matrix}
\tilde{\mathcal E}[C]&+&\text{Kirchhoff law}&\Rightarrow&\text{gradient flow in the discrete model}\\
\updownarrow& &\updownarrow& &\updownarrow\\
\mathcal E[c]&+&\text{Poisson equation}&\Rightarrow&\text{ $L^2$ -gradient flow in the continuum model}
\end{matrix}
$$
Let $\phi=\mbox{diag }(\phi_1,\phi_2,\ldots,\phi_n)$ be a diagonal matrix, and $\varepsilon$ is arbitrarily small. 

Via the expansion $p[c+\varepsilon \phi]=p_0+\varepsilon p_1+O(\varepsilon^2)$


$$
\dfrac{\mathrm d\mathcal E[c+\varepsilon\phi]}{\mathrm d\varepsilon}\mid_{\varepsilon=0}=\sum_{k=1}^d\int_\Omega(\partial_{x_k}p_0)^2\phi_k+2c_k(\partial_{x_k}p_0)(\partial_{x_k} p_1)+\nu|c_k|^{\gamma-2}c_k\phi_k\mathrm dx
$$

Multiplicating the Poisson equation with permeability tensor $c+\varepsilon\phi$ by $p_0$ and integrating by parts, we have
$$
\sum_{k=1}^ d\int_\Omega(c_k+\varepsilon\phi_k)(\partial_{x_k} p_0)^2+\varepsilon c_k(\partial_{x_k}p_0)(\partial _{x_k}p_1)\mathrm dx=\int_\Omega Sp_0\mathrm dx+O(\varepsilon^2)
$$
Thus
$$
\begin{align*}
O(\varepsilon^2)=&\sum_{k=1}^ d\int_\Omega(c_k+\varepsilon\phi_k)(\partial_{x_k} p_0)^2+\varepsilon c_k(\partial_{x_k}p_0)(\partial _{x_k}p_1)\mathrm dx-\int_\Omega Sp_0\mathrm dx\\
=&\sum_{k=1}^ d\int_\Omega\varepsilon\phi_k(\partial_{x_k} p_0)^2+\varepsilon c_k(\partial_{x_k}p_0)(\partial _{x_k}p_1)\mathrm dx+\left[\int_\Omega c_k(\partial_{x_k} p_0)^2-Sp_0\mathrm dx\right]\\
=&\varepsilon\sum_{k=1}^ d\int_\Omega\phi_k(\partial_{x_k} p_0)^2+c_k(\partial_{x_k}p_0)(\partial _{x_k}p_1)\mathrm dx\\
\end{align*}
$$
Let $\varepsilon\to 0$, We obtain the identity 
$$
\sum_{k=1}^ d\int_\Omega\phi_k(\partial_{x_k} p_0)^2+c_k(\partial_{x_k}p_0)(\partial _{x_k}p_1)\mathrm dx=0
$$
Thus
$$
\begin{align*}
\dfrac{\mathrm d\mathcal E[c+\varepsilon\phi]}{\mathrm d\varepsilon}\mid_{\varepsilon=0}=&\sum_{k=1}^d\int_\Omega(\partial_{x_k}p_0)^2\phi_k+2c_k(\partial_{x_k}p_0)(\partial_{x_k} p_1)+\nu|c_k|^{\gamma-2}c_k\phi_k\mathrm dx\\
=&\sum_{k=1}^d\int_\Omega-(\partial_{x_k}p_0)^2\phi_k+\nu|c_k|^{\gamma-2}c_k\phi_k\mathrm dx\\
=&\sum_{k=1}^d\int_\Omega\left[-(\partial_{x_k}p_0)^2+\nu|c_k|^{\gamma-2}c_k\right]\phi_k\mathrm dx\\
\end{align*}
$$
Thus we  deduce that
$$
\partial_t c_k=(\partial_{x_k} p)^2-\nu|c_k|^{\gamma-2}c_k
$$
In the previous part, we discuss the gradient flow with respect to rectangular parallelotopes. In fact the coordinate transform $\mathcal T: e_k\to f_k$  leads to the transformed continuum energy functional
$$
E[c]=\int_\Omega\nabla p^T\cdot\mathbb T[c]\cdot\nabla p+\dfrac{\nu}{\gamma}|c|^\gamma\mathrm dx
$$
coupled with the transformed Poisson equation
$$
-\nabla\cdot\left[\mathbb T[c]\cdot\nabla p\right]=S
$$
Here we define the permeability tensor $\mathbb T[c]:=\sum_{k=1}^dc_k f_k\otimes f_k$.

Thus
$$
\partial_t c_k=(f_k\cdot\nabla p)^2-\nu|c_k|^{\gamma-2}c_k
$$

### Global existence of Solutions of a Modified Macroscopic Model

#### The establishment of the full PDE system

We notice that the Poisson function suffers from two drawbacks. One is that the diagonal of the tensor $c(x)$ might vanish, while the other one is that the random fluctuations can ill be neglected. 

1. To tackle with the first obstakle we rewirte the permeability tensor with a prescribed function that models the isotropic background permeability of the medium, i.e. $\mathbb T[c]:=r\mathbb I+c$ with $r(x)\geq r_0>0$, where $\mathbb I$ is the unit matrix with dimension $d$. The PDE $-\nabla\cdot(\mathbb T[c]\nabla p)=S$ remains elliptic iff diagonal of $c(x)$ are non-negative. 

2. As for the amendment of random fluctuations term, a linear diffusive term is introduced to model the random fluctuations in the medium. Let $D^2>0$ be the constant diffusivity, we thus obtain
   $$
   \partial_t c_k=D^2\nabla^2 c_k+\nabla p^T\cdot (f_k\otimes f_k)\cdot\nabla p-\nu|c_k|^{\gamma-2}c_k
   $$

Since
$$
\dfrac{D^2}{2}\nabla (c+\varepsilon\phi)^T\cdot\nabla (c+\varepsilon\phi)-\dfrac{D^2}{2}\nabla c^T\cdot\nabla c=\varepsilon D^2\nabla c^T\cdot\nabla \phi+O(\varepsilon^2)
$$
We deduce the amended formal $L^2$-gradient flow of the energy functional

$$
\mathcal E[c]=\int_\Omega\dfrac{D^2}{2}|\nabla c|^2+\nabla p^T\cdot\mathbb T[c]\nabla p+\dfrac{\nu}{\gamma}|c|^{\gamma}\mathrm dx
$$

Here $|\nabla c|:=\nabla c^T\cdot\nabla c=\sum_{k=1}^d\partial_{x_k}c_k$.

The PDE system
$$
\begin{align*}
\partial_t c_k&=D^2\nabla^2 c_k+|f_k\cdot\nabla p|^2-\nu|c_k|^{\gamma-2}c_k\\
S&=-\nabla\cdot(\mathbb T[c]\nabla p)\\
\mathbb T[c]&=c+r\mathbb I
\end{align*}
$$
subject to homogeneous Dirichlet boundary boundary conditions for $c$ and no-flux boundary conditions for $p$. Thus for all $x\in\partial\Omega$ and $t>0$
$$
c(t,x)\equiv 0,\quad\partial_{n}p(t,x)\equiv 0
$$
The initial datum $c_0(x):=c(0,x)$ is a diagonal tensor field with non-negative diagonal elements.

#### Global existence of the weak solutions

The estimation of weak solutions of
$$
\begin{align*}
\partial_t c_k&=D^2\nabla^2 c_k+|f_k\cdot\nabla p|^2-\nu|c_k|^{\gamma-2}c_k\\
S&=-\nabla\cdot(\mathbb T[c]\nabla p)\\
\mathbb T[c]&=c+r\mathbb I
\end{align*}
$$
is not supposed to be included in this report. From the research of , we admits a global weak solution $(c,p)$ satisfying
$$
\begin{align*}
c&\in L^\infty(0,\infty;H_0^1(\Omega))\cap L^\infty(0,\infty;L^\gamma(\Omega))\\
\partial_t c&\in L^2((0,\infty)\times\Omega)\\
\nabla p&\in L^\infty(0,\infty;L^2(\Omega))\\
c\nabla p&\in L^\infty(0,\infty;L^2(\Omega))
\end{align*}
$$
for $S\in L^2(\Omega)$ and $c_0(x)\in H_0^1(\Omega)^{d\times d}\cap L^\gamma(\Omega)^{d\times d}$. While the regularized energy functional satisfied
$$
\mathcal E'[c(t)]=\mathcal E'[c_0]+\sum_{k=1}^d\int_0^t\int_\Omega\left(\partial_t c_k(s,x)\right)^2\mathrm dx\mathrm ds
$$
for all $t\in(0,\infty)$.



Acknowledgement





This report mainly summarise two models of biological transport networks, the discrete (microscopic) one and the cotinuum (macroscopic) one. The analysis of global existence of solutions in the first discrete model (ODE model) provides the theoritical interpretation of optimisation of biological networks. In order to establish the continuous model (PDE model), central difference method is applied. Due to the drawbacks of  uncorrected macroscopic model, diffusion and perturbation including random fluctuations are also taken into consideration. The global existence of solutions in the PDE model is mentioned yet not fully illustrated at the final part of the report.

Abstract 

Over the seminar in this semester, our group presented a brief introduction to transprot networks based on the research of our instructor Dan Hu, whose theories of adaption and optimisation of Biological Transport Networks is highlighted throughout our presentations.

In pevious presentations, Yang introduced the heuristic discover of networks build by Physarum, drawing forth the research of mathematical model of transport networks. Hereafter, the index of material consumption $\gamma$ was discussed to characterise the node structure of optimised networks by Tang, where structures of loops were highly underlined. In light of this, Zou analysed how the damage and fluctuations induce loops in optimal transport networks. The systematic theories of modeling is introduced by Ye. Subsequent numerical analysis including solvability of Kirchoff equation, Lagrange conditional  extrema, redundancy were individually analysed by Guo. The final presentation of mine was mainly about a macroscopic and continuum model deduced by the previous model in Ye's presentation. The analysis of global existence of solutions was also mentioned. 
$$
\begin{align*}
S=&-\nabla \cdot(c\nabla p)\\
=&-\sum_{k=1}^d\partial_{x_k} (c_k\partial_{x_k}p)\\
=&-\sum_{k=1}^d\left(\dfrac{c_k(x_{(i+1/2)_k})\partial_{x_k}p(x_{(i+1/2)_k})}{h^{(d)}_k}\right.\\
&\quad \left.\dfrac{-c_k(x_{(i-1/2)_k})\partial_{x_k}p(x_{(i-1/2)_k})}{h^{(d)}_k}\right)+O(h^{(d)}_k)\\
=&-\sum_{k=1}^d\left(\dfrac{c_k{(x_{(i+1/2)_k})}\cdot\dfrac{p(x_{(i+1)_k})-p(x_{(i)_k})}{h^{(d)}_k}}{h^{(d)}_k}\right.\\
&\left.\dfrac{-c_k{(x_{(i-1/2)_k})}\cdot\dfrac{p(x_{(i)_k})-p(x_{(i-1)_k})}{h^{(d)}_k}}{h^{(d)}_k}\right)+O(h^{(d)}_k)\\
=&\cdots\\
=&-\sum_{k=1}^dC_{(i-1)_k,i}\dfrac{(\Delta P)_{(i-1)_k,i}}{L_{(i-1)_k,i}}-C_{i,(i+1)_k}\dfrac{(\Delta P)_{i,(i+1)_k}}{L_{i,(i+1)_k}}+O(h^{(d)}_k)
\end{align*}
$$
