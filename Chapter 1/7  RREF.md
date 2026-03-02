
# Column Correspondence Theorem

> [!important] Theorem
> elementary row operation 前后的两个矩阵，其列向量之间的线性组合关系完全相同。

> 原因：
> ①==每次 elementary row operation 都不会改变列向量间的线性组合关系==
> ②==所有的 elementary row operation 都是可逆的==
> 
> 以下示例演示了三种 elementary row operation（interchange、scaling、row addition）都没有改变矩阵的 $\mathbf{a}_1+\mathbf{a}_2=\mathbf{a}_3$ 这一关系：
> ![[Pasted image 20260216121721.png|600]]

---

> [!NOTE] 推论
> ![[Pasted image 20260216110936.png|500]]

> 原因：RREF 是由原矩阵经过多次 elementary row operation 得到的，而每次 elementary row operation 都不会改变 column 间的线性组合关系。

> 【示例】$R$ 是 $A$ 的 RREF，有以下关系：
> 
> ![[Pasted image 20260216112343.png|500]]

# Pivot Column

### 性质

##### Pivot columns are independent.

![[Pasted image 20260223130008.png|550]]

> 证明：如图所示，$A$ 是一个矩阵，$R$ 是它的 RREF。
> - RREF 中的 pivot columns 显然 independent。
>     原因：每个 pivot column 都是 unit vector $\mathbf{e}_1,\mathbf{e}_2,\cdots$，每个 unit vector 都一定不是其他 unit vector 的 linear combination。
> - 由 Column Correspondence Theorem 知，$A$ 的 pivot columns 也是 independent 的。

##### 每个 non-pivot column 一定是它左侧的 pivot columns 的 linear combination

![[Pasted image 20260223125743.png|550]]

> 证明：如图所示，$A$ 是一个矩阵，$R$ 是它的 RREF。
> - RREF 中，每个 non-pivot column 都是它左边的 pivot columns 的 linear combination（trivial）
> - 由 Column Correspondence Theorem 知，$A$ 中具有同样的线性组合关系。

### Pivot column vs Independent

> [!important] Theorem
> 在矩阵 $A$ 中：
> - Columns  of A are **independent** ⇔ 每一列都是 pivot column
> - Columns  of A are **dependent** ⇔ 存在 non-pivot column

> 证明：（仅证命题1，对命题1两边取否定即得命题2）
> 【左推右】
>   假设存在一个 non-pivot column
>   那它一定是左侧的 pivot columns 的 linear combination（pivot column的性质2）
>   ⇒ Columns of A are dependent，与已知条件矛盾！
> 【右推左】（pivot column的性质1）

> 案例
> ①已知一个 $3\times 3$ 的矩阵的列向量是 independent 的，求它的 RREF。
> 
> 解： 由矩阵的列向量 independent 知：它的每一列都是 pivot column
>     而 pivot column 一定是单位向量
>     综上，它的 RREF 一定是下面这样：
>    ![[Pasted image 20260223184655.png|500]]
>    
> ②已知一个 $4\times 3$ 的矩阵的列向量是 independent 的，则它的 RREF 一定是下面这样：
>    ![[Pasted image 20260223185013.png|500]]
>    
> ③一个 $3\times 4$ 的矩阵的列向量不可能是 independent 的：
>    ![[Pasted image 20260224101403.png|500]]

> [!NOTE] Summary
> - 若**方形矩阵** ($m=n$) 的 columns 是 independent 的，则它的 RREF 一定是单位矩阵 $I$。
> - 若**高瘦矩阵** ($m>n$) 的 columns 是 independent 的，则它的 RREF 一定是 $\begin{bmatrix}I\\ O\end{bmatrix}$。
> - ==**矮胖矩阵** ($m<n$) 的 columns 一定是 dependent 的==。
>   换句话说，==More than $m$ vectors in $\mathbb{R}^m$ must be dependent==。
>   换句话说，==$m$ 维空间中最多能选出 $m$ 个向量构成 independent 向量组==。

# Check Independence

> [!question] 
> 向量 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \in \mathbb{R}^n$，判断这组向量 dependent 还是 independent。

##### 根据定义判断

根据定义，需要判断方程 $x_1\mathbf{u}_1+x_2\mathbf{u}_2+\cdots+x_k\mathbf{u}_k=\mathbf{0}$ 是否存在不全为零的解。从 **column aspect** 来看，该方程是一个线性方程组 $A\mathbf{x}=\mathbf{0}$（其中 $A=\begin{bmatrix}\mathbf{u}_1 & \mathbf{u}_2 & \cdots & \mathbf{u}_k\end{bmatrix}$，$\mathbf{x}=\begin{bmatrix}x_1 \\ x_2 \\ \vdots \\ x_k\end{bmatrix}$），可以直接求解该方程组，根据方程组==是否存在非 $\mathbf{0}$ 解==来确定向量组 dependent 还是 independent。

> 例：
> ![[Pasted image 20260221111038.png|500]]
> 
> ![[Pasted image 20260223091720.png|500]]

##### 根据 RREF 是否有 non-pivot column 判断

将向量组写成矩阵的形式，化为 RREF，看是否有 non-pivot column。

> 【例1】
> ![[Pasted image 20260224112955.png|400]]
> 
> 解：dependent，因为矮胖矩阵一定有 non-pivot column。
> 
> 【例2】Dependent or Independent？
> ![[Pasted image 20260224114752.png|180]]
> 
> 解：$\begin{bmatrix}1 & 1 & 1 \\ 2 & -3 & 2 \\ 0 & 1 & -2 \\ -1 & -2 &3\end{bmatrix}$ $\xrightarrow{RREF}$ $\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 &0\end{bmatrix}$
> 全是 pivot column，因此 independent。

# Rank

> [!NOTE] rank的三个等价定义
> 1. 最多能选出多少个列向量构成 independent 向量组
> 2. pivot columns 的个数
> 3. RREF 中 non-zero rows 的个数

#### rank = pivot columns 的个数 = RREF 中 non-zero rows 的个数

> [!important] Theorem
> **rank** = ==pivot columns 的个数== = ==RREF 中 non-zero rows 的个数==

> **第二个等号的证明：**
> RREF 中，每一个 non-zero row 都会有一个 leading entry，而每一个 leading entry 对应一个 pivot column。

> **第一个等号的证明：**
> 设矩阵 $A$ 的 RREF 为 $R$。由 Column Correspondence Theorem 知
> $$\text{rank}(R)=\text{rank}(A)$$
>     ![[Pasted image 20260224191612.png|600]]
> 在 $R$ 中选出所有的 pivot columns（设个数为 $r$）。由 pivot column 的性质1知，这些向量一定 independent，故
> $$\text{rank}\ge r$$
>     ![[Pasted image 20260224191705.png|600]]
> 去掉 RREF 中的 zero rows 不会改变列向量间的线性组合关系（trivial），裁剪后的矩阵仅剩 non-zero rows，个数为 $r$（因为“RREF 中 non-zero rows 的个数 = pivot columns 的个数”），因此矩阵中的每一列可视为 $\mathbb{R}^r$ 中的向量。 而 $r$ 维空间中最多能选出 $r$ 个向量构成 independent 向量组（见"Pivot column vs Independent"的"Summary"部分），故
> $$\text{rank}\le r$$
>     ![[Pasted image 20260224191734.png|600]]
> 综上，$\text{rank}=r$。

#### rank ≤ min(m, n)

$A$ 是一个 $m\times n$ 矩阵，有以下结论：

> [!important] Theorem
> $$\text{rank}\ A\le \text{min}(m,n)$$

> 证明：根据 rank 的两个等价定义（图中蓝色、橙色方框）
> ![[Pasted image 20260225111058.png|600]]

> [!NOTE] full rank / rank deficient
> - 若 $\text{rank}\ A=\text{min}(m,n)$，则称 $A$ is **full rank**.
> - 若 $\text{rank}\ A<\text{min}(m,n)$，则称 $A$ is **rank deficient**.

> [!NOTE] 
> 从 rank 角度解释 “**矮胖矩阵** ($m<n$) 的 columns 一定是 dependent 的”：
> 
> ① $\text{rank}\ A=n$ $\iff$ $A$ 的列 independent
> ② $\text{rank}\ A\le \text{min}(m,n)$
> 
> 由①②知，若 $m<n$，则 $A$ 的列 dependent

#### 与solution of system of linear equations的关系

> [!NOTE] Overview
> - 是否有解？$\implies$ **由 $A$ 和 $\mathbf{b}$ 共同决定**
> - 有解的前提下，有唯一解/无穷多解？$\implies$ **只跟 $A$ 有关**
> - 是否总是有解？$\implies$ **只跟 $A$ 有关**

> 例1：A system of linear equations is called *underdetermined* if it has **fewer equations than variables**. What can be said about the **number** of solutions of an underdetermined system?
> 
> 解：方程个数 < 未知数个数，即 $m < n$。
> - 是否有解？
>     由 $A$ 和 $\mathbf{b}$ 共同决定，**可能有解也可能无解**。
> - 有解的前提下，有唯一解/无穷多解？
>     只跟 $A$ 有关。由于 $\text{rank}\ A \le \text{min}(m,n)=m<n$，因此**若有解，则必有无穷多解**。
> 
> 例2：A system of linear equations is called *overdetermined* if it has **more equations than variables**. What can be said about the **number** of solutions of an overdetermined system?
> 
> 解：方程个数 > 未知数个数，即 $m > n$。
> - 是否有解？
>     由 $A$ 和 $\mathbf{b}$ 共同决定，**可能有解也可能无解**。
> - 有解的前提下，有唯一解/无穷多解？
>     只跟 $A$ 有关。$\text{rank}\ A=n$ 时，有**唯一解**；$\text{rank}\ A<n$ 时有**无穷多解**。

##### 有解的前提下，有唯一解/无穷多解？

> [!important] Theorem
> **线性方程组 $A\mathbf{x}=\mathbf{b}$ 有解的前提下**：
> - $\text{rank}\ A$ = ==basic variables 的个数==
> - $\text{nullity}\ A$ = ==free variables 的个数==

> 证明：设 $R$ 是 $A$ 的 RREF
> - basic variables 的个数 ==＝== $R$ 中 non-zero rows 的个数（因为 $R$ 中每个 non-zero row 都对应一个方程，每个方程都对应一个 basic variable）==＝== $\text{rank}\ A$
> - free variables 的个数 ==＝== $R$ 中 columns 的个数 - basic variables 的个数 ==＝== $R$ 中 columns 的个数 - $\text{rank}\ A$ ==＝== $\text{nullity}\ A$
> 
> ![[Pasted image 20260225182647.png|600]]

因此，在线性方程组 $A\mathbf{x}=\mathbf{b}$ 有解的前提下：
- $\text{rank}\ A=n$ 就意味着 basic variables 的数量为 $n$，也就意味着 free variable 的数量为 $0$，也就意味着方程组**有唯一解**。
- $\text{rank}\ A<n$ 就意味着 basic variables 的数量小于 $n$，也就意味着 free variable 的数量不为 $0$，也就意味着方程组**有无穷多解**。
该结论与 [[6  solution]] 中的完全一致。

##### 是否有解？

> [!important] Theorem
> 线性方程组 $A\mathbf{x}=\mathbf{b}$ **有解**
> $\iff$ 增广矩阵 $\begin{bmatrix}A & \mathbf{b}\end{bmatrix}$ 的 RREF 中不存在形如 ==$\begin{bmatrix}0 & 0 & \cdots & 0 & d\end{bmatrix}$== （$d\ne 0$）的行
> $\iff$ $\text{Rank}\ A = \text{Rank}\ \begin{bmatrix}A & \mathbf{b}\end{bmatrix}$
> 
> 线性方程组 $A\mathbf{x}=\mathbf{b}$ **无解**
> $\iff$ 增广矩阵 $\begin{bmatrix}A & \mathbf{b}\end{bmatrix}$ 的 RREF 中存在形如 ==$\begin{bmatrix}0 & 0 & \cdots & 0 & d\end{bmatrix}$== （$d\ne 0$）的行
> $\iff$ $\text{Rank}\ A \ne \text{Rank}\ \begin{bmatrix}A & \mathbf{b}\end{bmatrix}$

> 案例：
> ![[Pasted image 20260226111539.png|400]]

> 证明提示：rank = RREF 中 non-zero rows 的个数

##### 是否总是有解？

$A$ 是一个 $m\times n$ 矩阵，$A=\begin{bmatrix}\mathbf{a}_1 & \mathbf{a}_2 & \cdots & \mathbf{a}_n\end{bmatrix}$，有以下结论：

> [!important] “线性方程组 $A\mathbf{x}=\mathbf{b}$ 对任意的 $\mathbf{b}$ 都有解”的等价条件
> $\forall \mathbf{b} \in \mathbb{R}^m$，$A\mathbf{x}=\mathbf{b}$ 有解
> 
> `// 路径1`
> $\iff$ $\forall \mathbf{b} \in \mathbb{R}^m$，$\mathbf{b}$ 是 columns of $A$ 的 linear combination
> $\iff$ $\forall \mathbf{b} \in \mathbb{R}^m$，$\mathbf{b}\in \text{Span}\ \{\mathbf{a}_1,\mathbf{a}_2,\cdots,\mathbf{a}_n\}$
> $\iff$ ==$\text{Span}\ \{\mathbf{a}_1,\mathbf{a}_2,\cdots,\mathbf{a}_n\}=\mathbb{R}^m$==
> 
> `// 路径2`
> $\iff$ $\forall \mathbf{b} \in \mathbb{R}^m$，$\begin{bmatrix}A & \mathbf{b}\end{bmatrix}$ 的 RREF 中不存在形如 $\begin{bmatrix}0 & 0 & \cdots & 0 & d\end{bmatrix}$ （$d\ne 0$）的行
> $\iff$ ==$A$ 的 RREF 中没有 zero row==
> $\iff$ ==$\text{rank}\ A = m$==

> 证明：
> $\forall \mathbf{b} \in \mathbb{R}^m$，$\begin{bmatrix}A & \mathbf{b}\end{bmatrix}$ 的 RREF 中不存在形如 $\begin{bmatrix}0 & 0 & \cdots & 0 & d\end{bmatrix}$ （$d\ne 0$）的行
> $\iff$ $A$ 的 RREF 中没有 zero row
> 
> 左推右：
> - 假设 $A$ 的 RREF $R$ 中有 zero row，设该 zero row 是第 $k$ 行。
> - 现在考虑增广矩阵 $\begin{bmatrix}R & \mathbf{b}'\end{bmatrix}$，其中令 $\mathbf{b}'$ 的第 $k$ 个分量 $\ne 0$
>   则这样的 $\mathbf{b}'$ 可以使 $\begin{bmatrix}R & \mathbf{b}'\end{bmatrix}$ 的第 $k$ 行恰为 $\begin{bmatrix}0 & 0 & \cdots & 0 & d\end{bmatrix}$（$d\ne 0$）
> - 将“使 $A$ 变为 $R$ 的一系列 elementary row operation”命名为 $ERO$
>   由于“elementary row operation 可逆”和“RREF 按列分块性质”，对 $\begin{bmatrix}R & \mathbf{b}'\end{bmatrix}$ 做 $ERO$ 的逆操作，可将该矩阵变为 $\begin{bmatrix}A & \mathbf{b}\end{bmatrix}$，其中 $\begin{bmatrix}A & \mathbf{b}\end{bmatrix} \xrightarrow{RREF} \begin{bmatrix}R & \mathbf{b}'\end{bmatrix}$。于是 $\begin{bmatrix}A & \mathbf{b}\end{bmatrix}$ 的 RREF 中存在形如 $\begin{bmatrix}0 & 0 & \cdots & 0 & d\end{bmatrix}$ （$d\ne 0$）的行，与已知条件矛盾！
> 
> 右推左：设 $\begin{bmatrix}A & \mathbf{b}\end{bmatrix} \xrightarrow{RREF} \begin{bmatrix}R & \mathbf{b}'\end{bmatrix}$，由“RREF 按列分块性质”知 $R$ 正是 $A$ 的 RREF，结合原命题知 $R$ 中没有 zero row，则 $\begin{bmatrix}R & \mathbf{b}'\end{bmatrix}$ 中也没有 zero row。

> [!important] Theorem
> $\mathbb{R}^m$ 中，$m$ 个 independent 向量的 Span 等于 $\mathbb{R}^m$。

> 例如，3 维空间中，3 个 independent 向量的 Span 等于 $\mathbb{R}^3$。

> 证明：
> $\mathbb{R}^m$ 中，$m$ 个 independent 向量 $\mathbf{a}_1,\mathbf{a}_2,\cdots,\mathbf{a}_m$
> 将它们组成矩阵：$A=\begin{bmatrix}\mathbf{a}_1 & \mathbf{a}_2 & \cdots & \mathbf{a}_m\end{bmatrix}$
> 则根据 rank 的定义，$\text{rank}\ A=m$
> $\implies$ $\text{Span}\ \{\mathbf{a}_1,\mathbf{a}_2,\cdots,\mathbf{a}_m\}=\mathbb{R}^m$（前面证明过）
