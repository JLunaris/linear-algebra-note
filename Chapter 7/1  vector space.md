
# Vector Space

> [!example] vector space
> 若集合 $V$ 同时满足以下条件：
> 1. 定义了称为 **vector addition** 和 **scalar multiplication** 的两种运算，使得：
>    ① closed under addition：$\forall \mathbf{u},\mathbf{v}\in V$，$\mathbf{u}+\mathbf{v}\in V$
>    ② closed under scaling：$\forall \mathbf{u}\in W$，$c\mathbf{u} \in W$（$c$ 是任意标量）
> 2. 满足以下 8 条公理（对于任意的 $\mathbf{u},\mathbf{v},\mathbf{w}\in V$，任意的标量 $a,b$）：
>    ① $\mathbf{u} + \mathbf{v} = \mathbf{v} + \mathbf{u}$
>    ② $(\mathbf{u} + \mathbf{v}) + \mathbf{w} = \mathbf{u} + (\mathbf{v} + \mathbf{w})$
>    ③ 存在 $\mathbf{0}\in V$，使得 $\mathbf{u} + \mathbf{0} = \mathbf{u}$
>    ④ 存在 $-\mathbf{u}\in V$，使得 $\mathbf{u} + (-\mathbf{u}) = \mathbf{0}$
>    ⑤ $1\mathbf{u}=\mathbf{u}$
>    ⑥ $(ab)\mathbf{u} = a(b\mathbf{u})$
>    ⑦ $a(\mathbf{u} + \mathbf{v}) = a\mathbf{u} + a\mathbf{v}$
>    ⑧ $(a + b)\mathbf{u} = a\mathbf{u} + b\mathbf{u}$
> 
> 则称 $V$ 是一个 **vector space**，$V$ 中的元素被称为 **vector**。

> 示例：常见的 vector space
> 
> 以下案例中，$m,n$ 为给定的正整数。
> 
> 【例1】$\mathbb{R}^n$ 是 vector space
> 
> 【例2】$\mathcal{M}_{m\times n}$ 是 vector space
> 原因：每个 $m\times n$ 矩阵都可以视为一个长度为 $mn$ 的向量，如图所示。
> ![[Pasted image 20260604160433.png|226]]
> 定义 vector addition 为矩阵加法，定义 scalar multiplication 为矩阵数乘。经测试满足 closed under addition 和 closed under scaling，也满足 8 条公理。
> 
> 【例3】所有 $n$ 次多项式构成的集合是 vector space
> 原因：任何 $n$ 次多项式都可以视为一个长度为 $n+1$ 的向量，如图所示。
> ![[Pasted image 20260604162919.png|346]]
> 定义 vector addition 为多项式加法，定义 scalar multiplication 为多项式数乘。经测试满足 closed under addition 和 closed under scaling，也满足 8 条公理。
> 
> 【例4】给定非空集合 $S$，记 $\mathcal{F}(S)$ 为所有从 $S$ 到 $\mathbb{R}$ 的函数所组成的集合，则函数空间 $\mathcal{F}(S)$ 是 vector space。
> 原因：每个函数都可以看成一个无限维向量（把每个自变量对应的函数值收集起来）。
> 定义 vector addition 为函数加法，定义 scalar multiplication 为函数数乘。经测试满足 closed under addition 和 closed under scaling，也满足 8 条公理。

# Isomorphism

> [!example] isomorphism（同构）
> $V$ 和 $W$ 是 vector space。若存在一个==线性变换== $T:V\rightarrow W$ 是 one-to-one 且 onto 的（即 invertible 的），则称 $T$ 是一个 **isomorphism**，称 $V$ 和 $W$ 是 **isomorphic** 的，记作 $V \cong W$。

> $W$ 和 $V$ 中的元素具有一一对应的关系。
> ![[Pasted image 20260604174530.png|276]]

> 示例：向量空间 $P_2=\{a+bx+cx^2\mid a,b,c\in \mathbb{R}\}$ 和 $\mathbb{R}^3$ 是 isomorphic 的。
> 
> 证明：定义映射 $T:P_2\rightarrow \mathbb{R}^3$ 为 $T(a+bx+cx^2)=\begin{bmatrix}a \\ b \\ c\end{bmatrix}$。
> ①证明 $T$ 是线性映射
>    - 对任意 2 次多项式 $p=a+bx+cx^2$，$q=d+ex+fx^2$，有 $T(p+q)=T((a+d)+(b+e)x+(c+f)x^2)=\begin{bmatrix}a+d \\ b+e \\ c+f\end{bmatrix}=\begin{bmatrix}a \\ b \\ c\end{bmatrix}+\begin{bmatrix}d \\ e \\ f\end{bmatrix}=T(p)+T(q)$
>    - 同理，对任意标量 $k$，$T(kp)=kT(p)$
> ②证明 $T$ 是 one-to-one 的：显然每个多项式对应唯一一个向量
> ③证明 $T$ 是 onto 的：显然每个向量都有对应的多项式
> 综上，$T$ 是一个同构，$P_2\cong \mathbb{R}^3$。

# Inner Product

> [!example] inner product
> vector space $V$ 上的 **inner product** 是一个函数，输入 $V$ 中任意两个向量 $\mathbf{u}$ 和 $\mathbf{v}$，输出一个标量，记作 ==$\langle\mathbf{u}, \mathbf{v}\rangle$==，且满足以下 4 条公理：
> 1. 若 $\mathbf{u} \neq \mathbf{0}$，则 $\langle\mathbf{u}, \mathbf{u}\rangle > 0$
> 2. $\langle\mathbf{u}, \mathbf{v}\rangle = \langle\mathbf{v}, \mathbf{u}\rangle$
> 3. $\langle\mathbf{u} + \mathbf{v}, \mathbf{w}\rangle = \langle\mathbf{u}, \mathbf{w}\rangle + \langle\mathbf{v}, \mathbf{w}\rangle$
> 4. $\langle a\mathbf{u}, \mathbf{v}\rangle = a\langle\mathbf{u}, \mathbf{v}\rangle$

> [!NOTE] 
> dot product 是 inner product 的一种特殊情况。

> 案例：frobenius inner product
> 
> vector space $\mathcal{M}_{m\times n}$（$m,n$ 为给定的正整数）中，定义 inner product 为 $\langle A, B \rangle = \sum\limits_{i=1}^{m} \sum\limits_{j=1}^{n} a_{ij} b_{ij}$，也就是==把两个矩阵对应位置的元素分别相乘，再全部相加==。称为 **frobenius inner product**。例如，$A=\begin{bmatrix}1 & 2 \\ 3 & 4\end{bmatrix}$，$B=\begin{bmatrix}5 & 6 \\ 7 & 8\end{bmatrix}$，则 $\langle A, B \rangle = 1\cdot 5+2\cdot 6+ 3 \cdot 7 + 4 \cdot 8=70$。
> 
> 定义 **frobenius norm**，也就是把矩阵扁平化为一个向量，然后计算向量的 2-norm。例如，$A=\begin{bmatrix}1 & 2 \\ 3 & 4\end{bmatrix}$，$\|A\|=\sqrt{1^2+2^2+3^2+4^2}$。
> 
> 显然，$\|A\|^2=\langle A, A \rangle$。
