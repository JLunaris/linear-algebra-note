
|         矩阵分解         |  适用范围   |
| :------------------: | :-----: |
|  对角化（$A=PDP^{-1}$）   | 可对角化的方阵 |
|   正交对角化（$A=PDP^T$）   |  实对称矩阵  |
| SVD（$A=U\Sigma V^T$） |  任意矩阵   |

本节只讨论实矩阵的 SVD。实际上，复矩阵也可以做 SVD。总之，任何矩阵都可以做 SVD。

# Singular Value Decomposition

> [!important] Singular Value Decomposition（奇异值分解）
> $A$ 是一个 $m\times n$ 实矩阵，==$\text{rank}\ A=k$==。则可以将 $A$ 分解为以下形式：
> $$A=U\Sigma V^T$$
> 其中：
> - $U$ 是 $m\times m$ 正交矩阵
> - $\Sigma$ 是 $m\times n$ 实矩阵，$\Sigma = \left[ \begin{array}{cccc|ccc} \sigma_1 & 0 & \cdots & 0 & 0 & 0 & \cdots & 0 \\ 0 & \sigma_2 & \cdots & 0 & 0 & 0 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots & \vdots & \vdots & & \vdots \\ 0 & 0 & \cdots & \sigma_k & 0 & 0 & \cdots & 0 \\ \hline 0 & 0 & \cdots & 0 & 0 & 0 & \cdots & 0 \\ \vdots & \vdots & & \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 0 & 0 & 0 & \cdots & 0 \end{array} \right]$, 其中 $\sigma_1\ge \sigma_2\ge \cdots \ge \sigma_k > 0$
> - $V$ 是 $n\times n$ 正交矩阵

> $\Sigma$ 是一个广义的“对角矩阵”，它不一定是方形。只有“主对角线”元素可以非零（但也可能为 $0$），其余位置元素都是 $0$。

> 上述定理中：
> ① 为什么 $\Sigma$ 一定容纳得下 $k$ 个对角元素？
> ② 求 $U$、$\Sigma$、$V$ 的 rank。
> ③ 不使用 $U\Sigma V^T=A$ 这个条件，求证 $\text{rank}(U\Sigma V^T)=k$。
> 
> 解：
> ① 因为 $\Sigma$ 是 $m\times n$ 矩阵，而 $\text{rank}\ A\le m$，$\text{rank}\ A\le n$。（$\text{rank}\ A=k$）
> ② $U$ 和 $V$ 都是正交矩阵，因此 $U$ 和 $V$ 的 columns 都是 independent 的，因此 $\text{rank}\ U=m$，$\text{rank}\ V=n$。显然 $\text{rank}\ \Sigma=k$。
> ③ $U$ 和 $V$ 都是正交矩阵，因此 $U$ 和 $V$ 是可逆矩阵。由“矩阵相乘，rank 保持不变的充分条件”知，$\text{rank}(U\Sigma V^T)=\text{rank}(\Sigma)=k$。

> [!example] singular value
> 上述定理中，$\sigma_1,\sigma_2,\cdots,\sigma_k$ 称为 $A$ 的 **singular value**s。

> 证明：只要证下面的定理。因为下面的定理可以写为 
> ![[Pasted image 20260602130501.png]]
> 则 $AV=U\Sigma$，其中 $V$ 是 $n\times n$ 正交矩阵，$U$ 是 $m\times m$ 正交矩阵，$\Sigma$ 是 $m\times n$ 矩阵。
> 即 $A=U\Sigma V^T$。

> [!important] Theorem
> $A$ 是一个 $m\times n$ 实矩阵，$\text{rank}\ A=k$。则存在：
> 1. $\mathbb{R}^n$ 的 orthonormal basis $\mathcal{B}_1=\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_n\}$
> 2. $\mathbb{R}^m$ 的 orthonormal basis $\mathcal{B}_2=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_m\}$
> 3. 标量 $\sigma_1\ge \sigma_2\ge \cdots \ge \sigma_k > 0$
> 
> 使得 $A\mathbf{v}_i = \begin{cases} \sigma_i \mathbf{u}_i & \text{if } 1 \le i \le k \\ \mathbf{0} & \text{if } i > k \end{cases}$

> 证明：由**引理1**知 $A^TA$ 是 $n\times n$ 实对称矩阵，因此可做正交对角化：$A^TA=PDP^T$（其中 $P$ 是正交矩阵，由 $A^TA$ 的 eigenvector 构成；$D$ 是对角矩阵，由 $A^TA$ 的 eigenvalue 构成）
> 设 $P=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_n\end{bmatrix}$，$D=\text{diag}(\lambda_1,\lambda_2,\cdots,\lambda_n)$。
> 接下来把 $D$ 的对角元素 $\lambda_i$ 按从大到小排列，同时调整 $P$ 中的对应 $\mathbf{v}_i$。
> 最终得到 $P=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_n\end{bmatrix}$，$D=\text{diag}(\lambda_1,\lambda_2,\cdots,\lambda_n)$，其中 $\lambda_1\ge \lambda_2\ge \cdots \ge \lambda_n$。
> ★由于 $P$ 是正交矩阵，因此可以把 $P$ 的 columns 构成 $\mathcal{B}_1$。
> 由**引理2**知 $A^TA$ 是 positive semidefinite 的，因此它的 eigenvalue $\lambda_i$ 都 $\ge 0$）。
> 由**引理3**知 $A^TA$ 的 rank 为 $k$，故 nullity 为 $n-k$，故 $\text{Null}(A^TA)$ 的 dimension 为 $n-k$。
> 而 eigenvalue $0$ 对应的 eigenspace 正是 $\text{Null}(A^TA)$，因此该 eigenspace 有 $n-k$ 个 basis。
> 因此 $P$ 中有 $n-k$ 个 columns 对应的 eigenvalue 是 $0$。综上可知：
> ![[Pasted image 20260602190715.png|280]]
> ★令 $\sigma_i=\sqrt{\lambda_i}$（$i=1,2,\cdots,k$），可以满足定理要求 $\sigma_1\ge \sigma_2\ge \cdots \ge \sigma_k > 0$。
> 接下来，只需要构造 $\mathcal{B}_2$，需要满足 ①orthonormal set ②$1\le i \le k$ 时，$A\mathbf{v}_i=\sigma_i \mathbf{u}_i$。
> ★对于 $1\le i \le k$，令 $\mathbf{u}_i=\cfrac{A\mathbf{v}_i}{\sigma_i}$，这些 $\mathbf{u}_i$ 组成的向量集一定是 orthonormal 的（证明如下）
>     证明：只要证 $\mathbf{u}_i\cdot\mathbf{u}_j=0$ 且 $\|\mathbf{u}_i\|=1$。
>     $\mathbf{u}_i\cdot\mathbf{u}_j=\cfrac{A\mathbf{v}_i}{\sigma_j}\cdot\cfrac{A\mathbf{v}_j}{\sigma_i}=\cfrac{1}{\sigma_i\sigma_j}(A\mathbf{v}_i)^T A\mathbf{v}_j=\cfrac{1}{\sigma_i\sigma_j}\mathbf{v}_i^TA^TA\mathbf{v}_j$，而 $A^TA\mathbf{v}_j=\lambda_j\mathbf{v}_j$，故 $\mathbf{u}_i\cdot\mathbf{u}_j=\cfrac{1}{\sigma_i\sigma_j}\mathbf{v}_i^T\lambda_j\mathbf{v}_j=\cfrac{\lambda_j}{\sigma_i\sigma_j}\mathbf{v}_i\cdot\mathbf{v}_j=0$
>     证 $\|\mathbf{u}_i\|=1$ 只要证 $\mathbf{u}_i\cdot\mathbf{u}_i=1$，只要把上行等式的 $j$ 替换成 $i$，结果为 $\mathbf{u}_i\cdot\mathbf{u}_i=\cfrac{\lambda_i}{\sigma_i^2}\mathbf{v}_i\cdot\mathbf{v}_i=\cfrac{\lambda_i}{\sigma_i^2}\|\mathbf{v}_i\|^2=\cfrac{\lambda_i}{\sigma_i^2}$，而 $\sigma_i=\sqrt{\lambda_i}$，因此 $\mathbf{u}_i\cdot\mathbf{u}_i=1$。
> ★目前已经得到 orthonormal set $\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$。根据 Extension Theorem，可以找到向量 $\mathbf{u}_{k+1},\cdots,\mathbf{u}_m$ 加入原先集合构成 $\mathbb{R}^m$ 的 basis。保持 $\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$ 不变，只对新增向量依次做 Gram-Schmidt Process，可将该集合变为 orthonormal set。

> [!important] 引理
> $A$ 是一个 $m\times n$ 实矩阵，$\text{rank}\ A=k$。则：
> 1. $A^TA$ 是实对称矩阵
> 2. $A^TA$ 是 positive semidefinite 的
> 3. $\text{rank}(A^TA)=\text{rank}(A)$

> 证明：首先，显然 $A^TA$ 是 $n\times n$ 矩阵（方阵）。
> **命题1**：$(A^TA)^T=A^TA$
> **命题2**：$A^TA$ 是实对称矩阵。只要证 $\forall\mathbf{v}\in\mathbb{R}^n,\mathbf{v}^TA^TA\mathbf{v}\ge 0$。
> $\mathbf{v}^TA^TA\mathbf{v}=(A\mathbf{v})^TA\mathbf{v}=A\mathbf{v}\cdot A\mathbf{v}=\|A\mathbf{v}\|^2\ge 0$
> **命题3**：由于 $A^TA$ 和 $A$ 的列数都是 $n$，只要证 $\text{nullity}(A^TA)=\text{nullity}(A)$。
> 只要证 $\text{Null}(A^TA)=\text{Null}(A)$。（因为 null space 的 dimension 等于 nullity）
> 只要证 ① $\forall\mathbf{v}\in \text{Null}(A^TA),\mathbf{v}\in \text{Null}(A)$ 且 ② $\forall\mathbf{v}\in \text{Null}(A),\mathbf{v}\in \text{Null}(A^TA)$。
> 证明①：$A^TA\mathbf{v}=\mathbf{0}$ $\implies$ $\mathbf{v}^TA^TA\mathbf{v}=\mathbf{0}$ $\implies$ $\mathbf{v}^TA^TA\mathbf{v}=\|A\mathbf{v}\|^2=0$ $\implies$ $A\mathbf{v}=\mathbf{0}$
> 证明②：$A\mathbf{v}=\mathbf{0}$ $\implies$ $A^TA\mathbf{v}=\mathbf{0}$

上述定理和证明过程告诉我们，如何对任意实矩阵 $A$ 做 SVD：

> [!important] How to SVD a real matrix
> 给定任意 $m\times n$ 实矩阵 $A$：
> - 计算 $A^TA$，这是一个 $n\times n$ 实对称矩阵。
> - 对 $A^TA$ 做正交对角化：$A^TA=PDP^T$，其中 $P=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_n\end{bmatrix}$ 为正交矩阵，$D=\text{diag}(\lambda_1,\lambda_2,\cdots,\lambda_n)$，且 $\lambda_1\ge \lambda_2\ge \cdots \ge \lambda_n$。定义 ==$V=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_n\end{bmatrix}$==。
> - 将所有 $>0$ 的 $\lambda_1,\lambda_2,\cdots,\lambda_k$ 取出，定义 $\sigma_i=\sqrt{\lambda_i}$，定义 ==$\Sigma = \left[ \begin{array}{cccc|c} \sigma_1 & 0 & \cdots & 0 & \\ 0 & \sigma_2 & \cdots & 0 & \\ \vdots & \vdots & \ddots & \vdots & \mathbf{O} \\ 0 & 0 & \cdots & \sigma_k & \\ \hline & & \mathbf{O} & & \mathbf{O} \end{array} \right]_{m \times n}$==
> - 对于 $1\le i \le k$，定义 $\mathbf{u}_i=\cfrac{A\mathbf{v}_i}{\sigma_i}$，则 $\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$ 为 orthonormal set。根据 Extension Theorem，可以找到向量 $\mathbf{u}_{k+1},\cdots,\mathbf{u}_m$ 加入原先集合构成 $\mathbb{R}^m$ 的 basis。保持 $\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$ 不变，只对新增向量依次做 Gram-Schmidt Process，可将该集合变为 orthonormal set。定义 ==$U=\begin{bmatrix}\mathbf{u}_1 & \mathbf{u}_2 & \cdots & \mathbf{u}_m\end{bmatrix}$==。
> 
> 最终得到 $A=U\Sigma V^T$。

### Reduced SVD

在完整 SVD 中：
![[Pasted image 20260603121137.png|371]]

若 $\text{rank}(A)=k$，则 $\Sigma = \left[ \begin{array}{cccc|c} \sigma_1 & 0 & \cdots & 0 & \\ 0 & \sigma_2 & \cdots & 0 & \\ \vdots & \vdots & \ddots & \vdots & \mathbf{O} \\ 0 & 0 & \cdots & \sigma_k & \\ \hline & & \mathbf{O} & & \mathbf{O} \end{array} \right]_{m \times n}$

事实上，可以只保留 $\Sigma$ 的“左上部分”，只保留 $U$ 和 $V$ 的前 $k$ 列，如图所示：
![[Pasted image 20260603121636.png|387]]

即 $\Sigma_k = \begin{bmatrix} \sigma_1 & 0 & \cdots & 0 \\ 0 & \sigma_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & \sigma_k \end{bmatrix}$，$U_k=\begin{bmatrix}\mathbf{u}_1 & \mathbf{u}_2 & \cdots & \mathbf{u}_k\end{bmatrix}$，$V_k=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_k\end{bmatrix}$
则 $A=U_k \Sigma_k V_k^T$，这就是 Reduced SVD。

> 证明：已知 $A=U \Sigma V^T$，求证 $A=U_k \Sigma_k V_k^T$。
> 设 $\Sigma=\begin{bmatrix}\Sigma_k & O \\ O & O\end{bmatrix}$，$U=\begin{bmatrix} U_k & R \end{bmatrix}$，$V^T=\begin{bmatrix}V_k^T \\ D\end{bmatrix}$。
> 则 $A=U \Sigma V^T=\begin{bmatrix} U_k & R \end{bmatrix}\begin{bmatrix}\Sigma_k & O \\ O & O\end{bmatrix}\begin{bmatrix}V_k^T \\ D\end{bmatrix}=\begin{bmatrix} U_k\Sigma_k & O \end{bmatrix}\begin{bmatrix}V_k^T \\ D\end{bmatrix}=\begin{bmatrix}U_k\Sigma_kV_k^T\end{bmatrix}$。

> [!important] 对任意实矩阵 $A$ 做 Reduced SVD
> 给定任意 $m\times n$ 实矩阵 $A$：
> - 计算 $A^TA$，这是一个 $n\times n$ 实对称矩阵。
> - 对 $A^TA$ 做正交对角化：$A^TA=PDP^T$，其中 $P=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_n\end{bmatrix}$ 为正交矩阵，$D=\text{diag}(\lambda_1,\lambda_2,\cdots,\lambda_n)$，且 $\lambda_1\ge \lambda_2\ge \cdots \ge \lambda_n$。做正交对角化时，只需要保证 $>0$ 的 $\lambda_1,\lambda_2,\cdots,\lambda_k$ 对应的 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k$ 构成的集合是 orthonormal 的即可，定义 ==$V_k=\begin{bmatrix}\mathbf{v}_1 & \mathbf{v}_2 & \cdots & \mathbf{v}_k\end{bmatrix}$==，定义 $\sigma_i=\sqrt{\lambda_i}$，定义 ==$\Sigma_k = \text{diag}(\sigma_1,\sigma_2,\cdots,\sigma_k)$==。
>   
> - 对于 $1\le i \le k$，定义 $\mathbf{u}_i=\cfrac{A\mathbf{v}_i}{\sigma_i}$，定义 ==$U_k=\begin{bmatrix}\mathbf{u}_1 & \mathbf{u}_2 & \cdots & \mathbf{u}_k\end{bmatrix}$==。
> 
> 最终得到 $A=U_k\Sigma_k V_k^T$。

### Low Rank Approximation（Truncated SVD）

设 $A$ 的 reduced SVD 为 $A=U_k\Sigma_k V_k^T$。

如果把最后一个 singular value 删掉，变为 $\Sigma_{k-1}$，则 $A_{k-1}=U_{k-1}\Sigma_{k-1} V_{k-1}^T$。如图所示：

![[Pasted image 20260603152415.png|414]]

由于 $\text{rank}\ U_{k-1}=k-1$，$\text{rank}\ V_{k-1}^T=\text{rank}\ V_{k-1}=k-1$，由“矩阵相乘，rank 保持不变的充分条件”知，$\text{rank}\ A_{k-1}=\text{rank}\ \Sigma_{k-1}=k-1$。

虽然 $A\neq A_{k-1}$，但是 $A_{k-1}$​ 是所有 rank $\le k-1$ 的矩阵中最接近 $A$ 的矩阵，即使得 $\|A-A'\|_F$ 最小的 $A'$。

> 矩阵 $A$ 的 **frobenius norm** 记作 $\|A\|_F$，含义为：把矩阵扁平化为一个向量，然后计算这个向量的 2-norm。

> [!important] Truncated SVD
> 对任意 $m\times n$ 实矩阵 $A$ 做 reduced SVD：$$A=U_k\Sigma_k V_k^T$$
> 只保留前 $r$（$r<k$）个 singular value，得到 $$A_{r}=U_{r}\Sigma_{r} V_{r}^T$$ 
> 则 $A_r$ 的 rank 为 $r$，且 $A_r$ 是所有 rank $\le r$ 的矩阵中最接近 $A$ 的矩阵。

> 证明：略。
