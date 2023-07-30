product topology (Тихонов topology) 与 box topology 之不同之处可以类比如下: 

定义: 称 $\{x_i\}_{i\in I}$ 线性无关, 若且仅若对一切 $I$ 的有限子集 $I_0$, $\{x_i\}_{i\in I_0}$ 均线性无关.

定义: 线性张成 $\mathrm{span}(\{x_i\}_{i\in I}):=\cup_{I_0}\mathrm{span}(\{x_i\}_{i\in I_0})$, 其中 $I_0$ 取遍 $\mathcal P(I)$ 中有限集.

比较第一个例子, 该例子与有限维线性空间比较贴近 **(注: 不要联想 "基" 的概念)**; 但需要收藏, 因为这涉及到某本著名泛函分析书里的错误. 

$c_0$ 为收敛至 $0$ 的数列全体, 记 $e_k=(0,\ldots, 0,1,0,\ldots)$ (第 $k$ 位为 $0$), 则

*  $\{e_k\}_{k\in\mathbb Z_{\geq 1}}$ 线性无关.
* $\mathrm{span}(\{e_k\}_{k\in\mathbb Z_{\geq 1}})\subsetneq c_0$.
* $\{e_1,e_2-e_1,e_3-e_2,\ldots\}$ 也线性无关.

记 $x=\sum_{k\geq 1}x_k e_k$. 定义 $c_0$ 上的二元函数 $d(x,y)=\sup_{n\geq 1}|x_n-y_n|$, 则

* $d$ 为良定义的度量.
* $(c_0,d)$ 完备.
* $\mathrm{span}(\{e_k\}_{k\in\mathbb Z_{\geq 1}})$ 为 $c_0$ 中非开非闭集.
* $\mathrm{span}(\{e_k\}_{k\in\mathbb Z_{\geq 1}})$ 在 $d$ 给出的拓扑的闭包下为 $c_0$. 
* **(留意此处!)** $\forall x\in c_0$, 存在唯一的 $\{x_k'\}_{k\in \mathbb Z_{\geq 1}}$ 使得 $x=\sum_{k\geq 1}x'_ke_k$. 换言之, $\sum_{k\geq 1}t_ke_k=0$ 当且仅当 $t_k\equiv 0$. 
* 从而 $c_0$ 上的线性函数为 $Tx=\sum_{k\geq 1}t_kx_k$ 形式, 其中 $\sum_{k\geq 1}|t_k|<\infty$. 

定义 $c$ 为收敛数列全体, 则

* 沿用以上的 $d$, $(c,d)$ 完备.
* $c$ 的线性无关组例如 $\{e_k\}_{k\in\mathbb Z_{\geq 1}}\cup\{(1,1,1,\ldots)\}$. 往后定义 $e_0=(1,1,\ldots)$
* $\mathrm{span}(\{e_k\}_{k\in\mathbb Z_{\geq 0}})$ 在 $d$ 给出的拓扑的闭包下为 $c$. 
* **(留意此处!)** $\forall x\in c$, 存在唯一的 $\{x_k'\}_{k\in \mathbb Z_{\geq 0}}$ 使得 $x=\sum_{k\geq 0}x'_ke_k$. 换言之, $\sum_{k\geq 0}t_ke_k=0$ 当且仅当 $t_k\equiv 0$. 
* 从而 $c$ 上的线性函数为 $Tx=\sum_{k\geq 0}t_kx_k$ 形式, 其中 $\sum_{k\geq 1}|t_k|<\infty$. 

第二个例子对初学者并不友好. 我们记 $d$ 为 $C([1,2])$ 上的二元函数, 定义为 $d(f,g)=\sup_{1\leq x\leq 2}|f(x)-g(x)|$. 有以下事实:

* Weierstrass 逼近定理: $\{1,x,x^2,\ldots\}$ 的闭包为 $C([1,2])$, 即对任意 $f\in C([1,2])$, 存在 $\{a_n\}_{n\geq 0}$ 使得 $f=\sum_{n\geq 0}a_n x^n$. 
* $\{x^n\}_{n\geq 0}$ 线性无关. 
* 因此,  $\dfrac{1}{x^m}$ 可由 $\{x^n\}_{n\geq 0}$ 逼近, 即 $\{x^m,x^{m+1},x^{m+1}\ldots\}$ 可逼近 $1$, 故闭包为 $C([1,2])$. 不难得到一个神奇的结论:
  1. $\{x^n\}_{n\geq 1}$ 中去掉任意有限个元素后仍在 $C([1,2])$ 中稠密. 
  2. 存在无穷组不全为 $0$ 的数列 $\{a_n\}_{n\geq 0}$ 使得 $\sum_{n\geq 0}a_nx^n\equiv 0$. 

记 $\prod_{i\in I}X_i$ 之 product topology 作 $(X,\tau_1)$, $\prod_{i\in I}X_i$ 之 box topology 作 $(X,\tau_2)$. 

* 使得投影算子 $p_i$ 连续的最粗拓扑为 $\tau_1$.
* $\tau_2$ 在 $|I|\geq \omega$ 时严格大于 $\tau_1$ (此处设恒存在 $U_i$ 使得 $\emptyset\subsetneq U_i\subsetneq X_i$).

记 $X$ 为 $\mathbb Z_{\geq 1}$ 个 $(\mathbb R,\tau_{\text{normal}})$ 之笛卡尔积, $\tau_i$ 定义如上, 则

* 选取 $(X,\tau _1)$, 则保证函数 $f:\mathbb R\to X,x\mapsto (x,x,x,\ldots)$ 连续之最粗拓扑为 $(\mathbb R,\tau_{\text{normal}})$. 
* 选取 $(X,\tau _1)$, 则保证函数 $f:\mathbb R\to X,x\mapsto (x,x,x,\ldots)$ 连续之最粗拓扑为 $(\mathbb R,\tau_{\text{discrete}})$. 注意到开集 $\prod_{k\geq 1} (x_0-k^{-1},x_0+k^{-1})$ 之原像为 $x_0$. 

**Ex1** 定义 $\ell^\infty$ 为有界数列全体, 以上的 $d$ 仍为 $\ell^\infty$ 上良定义的度量, $\ell^\infty$ 仍完备, 则

* 使得函数 $f:\mathbb R\to \ell^\infty$ 连续之最粗拓扑为 $(\mathbb R,\tau_{\text{discrete}})$.  

**Ex2** 对于上述 $(X,\tau_i)$ 是否均存在 $\{U_k\}_{k\in\mathbb Z_{\geq 1}}$ 使得

1. $U_1\subset U_2\subset\cdots U_k\subset U_{k+1}\subset\cdots$.
2. $\cup_{k\in\mathbb Z_{\geq 1}} U_k=X$.
3. $f^{-1}(U_k)=\emptyset$, $\forall k\in\mathbb Z_{\geq 1}$. 

