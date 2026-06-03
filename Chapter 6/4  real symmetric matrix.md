
# Real Symmetric Matrix

### 实对称矩阵的 eigenvalue 都是实数

> [!important] Theorem
> 实对称矩阵的 eigenvalue 都是实数。

> 证明（看懂即可）：实对称矩阵 $A$，有 eigenvalue $\lambda$。设 $\lambda=a+bi$。只要证 $b=0$。
> 设 $\mathbf{v}$ 是 $\lambda$ 对应的 eigenvector，则 $A\mathbf{v}=\lambda\mathbf{v}$ $\implies$ $\overline{A\mathbf{v}}=\overline{\lambda\mathbf{v}}$ $\implies$ $\bar{A}\bar{\mathbf{v}}=\bar{\lambda}\bar{\mathbf{v}}$ 
> 由于 $A$ 是实对称矩阵，因此 $A=\bar{A}$，因此 $\implies$ $A\bar{\mathbf{v}}=\bar{\lambda}\bar{\mathbf{v}}$
> $\overline{\mathbf{v}}^TA\mathbf{v}=\overline{\mathbf{v}}^T\lambda\mathbf{v}=\lambda\overline{\mathbf{v}}^T\mathbf{v}$ ……①
> $\overline{\mathbf{v}}^TA\mathbf{v}=\overline{\mathbf{v}}^TA^T\mathbf{v}=(A\overline{\mathbf{v}})^T\mathbf{v}=(\bar{\lambda}\overline{\mathbf{v}})^T\mathbf{v}=\bar{\lambda}\overline{\mathbf{v}}^T\mathbf{v}$ ……②
> 由①②知 $\lambda\overline{\mathbf{v}}^T\mathbf{v}=\bar{\lambda}\overline{\mathbf{v}}^T\mathbf{v}$
> 设 $\mathbf{v}=\begin{bmatrix}a_1+b_1i \\ a_2+b_2i \\ \vdots \\ a_n+b_ni\end{bmatrix}$，则 $\overline{\mathbf{v}}=\begin{bmatrix}a_1-b_1i \\ a_2-b_2i \\ \vdots \\ a_n-b_ni\end{bmatrix}$，则 $\overline{\mathbf{v}}^T\mathbf{v}=\overline{\mathbf{v}}\cdot\mathbf{v}=(a_1^2+b_1^2)+(a_2^2+b_2^2)+\cdots+(a_n^2+b_n^2)$
> 由于 eigenvector $\neq \mathbf{0}$，因此 $a_i,b_i$ 不全为 $0$，因此 $\overline{\mathbf{v}}^T\mathbf{v}>0$。
> 故 $\lambda\overline{\mathbf{v}}^T\mathbf{v}=\bar{\lambda}\overline{\mathbf{v}}^T\mathbf{v}$ $\implies$ $\lambda=\bar{\lambda}$ $\implies$ $b=0$

### 实对称矩阵的不同的 eigenvalue 对应的 eigenvector 是 orthogonal 的

> [!important] Theorem
> 实对称矩阵的不同的 eigenvalue 对应的 eigenvector 是 orthogonal 的。

> 证明（看懂即可）：实对称矩阵 $A$，有 eigenvalue $\lambda$、$\mu$（$\lambda\neq\mu$），设 $\lambda$ 对应的 eigenvector 是 $\mathbf{u}$，$\mu$ 对应的 eigenvector 是 $\mathbf{v}$。只要证 $\mathbf{u}\perp\mathbf{v}$。
> 已知 $A\mathbf{u}=\lambda\mathbf{u}$、$A\mathbf{v}=\mu\mathbf{v}$。
> $A\mathbf{u}\cdot\mathbf{v}=\lambda\mathbf{u}\cdot\mathbf{v}=\lambda(\mathbf{u}\cdot\mathbf{v})$ ……①
> $A\mathbf{u}\cdot\mathbf{v}=(A\mathbf{u})^T\mathbf{v}=\mathbf{u}^TA^T\mathbf{v}=\mathbf{u}^TA\mathbf{v}=\mathbf{u}\cdot A\mathbf{v}=\mathbf{u}\cdot\mu\mathbf{v}=\mu(\mathbf{u}\cdot\mathbf{v})$ ……②
> 由①②知 $\lambda(\mathbf{u}\cdot\mathbf{v})=\mu(\mathbf{u}\cdot\mathbf{v})$。而 $\lambda\neq\mu$，因此 $\mathbf{u}\cdot\mathbf{v}=0$。

### 实对称矩阵一定可正交对角化

> [!example] orthogonal diagonalizable（可正交对角化的）
> 对于方阵 $A$，若存在 ==orthogonal matrix== $P$、对角矩阵 $D$ 使得 $A=PDP^{-1}$（也可等价写为 ==$A=PDP^T$==），则称 $A$ 是**可正交对角化的**。

> [!important] Theorem
> 1. $A$ 是实对称矩阵 $\implies$ $A$ 可正交对角化
> 2. $A$ 可正交对角化 $\implies$ $A$ 是对称矩阵

> 证明：
> **命题1**：略
> **命题2**：$A^T=(PDP^T)^T=(P^T)^TD^TP^T=PDP^T=A$，因此 $A$ 是对称矩阵（但不一定是实对称矩阵）

##### 实对称矩阵的正交对角化

> 案例：orthogonal diagonalization of real symmetric matrices
> 
> 【例1】$A=\begin{bmatrix}2 & -2 \\ -2 & 5\end{bmatrix}$，求一个 orthogonal matrix $P$ 和对角矩阵 $D$ 使 $P^TAP=D$。
> 
> 解：$P^TAP=D$ $\iff$ $A=PDP^T$。只要对实对称矩阵 $A$ 做正交对角化。
> 特征多项式 $\det(A-tI_2)=(t-1)(t-6)=0$，解得 $t_1=1$，$t_2=6$。
> $1$ 对应的 eigenspace 为 $\text{Span}\ \{\begin{bmatrix}2 \\ 1\end{bmatrix}\}$，$6$ 对应的 eigenspace 为 $\text{Span}\ \{\begin{bmatrix}-1 \\ 2\end{bmatrix}\}$。
> $A$ 是实对称矩阵，因此不同 eigenvalue 对应的 eigenvector 是 orthogonal 的，因此 $\begin{bmatrix}2 \\ 1\end{bmatrix}$ 和 $\begin{bmatrix}-1 \\ 2\end{bmatrix}$ 是 orthogonal 的（更是 independent 的）。
> 对这两个向量做 normalization 后组成 $P = \begin{bmatrix} \frac{2}{\sqrt{5}} & -\frac{1}{\sqrt{5}} \\ \frac{1}{\sqrt{5}} & \frac{2}{\sqrt{5}} \end{bmatrix}$，此时 $D = \begin{bmatrix} 1 & 0 \\ 0 & 6 \end{bmatrix}$。
> 
> 【例2】$A = \begin{bmatrix} 4 & 2 & 2 \\ 2 & 4 & 2 \\ 2 & 2 & 4 \end{bmatrix}$，求一个 orthogonal matrix $P$ 和对角矩阵 $D$ 使 $P^TAP=D$。
> 
> 解：特征多项式 $\det(A-tI_3)=-(t - 2)^2(t - 8)=0$，解得 $t_1=2$，$t_2=8$。
> $2$ 对应的 eigenspace 为 $\text{Span}\ \{\begin{bmatrix} -1 \\ 1 \\ 0 \end{bmatrix},\begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix}\}$，$8$ 对应的 eigenspace 为 $\text{Span}\ \{\begin{bmatrix}1 \\ 1 \\ 1\end{bmatrix}\}$。
> $A$ 是实对称矩阵，因此不同 eigenvalue 对应的 eigenvector 是 orthogonal 的，因此 $\{\begin{bmatrix} -1 \\ 1 \\ 0 \end{bmatrix},\begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix}\}$ 和 $\begin{bmatrix}1 \\ 1 \\ 1\end{bmatrix}$ 是 orthogonal 的。
> 但 $\{\begin{bmatrix} -1 \\ 1 \\ 0 \end{bmatrix},\begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix}\}$ 内部不是 orthogonal 的，只是 independent 的。由于这是个 basis，因此可以对它做 Gram-Schmidt Process，从而得到 orthogonal basis $\left\{\begin{bmatrix} -1 \\ 1 \\ 0 \end{bmatrix},-\cfrac{1}{2}\begin{bmatrix} 1 \\ 1 \\ -2 \end{bmatrix}\right\}$。
> 对这三个向量做 normalization 后组成 $P = \begin{bmatrix} -\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{6}} & \frac{1}{\sqrt{3}} \\ \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{6}} & \frac{1}{\sqrt{3}} \\ 0 & -\frac{2}{\sqrt{6}} & \frac{1}{\sqrt{3}} \end{bmatrix}$，此时 $D = \begin{bmatrix} 2 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 8 \end{bmatrix}$。

# 特殊的实对称矩阵

### Positive Definite Matrix

> [!example] positive definite
> ==实对称矩阵== $C$（$n\times n$），若对于任意==非零向量== $\mathbf{v}\in\mathbb{R}^n$，都有
> $$\mathbf{v}^TC\mathbf{v}> 0$$
> 称 $C$ 是 **positive definite** 的。

> [!important] Theorem
> 对于==实对称矩阵== $A$：
> $A$ 是 positive definite 的 $\iff$ $A$ 的所有 eigenvalue 都 $>0$

> 证明：
> **左推右**：任取 $A$ 的一个 eigenvalue $\lambda$，对应 eigenvector $\mathbf{v}$。只要证 $\lambda>0$。
> 由 $A$ 正定知 $\mathbf{v}^TA\mathbf{v}>0$ $\implies$ $\mathbf{v}^T \lambda\mathbf{v}>0$ $\implies$ $\lambda\|\mathbf{v}\|^2>0$ $\implies$ $\lambda>0$
> **右推左**：任取 $\mathbf{v}\in\mathbb{R}^n$，$\mathbf{v}\neq\mathbf{0}$，只要证 $\mathbf{v}^TA\mathbf{v}>0$。
> $A$ 是实对称矩阵，一定可正交对角化：$A=PDP^T$（其中 $P$ 是正交矩阵，由 $A$ 的 eigenvector 构成；$D$ 是对角矩阵，由 $A$ 的 eigenvalue 构成）。
> 则 $\mathbf{v}^TA\mathbf{v}=\mathbf{v}^TPDP^T\mathbf{v}$
> 记 $\mathbf{y}=P^T\mathbf{v}$，则 $\mathbf{v}^TA\mathbf{v}=\mathbf{y}^TD\mathbf{y}=\mathbf{y}\cdot D\mathbf{y}=\begin{bmatrix}y_1 \\ y_2 \\ \vdots \\ y_n\end{bmatrix}\cdot \begin{bmatrix}\lambda_1y_1 \\ \lambda_2y_2 \\ \vdots \\ \lambda_ny_n\end{bmatrix}=\lambda_1y_1^2+\lambda_2y_2^2+\cdots+\lambda_ny_n^2$
> 由于 $\mathbf{v}\neq \mathbf{0}$，$P^T$ 是可逆矩阵，因此 $\mathbf{y}\neq\mathbf{0}$。
> $y_i$ 不全为 $0$，$\lambda_i>0$ $\implies$ $\mathbf{v}^TA\mathbf{v}>0$    ■
> 
> 注释：
> ①为什么 $P^T$ 是可逆矩阵：$P$ 是正交矩阵 $\implies$ $P^T$ 是正交矩阵 $\implies$ $P^T$ 的 columns 是 orthonormal 的 $\implies$ $P^T$ 的 columns 是 independent 的
> ②为什么由 $\mathbf{v}\neq \mathbf{0}$、$P^T$ 是可逆矩阵，可以推出 $\mathbf{y}\neq\mathbf{0}$：$P^T$ 是可逆矩阵 $\implies$ $P^T$ 是 one-to-one 的 $\implies$ $P^T\mathbf{0}=\mathbf{0}$，只有 $\mathbf{0}$ 会映射到 $\mathbf{0}$。而 $\mathbf{v}\neq \mathbf{0}$，所以映射到的一定不是 $\mathbf{0}$。

### Positive Semidefinite Matrix

> [!example] positive semidefinite
> ==实对称矩阵== $C$（$n\times n$），若对于任意 $\mathbf{v}\in\mathbb{R}^n$，都有
> $$\mathbf{v}^TC\mathbf{v}\ge 0$$
> 称 $C$ 是 **positive semidefinite** 的。

> [!important] Theorem
> 对于==实对称矩阵== $A$：
> $A$ 是 positive semidefinite 的 $\iff$ $A$ 的所有 eigenvalue 都 $\ge 0$

> 证明：
> **左推右**：任取 $A$ 的一个 eigenvalue $\lambda$，对应 eigenvector $\mathbf{v}$。只要证 $\lambda\ge 0$。
> 由 $A$ 半正定知 $\mathbf{v}^TA\mathbf{v}\ge 0$ $\implies$ $\mathbf{v}^T\lambda\mathbf{v}\ge 0$ $\implies$ $\lambda\|\mathbf{v}\|^2\ge 0$ $\implies$ $\lambda \ge 0$
> **右推左**：任取 $\mathbf{v}\in\mathbb{R}^n$，只要证 $\mathbf{v}^TA\mathbf{v}\ge 0$。
> $A$ 是实对称矩阵，一定可正交对角化：$A=PDP^T$（其中 $P$ 是正交矩阵，由 $A$ 的 eigenvector 构成；$D$ 是对角矩阵，由 $A$ 的 eigenvalue 构成）。
> 则 $\mathbf{v}^TA\mathbf{v}=\mathbf{v}^TPDP^T\mathbf{v}$
> 记 $\mathbf{y}=P^T\mathbf{v}$，则 $\mathbf{v}^TA\mathbf{v}=\mathbf{y}^TD\mathbf{y}=\mathbf{y}\cdot D\mathbf{y}=\begin{bmatrix}y_1 \\ y_2 \\ \vdots \\ y_n\end{bmatrix}\cdot \begin{bmatrix}\lambda_1y_1 \\ \lambda_2y_2 \\ \vdots \\ \lambda_ny_n\end{bmatrix}=\lambda_1y_1^2+\lambda_2y_2^2+\cdots+\lambda_ny_n^2$
> 由于 $\lambda_i\ge 0$，因此 $\mathbf{v}^TA\mathbf{v}\ge 0$。
