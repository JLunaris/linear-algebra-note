
# Determinant

Square matrix $A$ 的 **determinant** 是一个==标量==，记作 $\text{det}\ A$ 或 $|A|$。

### Cofactor Expansion

$A$ 是一个 $n\times n$ 方阵，有如下定义：

> [!example] 矩阵 $A_{ij}$
> 定义 $(n-1)\times(n-1)$ 矩阵 $A_{ij}$ 为：从 $A$ 中删去第 $i$ 行和第 $j$ 列后得到的矩阵。
> 
> ![[Pasted image 20260417212208.png|373]]

> [!example] $\text{det}\ A$
> 定义矩阵 $A$ 的 determinant 为：
> $$\text{det}\ A=a_{11}c_{11}+a_{12}c_{12}+\cdots+a_{1n}c_{1n}$$
> 其中，标量 ==$c_{ij}=(-1)^{i+j}\cdot\text{det}\ A_{ij}$==，称为 $A$ 的 ==$(i,j)$-cofactor==。
> 将上述等式称为矩阵 $A$ 沿第1行的 **cofactor expansion**。
> 特别地，对于 $1\times 1$ 矩阵 $\begin{bmatrix}a\end{bmatrix}$，定义 ==$\text{det}\begin{bmatrix}a\end{bmatrix}=a$==。

> 助记：Determinant of 2x2 matrices
> ![[Pasted image 20260417205118.png|300]]

> [!important] Theorem
> $A$ 的 determinant 可以通过沿其**任意一行**/**任意一列**做 cofactor expansion 来计算，它们的结果都是相同的。

> 矩阵 $A$ 沿第 $i$ 行的 cofactor expansion：$\text{det}\ A=a_{i1}c_{i1}+a_{i2}c_{i2}+\cdots+a_{in}c_{in}$
> 矩阵 $A$ 沿第 $j$ 列的 cofactor expansion：$\text{det}\ A=a_{1j}c_{1j}+a_{2j}c_{2j}+\cdots+a_{nj}c_{nj}$

> 证明：略。

### 基本性质

> 注：本节的证明全部省略。

##### 交换任意两行（或两列），det 变号

> [!important] Theorem
> 交换矩阵的任意两行（或两列），determinant 变号。

> [!important] 推论
> 若矩阵的两行（或两列）相同，则 determinant 为 $0$。

> 推导：$\begin{vmatrix}a & b \\ a & b\end{vmatrix}\xlongequal{r_1 \leftrightarrow r_2}-\begin{vmatrix}a & b \\ a & b\end{vmatrix}$，因此 $\begin{vmatrix}a & b \\ a & b\end{vmatrix}=0$。

##### determinant 对某一行（列）是线性的

具体分为以下两条性质：

> [!important] Theorem
> 矩阵的某一行（列）乘以 c，determinant 也乘以 c。

> [!important] Theorem
> 按某一行进行拆分：
> $$\begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ \vdots & \vdots & & \vdots \\ a_{i1}+b_{i1} & a_{i2}+b_{i2} & \cdots & a_{in}+b_{in} \\ \vdots & \vdots & & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn} \end{vmatrix} = \begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ \vdots & \vdots & & \vdots \\ a_{i1} & a_{i2} & \cdots & a_{in} \\ \vdots & \vdots & & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn} \end{vmatrix} + \begin{vmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ \vdots & \vdots & & \vdots \\ b_{i1} & b_{i2} & \cdots & b_{in} \\ \vdots & \vdots & & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn} \end{vmatrix}$$
> 按某一列进行拆分：
> $$\begin{vmatrix} a_{11} & \cdots & a_{1j}+b_{1j} & \cdots & a_{1n} \\ a_{21} & \cdots & a_{2j}+b_{2j} & \cdots & a_{2n} \\ \vdots & & \vdots & & \vdots \\ a_{n1} & \cdots & a_{nj}+b_{nj} & \cdots & a_{nn} \end{vmatrix} = \begin{vmatrix} a_{11} & \cdots & a_{1j} & \cdots & a_{1n} \\ a_{21} & \cdots & a_{2j} & \cdots & a_{2n} \\ \vdots & & \vdots & & \vdots \\ a_{n1} & \cdots & a_{nj} & \cdots & a_{nn} \end{vmatrix} + \begin{vmatrix} a_{11} & \cdots & b_{1j} & \cdots & a_{1n} \\ a_{21} & \cdots & b_{2j} & \cdots & a_{2n} \\ \vdots & & \vdots & & \vdots \\ a_{n1} & \cdots & b_{nj} & \cdots & a_{nn} \end{vmatrix}$$

> [!NOTE] Note
> $A$ 是一个 $n\times n$ 矩阵，则 $\text{det}(cA)=c^n\cdot\text{det}(A)$

##### 某一行（列）乘以 c 加到另一行（列）上，det 不变

> [!important] Theorem
> 矩阵的某一行（列）乘以 c 加到另一行（列）上，determinant 不变。

### 特殊矩阵的 determinant

##### diagonal matrix

> [!important] diagonal matrix 的 determinant 等于其主对角线元素的乘积
> 对角矩阵 $D = \text{diag}(d_1, d_2, \dots, d_n) = \begin{bmatrix}d_1 & 0 & \cdots & 0 \\ 0 & d_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & d_n\end{bmatrix}$，则 ==$\text{det}(D)=d_1d_2\cdots d_n$==.

> 证明：沿第1行或第1列展开即证。

> [!important] 推论
> ==$\text{det}(I_n)=1$==

##### upper / lower triangular matrix

> [!important] upper / lower triangular matrix 的 determinant 等于其主对角线元素的乘积
> 上三角矩阵 $U = \begin{bmatrix}u_{11} & u_{12} & \cdots & u_{1n} \\0 & u_{22} & \cdots & u_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & u_{nn}\end{bmatrix}$，则 ==$\text{det}(U)=u_{11}u_{22}\cdots u_{nn}$==.
> 
> 下三角矩阵 $L = \begin{bmatrix}l_{11} & 0 & \cdots & 0 \\ l_{21} & l_{22} & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ l_{n1} & l_{n2} & \cdots & l_{nn}\end{bmatrix}$，则 ==$\text{det}(L)=l_{11}l_{22}\cdots l_{nn}$==.

> 证明：上三角矩阵——沿第1列展开即证；下三角矩阵——沿第1行展开即证。

### Determinant vs Invertible

> [!important] Theorem
> $A$ is invertible $\iff$ $\text{det}(A)\neq 0$

> 证明：设 $n\times n$ 方阵 $A$ 的 RREF 是 $R$。现在分析 $\text{det}(A)$ 和 $\text{det}(R)$ 之间的关系：
> $R$ 是由 $A$ 经过 elementary row operation 得到的，包含以下三类，现在分析它们对 determinant 的影响：
> ① Interchange：仅改变 determinant 的正负
> ② Scaling (non-zero)：使 determinant 乘 k (k≠0)
> ③ Row addition：不改变 determinant
> 因此，$\text{det}(R)=\pm k_1 k_2 \cdots k_?\text{det}(A)$ （$k_1 k_2 \cdots k_?\neq 0$）
> 
> **左推右**：$A$ is invertible $\iff$ $R=I$
> 知 $\text{det}(R)=1$。若 $\text{det}(A)=0$，则由前面等式知 $\text{det}(R)=0$，与已知条件矛盾。故 $\text{det}(A)\neq 0$。
> **右推左**：等价于证 $A$ is not invertible $\implies$ $\text{det}(A)=0$
> $A$ is not invertible $\implies$ $\text{rank}(A)<n$ $\implies$ $R$ 中 non-zero rows 的个数 < n
> 即 $R$ 中有 zero row，因此 $\text{det}(R)=0$，由前面等式知 $\text{det}(A)=0$

### 高级性质

##### det(AB)=det(A)det(B)

> [!important] Theorem
> $A$、$B$ 均为方阵，有：
> $$\text{det}(AB)=\text{det}(A)\text{det}(B)$$

> 例：$A$ is invertible，已知 $\text{det}(A)$，求 $\text{det}(A^{-1})$
> 
> 解：$AA^{-1}=I$，故 $\text{det}(AA^{-1})=\text{det}(A)\text{det}(A^{-1})=1$
> 故 $\text{det}(A^{-1})=\cfrac{1}{\text{det}(A)}$

> 证明：
> 1)若 $A$ is not invertible：
>    - $A$ is not invertible $\implies$ $\text{det}(A)=0$ $\implies$ 右边=0
>    - $A$ is not invertible $\implies$ $AB$ is not invertible（因为 $AB$ 可以看作将两个矩阵所代表的函数串联，先经过 $B$ 再经过 $A$，$A$ 不可逆导致整体不可逆） $\implies$ $\text{det}(AB)=0$，即左边=0
> 2)若 $A$ is invertible：则 $A=E_k\cdots E_2 E_1$（$E$ 是 elementary matrix）
>    下面证明一个引理：$\text{det}(EA)=\text{det}(E)\text{det}(A)$
>    elementary matrix $E$ 分为以下三类：
>    ① Interchange：仅改变 determinant 的正负
>     故 $\text{det}(EA)=-\text{det}(A)$，$\text{det}(E)=-\text{det}(I)=-1$。故左边=右边。
>    ② Scaling (non-zero)：使 determinant 乘 k (k≠0)
>     故 $\text{det}(EA)=k\cdot\text{det}(A)$，$\text{det}(E)=k\cdot\text{det}(I)=k$。故左边=右边。
>    ③ Row addition：不改变 determinant
>     故 $\text{det}(EA)=\text{det}(A)$，$\text{det}(E)=\text{det}(I)=1$。故左边=右边。
>    引理证明结束。
>    左边：$\text{det}(AB)=\text{det}(E_k \cdots E_2 E_1 B)=\text{det}(E_k)\cdots\text{det}(E_2)\text{det}(E_1)\text{det}(B)$
>    右边：$\text{det}(A)\text{det}(B)=\text{det}(E_k \cdots E_2 E_1)\text{det}(B)=\text{det}(E_k)\cdots\text{det}(E_2)\text{det}(E_1)\text{det}(B)$

##### 对矩阵做 transpose，不会改变矩阵的 determinant

> [!important] Theorem
> $A$ 是方阵，有：
> $$\text{det}(A)=\text{det}(A^T)$$

> 证明：
> 1)若 $A$ is not invertible：
>    - $A$ is not invertible $\implies$ $\text{det}(A)=0$ $\implies$ 左边=0
>    - $A$ is not invertible $\implies$ $\text{rank}(A)<n$ $\implies$ $\text{rank}(A^T)<n$ $\implies$ $A^T$ 中 non-zero rows 的个数 < n，即 $A^T$ 中有 zero row，因此 $\text{det}(A^T)=0$ $\implies$ 右边=0
> 2)若 $A$ is invertible：则 $A=E_k\cdots E_2 E_1$（$E$ 是 elementary matrix）
>    下面证明一个引理：$\text{det}(E)=\text{det}(E^T)$
>    elementary matrix $E$ 分为以下三类：
>    ① Interchange：$E$ 是对称矩阵，因此 $E=E^T$，故 $\text{det}(E)=\text{det}(E^T)$
>     例如 $E=\begin{bmatrix}1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0\end{bmatrix}$ 是对称矩阵
>    ② Scaling (non-zero)：$E$ 是对称矩阵，因此 $E=E^T$，故 $\text{det}(E)=\text{det}(E^T)$
>     例如 $E=\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 3\end{bmatrix}$ 是对称矩阵
>    ③ Row addition：设 $E$ 是将 $I$ 的第 $i$ 行乘以 $c$ 加到第 $j$ 行得到的，则 $E^T$ 是将 $I$ 的第 $i$ 列乘以 $c$ 加到第 $j$ 列得到的，因此 $\text{det}(E)=\text{det}(E^T)$
>     例如 $E=\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 2 & 0 & 1\end{bmatrix}$，$E^T=\begin{bmatrix}1 & 0 & 2 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix}$
>    引理证明结束。
>    左边：$\text{det}(A)=\text{det}(E_k \cdots E_2 E_1)=\text{det}(E_k)\cdots\text{det}(E_2)\text{det}(E_1)$
>    右边：
>    $\begin{aligned}\text{det}(A^T)&=\text{det}((E_k\cdots E_2 E_1)^T)\\&=\text{det}(E_1^T E_2^T \cdots E_k^T)\\&=\text{det}(E_1^T)\text{det}(E_2^T)\cdots\text{det}(E_k^T)\\&=\text{det}(E_1)\text{det}(E_2)\cdots\text{det}(E_k)\end{aligned}$

# Cramer’s Rule

### Formula of $A^{-1}$

> [!important] Theorem
> $A$ 是 invertible 的 $n\times n$ 矩阵，有：
> $$A^{-1}=\cfrac{1}{\text{det}(A)}C^T$$
> 其中，$C$ 是由 $A$ 的所有 cofactor 构成的矩阵：$C = \begin{bmatrix}c_{11} & c_{12} & \cdots & c_{1n} \\ c_{21} & c_{22} & \cdots & c_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ c_{n1} & c_{n2} & \cdots & c_{nn}\end{bmatrix}$。
> ==$C^T$== 称为 $A$ 的 **adjugate matrix**（伴随矩阵）。

> 示例：可逆矩阵 $A=\begin{bmatrix}a & b \\ c & d\end{bmatrix}$，求 $A^{-1}$。
> 解：$A^{-1}=\cfrac{1}{\text{det}(A)}C^T=\cfrac{1}{ad-bc}C^T$
> $C=\begin{bmatrix}d & -c \\ -b & a\end{bmatrix}$，则 $C^T=\begin{bmatrix}d & -b \\ -c & a\end{bmatrix}$
> 因此 $A^{-1}=\cfrac{1}{ad-bc}\begin{bmatrix}d & -b \\ -c & a\end{bmatrix}$

> 证明：$A^{-1}=\cfrac{1}{\text{det}(A)}C^T$ $\iff$ $AC^T=\text{det}(A)I_n$
> 只要证 $AC^T=\text{det}(A)I_n$
> 只要证 $\begin{bmatrix}a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn}\end{bmatrix} \begin{bmatrix}c_{11} & c_{21} & \cdots & c_{n1} \\ c_{12} & c_{22} & \cdots & c_{n2} \\ \vdots & \vdots & \ddots & \vdots \\ c_{1n} & c_{2n} & \cdots & c_{nn}\end{bmatrix} = \begin{bmatrix} \det(A) & 0 & \cdots & 0 \\ 0 & \det(A) & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & \det(A) \end{bmatrix}$
> 只需验证等号右边矩阵的每个 entry 都等于左侧矩阵乘法中对应行/列的 inner product 即可：
> ①对角线元素：根据 $\det(A)$ 的定义，对角线元素正等于 **$\det(A)$**。
> ![[Pasted image 20260420145115.png|632]]
> ②非对角线元素：等号右边矩阵的 $(i,j)$-entry = $a_{i1}c_{j1} + a_{i2}c_{j2} + \cdots + a_{in}c_{jn}$（$i\ne j$）
>    构造一个新矩阵 $A'$：把 $A$ 的第 $j$ 行换成第 $i$ 行，导致该矩阵有两行相同，则 $\text{det}\ A'=0$。
>    将该矩阵按第 $j$ 行展开：$\text{det}\ A'=a_{i1}c_{j1} + a_{i2}c_{j2} + \cdots + a_{in}c_{jn}$（注意：这里的 $c_{j1},c_{j2},\cdots,c_{jn}$ 还是原矩阵 $A$ 的 cofactor，因为删的是第 $j$ 行）
>    所以 $a_{i1}c_{j1} + a_{i2}c_{j2} + \cdots + a_{in}c_{jn}=0$
>    以下是一个案例：
>    ![[Pasted image 20260420152516.png|577]]

### Cramer’s Rule

> [!important] Theorem
> $A$ 是 invertible 的 $n\times n$ 矩阵，则线性方程组 $A\mathbf{x}=\mathbf{b}$ 的解为：$$\mathbf{x}_i=\cfrac{\text{det}(B_i)}{\text{det}(A)}\quad \text{( } i = 1, 2, \cdots, n\text{ )}$$
> 其中，$B_i$ 表示将矩阵 $A$ 的**第 $i$ 列**替换为向量 $\mathbf{b}$ 后得到的矩阵。

> 证明：$A\mathbf{x}=\mathbf{b}$ 的解 $\mathbf{x}=A^{-1}\mathbf{b}=\cfrac{1}{\text{det}(A)}C^T\mathbf{b}$
> $C^T=\begin{bmatrix}c_{11} & c_{21} & \cdots & c_{n1} \\ c_{12} & c_{22} & \cdots & c_{n2} \\ \vdots & \vdots & \ddots & \vdots \\ c_{1n} & c_{2n} & \cdots & c_{nn}\end{bmatrix}$，则：
> $x_1=\cfrac{1}{\text{det}(A)}(b_1c_{11}+b_2c_{21}+\cdots+b_nc_{n1})$，括号内表达式 = $\text{det}\begin{bmatrix}b_1 & a_{12} & \cdots & a_{1n} \\b_2 & a_{22} & \cdots & a_{2n} \\\vdots & \vdots & \ddots & \vdots \\b_n & a_{n2} & \cdots & a_{nn}\end{bmatrix}$，将它记作 $\text{det}(B_1)$，因此 $x_1=\cfrac{\text{det}(B_1)}{\text{det}(A)}$。
> 同理 $x_2=\cfrac{\text{det}(B_2)}{\text{det}(A)}$，…，$x_n=\cfrac{\text{det}(B_n)}{\text{det}(A)}$。
