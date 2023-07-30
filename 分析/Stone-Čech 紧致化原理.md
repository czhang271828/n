### Stone-Čech 紧致化原理

##### 极大滤子空间

全文默认 $X$ 为无限集. 回顾先前介绍滤子时给出极大滤子的若干性质:

1. 存在 (比某一给定 $\mathscr F_0$ 细的) 极大滤子. 
2. 对于极大滤子, 以下叙述等价: 
   1. $\mathscr F$ 为极大滤子,
   2. $\forall A,B\subset  X$, $A\cup B\in \mathscr F$ 推出 $A\in \mathscr F$ 或 $B\in\mathscr F$. 
   3. $\forall A\subset X$, $\{A,A^c\}\cap \mathscr F\neq\emptyset$.  
3. $\mathscr U$ 为 $X$ 上极大滤子, $\{A_i\}_{i=1}^N\subset \mathcal P(X)$ 使得 $\cup_{i=1}^N A_i\in\mathscr U$, 则存在一个 $A_j\in\mathscr U$. 
4. $\mathscr U$ 为极大滤子, 若 $A\subset X$ 与 $\mathscr U$ 中所有元素均有无空的交, 则 $A\in\mathscr U$. 
5. $(X,\tau)$ 为拓扑空间, 有以下等价叙述:
   1.  $(X,\tau)$ 为紧拓扑空间,
   2. $X$ 上一切极大滤子收敛,
   3. $\cap\{\overline A\mid A\in\mathscr F\}\neq \emptyset$, $\mathscr F$ 为任意给定的滤子. 

**Def.** 记 $\beta X$ 为 $X$ 上极大滤子所成的集合. 

**Def.** 记 $[A]:=\{\mathscr U\in \beta X\mid A\in \mathscr U\}$, 即一切包含 $A$ 的极大滤子. 函数为
$$
[\cdot]:\mathcal P(X)\to \mathcal P(\beta X),A\mapsto [A].
$$
**Ex1.** $[\cdot]$ 保持 $(\mathcal P(X),\subset)$ 上序结构, 即 $[A]\subset [B]$ ($[A]=[B]$) 当且仅当 $A\subset B$ ($A=B$). 

**Ex2.** $[A\cup B]=[A]\cup [B]$, $[A\cap B]=[A]\cap [B]$, $[A^c]=[A]^c$. $\{[A\mid A\subset X]\}$ 构成 $\beta X$ 的拓扑基. 

**Prop.** $[\cdot]$ 并不总兼容无穷情形. 例如取 $X=\mathbb N$, $A_n=\{1,n+1,n+2,\ldots\}$. 则
$$
[\cap_{n=1}^\infty A_n]=[\{1\}]=\uparrow \{1\}.
$$
另一方面, $[A_n]$ 中元素总是补集有限 ($\forall n\in\mathbb N$), 从而 (实际上为一般结论, **Ex3**)
$$
[\cap _{n=1}^\infty A_n]\supset \cap_{n=1}^\infty[A_n].
$$
事实上, 根据 $[A^c]=[A]^c$ 可知 $[\cup_{n=1}^\infty A_n]\subset \cup_{n=1}^\infty[ A_n]$. 

**Prop.** $[A]$ 既开又闭, 且 $\beta X$ 为紧致集. 

*Proof.* 前一论断是因为 $[A]=[A^c]^c$​. 对后一论断, 假设 $\{[A_i]\}_{i\in I}$​ 为不含有限子覆盖的开覆盖 (任意开集可由若干拓扑基之并生成), 即
$$
[\cup_{k=1}^NA_{i_k}]=\cup_{k=1}^N [A_{i_k}]\neq \beta X=[X].
$$
故 $\cap _{k=1}^NA_{i_k}^c\neq \emptyset$, 因此 $\{A_i^c\}_{i\in I}$ 生成极大滤子 $\mathscr U_0$. 取 $A_i$ 使得 $\mathscr U_0\in [A_i]$, 从而 $A_i$ 与 $A_i^c$ 均属于 $\mathscr U_0$, 矛盾!

$\square$

**Def.** 称 $\mathscr U_x$ 为 $x\in X$ 生成的主极大滤子, 若且仅若 $\mathscr U$ 为包含 $x$ 的最小滤子. 兹有约定 $\mathscr U_x=x$, 从而 $X\subset \beta X$ 为子空间. 

**Prop.** $x\in X$ 在 $\beta X$ 中孤立, 但 $X$ 在 $\beta X$ 中稠密. 

*Proof.* 即证明 $\mathscr U_x$ 为 $\beta X$ 中孤立点, $\overline {\{\mathscr U_x\mid x\in X\}}=\beta X$. 注意到 $[\{x\}]=\mathscr \{\mathscr U_x\}$ 既开又闭, 从而 $\mathscr U_x$ 在 $\beta X$ 中孤立. 

对任意 $\mathscr U\in \beta X$, 包含 $\mathscr U$ 的基本开邻域 $[A]$ 满足 $A\in \mathscr U$. 由于 $A$ 非空, 故存在 $x\in A$, 即 $\mathscr U_x\in [A]$. 从而 $X$ 在 $\beta X$ 中稠密.

$\square$ 

实际上, $x\in A\in \mathscr U_x \in [A] $. 是以可见双对偶给出的典范嵌入 $x\mapsto \mathscr U_x$, $A\mapsto [A]$. 

**Prop.** 实际上, $\beta X$ 中 $\overline A=[A]$. 

*Proof.* 即证明 $\overline {\{\mathscr U_x\mid x\in A\}}=[A]$. 这是显然的. 

$\square$ 

**Def.** 称 $\beta X$ 为 $X$ 的 Stone-Čech 紧致化. 更严格地, 即 $X$ 在同构于 $\{\mathscr U_x\}_{x\in X}$ 的意义下在极大滤子空间上的紧化. 

**Ex3.** $X$ 为有限集时, $X$ 一定为 Stone-Čech 紧致的, 即 $X=\beta X$. 

As we mentioned before, sequences do not characterise neither continuity nor compactness. One counterexmple for the former is,
$$
i:(X,\tau)\to (X,\mathcal P(X))
$$
is sequentially continuous (two topologies have the same convergent sequence) yet not continuous. Here
$$
\begin{align*}
\eta&:=\mathcal P(X\setminus \{x_0\}),\\
\tau&:=\eta\cup\{A\cup\{x_0\}\mid A\in \eta, |A^c|\leq \omega\}.
\end{align*}
$$
One counterexample for the latter is the Stone-Čech compactification for the non-compact matric space. Since no sequences converge to a point in $\beta X\setminus X$ and $X$ is not sequentially compact, $\beta X$ is not sequentially compact. However, $\beta X$ is indeed compact!

##### 一种理解 $\beta X$ 的自然方式 

为研究 $\mathcal P(X)$, 我们将其等同为紧致集 $\{0,1\}^X=\prod_{x\in X}\{0,1\}$​. 考虑积拓扑空间, 置拓扑基 (同时也是基本开集族) 由形如以下的开集组成
$$
\prod_{x\in X\setminus \{x_j\}_{i=j}^N}\{0,1\}_{x}\cdot \prod_{j=1}^N\{i_j\}_{x_j},\quad i_j\in \{0,1\}.
$$
若再将 $\{\alpha_j\}_{j=1}^l$, $\{\beta_j\}_{j=1}^m$ 定义作取 $0$ 与 $1$ 的 $i_j$, 下用 $[ \{\alpha_j\}_{j=1}^l;\{\beta_j\}_{j=1}^m]$ 定义基本开集. 例如 $[\{1,3\},\{2,4,5\}]$ 表示 $\{0,1\}^{\mathbb N}$ 中的基本开集 $(0,1,0,1,1)\times  \{0,1\}^{\mathbb N-5}$. 

**Ex4.** 实际上, $\{0,1\}^X$ 的乘积拓扑可以如下方式对应 $\mathcal P(X)$ 上的拓扑: 基本开集为 $[ \{\alpha_j\}_{j=1}^l;\{\beta_j\}_{j=1}^m]:=\{J\in \mathcal P(X)\mid J_{\alpha_j}\equiv 0, J_{\beta_j}\equiv 1\}$, 即在一切 $\alpha_j$ 位置上为 $0$, $\beta_j$ 位置上为 $1$ 的集合所成的集族. 

**Thm.** 积拓扑空间 $\mathcal P(\mathcal P(X))$ 细于 $\beta X$. 等价地, $\beta X$ 恰为 $\mathcal P(\mathcal P(X))$ 对应的积拓扑空间导出的子空间拓扑. 

*Proof.* 根据定义, 积拓扑空间中的基本开集 $\mathcal P(\mathcal P(X))$ 形如
$$
[\{A_j\}_{j=1}^l;\{B_j\}_{j=1}^m]=\{\mathscr U \in \beta X\mid A_i\notin \mathscr U,B_i\in \mathscr U\}.
$$
对于极大滤子而言, 有如下等价定义 (**Ex2.** 在先前 notes 中找到其定义方式):

1. $A_i\notin \mathscr U,B_i\in \mathscr U$.
2. $A_i^c,B_i\in \mathscr U$.
3. $E:=(\cap_{j=1}^l A_j^c)\cap (\cap_{j=1}^m B_j)\in \mathscr U$. 

取 $[E]=\{\mathscr U\in \beta X\mid E\in\mathscr U\}$ 即可.

##### 扩张原理

**Ex5.** 此前应当回忆一则引理: 紧致度量空间为 $T_3$ 的, 即单点与单点外的任意闭集可分. 等价地, 任意一点的开邻域中包含某一闭邻域. 

**Thm.** (扩张定理) 对任意紧致集 $K$, $f:X\to K$ 能被唯一地延拓至连续函数 $\overline f:\beta X\to K$, 换言之, 存在以下交换图:

<img src="https://s2.loli.net/2022/07/03/ZUOiBLCKvGoRF2D.png" alt="image-20220703154858213" style="zoom:15%;" />

*Proof.* 对任意极大滤子 $\mathscr U \in \beta X$, $f(\mathscr U)$ 为 $K$ 中极大滤子. 由紧度量空间上的极大滤子收敛至一点 ($T_3$ 与开头所述的结论), 不妨记为 $\overline f(\mathscr U)$. 注意到 $f(\uparrow \{x_0\})=\overline f(x_0)$, $\overline f$ 正是 $f$ 的某种扩张. 

为证明 $\overline f$ 之连续性, 任取 $\mathscr U\in\beta X$, $V$ 为 $f(\mathscr U)$ 在 $K$ 中邻域, 则存在 $A\in \mathscr U$ 使得 $f(A)\subset V$. 对 $\mathscr U$ 的邻域 $[A]$, $\forall \mathscr U'\in [A]$, 总有 $f(A)\in f(\mathscr U')$. 因此 $\overline f(\mathscr U')\in \overline {f(A)}\subset\overline V$. 对任意 $\mathscr U\in\beta X$ 与 $\overline f(\mathscr U)$ 之邻域 $U$, 存在闭邻域 $V\subset U$ (据 $T_3$). 前文业已证明存在 $\mathscr U$ 的邻域 $[A]$ 使得对一切 $\mathscr U' \in [A]$ 均有 $\overline f(\mathscr U')\in V\subset U$, 从而连续性得证.

由于 $X$ 在 $\beta X$ 中稠密, 唯一性显然. 

$\square$

一般地有
$$
\overline f(\mathscr U)=\{B\subset X\mid \exists A\in \mathscr U,\forall x\in A:B\in f(x)\}.
$$
特别地, $\overline f(x_0)=f(\uparrow \{x_0\})$.

##### $\beta X$ 上的半群结构

记 $\cdot $ 为半群 $X$ 上的乘法结构, 显然 $\cdot$ 可被唯一地连续延拓至 $\beta X$ 上 (**Ex6**). 

**Def.** 称拓扑半群 $X$ 为 company, 若且仅若 $X$ 同时满足

* $\forall a\in X$, 映射 $R_a:X\to X,x\mapsto xa$ 连续.
* $X$ 为紧拓扑空间. 

显然对任意半群 $X$, $\beta X$ 为 company. 我们还应当澄清乘法的机理

**Thm.** 对半群 $X$, $\forall \mathscr U,\mathscr U'\in \beta X$, 则

* $\mathscr U\cdot \mathscr U'=\{A\subset X\mid \exists B\in \mathscr U,\forall b\in B,\exists C\in \mathscr U':b\cdot C\subset A\}$. 
* 特别地, $\forall A\in\mathscr U\cdot \mathscr U'$, $\exists b\in X$, $C\in \mathscr U$ 使得 $b\cdot C\subset A$. 

*Proof.* 仅需证明第一条 (**Ex7**). 

一方面, $\mathscr U \cdot \mathscr U'\in [A]$. 由于右乘映射 $\overline {R_{\mathscr U'}}$ 连续, 存在邻域 $(B\in \mathscr U\in )[B]$ 使得 $\overline {R_{\mathscr U'}}(B)=B\cdot \mathscr U'\subset [B]\cdot \mathscr U\subset [A]$. 

$\square$ 
