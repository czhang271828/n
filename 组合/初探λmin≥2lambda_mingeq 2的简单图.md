# 初探 $\lambda_\min\geq -2$ 的简单图

<center>Author: 张陈成,       Student ID: 5190171910019</center>

[TOC]

## 摘要

本稿旨在解答课本^[3]^中的问题: 如何寻找并分类所有 $\lambda_\min\geq -2$ 的简单图. 笔者结合前人工作(见参考文献)与个人所学, 整理了以下结论:

1. 一切 $\lambda_\min\geq -2$ 的简单图可由有限类标准图直接导出, 且上述标准图与 Coxeter 图直接对应. 
2. 一切 $\lambda_\min\geq -2$ 的强正则图可被简单分类并列举. 

$\lambda_\min\geq -2$ 之简单图的分类工作肇端于 19 世纪 60 年代, 其提出者Hoffman已做出具体而微的成果. 而后 Doob, Cvetković 等研究者将根系理论引入该问题中, 基本解决了一般的 $\lambda_\min\geq -2$ 之简单图的分类工作. 

本文关于广义线图之定义参照^[3]^, 关于根系理论与 Coxeter 图之定义参照^[4][5]^, 关于 Petersen 图为例外图之证明参阅^[1]^. 一般 $\lambda_\min\geq -2$ 之简单图的根系分类系笔者自行推导, 强正则图相关部分整理自^[2][5]^. 

<div style="page-break-after: always"></div>

## 问题转化

任取 $G(V,E)$ 为顶点数为 $n$ 的简单图, 记 $A$ 为其邻接矩阵. 当 $\lambda_\min(G)\geq 2$ 时, $A+2I$ 半正定, 则存在实数矩阵 $Q$ 使得 $Q^TQ=A$ . 记列向量 $Q=(q_1\,q_2\,\cdots\,q_n)$ , $a_{ij}$ 为 $A$ 中第 $ij$ 个元素, 则 $i\neq j$ 时有 $a_{ij}=\left< q_i, q_j\right>$ ​. 实际上
$$
\left< q_i,q_j\right>=\left\{\begin{align*}
&0&&i\not\sim j,\\
&1&&i\sim j,\\
&2&&i= j.\\
\end{align*}\right.
$$
视 $\{q_i\}$ 为 $\mathbb R^n$ 中以原点为起点的向量, 则诸 $q_i$ 模长均为 $2$ , 且两两成角为 $\pi/3$ 或 $\pi/2$ . 

由是可知, 任一满足 $\lambda_\min\geq -2$ 的简单图与某组两两成角为 $\pi/2$ 或 $\pi/3$ 的单位向量集可建立一一对应. 实际上, 可采用根系 (root system) 理论研究一般欧式空间高度对称的向量系统, 关于根系理论的公理化叙述可参见^[4]^. 

## $\lambda_\min\geq -2$ 的简单图所对应的根系类

沿用上节记号, 令 $\mathrm{c}(Q):=\{\pm \frac{1}{\sqrt 2}q_i\}$ 为所有列向量对应的方向. 若$\mathrm c(Q)$中存在夹角为 $\pi/3$ 的两个向量 $\{x,y\}$ , 则 $\{x-y\}$ 与 $\mathrm c(Q)$ 中所有向量的夹角余弦值仍为 $\{0,\pm 1/2,\pm 1\}$ 中一者. 某种意义上, 在 $\mathrm c(Q)$ 中为成角为 $\pi/3$ 的二元向量组添加差向量之操作可视作一种完备化. 依照以上步骤有限扩充 $\mathrm c(Q)$ 可直接导出更大的图$\tilde G$, 且原图 $G$ 为 $\tilde G$ 的删点子图. 由于每一 $c(Q)$ 有唯一对应的 $c(\tilde Q)$ , 下仅需研究所有可能的 $c(\tilde Q)$ , 即满足以下条件的向量集 $\Phi$ :

1. $\forall q\in \Phi$ , $\|q\|_2=1$. $\pm q\in\Phi$ .
2. $\forall x,y\in\Phi$ , $\left< x,y\right>\in\{0,\pm 1/2,\pm 1\}$ . 
3. 若 $\exists x,y\in\Phi$ 使得 $\left< x, y\right>=1/2$ , 则 $\pm(x-y)\in\Phi$ . 
4. 为研究方便, 不妨设图连通(等价地称 $\Phi$ 连通), 即不存在非空划分 $\Phi=\Phi_1\dot \cup \Phi_2$ 使得 $\forall (x,y)\in(\Phi_1,\Phi_2)$ , $\left< x,y\right>\equiv 0$ . 

下对 $\Phi$ 删除若干元素以简化, 同时保证每一简化后的集合 $\Phi'$ 与原集合 $\Phi$ 唯一对应. 

1. 选择 $\mathrm{span}(\Phi)$ 中半空间(开集)使得$\Phi$中恰有一半元素落在该半空间中. 例如选择 $\alpha\in \mathrm{span}(\Phi)$ 使得 $\forall x\in\Phi$ , $\left< \alpha,x\right>\neq 0$ . 记 $\Phi_\alpha^+:=\{x:\left< \alpha,x\right>>0\}$ . 
2. 若存在 $x,y\in\Phi$ 使得 $\left< x,y\right> =-1/2$ , 则删去 $x+y$ , 如是重复直至不可再操作得 $\Phi'$ . 实际上, 分步操作等价于同时操作, 且最终对应的 $\Phi'$ 唯一且连通. 

下证明第二步中所述之论断. 视 $\Phi$ 中元素为顶点集 $V(\Phi)$ , 构造带权重 $\pm 1$ 的边集 $E(\Phi)$ , 其中权重定义为 $\left< v_i,v_j\right>$ (权重为$0$即不连边). 依对$\Phi$之构造, 图 $G(\Phi)$ 满足以下性质: 任意权重为 $-1$ 的边含于唯一的三角形, 且该三角形其余两边权重均为 $1$ . 

实际上, $G(\Phi')$ 由 $G(\Phi')$ 删去一切边权重为 $\{-1,-1,1\}$ 的三角形中权为 $-1$ 之边所对的顶点所得. 由于该些顶点确定, 故删除方式存在且唯一. 下考虑连通性: 若子图 $\triangle ABC$ 中 $A$ 点连接了 $\triangle ABC$ 中两条权重为 $-1$ 的边, 且 $A$ 的度数大于 $2$ , 则不妨设 $A\sim D$ . 由于 $1=|\left< A,D\right>|=|\left< B,D\right>+\left< C,D\right>|\neq0$ , 从而 $D$ 与 $B$ 或 $C$ 存在连边. 从而删除顶点 $A$ 不会造成连通度的增加. 综上, 原论断正确. 

自 $\Phi'$ 补全为 $\Phi$ 之方式更为简单, 只需确保一切权重为 $-1$ 的边含于唯一的三角形, 且该三角形其余两边权重均为 $1$ . 下称 $\Phi'$ 为最简根系. 

## 最简根系对应的 Coxeter 图

Coxeter 图之定义见附录. 本文中的 $G(\Phi')$ 即一类特殊的 Coxeter 图. 

$G(\Phi')$ 满足如下性质: 

1. 对任意 $\{x,y\}\subset \Phi'$ , $\left< x,y\right>\leq 0$ .

   实际上, 若存在夹角为 $\pi/3$ 的 $\{x,y\}$ , 则 $\{\pm(x-y)\}\subset \Phi$ , 从而简化 $\Phi\to\Phi'$ 之时 $x$ 或 $y$ 应被消除. 上以证明简化过程存在且唯一, 故矛盾. 

2. $G(\Phi')$ 中边数 $e$ 严格小于顶点数 $n$ . 

   据上条结论, 注意到
   $$
   0\leq\left< \sum_{x\in\Phi'} x, \sum_{x\in\Phi'} x\right>=\sum_{x\in\Phi'}\left< x,x\right>+2\sum_{i< j}\left< x_i,x_j\right>\leq n-e.
   $$
   取等时要求 $\Phi'$ 中不等的向量间夹角恒为 $\pi/3$ , 即 $\Phi'$ 由转化完全图之$\Phi$所得. 而 $2I+A(K_n)$ 满秩, 从而一切满足 $Q^TQ=QQ^T=(2I+A(K_n))$ 的方阵满秩. 注意到一切对应 $\Phi$ 的 $\mathrm{c}(Q)$ 的包含了某一等距同构于 $\Phi'$ 的子集, 反之 $\mathrm{c}(Q)$ 无法补全至 $\Phi$ . 而 $\sum_{x\in\Phi'}x=0$ 说明 $\Phi'$ 含有线性无关项, 从而 $\mathrm c(Q)$ 并非线性无关. 矛盾. 

3. (已证明) $G(\Phi')$ 连通. 

从而 $G(\Phi')$ 为树. 下推导该类树的性质. 

1. $G(\Phi')$ 中顶点度数不超过 $3$ . 设 $\{x_i\}_{i=1}^k$ 为 $y$ 的邻点, 由于 $G(\Phi')$ 无圈, 则 $\{x_i\}_{i=1}^k$ 两两不交. 从而
   $$
   1=\left< y,y\right>\geq \left< \sum_{i=1}^k \left< x_k,y\right> x_k,\sum_{i=1}^k \left< x_k,y\right> x_k\right>\geq \sum_{i=1}^k\left< x_k,y\right>^4=\dfrac{k}{4}.
   $$
   实际上, 第一处等号无法取到 (即 $y$ 与 $\{x_i\}_{i=1}^k$ 线性无关) ; 反之设 $y=\sum_{i=1}^kc_i x_i$ , 则 $\left< y,y\right>=\sum_{i=1}^k c_i^2=1$ . $c_i=\left< x_i,y\right>\in\{-1/2,0\}$ , 从而 $y$ 与至少四个元素夹角为 $2\pi/3$ . 从而 $y$ 在 $G(\Phi)$ 中含于某一三角形, 且 $y$ 在该三角形中连边均为 $1$ , 从而 $y$ 应被消除. 矛盾.

2. $G(\Phi')$ 中路可视作单点. 如取 $x_1-x_2-\cdots -x_k$ 为 $G(\Phi')$ 中一条路 (即 $P_n$ 子图), 记 $x_0=\sum_{i=1}^k x_i$ , 则
   $$
   \left< x,x\right>=\sum_{i=1}^k \left< x_i,x_1\right>+2\sum_{i< j}\left< x_i,x_j\right>=k-(k-1)=1.
   $$
   由于任意路外点 (如取 $y$ ) 与路至多有一个交点, 从而 $\left< x,y\right>\in\{0,-1/2\}$ . 

结合上述两点论断, 任意链有至多一个分叉点, 即 $G(\Phi')$ 有至多三个末端. 

为方便, 约定 $\mathbb B^n$ 为 $\mathbb R^n$ 中的标准正交基. 

### $A_n$ 图

若 $G(\Phi')=P_n$ ​, 考虑
$$
A_n\sim\{\pm(e_i-e_j):e_i,e_j\in\mathbb B^{n+1},i\neq j\}
$$
即可.

### $D_n$ 图

若 $G(\Phi')$ 为有三个端点的树, 不妨设 $G(\Phi')$ 由三条路 $\{u_i\}_{i=1}^p$ , $\{v_i\}_{i=1}^q$ , $\{u_i\}_{i=1}^r$ 连接而成, 且令 $c=u_p=u_q=u_r$ . 记 $u=\sum_{i=1}^{p-1}i\cdot u_i$ , $v=\sum_{i=1}^{q-1}i\cdot v_i$, $w=\sum_{i=1}^{r-1}i\cdot w_i$ , 则
$$
1=\left< c,c\right>\geq\sum_{x\in\{u,v,w\}}\dfrac{\left< c,x\right> ^2}{\left< x,x\right>}=\sum_{t\in\{p,q,r\}}\dfrac{1-p^{-1}}{2}.
$$
从而 $\dfrac{1}{p}+\dfrac{1}{q}+\dfrac{1}{r}\geq 1$ . 实际上, 若采用多数 Lie 群相关教材中对最简根系之定义, $\Phi'$ 中元素的线性无关性从定义中即可说明. 因此上式等号不可取. 

依假定, $p,q,r\geq 2$ . 从而 $p=q=1$ 时 $r\in\mathbb N=\{0,1\}$ . 即
$$
D_n\sim\{\pm e_i\pm e_j:e_i,e_j\in \mathbb B^n\}.
$$

### $E_{6,7,8}$ 图

考虑解 $p=2$ , $q=3$ , $r=3,4,5$ . 构造并检验之 (过程略) 得
$$
E_8\sim D_8\cup \left\{\sum_{i=1}^8\dfrac{\varepsilon_i}{2}e_i:\varepsilon\in\{\pm 1\}, e_i\in\mathbb B^8,\prod_{i=1}^n\varepsilon_i=1\right\}.
$$
对应$r=6$之情形.
$$
E_7\sim \left\{ x\perp v:x\in E_8\right\}\quad \text{for any fixed }v\in E_8.
$$
对应$r=5$之情形.
$$
E_6\sim \{x\perp \mathrm{span}(v_1,v_2,v_3):x\in E_8\}\quad \text{for any fixed }v_i\in E_8.
$$
因此, 我们对所有 $\lambda_\min\geq-2$ 的简单图之类别进行了初步界定. 

<div style="page-break-after: always"></div>

## $\lambda_\min \geq-2$ 简单图之分类

本节将给出以下结论: 

* 图 $G$ 有 $A_n$ 表示若且仅若 $G$ 为某一顶点数为 $n+1$ 的二分图之线图.
* 图 $G$ 有 $D_n$ 表示若且仅若 $G$ 为某一广义线图 (含不以 $A_n$ 表示的线图).
* 图 $G$ 有 $E_n$ 表示若且仅若 $G$ 为例外图.

对 $G$ 而言, 线图 $L(G)$ 以 $E(G)$ 为顶点集合, 以 $E(G)$ 中的边相邻关系决定 $V(L(G))$ 中的顶点相邻关系. 下图为由 $G$ 构造 $L(G)$ 之方式.

<center><img src="https://files.mdnice.com/user/12571/5f10ab90-c2fa-4bcb-9395-b0c998749b10.png" style="zoom:50%;" /><img src="https://files.mdnice.com/user/12571/fa4dc5bb-7a46-450c-b073-8fcd3f4d07e8.png" style="zoom:50%;" /><img src="https://files.mdnice.com/user/12571/40219f98-d10d-484d-b791-31c05506cf35.png" style="zoom:50%;" /><img src="https://files.mdnice.com/user/12571/b375d0b9-3e77-42e6-8996-1e833e7f9d89.png" style="zoom:50%;" /></center>

作 $G$ 的导出矩阵 $B:=(b_{ve})_{|V|\times |E|}$ , $b_{ve}=1$ 若且仅若点 $v$ 与边 $e$ 相连, 反之 $b_{ve}=0$ . 从而 $B^TB-2I_{|E|}$ 即为 $G$ 线图之邻接矩阵 $A(L(G))$ . 由于 $B^TB$ 半正定, $L(G)$之特征值至少为 $-2$ . 

若在 $G$ 中顶点 $j$ 处添上一条边得图 $G'$ , 则 $L(G)$ 为 $L(G')$ 的某一删点图. 特别地, 记 $A:=A(L(G))$ , 则 $A(L(G'))$ 具有一般形式 $\begin{pmatrix}0&u^T\\u&A\end{pmatrix}$ . 对图 $G''$ 使得
$$
A(L(G''))=\begin{pmatrix}0&0&u^T\\0&0&u^T\\u&u&A\end{pmatrix}.
$$
经构造, $G''$ 并非简单图, 但可通过在简单图上添加重边获得. 由于 $A(L(G''))$ 仍为简单图, 同时具备线图的重要特点: $A(L(G''))+2I$ 半正定, 即 $\lambda_\min \geq -2$. 现称该类形如 $A(L(G''))$ 的图为广义线图. 

如下图所示, 构造广义线图的一般步骤如下:

![](https://files.mdnice.com/user/12571/4494a876-172d-4d77-b10a-220cfbb38e6c.png)

1. 在简单图 $H$ 的部分顶点处添加若干条花瓣 (pendant) , 即有偶数条重边的添边. 例如 $\hat H$ 由 $H$ 于点 $1$ 上添加一片花瓣, 于点 $4$ 上添加两片花瓣所得.
2. 仿照线图的定义, 对 $\hat H$ 中边进行编号. 其中, 两边相邻若且仅若仅有一个公共顶点. 例如, $i\sim h$ , $c\sim a$ ; 但 $i\not\sim j$ . 
3. 根据连边关系作线图 $L(\hat H)$. 

注意到广义线图 $L(G,a_1,\ldots, a_m)$ 即线图 $L(G)$ 上添加点
$$
\{(i,\pm l):i=1,\ldots, m,l=1,\ldots,a_i\}
$$
所得. 记 $e_i+e_j$ 为 $L(G,a_1,\ldots,a_m)$ 中由边 $ij\in E(G)$ 对应点所表示的向量, $e_i\pm e_{(i,l)}$ 分别对应点 $(i,\pm l)$ 即可得广义线图之 $D_n$ 表示. 若 $G$ 为二分图, 将边 $ij$ 记作 $e_i-e_j$ 即可得 $A_n$ 表示. 此外, 应说明无法由 $A_n$ 或 $D_n$ 表示的图之存在性. 

实际上, 部分满足 $\lambda_\min\geq -2$ 之图不属于线图或广义线图, 如 Petersen 图. 注意到 Petersen 图中任意相邻的两点 $u,v$ 满足 $N(u)\neq N(v)$ . 从而 Petersen 图并非广义线图. 假设存在 $H$ 使得 $L(H)$ 为 Petersen 图, 则由于 Petersen 图中相邻两点没有公共邻点, 故 $H$ 中不含度至少为 $3$ 的点. 显然 $H$ 为若干圈, 散点及路之无交并. 矛盾. 

注意到 $E_n$ 有限, 故例外图有限. 从而对顶点足够多的连通图而言, 若 $\lambda_\min\geq -2$ , 则该图为线图或广义线图, 进而可通过合适的算法约化之.  

就最小特征值严格大于 $-2$ 的图而言, 可稽的结论^[4]^包括:

1. 若 $H$ 为某一树的线图, 则 $\lambda_\min >-2$ .
2. 若 $H$ 为某一树添上一片花瓣所生成的广义线图, 则 $\lambda_\min >-2$ .
3. 若 $H$ 为顶点数为奇数的单圈图, 则 $\lambda_\min >-2$ .
4. 某些例外图也满足 $\lambda_\min >-2$ .

## $\lambda_\min=-2$ 的强正则图

本节将总结 $\lambda_\min=2$ 之强正则图, 原因有下:

1. $\lambda_\min \geq 2$ 的图系本文中心议题. 
2. Seidel 证明了 $\lambda_\min> -2$ 的所有强正则图无非 $K_n$ 与 $C_5$. 该结果较为平凡.

记强正则图 $G(v,k,\lambda,\mu)$ 为一切满足以下条件的图

1. $G$ 为顶点数为$v$的正则图, 每条边度为 $k$ . 
2. $G$ 中任意相邻的两点的公共邻点数量恒为 $\lambda$ .
3. $G$ 中任意不邻的两点的公共邻点数量恒为 $\mu$ .

强正则图 $G(v,k,\lambda,\mu)$ 含有重数为 $1$ 的主特征值 $k$ . 对任意非主特征值 $x$ 所述的特征向量 $x$ , 有 $x^T\mathbf 1_v=0$ . 注意到
$$
A^2=kI+\lambda A+\mu(\mathbf 1_{v\times v}-I_v-A).
$$
从而
$$
[A^2+(\mu-\lambda)A+(\mu-k)I_v]x=\mathbf 0_v.
$$
解得
$$
\left\{\begin{align*}
\tau =&\,\dfrac{1}{2}\left[(\lambda-\mu)+\sqrt{(\lambda-\mu)^2+4(k-\mu)}\right],\\
\theta =&\,\dfrac{1}{2}\left[(\lambda-\mu)-\sqrt{(\lambda-\mu)^2+4(k-\mu)}\right].\\
\end{align*}\right.
$$
重数$m_\tau$与$m_\theta$满足$\mathrm{trace}(A)=\tau m_\tau+\theta m_\theta+k=0$, 以及$m_\tau+m_\theta+1=n$. 从而
$$
\left\{\begin{align*}
m_\tau=&\,\dfrac{1}{2}\left[v-1-\dfrac{2k+(v-1)(\lambda-\mu)}{\sqrt{(\lambda-\mu)^2+4(k-\mu)}}\right],\\
m_\theta=&\,\dfrac{1}{2}\left[v-1+\dfrac{2k+(v-1)(\lambda-\mu)}{\sqrt{(\lambda-\mu)^2+4(k-\mu)}}\right].\\
\end{align*}\right.
$$
对任意点 $v_0\in G$ , $v_0$ 的邻点集向非邻点集引出 $k(k-\lambda-1)$ 条边, 而 $v_0$ 邻点集向非邻点集引出 $\mu(v-k-1)$ 条边,从而 $k(k-\lambda-1)=(v-k-1)\mu$ . 

当 $\theta=-2$ 时, 化简得 $k=2\lambda-\mu+4$ . 

* 当 $\mu=2$ 时, 得通解 $(n^2,2(n-1),n-2,2)$ , 其中 $n\geq 2$ . 

* 当 $\mu=4$ 时, 得通解 $(n(n-1)/2,2(n-2),n-2,4)$ , 其中 $n\geq 4$ .

当 $\mu\neq 2,4$ 时, 由特征值关系化简知 $m_\tau=\dfrac{2v-k-2}{\tau+2}=\dfrac{(\mu+2\tau)(\mu+2\tau+2)}{\mu(\tau+2)}$ . 下从图的"部件"数量考察.

设 $x\sim a,b$ 但 $a\not\sim b$ , 记 $\{x,a,b\}$ 包含于 $c$ 个 $K_{1,3}$ 及 $q$ 个 $C_4$ . 这里限定 $K_{1,3}$ 中任意三点不为 $G$ 中某一 $K_3$ 的三个顶点, 例如 $G=K_4$ 不包含 $K_{1,3}$ , 但 $G=K_{3,3}$ 包含 $K_{1,3}$ . 计算 $x$ 邻点数量得
$$
\begin{align*}
k&=\sum_{y\not\sim a,y\not\sim b\\y\sim x}1+\sum_{y\not\sim a,y\sim b\\y\sim x}1+\sum_{y\sim a,y\not\sim b\\y\sim x}1-\sum_{y\sim a,y\sim b\\y\sim x}1\\
&=2+2\lambda-(\mu-1-q)+c
\end{align*}
$$
故 $c+q=k-3-2\lambda+\mu=1$ . 因此 $c=0,q=1$ 或 $c=1,q=0$ .

若 $c=1$ , 则不妨设 $\{x,a,b,c\}$ 组成 $K_{1,3}$ . 记 $N(v):=\{x:x\sim v\}$ 为 $v$ 之邻域, $N(H):\{x\in N(v):v\in H\}$ 为 $H$ 之邻域, $F(H):=V(G)\setminus(V(H)\cup N(H))$ 为外点集. 注意到

1. $N(x)\cap F(a)$ 内, $k-\lambda-1=\tau +1$ 个点在 $\{b,c\}\cup N(b,c)\setminus\{x\}$ 中, 从而 $\tau\leq \mu$ . 
2. $(N(a)\cap F(x))\cup\{a\}$ 中的 $k-\lambda$ 个点包含于 $F(\{b,c\})$ 中的 $\lambda=v-2k+\mu-2$ 个点, 从而 $v\geq 5\tau+\mu+4$ . 
3. $\mu v=(k-\tau)(k+2)$ , 从而 $v=3\tau+\mu+2+\dfrac{2\tau(\tau+1)}{\mu}\in\mathbb N$ . 因此 $\mu\leq r$ . 

故得系数组

* $(6\tau+4,3\tau,2\tau-2,\tau)$ , 其中 $m_\tau=9-\dfrac{12}{\tau+2}\in\mathbb N$ . 据 A. E. Brouwer 对 $\mu$ 界之估计 ($v\leq\dfrac{m_\tau(m_\tau+3)}{2}$) , 取 $\tau=1,2,4,10$ 即可.

若 $q=1$ , $\{x,a,b\}$ 属于唯一的 $C_4$ , 进而 $\mu$ 必为偶数, $N(a,b)$ 包含为 $K_{(\mu/2)\times 2}$ . 若 $a\sim d\not\sim b$ , 则 $d$ 与 $N(a,b)$ 中的 $\mu/2$ 个点恰好相邻 (此处从 $K_{1,3}$ 之不存在性分析即可) . 注意到 $F(b)$ 导出强正则图 (系数为 $(v-k-1,k-\mu,\lambda- \mu/2,\mu)$ ) , 此处允许 $v-k-1=0$ 及 $k-\mu=0$ 之情况. 

* $v-k-1=0$情形对应$K_{2\times n}$.

若 $F(b)$ 导出完全图, 则 $m_\tau=8-\dfrac{12}{\tau+2}$ . 从而枚举知

* $(10,6,3,4)$ , $(16,10,6,6)$ .

若 $F(b)$ 导出 (其余情形的) 强正则图, 则由
$$
(k-\mu)=2(\lambda-\mu/2)-\mu+4
$$
知 $F(b)$ 导出的强正则图的最小特征值仍为 $-2$ . 该导出图的最大特征值重数为 $\dfrac{2\tau(\tau+1)}{(\tau-\mu/2+2)\mu/2}$ , 从而 $\mu$ 仅可能为 $6$ 或 $8$ , 或该导出的强正则图为 $K_{2\times n}$ 形式. 就此再进行有限次的枚举, 最终整理得到七类可能的图. 

1. $K_{n\times 2}$ . 

2. $L_2(n)$ , 亦作 $H(2,n)$ . 系数为 $(n^2,2(n-1),n-2,2)$ . 前一种表示方式对应格点图 (lattice graph) , 每一点仅与同行同列的点相连.

   <img src="https://files.mdnice.com/user/12571/ae34879c-e6b0-43eb-a4ae-686a53092afc.png" style="zoom:33%;" />

   后一种表示方式为 $2$ 阶 Hamming 图, $H(2,n)$ 的顶点集与 $V(K_n)\times V(K_n)$ 相同, 记作
   $$
   \{(x_1,x_2):x_1,x_2\in\{1,2,\ldots, n\}\}
   $$
   $(x_i,x_j)\sim(x_k,x_l)$ 若且仅若 $i=k$ 或 $j=l$ .

3. $T(n)$ . 系数为 $(n(n-1)/2,2(n-2),n-2,4)$ . 构造与 $L_2(n)$ 相似, 只是 $n$ 阶正方形被换做了 $n$ 阶三角形. 值得一提的是, $T(n)=L(K_n)$.

4. Shrikhand 图. Shrikhand 于1959年证明了结论: 格点图之系数决定了唯一的强正则图, 但 $n=4$ 例外. 实际上, Shrikhand 图与 $L_2(4)$ 拥有相同的谱. 

   <img src="https://files.mdnice.com/user/12571/a639641a-a331-4c45-b1c7-90525968cdd0.png" style="zoom: 20%;" />

5. Chang 图. $T(n)$ 之系数确定了唯一的强正则图, 除了 $n=8$ 时的三个异构图. 该类图由 Chien-Chiang Lee (李建強) 首次发现, 图附于文末. 

6. Petersen 图 ($KG_{5,2}$) , 系数为 $(10,3,0,1)$ . 依 $KG_{5,2}$ 之定义作下图

   <img src="https://files.mdnice.com/user/12571/5bdbaddc-7429-4354-bfd7-a3ef85c0c311.png" style="zoom: 50%;" />

   图中以 $\mathbb Z_5$ 之二元子集为点, 连边若且仅若点所对应的子集相离. 

7. Clebsch 图, 系数为 $(16,10,6,6)$ . 这是证明末段 $\mu=6$ 情形所对应的结果, 其形如下.

   <img src="https://files.mdnice.com/user/12571/8ff3afa9-c4fe-4bd4-a682-499fae18c748.png" style="zoom:50%;" />

8. Schläfli 图, 系数为 $(27,16,10,8)$ . 这是证明末段 $\mu=8$ 情形所对应的结果. 善洞若观火, 明察秋毫者可领会 Schläfli 图中任意一点的邻域 ($16$个点) 导出 Clebsch 图之补图. Schläfli 图附于文末.

<div style="page-break-after: always"></div>

## 参考文献

[1] Douglas B. West. *Introduction to Graph Theory.* Pearson Education, Inc., 221 River Street Hoboken, NJ 07030 U.S.A., 2002.

[2] Slobodan Simić, Dragoš Cvetković, Peter Rowlinson. *An Introduction to the Theory of Graph Spectra.* Cambrige University Press, The Edinburgh Building, 	  Cambridge CB2 8RU, U.K., 2002.

[3] G.F. Royle C. Godsil. *Algebraic Graph Theory (Graduate Texts in Mathematics, 207)*. Springer Publishing Company, Inc., New York, U.S.A., 2002.

[4] Daniel Bump. *Lie Groups (Graduate Texts in Mathematics, 136)*. Springer Publishing Company, Inc., New York, U.S.A., 2013.

[5] Andries E. Brouwer, Hendrik Van Maldeghem, *Strongly regular graphs*, a preprint downloaded 2021-06-17 from [Here](https://homepages.cwi.nl/~aeb/math/srg/rk3/srgw.pdf), listed as fragments of a text on strongly regular graphs in section 2021 of [This](https://www.win.tue.nl/~aeb/preprints.html).

<div style="page-break-after: always"></div>

## 附图

![](https://files.mdnice.com/user/12571/bb9c3ee5-9b1a-49d5-bf59-25e32bdbb422.png)

<center>Schläfli图</center>

<img src="https://files.mdnice.com/user/12571/f78fb9fc-7c2b-4fbc-a850-727215eff899.png" style="zoom:100%;" />

<center>Chang图</center>

