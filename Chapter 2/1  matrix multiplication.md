
# Four Aspects for Multiplication

![[Pasted image 20260228184142.png|624]]

### Inner Product
![[Pasted image 20260228172929.png|637]]

> [!NOTE] 
> 助记：将 $A$ 放在左边，$B$ 放在上边。
> 
> ![[Pasted image 20260227182256.png|450]]

> 案例：$A=\begin{bmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix}$，$B=\begin{bmatrix} -1 & 1 \\ 3 & 2 \end{bmatrix}$，求 $AB$。
> 
> ![[Pasted image 20260227184916.png|350]]

### Linear Combination of A's Columns

![[Pasted image 20260228111105.png|500]]

> 案例：$A=\begin{bmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix}$，$B=\begin{bmatrix} -1 & 1 \\ 3 & 2 \end{bmatrix}$，求 $AB$。
> ![[Pasted image 20260228111342.png|500]]

### Linear Combination of B's Rows

![[Pasted image 20260228112923.png|500]]
> 案例：$A=\begin{bmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix}$，$B=\begin{bmatrix} -1 & 1 \\ 3 & 2 \end{bmatrix}$，求 $AB$。
> ![[Pasted image 20260228113047.png|400]]

### Summation of Matrices

![[Pasted image 20260228125129.png|550]]

> 案例：$A=\begin{bmatrix} 1 & 2 \\ 3 & 4 \\ 5 & 6 \end{bmatrix}$，$B=\begin{bmatrix} -1 & 1 \\ 3 & 2 \end{bmatrix}$，求 $AB$。
> ![[Pasted image 20260228124204.png|450]]

# Block Multiplication

> [!NOTE] Partition（分块）
> **Partition**：用若干横线和竖线将一个矩阵分成若干子矩阵（每个子矩阵称为一个 **block**）。
> 
> ![[Pasted image 20260228151736.png|400]]

$A$ 是一个 $m\times n$ 矩阵，$B$ 是一个 $n\times p$ 矩阵。对 $A$ 和 $B$ 进行分块，使得 ==$A$ 的**列分块方式**与 $B$ 的**行分块方式**一致==。在这种分块下，矩阵乘积 $AB$ 可以通过**分块矩阵乘法**来计算：将每个子矩阵视为一个 entry，从 inner product aspect 做矩阵乘法。

> 案例1：
> ![[Pasted image 20260228170740.png|400]]
> 
> 案例2：$A = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 6 & 8 & 5 & 0 \\ -7 & 9 & 0 & 5 \end{bmatrix}$，求 $A^2$，$A^3$。
> 解：
> ![[Pasted image 20260228172544.png|449]]

# 矩阵乘法的意义

> [!NOTE] Summary
> - Multiple Inputs：$AB=\begin{bmatrix}A\mathbf{b}_1 & A\mathbf{b}_2 & \cdots & A\mathbf{b}_p\end{bmatrix}$
> - Composition of Linear Systems：$(AB)\mathbf{v}=A(B\mathbf{v})$

### Multiple Inputs to a Linear System

$A$ 是一个 $m\times n$ 矩阵，$B$ 是一个 $n\times p$ 矩阵，$B=\begin{bmatrix}\mathbf{b}_1 & \mathbf{b}_2 & \cdots & \mathbf{b}_p\end{bmatrix}$。从 Linear Combination of A's Columns 角度来看：
$$AB=\begin{bmatrix}A\mathbf{b}_1 & A\mathbf{b}_2 & \cdots & A\mathbf{b}_p\end{bmatrix}$$
在这一视角下，可以将 $A$ 看作一个==线性系统==，向其中同时输入多个向量 $\mathbf{b}_1,\mathbf{b}_2,\cdots,\mathbf{b}_p$，得到多个输出向量 $A\mathbf{b}_1,A\mathbf{b}_2,\cdots,A\mathbf{b}_p$。因此矩阵乘积 $AB$ 可以看作是**将 $B$ 的各列作为输入，同时输入线性系统 $A$ 所得到的输出**。

![[Pasted image 20260301102441.png|626]]

### Composition of Linear Systems

> [!NOTE] Composition（复合）
> 如果 $f: \mathcal{S}_1 \to \mathcal{S}_2$，$g: \mathcal{S}_2 \to \mathcal{S}_3$，那么 **composition** $g \circ f: \mathcal{S}_1 \to \mathcal{S}_3$ 定义为
> $$(g \circ f)(\mathbf{u}) = g(f(\mathbf{u})),\quad \forall \mathbf{u}\in S_1$$
> ![[Pasted image 20260301111515.png|400]]
> ![[Pasted image 20260301115054.png|400]]

![[Pasted image 20260301123015.png|510]]

$A$ 是一个 $m\times n$ 矩阵，$B$ 是一个 $n\times p$ 矩阵，则对于任意的 $\mathbf{v}\in\mathbb{R}^p$，有：
$$(AB)\mathbf{v}=A(B\mathbf{v})$$
> 证明：
> $\begin{aligned}(AB)\mathbf{v} &= \begin{bmatrix}A\mathbf{b}_1 & A\mathbf{b}_2 & \cdots & A\mathbf{b}_p\end{bmatrix}\mathbf{v} \\ &= v_1(A\mathbf{b}_1)+v_2(A\mathbf{b}_2)+\cdots+v_p(A\mathbf{b}_p)\\ &=A(v_1\mathbf{b}_1+v_2\mathbf{b}_2+\cdots+v_p\mathbf{b}_p)\\ &=A(B\mathbf{v})\end{aligned}$

> 案例：如果矩阵 $B$ 表示一种线性变换（比如缩放），矩阵 $A$ 表示另一种线性变换（比如平移），那么 $AB$ 表示先做 $B$ 变换，再做 $A$ 变换。其本质正是 $(AB)\mathbf{v}=A(B\mathbf{v})$。

# 矩阵乘法的属性

> [!NOTE] Matrix Multiplication Is Not Commutative
> 对于任意矩阵 $A$ 和 $B$，$AB$ 不一定等于 $BA$。

> Q：对于矩阵 $A$ 和 $B$，若 $AB$ 和 $BA$ 均有定义，则 $A$ 和 $B$ 需要满足什么条件？
> A：$A$ 是 $m\times n$ 矩阵，$B$ 是 $n\times m$ 矩阵。

---

> [!important] Properties of Matrix Multiplication
> $A$ 和 $B$ 是 $k \times m$ 矩阵，$C$ 是 $m \times n$ 矩阵，$P$ 和 $Q$ 是 $n \times p$ 矩阵。则下列命题成立：
> 1. **数乘结合律**：对任意标量 $s$，$s(AC)=(sA)C=A(sC)$
> 2. **结合律**：$A(CP)=(AC)P$
> 3. **分配率**
>     - 右分配率：$(A+B)C=AC+BC$
>     - 左分配率：$C(P+Q)=CP+CQ$
> 4. $I_k A=A=AI_m$
> 5. 任何矩阵与零矩阵的乘积都是零矩阵。
> 6. $(AC)^T=C^TA^T$

> **证明**(1-5)：
> 思路：将矩阵乘法展开为多个 Matrix-Vector Product，利用 Matrix-Vector Product 的性质进行推导，最后再收回为矩阵乘法。以②为例，其余同理。
> 
> $\begin{aligned}A(CP)&=A\begin{bmatrix}C\mathbf{p}_1 & C\mathbf{p}_2 & \cdots & C\mathbf{p}_p\end{bmatrix}\\ &=\begin{bmatrix}A(C\mathbf{p}_1) & A(C\mathbf{p}_2) & \cdots & A(C\mathbf{p}_p)\end{bmatrix}\\ &=\begin{bmatrix}(AC)\mathbf{p}_1 & (AC)\mathbf{p}_2 & \cdots & (AC)\mathbf{p}_p\end{bmatrix}\\ &=(AC)P\end{aligned}$
> 注释：
> - 第1个等号：矩阵乘法意义之“Multiple Inputs to a Linear System”，展开 $CP$
> - 第2个等号：矩阵乘法意义之“Multiple Inputs to a Linear System”，展开 $AB$，其中 $B$ 的每一列分别是 $C\mathbf{p}_1,C\mathbf{p}_2, \cdots , C\mathbf{p}_p$
> - 第3个等号：矩阵乘法意义之“Composition of Linear Systems”，$A(B\mathbf{v})=(AB)\mathbf{v}$
> - 第4个等号：矩阵乘法意义之“Multiple Inputs to a Linear System“，收回为 $(AC)P$

> **证明**(6)：
> $A = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1m} \\ a_{21} & a_{22} & \cdots & a_{2m} \\ \vdots & \vdots & \ddots & \vdots \\ a_{k1} & a_{k2} & \cdots & a_{km} \end{bmatrix}, \quad C = \begin{bmatrix} c_{11} & c_{12} & \cdots & c_{1n} \\ c_{21} & c_{22} & \cdots & c_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ c_{m1} & c_{m2} & \cdots & c_{mn} \end{bmatrix}$
> 
> $(AC)^T$ 的 ($i$, $j$)-entry 是 $AC$ 的 ($j$, $i$)-entry，也就是 **$A$ 的第 $j$ 行与 $C$ 的第 $i$ 列的 inner product**，即：
> $$\begin{bmatrix} a_{j1} & a_{j2} & \cdots & a_{jm} \end{bmatrix} \begin{bmatrix} c_{1i} \\ c_{2i} \\ \vdots \\ c_{mi} \end{bmatrix} = a_{j1}c_{1i} + a_{j2}c_{2i} + \cdots + a_{jm}c_{mi}$$
> $C^TA^T$ 的 ($i$, $j$)-entry 是 **$C^T$ 的第 $i$ 行与 $A^T$ 的第 $j$ 列的 inner product**，即：
> $$[c_{1i} \quad c_{2i} \quad \dots \quad c_{mi}] \begin{bmatrix} a_{j1} \\ a_{j2} \\ \vdots \\ a_{jm} \end{bmatrix} = c_{1i} a_{j1} + c_{2i} a_{j2} + \dots + c_{mi} a_{jm}$$
> 由于上述两个表达式相等，因此 $(AC)^T$ 的第 $(i, j)$ 个元素等于 $C^T A^T$ 的第 $(i, j)$ 个元素。 ■

---

> [!NOTE] Power of Square Matrices
> $A$ 是 $n\times n$ **方阵**，其幂定义为连乘：$A^k = \underbrace{A A \cdots A}_{k \text{ 个}} \quad (k \ge 1)$。
> 规定 ==$A^0=I_n$==。

---

> [!NOTE] 两个 Diagonal Matrix 相乘
> $A = \text{diag}(a_1, a_2, \dots, a_n)$，$B = \text{diag}(b_1, b_2, \dots, b_n)$。它们的乘积仍然是一个对角矩阵，且对角线上的元素是 $A$、$B$ 中对应元素的乘积：==$AB = \text{diag}(a_1b_1, a_2b_2, \cdots, a_nb_n)$==

> 案例：
> ![[Pasted image 20260302111558.png|500]]

---

> [!NOTE] 
> $AA^T$ 和 $A^TA$ 都是对称矩阵。（$A$ 可以是任何矩阵）

> 证明：要证 $C$ 是对称矩阵，只要证 $C^T=C$。
> $(AA^T)^T=A^{TT}A^T=AA^T$ 
> $(A^TA)^T=A^TA^{TT}=A^TA$

##### Practical Computation Issue

> [!question] Thinking
> Q：$A$ 是 $m\times n$ 矩阵，$B$ 是 $n\times p$ 矩阵，则计算 $AB$ 需要执行多少次乘法运算？
> A：$AB$ 中共有 $m\times p$ 个元素，每个元素都由 $n$ 次乘法运算得到，总共需要 ==$mnp$== 次乘法运算。

设 $A$ 是 $k \times m$ 矩阵，$C$ 是 $m \times n$ 矩阵，$P$ 是 $n \times p$ 矩阵。矩阵乘法满足结合律，虽然 $A(CP)$ 与 $(AC)P$ 的结果相同，但不同的计算顺序会导致运算量差异巨大：

- $A(CP)$：共执行 $(mnp+kmp)$ 次乘法运算
- $(AC)P$：共执行 $(kmn+knp)$ 次乘法运算

这两个数在实际问题中**可能相差几个数量级**。

# 方阵的 trace

矩阵 $A$ 是 $n\times n$ 方阵，定义 $A$ 的 **trace** 为 $A$ 的**对角线元素之和**：
$$\text{trace}(A)=a_{11}+a_{22}+\cdots+a_{nn}$$

> [!important] Theorem
> $A$ 是 $m\times n$ 矩阵，$B$ 是 $n\times m$ 矩阵，有：==$\text{trace}(AB)=\text{trace}(BA)$==

> 证明：
> $AB$ 是 $m\times m$ 方阵，其第 $i$ 个对角元素为 $\begin{bmatrix}a_{i1} & a_{i2} & \cdots & a_{in}\end{bmatrix}\begin{bmatrix}b_{1i} \\ b_{2i} \\ \vdots \\ b_{ni}\end{bmatrix}=\sum\limits_{j=1}^{n}a_{ij}b_{ji}$
> $\text{trace}(AB)=\sum\limits_{i=1}^{m}\sum\limits_{j=1}^{n}a_{ij}b_{ji}$
> $BA$ 是 $n\times n$ 矩阵，其第 $i$ 个对角元素为 $\begin{bmatrix}b_{i1} & b_{i2} & \cdots & b_{im}\end{bmatrix}\begin{bmatrix}a_{1i} \\ a_{2i} \\ \vdots \\ a_{mi}\end{bmatrix}=\sum\limits_{j=1}^{m}b_{ij}a_{ji}$
> $\text{trace}(BA)=\sum\limits_{i=1}^{n}\sum\limits_{j=1}^{m}b_{ij}a_{ji}$
> $\xrightarrow{换个变量名}$ $\text{trace}(BA)=\sum\limits_{j=1}^{n}\sum\limits_{i=1}^{m}b_{ji}a_{ij}$
> $\xrightarrow{交换求和符号顺序}$ $\text{trace}(BA)=\sum\limits_{i=1}^{m}\sum\limits_{j=1}^{n}b_{ji}a_{ij}$
> 
> 因此 $\text{trace}(AB)=\text{trace}(BA)$

> [!NOTE] 
> 可以把 $\sum$ 求和类比为编程语言中的 **for 循环**，例如 $\sum\limits_{i=1}^{n}\sum\limits_{j=1}^{m}b_{ij}a_{ji}$ 可以看作：
> ```
> double sum = 0;
> for(int i = 1; i <= n; ++i)
> 	for(int j = 1; j <= m; ++j)
> 		sum += b[i][j] * a[j][i];
> ```

