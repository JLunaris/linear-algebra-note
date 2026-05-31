
# Orthogonal Matrix

> [!example] orthogonal matrix
> 若 $n\times n$ ==方阵== $Q$ 的 columns 是 ==orthonormal== 的，则称 $Q$ 是 **orthogonal matrix**。

> 案例：判断 $\theta$-rotation 矩阵 $A_\theta = \begin{bmatrix} \cos \theta & -\sin \theta \\ \sin \theta & \cos \theta \end{bmatrix}$ 是不是 orthogonal matrix。
> 
> 解：首先 $A_\theta$ 是方阵。由 $\begin{bmatrix} \cos \theta \\ \sin \theta \end{bmatrix} \cdot \begin{bmatrix} -\sin \theta \\ \cos \theta \end{bmatrix} =  0$ 知，$A_\theta$ 的 columns 是 orthogonal 的；再结合 $\left\|\begin{bmatrix} \cos \theta \\ \sin \theta \end{bmatrix}\right\|= 1$，$\left\|\begin{bmatrix} -\sin \theta \\ \cos \theta \end{bmatrix}\right\|= 1$ 知，$A_\theta$ 的 columns 是 orthonormal 的。
> 因此 $A_\theta$ 是 orthogonal matrix。

> [!example] orthogonal operator
> 若 linear operator $T$ 对应的矩阵是 orthogonal matrix，则称 $T$ 是 **orthogonal operator**.

### orthogonal matrix ⟺ norm-preserving

> [!example] norm-preserving
> 对于 linear operator $T:\mathbb{R}^n\to\mathbb{R}^n$，若对于任意向量 $\mathbf{u}\in\mathbb{R}^n$，都有
> $$\|T(\mathbf{u})\|=\|\mathbf{u}\|$$
> 则称 $T$ 是 **norm-preserving** 的。

> 即输入、输出向量的 norm 相等（但方向不一定相同）。

> 案例：
> ① $\theta$-rotation 矩阵 $A_\theta = \begin{bmatrix} \cos \theta & -\sin \theta \\ \sin \theta & \cos \theta \end{bmatrix}$ 是 norm-preserving 的，因为它只旋转向量，不改变向量的长度。
> ② 矩阵 $A=\begin{bmatrix}1 & 0 \\ 0 & -1\end{bmatrix}$ 将任意向量关于 $x$ 轴翻转，不改变向量的长度，因此是 norm-preserving 的。

> [!important] Theorem
> $Q$ 是一个 $n\times n$ 矩阵（**方阵**），有：$Q$ is orthogonal $\iff$ $Q$ is norm-preserving

> 证明：见 Orthogonal Matrix Theorem。

### Orthogonal Matrix Theorem

> [!important] Theorem
> $Q$ 是一个 $n\times n$ 矩阵（**方阵**），$Q$ is orthogonal **等价于**以下任一条件：
> 1. $Q$ is invertible，且 ==$Q^{-1}=Q^T$==（等价于 ==$Q^TQ=I_n$==）
> 2. $Q$ preserves dot product（即 $\forall\mathbf{u},\mathbf{v}\in\mathbb{R}^n$，==$Q\mathbf{u}\cdot Q\mathbf{v}=\mathbf{u}\cdot\mathbf{v}$==）
> 3. $Q$ preserves norm（即 $\forall\mathbf{u}\in\mathbb{R}^n$，==$\|Q\mathbf{u}\|=\|\mathbf{u}\|$==）

> 证明：将 $Q$ is orthogonal 记作命题 (0)。设 $Q=\begin{bmatrix}\mathbf{q}_1 & \mathbf{q}_2 & \cdots & \mathbf{q}_n\end{bmatrix}$。
> 
> (3)$\implies$(0)：只要证 $\|\mathbf{q}_i\|=1$ 且 $\mathbf{q}_i\cdot\mathbf{q}_j=0$ （$\forall i,j=1,2,\cdots,n$）
> $\|\mathbf{q}_i\|=\|Q\mathbf{e}_i\|$，由于 $Q$ 是 norm-preserving 的，因此 $\|Q\mathbf{e}_i\|=\|\mathbf{e}_i\|=1$，因此 $\|\mathbf{q}_i\|=1$。
> $\|\mathbf{q}_i+\mathbf{q}_j\|^2=\|Q\mathbf{e}_i+Q\mathbf{e}_j\|^2=\|Q(\mathbf{e}_i+\mathbf{e}_j)\|^2=\|\mathbf{e}_i+\mathbf{e}_j\|^2=2$ ……①
> $\|\mathbf{q}_i+\mathbf{q}_j\|^2=(\mathbf{q}_i+\mathbf{q}_j)\cdot(\mathbf{q}_i+\mathbf{q}_j)=\|\mathbf{q}_i\|^2+\|\mathbf{q}_j\|^2+2(\mathbf{q}_i\cdot\mathbf{q}_j)=2+2(\mathbf{q}_i\cdot\mathbf{q}_j)$ ……②
> 由①②式知，$\mathbf{q}_i\cdot\mathbf{q}_j=0$
> 
> (0)$\implies$(1)：只要证 $Q^TQ=I_n$。
> $Q^TQ=\begin{bmatrix}\mathbf{q}_1^T \\ \mathbf{q}_2^T \\ \vdots \\ \mathbf{q}_n^T\end{bmatrix}\begin{bmatrix}\mathbf{q}_1 & \mathbf{q}_2 & \cdots & \mathbf{q}_n\end{bmatrix}=\begin{bmatrix} \mathbf{q}_1\cdot\mathbf{q}_1 & \mathbf{q}_1\cdot\mathbf{q}_2 & \cdots & \mathbf{q}_1\cdot\mathbf{q}_n \\ \mathbf{q}_2\cdot\mathbf{q}_1 & \mathbf{q}_2\cdot\mathbf{q}_2 & \cdots & \mathbf{q}_2\cdot\mathbf{q}_n \\ \vdots & \vdots & \ddots & \vdots \\ \mathbf{q}_n\cdot\mathbf{q}_1 & \mathbf{q}_n\cdot\mathbf{q}_2 & \cdots & \mathbf{q}_n\cdot\mathbf{q}_n \end{bmatrix}= \begin{bmatrix} 1 & 0 & \cdots & 0 \\ 0 & 1 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1 \end{bmatrix} = I_n$
> 
> 
> (1)$\implies$(2)：$Q\mathbf{u}\cdot Q\mathbf{v}=(Q\mathbf{u})^TQ\mathbf{v}=\mathbf{u}^TQ^TQ\mathbf{v}=\mathbf{u}^T\mathbf{v}=\mathbf{u}\cdot\mathbf{v}$
> 
> (2)$\implies$(3)：$Q\mathbf{u}\cdot Q\mathbf{v}=\mathbf{u}\cdot\mathbf{v}$ $\implies$ $Q\mathbf{u}\cdot Q\mathbf{u}=\mathbf{u}\cdot\mathbf{u}$ $\implies$ $\|Q\mathbf{u}\|^2=\|\mathbf{u}\|^2$ $\implies$ $\|Q\mathbf{u}\|=\|\mathbf{u}\|$
> 
> 综上，这些推导形成了闭环，因此这些命题等价。

### Properties

> [!important] Theorem
> 设 $P$、$Q$ 都是 orthogonal matrix，则：
> 1. $\text{det}\ Q=\pm 1$
> 2. $PQ$ 是 orthogonal matrix
> 3. $Q^{-1}$ 是 orthogonal matrix
> 4. $Q^T$ 是 orthogonal matrix

> 证明：
> **命题1**：$\text{det}(QQ^T)=\text{det}(I_n)=1$ ……①
> $\text{det}(QQ^T)=(\text{det}\ Q)(\text{det}\ Q^T)=(\text{det}\ Q)(\text{det}\ Q)=(\text{det}\ Q)^2$ ……②
> 由①②知 $\text{det}\ Q=\pm 1$
> **命题2**：
> 法1：对于任意向量 $\mathbf{u}$，$PQ\mathbf{u}$ 表示把 $\mathbf{u}$ 先经过 $Q$ 再经过 $P$。而 $P$、$Q$ 都是 orthogonal matrix，因此它们都是 norm-preserving 的，因此 $\mathbf{u}$ 的 norm 不会改变，因此 $PQ$ 是 norm-preserving 的，因此 $PQ$ 是 orthogonal matrix。
> （数学描述：$\|Q\mathbf{u}\|=\|\mathbf{u}\|$，$\|P(Q\mathbf{u})\|=\|Q\mathbf{u}\|$，因此 $\|PQ\mathbf{u}\|=\|P(Q\mathbf{u})\|=\|Q\mathbf{u}\|=\|\mathbf{u}\|$，因此 $PQ$ 是 norm-preserving 的，因此 $PQ$ 是 orthogonal matrix）
> 法2：只要证 $(PQ)^{-1}=(PQ)^T$。有 $(PQ)^{-1}=Q^{-1}P^{-1}=Q^TP^T=(PQ)^T$。
> **命题3**：
> 法1：$Q$ 是 norm-preserving 的，则 $Q$ 的逆操作显然也是 norm-preserving 的。
> 法2：只要证 $(Q^{-1})^{-1}=(Q^{-1})^T$。有 $(Q^{-1})^{-1}=(Q^T)^{-1}=(Q^{-1})^T$。
> **命题4**：$Q^T=Q^{-1}$，已经证明 $Q^{-1}$ 是 orthogonal matrix，所以 $Q^T$ 也是。

> [!NOTE] 
> 一个==方阵==，若它的 columns 是 orthonormal 的，则它的 rows 也是 orthonormal 的。

> 原因：方阵 $P$ 的 columns 是 orthonormal 的 $\implies$ $P$ 是 orthogonal matrix $\implies$ $P^T$ 是 orthogonal matrix $\implies$ $P^T$ 的 columns 是 orthonormal 的，即 $P$ 的 rows 是 orthonormal 的。
