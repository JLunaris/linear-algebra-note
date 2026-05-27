
# Norm

> [!example] norm (length)
> 向量 $\mathbf{v}=\begin{bmatrix}v_1 \\ v_2 \\ \vdots \\ v_n\end{bmatrix}$ 的 **norm** 定义为 $\| \mathbf{v} \|=\sqrt{v_1^2+v_2^2+\cdots+v_n^2}$.

> [!quote] p-norm
> 向量 $\mathbf{v}=\begin{bmatrix}v_1 \\ v_2 \\ \vdots \\ v_n\end{bmatrix}$ 的 **p-norm** 的定义为 $\|\mathbf{v}\|_p = \left( \sum\limits_{i=1}^n |v_i|^p \right)^{1/p}$，其中 $p\ge 1$. 例如：
> - 1-norm：$\| \mathbf{v} \|_1=|v_1|+|v_2|+\cdots+|v_n|$
> - 2-norm：$\| \mathbf{v} \|_2=\sqrt{v_1^2+v_2^2+\cdots+v_n^2}$
> - 3-norm：$\| \mathbf{v} \|_3=\sqrt[3]{|v_1|^3+|v_2|^3+\cdots+|v_n|^3}$
> - 4-norm：$\| \mathbf{v} \|_4=\sqrt[4]{v_1^4+v_2^4+\cdots+v_n^4}$

> [!example] distance
> 向量 $\mathbf{u}$ 和 $\mathbf{v}$ 的 **distance** 定义为 $\| \mathbf{u}-\mathbf{v} \|$.

### 性质

> [!important] Theorem
> $\mathbf{u}$ 是向量，$c$ 是标量，有：
> $$\|c\mathbf{u}\|=|c|\|\mathbf{u}\|$$

> 证明：根据定义即证

# Unit Vector

> [!example] unit vector
> norm 为 $1$ 的 vector 称为 **unit vector**。

### Normalization

> [!important] Theorem
> 任何非零向量 $\mathbf{v}$ 都可以被 **normalized**（归一化），即通过==乘以标量 $\cfrac{1}{\|\mathbf{v}\|}$== 将其转换为一个 unit vector。

> 几何含义：不改变方向，只改变长度（长度变为 $1$）。

> 证明：$\left\|\cfrac{1}{\|\mathbf{v}\|}\mathbf{v}\right\|=\left| \cfrac{1}{\|\mathbf{v}\|} \right| \|\mathbf{v}\|=\cfrac{1}{\|\mathbf{v}\|}\|\mathbf{v}\|=1$

# Dot product

> [!example] dot product
> 向量 $\mathbf{u}=\begin{bmatrix}u_1 \\ u_2 \\ \vdots \\ u_n\end{bmatrix}$ 和 $\mathbf{v}=\begin{bmatrix}v_1 \\ v_2 \\ \vdots \\ v_n\end{bmatrix}$ 的 **dot product** 定义为 $\mathbf{u} \cdot \mathbf{v}=u_1v_1+u_2v_2+\cdots+u_nv_n$.

### 性质

> [!important] Theorem
> $$\mathbf{u}\cdot\mathbf{v}=\mathbf{u}^T\mathbf{v}=\mathbf{v}^T\mathbf{u}$$

> 证明：$\mathbf{u} \cdot \mathbf{v}=u_1v_1+u_2v_2+\cdots+u_nv_n=\begin{bmatrix}u_1 & u_2 & \cdots & u_n\end{bmatrix}\begin{bmatrix}v_1 \\ v_2 \\ \vdots \\ v_n\end{bmatrix}=\mathbf{u}^T\mathbf{v}$. 同理，$\mathbf{u} \cdot \mathbf{v}=\mathbf{v}^T\mathbf{u}$.

> [!important] Properties of Dot product
> $\mathbf{u}$、$\mathbf{v}$、$\mathbf{w}$ 是向量，$c$ 是标量。
> 1. **数乘结合律**：$c(\mathbf{u}\cdot\mathbf{v})=(c\mathbf{u})\cdot\mathbf{v}=\mathbf{u}\cdot(c\mathbf{v})$
> 2. **交换律**：$\mathbf{u}\cdot\mathbf{v}=\mathbf{v}\cdot\mathbf{u}$
> 3. **分配率**
>     - 左分配率：$\mathbf{u}\cdot(\mathbf{v}+\mathbf{w})=\mathbf{u}\cdot\mathbf{v}+\mathbf{u}\cdot\mathbf{w}$
>     - 右分配率：$(\mathbf{v}+\mathbf{w})\cdot\mathbf{u}=\mathbf{v}\cdot\mathbf{u}+\mathbf{w}\cdot\mathbf{u}$
> 4. $\mathbf{u}\cdot\mathbf{u}=0$ $\iff$ $\mathbf{u}=\mathbf{0}$

> 证明：根据定义即证

# Norm & Dot product

### 性质

> [!important] Theorem
> $$\mathbf{u}\cdot\mathbf{u}=\|\mathbf{u}\|^2$$

> 证明：根据定义即证

> 【例1】求证 $\|\mathbf{u}+\mathbf{v}\|^2= \|\mathbf{u}\|^2+2(\mathbf{u}\cdot\mathbf{v})+\|\mathbf{v}\|^2$.
> 
> 证明：$\begin{aligned}\|\mathbf{u}+\mathbf{v}\|^2 &=(\mathbf{u}+\mathbf{v})\cdot(\mathbf{u}+\mathbf{v}) \\ &=\mathbf{u}\cdot\mathbf{u}+\mathbf{u}\cdot\mathbf{v}+\mathbf{v}\cdot\mathbf{u}+\mathbf{v}\cdot\mathbf{v} \\ &= \mathbf{u}\cdot\mathbf{u}+2(\mathbf{u}\cdot\mathbf{v})+\mathbf{v}\cdot\mathbf{v} \\ &= \|\mathbf{u}\|^2+2(\mathbf{u}\cdot\mathbf{v})+\|\mathbf{v}\|^2\end{aligned}$
> 
> 【例2】求证 $(\mathbf{u}+\mathbf{v})\cdot(\mathbf{u}-\mathbf{v})=\|\mathbf{u}\|^2-\|\mathbf{v}\|^2$.
> 
> 证明：$(\mathbf{u}+\mathbf{v})\cdot(\mathbf{u}-\mathbf{v})=\mathbf{u}\cdot\mathbf{u}-\mathbf{v}\cdot\mathbf{v}=\|\mathbf{u}\|^2-\|\mathbf{v}\|^2$

### 定理

##### Pythagorean Theorem

> [!important] Pythagorean Theorem in $\mathbb{R}^n$（毕达哥拉斯定理）
> $$\mathbf{u}\perp \mathbf{v} \iff \|\mathbf{u}+\mathbf{v}\|^2=\|\mathbf{u}\|^2+\|\mathbf{v}\|^2$$

> 证明：$\|\mathbf{u}+\mathbf{v}\|^2= \|\mathbf{u}\|^2+2(\mathbf{u}\cdot\mathbf{v})+\|\mathbf{v}\|^2$
> $\mathbf{u}\perp \mathbf{v}$ $\iff$ $\mathbf{u}\cdot\mathbf{v}=0$ $\iff$ $\|\mathbf{u}+\mathbf{v}\|^2=\|\mathbf{u}\|^2+\|\mathbf{v}\|^2$

##### Cauchy–Schwarz Inequality

> [!important] Cauchy–Schwarz Inequality（柯西-施瓦茨不等式，简称柯西不等式）
> $$\mathbf{u}\cdot\mathbf{v}\le \|\mathbf{u}\| \cdot \|\mathbf{v}\|$$

> 助记：$\mathbf{u} \cdot \mathbf{v} = \|\mathbf{u}\| \|\mathbf{v}\| \cos\theta$，而 $\cos\theta\in[-1,1]$，故 $\mathbf{u}\cdot\mathbf{v}\le \|\mathbf{u}\| \cdot \|\mathbf{v}\|$

> 证明（看懂即可）：$\mathbf{u}=\mathbf{0}$ 或 $\mathbf{v}=\mathbf{0}$ 时，不等式显然成立。下证 $\mathbf{u}\neq\mathbf{0}$ 且 $\mathbf{v}\neq\mathbf{0}$ 时的情况：
> 令 $\mathbf{w}=\cfrac{1}{\|\mathbf{u}\|}\mathbf{u}$，$\mathbf{z}=\cfrac{1}{\|\mathbf{v}\|}\mathbf{v}$，则 $\mathbf{w}\cdot\mathbf{w}=\mathbf{z}\cdot\mathbf{z}=1$
> 则 $0\le\|\mathbf{w}\pm\mathbf{z}\|^2=(\mathbf{w}\pm\mathbf{z})\cdot(\mathbf{w}\pm\mathbf{z})=\mathbf{w}\cdot\mathbf{w}+\mathbf{z}\cdot\mathbf{z}\pm2(\mathbf{w}\cdot\mathbf{z})=2\pm2(\mathbf{w}\cdot\mathbf{z})$
> 即 $\pm\mathbf{w}\cdot\mathbf{z}\le 1$，即 $|\mathbf{w}\cdot\mathbf{z}|\le 1$，即 $\left|(\cfrac{1}{\|\mathbf{u}\|}\mathbf{u})\cdot(\cfrac{1}{\|\mathbf{v}\|}\mathbf{v})\right|\le 1$，即 $\cfrac{1}{\|\mathbf{u}\|  \|\mathbf{v}\|}|\mathbf{u}\cdot\mathbf{v}|\le 1$
> 即 $|\mathbf{u}\cdot\mathbf{v}|\le \|\mathbf{u}\| \cdot \|\mathbf{v}\|$，即 $\mathbf{u}\cdot\mathbf{v}\le \|\mathbf{u}\| \cdot \|\mathbf{v}\|$ 

##### Triangle Inequality

> [!important] Triangle Inequality（三角不等式）
> $$\|\mathbf{u}+\mathbf{v}\| \le \|\mathbf{u}\| + \|\mathbf{v}\|$$

> 助记：三角形两边之和大于第三边。

> 证明：只要证 $\|\mathbf{u}+\mathbf{v}\|^2 \le (\|\mathbf{u}\| + \|\mathbf{v}\|)^2$
> 即 $(\mathbf{u}+\mathbf{v})\cdot(\mathbf{u}+\mathbf{v}) \le \|\mathbf{u}\|^2+\|\mathbf{v}\|^2+2\|\mathbf{u}\|\|\mathbf{v}\|$
> 即 $\|\mathbf{u}\|^2+2(\mathbf{u}\cdot\mathbf{v})+\|\mathbf{v}\|^2 \le \|\mathbf{u}\|^2+\|\mathbf{v}\|^2+2\|\mathbf{u}\|\|\mathbf{v}\|$
> 即 $2(\mathbf{u}\cdot\mathbf{v}) \le 2\|\mathbf{u}\|\|\mathbf{v}\|$，即 $\mathbf{u}\cdot\mathbf{v} \le \|\mathbf{u}\|\|\mathbf{v}\|$
> 这正是柯西不等式。

# Orthogonal

> [!example] orthogonal (perpendicular)
> 若 $\mathbf{u}\cdot\mathbf{v}=0$，则称 $\mathbf{u}$ 和 $\mathbf{v}$ 是 **orthogonal** 的，记作 $\mathbf{u}\perp\mathbf{v}$。

> [!NOTE] 
> $\mathbf{0}$ 与任何向量正交。

### Orthogonal Set

> [!example] orthogonal set
> 若向量集 $S$ 中的所有向量两两间都是 orthogonal 的，则称 $S$ 是 **orthogonal set**。
> 特别地，只有一个向量的集合是 orthogonal set。

> 【例】判断 $\mathcal{S} = \left\{ \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}, \begin{bmatrix} 1 \\ 1 \\ -1 \end{bmatrix}, \begin{bmatrix} 5 \\ -4 \\ 1 \end{bmatrix} \right\}$ 是不是 orthogonal set
> 解：令集合中的三个向量分别为：$v_1 = \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix},  v_2 = \begin{bmatrix} 1 \\ 1 \\ -1 \end{bmatrix}, v_3 = \begin{bmatrix} 5 \\ -4 \\ 1 \end{bmatrix}$
> 验证这些向量是否两两间 orthogonal：
> - $\mathbf{v}_1 \cdot \mathbf{v}_2 = 1 + 2 - 3 = 0$ $\implies$ $\mathbf{v}_1\perp\mathbf{v}_2$
> - $\mathbf{v}_1 \cdot \mathbf{v}_3 = 5 - 8 + 3 = 0$ $\implies$ $\mathbf{v}_1\perp\mathbf{v}_3$
> - $\mathbf{v}_2 \cdot \mathbf{v}_3 = 5 - 4 - 1 = 0$ $\implies$ $\mathbf{v}_2\perp\mathbf{v}_3$
> 综上，$S$ 是 orthogonal set

##### 不含零向量的 orthogonal set 是 independent 的

> [!question] orthogonal set 一定是 independent 的吗？
> 不一定。反例：包含 $\mathbf{0}$ 的 orthogonal set。

> [!important] Theorem
> 不含零向量的 orthogonal set 是 independent 的。

> 证明：设 $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$ 是 orthogonal set，且所有元素都不是 $\mathbf{0}$。
> 只要证 $c_1\mathbf{v}_1+c_2\mathbf{v}_2+\cdots+c_k\mathbf{v}_k=\mathbf{0}$ 的唯一解是 $c_1=c_2=\cdots=c_k=0$。
> 对于任意 $\mathbf{v}_i$，有 $(c_1\mathbf{v}_1+c_2\mathbf{v}_2+\cdots+c_k\mathbf{v}_k)\cdot\mathbf{v}_i=0$
> $\begin{aligned}(c_1\mathbf{v}_1+c_2\mathbf{v}_2+\cdots+c_k\mathbf{v}_k)\cdot\mathbf{v}_i &=(c_1\mathbf{v}_1)\cdot\mathbf{v}_i+(c_2\mathbf{v}_2)\cdot\mathbf{v}_i+\cdots+(c_k\mathbf{v}_k)\cdot\mathbf{v}_i \\ &= c_1(\mathbf{v}_1\cdot\mathbf{v}_i)+c_2(\mathbf{v}_2\cdot\mathbf{v}_i)+\cdots+c_k(\mathbf{v}_k\cdot\mathbf{v}_i) \\ &= c_i(\mathbf{v}_i\cdot\mathbf{v}_i) \\ &= c_i \|\mathbf{v}_i\|^2\end{aligned}$
> 即 $c_i \|\mathbf{v}_i\|^2=0$，而 $\mathbf{v}_i\neq\mathbf{0}$，故 $c_i=0$
> $\implies$ $c_1=c_2=\cdots=c_k=0$
> 带回原方程显然成立，因此 $c_1\mathbf{v}_1+c_2\mathbf{v}_2+\cdots+c_k\mathbf{v}_k=\mathbf{0}$ $\iff$ $c_1=c_2=\cdots=c_k=0$

### Orthonormal Set

> [!example] orthonormal set
> 所有向量都是 unit vector 的 orthogonal set 称为 **orthonormal set**。

> 例如 $\mathcal{S} = \left\{ \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}, \begin{bmatrix} 1 \\ 1 \\ -1 \end{bmatrix}, \begin{bmatrix} 5 \\ -4 \\ 1 \end{bmatrix} \right\}$ 是 orthogonal set，但不是 orthonormal set
> 把所有向量进行 normalization，得到 orthonormal set $\mathcal{S}' = \left\{ \frac{1}{\sqrt{14}} \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}, \, \frac{1}{\sqrt{3}} \begin{bmatrix} 1 \\ 1 \\ -1 \end{bmatrix}, \, \frac{1}{\sqrt{42}} \begin{bmatrix} 5 \\ -4 \\ 1 \end{bmatrix} \right\}$

> [!important] Theorem
> orthonormal set 是 independent 的。

> 证明：不含零向量的 orthogonal set 是 independent 的，orthonormal set 不含零向量。

### Orthogonal / Orthonormal Basis

> [!example] orthogonal / orthonormal basis
> - 如果一个 basis 是 orthogonal set，称为 **orthogonal basis**
> - 如果一个 basis 是 orthonormal set，称为 **orthonormal basis**

> 例如 $\mathcal{S} = \left\{ \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} \right\}$ 是 $\mathbb{R}^3$ 的 basis，也是 orthogonal basis，也是 orthonormal basis

### 用 orthogonal / orthonormal basis 表示 subspace 中的向量

> [!important] Theorem
> $S=\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$ 是 subspace $V$ 的一个 ==orthogonal basis==，则对于任意 $\mathbf{u}\in V$ 有：
> $$\mathbf{u}=c_1\mathbf{v}_1+c_2\mathbf{v}_2+\cdots+c_k\mathbf{v}_k$$
> 其中，$c_i=\cfrac{\mathbf{u}\cdot\mathbf{v}_i}{\|\mathbf{v}_i\|^2}$（$i=1,2,\cdots,k$）.
> 特别地，若 $S$ 是 ==orthonormal basis==，则 $c_i=\mathbf{u}\cdot\mathbf{v}_i$.

> 证明：$S=\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$ 是 subspace $V$ 的一个 orthogonal basis，则对于任意 $\mathbf{u}\in V$ 有 $\mathbf{u}=c_1\mathbf{v}_1+c_2\mathbf{v}_2+\cdots+c_k\mathbf{v}_k$。
> 则 $\mathbf{u}\cdot\mathbf{v}_i=c_1\mathbf{v}_1\cdot\mathbf{v}_i+c_2\mathbf{v}_2\cdot\mathbf{v}_i+\cdots+c_k\mathbf{v}_k\cdot\mathbf{v}_i=c_i\mathbf{v}_i\cdot\mathbf{v}_i$
> $\implies$ $\mathbf{u}\cdot\mathbf{v}_i=c_i\|\mathbf{v}_i\|^2$
> $\implies$ $c_i=\cfrac{\mathbf{u}\cdot\mathbf{v}_i}{\|\mathbf{v}_i\|^2}$
> 特别地，若 $S$ 是 orthonormal basis，则 $\|\mathbf{v}_i\|=1$，则 $c_i=\mathbf{u}\cdot\mathbf{v}_i$

> 示例：$S=\left\{\begin{bmatrix}1 \\ 2 \\3 \end{bmatrix},\begin{bmatrix}1 \\ 1 \\ -1 \end{bmatrix},\begin{bmatrix}5 \\ -4 \\1 \end{bmatrix}\right\}$ 是 $\mathbb{R}^3$ 的一个 orthogonal basis，$\mathbf{u}=\begin{bmatrix}3 \\ 2 \\ 1 \end{bmatrix}$，求 $[\mathbf{u}]_S$。
> 
> 解：
> **法1**：$[\mathbf{u}]_S=S^{-1}\mathbf{u}$
> **法2**：设 $S$ 的三个向量分别是 $\mathbf{v}_1,\mathbf{v}_2,\mathbf{v}_3$。
> $\mathbf{u}=c_1\mathbf{v}_1+c_2\mathbf{v}_2+c_3\mathbf{v}_3$，其中 $c_1=\cfrac{\mathbf{u}\cdot\mathbf{v}_1}{\|\mathbf{v}_1\|^2}=\cfrac{10}{14}$，$c_2=\cfrac{\mathbf{u}\cdot\mathbf{v}_2}{\|\mathbf{v}_2\|^2}=\cfrac{4}{3}$，$c_3=\cfrac{\mathbf{u}\cdot\mathbf{v}_3}{\|\mathbf{v}_3\|^2}=\cfrac{8}{42}$
> 故 $[\mathbf{u}]_S=\begin{bmatrix}\cfrac{10}{14} \\ \cfrac{4}{3} \\ \cfrac{8}{42}\end{bmatrix}$

### Gram-Schmidt Process

> [!important] Gram-Schmidt Process
> subspace $W$ 的任意 ==basis== $\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$ 都可以改造为 ==orthogonal basis== $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$，改造过程如下：
> $$\begin{aligned} \mathbf{v}_1 &= \mathbf{u}_1, \\ \mathbf{v}_2 &= \mathbf{u}_2 - \cfrac{\mathbf{u}_2 \cdot \mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1, \\ \mathbf{v}_3 &= \mathbf{u}_3 - \cfrac{\mathbf{u}_3 \cdot \mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1 - \cfrac{\mathbf{u}_3 \cdot \mathbf{v}_2}{\|\mathbf{v}_2\|^2}\mathbf{v}_2, \\ &\ \ \vdots \\ \mathbf{v}_k &= \mathbf{u}_k - \cfrac{\mathbf{u}_k \cdot \mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1 - \cfrac{\mathbf{u}_k \cdot \mathbf{v}_2}{\|\mathbf{v}_2\|^2}\mathbf{v}_2 - \dots - \cfrac{\mathbf{u}_k \cdot \mathbf{v}_{k-1}}{\|\mathbf{v}_{k-1}\|^2}\mathbf{v}_{k-1}. \end{aligned}$$

> 示例：$S=\{\mathbf{u}_1,\mathbf{u}_2,\mathbf{u}_3\}$ 是 subspace $W$ 的一个 basis，将其正交化为 orthogonal basis。
> 其中 $\mathbf{u}_1=\begin{bmatrix}1 \\ 1 \\ 1 \\ 1\end{bmatrix}$，$\mathbf{u}_2=\begin{bmatrix}2 \\ 1 \\ 0 \\ 1\end{bmatrix}$，$\mathbf{u}_3=\begin{bmatrix}1 \\ 1 \\ 2 \\ 1\end{bmatrix}$.
> 
> 解：$\mathbf{v}_1=\mathbf{u}_1=\begin{bmatrix}1 \\ 1 \\ 1 \\ 1\end{bmatrix}$
> $\mathbf{v}_2 = \mathbf{u}_2 - \cfrac{\mathbf{u}_2 \cdot \mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1 = \begin{bmatrix} 2 \\ 1 \\ 0 \\ 1 \end{bmatrix} - \cfrac{4}{4} \begin{bmatrix} 1 \\ 1 \\ 1 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 \\ 0 \\ -1 \\ 0 \end{bmatrix}$
> $\mathbf{v}_3 = \mathbf{u}_3 - \cfrac{\mathbf{u}_3 \cdot \mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1 - \cfrac{\mathbf{u}_3 \cdot \mathbf{v}_2}{\|\mathbf{v}_2\|^2}\mathbf{v}_2 = \begin{bmatrix} 1 \\ 1 \\ 2 \\ 1 \end{bmatrix} - \cfrac{5}{4} \begin{bmatrix} 1 \\ 1 \\ 1 \\ 1 \end{bmatrix} - \cfrac{(-1)}{2} \begin{bmatrix} 1 \\ 0 \\ -1 \\ 0 \end{bmatrix} = \cfrac{1}{4} \begin{bmatrix} 1 \\ -1 \\ 1 \\ -1 \end{bmatrix}$

> 证明：对于 $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k\}$：
> **(1)** 证明 $\text{Span}\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n}\}=\text{Span}\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_{n}\}$，其中 $n$ 是常数，$n\le k$
> - 一方面，每个 $\mathbf{v}_i$ 都是由 $\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_i$ 线性组合得到，故 $\text{Span}\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n}\}\subseteq\text{Span}\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_{n}\}$
> - 另一方面，由 Gram–Schmidt 公式移项可知，每个 $\mathbf{u}_i$ 都是由 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_i$ 线性组合得到，故 $\text{Span}\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_{n}\}\subseteq\text{Span}\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n}\}$
> 综上，$\text{Span}\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n}\}=\text{Span}\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_{n}\}$    ■
> 
> **(2)** 证明 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_k$ 都不是 $\mathbf{0}$
> 使用归纳法，$\mathbf{v}_1=\mathbf{u}_1\neq\mathbf{0}$（因为 basis 不可能含有 $\mathbf{0}$），下设 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n-1}\neq\mathbf{0}$，只要证 $\mathbf{v}_n\neq\mathbf{0}$。
> $\mathbf{v}_n=\mathbf{u}_n - \cfrac{\mathbf{u}_n \cdot \mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1 - \cfrac{\mathbf{u}_n \cdot \mathbf{v}_2}{\|\mathbf{v}_2\|^2}\mathbf{v}_2 - \dots - \cfrac{\mathbf{u}_n \cdot \mathbf{v}_{n-1}}{\|\mathbf{v}_{n-1}\|^2}\mathbf{v}_{n-1}$
> 假设 $\mathbf{v}_n=\mathbf{0}$，则 $\mathbf{u}_n=\cfrac{\mathbf{u}_n \cdot \mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1+\cfrac{\mathbf{u}_n \cdot \mathbf{v}_2}{\|\mathbf{v}_2\|^2}\mathbf{v}_2+\cdots+\cfrac{\mathbf{u}_n \cdot \mathbf{v}_{n-1}}{\|\mathbf{v}_{n-1}\|^2}\mathbf{v}_{n-1}$
> 则 $\mathbf{u}_n\in\text{Span}\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n-1}\}=\text{Span}\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_{n-1}\}$
> 这与 $\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_n\}$ 是 basis 矛盾！故 $\mathbf{v}_n\neq\mathbf{0}$。    ■
> 
> **(3)** 证明它是 orthogonal set
> 使用归纳法，显然 $\{\mathbf{v}_1\}$ 是 orthogonal set，下设 $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n-1}\}$ 是 orthogonal set，只要证 $\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n-1},\mathbf{v}_n\}$ 是 orthogonal set。
> 由于已知 $\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n-1}$ 两两间正交，因此只要证 $\mathbf{v}_n\perp\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{n-1}$
> 即证 $\mathbf{v}_n\cdot\mathbf{v}_i=0$（$i=1,2,\cdots,n-1$）
> $\begin{aligned}\mathbf{v}_n\cdot\mathbf{v}_i&=(\mathbf{u}_n - \cfrac{\mathbf{u}_n \cdot \mathbf{v}_1}{\|\mathbf{v}_1\|^2}\mathbf{v}_1 - \cfrac{\mathbf{u}_n \cdot \mathbf{v}_2}{\|\mathbf{v}_2\|^2}\mathbf{v}_2 - \dots - \cfrac{\mathbf{u}_n \cdot \mathbf{v}_{n-1}}{\|\mathbf{v}_{n-1}\|^2}\mathbf{v}_{n-1})\cdot\mathbf{v}_i \\ &= \mathbf{u}_n\cdot\mathbf{v}_i-\cfrac{\mathbf{u}_n \cdot \mathbf{v}_i}{\|\mathbf{v}_i\|^2}\mathbf{v}_i\cdot\mathbf{v}_i \\ &= \mathbf{u}_n\cdot\mathbf{v}_i-\cfrac{\mathbf{u}_n \cdot \mathbf{v}_i}{\|\mathbf{v}_i\|^2}\|\mathbf{v}_i\|^2 \\ &=0\quad ■\end{aligned}$
> 
> **(4)** 证明它是 $\text{Span}\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$ 的 basis
> **(4.1)** 证明它 independent：前面证明过它是 orthogonal set，因此只要证它不含 $\mathbf{0}$，即可证明它 independent。(2) 已经证明了它不含 $\mathbf{0}$。    ■
> **(4.2)** 证明它是 generating set：即证 $\text{Span}\{\mathbf{v}_1,\mathbf{v}_2,\cdots,\mathbf{v}_{k}\}=\text{Span}\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_{k}\}$。(1) 已经证明了这一点。    ■
