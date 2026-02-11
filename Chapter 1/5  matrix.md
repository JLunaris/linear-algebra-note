
# Matrix

![[Pasted image 20260205095905.png|500]]

1. `m`行`n`列，称矩阵的 **size** 为 **m by n**，记作 $m \times n$ .
2. 所有`m`行`n`列的矩阵构成的集合，在数学上记作 $\mathbb{M}_{m \times n}$ .
3. 某些向量也是矩阵：例如 $\begin{bmatrix} 1\\ 2\\ 3\end{bmatrix}$ 是 $3 \times 1$ 的矩阵，$\begin{bmatrix} 1 & 2 & 3 \end{bmatrix}$ 是 $1 \times 3$ 的矩阵.
4. 矩阵的第`i`行第`j`列元素称为该矩阵的 **(i, j)-entry** 。
5. 矩阵![[Pasted image 20260205110015.png|200]]可以写为这种形式：$A=\begin{bmatrix}\mathbf{a}_1 & \mathbf{a}_2 & ... & \mathbf{a}_n \end{bmatrix}$。
   其中，每个 $\mathbf{a}_j$ 是矩阵的第 j 列。

# Properties of Matrix

- 加减：Two matrices with the ==same size== can add or subtract. 两矩阵的各对应元素加减。
- 标量乘法：矩阵中的每个元素都乘上该数字。
- 性质：矩阵也是向量，满足向量的基本性质（见[[3  vector#向量的严格定义]]），例如：
  ![[Pasted image 20260205112352.png]]

# 特殊矩阵

### Square Matrix

![[Pasted image 20260205113048.png|250]]
##### Upper/Lower Triangular Matrix

![[Pasted image 20260205113411.png|300]]
上三角矩阵：对角线下方都是`0`.
下三角矩阵：对角线上方都是`0`.

##### Diagonal Matrix

![[Pasted image 20260205114100.png|300]]

##### Identity Matrix

单位矩阵（通常记作 $I$ 或 $I_n$）是一个**主对角线全为 1，其余元素全为 0** 的方阵。
$$I_n = \begin{bmatrix}
1 & 0 & \cdots & 0 \\ 0 & 1 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1
\end{bmatrix} = \begin{bmatrix} \mathbf{e}_1 & \mathbf{e}_2 & \cdots & \mathbf{e}_n \end{bmatrix}$$

- $n$ 表示矩阵的 size 为 $n \times n$
- $\mathbf{e}_j$ 表示单位向量

##### Symmetric Matrix

满足 $A^T=A$ 的矩阵（一定是方阵）。

例如，令 $A=\begin{bmatrix}1 & 2 & 4 \\ 2 & 3 & -1 \\ 4 & -1 & 5\end{bmatrix}$. 则 $A^T=\begin{bmatrix}1 & 2 & 4 \\ 2 & 3 & -1 \\ 4 & -1 & 5\end{bmatrix}=A$. 因此 $A$ 是对称的.

In general, a square matrix $A$ is symmetric if and only if $a_{ij} = a_{ji}$ for all $i$ and $j$ .

### Zero Matrix

![[Pasted image 20260205120821.png|500]]

# Transpose

如果`A`是 $m\times n$ 矩阵，则 $A^T$（transpose of `A`）是 $n\times m$ 矩阵，它的 (i,j)-entry 是`A`的 (j-i)-entry.

![[Pasted image 20260205130241.png|500]]

---

![[Pasted image 20260205150228.png]]
性质 (a) 和 (b) 说明 Transpose 是一个 Linear System.