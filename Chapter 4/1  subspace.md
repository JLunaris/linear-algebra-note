
# Subspace

若一个==非空==向量集 $W$ 同时满足以下条件：
1. ==closed under addition==：$\forall \mathbf{u},\mathbf{v}\in W$，$\mathbf{u}+\mathbf{v}\in W$
2. ==closed under scaling==：$\forall \mathbf{u}\in W$，$c\mathbf{u} \in W$（$c$ 是任意标量）
则称 $W$ 是一个 **subspace**。

换句话说，把非空向量集 $W$ 里的任意向量拿出来做 ==linear combination==，得到的结果仍属于 $W$，则称 $W$ 是一个 **subspace**。

> **等价定义**：同时满足以下 3 个条件的向量集 $W$ 称为 subspace：
> ① $\mathbf{0}\in W$
> ② $\forall \mathbf{u},\mathbf{v}\in W$，$\mathbf{u}+\mathbf{v}\in W$
> ③ $\forall \mathbf{u}\in W$，$c\mathbf{u} \in W$（$c$ 是任意标量）
> 
> 条件①是为了保证非空。在非空前提下，③可以推出①（令 $c=0$ 即得）。

> [!NOTE] 
> 任何 subspace 都包含 $\mathbf{0}$（任何 subspace 都一定经过原点）

> 案例：判断 vector set 是不是 subspace
> 
> 【例1】$W = \left\{ \begin{bmatrix} w_1 \\ w_2 \\ w_3 \end{bmatrix} : 6w_1 - 5w_2 + 4w_3 = 0 \right\}$
> 
> 解：①对 $W$ 中任意的 $\mathbf{u}=\begin{bmatrix}u_1 \\ u_2 \\ u_3\end{bmatrix}$，$\mathbf{v}=\begin{bmatrix}v_1 \\ v_2 \\ v_3\end{bmatrix}$，$\mathbf{u}+\mathbf{v}=\begin{bmatrix}u_1+v_1 \\ u_2+v_2 \\ u_3+v_3\end{bmatrix}$
> 将 $\mathbf{u}+\mathbf{v}$ 代入等式得 $\begin{aligned}6(u_1+v_1)-5(u_2+v_2)+4(u_3+v_3)=(6u_1-5u_2+4u_3)+(6v_1-5v_2+4v_3)=0+0=0\end{aligned}$
> 因此 $\mathbf{u}+\mathbf{v}\in W$
> ②对 $W$ 中任意的 $\mathbf{u}=\begin{bmatrix}u_1 \\ u_2 \\ u_3\end{bmatrix}$，$c\mathbf{u}=\begin{bmatrix}cu_1 \\ cu_2 \\ cu_3\end{bmatrix}$
> 将 $c\mathbf{u}$ 代入等式得 $6(cu_1)-5(cu_2)+4(cu_3)=c(6u_1-5u_2+4u_3)=c(0)=0$
> 因此 $c\mathbf{u}\in W$
> 综上，$W$ 是 subspace。
> 
> 【例2】$W=\left\{ c\mathbf{w} : c\in \mathbb{R} \right\}$，$\mathbf{w}$ 是 $\mathbb{R}^3$ 中的一个非零向量。
> 
> 解：是 subspace。
> ![[Pasted image 20260329142237.png|438]]
> 
> 【例3】$V=\left\{ \begin{bmatrix}v_1 \\ v_2\end{bmatrix}: v_1\ge 0 \text{ 且 } v_2\ge 0 \right\}$，$W=\left\{ \begin{bmatrix}w_1 \\ w_2\end{bmatrix}: w_1^2=w_2^2 \right\}$
> 
> 解：都不是 subspace。
> ![[Pasted image 20260329143954.png|587]]
> 
> 【例4】$\mathbb{R}^n$ 是 subspace。
> 
> 【例5】向量集 $\left\{ \mathbf{0} \right\}$ 是 subspace。

> [!NOTE] zero subspace
> 向量集 $\left\{ \mathbf{0} \right\}$ 是 subspace，称为 **zero subspace**。

### Subspace vs Span

##### span 一定是 subspace

> [!important] Theorem
> 任何向量集的 span 都是 subspace。

> 证明：设 $S=\{\mathbf{w}_1,\mathbf{w}_2,\cdots,\mathbf{w}_k\}$
> ①$\forall \mathbf{u},\mathbf{v}\in \text{Span}\ S$，有 $\mathbf{u}=a_1\mathbf{w}_1+a_2\mathbf{w}_2+\cdots+a_k\mathbf{w}_k$，$\mathbf{v}=b_1\mathbf{w}_1+b_2\mathbf{w}_2+\cdots+b_k\mathbf{w}_k$
>    则 $\mathbf{u}+\mathbf{v}=(a_1+b_1)\mathbf{w}_1+(a_2+b_2)\mathbf{w}_2+\cdots+(a_k+b_k)\mathbf{w}_k \in \text{Span}\ S$
>    知 $\text{Span}\ S$ 满足 closed under addition
> ②$\forall \mathbf{u}\in \text{Span}\ S$，有 $\mathbf{u}=a_1\mathbf{w}_1+a_2\mathbf{w}_2+\cdots+a_k\mathbf{w}_k$
>    则 $c\mathbf{u}=(ca_1)\mathbf{w}_1+(ca_2)\mathbf{w}_2+\cdots+(ca_k)\mathbf{w}_k\in \text{Span}\ S$
>    知 $\text{Span}\ S$ 满足 closed under scaling
> 综上，$\text{Span}\ S$ 是 subspace。

##### subspace 可以用 span 表示

> [!important] Theorem
> 任何 subspace 都可以写成某向量集的 span。

> 证明：①每个 non-zero subspace 都有 basis（后面证明），non-zero subspace 可以写成它的 basis 的 span。 ②zero subspace $\{\mathbf{0}\}$ 可以写成它本身的 span。

### 与矩阵有关的 subspace

##### Column Space 和 Row Space

- 矩阵 $A$ 的 columns 的 span 称为 $A$ 的 **column space**，记作 $\text{Col}\ A$。
- 矩阵 $A$ 的 rows 的 span 称为 $A$ 的 **row space**，记作 $\text{Row}\ A$。

> [!important] Theorem
> 矩阵的 column space 和 row space 都是 subspace。

> 原因：span 是 subspace。

---

> [!NOTE] 从 linear transformation 角度理解 column space
> 设 $A$ 是 $m\times n$ 矩阵，有：$\text{Col}\ A$ = ==$\{A\mathbf{v} \mid \mathbf{v}\in \mathbb{R}^n \}$== = ==$A$ 所对应函数的 range==

> [!NOTE] 
> 线性方程组 $A\mathbf{x}=\mathbf{b}$ 有解 $\iff$ $\mathbf{b}$ 在 $A$ 的 columns 的 span 中 $\iff$ ==$\mathbf{b}\in \text{Col}\ A$==

> 例：$A=\begin{bmatrix}1 & 2 & 1 & -1 \\ 2 & 4 & 0 & -8 \\ 0 & 0 & 2 & 6 \end{bmatrix}$，问：$\mathbf{u}=\begin{bmatrix}2 \\ 1 \\ 1\end{bmatrix}$ 是否属于 $\text{Col}\ A$，$\mathbf{v}=\begin{bmatrix}2 \\ 1 \\ 3\end{bmatrix}$ 是否属于 $\text{Col}\ A$。
> 
> 解：本质上是问 $A\mathbf{x}=\mathbf{u}$ 和 $A\mathbf{x}=\mathbf{v}$ 是否有解。
> ![[Pasted image 20260329214023.png|567]]

##### Null Space

矩阵 $A$ 的 **null space** 定义为方程 $A\mathbf{x}=\mathbf{0}$ 的解集，记作 $\text{Null}\ A$。写成集合的形式为：
$$\text{Null}\ A=\{\mathbf{x} \mid A\mathbf{x}=\mathbf{0}\}$$
null space 表示“==所有被矩阵映射到 $\mathbf{0}$ 的输入向量的集合==”，这也是 “null” 这一名称的由来。

> 任何矩阵都有 null space（因为方程 $A\mathbf{x}=\mathbf{0}$ 至少有 $\mathbf{x}=\mathbf{0}$ 作为它的一个解)

> [!important] Theorem
> 矩阵的 null space 是 subspace。

> 证明：①$\forall \mathbf{u},\mathbf{v}\in \text{Null}\ A$，有 $A\mathbf{u}=\mathbf{0}$，$A\mathbf{v}=\mathbf{0}$
> 由于 $A(\mathbf{u}+\mathbf{v})=A\mathbf{u}+A\mathbf{v}=\mathbf{0}$，因此 $\mathbf{u}+\mathbf{v}\in \text{Null}\ A$
> 知 $\text{Null}\ A$ 满足 closed under addition
> ②$\forall \mathbf{u}\in \text{Null}\ A$，有 $A\mathbf{u}=\mathbf{0}$
> 由于 $A(c\mathbf{u})=c(A\mathbf{u})=c\mathbf{0}=\mathbf{0}$，因此 $c\mathbf{u}\in\text{Null}\ A$
> 知 $\text{Null}\ A$ 满足 closed under scaling
> 综上，$\text{Null}\ A$ 是 subspace。

> 例：求矩阵 $A=\begin{bmatrix}1 & 2 & 1 & -1 \\ 2 & 4 & 0 & -8 \\ 0 & 0 & 2 & 6 \end{bmatrix}$ 的 null space 的一个 generating set
> 
> 解：先求矩阵 $A$ 的 null space，即求 $A\mathbf{x}=\mathbf{0}$ 的解集
> 解得 $\text{Null}\ A=\left\{ \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \end{bmatrix} : \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \end{bmatrix} = x_2\begin{bmatrix} -2 \\ 1 \\ 0 \\ 0 \end{bmatrix}+x_4\begin{bmatrix} 4 \\ 0 \\ -3 \\ 1 \end{bmatrix}\right\}=\text{Span}\left\{ \begin{bmatrix} -2 \\ 1 \\ 0 \\ 0\end{bmatrix}, \begin{bmatrix} 4 \\ 0 \\ -3 \\ 1\end{bmatrix} \right\}$
> 故 $\left\{ \begin{bmatrix} -2 \\ 1 \\ 0 \\ 0\end{bmatrix}, \begin{bmatrix} 4 \\ 0 \\ -3 \\ 1\end{bmatrix} \right\}$ 是 $\text{Null}\ A$ 的一个 generating set。

---

> [!important] Theorem
> 若矩阵 $A$ 对应的函数是 one-to-one 的，则 $\text{Null}\ A=\{ \mathbf{0} \}$。

> 证明：$A$ is one-to-one $\implies$ 方程 $A\mathbf{x}=\mathbf{0}$ 的唯一解是 $\mathbf{x}=\mathbf{0}$ $\implies$ $\text{Null}\ A=\{ \mathbf{0} \}$

##### 与 elementary row operation 的关系

> [!important] Theorem
> elementary row operation 不会改变矩阵的 **row space** 和 **null space**，但可能改变矩阵的 **column space**。 

> 原因：
> - 对 row 做 interchange / scaling(non zero) / row addition 显然都不会改变 rows 的 span，但可能改变 columns 的 span，例如：$\begin{bmatrix}1 & 1 \\ 1 & 1\end{bmatrix} \xrightarrow{-r_1+r_2} \begin{bmatrix}1 & 1 \\ 0 & 0\end{bmatrix}$，columns 的 span 从直线 $y=x$ 变成直线 $y=0$
> - 对 $\begin{bmatrix}A \mid \mathbf{0}\end{bmatrix}$ 做 elementary row operation 不会改变方程 $A\mathbf{x}=\mathbf{0}$ 的解集 $\implies$ 对 $A$ 做 elementary row operation 不会改变方程 $A\mathbf{x}=\mathbf{0}$ 的解集，即不会改变 $\text{Null}\ A$

> [!NOTE] 推论
> 设矩阵 $A$ 的 RREF 是 $R$，则：
> - $\text{Row}\ A=\text{Row}\ R$
> - $\text{Null}\ A=\text{Null}\ R$
> - $\text{Col}\ A$ 不一定等于 $\text{Col}\ R$

# Basis

> [!example] subspace 的 basis
> 对于 subspace $V$，若向量集 $B$ 同时满足以下条件：
> 
> 1. ==independent==
> 2. 是 $V$ 的 ==generating set==（即 $\text{Span}\ B=V$）
> 
> 则称 $B$ 是 $V$ 的一个 **basis**。

> 案例：
> ① $\{\mathbf{e}_1,\mathbf{e}_2,\cdots,\mathbf{e}_n\}$ 是 $\mathbb{R}^n$ 的一个 basis。
> ② ==basis 不是唯一的==，例如 $\left\{ \begin{bmatrix}1 \\ 1\end{bmatrix}, \begin{bmatrix}1 \\ -1\end{bmatrix} \right\}$、$\left\{ \begin{bmatrix}1 \\ 3\end{bmatrix}, \begin{bmatrix}-3 \\ 1\end{bmatrix} \right\}$、$\left\{ \begin{bmatrix}1 \\ 1\end{bmatrix}, \begin{bmatrix}1 \\ 2\end{bmatrix} \right\}$ 都是 $\mathbb{R}^2$ 的 basis。之前讲过，任意 $n$ 个 independent 向量都可以 span 整个 $\mathbb{R}^n$，因此任意 $n$ 个 independent 向量构成的集合都是 $\mathbb{R}^n$ 的 basis。

### 每个 non-zero subspace 都有 basis

> [!important] Theorem
> 每个 non-zero subspace 都有 basis。

> 证明：对于 non-zero subspace $V$，取其中一个非零向量 $\mathbf{v}$ 构成集合 $S=\{\mathbf{v}\}$，则 $S$ 显然是 independent 的。由 Extension Theorem 知，$V$ 的 independent 子集 $S$ 要么是 basis，要么可以通过加入一些向量变成 basis。

### 矩阵的 pivot columns（取自原矩阵） 构成其 column space 的一个 basis

> [!important] Theorem
> 矩阵的 pivot columns（==取自原矩阵==）构成其 column space 的一个 basis。

> 证明：①pivot columns 一定 independent   ②non-pivot column 都可以写成 pivot columns 的 linear combination，因此 non-pivot column 都是 span 冗余向量，仅需 pivot columns 就可以 span 整个 column space。
> 综上，pivot columns 是 column space 的一个 basis。

> 案例：
> ![[Pasted image 20260401153452.png|511]]
> 则 $\text{Span}\ \left\{ \begin{bmatrix}1 \\ -1 \\ 2 \\ 3\end{bmatrix}, \begin{bmatrix}-1 \\ 1 \\ -3 \\ 2\end{bmatrix}, \begin{bmatrix}2 \\ 2 \\ 2 \\ 0\end{bmatrix} \right\}=\text{Col}\ A$， $\left\{ \begin{bmatrix}1 \\ -1 \\ 2 \\ 3\end{bmatrix}, \begin{bmatrix}-1 \\ 1 \\ -3 \\ 2\end{bmatrix}, \begin{bmatrix}2 \\ 2 \\ 2 \\ 0\end{bmatrix} \right\}$ 是 $\text{Col}\ A$ 的一个 basis。

### Three Theorems of Basis

> [!NOTE] 引理（与 span 有关的性质）
> 1. $S\subseteq \text{Span}\ S$ （推论：==subspace 的 basis 一定 $\subseteq$ subspace==）
> 2. $S' \subseteq \text{Span}\ S$ $\iff$ $\text{Span}\ S' \subseteq \text{Span}\ S$
>   > ![[Pasted image 20260401160830.png|240]]
>   > 深绿色-$S'$，蓝色-$\text{Span}\ S$，浅绿色-$\text{Span}\ S'$

> 证明：
> 命题1：trivial
> 命题2：**左推右**：$S' \subseteq \text{Span}\ S$，而 $\text{Span}\ S$ 是 subspace，因此把 $S'$ 里的任意向量拿出来做 linear combination，得到的结果仍属于 $\text{Span}\ S$，即 $\text{Span}\ S' \subseteq \text{Span}\ S$。**右推左**：$S'\subseteq \text{Span}\ S'$，而 $\text{Span}\ S' \subseteq \text{Span}\ S$，故 $S' \subseteq \text{Span}\ S$。

##### 一个 subspace 的所有 basis 的大小相同

> [!important] Theorem
> subspace $V$ 的任意两个 basis 都具有相同个数的向量。

> 证明：略。

> [!example] subspace 的 dimension
> 将 subspace $V$ 的 ==basis 的元素个数==称为 $V$ 的 **dimension**，记作 $\text{dim}\ V$。
> 
> 特别地，约定 zero-subspace 的 dimension 为 $0$。

> 【例】求 subspace $V = \left\{ \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \end{bmatrix}  : x_1 - 3x_2 + 5x_3 - 6x_4 = 0 \right\}$ 的 dimension。
> 
> 解：dimension 的定义是 basis 的元素个数，需要求一个 basis。
> 解线性方程组，解得 $\begin{bmatrix}x_1 \\ x_2 \\ x_3 \\ x_4\end{bmatrix} = \begin{bmatrix} 3x_2-5x_3+6x_4 \\ x_2 \\ x_3 \\ x_4 \end{bmatrix} = x_2 \begin{bmatrix} 3 \\ 1 \\ 0 \\ 0 \end{bmatrix} + x_3 \begin{bmatrix} -5 \\ 0 \\ 1 \\ 0 \end{bmatrix} + x_4 \begin{bmatrix} 6 \\ 0 \\ 0 \\ 1 \end{bmatrix}$
> 因此 $V=\text{Span}\left\{\begin{bmatrix}3 \\ 1 \\ 0 \\ 0\end{bmatrix},\begin{bmatrix}-5 \\ 0 \\ 1 \\ 0\end{bmatrix},\begin{bmatrix}6 \\ 0 \\ 0 \\ 1\end{bmatrix}\right\}$
> 这三个向量显然 independent，因此 $\text{dim}\ V=3$。

> [!NOTE] 
> $\mathbb{R}^m$ 的 dimension 为 $m$。

> 证明：显然 $\{\mathbf{e}_1,\mathbf{e}_2,\cdots,\mathbf{e}_m\}$ 是 $\mathbb{R}^m$ 的一个 basis，因此 $\mathbb{R}^m$ 的 dimension 为 $m$。

##### basis 是最小的 generating set

> [!important] (Reduction Theorem)
> non-zero subspace $V$ 的任意一个 generating set，要么是 basis，要么可以通过删去一些向量变成 basis。

> 助记：==generating set 中一定含有 basis==。

> 证明：设 $S=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$ 是 $V$ 的一个 generating set，即 $\text{Span}\ S=V$。
> - 若 $S$ independent，则根据定义 $S$ 是 $V$ 的 basis。
> - 若 $S$ dependent，设 $A=\begin{bmatrix}\mathbf{u}_1 & \mathbf{u}_2 & \cdots & \mathbf{u}_k\end{bmatrix}$，有 $\text{Span}\ S=\text{Col}\ A=V$。
>    而 $A$ 的 pivot columns 构成 $\text{Col}\ A$ 的一个 basis（前面已证明），因此 $S$ 可以通过删去所有 non-pivot column 变成 $V$ 的一个 basis。

> 示例：$\mathcal{S} = \left\{ \begin{bmatrix} 1 \\ 2 \\ 1 \\ 1 \end{bmatrix}, \begin{bmatrix} 2 \\ 4 \\ 1 \\ 1 \end{bmatrix}, \begin{bmatrix} 1 \\ -1 \\ 0 \\ 1 \end{bmatrix}, \begin{bmatrix} 2 \\ 1 \\ 1 \\ 2 \end{bmatrix}, \begin{bmatrix} 1 \\ -1 \\ 2 \\ 1 \end{bmatrix} \right\}$ 是 subspace $V$ 的一个 generating set，将其写为矩阵形式 $A = \begin{bmatrix}1 & 2 & 1 & 2 & 1 \\2 & 4 & -1 & 1 & -1 \\1 & 2 & 0 & 1 & 2 \\1 & 2 & 1 & 2 & 1\end{bmatrix}\xrightarrow{RREF} \begin{bmatrix}1 & 2 & 0 & 1 & 0 \\0 & 0 & 1 & 1 & 0 \\0 & 0 & 0 & 0 & 1 \\0 & 0 & 0 & 0 & 0\end{bmatrix}$，pivot column 是第1/3/5 列，因此仅保留原矩阵第1/3/5 列，形成的集合 $\left\{ \begin{bmatrix} 1 \\ 2 \\ 1 \\ 1 \end{bmatrix}, \begin{bmatrix} 1 \\ -1 \\ 0 \\ 1 \end{bmatrix}, \begin{bmatrix} 1 \\ -1 \\ 2 \\ 1 \end{bmatrix} \right\}$ 是 subspace $V$ 的一个 basis。

> [!important] 推论
> subspace $V$ 的 dimension 为 $k$，则 $V$ 的 generating set 的元素个数一定 $\ge k$。

> [!NOTE] 
> 要 generate $\mathbb{R}^m$，至少需要 $m$ 个向量。

> 证明：因为 $\mathbb{R}^m$ 的 dimension 为 $m$（前面已证明）。

##### basis 是 subspace 中最大的 independent 向量集

> [!important] (Extension Theorem)
> non-zero subspace $V$ 的任意一个 independent 子集，要么是 basis，要么可以通过加入一些向量变成 basis。

> 助记：independent 子集——==要么是 basis，要么正在变成 basis（通过加入一些向量）==。

> 证明：设 $S=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}\subseteq V$，且 $S$ independent。
> - 若 $\text{Span}\ S=V$，则根据定义 $S$ 是 $V$ 的 basis。
> - 若 $\text{Span}\ S\neq V$，由于 $S\subseteq V$，根据 subspace 定义知 $\text{Span}\ S\subseteq V$，因此 $\text{Span}\ S\subset V$
>    任取 $\mathbf{v}_1\in V$ 且 $\mathbf{v}_1\notin \text{Span}\ S$，则 $S'=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k,\mathbf{v}_1\}$ independent（因为 $\mathbf{v}_1$ 不是"Span冗余向量"），且 $\text{Span}\ S' \subseteq V$。若 $\text{Span}\ S'=V$，则 $S'$ 是 $V$ 的一个 basis；若 $\text{Span}\ S'\subset V$，则：任取 $\mathbf{v}_2\in V$ 且 $\mathbf{v}_2\notin \text{Span}\ S'$，则 $S''=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k,\mathbf{v}_1,\mathbf{v}_2\}$ independent，且 $\text{Span}\ S'' \subseteq V$ ……
>    重复以上操作，直到 $S$ 变成 $V$ 的 generating set（因而变成 $V$ 的一个 basis）。
>    上述操作一定可以在有限步内完成，因为每一步都增加 independent 向量，而 $V\subseteq \mathbb{R}^m$（$V$ 是 $\mathbb{R}^m$ 的 subspace），$\mathbb{R}^m$ 中最多可以选出 $m$ 个向量构成 independent 向量组。
>    因此 $S$ 可以通过加入一些向量变成 basis。
>    ![[Pasted image 20260402175923.png|212]]
>    图示：通过加入“蓝圈之外、绿圈之内的向量”逐步扩大 $\text{Span}\ S$，直到占满 $V$。

> [!important] 推论
> subspace $V$ 的 dimension 为 $k$，则 $V$ 中最多能选出 $k$ 个向量构成 independent 向量集。

> [!NOTE] 
> $\mathbb{R}^m$ 中最多能选出 $m$ 个向量构成 independent 向量组。

> 证明：因为 $\mathbb{R}^m$ 的 dimension 为 $m$（前面已证明）。

### subspace 中的 subspace

> [!important] Theorem
> $V$ 和 $W$ 都是 subspace，若 ==$V\subseteq W$==，有以下结论：
> 1. $\text{dim}\ V\le \text{dim}\ W$
> 2. $\text{dim}\ V=\text{dim}\ W$ $\iff$ $V=W$

> 直观理解：
> 想象在 $\mathbb{R}^3$ 中，$V$ 是一条直线（dim = 1），$W$ 是一个平面（dim = 2）。
> 很明显，如果直线在平面内（$V\subseteq W$），则 $\text{dim}\ V\le \text{dim}\ W$。
> 如果 $V$ 扩张为一个平面（$\text{dim}\ V=\text{dim}\ W$），且 $V\subseteq W$，那它们只能是**同一个平面**。
> 
> ![[Pasted image 20260403114433.png|359]]

> 证明：
> ![[Pasted image 20260403142501.png|222]]
> 设 $B_V$ 是 $V$ 的一个 basis，则 $\text{Span}\ B_V=V$ 且 $B_V$ independent
> 知 $B_V \subseteq V \subseteq W$（因为之前讲过的引理：subspace 的 basis 一定 $\subseteq$ subspace）
> 在 $W$ 中，$B_V$ 是其 independent 子集。由 Extension Theorem 知，$B_V$ 要么是 $W$ 的 basis，要么可以通过加入一些向量变成 $W$ 的 basis。
> 故 $\text{dim}\ V\le \text{dim}\ W$。**命题1得证**。
> 若 $\text{dim}\ V=\text{dim}\ W$（记它们 $=k$），则 $W$ 的 basis 最多含有 $k$ 个向量，而 $W$ 的 independent 子集 $B_V$ 含有 $k$ 个向量，因此 $B_V$ 就是 $W$ 的 basis。
> 故 $V=W$。**命题2得证**。

### 判断向量集是否是 basis

判断向量集 $B$ 是不是 subspace $V$ 的 basis，最直觉的方法是**根据定义检查**，即检查 $B$ 是否：①independent ②是 $V$ 的 generating set。条件①容易检查，但条件②不容易检查。

我们有以下定理来判断向量集是否是 basis：

> [!important] Theorem
> subspace $V$ 的 dimension 为 $k$，==$S$ 恰好有 $k$ 个向量==。则：
> - $S$ 是 $V$ 的 independent 子集 $\implies$ $S$ 是 $V$ 的一个 basis
> - $S$ 是 $V$ 的 generating set $\implies$ $S$ 是 $V$ 的一个 basis

> 证明：由 Extension Theorem 和 Reduction Theorem 即得。

> 案例：$V = \left\{ \begin{bmatrix} v_1 \\ v_2 \\ v_3 \\ v_4 \end{bmatrix} : v_1 + v_2 + v_4 = 0 \right\}$，判断 $\mathcal{B} = \left\{ \begin{bmatrix} 1 \\ -1 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 1 \\ 0 \\ 1 \\ -1 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 1 \\ -1 \end{bmatrix} \right\}$ 是否是 $V$ 的 basis。
> 解：
> **step 1**（找一个 basis，求 $\text{dim}\ V$）：$\begin{bmatrix} v_1 \\ v_2 \\ v_3 \\ v_4 \end{bmatrix} = \begin{bmatrix} -v_2 - v_4 \\ v_2 \\ v_3 \\ v_4 \end{bmatrix} = v_2 \begin{bmatrix} -1 \\ 1 \\ 0 \\ 0 \end{bmatrix} + v_3 \begin{bmatrix} 0 \\ 0 \\ 1 \\ 0 \end{bmatrix} + v_4 \begin{bmatrix} -1 \\ 0 \\ 0 \\ 1 \end{bmatrix}$，故 $V=\text{Span}\left\{ \begin{bmatrix} -1 \\ 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} -1 \\ 0 \\ 0 \\ 1 \end{bmatrix} \right\}$，这三个向量显然 independent，故 $\text{dim}\ V=3$
> **step 2**（检查 $B$ 是否有 $\text{dim}\ V$ 个向量）：是
> **step 3**（检查 $B$ 是否是 $V$ 的 independent 子集）：
> 首先将 $B$ 中的每个向量依次代入方程 $v_1 + v_2 + v_4 = 0$，都满足，因此 $B\subseteq V$。
> 然后检查 $B$ 是否 independent， $\begin{bmatrix} 1 & 1 & 0 \\-1 & 0 & 1 \\1 & 1 & 1 \\0 & -1 & -1 \end{bmatrix}\xrightarrow{RREF} \begin{bmatrix} 1 & 0 & 0 \\0 & 1 & 0 \\0 & 0 & 1 \\0 & 0 & 0 \end{bmatrix}$，知 $B$ independent。
> 综上，$B$ 是 $V$ 的 basis。

# 与矩阵有关的 subspace 的 basis 和 dimension

### Column Space 的 basis 和 dimension

> [!important] $\text{Col}\ A$ 的 basis 和 dimension
> - **One of Bases**：$A$ 的 pivot columns（取自原矩阵）
> - **Dimension**：$\text{dim}(\text{Col}\ A)=\text{rank}\ A$

> 证明：$\text{dim}(\text{Col}\ A)$ = pivot columns 的个数 = $\text{rank}\ A$

### Row Space 的 basis 和 dimension

> [!important] $\text{Row}\ A$ 的 basis 和 dimension
> - **One of Bases**：$A$ 的 RREF 的 non-zero rows
> - **Dimension**：$\text{dim}(\text{Row}\ A)=\text{rank}\ A$

> 证明：
> ① 设 $A$ 的 RREF 为 $R$。
>    ![[Pasted image 20260404181345.png|525]]
>    - elementary row operation 不会改变矩阵的 row space，因此 $\text{Row}\ A=\text{Row}\ R$
>    - ==$R$ 的 non-zero rows 一定 independent==（因为每个 non-zero row 都有 leading entry，其他行在这一列都是 $0$，导致其他行无法线性组合出这一行），$R$ 的 non-zero rows 可以 span 整个 $\text{Row}\ R$，因此 $R$ 的 non-zero rows 是 $\text{Row}\ R$ 的一个 basis
>    - 而 $\text{Row}\ A=\text{Row}\ R$，因此 $R$ 的 non-zero rows 是 $\text{Row}\ A$ 的一个 basis
> ② $\text{dim}(\text{Row}\ A)$ = RREF 中 non-zero rows 的个数  = $\text{rank}\ A$

### Null Space 的 basis 和 dimension

> [!important] $\text{Null}\ A$ 的 basis 和 dimension
> - **One of Bases**：$A\mathbf{x}=\mathbf{0}$ 通解的 parametric representation 中，每个与 free variable 相乘的向量
> - **Dimension**：$\text{dim}(\text{Null}\ A)=\text{nullity}\ A$

> 示例：$A = \begin{bmatrix}3 & 1 & -2 & 1 & 5 \\1 & 0 & 1 & 0 & 1 \\-5 & -2 & 5 & -5 & -3 \\-2 & -1 & 3 & 2 & -10\end{bmatrix}$，求 $\text{null}\ A$ 的一个 basis。
> 解：求解 $A\mathbf{x}=\mathbf{0}$ 以求出 $\text{null}\ A$。
> $A$ 的 RREF = $\begin{bmatrix}1 & 0 & 1 & 0 & 1 \\0 & 1 & -5 & 0 & 4 \\0 & 0 & 0 & 1 & -2 \\0 & 0 & 0 & 0 & 0\end{bmatrix}$。方程组化简为：$\begin{aligned}x_1 + x_3 + x_5 &= 0 \\x_2 - 5x_3 + 4x_5 &= 0 \\x_4 - 2x_5 &= 0\end{aligned}$
> 通解的 parametric representation 为：$\begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5 \end{bmatrix} = \begin{bmatrix} -x_3-x_5 \\ 5x_3-4x_5 \\ x_3 \\ 2x_5 \\ x_5 \end{bmatrix} = x_3 \begin{bmatrix} -1 \\ 5 \\ 1 \\ 0 \\ 0 \end{bmatrix} + x_5 \begin{bmatrix} -1 \\ -4 \\ 0 \\ 2 \\ 1 \end{bmatrix}$
> $\left\{\begin{bmatrix} -1 \\ 5 \\ 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} -1 \\ -4 \\ 0 \\ 2 \\ 1 \end{bmatrix}\right\}$ 是 $\text{null}\ A$ 的一个 basis

> 证明：
> ① $A\mathbf{x}=\mathbf{0}$ 通解的 parametric representation 中，绝对不会有常数项（因为增广矩阵 $\begin{bmatrix}A \mid \mathbf{0}\end{bmatrix}\xrightarrow{RREF}\begin{bmatrix}R \mid \mathbf{0}\end{bmatrix}$，最右列一定全是 $0$），因此 parametric representation 中每个与 free variable 相乘的向量，它们的 span = $\text{nullity}\ A$。
> 接下来要证明这些向量 independent。例如上例中 $x_3$ 和 $x_5$ 是 free variable，则观察与之相乘的向量：在第 3 行，只有第一个向量有数字 $1$，其余向量都是 $0$；在第 5 行，只有第二个向量有数字 $1$，其余向量都是 $0$。这就导致了任何向量都无法用其他向量线性表出，因此 independent。
> ② $\text{dim}(\text{null}\ A)$ = $A\mathbf{x}=\mathbf{0}$ 通解中 free variable 的个数 = $\text{nullity}\ A$

### 引申出的重要结论

##### rank = dim(Col A) = dim(Row A)

> [!example] Summary：More definitions of Rank
> 1. 最多能选出多少个列向量构成 independent 向量组
> 2. pivot columns 的个数 = ==column space 的 dimension== = ==range 的 dimension==
> 3. RREF 中 non-zero rows 的个数 = ==row space 的 dimension==

> 注释：把矩阵 $A$ 视为函数（线性变换），则 $\text{Col}\ A$ 就是 $A$ 的 range

##### nullity = dim(Null A)

##### 对矩阵做 transpose，不会改变矩阵的 rank

> [!important] Theorem
> $$\text{rank}\ A=\text{rank}\ A^T$$

> 证明：$\text{rank}\ A^T=\text{dim}(\text{Col}\ A^T)=\text{dim}(\text{Row}\ A)=\text{rank}\ A$
