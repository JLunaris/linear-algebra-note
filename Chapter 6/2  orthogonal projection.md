
# Orthogonal Projection

### Orthogonal Complement

> [!example] orthogonal complement
> 对于==非空==向量集 $S\subseteq\mathbb{R}^n$，$\mathbb{R}^n$ 中==所有==与 $S$ 中每一个向量都正交的向量构成的集合称为 $S$ 的 **orthogonal complement**，记作 $S^{\perp}$（读作“$S$ perp”）。即：$$S^{\perp}=\{\mathbf{v}\in\mathbb{R}^n\mid\forall\mathbf{u}\in S,\mathbf{v}\cdot\mathbf{u}=0\}$$

> 例如，$S=\mathbb{R}^n$，则 $S^{\perp}=\{\mathbf{0}\}$；$S=\{\mathbf{0}\}$，则 $S^{\perp}=\mathbb{R}^n$。

> 示例：$\mathbb{R}^3$ 的 subspace $xy$-平面 $W=\left\{\begin{bmatrix}w_1\\w_2\\0\end{bmatrix}: w_1,w_2\in\mathbb{R}\right\}$，求 $W^\perp$。
> 
> 解：$W^\perp=\{\mathbf{v}\mid \forall\mathbf{w}\in W,\mathbf{v}\cdot\mathbf{w}=0\}$。设 $\mathbf{v}=\begin{bmatrix}v_1\\v_2\\v_3\end{bmatrix}$，即求 $\mathbf{v}\cdot\mathbf{w}=0$ 的全部解。
> $\begin{bmatrix}v_1\\v_2\\v_3\end{bmatrix}\cdot\begin{bmatrix}w_1\\w_2\\0\end{bmatrix}=0$ $\iff$ $v_1w_1+v_2w_2=0$。由于 $w_1,w_2$ 可以任意取值，因此解得 $v_1=v_2=0,v_3\in \mathbb{R}$，即 $\mathbf{v}=\begin{bmatrix}0\\0\\v_3\end{bmatrix}$。故 $W^{\perp}=\left\{\begin{bmatrix}0\\0\\v_3\end{bmatrix}:v_3\in\mathbb{R}\right\}$。
> ![[Pasted image 20260520104142.png|415]]

##### orthogonal complement 是 subspace

> [!important] Theorem
> 对于非空向量集 $S\subseteq\mathbb{R}^n$（不一定是 subspace），$S^{\perp}$ 是 subspace。

> 证明：$S^{\perp}=\{\mathbf{v}\mid\forall\mathbf{u}\in S,\mathbf{v}\cdot\mathbf{u}=0\}$
> ①显然 $\mathbf{0}\in S^{\perp}$
> ②任取 $\mathbf{v}_1,\mathbf{v}_2\in S^{\perp}$，则 $\forall\mathbf{u}\in S,\mathbf{v}_1\cdot\mathbf{u}=0$，$\forall\mathbf{u}\in S,\mathbf{v}_2\cdot\mathbf{u}=0$
>    $\forall\mathbf{u}\in S,(\mathbf{v}_1+\mathbf{v}_2)\cdot\mathbf{u}=\mathbf{v}_1\cdot\mathbf{u}+\mathbf{v}_2\cdot\mathbf{u}=0$，因此 $\mathbf{v}_1+\mathbf{v}_2\in S^{\perp}$
> ③任取 $\mathbf{v}\in S^{\perp}$，则 $\forall\mathbf{u}\in S,\mathbf{v}\cdot\mathbf{u}=0$
>    $\forall\mathbf{u}\in S,(c\mathbf{v})\cdot\mathbf{u}=c(\mathbf{v}\cdot\mathbf{u})=0$，因此 $c\mathbf{v}\in S^{\perp}$

##### 只有零向量可能同时处于 S 和 S^⊥

> [!important] Theorem
> 对于非空向量集 $S\subseteq\mathbb{R}^n$，有
> $$S\cap S^{\perp}\subseteq\{\mathbf{0}\}$$
> 特别地，若 $\mathbf{0}\in S$，则
> $$S\cap S^{\perp}=\{\mathbf{0}\}$$

> 证明：
> **命题1**：取任意 $\mathbf{v}\in S\cap S^{\perp}$，根据正交补定义知 $\forall\mathbf{s}\in S,\mathbf{v}\cdot\mathbf{s}=0$。由于 $\mathbf{v}\in S$，取 $\mathbf{s}=\mathbf{v}$，则有 $\mathbf{v}\cdot\mathbf{v}=0$，解得 $\mathbf{v}=\mathbf{0}\in\{\mathbf{0}\}$。
> **命题2**：先证 $\{\mathbf{0}\}\subseteq S\cap S^{\perp}$：①$\mathbf{0}\in S$；②$S^\perp$ 是 subspace $\implies$ $\mathbf{0}\in S^\perp$。由①②即证。
> 再证 $S\cap S^{\perp}\subseteq\{\mathbf{0}\}$：命题1已经证明。

##### span S 的正交补 = S 的正交补

> [!important] Theorem
> 对于非空向量集 $S\subseteq\mathbb{R}^n$，有
> $$(\text{Span}\ S)^{\perp}=S^{\perp}$$

> 证明：设 $S^{\perp}=\{\mathbf{v}\mid\forall\mathbf{u}\in S,\mathbf{v}\cdot\mathbf{u}=0\}$，$(\text{Span}\ S)^{\perp}=\{\mathbf{v}\mid\forall\mathbf{w}\in\text{Span}\ S,\mathbf{v}\cdot\mathbf{w}=0\}$
> ①证明 $(\text{Span}\ S)^{\perp}\subseteq S^{\perp}$：
> 任取 $\mathbf{v}\in(\text{Span}\ S)^{\perp}$，则 $\forall\mathbf{w}\in\text{Span}\ S,\mathbf{v}\cdot\mathbf{w}=0$。
> 由于 $S\subseteq\text{Span}\ S$，故 $\mathbf{w}\in S$，故 $\forall\mathbf{w}\in S,\mathbf{v}\cdot\mathbf{w}=0$，故 $\mathbf{v}\in S^{\perp}$
> ②证明 $S^{\perp}\subseteq(\text{Span}\ S)^{\perp}$：
> 任取 $\mathbf{v}\in S^{\perp}$，则 $\forall\mathbf{u}\in S,\mathbf{v}\cdot\mathbf{u}=0$。
> 只要证 $\forall\mathbf{w}\in\text{Span}\ S,\mathbf{v}\cdot\mathbf{w}=0$。
> 设 $S=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$，则 $\mathbf{w}=c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k$（$c_1,c_2,\cdots,c_k$ 为任意实数）
> $\mathbf{v}\cdot\mathbf{w}=c_1\mathbf{u}_1\cdot\mathbf{v}+c_2\mathbf{u}_2\cdot\mathbf{v}+\cdots+c_k\mathbf{u}_k\cdot\mathbf{v}=0$

推论：

> [!important] subspace 的正交补 = 其 basis 的正交补
> 
> 设 $B$ 是 subspace $W$ 的 basis，则 $W^{\perp}=B^{\perp}$。

> 案例：求 subspace 的正交补，只需求其 basis 的正交补。
> 
> 【例】subspace $W=\text{Span}\{\mathbf{u}_1,\mathbf{u}_2\}$，其中 $\mathbf{u}_1=\begin{bmatrix}1\\1\\-1\\4\end{bmatrix}$，$\mathbf{u}_2=\begin{bmatrix}1\\-1\\1\\2\end{bmatrix}$，求 $W^{\perp}$。
> 解：$W^{\perp}=\{\mathbf{u}_1,\mathbf{u}_2\}^{\perp}=\{\mathbf{v}\mid\mathbf{u}_1\cdot\mathbf{v}=0 \text{ 且 }\mathbf{u}_2\cdot\mathbf{v}=0\}$
> 即 $\begin{matrix} v_1 + v_2 - v_3 + 4v_4 = 0 \\ v_1 - v_2 + v_3 + 2v_4 = 0 \end{matrix}$，即 $A\mathbf{v}=\mathbf{0}$，其中 $A=\begin{bmatrix} 1 & 1 & -1 & 4 \\ 1 & -1 & 1 & 2 \end{bmatrix}$，只需求 $\text{Null}\ A$。
> 解得 $\begin{bmatrix} v_1 \\ v_2 \\ v_3 \\ v_4 \end{bmatrix} = \begin{bmatrix} -3v_4 \\ v_3 - v_4 \\ v_3 \\ v_4 \end{bmatrix} = v_3 \begin{bmatrix} 0 \\ 1 \\ 1 \\ 0 \end{bmatrix} + v_4 \begin{bmatrix} -3 \\ -1 \\ 0 \\ 1 \end{bmatrix}$，因此 $W^{\perp}=\text{Span}\left\{ \begin{bmatrix} 0 \\ 1 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} -3 \\ -1 \\ 0 \\ 1 \end{bmatrix} \right\}$。

##### Row A 的正交补 = Null A

> [!important] Theorem
> 对于矩阵 $A$，有
> $$(\text{Row}\ A)^{\perp}=\text{Null}\ A$$

> 证明：设 $A = \begin{bmatrix} \mathbf{r}_1^T \\ \mathbf{r}_2^T \\ \vdots \\ \mathbf{r}_m^T \end{bmatrix}$，则 $(\text{Row}\ A)^{\perp}=\{\mathbf{r}_1,\mathbf{r}_2,\cdots,\mathbf{r}_m\}^{\perp}$。
> 即满足 $\begin{cases} \mathbf{v} \cdot \mathbf{r}_1 = 0 \\ \mathbf{v} \cdot \mathbf{r}_2 = 0 \\ \ \vdots \\ \mathbf{v} \cdot \mathbf{r}_m = 0 \end{cases}$ 的所有 $\mathbf{v}$ 组成的集合，即 $A\mathbf{v}=\mathbf{0}$ 的所有解，即 $\text{Null}\ A$。

> [!NOTE] 
> 对于矩阵 $A$，有
> $$(\text{Col}\ A)^{\perp}=\text{Null}\ A^T$$

> 证明：$(\text{Col}\ A)^{\perp}=(\text{Row}\ A^T)^{\perp}=\text{Null}\ A^T$

### Orthogonal Decomposition Theorem

> [!important] Theorem
> $W$ 是 $\mathbb{R}^n$ 的 subspace，对于任意 $\mathbf{u}\in\mathbb{R}^n$，都存在==唯一的 $\mathbf{w}\in W$== 和==唯一的 $\mathbf{z}\in W^\perp$== 使得：
> $$\mathbf{u}=\mathbf{w}+\mathbf{z}$$

> 几何含义：原向量 = 平行于 $W$ 的部分 + 垂直于 $W$ 的部分

> 示例：$W$ 是 $\mathbb{R}^2$ 的 subspace
> ![[Pasted image 20260521115931.png|183]]

> 证明：略

> [!important] 推论
> 对于 $\mathbb{R}^n$ 的 subspace $W$，有
> $$\text{dim}\ W+\text{dim}\ W^\perp=n$$

> $W^\perp$ 补全了整个 $\mathbb{R}^n$，这也是为什么 $W^\perp$ 被称为正交“补”的原因。

> **证明**：设 $W$ 的 basis 是 $\{\mathbf{w}_1,\mathbf{w}_2,\cdots,\mathbf{w}_k\}$，$W^\perp$ 的 basis 是 $\{\mathbf{z}_1,\mathbf{z}_2,\cdots,\mathbf{z}_{r}\}$。
> 由于 $W\cap W^\perp=\{\mathbf{0}\}$，故 $S=\{\mathbf{w}_1,\mathbf{w}_2,\cdots,\mathbf{w}_k,\mathbf{z}_1,\mathbf{z}_2,\cdots,\mathbf{z}_r\}$ 无重复向量。
> 只要证 $S$ 是 $\mathbb{R}^n$ 的 basis。
> ①证明 $S$ 是 independent 的：只要证 $c_1\mathbf{w}_1+c_2\mathbf{w}_2+\cdots+c_k\mathbf{w}_k+d_1\mathbf{z}_1+d_2\mathbf{z}_2+\cdots+d_r\mathbf{z}_r=\mathbf{0}$ 的唯一解是 $c_1=\cdots=c_k=d_1=\cdots=d_r=0$。
> 原方程 $\implies$ $c_1\mathbf{w}_1+c_2\mathbf{w}_2+\cdots+c_k\mathbf{w}_k=-d_1\mathbf{z}_1-d_2\mathbf{z}_2-\cdots-d_r\mathbf{z}_r$
> 该方程左边 $\in W$，右边 $\in W^\perp$，结合 $W\cap W^\perp=\{\mathbf{0}\}$ 知 $c_1\mathbf{w}_1+c_2\mathbf{w}_2+\cdots+c_k\mathbf{w}_k=-d_1\mathbf{z}_1-d_2\mathbf{z}_2-\cdots-d_r\mathbf{z}_r=\mathbf{0}$
> 解得 $c_1=\cdots=c_k=0$，$d_1=\cdots=d_r=0$。
> ②证明 $\text{Span}\ S=\mathbb{R}^n$
> 任取 $\mathbf{u}\in\mathbb{R}^n$，由正交分解定理知，存在 $\mathbf{w}\in W,\mathbf{z}\in W^\perp$ 使得 $\mathbf{u}=\mathbf{w}+\mathbf{z}$
> 设 $\mathbf{w}=c_1\mathbf{w}_1+c_2\mathbf{w}_2+\cdots+c_k\mathbf{w}_k$，$\mathbf{z}=d_1\mathbf{z}_1+d_2\mathbf{z}_2+\cdots+d_r\mathbf{z}_r$
> 故 $\mathbf{u}=c_1\mathbf{w}_1+c_2\mathbf{w}_2+\cdots+c_k\mathbf{w}_k+d_1\mathbf{z}_1+d_2\mathbf{z}_2+\cdots+d_r\mathbf{z}_r$
> 因此 $\mathbb{R}^n\subseteq \text{Span}\ S$。
> 又因为 $S\subset\mathbb{R}^n$，因此 $\text{Span}\ S\subseteq\mathbb{R}^n$。
> 综上，$\text{Span}\ S=\mathbb{R}^n$。

上面的证明可以得到：

> [!important] 推论
> 对于 $\mathbb{R}^n$ 的 subspace $W$，设 $\{\mathbf{w}_1,\mathbf{w}_2,\cdots,\mathbf{w}_k\}$ 是 $W$ 的 basis，$\{\mathbf{z}_1,\mathbf{z}_2,\cdots,\mathbf{z}_{n-k}\}$ 是 $W^\perp$ 的 basis，则 $\{\mathbf{w}_1,\mathbf{w}_2,\cdots,\mathbf{w}_k,\mathbf{z}_1,\mathbf{z}_2,\cdots,\mathbf{z}_{n-k}\}$ 是 $\mathbb{R}^n$ 的 basis。

---

> 【例】假设 $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_n\}$ 是 $\mathbb{R}^n$ 的 orthogonal basis。对于任意的 $k$（其中 $1\le k <n$），定义 $W=\text{Span}\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$。求证 $\{\mathbf{v}_{k+1},\mathbf{v}_{k+2},\cdots,\mathbf{v}_n\}$ 是 $W^\perp$ 的 orthogonal basis。
> 
> 证明：
> - 证明 orthogonal：显然。
> - 证明 basis：只要证 ①independent ②子集 ③元素个数为 $\text{dim}\ W^\perp$。
>   ①independent：显然。
>   ②$W^\perp$ 的子集：只要证 $\mathbf{v}_{k+1},\mathbf{v}_{k+2},\cdots,\mathbf{v}_n$ 与 $W$ 的所有元素 orthogonal $\iff$ 只要证 $\mathbf{v}_{k+1},\mathbf{v}_{k+2},\cdots,\mathbf{v}_n$ 与 $W$ 的 generating set（即 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k$） 垂直。这是显然的。
>   ③元素个数为 $\text{dim}\ W^\perp$：由 $\text{dim}\ W+\text{dim}\ W^\perp=n$ 知 $\text{dim}\ W^\perp=n-k$。显然 $\{\mathbf{v}_{k+1},\mathbf{v}_{k+2},\cdots,\mathbf{v}_n\}$ 的元素个数也为 $n-k$。

### Orthogonal Projection

> [!example] orthogonal projection on subspaces
> $W$ 是 $\mathbb{R}^n$ 的 subspace，对于任意 $\mathbf{u}\in\mathbb{R}^n$，都存在唯一的 $\mathbf{w}\in W$ 和唯一的 $\mathbf{z}\in W^\perp$ 使得：
> $$\mathbf{u}=\mathbf{w}+\mathbf{z}$$
> 其中，$\mathbf{w}$ 称为 $\mathbf{u}$ 在 $W$ 上的 **orthogonal projection**。
> 
> 定义函数 $U_W:\mathbb{R}^n\to\mathbb{R}^n$，满足 $\forall\mathbf{u}\in\mathbb{R}^n$，$U_W(\mathbf{u})$ 是 $\mathbf{u}$ 在 $W$ 上的 orthogonal projection，即 $U_W(\mathbf{u})=\mathbf{w}$，称该函数为 $W$ 的 **orthogonal projection operator**。

> 图示：
> ![[Pasted image 20260521124832.png|402]]

##### orthogonal projection operator 是线性的

> [!important] Theorem
> orthogonal projection operator 是线性的。

> 证明：设 $W$ 是 $\mathbb{R}^n$ 的 subspace，$U_W$ 是 $W$ 上的 orthogonal projection operator。
> ①preserving scaling：
>    设 $\mathbf{u}=\mathbf{w}+\mathbf{z}$，其中 $\mathbf{u}\in\mathbb{R}^n$，$\mathbf{w}\in W$，$\mathbf{z}\in W^\perp$ $\implies$ $U_W(\mathbf{u})=\mathbf{w}$
>    则 $c\mathbf{u}=c\mathbf{w}+c\mathbf{z}$，由 $W$ 和 $W^\perp$ 是 subspace 知 $c\mathbf{w}\in W$，$c\mathbf{z}\in W^\perp$ $\implies$ $U(c\mathbf{u})=c\mathbf{w}$
> ②preserving addition：（同理，以下内容简写）
>    $\mathbf{u}_1=\mathbf{w}_1+\mathbf{z}_1$ $\implies$ $U_W(\mathbf{u}_1)=\mathbf{w}_1$
>    $\mathbf{u}_2=\mathbf{w}_2+\mathbf{z}_2$ $\implies$ $U_W(\mathbf{u}_2)=\mathbf{w}_2$
>    $\mathbf{u}_1+\mathbf{u}_2=(\mathbf{w}_1+\mathbf{w}_2)+(\mathbf{z}_1+\mathbf{z}_2)$ $\implies$ $U_W(\mathbf{u}_1+\mathbf{u}_2)=\mathbf{w}_1+\mathbf{w}_2$

##### closest vector property

> [!important] Theorem
> 向量 $\mathbf{u}$ 在 subspace $W$ 上的 ==orthogonal projection== 是 $W$ 中与 $\mathbf{u}$ 距离最近的向量。

> 证明：
> ![[Pasted image 20260522145919.png|467]]
> 设 $\mathbf{w}$ 是 $\mathbf{u}$ 在 $W$ 上的 orthogonal projection，$\mathbf{w}'$ 是 $W$ 中的任意向量（$\mathbf{w}'\neq\mathbf{w}$）
> 只要证 $\|\mathbf{u}-\mathbf{w}\|<\|\mathbf{u}-\mathbf{w}'\|$。只要证 $\|\mathbf{u}-\mathbf{w}\|^2<\|\mathbf{u}-\mathbf{w}'\|^2$。
> $\|\mathbf{u}-\mathbf{w}'\|^2=\|(\mathbf{u}-\mathbf{w})+(\mathbf{w}-\mathbf{w}')\|^2 =\|\mathbf{u}-\mathbf{w}\|^2+2(\mathbf{u}-\mathbf{w})\cdot(\mathbf{w}-\mathbf{w}')+\|\mathbf{w}-\mathbf{w}'\|^2$
> 由正交分解定理知 $(\mathbf{u}-\mathbf{w})\in W^\perp$，由 subspace 性质知 $(\mathbf{w}-\mathbf{w}')\in W$，因此 $(\mathbf{u}-\mathbf{w}) \cdot (\mathbf{w}-\mathbf{w}')=0$
> 因此 $\|\mathbf{u}-\mathbf{w}'\|^2=\|\mathbf{u}-\mathbf{w}\|^2+\|\mathbf{w}-\mathbf{w}'\|^2 > \|\mathbf{u}-\mathbf{w}\|^2$

##### 向量到 subspace 的距离

> [!example] 向量到 subspace 的距离
> $W$ 是 $\mathbb{R}^n$ 的 subspace，$\mathbf{u}\in\mathbb{R}^n$，$\mathbf{u}$ 在 $W$ 上的 orthogonal projection 为 $\mathbf{w}$。定义 $\mathbf{u}$ 到 $W$ 的距离为 ==$\|\mathbf{u}-\mathbf{w}\|$==。

### Orthogonal Projection Matrix

由于 orthogonal projection operator $U_W$ 是线性的，因此它一定对应了一个矩阵 $P_W$，使得对于任意的 $\mathbf{u}\in \mathbb{R}^n$，$U_W(\mathbf{u})=P_W\mathbf{u}$。

> [!example] orthogonal projection matrix
> $W$ 是 $\mathbb{R}^n$ 的 subspace，orthogonal projection operator $U_W$ 对应的矩阵 $P_W$ 称为 $W$ 的 **orthogonal projection matrix**。

> [!important] Theorem
> $W$ 是 $\mathbb{R}^n$ 的 subspace，$W$ 的 ==basis== 是 $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$，构造矩阵 $C=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_k\end{bmatrix}$，则 $W$ 的 orthogonal projection matrix $$P_W=C(C^TC)^{-1}C^T$$

> 助记：画一个天线宝宝丁丁。

> $P_W$ 是一个 $n\times n$ 方阵（输入 $n$ 维向量，输出 $n$ 维向量）。

> **证明**（看懂即可）：设 $\mathbf{u}$ 是 $\mathbb{R}^n$ 中的任一向量，$\mathbf{u}$ 在 $W$ 上的正交投影 $U_W(\mathbf{u})=\mathbf{w}$。
> - $\mathbf{u}-\mathbf{w}\in W^\perp$ $\implies$ $(\mathbf{u}-\mathbf{w})\perp \mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k$ $\implies$ $C^T(\mathbf{u}-\mathbf{w})=\mathbf{0}$ $\implies$ $C^T\mathbf{u}=C^T\mathbf{w}$
> - $\mathbf{w}\in W$，因此可设 $\mathbf{w}=C\mathbf{b}$，其中 $\mathbf{b}\in\mathbb{R}^k$。则 $\implies$ $C^T\mathbf{u}=C^TC\mathbf{b}$
> 由于 $C^TC$ 是可逆的（见下面引理），因此 $(C^TC)^{-1}C^T\mathbf{u}=\mathbf{b}$
> 代入 $\mathbf{w}=C\mathbf{b}$ 得 $\mathbf{w}=C(C^TC)^{-1}C^T\mathbf{u}$，故 $P_W=C(C^TC)^{-1}C^T$
> 
> **引理**：矩阵 $C$ 的 columns 是 independent 的，则 $C^TC$ 是可逆的
> **证明**：$C$ 是 $n\times k$ 矩阵，则 $C^TC$ 是 $k\times k$ 方阵。只要证 $C^TC$ 的 columns 是 independent 的。
> 只要证 $C^TC\mathbf{b}=\mathbf{0}$ 的唯一解是 $\mathbf{b}=\mathbf{0}$。
> 方程两边是 $k\times 1$ 矩阵，两边同乘 $\mathbf{b}^T$ 得 $\mathbf{b}^TC^TC\mathbf{b}=\mathbf{0}$ $\implies$ $(C\mathbf{b})^T(C\mathbf{b})=\mathbf{0}$ $\implies$ $(C\mathbf{b})\cdot(C\mathbf{b})=0$ $\implies$ $\|C\mathbf{b}\|^2=0$ $\implies$ $C\mathbf{b}=\mathbf{0}$
> 由于 $C$ 的 columns 是 independent 的，因此 $\implies$ $\mathbf{b}=\mathbf{0}$

> [!NOTE] $P_W\mathbf{u}$ 的几何含义
> 对于任意的 $\mathbf{u}\in\mathbb{R}^n$，$P_W\mathbf{u}$ 表示==将 $\mathbf{u}$ 向 $W$ 投影的结果==。

---

> 【例】$W$ 是 $\mathbb{R}^n$ 的 subspace。求证：
>  ① $(P_W)^2=P_W$
>  ② $(P_W)^T=P_W$
>  ③ $P_WP_{W^\perp}=P_{W^\perp}P_W=O$
>  ④ $P_W+P_{W^\perp}=I_n$
> 
> 证明：
> ① $(P_W)^2=C(C^TC)^{-1}C^TC(C^TC)^{-1}C^T=C(C^TC)^{-1}(C^TC)(C^TC)^{-1}C^T=C(C^TC)^{-1}C^T=P_W$
> 几何含义：对于 $\mathbb{R}^n$ 中任意向量 $\mathbf{u}$，$P_W\mathbf{u}$ 表示将 $\mathbf{u}$ 向 $W$ 投影的结果，$P_WP_W\mathbf{u}$ 表示将投影结果再向 $W$ 投影。显然，向 $W$ 正交投影一次以后，再投影任意次都不会发生任何变化。
> ② $(P_W)^T=(C(C^TC)^{-1}C^T)^T=C((C^TC)^{-1})^TC^T=C((C^TC)^T)^{-1}C^T=C(C^TC)^{-1}C^T=P_W$
> ③ **证法1**：设 $W$ 的 basis 是 $\{\mathbf{w}_1,\mathbf{w}_2,\cdots,\mathbf{w}_k\}$，$W^\perp$ 的 basis 是 $\{\mathbf{z}_1,\mathbf{z}_2,\cdots,\mathbf{z}_{n-k}\}$。
>    则 $P_W=C(C^TC)^{-1}C^T$，其中 $C=\begin{bmatrix}\mathbf{w}_1 & \mathbf{w}_2 & \cdots & \mathbf{w}_k\end{bmatrix}$；
>    $P_{W^\perp}=D(D^TD)^{-1}D^T$，其中 $D=\begin{bmatrix}\mathbf{z}_1 & \mathbf{z}_2 & \cdots & \mathbf{z}_{n-k}\end{bmatrix}$。
>    则 $P_WP_{W^\perp}=C(C^TC)^{-1}C^TD(D^TD)^{-1}D^T$。
>    注意到 $C^{\mathrm{T}}D = \begin{bmatrix} \mathbf{w}_1^{\mathrm{T}}  \\  \mathbf{w}_2^{\mathrm{T}} \\ \vdots \\ \mathbf{w}_k^{\mathrm{T}} \end{bmatrix} \begin{bmatrix} \mathbf{z}_1 & \mathbf{z}_2 & \cdots & \mathbf{z}_{n-k} \end{bmatrix} = \begin{bmatrix} \mathbf{w}_1 \cdot \mathbf{z}_1 & \mathbf{w}_1 \cdot \mathbf{z}_2 & \cdots & \mathbf{w}_1 \cdot \mathbf{z}_{n-k} \\ \mathbf{w}_2 \cdot \mathbf{z}_1 & \mathbf{w}_2 \cdot \mathbf{z}_2 & \cdots & \mathbf{w}_2 \cdot \mathbf{z}_{n-k} \\ \vdots & \vdots & \ddots & \vdots \\ \mathbf{w}_k \cdot \mathbf{z}_1 & \mathbf{w}_k \cdot \mathbf{z}_2 & \cdots & \mathbf{w}_k \cdot \mathbf{z}_{n-k} \end{bmatrix}=O$
>    因此 $P_WP_{W^\perp}=O$。同理 $P_{W^\perp}P_W=O$。
> **证法2**：对于 $\mathbb{R}^n$ 中任意向量 $\mathbf{u}$，存在 $\mathbf{w}\in W$ 和 $\mathbf{z}\in W^\perp$ 使 $\mathbf{u}=\mathbf{w}+\mathbf{z}$。
>    $\begin{aligned}P_WP_{W^\perp}\mathbf{u}&=P_WP_{W^\perp}(\mathbf{w}+\mathbf{z}) \\ &=P_WP_{W^\perp}\mathbf{w}+P_WP_{W^\perp}\mathbf{z}\\ &= P_W\mathbf{0} + P_W\mathbf{z} \\ &= \mathbf{0}+\mathbf{0} \end{aligned}$
>    由于 $P_WP_{W^\perp}\mathbf{u}=\mathbf{0}$ 对任意 $\mathbf{u}\in\mathbb{R}^n$ 都成立，因此 $P_WP_{W^\perp}=O$。同理 $P_{W^\perp}P_W=O$。
> 几何含义：如图所示，显然 $P_{W^\perp}P_W\mathbf{u}=\mathbf{0}$。
> ![[Pasted image 20260525155750.png|205]]
> ④ 对于 $\mathbb{R}^n$ 中任意向量 $\mathbf{u}$，存在 $\mathbf{w}\in W$ 和 $\mathbf{z}\in W^\perp$ 使 $\mathbf{u}=\mathbf{w}+\mathbf{z}$。
> $\begin{aligned}(P_W+P_{W^\perp})\mathbf{u}&=(P_W+P_{W^\perp})(\mathbf{w}+\mathbf{z})\\ &= P_W(\mathbf{w}+\mathbf{z})+P_{W^\perp}(\mathbf{w}+\mathbf{z})\\ &=P_W\mathbf{w}+P_W\mathbf{z}+P_{W^\perp}\mathbf{w}+P_{W^\perp}\mathbf{z} \\ &=\mathbf{w}+\mathbf{0}+\mathbf{0}+\mathbf{z}\\ &= \mathbf{u} \end{aligned}$
> 由于 $(P_W+P_{W^\perp})\mathbf{u}=\mathbf{u}$ 对任意 $\mathbf{u}\in\mathbb{R}^n$ 都成立，因此 $P_W+P_{W^\perp}=I_n$。

##### 用 orthogonal / orthonormal basis 计算 orthogonal projection

> [!important] Theorem
> $W$ 是 $\mathbb{R}^n$ 的 subspace，$W$ 的 ==orthogonal basis== 是 $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$，则对于任意的 $\mathbf{u}\in \mathbb{R}^n$，$\mathbf{u}$ 在 $W$ 上的 orthogonal projection
> $$\mathbf{w}=c_1\mathbf{v}_1+c_2\mathbf{v}_2+\cdots+c_k\mathbf{v}_k$$
> 其中，$c_i=\cfrac{\mathbf{u}\cdot\mathbf{v}_i}{\|\mathbf{v}_i\|^2}$（$i=1,2,\cdots,k$）.
> 特别地，若 $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$ 是 ==orthonormal basis==，则 $c_i=\mathbf{u}\cdot\mathbf{v}_i$.

> 证明：$\mathbf{w}=P_W\mathbf{u}=C(C^TC)^{-1}C^T\mathbf{u}$，其中 $C=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_k\end{bmatrix}$
> ①求 $C^{\mathrm{T}}C =\begin{bmatrix} \mathbf{v}_1^{\mathrm{T}}  \\  \mathbf{v}_2^{\mathrm{T}} \\ \vdots \\ \mathbf{v}_k^{\mathrm{T}} \end{bmatrix} \begin{bmatrix} \mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_k \end{bmatrix}= \begin{bmatrix} \mathbf{v}_1 \cdot \mathbf{v}_1 & \mathbf{v}_1 \cdot \mathbf{v}_2 & \cdots & \mathbf{v}_1 \cdot \mathbf{v}_k \\\mathbf{v}_2 \cdot \mathbf{v}_1 & \mathbf{v}_2 \cdot \mathbf{v}_2 & \cdots & \mathbf{v}_2 \cdot \mathbf{v}_k \\\vdots & \vdots & \ddots & \vdots \\\mathbf{v}_k \cdot \mathbf{v}_1 & \mathbf{v}_k \cdot \mathbf{v}_2 & \cdots & \mathbf{v}_k \cdot \mathbf{v}_k\end{bmatrix}$
>    由于 $\{\mathbf{v}_1, \mathbf{v}_2, \cdots, \mathbf{v}_k\}$ 是 orthogonal basis，因此当 $i \neq j$ 时，$\mathbf{v}_i \cdot \mathbf{v}_j = 0$。
>    因此 $C^{\mathrm{T}}C = \begin{bmatrix} \|\mathbf{v}_1\|^2 & 0 & \cdots & 0 \\ 0 & \|\mathbf{v}_2\|^2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & \|\mathbf{v}_k\|^2 \end{bmatrix}$ 是一个对角矩阵。
> ②求 $(C^{\mathrm{T}}C)^{-1}$，对角矩阵的求逆，只需每个对角元素取倒数即可：
>    $(C^{\mathrm{T}}C)^{-1} = \begin{bmatrix} \cfrac{1}{\|\mathbf{v}_1\|^2} & 0 & \cdots & 0 \\ 0 & \cfrac{1}{\|\mathbf{v}_2\|^2} & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & \cfrac{1}{\|\mathbf{v}_k\|^2} \end{bmatrix}$
> ③求 $C(C^{\mathrm{T}}C)^{-1}=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_k\end{bmatrix}\begin{bmatrix} \cfrac{1}{\|\mathbf{v}_1\|^2} & 0 & \cdots & 0 \\ 0 & \cfrac{1}{\|\mathbf{v}_2\|^2} & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & \cfrac{1}{\|\mathbf{v}_k\|^2} \end{bmatrix}=\begin{bmatrix}\cfrac{\mathbf{v}_1}{\|\mathbf{v}_1\|^2} & \cfrac{\mathbf{v}_2}{\|\mathbf{v}_2\|^2}& \cdots &\cfrac{\mathbf{v}_k}{\|\mathbf{v}_k\|^2}\end{bmatrix}$
> ④求 $C(C^TC)^{-1}C^T=\begin{bmatrix}\cfrac{\mathbf{v}_1}{\|\mathbf{v}_1\|^2} & \cfrac{\mathbf{v}_2}{\|\mathbf{v}_2\|^2}& \cdots &\cfrac{\mathbf{v}_k}{\|\mathbf{v}_k\|^2}\end{bmatrix}\begin{bmatrix} \mathbf{v}_1^{\mathrm{T}}  \\  \mathbf{v}_2^{\mathrm{T}} \\ \vdots \\ \mathbf{v}_k^{\mathrm{T}} \end{bmatrix}=\cfrac{\mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1^T+\cfrac{\mathbf{v}_2}{\|\mathbf{v}_2\|^2}\mathbf{v}_2^T+\cdots+\cfrac{\mathbf{v}_k}{\|\mathbf{v}_k\|^2}\mathbf{v}_k^T$
> ⑤求 $C(C^TC)^{-1}C^T\mathbf{u}=\sum\limits_{i=1}^{k} \cfrac{\mathbf{v}_i}{\|\mathbf{v}_i\|^2}\mathbf{v}_i^T\mathbf{u}=\sum\limits_{i=1}^{k} \cfrac{\mathbf{v}_i}{\|\mathbf{v}_i\|^2}(\mathbf{v}_i\cdot\mathbf{u})=\sum\limits_{i=1}^{k} \cfrac{\mathbf{v}_i\cdot\mathbf{u}}{\|\mathbf{v}_i\|^2}\mathbf{v}_i$

### Applications of Orthogonal Projection

##### Inconsistent System of Linear Equations

对于 inconsistent 线性方程组 $A\mathbf{x}=\mathbf{b}$，虽然无解（即 $\mathbf{b}\notin \text{Col}\ A$），但可以寻找它的近似解：寻找向量 $\mathbf{z}$，使得 $A\mathbf{z}$ 与 $\mathbf{b}$ 距离最近（也就是使 $\|A\mathbf{z}-\mathbf{b}\|$ 最小）。

设 $W=\text{Col}\ A$，由于 $A\mathbf{z}\in W$，因此该问题等价于在 $W$ 中寻找与 $\mathbf{b}$ 距离最近的向量。根据 closest vector property，$W$ 中与 $\mathbf{b}$ 距离最近的向量正是 $\mathbf{b}$ 在 $W$ 上的 orthogonal projection $P_W\mathbf{b}$。

![[Pasted image 20260525191445.png|449]]

> [!important] Theorem
> inconsistent 线性方程组 $A\mathbf{x}=\mathbf{b}$ 的近似解是以下线性方程组的解（设 $W=\text{Col}\ A$）：
> $$A\mathbf{x}=P_W\mathbf{b}$$

> 线性方程组 $A\mathbf{x}=P_W\mathbf{b}$ 一定有解，因为 $P_W\mathbf{b}\in\text{Col}\ A$。

##### Least Squares Approximation

![[Pasted image 20260526150449.png|513]]

给定一组真实数据 $(x_1, y_1), (x_2, y_2), \cdots, (x_n, y_n)$，绘制在坐标系中如图所示。$x$ 与 $y$ 之间存在近似线性（直线）的关系，我们希望找到一条最能拟合该数据的直线 $y = a_0 + a_1x$。

对于每个数据点 $(x_i,y_i)$，该直线给出的预测值为 $y=a_0+a_1x$，则误差 $e_i=y_i-(a_0+a_1x)$。最常用的拟合标准是：使所有误差的平方和达到最小，即寻找 $a_0,a_1$ 使
$$E = [y_1 - (a_0 + a_1x_1)]^2 + [y_2 - (a_0 + a_1x_2)]^2 + \dots + [y_n - (a_0 + a_1x_n)]^2$$
达到最小。寻找这条直线的方法称为 **method of least squares**（最小二乘法）。

> 设误差向量 $\mathbf{e} =\begin{bmatrix}e_1\\e_2\\ \vdots \\ e_n\end{bmatrix}= \begin{bmatrix} y_1 - (a_0 + a_1x_1) \\ y_2 - (a_0 + a_1x_2) \\ \vdots \\ y_n - (a_0 + a_1x_n) \end{bmatrix}$，则 $E=\|\mathbf{e}\|^2$
> 原问题 $\iff$ 寻找使 $\|\mathbf{e}\|^2$ 最小的 $a_0,a_1$ $\iff$ 寻找使 $\|\mathbf{e}\|$ 最小的 $a_0,a_1$
> 设 $\mathbf{v}_1 = \begin{bmatrix} 1 \\ 1 \\ \vdots \\ 1 \end{bmatrix}$，$\mathbf{v}_2 = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}$，$\mathbf{y} = \begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix}$，则 $\mathbf{e}=\mathbf{y}-(a_0\mathbf{v}_1+a_1\mathbf{v}_2)$
> 令 $C=\begin{bmatrix}\mathbf{v}_1,\mathbf{v}_2\end{bmatrix}$，$\mathbf{a}=\begin{bmatrix}a_0 \\ a_1\end{bmatrix}$，则 $\mathbf{e}=\mathbf{y}-C\mathbf{a}$，则 $\|\mathbf{e}\|=\|\mathbf{y}-C\mathbf{a}\|$
> 因此原问题 $\iff$ 寻找使 $\mathbf{y}$ 和 $C\mathbf{a}$ 距离最近的 $a_0,a_1$
> 由于 $\mathbf{y}\in\mathbb{R}^n$，$C\mathbf{a}\in\text{Col}\ C\triangleq W$，根据 closest vector property，$W$ 中与 $\mathbf{y}$ 距离最近的向量正是 $\mathbf{y}$ 在 $W$ 上的 orthogonal projection $P_W\mathbf{y}$。因此求解方程 $C\mathbf{a}=P_W\mathbf{y}$ 即可。
> 对于任何合理的数据集，其 $x_i$ ==不完全相等==，因此 $\mathbf{v}_1$ 和 $\mathbf{v}_2$ 是 independent 的，从而 $\{\mathbf{v}_1, \mathbf{v}_2\}$ 构成 $W$ 的一个 basis。因此 $P_W=C(C^TC)^{-1}C^T$。原方程 $\iff$ $C\mathbf{a}=C(C^TC)^{-1}C^T\mathbf{y}$。
> 由于 $C$ 的 columns 是 independent 的，因此 $C$ 是 one-to-one 的
> 故原方程 $\iff$ $\mathbf{a}=(C^TC)^{-1}C^T\mathbf{y}$

> [!important] Theorem
> 给定一组真实数据 $(x_1, y_1), (x_2, y_2), \cdots, (x_n, y_n)$，且 $x_i$ 不完全相等。设 $$C = \begin{bmatrix} 1 & x_1 \\ 1 & x_2 \\ \vdots & \vdots \\ 1 & x_n \end{bmatrix}, \quad \mathbf{y} = \begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix}$$
> 则使用最小二乘法拟合这组数据得到的等式 $y = a_0 + a_1x$ 的系数满足 $$\begin{bmatrix} a_0 \\ a_1 \end{bmatrix}=(C^TC)^{-1}C^T\mathbf{y}$$

可以使用类似的方法，进行更复杂的拟合：

> [!NOTE] 将单自变量数据拟合为 $k$ 次多项式 $y = a_0 + a_1x + a_2x^2 + \dots + a_kx^k$
> 已知 $n$ 个真实数据 $(x_i,y_i)$。
> 构造矩阵 $C = \begin{bmatrix} 1 & x_1 & x_1^2 & \cdots & x_1^k \\ 1 & x_2 & x_2^2 & \cdots & x_2^k \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 1 & x_n & x_n^2 & \cdots & x_n^k \end{bmatrix}$，$\mathbf{a}=\begin{bmatrix} a_0 \\ a_1 \\ \vdots \\ a_k \end{bmatrix}$，$\mathbf{y} = \begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix}$。
> 求解方程 $C\mathbf{a}=P_W\mathbf{y}$ 即可（其中 $P_W$ 是 $\text{Col}\ C$ 的 orthogonal projection matrix）。
> 特别地，若 $C$ 的 columns 是 independent 的，则 $\mathbf{a}=(C^TC)^{-1}C^T\mathbf{y}$。

> 案例：将一组单自变量数据拟合为二次曲线
> ![[Pasted image 20260527172518.png|214]]

> [!NOTE] 将多自变量数据拟合为 $k$ 元多项式 $y = a_0 + a_1x_1 + a_2x_2 + \dots + a_kx_k$
> 已知 $n$ 个真实数据 $(x_{1i},x_{2i},\cdots,x_{ki},y_i)$。
> 构造矩阵 $C = \begin{bmatrix} 1 & x_{11} & x_{21} & \cdots & x_{k1} \\ 1 & x_{12} & x_{22} & \cdots & x_{k2} \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 1 & x_{1n} & x_{2n} & \cdots & x_{kn} \end{bmatrix}$，$\mathbf{a}=\begin{bmatrix} a_0 \\ a_1 \\ \vdots \\ a_k \end{bmatrix}$，$\mathbf{y} = \begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix}$。
> 求解方程 $C\mathbf{a}=P_W\mathbf{y}$ 即可（其中 $P_W$ 是 $\text{Col}\ C$ 的 orthogonal projection matrix）。
> 特别地，若 $C$ 的 columns 是 independent 的，则 $\mathbf{a}=(C^TC)^{-1}C^T\mathbf{y}$。

> 案例：将一组多自变量数据拟合为平面
> ![[Pasted image 20260527174001.png|313]]