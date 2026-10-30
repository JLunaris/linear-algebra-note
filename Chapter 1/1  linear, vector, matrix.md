
# Linear System

**system** 也称为 **function**、**transformation**、**operator**，根据输入产生输出。

具有以下两个特征的 system 称为 **linear system**：

1. ==Preserving Scaling==：输入乘上 $k$ 倍，输出也会乘上 $k$ 倍。
   ![[Pasted image 20260203165900.png|592]]

2. ==Preserving Addition==：输入 $x_1$ 输出 $y_1$，输入 $x_2$ 输出 $y_2$，则输入 $x_1+x_2$ 输出 $y_1+y_2$。
   ![[Pasted image 20260203170041.png|620]]

> 案例：判断是否为线性系统
> 
> 【例1】$f(x)=x^2$ 是不是线性系统？
> 
> 解：$f(kx)=k^2x^2\neq kf(x)$，不满足“Preserving Scaling”.
> $f(x_1+x_2)=(x_1+x_2)^2\neq f(x_1)+f(x_2)$，不满足“Preserving Addition”.
> 因此不是线性系统.
> 
> 【例2】如图，对矩阵做 transpose 的系统，是不是线性系统？
> ![[Pasted image 20260203175417.png|429]]
> 
> 解：记系统为 $f(A)=A^T$.
> $f(kA)=(kA)^T=kA^T=kf(A)$，满足“Preserving Scaling”.
> $f(A+B)=(A+B)^T=A^T+B^T=f(A)+f(B)$，满足“Preserving Addition”.
> 因此是线性系统.
> 
> 【例3】如图，对函数求导的系统，是不是线性系统？
> ![[Pasted image 20260203175953.png|422]]
> 
> 解：$[k \cdot f(x)]'=k \cdot f'(x)$，满足“Preserving Scaling”.
> $[f(x)+g(x)]'=f'(x)+g'(x)$，满足“Preserving Addition”.
> 因此是线性系统.
> 
> 【例4】如图，对函数积分的系统，是不是线性系统？
> ![[Pasted image 20261029175045.png|464]]
> 
> 解：$\displaystyle\int_a^b cf(x)\,\mathrm{d}x=c\displaystyle\int_a^b f(x)\,\mathrm{d}x$，满足“Preserving Scaling”.
> $\displaystyle\int_a^b [f(x)+g(x)]\,\mathrm{d}x=\int_a^b f(x)\,\mathrm{d}x+\int_a^b g(x)\,\mathrm{d}x$，满足“Preserving Addition”.
> 因此是线性系统.

> [!NOTE] Note
> 微分和积分系统都属于线性系统。

# Vector

> [!example] vector（非严格定义）
> $n$ 个数 $v_1,v_2,\cdots,v_n$ 组成的有序数组 $\mathbf{v}=\begin{bmatrix}v_1 \\ v_2 \\ \vdots \\ v_n\end{bmatrix}$ 叫做 $n$ 维**向量**，其中 $v_1,v_2,\cdots,v_n$ 叫做向量 $\mathbf{v}$ 的分量（**component**），例如 $v_i$ 就是向量 $\mathbf{v}$ 的第 $i$ 个分量。

> [!example] $\mathbb{R}^n$
> <font color="#c0504d">所有</font>含有 $n$ 个分量的向量（且分量均为实数）构成的集合，在数学上记作 $\mathbb{R}^n$。

> 这个符号包含了几个核心信息：$\mathbb{R}$ 代表实数集，$n$ 代表维数（即向量中分量的个数）。

### Properties of Vector

不是说向量有以下特征，而是==有以下特征的东西被定义为向量==：

![[Pasted image 20260204110441.png]]

### Unit Vector

> [!example] unit vector（单位向量）
> <font color="#c0504d">只有一个分量是 $1$，其他分量都是 $0$</font> 的向量称为**单位向量**。
> 
> 记作 $\mathbf{e}_i$，其中 $i$ 表示第几个分量是 $0$。

# Matrix

> [!example] matrix
> 由 $m\times n$ 个数排成 $m$ 行 $n$ 列的如下矩形阵列：
> $$\boldsymbol{A} = \begin{pmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{pmatrix}$$
> 称为一个 $m$ 行 $n$ 列的**矩阵**。
> 
> - 称该矩阵的 **size** 是 <font color="#c0504d">m by n</font>，记作 $m \times n$。
> - 矩阵的第 $i$ 行第 $j$ 列元素称为该矩阵的 **(i, j)-entry**。

> 矩阵 $A$ 可以写为这种形式：$A=\begin{bmatrix}\mathbf{a}_1 & \mathbf{a}_2 & ... & \mathbf{a}_n \end{bmatrix}$。其中，每个 $\mathbf{a}_j$ 是矩阵的第 $j$ 列。

> 向量也可以视为矩阵：例如 $\begin{bmatrix} 1\\ 2\\ 3\end{bmatrix}$ 是 $3 \times 1$ 的矩阵，$\begin{bmatrix} 1 & 2 & 3 \end{bmatrix}$ 是 $1 \times 3$ 的矩阵。

- 若两个矩阵的行数、列数分别相等，则称这两个矩阵是**同型的**。
- 若两个同型矩阵 $A$ 和 $B$ 的所有对应元素都相等，即 $a_{ij}=b_{ij}$，则称矩阵 $A$ 和矩阵 $B$ **相等**，记作 $A=B$。
- 所有 $m$ 行 $n$ 列的矩阵构成的集合，通常记作 $M_{m \times n}$。

### 加减、数乘运算

- 加减：两个同型矩阵可以相加减。定义为两矩阵的各对应元素加减。
- 标量乘法：矩阵中的每个元素都乘上该数字。
- 性质：
  ![[Pasted image 20260205112352.png|608]]

### Transpose

如果 $A$ 是 $m\times n$ 矩阵，则 $A^T$（transpose of $A$）是 $n\times m$ 矩阵，它的 (i,j)-entry 是 $A$ 的 (j-i)-entry.

![[Pasted image 20260205130241.png|434]]

![[Pasted image 20260205150228.png|606]]

性质 (a) 和 (b) 说明 Transpose 是一个 Linear System.

### 特殊的矩阵

##### Square Matrix

The matrix is **square** if $m = n$.
![[Pasted image 20260205113048.png|216]]

- ==Upper/Lower Triangular Matrix==

  ![[Pasted image 20260205113411.png|300]]
  上三角矩阵：对角线下方都是`0`.
  下三角矩阵：对角线上方都是`0`.

- ==Diagonal Matrix==

  ![[Pasted image 20260205114100.png|269]]

  一般形式为 $\begin{bmatrix}d_1 & 0 & \cdots & 0 \\ 0 & d_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & d_n\end{bmatrix}$，记作 $\text{diag}(d_1, d_2, \dots, d_n)$。

- ==Identity Matrix==
  单位矩阵（通常记作 $I$ 或 $I_n$）是一个**主对角线全为 1，其余元素全为 0** 的方阵。$$I_n = \begin{bmatrix}
1 & 0 & \cdots & 0 \\ 0 & 1 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1
\end{bmatrix} = \begin{bmatrix} \mathbf{e}_1 & \mathbf{e}_2 & \cdots & \mathbf{e}_n \end{bmatrix}$$上式中 $n$ 表示矩阵的 size 为 $n \times n$，$\mathbf{e}_j$ 表示单位向量。

- ==Symmetric Matrix==
  满足 $A^T=A$ 的矩阵（一定是方阵）。
  
  例如，令 $A=\begin{bmatrix}1 & 2 & 4 \\ 2 & 3 & -1 \\ 4 & -1 & 5\end{bmatrix}$. 则 $A^T=\begin{bmatrix}1 & 2 & 4 \\ 2 & 3 & -1 \\ 4 & -1 & 5\end{bmatrix}=A$. 因此 $A$ 是对称的.
  
  In general, a square matrix $A$ is symmetric if and only if $a_{ij} = a_{ji}$ for all $i$ and $j$ .

##### Zero Matrix

![[Pasted image 20260205120821.png|385]]

# Matrix-Vector Product

![[Pasted image 20260205161050.png|352]]
要使矩阵 $A$ 与向量 $\mathbf{x}$ 能够相乘（$A\mathbf{x}$），必须满足前提：矩阵 $A$ 的列数=向量 $\mathbf{x}$ 的行数。

- ==Row Aspect：Inner Product with Row==
  矩阵 $A$ 的**每一行**分别与**向量 $\mathbf{x}$** 做内积。
  ![[Pasted image 20260205163216.png|446]]
  例如，$A = \begin{bmatrix} 2 & 3 & 1 \\ 1 & 5 & 3 \end{bmatrix}$，$\mathbf{x} = \begin{bmatrix} 4 \\ 1 \\ 3 \end{bmatrix}$，则 $A\mathbf{x}=\begin{bmatrix}2\times 4+3\times 1+1\times3 \\ 1\times 4 + 5\times 1 + 3 \times 3\end{bmatrix}$.

- ==Column  Aspect：Weighted sum of Columns==
  矩阵 $A$ 的**每一列**分别与**向量 $\mathbf{x}$ 的对应分量**相乘，做 weighted sum.
  ![[Pasted image 20260205170054.png|446]]

### Properties of Matrix-Vector Product

> [!important] 性质
> $A$、$B$ 是 $m \times n$ 矩阵，$\mathbf{u}$、$\mathbf{v}$ 是 $\mathbb{R}^n$ 中的向量，$c$ 为标量。则：
> 1. $A(\mathbf{u}+\mathbf{v})=A\mathbf{u}+A\mathbf{v}$.
> 2. $A(c\mathbf{u})=c(A\mathbf{u})=(cA)\mathbf{u}$.
> 3. $(A+B)\mathbf{u}=A\mathbf{u}+B\mathbf{u}$.
> 4. $A\mathbf{0}=\mathbf{0}$.（其中第一个 $\mathbf{0} \in \mathbb{R}^n$，第二个 $\mathbf{0} \in \mathbb{R}^m$）
> 5. $O\mathbf{v}=\mathbf{0}$.（其中零矩阵 $O_{m\times n}$，$\mathbf{0}\in \mathbb{R}^m$）
> 6. $I_n \mathbf{v}=\mathbf{v}$.

> 证明：$A=\begin{bmatrix} \mathbf{a_1} & \mathbf{a_2} & \cdots & \mathbf{a_n}\end{bmatrix}$，$B=\begin{bmatrix} \mathbf{b_1} & \mathbf{b_2} & \cdots & \mathbf{b_n}\end{bmatrix}$，$\mathbf{u} = \begin{bmatrix} u_1 \\ u_2 \\ \vdots \\ u_n \end{bmatrix}$ 和 $\mathbf{v} = \begin{bmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{bmatrix}$.
> <font color="#c0504d">命题1</font>：根据矩阵乘法定义：
> $\begin{aligned}左边 &= (u_1+v_1)\mathbf{a}_1+(u_2+v_2)\mathbf{a}_2+\cdots+(u_n+v_n)\mathbf{a}_n \\ &= (u_1\mathbf{a}_1+u_2\mathbf{a}_2+\cdots+u_n\mathbf{a}_n)+(v_1\mathbf{a}_1+v_2\mathbf{a}_2+\cdots+v_n\mathbf{a}_n) \\ &= A\mathbf{u}+A\mathbf{v} = 右边 \end{aligned}$
> <font color="#c0504d">命题2-6</font>：同理1.

> [!important] 矩阵 column 的提取
> $A$ 是 $m\times n$ 矩阵，有
> $$A\mathbf{e}_j=\mathbf{a}_j$$
> 其中单位向量 $\mathbf{e}_j \in \mathbb{R}^n$，$\mathbf{a}_j$ 是 $A$ 的第 j 列。

> [!important] Theorem
> $A$、$B$ 都是 $m \times n$ 矩阵。
> 
> 若 $\forall \mathbf{v} \in \mathbb{R}^n, A\mathbf{v}=B\mathbf{v}$，则 $A=B$。

> 证明：要证矩阵相等，只要证它们的每一列都对应相等。
> ![[Pasted image 20260206172816.png|452]]

> 事实上，只需要对任意单位向量 $\mathbf{e}_i\in\mathbb{R}^n$ 都有 $A\mathbf{e}_i=B\mathbf{e}_i$，则 $A=B$。
