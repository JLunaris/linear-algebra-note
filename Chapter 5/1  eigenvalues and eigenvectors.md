
# Eigenvalues and Eigenvectors

> [!example] 方阵的 eigenvalue & eigenvector
> 对于矩阵 $A$，若存在==非零向量 $\mathbf{v}$==、==标量 $\lambda$==，满足：$$A\mathbf{v}=\lambda \mathbf{v}$$则称 $\mathbf{v}$ 是 $A$ 的 **eigenvector**，$\lambda$ 是 $A$ 的 **eigenvalue**。
> 并称 $\lambda$ 是 $\mathbf{v}$ 对应的 eigenvalue，$\mathbf{v}$ 是 $\lambda$ 对应的 eigenvector。

> 有关上述定义的说明：
> 1. $A$ 一定是==方阵==（若不是方阵，则输入和输出向量的维度不相等，$A\mathbf{v}= \lambda \mathbf{v}$ 不可能成立）。
> 2. $\mathbf{0}$ 不是 eigenvector，尽管 $\mathbf{0}$ 也满足 $A\mathbf{v}= \lambda \mathbf{v}$。

> 案例：
> ![[Pasted image 20260505153850.png|397]]

> [!important] Theorem
> 对于方阵 $A$：
> - 一个 eigenvector 对应==唯一一个== eigenvalue
> - 一个 eigenvalue 对应==无穷多个== eigenvector

> 证明：
> **命题1**：假设某 eigenvector $\mathbf{v}$ 对应两个 eigenvalue $\lambda_1,\lambda_2$，则 $A\mathbf{v}=\lambda_1\mathbf{v}$，$A\mathbf{v}=\lambda_2\mathbf{v}$
> 两式相减得 $\mathbf{0}=(\lambda_1-\lambda_2)\mathbf{v}$，由于 $\mathbf{v}\neq \mathbf{0}$，因此 $\lambda_1-\lambda_2=0$，即 $\lambda_1=\lambda_2$
> **命题2**（证法1）：设 $\lambda$ 是 $A$ 的一个 eigenvalue。根据定义，方程 $A\mathbf{v}=\lambda\mathbf{v}$ 一定有非 $\mathbf{0}$ 解。
> $A\mathbf{v}=\lambda\mathbf{v}$ $\iff$ $A\mathbf{v}-\lambda\mathbf{v}=\mathbf{0}$ $\iff$ $(A-\lambda I_n)\mathbf{v}=\mathbf{0}$。这是一个 homogeneous 的线性方程组，因此必有 $\mathbf{v}=\mathbf{0}$ 作为它的一个解。又因为它还有非 $\mathbf{0}$ 解，因此有无穷多解。
> **命题2**（证法2）：设 eigenvalue $\lambda$ 对应的 eigenvector 是 $\mathbf{v}$，则 $A\mathbf{v}=\lambda\mathbf{v}$
> 对任意非零标量 $c$，有 $A(c\mathbf{v})=c(\lambda\mathbf{v})=\lambda(c\mathbf{v})$，因此 $c\mathbf{v}$ 也是 $\lambda$ 对应的 eigenvector。

> [!example] 等价定义
> 对于线性变换 $T$，若存在==非零向量 $\mathbf{v}$==、==标量 $\lambda$==，满足：$$T(\mathbf{v})=\lambda \mathbf{v}$$则称 $\mathbf{v}$ 是 $T$ 的 **eigenvector**，$\lambda$ 是 $T$ 的 **eigenvalue**。

> 几何含义：经过线性变换 $T$ 后仍与原向量共线的非零向量，就是 eigenvector。

### 案例

> 【例1】shear transformation
> - 对于图像中的每一个像素点（向量），做线性变换 $T\left(\begin{bmatrix}x \\ y\end{bmatrix}\right)=\begin{bmatrix}x+0.27y \\ y\end{bmatrix}$。
> - 含义：$y$ 坐标不变，只改变 $x$ 坐标。$x$ 坐标的改变量与 $y$ 有关，$y$ 越大，$x$ 坐标偏移量越大。
> - 蓝色轴上的任意非零向量（即 $y=0$ 的非零向量），变换前=变换后，因此这些向量是 eigenvector，对应的 eigenvalue 是 $1$。
> ![[Pasted image 20260505163205.png|451]]
> 
> 【例2】reflection
> - 关于直线 $\mathcal{L}:y=\cfrac{1}{2}x$ 的反射变换 $T$ 是一个线性变换。
> - $T(\mathbf{b}_1)=\mathbf{b}_1$，因此 $\mathbf{b}_1$ 是 eigenvector，对应的 eigenvalue 是 $1$。
> - $T(\mathbf{b}_2)=-\mathbf{b}_2$，因此 $\mathbf{b}_2$ 是 eigenvector，对应的 eigenvalue 是 $-1$。
> ![[Pasted image 20260505164017.png|292]]
> 
> 【例3】放大与缩小
> - 对于图像中的每一个像素点（向量），以某点为原点，做线性变换 $T_1$（放大） 或 $T_2$（缩小）。
> - 含义：以 $T_1$ 为例，$\begin{bmatrix}2 & 0 \\ 0 & 2\end{bmatrix}\begin{bmatrix}x \\ y\end{bmatrix}=\begin{bmatrix}2x \\ 2y\end{bmatrix}=2\begin{bmatrix}x \\ y\end{bmatrix}$，即所有向量都伸长为原来的 2 倍，方向不变。
> - 所有向量（除了 $\mathbf{0}$）都是 eigenvector，$T_1$ 中对应的 eigenvalue 是 $2$，$T_2$ 中对应的 eigenvalue 是 $0.5$。
> ![[Pasted image 20260505165645.png|528]]
> 
> 【例4】rotation
> - 该变换中，所有向量都会改变方向，因此不存在 eigenvector 和 eigenvalue。
> ![[Pasted image 20260505171327.png|478]]

### Eigenspace

> [!question] 一个 eigenvalue 对应的所有 eigenvector 是否构成 subspace？
> 方阵 $A$ 的一个 eigenvalue 是 $\lambda$，问 $\lambda$ 对应的所有 eigenvector 是否构成 subspace？

> 分析：$\lambda$ 对应的所有 eigenvector 构成的集合 $S=\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v} \text{ 且 } \mathbf{v}\neq\mathbf{0}\}$
> subspace 必须有 $\mathbf{0}$，而 eigenvector 不能是 $\mathbf{0}$，因此 $S$ 不是 subspace。
> 但如果把 $\mathbf{0}$ 加入 $S$ 构成 $S'=\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v}\}$，则 $S'$ 是 subspace（根据定义很容易证明）。
> 事实上，$S'$ 正是 $\lambda$ 对应的 eigenspace。

> [!example] 方阵的 eigenspace
> 方阵 $A$ 的一个 eigenvalue 是 $\lambda$，集合 $\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v} \}$ 称为 $A$ 的 **eigenspace**，并称它是 $\lambda$ 对应的 eigenspace。

> 一个 eigenvalue 对应一个 eigenspace。

> [!important] Theorem
> 方阵的 eigenspace 是 subspace。
> 具体来讲，方阵 $A$ 的一个 eigenvalue $\lambda$ 对应的 eigenspace 为 $\text{Null}(A-\lambda I_n)$。

> 证明：方阵 $A$ 的一个 eigenvalue 是 $\lambda$，则 $\lambda$ 对应的 eigenspace 为 $S=\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v}\}$
> $A\mathbf{v}=\lambda\mathbf{v}$ $\iff$ $A\mathbf{v}-\lambda\mathbf{v}=\mathbf{0}$ $\iff$ $A\mathbf{v}-\lambda I_n \mathbf{v}=\mathbf{0}$ $\iff$ $(A-\lambda I_n) \mathbf{v}=\mathbf{0}$
> 因此 $S=\text{Null}(A-\lambda I_n)$。而 null space 是 subspace，因此 $S$ 是 subspace。

> [!important] Theorem
> $\lambda$ 对应的 eigenspace = $\{$$\lambda$ 对应的所有 eigenvector$\}$ + $\{\mathbf{0}\}$

> 证明：
> - $\lambda$ 对应的所有 eigenvector 构成的集合 = $\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v} \text{ 且 } \mathbf{v}\neq\mathbf{0}\}$
> - $\lambda$ 对应的 eigenspace = $\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v} \}$

---

> 案例：检查一个数字是否是 eigenvalue
> 
> 【例1】线性变换 $T\left( \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} \right) = \begin{bmatrix} -2x_2 \\ -3x_1 + x_2 \end{bmatrix}$，检查 $3$ 是否是 $T$ 的 eigenvalue。
> 
> 解：$T$ 对应的矩阵 $A=\begin{bmatrix}0 & -2 \\ -3 & 1\end{bmatrix}$，只需验证方程 $A\mathbf{v}=3\mathbf{v}$ 是否有非 $\mathbf{0}$ 解。
> 原方程 $\iff$ $(A-3I_2)\mathbf{v}=\mathbf{0}$。
> $A-3I_2=\begin{bmatrix}-3 & -2 \\ -3 & -2\end{bmatrix}$，该矩阵 dependent，又因为方程一定有解（$\mathbf{0}$），故方程有无穷多解，故方程必有非 $\mathbf{0}$ 解。因此 $3$ 是 $T$ 的 eigenvalue。
> 
> 【例2】$B = \begin{bmatrix} 3 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 2 & 1 \end{bmatrix}$，检查 $3$ 是否是 $B$ 的 eigenvalue；如果是，求它对应的 eigenspace 的一个 basis。
> 
> 解：①验证方程 $B\mathbf{v}=3\mathbf{v}$ 是否有非 $\mathbf{0}$ 解。原方程 $\iff$ $(B-3I_3)\mathbf{v}=\mathbf{0}$。
> $B-3I_3=\begin{bmatrix} 0 & 0 & 0 \\ 0 & -2 & 2 \\ 0 & 2 & -2 \end{bmatrix}$，该矩阵 dependent，又因为方程一定有解（$\mathbf{0}$），故方程有无穷多解，故方程必有非 $\mathbf{0}$ 解。因此 $3$ 是 $B$ 的 eigenvalue。
> ②求解方程组，解得 $\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = \begin{bmatrix} x_1 \\ x_3 \\ x_3 \end{bmatrix} = x_1 \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + x_3 \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}$，由于 eigenspace 是 null space，因此 $\left\{ \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix} \right\}$ 是该 eigenspace 的一个 basis。

### Finding All Eigenvalues

> [!important] Theorem
> 标量 $t$ 是方阵 $A$ 的 eigenvalue $\iff$ $\text{det}(A-tI_n)=0$

> 证明：标量 $t$ 是方阵 $A$ 的 eigenvalue
> $\iff$ 方程 $A\mathbf{v}=t\mathbf{v}$ 有非 $\mathbf{0}$ 解
> $\iff$ 方程 $(A-tI_n)\mathbf{v}=\mathbf{0}$ 有非 $\mathbf{0}$ 解
> $\iff$ 方程 $(A-tI_n)\mathbf{v}=\mathbf{0}$ 有无穷多解
> $\iff$ 矩阵 $A-tI_n$ 的 columns 是 dependent 的
> $\iff$ 矩阵 $A-tI_n$ 不可逆
> $\iff$ $\text{det}(A-tI_n)=0$

> 案例：求方阵的所有 eigenvalue
> 
> 【例1】求 $A=\begin{bmatrix}-4 & -3 \\ 3 & 6\end{bmatrix}$ 的所有 eigenvalue。
> 
> 解：特征方程为 $\text{det}(A-tI_2)=0$
> $A-tI_2=\begin{bmatrix}-4-t & -3 \\ 3 & 6-t\end{bmatrix}$，$\text{det}(A-tI_2)=(-4-t)(6-t)-(-3)\cdot 3=(t+3)(t-5)=0$，解得 $t=-3$ 或 $5$。因此 $A$ 的所有 eigenvalue 是 $-3$ 或 $5$。
> 
> 【例2】求二维平面上以原点为中心逆时针旋转 $90^\circ$ 的线性变换 $T$ 对应的矩阵，并求它的所有 eigenvalue。
> 
> 解：$T(\mathbf{e}_1)=\begin{bmatrix}0 \\ 1\end{bmatrix}$，$T(\mathbf{e}_2)=\begin{bmatrix}-1 \\ 0\end{bmatrix}$。故 $T$ 对应的矩阵 $A=\begin{bmatrix}0 & -1 \\ 1 & 0\end{bmatrix}$。
> 特征方程为 $\text{det}(A-tI_2)=0$。
> $A-tI_2=\begin{bmatrix}-t & -1 \\ 1 & -t\end{bmatrix}$，$\text{det}(A-tI_2)=t^2+1=0$，方程无实根，因此没有实数的 eigenvalue。
> （但有复数的 eigenvalue $i$）

### Characteristic Polynomial

> [!example] 方阵的 characteristic equation 和 characteristic polynomial
> - 方程 ==$\text{det}(A-tI_n)=0$== 称为 $A$ 的 **characteristic equation**（特征方程）
> - ==$\text{det}(A-tI_n)$== 称为 $A$ 的 **characteristic polynomial**（特征多项式）

























