#### Statement of the original problem

For any hypercube $\mathbb Q_n\,(n\geq 2)$, there exists some **symmetric flips** of some $1$'s in the adjacency matrix $A(\mathbb Q_n)$ such that the spectral of $A(\mathbb Q_n)$ are $\pm\sqrt n$, that is, $\mathrm{spec}(A(\mathbb Q_n))=(\sqrt n^{(2^{n-1})},-\sqrt n^{(2^{n-1})})$ since $\mathrm{trace}(A)=0$. 

In 2019, H. Huang defined a sequence of symmetric square matrices iteratively as follows, which is highlighted in his [paper](https://arxiv.org/pdf/1907.00847.pdf): 
$$
A_1=\begin{pmatrix}0&1\\1&0\end{pmatrix},\quad A_{n+1}:=\begin{pmatrix}A_n&I\\I&-A_n\end{pmatrix}.
$$
Notice that the method of iterating above resembles the how Sylvester constructed the [Hadamard matrix](https://en.wikipedia.org/wiki/Hadamard_matrix) in 1867; whereas the number of flips in $A(\mathbb Q_n)$ still has room for reduction under such construction. For instance, via Huang's construction we have
$$
A_3 = \begin{pmatrix}
0&1&1&0&1&0&0&0\\
1&0&0&1&0&1&0&0\\
1&0&0&-1&0&0&1&0\\
0&1&-1&0&0&0&0&1\\
1&0&0&0&0&-1&-1&0\\
0&1&0&0&-1&0&0&-1\\
0&0&1&0&-1&0&0&1\\
0&0&0&1&0&-1&1&0\\
\end{pmatrix}.
$$
Here $4$ pairs of $1$'s flip, here $4$ is defined as the **flip index**. Actually, the flip index of signed matrix
$$
A_3' = \begin{pmatrix}
0&1&-1&0&1&0&0&0\\
1&0&0&1&0&1&0&0\\
-1&0&0&1&0&0&1&0\\
0&1&1&0&0&0&0&-1\\
1&0&0&0&0&-1&1&0\\
0&1&0&0&-1&0&0&1\\
0&0&1&0&1&0&0&1\\
0&0&0&-1&0&1&1&0\\
\end{pmatrix}
$$
is only $3$ (the **minimum flip index** of $\mathbb Q_3$ actually). 

In the main part of the manuscript, we shall discuss that:

* the equivalent statement of the original problem
* the minimum flip index of $\mathbb Q_n$

Since any signed matrix of $A(\mathbb Q_n)$ with column vectors $(q_1,q_2,\ldots, q_{2^n})$ is symmetric, the following statements are equivalent.
$$
\mathrm{spec}(\mathrm{sign}(A^2))=n\Leftrightarrow \left< q_i, q_j\right>=\delta_i^j\Leftrightarrow \dfrac{1}{\sqrt n}A \in O_{2^n}(\mathbb R).
$$

#### A short discussion of the main problem

For the case that $n\geq 3$, we shall prove the existence of signed matrix $\mathrm{sign}A(\mathbb Q_n)$ such that $\mathrm{sign}(A(\mathbb Q_n))$ consists of orthogonal column vectors. Let

* $v_1,\ldots, v_{2^n}$ be verteces of $\mathbb Q_n$.
* $u_1,\ldots,u_{2^n}$ be column vectors of $A(\mathbb Q_n)$ w.r.t. $v_i$'s.
* $w_1,\ldots,w_{2^n}$ be column vectors of some valid $\mathrm{sign}A(\mathbb Q_n)$ w.r.t. $v_i$'s.

Since $\left< u_i,u_j\right>\neq 0$ if and only if $N(u_i)\cap N(u_j)\neq 0$. When $i\neq j$, the following statements are equivalent:

* $N(u_i)\cap N(u_j)\neq 0$.
* $|N(u_i)\cap N(u_j)|=2$.
* $u_i$ and $u_j$ are adjoint in some $\mathbb Q_2$-subgraph in $\mathbb Q_n$. 

For each $\mathbb Q_2$-subgraph in $\mathbb Q_n$, the induced adjacency matrix is either $\pm A_2$ in the sense of *congruence*. As some $-1$ elements in $\mathrm{sign}(A)$ are signed, we *colour* the corresponding edges in $\mathbb Q_n$ (the remains are called *uncoloured*). We only need to prove that: 

> There exists a colouring of edges for $\mathbb Q_n$ such that every **$\mathbb Q_2$-subgraph** has odd number of edges coloured. 

Here, Huang's construction for $\mathrm{sign}(A(\mathbb Q_3))$ is given as follows:

<img src="https://files.mdnice.com/user/12571/b424c55a-d4ef-43bc-b2e7-4b85ca284a52.png" style="zoom:40%;" />

In order to seek for the minimal flip index, we only need to prove that:

> There exists a colouring of edges for $\mathbb Q_n$ such that every $\mathbb Q_2$-subgraph has **only one** edge coloured. 

For instance, one possible colouring of edges in $\mathbb Q_3$ with minimum flip index is given as follows.

<img src="https://files.mdnice.com/user/12571/5c05bd6a-a4b0-46d3-ae19-23735cf92af9.png" style="zoom:67%;" />

We define the **dimer** as the graph congruent to the *Chinese character* "日". The statement above equals that all $\mathbb Q_2$ subgraphs in $\mathbb Q_n$ has a perfect dimer covering, that is, a *complete* and *non-overlapping* covering. Therefore, the *mid-edges* of all dimers in a perfect covering establish an one-to-one correspondence to all coloured edges. For instance, the dimers $2437512$, $2687342$, $1268751$ perfectly covers the $\mathbb Q_3$ cube. 

We shall prove that such a covering exists for all $\mathbb Q_n$ for $n\geq 3$ via *Mathematical Induction*.

1. There is a perfect dimer covering for $\mathbb Q_3$. 
2. Assume that the statement is true for $n=k$. In order to prove that $\mathbb Q_{k+1}$ has a perfect dimer covering, we first perfectly cover the *inside and outside $\mathbb Q_k$ cubes* by assumption. Since the rest of $\mathbb Q_2$-subgraphs correspond the edges of $\mathbb Q_k$, we only need to prove that $\mathbb Q_k$ has a perfect *$P_2$ covering* on its edges, which equals that the **line graph** $L(\mathbb Q_n)$ has a perfect matching. Since every line graph is *claw-free*, the line graph of a connected graph with an even size has at least one perfect matching.

Hence the minimal flip index of $\mathbb Q_n$ is number of dimers in any perfect covering, that is, $n(n-1)(n-2)2^{n-4}$ for $n\geq 3$. 
