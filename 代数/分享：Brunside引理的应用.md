**分享：Brunside引理的应用**

***

考虑下列计数问题：$n$颗柱子串成一圈项链，每颗可选$r$种颜色，若视翻转与旋转后相同的两条项链为同类的，试问一共可生成几类项链？

设$n=6$、$r=4$，项链类数减一即卤代苯（氟氯溴碘代苯，不考虑存在性及非常规的异构现象）的种数。

自然的想法是将同类的所有项链视为等价类。将$n$颗珠子串成的项链视为正$n$边型，我们自然地引入集正$n$边型所有旋转和翻转的变换的群$D_n$：

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/59/Pentagon_Linear.png/220px-Pentagon_Linear.png" alt="img" style="zoom:50%;" />

上图的多边形的不变变换包括：旋转$2\pi/n$的变换，记变换为$a$；沿$x$轴翻转 ，记变换为$b$。则所有变换可由$a$与$b$生成，易知变换构成群。记变换群$D_n:=\left<a,b\right>$。

$D_n$中元素满足：$a^n=$e，$b^2=e$，$(ab)^2=e$。这里$e$是单位元。可用半直积对群结构做更清晰的阐述，即
$$
D_n\cong \mathbb Z_n\rtimes_\varphi\mathbb Z_2
$$
形式上，$D_n$元素为$\mathbb Z_n$与$\mathbb Z_2$的笛卡尔积，前者同构于旋转变换而后者同构于翻转。乘积上，$\forall (g,h),(g',h')\in\mathbb Z_n\times\mathbb Z_2$
$$
(g,h)(g',h'):=(g\varphi_h(g'),hh')
$$
这里设$\mathbb Z_2=\{0_2,1_2\}$，则$\varphi_{1_2}:g\mapsto -g$，$\varphi_{0_2}:g\mapsto g$。容易验证半直积构成的群于其上的乘法是良定义的。

回到项链，视$\Omega$为同类合并前的所有项链种数，将变换$D_n$作用在$\Omega$的所有元素上即为合并操作，记$D_n\curvearrowright\Omega$为群$D_n$在$\Omega$上的作用。合并后的项链类数是集合
$$
\{D_n \omega:\omega\in\Omega\}
$$
中的元素个数。一般称$D_n\omega$为$\omega$的$D_n$-轨道，我们只需求所有轨道条数。

Burnside引理是指：设群$G$作用在集合$\Omega$上，记$F(g)$为$\Omega$中$g$的不动点个数，即$|\{\omega:g\omega=\omega\}|$。设$t$为轨道的数量，则
$$
t=\dfrac{1}{|G|}\sum_{g\in G}F(g)
$$
证明比较容易，我们只需通过两种方式计算$(G,\Omega)$中不动点对的数量$\Gamma$，即所有满足$g\omega=\omega$的$(g,\omega)$组数：

1. 若固定$\Omega$，考虑每个$g\in G$，则$\Gamma=\sum_{g\in G}F(g)$。

2. 若固定$G$，考虑每个$\omega\in\Omega$，我们记$G_\omega:=\{g\in G:g\omega=\omega\}$。有如下引理：对任意$x,y\in\Omega$，$Gx\neq Gy\Leftrightarrow Gx\cap Gy=\emptyset$。只证明必要性：不然，设$z\in Gx\cap Gy$，则$\exists g_0\in G$使得$g_0z=x$，故$Gx=Gy$矛盾。因此$\Omega$可看作若干$G\omega_i$的无交并，$1\leq i\leq t$。
   考虑映射
   $$
   \pi:Gx\to G/G_x,gx\mapsto gG_x
   $$
   易知$\pi$是双射，因此$|Gx|=|G|/|G_x|$。
   $$
   \Gamma=\sum_{\omega\in\Omega}|G_\omega|=\sum_{\omega\in\Omega}\dfrac{|G|}{|G\omega|}=\sum_{i=1}^t\sum_{\omega \in G\omega_i}\dfrac{|G|}{|G\omega_i|}=t|G|
   $$

综上，Burnside引理：$t=\dfrac{1}{|G|}\sum_{g\in G}F(g)$得证。Burnside引理的核心内涵已在证明中体现，即通过两种不同的方式等价地计算不动点对的组数。

回归项链问题，我们将题目数学化地阐述：

将$B=\{1,2,\ldots, n\}$视作珠子集合，$C=\{c_1,c_2,\ldots,c_r\}$视作颜色集合。取$y_i\in C$为第$i$颗珠子的颜色，将一串项链看作一个$B$到$C$的映射（每颗珠子赋值一种颜色）。记$\Omega:=C^B:\{f:f:B\to C\}$。

回顾前文，我们需要利用二面体群$D_n$在$\Omega$上的作用以计数项链的类，首先需要定义$\alpha\in D_n$与$f\in \Omega$的乘法。视$\alpha$为置换关系，则
$$
\alpha\times f=
\begin{pmatrix}
1&2&\cdots&n\\
i_1&i_2&\cdots&i_n
\end{pmatrix}
\begin{pmatrix}
1&2&\cdots&n\\
y_1&y_2&\cdots&y_n
\end{pmatrix}
=
\begin{pmatrix}i_1&i_2&\cdots&i_n\\y_1&y_2&\cdots&y_n\end{pmatrix}
$$
注意到项链类数即轨道条数，根据Burnside引理，只需求$\dfrac{1}{|D_n|}\sum_{\alpha\in D_n}F(\alpha)$。

$\alpha\times f=f$当且仅当将$\alpha$写成轮换形式后，每组轮换因子序标对应的$y_i$相同。一条重要的定理是：任意置换写成两两不交轮换的形式是唯一的。我们设$\alpha$的轮换形式种长度为$i$的轮换有$m_i$种，故$F(\alpha)=r^{m_1+m_2+\cdots m_n}$。$D_n$中元素一定能写为$a^pb^q$形式，其中$0\leq p\leq n-1$，$q=0,1$。下计算每个$a^pb^q$对应的不交轮换形式：

$a^i=(12\cdots n)^i$。任意元素轮换$\dfrac{n}{\gcd(i,n)}$次后总能回到原位，故每个轮换包含了$\dfrac{n}{\gcd(i,n)}$个元素，共$\gcd(i,n)$个$\dfrac{n}{\gcd(i,n)}$-轮换。$F(\alpha)=\sum_{i=0}^{n-1}r^{\gcd(i,n)}$。

$n$为奇数时，经变化$a^ib$后的正$n$边形有且仅有一个不动点。根据对称性，$\alpha$可由$\dfrac{n-1}{2}$个对换（$2$-轮换）和一个不动点（$1$-轮换）组成。$F(\alpha)=r^{(n+1)/2}$。

$n$为偶数时，当$i$取遍$0$至$n-1$，有一半的变化由$\dfrac{n}{2}$个对换组成，一半的变化由$\dfrac{n}{2}-1$个对换和两个不动点组成。$F(\alpha)$分别为$r^{n/2}$与$r^{(n+2)/2}$。

综上，$n$颗柱子串成一圈项链，每颗可选$r$种颜色，项链类数共计
$$
t=\dfrac{1}{2n}\sum_{i=0}^{n-1}r^{\gcd(n,i)}+\left\{\begin{align*}&\dfrac{1}{2}r^{(n+1)/2}&&\text{$n$ 为奇数},\\&\dfrac{1}{4}(r^{n/2}+r^{(n+2)/2})&&\text{$n$ 为偶数}.\\\end{align*}\right.
$$

***

应用：卤代苯一共有几种？

解：即令$n=6$，$r=4$。
$$
t=\dfrac{1}{12}(4096+4+16+64+16+4)+\dfrac{1}{4}(64+256)=430
$$
故共有$429$种卤代苯。