# 图谱论讲稿 I(修改稿)

### 会议中未解决的问题

**Q1** 正则图补图的特征多项式?

**A1** 设$G$为度为$k$的正则图, 顶点数为$n$. 由于$\overline G$度为$n-k$, 故$\lambda_1(\overline G)=n-k$, 相应的特征向量为$\mathbf 1$. 若$\lambda_i x_i=A(G)x_i$, 则
$$
(J-I-A)x_1=\mathbf 1\mathbf 1^Tx_i-(\lambda_i+1)x_i=-(\lambda_i+1)x_i.
$$
故$P_{\overline G}(x)=P_G(-x-1)\cdot \dfrac{(-1)^n(x-n+k+1)}{x+k+1}$. 

将结论用于join graph, 则
$$
P_{G_1\bigtriangledown G_2}(x)=\dfrac{P_{G_1}(x)P_{G_2}(x)}{(x-k_1)(x-k_2)}[(x-k_1)(x-k_2)-n_1n_2].
$$
**Q2** 称$G$为Cartesian product可分解的, 若且仅若存在非平凡图$G_1,G_2$使得$G_1\square G_2=G$. 试寻找例子以说明Cartesian product可分解的图不一定存在唯一的最小分解. 

**A2** 等价于说明非负整系数多项式环非UFD. 注意到
$$
(x^3+1)(x^2+x+1)=(x+1)(x^4+x^2+1).
$$
对图$G$​, 定义$G^1=G$, $G^n=G\square G^{n-1}$, 则
$$
(G^3\dot\cup K_1)\square (G^2\dot\cup G\dot\cup K_1)=(G\dot\cup K_1)\square (G^4\dot\cup G^2\dot\cup K_1).
$$
不妨取$G=P_2=Q_1$为$1$维超立方体, 下证明$(G^3\dot\cup K_1)$非Cartesian product可分解: 注意到$(G^3\dot\cup K_1)$顶点数为$9$且不连通, 显然无法成为两个不连通$3$-顶点图之Cartesian product. 同理, $(G^2\dot\cup G\dot\cup K_1)$之顶点数为质数, 显然不可Cartesian product分解. 

**Q3** 给定$A(G)$与$A(G-j)$的谱(邻接矩阵未知), 试计算$A(G)$中特征值$\lambda_j$对应的特征向量$x^j$中第$k$项分量之模长, 即$x^j_k$. 此处需假定$A(G)$之谱无重根. 

**A3** 注意到$P_{G-j}(x)$为$\mathrm{adj}(xI-A)$的$j,j$项余子式, 设$\mathbf 1^j$为第$j$项为$1$而其余项为$0$的向量, 则
$$
\begin{align*}
P_{G-j}(x)=&(\mathbf 1^j)^T\mathrm{adj}(xI-A)\mathbf 1^j\\
=&P_G(x)(\mathbf 1^j)^T(xI-A)^{-1}\mathbf 1^j\\
=&P_G(x)(\mathbf 1^j)^T\left(\sum_i\dfrac{1}{x-\lambda_i}P_i\right)\mathbf 1^j\\
=&P_G(x)e_i^T\left(\sum_i\dfrac{E_i}{x-\lambda_i}\right)e_i\\
=&P_G(x)\sum_i\dfrac{\alpha_{ij}^2}{x-\lambda_i}
\end{align*}
$$
代入$x=\lambda_k$​, 则
$$
P_{G-j}(\lambda_k)=\alpha_{jk}^2\prod_{i\neq k}(\lambda_k-\lambda_i).
$$
此处
$$
|x_k^j|^2=\alpha_{jk}^2=\dfrac{\prod_{i\neq k}(\lambda_k-\lambda_j)}{\prod_{\mu\in\mathrm{Spec}(G-j)}(\lambda_k-\mu)}.
$$

***

### Angle Matrix of a Graph 

##### $\alpha_{ij}$, the angle

For any simple graph $G(V,E)$ with neither directions, multiple edges, loops $G(V,E)$, the adjacency matrix $A=A(G)$ is symmetric. In light of the *polar decomposition*, we have
$$
A=Q^T\Lambda Q=\sum_{i=1}^r \lambda_i\cdot P_i=\sum_{i=1}^r \lambda_i\cdot Q^TE_iQ
$$
where $\lambda_1>\lambda_2>\cdots>\lambda_r$, $O_n(\mathbb R)\ni Q=(x_1,x_2,\ldots, x_n)$. 

* $\alpha_{ij}:\|E_ix_j\|=\sqrt{x^T_jE_ix_j}$ denotes the $ij$-th *angle*, that is, the $i$-th index of eigenvector $x_j$. The *angle matrix* is given by $(\alpha_{ij})_{r\times n}$. 
* $\sum_{i=1}^r\alpha_{ij}^2=\sum_{i}x_j^TE_ix_j=x_j^TIx_j=1$.
* $\sum_{j=1}^n\alpha_{ij}^2=\sum_{j}x_j^TE_ix_j=\mathrm{trace}(Q^TE_iQ)=\dim\mathscr E_{\lambda_i}$. Here $\mathscr E_{\lambda_i}$ denotes the root space of $\lambda_i$. 

##### $\beta_i$, the main angle

The *main angle* $\beta_i$ is defined as $\dfrac{\|P_i\cdot\mathbf 1_n\|}{\sqrt n}$. Hence
$$
\sum_i\beta_i^2=\dfrac{\mathbf 1^T I\mathbf 1}{n}=1.
$$

For any polynomial $P(x)$ which is well-defined on the ring $R$ and matrix ring $\mathscr M(n, R)$, we notice that $P_iP_j=O$ for any $i\neq j$. Hence we deduce that
$$
P(A)=\sum_{i}P(\lambda_i)P_i
$$
with the corollary
$$
\mathbf 1^TP(A)\mathbf 1=n\sum_{i}P(\lambda_i)\beta_i^2.
$$
Further more, the polynomial $P$ can be replaced by *some function* once its convergence is determined.

***

### Operation, Modification&Compositions of Graphs

##### Basic Graph Operations

Simple operations:

* The *disjoint union* $G_1\dot\cup G_2$. 
* The *complement* $\overline G$.
* The *join* $G_1\bigtriangledown G_2:=\overline{\overline{G_1}\dot\cup\overline{G_2}}$.
* The *vertex-deleted graph* $G-j$. 
* The *pendant-added* graph $G_j$.
* The *coalescence* $G_u\cdot H_v$, or $G\cdot H$ for short, w.r.t. $u\in V(G)$, $v\in V(H)$. 
* The *bridged graph* $GuvH$. 

Some special operations: 

* The *corona* $G\circ H$.
* The *subdivision* graph $S(G)$.
* The *line graph* $L(G)$. 

*NEPS(*non-complete extended $p$-sum) operations.

##### Characteristic Polynomials under the Modifications

For *disjoint union*, we have
$$
P_{G_1\dot\cup G_2}(x)=P_{G_1}(x)P_{G_2}(x).
$$
Further more, for any finite graph set $\{G_i\}_{i=1}^m$ we have
$$
P_{\dot\cup\{G_i\}_{i=1}^m}(x)=\prod _{i=1}^mP_{G_i}(x).
$$
For *complement*, we have 
$$
\begin{align*}
P_{\overline G}(x)=&\det(xI-J+I+A)\\
=&\det((x+1)I+A)-\mathbf 1^T\mathrm{adj}((x+1)I+A)\mathbf 1\\
=&(-1)^nP_G(-x-1)(1-\mathbf 1^T((x+1)I+A)^{-1}\mathbf 1)\\
=&(-1)^nP_G(-x-1)\left(1-n\sum_{i=1}^r\dfrac{\beta_i^2}{x+1+\lambda_i}\right)
\end{align*}
$$

> Lemma (UNNECESSARY). $\det(A+ uv^T)=\det(A)+v^T\mathrm{adj}(A)u$.
>
> Proof of the lemma. Since
> $$
> \left|\begin{matrix}
> 1&v^T\\\mathbf 0&A+uv^T
> \end{matrix}\right|=\left|\begin{matrix}
> 1&v^T\\\mathbf -u&A
> \end{matrix}\right|=\left|\begin{matrix}
> 1+v^TA^{-1}u&v^T\\0&A
> \end{matrix}\right|
> $$
> Q.E.D.

For *join*, we have
$$
\begin{align*}
P_{\overline {G_1\dot\cup G_2}}(x)=&(-1)^{n_1+n_2}P_{G_1\dot\cup G_2}(-x-1)\left(1-(n_1+n_2)\sum_{i=1}^s\dfrac{\beta_i^2}{x+1+\lambda_i}\right)\\
&(-1)^{n_1+n_2}P_{G_1\dot\cup G_2}(-x-1)\left(1-n_1\sum_{i=1}^s\dfrac{(\beta_i^{(1)})^2}{x+1+\lambda_i}-n_2\sum_{i=1}^s\dfrac{(\beta_i^{(2)})^2}{x+1+\lambda_i}\right)\\
=&-(-1)^{n_1+n_2}P_{G_1\dot\cup G_2}(-x-1)\\
&+(-1)^{n_1+n_2}P_{G_1\dot\cup G_2}(-x-1)\left(1-n_1\sum_{i=1}^s\dfrac{(\beta_i^{(1)})^2}{x+1+\lambda_i}\right)\\
&+(-1)^{n_1+n_2}P_{G_1\dot\cup G_2}(-x-1)\left(1-n_2\sum_{i=1}^s\dfrac{(\beta_i^{(2)})^2}{x+1+\lambda_i}\right)\\
=&(-1)^{n_2}P_{\overline {G_1}}(x)P_{G_2}(-x-1)+(-1)^{n_1}P_{\overline {G_2}}(x)P_{G_1}(-x-1)\\
&-(-1)^{n_1+n_2}P_{G_1\dot\cup G_2}(-x-1)
\end{align*}.
$$

Hence
$$
\begin{align*}
&P_{G_1\bigtriangledown G_2}(x)+(-1)^{n_1+n_2}P_{G_1\dot\cup G_2}(-x-1)\\=&(-1)^{n_2}P_{\overline {G_1}}(x)P_{G_2}(-x-1)+(-1)^{n_1}P_{\overline {G_2}}(x)P_{G_1}(-x-1)
\end{align*}.
$$
We deduce that
$$
P_{G_1\bigtriangledown G_2}(x)=P_{G_1}(x)P_{G_2}(x)\left(1-n_1n_2\sum_{i=1}^{r_1}\sum_{j=1}^{r_2}\dfrac{(\beta_i^{(1)}\beta_j^{(2)})^2}{(x-\lambda_i^{(1)})(x-\lambda_j^{(2)})}\right).
$$

##### Characteristic Polynomials under the Compositions

For *vertex-deleted graph* $G-j$, $P_{G-j}(x)$ is the $j$-th diagonal element of $\mathrm{adj}(xI-A)$. Since
$$
\mathrm{adj}(xI-A)=P_G(x)(xI-A)^{-1}=P_G(x)\sum_{i=1}^r\dfrac{P_i}{x-\lambda_i}
$$
we deduce that $\displaystyle{P_{G-j}(x)=P_G(x)\sum_{i=1}^r\dfrac{\alpha_{ij}^2}{x-\lambda_i}}$. 

For the *pendant-added graph* $G_j$, we notice that
$$
P_{G_j}(x)=xP_G(x)-P_{G-j}(x).
$$
Hence $\displaystyle{\displaystyle{P_{G_j}(x)=P_G(x)\left(x-\sum_{i=1}^r\dfrac{\alpha_{ij}^2}{x-\lambda_i}\right)}}$. 

For *coalescence* $G\cdot H$ in which $u\in G$ and $v\in H$, we have
$$
\begin{align*}
P_{G\cdot H}(x)=&\left|\begin{matrix}
xI-A'&-r&O\\-r^T&x&-s^T\\O&-s&xI-B'
\end{matrix}\right|\\
=&\left|\begin{matrix}
xI-A'&-r&O\\-r^T&x&-s^T\\O&\mathbf 0&xI-B'
\end{matrix}\right|+\left|\begin{matrix}
xI-A'&\mathbf 0&O\\-r^T&x&-s^T\\O&-s&xI-B'
\end{matrix}\right|\\
&-\left|\begin{matrix}
xI-A'&\mathbf 0&O\\-r^T&x&-s^T\\O&\mathbf 0&xI-B'
\end{matrix}\right|\\
=&P_G(x)P_{H-v}(x)+P_{G-u}(x)P_H(x)-xP_{G-u}(x)P_{H-v}(x)
\end{align*}.
$$
For the *bridged graph* $GuvH$, we have 
$$
\begin{align*}
P_{GuvH}(x)&=P_{G_u}(x)P_{H-v}(x)+P_G(x)P_H(x)-xP_G(x)P_{H-v}(x)\\
&=P_G(x)P_H(x)-P_{G-u}(x)P_{H-v}(x)
\end{align*}
$$
For *corona graph* $G\circ H$, we have 
$$
\begin{align*}
P_{G\circ H}(x)=&\det\left|\begin{matrix}xI-A&-J_1&-J_2&\cdots&-J_n\\-J_1^T&xI-B\\-J_2^T& &xI-B\\\vdots& & &\ddots\\-J_n^T& & & & xI-B\end{matrix}\right|\\
=&\det\left|\begin{matrix}xI-A-\dfrac{m}{x-r}I&-J_1&-J_2&\cdots&-J_n\\\mathbf0&xI-B\\\mathbf 0& &xI-B\\\vdots& & &\ddots\\\mathbf 0& & & & xI-B\end{matrix}\right|\\
=&P_G\left(x-\dfrac{m}{x-r}\right)(P_H(x))^n\\
\end{align*}
$$
where $n=|V(G)|$. 

For *subdivision graph*, we can notice that $A(S(G))=\begin{pmatrix}O&B^T\\B&O\end{pmatrix}$. Here $B$ denotes the *induced graph* (from edges to vertices). Hence
$$
P_{S(G)}(x)=x^{|E|-|V|}Q_G(x^2)
$$
where $Q_G(x)$ denotes the characteristic polynomial of *signless Laplacian* $BB^T=A+D$. 

For *line graph* $L(G)$, the characteristic polynomial is given by
$$
P_{L(G)}(x)=(x+2)^{|E|-|V|}(x)Q_G(x+2).
$$

##### NEPS(non-complete extended $p$-sum)

The *NEPS* is a multiple operation of a set of graph via a given tuple $\mathcal B\subset\{0,1\}^n\setminus\{0\}^n$, e.g. $\{G_i\}_{i=1}^n$. It outcomes $\mathrm{NEPS}(\{G_i\}_{i=1}^n,\mathcal B)$ satisfying:

* The vertices of the the outcome is the (classical) *Cartesian product*
  $$
  \prod_{i=1}^nV(G_i)=G_1\times\cdots\times G_n.
  $$

* The vertices $(x_1,\ldots,x_n)$ and $(y_1,\ldots, y_n)$ are adjacent if and only if there exists a $\beta\subset \mathcal B$ such that $\beta_i=0\Leftrightarrow x_i=y_i$ and $x_j\sim y_j\Leftrightarrow \beta_j=1$.

As for *Cartesian product* $G\square H$, $V(G\square H)\cong V(G)\times V(G)$, $(g_i,h_i)\sim (g_j,h_j)$ if either

* $g_1=g_2$ and $h_1\sim h_2$ in $H$, w.r.t. $(0,1)\in\mathcal B$.
* $h_1=h_2$ and $g_1\sim g_2$ in $G$, w.r.t. $(1,0)\in\mathcal B$.

<img src="https://files.mdnice.com/user/12571/95b7df3c-13f7-45d3-be6d-922edd90ca2b.png" style="zoom:25%;" />

It is trivial to verify that:

* $\square$ is commutative. 
* $\square$ is associative. 

that is, the associativity and commutativity.

As for *tensor product* $G\times H$, $V(G\times H)\cong V(G)\times V(H)$, $(g_i,h_i)\sim(g_j,h_j)$ if and only if $(g_i\sim g_j)\land (h_i\sim h_j)$, w.r.t. $\mathcal B=\{(1,1)\}$. 

<img src="https://files.mdnice.com/user/12571/76cc7ada-3382-4288-b2b8-07a288c9c748.png" style="zoom:25%;" />

The strong product $G\boxtimes H$, w.r.t. $\mathcal B=\{0,1\}^2-\{0,0\}$, etc. 

The adjacency matrix (trivial proof by definition) is
$$
A(\mathrm{NEPS}(\{G_i\}_{i=1}^n;\mathcal B))=\sum_{\beta\in\mathcal B}\otimes_{i=1}^n A(G_i)^{\beta_i}.
$$
Since $(A\otimes C)(B\otimes D)=(AC)\otimes(B D)$, the spectral outcome
$$
\sum_{\beta\in\mathcal B}\left(\prod _{i=1}^n {\lambda_i^{i_k}}^{\beta_i}\right)
$$
where $\lambda_i^{i_k}$ is the $k$-th eigenvalue of $G_i$ with corresponding eigenvalue $x_i^{i_k}$. Thus the eigen vector of $A(\mathrm{NEPS}(\{G_i\}_{i=1}^n;\mathcal B))$ is 
$$
\sum_{\beta\in\mathcal B}\otimes_{i=1}^n {x_i^{i_k}}.
$$

