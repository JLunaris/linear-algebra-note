
# Eigenvalues and Eigenvectors

> [!example] 方阵的 eigenvalue & eigenvector
> 对于矩阵 $A$，若存在==非零向量 $\mathbf{v}$==、==标量 $\lambda$==，满足：$$A\mathbf{v}=\lambda \mathbf{v}$$则称 $\mathbf{v}$ 是 $A$ 的 **eigenvector**，$\lambda$ 是 $A$ 的 **eigenvalue**。
> 并称 $\lambda$ 是 $\mathbf{v}$ 对应的 eigenvalue，$\mathbf{v}$ 是 $\lambda$ 对应的 eigenvector。

> 有关上述定义的说明：
> 1. $A$ 一定是==方阵==（若不是方阵，则输入和输出向量的维度不相等，$A\mathbf{v}= \lambda \mathbf{v}$ 不可能成立）。
> 2. $\mathbf{0}$ 不是 eigenvector，尽管 $\mathbf{0}$ 也满足 $A\mathbf{v}= \lambda \mathbf{v}$。
> 3. eigenvalue 有可能为 $0$。

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

> 注意：一个 eigenvalue 对应的 eigenvector 不一定都在一条直线上。
> 例如，对于方阵 $A = \begin{bmatrix} -1 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 2 & 1 \end{bmatrix}$ 有：$\begin{bmatrix} -1 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 2 & 1 \end{bmatrix} \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} = \begin{bmatrix} -1 \\ 0 \\ 0 \end{bmatrix}$，$\begin{bmatrix} -1 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 2 & 1 \end{bmatrix} \begin{bmatrix} 0 \\ 1 \\ -1 \end{bmatrix} = \begin{bmatrix} 0 \\ -1 \\ 1 \end{bmatrix}$.
> 可知它的一个 eigenvalue 为 $-1$，对应的这两个 eigenvector 并不在一条直线上。

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
> $\lambda$ 对应的 eigenspace = $\{$$\lambda$ 对应的所有 eigenvector$\}$ + $\{\mathbf{0}\}$

> 证明：
> - $\lambda$ 对应的所有 eigenvector 构成的集合 = $\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v} \text{ 且 } \mathbf{v}\neq\mathbf{0}\}$
> - $\lambda$ 对应的 eigenspace = $\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v} \}$

> [!important] Theorem
> 方阵的 eigenspace 是 subspace。
> 具体而言，方阵 $A$ 的一个 eigenvalue $\lambda$ 对应的 eigenspace 为 ==$\text{Null}(A-\lambda I_n)$==。

> **求 eigenspace 的 basis**：
> 因为 eigenspace 是 nullspace，因此 $(A-\lambda I_n) \mathbf{v}=\mathbf{0}$ 通解的 parametric representation 中，每个与 free variable 相乘的向量，就是其 basis。

> 证明：方阵 $A$ 的一个 eigenvalue 是 $\lambda$，则 $\lambda$ 对应的 eigenspace 为 $S=\{\mathbf{v}\mid A\mathbf{v}=\lambda\mathbf{v}\}$
> $A\mathbf{v}=\lambda\mathbf{v}$ $\iff$ $A\mathbf{v}-\lambda\mathbf{v}=\mathbf{0}$ $\iff$ $A\mathbf{v}-\lambda I_n \mathbf{v}=\mathbf{0}$ $\iff$ $(A-\lambda I_n) \mathbf{v}=\mathbf{0}$
> 因此 $S=\text{Null}(A-\lambda I_n)$。而 null space 是 subspace，因此 $S$ 是 subspace。

> 案例：检查一个数字是否是 eigenvalue
> 
> 【例】$B = \begin{bmatrix} 3 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 2 & 1 \end{bmatrix}$，检查 $3$ 是否是 $B$ 的 eigenvalue。
> 
> 解：只需验证方程 $B\mathbf{v}=3\mathbf{v}$ 是否有非 $\mathbf{0}$ 解。原方程 $\iff$ $(B-3I_3)\mathbf{v}=\mathbf{0}$。
> $B-3I_3=\begin{bmatrix} 0 & 0 & 0 \\ 0 & -2 & 2 \\ 0 & 2 & -2 \end{bmatrix}$，该矩阵 dependent，又因为方程一定有解（$\mathbf{0}$），故方程有无穷多解，故方程必有非 $\mathbf{0}$ 解。因此 $3$ 是 $B$ 的 eigenvalue。

> 案例：求 eigenvalue 对应的 eigenspace 的一个 basis
> 
> 【例】已知 $B = \begin{bmatrix} 3 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 2 & 1 \end{bmatrix}$ 的一个 eigenvalue 是 $3$，求 $3$ 对应的 eigenspace 的一个 basis。
> 
> 解：$B\mathbf{v}=3\mathbf{v}$ $\iff$ $(B-3I_3)\mathbf{v}=\mathbf{0}$
> 求解该线性方程组，解得 $\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = \begin{bmatrix} x_1 \\ x_3 \\ x_3 \end{bmatrix} = x_1 \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + x_3 \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}$，由于 **eigenspace 是 null space**，因此 $\left\{ \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix} \right\}$ 是该 eigenspace 的一个 basis。

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

> [!NOTE] Summary
> 方阵 $A$ 的所有 eigenvalue，是 $A$ 的 characteristic equation 的所有解，也就是 $A$ 的 characteristic polynomial 的所有根。

### Characteristic Polynomial

> [!example] 方阵的 characteristic equation 和 characteristic polynomial
> - 方程 ==$\text{det}(A-tI_n)=0$== 称为 $A$ 的 **characteristic equation**（特征方程）
> - ==$\text{det}(A-tI_n)$== 称为 $A$ 的 **characteristic polynomial**（特征多项式）

> [!NOTE] 
> 矩阵与其 RREF 的 characteristic polynomial 通常是不同的，因此 eigenvalue 通常也不同。因此，**无法通过对矩阵做 elementary row operation 来寻找其 eigenvalue**。

> 证明：举一个反例即可
> 关于 $x$ 轴的反射变换，对应的矩阵是 $A=\begin{bmatrix}1 & 0 \\ 0 & -1\end{bmatrix}$，它具有两个 eigenvalue（$1$ 和 $-1$）
> 而 $A$ 的 RREF $R=\begin{bmatrix}1 & 0 \\ 0 & 1\end{bmatrix}$，它只有一个 eigenvalue（$1$）
> eigenvalue 不同 $\implies$ characteristic polynomial 不同

##### 相似矩阵具有相同的 characteristic polynomial，因而具有相同的 eigenvalue

> [!important] Theorem
> 相似矩阵具有相同的 characteristic polynomial，因而具有相同的 eigenvalue。

> 证明：设方阵 $A$ 和 $B$ 是相似的，则存在可逆矩阵 $P$ 使得 $B=P^{-1}AP$。
> 只要证 $\text{det}(A-tI_n)=\text{det}(B-tI_n)$。
> 
> $\begin{aligned} \det (B - tI_n) &= \det (P^{-1}AP - tP^{-1}P)  \\ &= \det (P^{-1}(AP - tP)) \\ &= \det (P^{-1}(A - tI_n)P) \\ &= \det(P^{-1}) \det(A-tI_n) \det(P) \\ &= \det(P^{-1}) \det(P) \det(A-tI_n) \\ &= \det (A - tI_n) \end{aligned}$

> [!NOTE] 深层含义
> $A$ 和 $B$ 相似，意味着 $A$ 和 $B$ 是同一个线性变换，在不同 coordinate system 下看到的结果。而 eigenvalue 描述的是线性变换本身的内在性质，不依赖于具体的 coordinate system。因此，相似矩阵具有相同的 eigenvalue。

##### n 阶方阵的 characteristic polynomial 的 degree 为 n

> [!important] Theorem
> $n$ 阶方阵的 characteristic polynomial 是一个 ==$n$ 次多项式==。

> 证明提示：$n$ 阶方阵 $A$ 的特征多项式 $\det(A-tI_n)=\det\begin{bmatrix}a_{11}-t & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22}-t & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{n1} & a_{n2} & \cdots & a_{nn}-t\end{bmatrix}$。
> 只有对角线元素带有 $t$，能为多项式贡献“次数”。

> [!important] Theorem
> $n$ 阶方阵最多有 $n$ 个 eigenvalue。

> 原因：$n$ 阶方阵的 characteristic polynomial 是一个 $n$ 次多项式，根据**代数基本定理**，$n$ 次多项式在 $\mathbb{C}$ 上恰有 $n$ 个根（计入重数）。这 $n$ 个根中可能有重根，因此最多有 $n$ 个不同的根，导致最多有 $n$ 个 eigenvalue。若只在 $\mathbb{R}$ 上讨论，根可能会更少。
> 总结：导致 eigenvalue 个数可能小于 $n$ 的原因：①重根 ②非实数根

##### eigenvalue 的 multiplicity

> [!quote] $n$ 次多项式的因式分解
> 在复数域 $\mathbb{C}$ 上，任意 $n$ 次多项式：
> $$p(x) = a_n x^n + a_{n-1} x^{n-1} + \dots + a_1 x + a_0 \quad (a_n \neq 0)$$
> 都可以被因式分解为如下形式：
> $$p(x) = a_n(x - x_1)(x - x_2)(x - x_3)\dots(x - x_n)$$
> 其中，$x_1,x_2,\cdots,x_n$ 是多项式的根（可能有重根）。

$n$ 阶方阵的特征多项式是 $n$ 次多项式，结合上述定理可以推出以下结论：

> [!example] eigenvalue 的 multiplicity
> 对 $n$ 阶方阵 $A$ 的特征多项式 $\det(A-tI_n)$ 做因式分解，一定可以分解为以下形式：
> $$c(t-\lambda_1)^{m_1}(t-\lambda_2)^{m_2}\cdots(t-\lambda_k)^{m_k}$$
> 其中，$c$ 为常数，$\lambda_1,\lambda_2,\cdots,\lambda_k$ 为==不同的== eigenvalues（$k\le n$），$m_1,m_2,\cdots,m_k$ 是正整数，且 ==$m_1+m_2+\cdots+m_k=n$==。
> 
> 对于每个因子 $(t-\lambda_i)^{m_i}$，$m_i$ 称为 $\lambda_i$ 的 **multiplicity**（重数）。

> 示例：$\det(M - tI_{10}) = (t - 5)^2(t + 6)(t - 7)^3(t - 8)^4$，则 $M$ 的 eigenvalues 为：$5$，multiplicity 为 $2$；$-6$，multiplicity 为 $1$；$7$，multiplicity 为 $3$；$8$，multiplicity 为 $4$。

> [!important] Theorem
> 对于方阵 $A$ 的一个 eigenvalue $\lambda$：
> $\lambda$ 对应的 eigenspace 的 dimension ==≤== $\lambda$ 的 multiplicity。

> 证明：略。

> [!NOTE] Summary
> ![[Pasted image 20260508171023.png|500]]

### 上三角矩阵 / 下三角矩阵 / 对角矩阵的 eigenvalues 是其对角元素

> [!important] Theorem
> 上三角矩阵 / 下三角矩阵 / 对角矩阵的 eigenvalues 是其对角元素。

> 证明：以上三角矩阵 $U = \begin{bmatrix}u_{11} & u_{12} & \cdots & u_{1n} \\0 & u_{22} & \cdots & u_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & u_{nn}\end{bmatrix}$ 为例：
> 特征多项式 $\det(U-tI_n)=\det\begin{bmatrix}u_{11}-t & u_{12} & \cdots & u_{1n} \\0 & u_{22}-t & \cdots & u_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & u_{nn}-t\end{bmatrix}=(u_{11}-t)(u_{22}-t)\cdots(u_{nn}-t)$
> 显然它的根分别是 $u_{11},u_{22},\cdots,u_{nn}$ .

# Diagonalization

> [!example] diagonalizable（可对角化的）
> 若方阵 $A$ ==相似于一个对角矩阵==，则称 $A$ 是**可对角化的**。
> 即存在可逆矩阵 $P$、对角矩阵 $D$ 使得 $A=PDP^{-1}$。

> [!NOTE] 
> 不是所有的方阵都是可对角化的。

> 反例：
> 考虑矩阵 $A=\begin{bmatrix}0 & 1 \\ 0 & 0\end{bmatrix}$，假设它是可对角化的，则 $A=PDP^{-1}$，其中 $P$ 是可逆阵，$D$ 是对角阵。
> 则 $A^2=PDP^{-1}PDP^{-1}=PD^2P^{-1}$，而 $A^2=\begin{bmatrix}0 & 1 \\ 0 & 0\end{bmatrix}\begin{bmatrix}0 & 1 \\ 0 & 0\end{bmatrix}=O$，综上 $PD^2P^{-1}=O$。
> 等式两边左乘 $P^{-1}$，右乘 $P$，得 $D^2=O$。
> 由于 $D$ 是对角矩阵，结合对角矩阵相乘的性质知 $D=O$。
> 则 $A=PDP^{-1}=O$，与 $A=\begin{bmatrix}0 & 1 \\ 0 & 0\end{bmatrix}$ 矛盾！

### 可对角化 ⟺ 能够找到 n 个 independent 的 eigenvector

> [!important] Theorem
> 对于 $n$ 阶方阵 $A$：
> $A$ 是可对角化的 $\iff$ $A$ 能够找到 $n$ 个 independent 的 eigenvector

> 证明：
> $n$ 阶方阵 $A$ 是可对角化的 $\iff$ $A=PDP^{-1}$（$P$ 是可逆矩阵，$D$ 是对角矩阵） $\iff$ $AP=PD$
> 设 $P=\begin{bmatrix}\mathbf{p}_1 & \mathbf{p}_2 & \cdots & \mathbf{p}_n \end{bmatrix}$，$D=\begin{bmatrix}d_1 & 0 & \cdots & 0 \\ 0 & d_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & d_n\end{bmatrix}$
> 则方程可以写为 $\begin{bmatrix}A\mathbf{p}_1 & A\mathbf{p}_2 & \cdots & A\mathbf{p}_n \end{bmatrix}=\begin{bmatrix}d_1\mathbf{p}_1 & d_2\mathbf{p}_2 & \cdots & d_n\mathbf{p}_n\end{bmatrix}$
> $\iff$ $A\mathbf{p}_i=d_i\mathbf{p}_i$（$i=1,2,\cdots,n$）
> $\iff$ $\mathbf{p}_i$ 是 $A$ 的 eigenvector，对应的 eigenvalue 是 $d_i$（$i=1,2,\cdots,n$）
> 由于 $P$ 是可逆阵，因此
> $\iff$ $A$ 能够找到 $n$ 个 independent 的 eigenvector，构成 $P$，它们对应的 eigenvalue 构成 $D$

上述定理和证明过程告诉我们，如何对角化一个可对角化的矩阵 $A$：

> [!important] How to diagonalize a diagonalizable matrix
> 将 $A$ 的 $n$ 个 independent 的 eigenvector 按列组成可逆矩阵$$P=\begin{bmatrix}\mathbf{p}_1 & \mathbf{p}_2 & \cdots & \mathbf{p}_n \end{bmatrix}$$
> 将这些 eigenvector 对应的 eigenvalue 按相同顺序放到对角线上组成对角矩阵
> $$D=\begin{bmatrix}d_1 & 0 & \cdots & 0 \\ 0 & d_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & d_n\end{bmatrix}$$
> 则
> $$A=PDP^{-1}$$

接下来的目标是，能否找到、如何找到 $n$ 个 independent 的 eigenvector。

### 相关引理

##### 不同的 eigenvalue 对应的 eigenvector 是 independent 的

> [!important] Theorem
> 对于一个方阵：从所有的 eigenspace 中分别任取一个 eigenvector，组成的向量组是 independent 的。
> 
> ![[Pasted image 20260509145537.png|422]]

> **证明**：对于 $n$ 阶方阵 $A$，设 $\lambda_1,\lambda_2,\cdots,\lambda_k$ 是 $A$ 的互不相同的 eigenvalues，从它们对应的 eigenspace 中分别任取一个 eigenvector $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k$ 。下面证明 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k$ 是 independent 的。
> 使用数学归纳法。当 $k=1$ 时，$\mathbf{v}_1$ 显然 independent。假设 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{k-1}$ 是 independent 的，只要证 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k$ 是 independent 的。
> 只要证方程 $c_1\mathbf{v}_1+c_2\mathbf{v}_2+\cdots+c_k\mathbf{v}_k=\mathbf{0}$（......①）的唯一解是 $c_1=c_2=\cdots=c_k=0$
> 原方程 $\iff$ $c_1A\mathbf{v}_1+c_2A\mathbf{v}_2+\cdots+c_kA\mathbf{v}_k=A\mathbf{0}=\mathbf{0}$
> $\iff$ $c_1\lambda_1\mathbf{v}_1+c_2\lambda_2\mathbf{v}_2+\cdots+c_k\lambda_k\mathbf{v}_k=\mathbf{0}$（......②）
> ②-$\lambda_k$① 得 $c_1(\lambda_1-\lambda_k)\mathbf{v}_1+c_2(\lambda_2-\lambda_k)\mathbf{v}_2+\cdots+c_{k-1}(\lambda_{k-1}-\lambda_k)\mathbf{v}_{k-1}=\mathbf{0}$
> 由于 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{k-1}$ independent，故 $c_1(\lambda_1-\lambda_k)=c_2(\lambda_2-\lambda_k)=\cdots=c_{k-1}(\lambda_{k-1}-\lambda_k)=0$
> 由于 $\lambda_1,\lambda_2,\cdots,\lambda_k$ 互不相等，则只能 $c_1=c_2=\cdots=c_{k-1}=0$
> 带回 ① 得 $c_k\mathbf{v}_k=\mathbf{0}$，由于 $\mathbf{v}_k\neq \mathbf{0}$，故 $c_k=0$
> 综上 $c_1=c_2=\cdots=c_k=0$   ■

> [!important] 推论
> 对于一个方阵：不同的 eigenvalue 对应的 eigenvector 一定 independent。

> [!important] 推论
> 对于一个方阵：不同的 eigenspace，除了 $\mathbf{0}$ 外，不可能有重复的 eigenvector。

> [!important] 推论
> 若 $n$ 阶方阵 $A$ 有 $n$ 个 eigenvalue，则 $A$ 是可对角化的。

##### 所有 eigenspace 的 bases 组成的向量集是 independent 的，并且是最大的 independent eigenvector  set

> [!important] Theorem
> 对于一个方阵：所有 eigenspace 的 bases 组成的向量集是 independent 的，并且是最大的 independent eigenvector  set。
> 
> ![[Pasted image 20260509173925.png|486]]

> 证明思路：
> **命题1**（independent）：
> ①每个 eigenspace 内部 bases 一定 independent
> ②不同 eigenspace 中各自取一个 eigenvector，这些向量 independent
> 结合①②可以证明，这些 bases 组成的向量集一定 independent。
> **命题2**（最大的）：
> 设第 $i$ 个 eigenspace 的 dimension 为 $d_i$（$i=1,2,\cdots,k$），则每个 eigenspace 内最多可以找到 $d_i$ 个 independent 向量。把每个 eigenspace 的 bases（个数为 $d_i$）全部组织起来，得到的就是最大的 independent eigenvector set。因为若再向该向量集中加入新的 eigenvector，则它必然属于某个 eigenspace，意味着该 eigenspace 中选择了超过 $d_i$ 个向量，则这些向量必然 dependent。

### 可对角化 ⟺ 对于每一个 eigenvalue，其对应的 eigenspace 的 dimension = 其 multiplicity

> [!important] Theorem
> 对于 $n$ 阶方阵 $A$：
> $A$ 是可对角化的 $\iff$ 对于 $A$ 的每一个 eigenvalue，其对应的 eigenspace 的 dimension ==＝== 其 multiplicity

> **求 eigenspace 的 dimension**：
> eigenvalue $\lambda$ 对应的 eigenspace 为 $\text{Null}(A-\lambda I_n)$，其 dimension 为 $\text{Nullity}(A-\lambda I_n)$。因此将 $A-\lambda I_n$ 化为 RREF 即可看出 dimension，不需要继续求解得到 basis 才确定 dimension。

> 证明：
> ![[Pasted image 20260511154600.png|416]]
> 所有 eigenspace 的 bases 组成的向量集是最大的 independent eigenvector  set，因此：
> $d_1+d_2+\cdots+d_k\ge n$ $\implies$ 能够找到 $n$ 个 independent 的 eigenvector $\implies$ $A$ 是可对角化的
> 而之前讲到，$d_1\le m_1,d_2\le m_2,\cdots,d_k\le m_k$，故 $d_1+d_2+\cdots+d_k\le m_1+m_2+\cdots+m_k=n$
> 因此，当且仅当 $d_1+d_2+\cdots+d_k=n$ 时，$A$ 是可对角化的。
> 而要使 $d_1+d_2+\cdots+d_k=n$，只能 $d_1=m_1,d_2=m_2,\cdots,d_k=m_k$ 。

上述定理告诉我们，如何检验方阵 $A$ 是否可对角化：

> [!important] Test for a Diagonalizable Matrix
> 对 $n$ 阶方阵 $A$ 的特征多项式 $\det(A-tI_n)$ 做因式分解，一定可以分解为以下形式：
> $$\det(A-tI_n)=c(t-\lambda_1)^{m_1}(t-\lambda_2)^{m_2}\cdots(t-\lambda_k)^{m_k}$$
> 其中，$c$ 为常数，$\lambda_1,\lambda_2,\cdots,\lambda_k$ 为不同的 eigenvalues，$m_1,m_2,\cdots,m_k$ 是正整数。
> 
> 对于 $A$ 的每一个 eigenvalue ==$\lambda_i$==，对应的 eigenspace 的 dimension 为 ==$d_i$==。
> 则：当且仅当 ==$m_i=d_i$==（$i=1,2,\cdots,k$）时，$A$ 是可对角化的。

> 案例：检验方阵 $A$ 是否可对角化；如果可以，对角化它。
> 
> 【例1】判断矩阵 $A=\begin{bmatrix}-1 & 0 & 0 \\ 0 & 1 & 2 \\ 0 & 2 & 1\end{bmatrix}$ 是否可对角化；如果可以，对角化它。
> 
> 解：特征多项式 $\det A=-(t+1)^2(t-3)$，解得 eigenvalue 是 $-1,3$.
> - 对于 eigenvalue $-1$：$A\mathbf{v}=(-1)\mathbf{v}$，即 $(A+I_3)\mathbf{v}=\mathbf{0}$，将 $A+I_3$ 化为 RREF 得 $\begin{bmatrix}0 & 1 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}$.
>    知 eigenspace 的 dimension 为 $\text{nullity}(A+I_3)=n-\text{rank}(A+I_3)=3-1=2$.
>    $2=2$，没有问题. 进一步求解得 $\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = \begin{bmatrix} x_1 \\ -x_3 \\ x_3 \end{bmatrix} = x_1\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} + x_3\begin{bmatrix} 0 \\ -1 \\ 1 \end{bmatrix}$.
>    故 $\left\{\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}，\begin{bmatrix} 0 \\ -1 \\ 1 \end{bmatrix}\right\}$ 是 $-1$ 对应的 eigenspace 的 basis.
> - 对于 eigenvalue $3$：$A\mathbf{v}=3\mathbf{v}$，即 $(A-3I_3)\mathbf{v}=\mathbf{0}$，将 $A-3I_3$ 化为 RREF 得 $\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & -1 \\ 0 & 0 & 0\end{bmatrix}$.
>    知 eigenspace 的 dimension 为 $\text{nullity}(A-3I_3)=n-\text{rank}(A-3I_3)=3-2=1$.
>    $1=1$，没有问题. 进一步求解得 $\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = \begin{bmatrix} 0 \\ x_3 \\ x_3 \end{bmatrix} = x_3 \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}$.
>    故 $\left\{\begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}\right\}$ 是 $3$ 对应的 eigenspace 的 basis.
> 将这些 bases 组成矩阵 $P=\begin{bmatrix}1 & 0 & 0 \\ 0 & -1 & 1 \\ 0 & 1 & 1\end{bmatrix}$，$D=\begin{bmatrix}-1 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 3\end{bmatrix}$.
> 
> 【例2】判断 $T\left( \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} \right) = \begin{bmatrix} -x_1 + x_2 + 2x_3 \\ x_1 - x_2 \\ 0 \end{bmatrix}$ 是否可对角化；如果可以，对角化它。
> 
> 解：$T$ 对应的矩阵 $A=\begin{bmatrix} -1 & 1 & 2 \\ 1 & -1 & 0 \\ 0 & 0 & 0 \end{bmatrix}$，其特征多项式为 $\det(A-tI_n)=-t^2(t+2)$，解得 eigenvalue 为 $0,-2$.
> - 对于 eigenvalue $0$：$A\mathbf{v}=\mathbf{0}$，将 $A$ 化为 RREF 得 $\begin{bmatrix}  1 & -1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 0 \end{bmatrix}$.
>    知 eigenspace 的 dimension 为 $\text{nullity}(A)=n-\text{rank}(A)=3-2=1$.
>    $1<2$，知 $A$ 不可以对角化.

### Application of Diagonalization

##### 快速计算矩阵幂

> [!success] 快速计算 $A^k$
> 若 $A$ 是可对角化的（$A=PDP^{-1}$，其中 $P$ 是可逆矩阵、$D$ 是对角矩阵），则
> $$A^k=PD^kP^{-1}$$
> 而 $D^k$ 很容易计算：$D = \begin{bmatrix} \lambda_1 & & \\ & \ddots & \\ & & \lambda_n \end{bmatrix}$，则 $D^k = \begin{bmatrix} \lambda_1^k & & \\ & \ddots & \\ & & \lambda_n^k \end{bmatrix}$

> 证明：$A^2=(PDP^{-1})(PDP^{-1})=PD^2P^{-1}$，以此类推。

##### 找到一个自然的 coordinate system，使线性变换变得简单

