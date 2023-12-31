# Furstenberg's Proof.

Assume you two are both familiar with *Ch 1* in 尤's book. Here is a super cool stuff I'd like to show: Furstenberg's proof of the infinitude of primes. 

**Problem.** Try to prove there are infinite primes in a super cool style. 

**Furstenberg's proof.** Define the topology on $\mathbb Z$, that is, open sets are generated by arithmetic sequences (in the form of $a\mathbb Z+b$). We denote
$$
S(a,b):=a\mathbb Z+b:=\{an+b\mid n\in\mathbb Z\}.
$$
Then $S(a,b)$ are both open and closed. 

Assume that prime numbers are finite. Then $\cup_{p\text{ is prime}}S(p,0)$ is a finite union of closed sets, thus closed. As a result, $\{\pm 1\}=\mathbb Z-\cup_{p\text{ is prime}}S(p,0)$ is open. This would be a contradiction!

***

Here is another thought-provoking problem we shall discuss in several days. 

> Definition 1-5 seems trivial yet referenced for the sake of rigor. 

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

***

**Problem.** Proves that **all critical graph is finite**, that is, $|V|<\infty$. 

The *axiom of chioce* is required when necessary. 