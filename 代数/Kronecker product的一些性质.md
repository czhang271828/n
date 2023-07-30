### Kronecker product的一些性质

##### Kronecker积引入

设$A=\begin{pmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{pmatrix}$, $B=\begin{pmatrix}b_{11}&b_{12}\\b_{21}&b_{22}\end{pmatrix}$, $X=\begin{pmatrix}x_{11}&x_{12}\\x_{21}&x_{22}\end{pmatrix}$, $Y=\begin{pmatrix}y_{11}&y_{12}\\y_{21}&y_{22}\end{pmatrix}$. 从而：

1. 矩阵方程$AX=Y$​等价于
   $$
   \begin{pmatrix}
   a_{11}&0&a_{12}&0\\
   0&a_{11}&0&a_{12}\\
   a_{21}&0&a_{22}&0\\
   0&a_{21}&0&a_{22}\\
   \end{pmatrix}\cdot\begin{pmatrix}
   x_1\\x_2\\x_3\\x_4
   \end{pmatrix}=\begin{pmatrix}
   y_1\\y_2\\y_3\\y_4
   \end{pmatrix}.
   $$

2. 矩阵方程$XB=Y$等价于
   $$
   \begin{pmatrix}
   b_{11}&b_{21}&0&0\\
   b_{12}&b_{22}&0&0\\
   0&0&b_{11}&b_{21}\\
   0&0&b_{12}&b_{22}\\
   \end{pmatrix}\cdot\begin{pmatrix}
   x_1\\x_2\\x_3\\x_4
   \end{pmatrix}=\begin{pmatrix}
   y_1\\y_2\\y_3\\y_4
   \end{pmatrix}.
   $$

3. 矩阵方程$AXB=Y$等价于
   $$
   \begin{pmatrix}
   a_{11}b_{11}&a_{11}b_{21}&a_{12}b_{11}&a_{12}b_{21}\\
   a_{11}b_{12}&a_{11}b_{22}&a_{12}b_{12}&a_{12}b_{22}\\
   a_{21}b_{11}&a_{21}b_{21}&a_{22}b_{11}&a_{22}b_{21}\\
   a_{21}b_{12}&a_{21}b_{22}&a_{22}b_{12}&a_{22}b_{22}\\
   \end{pmatrix}\cdot\begin{pmatrix}
   x_1\\x_2\\x_3\\x_4
   \end{pmatrix}=\begin{pmatrix}
   y_1\\y_2\\y_3\\y_4
   \end{pmatrix}.
   $$

实际上, 上式左端可写作分块矩阵形式
$$
\begin{pmatrix}
a_{11}b_{11}&a_{11}b_{21}&a_{12}b_{11}&a_{12}b_{21}\\
a_{11}b_{12}&a_{11}b_{22}&a_{12}b_{12}&a_{12}b_{22}\\
a_{21}b_{11}&a_{21}b_{21}&a_{22}b_{11}&a_{22}b_{21}\\
a_{21}b_{12}&a_{21}b_{22}&a_{22}b_{12}&a_{22}b_{22}\\
\end{pmatrix}=\begin{pmatrix}
a_{11}B^T&a_{12}B^T\\a_{21}B^T&a_{22}B^T
\end{pmatrix}.
$$
记作$A\otimes B^T$. 

##### Kronecker积性质

一般地, 设$P\in K^{k\times l}$, $Q\in K^{m\times n}$, 从而$P\otimes Q\in K^{km\times ln}$. 其形式为
$$
P\otimes Q=\begin{pmatrix}p_{11}Q&p_{12}Q&\cdots &p_{1l}Q\\p_{21}Q&p_{22}Q&\cdots&p_{2l}Q\\\vdots&\vdots&\ddots&\vdots\\p_{k1}Q&p_{k2}Q&\cdots &p_{kl}Q\\\end{pmatrix}.
$$
在维度允许的前提下, 有如下性质:

1. $\otimes$为二元运算, 满足分配律, 结合律. 
2. 满足双线性性, 即对$\otimes $两端自变量均线性. 
3. $(A\otimes B)\cdot(C\otimes D)=(A\cdot C)\otimes (B\cdot D)$.
4. 转置$(A\otimes B)^T=A^T\otimes B^T$.
5. 秩$\mathrm r(A\otimes B)=\mathrm r(A)\cdot\mathrm r(B)$.
6. 行列式$(\det A)^{\dim A}(\det B)^{\dim B}=\det(A\otimes B)$.
7. 迹$\mathrm{tr}(A\otimes B)=\mathrm{tr}(A)\mathrm{tr}(B)$.
8. 设$A$, $B$的特征值分别为$\{\lambda_i\}$, $\{\mu_i\}$, 对应的特征向量分别为$\{v_i\}$, $\{u_i\}$, 则$A\otimes B$的特征值为$\{\lambda_i\mu_j\}$, 对应的特征向量为$\{v_i\otimes u_j\}$. 
9. 由$5-9$可见$A\otimes B$与$B\times A$有相同的行列式, 秩, 迹, 以及特征值. 

##### 总结

实际上, 矩阵方程$AX=Y$与$XB=Y$的本质仍为线性代数, 因此可以化作简单的线性方程组问题. Kronecker积深刻地描述了该种转化关系. 