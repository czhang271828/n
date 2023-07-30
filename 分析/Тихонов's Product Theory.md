# Тихонов's Product Theory

### A Straightforward Proof

**The Main Theorem.** Let $(X_i)_{i\in I}$ be a family of compact spaces. Then the product space $\prod_{i\in I}X_i$ is compact. Here **A9** is admitted when necessary. 

**Proof.** For the sake of contradiction, assume there exists a family of open subsets $\mathcal U$ covers $\prod_{i\in I}X_i$ with no finite subcovers. We denote $\prod_{i\in J}X_i=:X_J$. 

**Step 1.** Let $\pi_{I_0}:X_I\to X_{I_0}$ be a **projection map** for $I_0\subset I$. The transitive map is defined as
$$
\pi_{I_1,I_2}:=\pi_{I_1}^{-1}\circ \pi_{I_2}:X_{I_1}\to X_{I_2}.
$$
The transitive map is well defined when $I_2\subset I_1\subset I$. Let $(P,\subset )$ denotes pratially ordered set of all $X_J$ ($J\subset I$).

**Step 2.** We call $p\in X_J\in P$ a **bad point** whenever for each neighbourhood $U_p$ of $p$, no finite subsets of $\mathcal U$ cover $\pi_{J}^{-1}(U_p)$ . When $p$ and $q$ are in disjoint $X_{I_1}$ and $X_{I_2}$ ($I_1\cap I_2=\emptyset $), we defind $p\lor q$ as a concatenation. 

**Step 3.** Let $\mathbf B$ denote the set of all bad points, define $p,q\leqq p\lor q$ in $\mathbf B$. We claim that $\mathbf B$ is *downward closed* for $\leqq$, that is, $q\in \mathbf B$ implies $p\in \mathbf B$ for each $p\leqq q$. (It seems trivial , **Ex1**). $\mathbf B$ is non-empty since $\emptyset \in\mathbf B$ by assumption ($X_I$ has no finite subcover). 

**Step 4.** Let $p\in X_J\in P$ be a bad point with $J\subsetneq I$. We claim that for each $i_J\in I\setminus J$, there exists $a\in X_{\{i_J\}}$ such that $p\lor a\in \mathbf B$. 

Assume that $p\lor a\notin \mathbf B$ for each $a\in X_{\{i_J\}}$. Then there exists a neighbourhood $V_{p\lor a}$ such that $\pi^{-1}_{J\cup \{i_J\}}(V_{p\lor a})$ can be covered by a finite subset $\mathcal U'\subset \mathcal U$. Without the loss of generality, let $V_{p\lor a}=O_{p}\times W_a\in X_J\times X_{\{i_J\}}$. Since $X_{\{i_J\}}$ is compact, one can find $\{a_k\}_{k=1}^N\in X_{\{i_J\}}$ such that $X_{\{i_J\}}=\cup_{k=1}^N W_{a_k}$, $O_p=\cap_{k=1}^N O_{p,a_k}$. Then 
$$
\pi^{-1}_J(O_p)=\cup_{k=1}^N\pi^{-1}_{J\cup\{j_I\}}(O_p\times W_a)\subset \cup_{i=1}^N\pi^{-1}_{J\cup\{i_J\}}(V_{a_k}).
$$
As a result, $\pi_J^{-1}(O_p)$ can be covered by finite many subsets in  $\mathcal U$, which contradicts $p\in\mathbf B$. 

**Step 5.** We shall show that each chain $\mathbf C$ in $\mathbf B$ has an upper bound in $\mathbf B$. Indeed, $\lor \mathbf C:=\lor \{q\mid q\in \mathbf C\}$ is well defined, we shall show that $(\lor \mathbf C)\subset  \mathbf B$. Denote $\{p\}:=\lor\mathbf C$. 

Let $V$ be any neighbourhood of $p\in X_J$. By definition of product topology, we assume that $V=\pi^{-1}_{J,F}(W)$ where $F\subset J$ is finite and $W$ is open in $X_F$. One can find $q_0\in\mathbf C$ such that $p|_F\leqq q_0 $, which implies that $p|_F\in\mathbf B$. As a result, $\pi_F^{-1}(W)=\pi^{-1}_J(V)$ cannot be covered by finitely many subsets in $\mathcal U$. Therefore, $p\in \mathbf B$. 

**Step 6.** In light of Zorn's lemma, there exists $p\in X_I$ such that $p\in\mathbf B$ by **Step 5.**, that is, $p$ cannot be covered by finite subfamily of opensets in $\mathcal U$. 

$\square$

**Remark.** Main idea of proof: define the set of bad points $\mathbf B$ (non-empty) and utilise the Zorn's lemma to deduce the maximum of $\mathbf B$, thus leads to a contradiction.

<div style="page-break-after: always"></div>

### Critical graphs are finite graphs

**Definiton 1.** We call $G=G(V,E)$ a **simple graph** whenenver $V$ is a set and $E\subset \{\{x,y\}\mid x,y\in V,x\neq y\}$. Here $V$ (or $E$) is the set of vertices (or edges).

Simple graph is always *unweighted, undirected, without self-loops and multi-edges*. 

**Definition 2.** Let $G$ be a simple graph. $G$ is **$k$-colourable on vertices** whenever there exists a function $f\in \{1,2,\ldots, k\}^V$ s.t. $f(x)\neq f(y)$ when $\{x,y\}\in E$. 

**Definition 3.** The **minimal number for vertex colouring** is the minimal positive integer $k_\min=:\chi(G)$, such that $G$ is $k_\min$-colourable on vertices. 

**Definition 4.** The **vertex-deleted graphs** of $G$ are in the form of
$$
G_{x_0}(V',E'):=G_{x_0}(\{x\in V\mid x\neq x_0\},\{\{x,y\}\in E\mid x,y\neq x_0\}).
$$
Informally speaking, $G_{x_0}$ is obtained from $G$ by deleting $x_0$ and all edges connecting to it.

**Definition 5.** We call a simple graph $G$ **critical** whenever $\chi (G)<\infty$ and
$$
\sup_{x\in G}\chi(G_x)=\max_{x\in G}\chi(G_x) <\chi(G).
$$

**Main problem.** Proves that **all critical graphs are finite graphs**, that is, $|V|<\infty$ for each critical graph $G(V,E)$. 

> The *axiom of chioce* is required when necessary. 

The main problem is a straight corollary of the following **marvelous theorem**.

**De Bruijn–Erdős theorem.** Let $G(V,E)$ be a infinite graph, that is, $|V|\geq|\mathbb N|$. If $\chi(F)\leq k$ for each finite subgraph $F$ in $G$, then $\chi(G)\leq k$. 

**Proof.** Let $S=\{1,2,\ldots ,k\}$, $X=k^{V(G)}$ be the product topology space $(X,\tau)$. Let $\mathcal F\subset\tau $ denotes all possible schemes of colouring of every finite subgraphs in $G$. Then $\mathcal F$ consists of closed sets in $(X,\tau)$ and each finite subset in $\mathcal F$ has non-empty intersection. Since $k^{V(G)}$ is compact, $\cap \mathcal F$ is nonempty (by **FICC.**). 

$\square$

**Finite intersection criterion of compact sets (FICC).** Let $X$ be a compact topology space, $\mathcal F$ be a familiy of closed subsets of $X$. Then $\cap\mathcal F\neq\empty$ whenever each finite subfamily of $\mathcal F$ has non-empty intersection.

**Proof.** It is just the opposite of Heine-Borel covering theorem, which is trivial.

$\square$ 

### Hall's marriage theorem

**Hall's marriage theorem (oral edition).** $V_1$ 表示 A 性别的光棍, $V_2$ 表示 B 性别的光棍, 然而只有特定的人才有结婚的可能性, 例如 $u\in V_1$ 与 $v\in V_2$ 可结婚若且仅若 $u$ 与 $v$ 存在连边. 记 $V_1$ 与 $V_2$ 之间的连边构成集合 $E$. 实际上, 常称简单图 $G(V_1\dot\cup V_2,E)$ 为二部图 (bipartite graph). 对任意 $S\subset V_1$, 记
$$
\Gamma(S)=\{v\in V_2\mid uv\in E\text{ for some }u\in V_1\}\subset V_2.
$$
即所有留有 $S$ 中 A 性别的光棍可生成的结婚证之最大集合 (商掉时间与效力等属性, 例如一个人可以有多张证). 则 A 性别的光棍可以脱单若且仅若 $|\Gamma(S)|\geq |S|$ 对一切 $S\in\mathcal P(V_1)$ 恒成立.

**Proof.** Finite case. When $V_1$ is finite, we assume $S_2$ is finite without the loss of generality. Then we shall analysis the following two cases.

**Case I.** Suppose that for all proper subspace $S\neq \empty$ of $V_1$, $|\Gamma(S)|\geq |S|+1$. Then for arbitrary $e=uv\in E$, the vertex-deleted graph $G_{u,v}$ still satisfies Hall's condition.

**Case II** Suppose that for some proper subset $S_0\neq \empty$ of $V_1$, $|\Gamma(S_0)|=|S_0|$. Then the induces subgraph $G(S_0\dot\cup\Gamma(S_0))$ and $G((V_1\setminus S_0)\dot\cup (V_1\setminus \Gamma(S_0)))$ satisfies Hall's condition. 

> Either is trivial, or is trivial.

Trivial by mathematical induction. 

Infinite case (The Тихонов's Product Theory is required, left as **Ex2**). 

$\square$ 