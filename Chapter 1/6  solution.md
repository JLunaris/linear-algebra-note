
# Solution of System of Linear Equations

如下图所示，**给定** $A$ 和 $\mathbf{b}$，寻找所有可能的 $\mathbf{x}$ ，这个过程称为==求解线性方程组==。
![[Pasted image 20260206182936.png]]

线性方程组的解只能是以下3种情况：①无解 ②唯一解 ③无穷多解

![[Pasted image 20260207101748.png|280]]

有解的线性方程组被称为相容的(**consistent**)，无解的线性方程组被称为不相容的(**inconsistent**)。

> [!NOTE] Only Unique and Infinite?
> 如果线性方程组有解，则要么只有唯一解，要么有无穷多解。
> 
> ![[Pasted image 20260207111012.png|500]]

##### Overview

![[Pasted image 20260207111938.png]]

# Linear Combination

向量 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \in \mathbb{R}^n$，定义 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 的 **linear combination** 为形如
$$\mathbf{v}=c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k$$
的==向量==，其中 $c_1, c_2, \cdots, c_k$ 是标量，称为该 linear combination 的 **coefficient**s.

> [!tip] Tip
> 其实就是 **weighted sum**.

##### 与system of linear equations的关系

在 system of linear equations $A\mathbf{x}=\mathbf{b}$ 中：
![[Pasted image 20260207173058.png|600]]

##### 与solution of system of linear equations的关系

![[Pasted image 20260207174917.png|600]]

---

> 案例：求解线性方程组
>
> 【例1】
> ![[Pasted image 20260207180103.png|500]]
> ![[Pasted image 20260207180331.png|500]]
> 
> 【例2】
> ![[Pasted image 20260207180454.png|500]]
> ![[Pasted image 20260207182456.png|500]]
> 
>【例3】
>![[Pasted image 20260207184738.png|500]]
>![[Pasted image 20260207184917.png|500]]

> [!NOTE] Note
> 1. 若 $\mathbf{u}$ 和 $\mathbf{v}$ 是 $\mathbb{R}^2$ 空间中的任意两个不平行的向量，则 $\mathbb{R}^2$ 中的每一个向量都可以表示为 $\mathbf{u}$ 和 $\mathbf{v}$ 的线性组合。
>  ![[Pasted image 20260207185135.png|200]]
>  2. 若 $\mathbf{u}$、$\mathbf{v}$、$\mathbf{w}$ 是 $\mathbb{R}^3$ 空间中的任意三个不平行的向量，则 $\mathbb{R}^3$ 中的每一个向量都可以表示为 $\mathbf{u}$、$\mathbf{v}$、$\mathbf{w}$ 的线性组合吗？
>    答案：不一定，例如三个向量（不平行但）共面。

# Span

向量集 $S=\{\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \} \subseteq \mathbb{R}^n$，定义 $S$ 的 span 为：

$\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 的**所有** linear combination 构成的==集合==

记作 $\text{Span} \ S$ 或 $\text{Span} \ \{\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \}$.

> [!NOTE] Note
> 将span视为函数：`VectorSet span(VectorSet S)`
> - 输入一个向量集`S`，输出一个向量集
> - 功能：返回`S`中所有向量的**所有可能的 linear combination 构成的集合。**
>
> `VectorSet V = span(S)`，称：==`S` generates `V`==，==`S` 是 `V` 的一个 **generating set**==。

> 案例：求span
> 
> 【例1】$S_0=\left\{\begin{bmatrix}0 \\ 0\end{bmatrix} \right\}$
>  $\text{Span}\ S_0=\left\{\begin{bmatrix}0 \\ 0\end{bmatrix} \right\}$
>
> 【例2】$S_1=\left\{\begin{bmatrix}1 \\ -1\end{bmatrix} \right\}$
> ![[Pasted image 20260208115250.png|200]]

> [!NOTE] Note
> 如果向量集 $S$ 中有非零向量，则 $\text{Span}\ S$ 中必有无穷多的向量。

> 【例3】
> ![[Pasted image 20260208120049.png|500]]
>
> 【例4】
> ![[Pasted image 20260208122128.png|550]]

##### 与solution of system of linear equations的关系

![[Pasted image 20260208122948.png]]

> [!summary] Summary
> 线性方程组 $A \vec{x} = \vec{b}$ 是否有解（线性方程组 $x_1 \vec{a_1} + x_2 \vec{a_2} + \cdots + x_n \vec{a_n} = \vec{b}$ 是否有解）
> $\iff$ $\vec{b}$ 是不是 $\vec{a_1}, \vec{a_2}, \cdots, \vec{a_n}$ 的线性组合
> $\iff$ $\vec{b}$ 是否 $\in \text{Span}\ \{\vec{a_1}, \vec{a_2}, \cdots, \vec{a_n}\}$

##### Span冗余向量

> 案例：冗余的向量
> ![[Pasted image 20260209123731.png|500]]

> [!important] Theorem
> ![[Pasted image 20260209110717.png|580]]

> 证明：
> 【左推右】
> $\vec{v} =b_1 \vec{u_1} + b_2 \vec{u_2} + \cdots + b_k \vec{u_k}$
> 
> $\begin{aligned}\forall \vec{z}\in \text{Span}\ \{\vec{u_1}, \vec{u_2}, \cdots, \vec{u_k}, \vec{v} \},\ \vec{z}&=c_1 \vec{u_1} + c_2 \vec{u_2} +\cdots+c_k \vec{u_k}+c\vec{v} \\ &=c_1 \vec{u_1} + c_2 \vec{u_2} +\cdots+c_k \vec{u_k}+c(b_1 \vec{u_1} + b_2 \vec{u_2} + \cdots + b_k \vec{u_k}) \\ &=(c_1+cb_1)\vec{u_1}+(c_2+cb_2)\vec{u_2}+\cdots+(c_k+cb_k)\vec{u_k} \\ &\in \text{Span}\ S \end{aligned}$
> 
> $\begin{aligned}\forall \vec{z}\in \text{Span}\ S,\ \vec{z}&=c_1 \vec{u_1} + c_2 \vec{u_2} +\cdots+c_k \vec{u_k}\\ &=c_1 \vec{u_1} + c_2 \vec{u_2} +\cdots+c_k \vec{u_k}+0\vec{v}\\ &\in \text{Span}\ \{\vec{u_1}, \vec{u_2}, \cdots, \vec{u_k}, \vec{v} \}\end{aligned}$
>  
> 【右推左】
> $\vec{v} = 0\vec{u_1} + 0\vec{u_2} + \cdots + 0\vec{u_k} + \vec{v} \in \text{Span}\ \{\vec{u_1}, \vec{u_2}, \cdots, \vec{u_k}, \vec{v} \}=\text{Span}\ S$

> [!summary] Summary
> ![[Pasted image 20260402173817.png]]
> - $\mathbf{v}$ 是 $\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k$ 的线性组合 $\iff$ $\mathbf{v}\in\text{Span}\ S$ $\iff$ $\mathbf{v}$ 的加入不会使 span 范围扩大
> - $\mathbf{v}$ 不能由 $\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k$ 线性表出 $\iff$ $\mathbf{v}\notin\text{Span}\ S$ $\iff$ $\mathbf{v}$ 的加入会使 span 范围扩大

---

> [!NOTE] 两集合相等的充要条件
> 集合 $A=B$ 的充要条件：$\forall x\in A, x\in B$ 且 $\forall x\in B, x\in A$ 
> ![[Pasted image 20260209115730.png|70]]

> 案例：证明Span之间的关系
> 
> 【例1】$S_1$、$S_2$ 是 $\mathbb{R}^n$ 的有限子集，$S_1 \subseteq S_2$，求证 $\text{Span}\ S_1 \subseteq \text{Span}\ S_2$ .
> 
> 证明：只要证 $\forall \mathbf{z}\in \text{Span}\ S_1, \mathbf{z}\in \text{Span}\ S_2$.
> 令 $S_1=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}$, $S_2=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_m\}$, $m\ge k$.
   $\begin{aligned}\forall \mathbf{z}\in \text{Span}\ S_1, \mathbf{z}&=c_1 \mathbf{u}_1+c_2 \mathbf{u}_2+\cdots+c_k \mathbf{u}_k\\ &=c_1 \mathbf{u}_1+c_2 \mathbf{u}_2+\cdots+c_k \mathbf{u}_k+0\mathbf{u}_{k+1}+0\mathbf{u}_{k+2}+\cdots+0\mathbf{u}_{m}\\ &\in\text{Span}\ S_2\end{aligned}$
>
> 【例2】$\mathbf{u}$、$\mathbf{v}$ $\in\mathbb{R}^n$，求证 $\text{Span} \ \{\mathbf{u}, \mathbf{v}\}=\text{Span} \ \{\mathbf{u}+\mathbf{v}, \mathbf{u}-\mathbf{v}\}$ .
> 
> 证明：
> ![[Pasted image 20260209155948.png|600]]
> 
> 【例3】$\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \in \mathbb{R}^n$ 且 $c_1, c_2, \cdots, c_k$ 是**非零**标量。
> 求证：$\text{Span} \ \{\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k\}=\text{Span} \ \{c_1\mathbf{u}_1, c_2\mathbf{u}_2, \cdots, c_k\mathbf{u}_k\}$ .
> 
> 证明：方法同例2。
> 
> 【例4】$\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \in \mathbb{R}^n$ 且 $c$ 是标量。
> 求证：$\text{Span} \ \{\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k\}=\text{Span} \ \{\mathbf{u}_1+c\mathbf{u}_2, \mathbf{u}_2, \cdots, \mathbf{u}_k\}$ .
> 
> 证明：方法同例2。
> 
> 【例5】设矩阵 $B$ 是通过对矩阵 $A$ 进行**一次elementary row operation**得到的。
> 求证：$\text{Span}\ \{B\ \text{的各行}\}=\text{Span}\ \{A\ \text{的各行}\}$.
> 
> 证明：elementary row operation 包含3种情况：
> ① Interchange：显然不改变 span.
> ② Scaling：例3已经证明.
> ③ Row Addition：例4已经证明.
> 
> 【例6】Prove that every linear combination of the **rows of A** can be written as a linear combination of the **rows of the reduced row echelon form of A**.
> 
> 证明：原命题等价于 $\text{Span}\ \{\text{rows of }A\}=\text{Span}\ \{\text{rows of the reduced row echelon form of }A\}$.
> 矩阵 $A$ 经过多次elementary row operation得到其最简行阶梯形式 $R$，由于每次elementary row operation都不会改变 $\text{Span}\ \{\text{各行}\}$ （例5已经证明），因此原命题成立。

# Linearly Dependent / Linearly Independent

向量 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \in \mathbb{R}^n$，若存在**不全为零**的标量 $c_1,c_2,\cdots,c_k$ ，使
$$c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}\text{，}$$
则称 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 线性依赖（==linearly dependent==），否则（即**只有 $c_1,c_2,\cdots,c_k$ 全为零**能使等式成立）称 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 线性独立（==linearly independent==）。

> [!tip] 
> 找得到一组**不全为零**的 $c_1,c_2,\cdots,c_k$ 使 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$ 成立，就可以找到**无穷多组**（给这组解乘上任意常数 $\lambda$ 即可获得一组新的解）。

换句话说，对于方程 $x_1\mathbf{u}_1+x_2\mathbf{u}_2+\cdots+x_k\mathbf{u}_k=\mathbf{0}$：
- 若**存在不全为零的解**，则称 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ **线性依赖**；
- 若**只有全为零的解**，则称 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ **线性独立**。

另一种表述形式：**向量集**线性依赖/线性独立，指的是**向量集中的所有向量**线性依赖/线性独立。

> 案例：判断向量组是linearly dependent还是linearly independent
> 
> 【例1】
> ![[Pasted image 20260210161138.png|500]]
> 
> 【例2】
> ![[Pasted image 20260210161222.png|500]]

> [!NOTE] 
> 包含**零向量**的向量组一定**线性依赖**。

##### Dependent=存在Span冗余向量；Independent=没有Span冗余向量

> [!important] Theorem
> 向量个数 $k > 1$ 的前提下：
>  ![[Pasted image 20260210184416.png]]
> 
>  向量个数 $k=1$ 时（trivial）：$\{\mathbf{u}\}$ dependent $\iff$ $\mathbf{u}=\mathbf{0}$ .

> 证明：
> 【左推右】
> 存在 $c_1, c_2, \cdots, c_k$ 不全为 $0$，使 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$
> 不妨设 $c_i\neq 0$，有 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=-c_i\mathbf{u}_i$ （等式左边没有 $c_i\mathbf{u}_i$）
> 则 $\cfrac{c_1}{-c_i}\mathbf{u}_1+\cfrac{c_2}{-c_i}\mathbf{u}_2+\cdots+\cfrac{c_k}{-c_i}\mathbf{u}_k=\mathbf{u}_i$
> 知 $\mathbf{u}_i$ 是其他向量的线性组合.
> 
> 【右推左】
> $\mathbf{u}_i=c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k$（等式右边没有 $c_i\mathbf{u}_i$）
> 则 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+(-1)\mathbf{u}_i+\cdots+c_k\mathbf{u}_k=\mathbf{0}$
> 知 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 线性依赖.

> [!summary] 
> 向量个数 $k > 1$ 时：
>  - $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ dependent $\iff$ $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 中存在Span冗余向量
>  - $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ independent $\iff$ $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 中没有Span冗余向量
>
> 向量个数 $k = 1$ 时：
>  - $\{\mathbf{u}\}$ dependent $\iff$ $\mathbf{u}=\mathbf{0}$
>  - $\{\mathbf{u}\}$ independent $\iff$ $\mathbf{u}\neq \mathbf{0}$

##### 与solution of system of linear equations的关系

> [!important] Theorem
> 线性方程组 $A\mathbf{x}=\mathbf{b}$，其中 $A=\begin{bmatrix}\mathbf{a}_1 & \mathbf{a}_2 & \cdots & \mathbf{a}_n\end{bmatrix}$
> 
> ![[Pasted image 20260211110855.png|450]]

> 命题1的证明：
> 【左推右】
> 存在 $c_1, c_2, \cdots, c_n$ 不全为 $0$，使 $c_1\mathbf{a}_1+c_2\mathbf{a}_2+\cdots+c_n\mathbf{a}_n=\mathbf{0}$
> 设 $A\mathbf{x}=\mathbf{b}$ 的一个解为 $\mathbf{x}_1=\begin{bmatrix}d_1 \\ d_2 \\ \vdots \\ d_n\end{bmatrix}$，则 $d_1\mathbf{a}_1+d_2\mathbf{a}_2+\cdots+d_n\mathbf{a}_n=\mathbf{b}$
> 则有 $(c_1+d_1)\mathbf{a}_1+(c_2+d_2)\mathbf{a}_2+\cdots+(c_n+d_n)\mathbf{a}_n=\mathbf{b}$
> 由于 $c_1, c_2, \cdots, c_n$ 不全为 $0$，因此又找到一个解：$\mathbf{x}_2=\begin{bmatrix}c_1+d_1 \\ c_2+d_2 \\ \vdots \\ c_n+d_n\end{bmatrix} \ne \mathbf{x}_1$
> 一旦找到两个解，就可以找到无穷多解（见本节“Only Unique and Infinite?”）.
> 
> 【右推左】
> 取 $A\mathbf{x}=\mathbf{b}$ 的两个解 $\mathbf{x}_1=\begin{bmatrix}c_1 \\ c_2 \\ \vdots \\ c_n\end{bmatrix}$，$\mathbf{x}_2=\begin{bmatrix}d_1 \\ d_2 \\ \vdots \\ d_n\end{bmatrix}$，且 $\mathbf{x}_1 \ne \mathbf{x}_2$.
> 则    $c_1\mathbf{a}_1+c_2\mathbf{a}_2+\cdots+c_n\mathbf{a}_n=\mathbf{b}$
>     $d_1\mathbf{a}_1+d_2\mathbf{a}_2+\cdots+d_n\mathbf{a}_n=\mathbf{b}$
> 则有 $(c_1-d_1)\mathbf{a}_1+(c_2-d_2)\mathbf{a}_2+\cdots+(c_n-d_n)\mathbf{a}_n=\mathbf{0}$
> 由 $\mathbf{x}_1 \ne \mathbf{x}_2$ 知 $c_i-d_i$（$i=1,2,\cdots,n$）不全为 $0$
> 故 $\mathbf{a}_1,\mathbf{a}_2,\cdots,\mathbf{a}_n$ dependent.

> 命题2的证明：
> 
> 在 $A\mathbf{x}=\mathbf{b}$ 有解的前提下，解的情况只有两种：唯一解、无穷多解。
> 因此：
>     -「dependent」与「independent」互为否定
>     -「无穷多解」与「唯一解」互为否定
> 因此，**对命题1两边取否定，等价关系仍然成立**。

> [!important] 推论
> 方程 $A\mathbf{x}=\mathbf{b}$ **最多有 1 解** $\iff$ $A$ 的 columns 是 independent 的

> 证明：
> - 左推右：有解的前提下，方程 $A\mathbf{x}=\mathbf{b}$ 有唯一解 $\implies$ $A$ 的 columns 是 independent 的
> - 右推左：$A$ 的 columns 是 independent 的 $\implies$ 有解时必有唯一解 $\implies$ 最多有 1 解

---

> [!NOTE] homogeneous system of linear equations
> 线性方程组 $A\mathbf{x}=\mathbf{b}$ 在 $\mathbf{b}=\mathbf{0}$ 时被称为 **homogeneous**（齐次的），否则被称为 **nonhomogeneous**（非齐次的）。
> 
> 性质：齐次线性方程组总是有 $\mathbf{x}=\mathbf{0}$ 作为它的一个解。

> [!important] 推论 for 齐次线性方程组
> - 方程 $A\mathbf{x}=\mathbf{0}$ 有**唯一解** ($\mathbf{x}=\mathbf{0}$) $\iff$ $A$ 的 columns 是 independent 的
> - 方程 $A\mathbf{x}=\mathbf{0}$ 有**无穷多解** $\iff$ $A$ 的 columns 是 dependent 的

---

> 案例：证明向量组 dependent/independent
> 
> 【例1】$\mathbb{R}^n$ 中，向量 $\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k$ independent，向量 $\mathbf{v}=c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k$，$c_1\ne 0$.
> 求证：$\mathbf{v},\mathbf{u}_2,\cdots,\mathbf{u}_k$ independent.
> 
> 证明：只要证 $a_1\mathbf{v}+a_2\mathbf{u}_2+\cdots+a_k\mathbf{u}_k=\mathbf{0}$ 的唯一解是 $a_1=a_2=\cdots=a_k=0$
> 接下来开始解方程.
> 原方程 $\iff$ $a_1(c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k)+a_2\mathbf{u}_2+\cdots+a_k\mathbf{u}_k=\mathbf{0}$
> $\iff$ $(a_1c_1)\mathbf{u}_1+(a_1c_2+a_2)\mathbf{u}_2+\cdots+(a_1c_k+a_k)\mathbf{u}_k=\mathbf{0}$
> 由 $\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k$ independent 知：原方程 $\iff$ $a_1c_1=a_1c_2+a_2=\cdots=a_1c_k+a_k=0$
> 考虑到 $c_1\ne 0$，解得 $a_1=a_2=\cdots=a_k=0$
> 
> 【例2】$\mathbb{R}^n$ 中，向量 $\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k$ independent，$c_1,c_2,\cdots,c_k$ 均为非零标量.
> 求证：$c_1\mathbf{u}_1,c_2\mathbf{u}_2,\cdots,c_k\mathbf{u}_k$ independent.
> 
> 证明：只要证 $d_1(c_1\mathbf{u}_1)+d_2(c_2\mathbf{u}_2)+\cdots+d_k(c_k\mathbf{u}_k)=\mathbf{0}$ 的唯一解是 $d_1=d_2=\cdots=d_k=0$
> 接下来开始解方程.
> 原方程 $\iff$ $(d_1c_1)\mathbf{u}_1+(d_2c_2)\mathbf{u}_2+\cdots+(d_kc_k)\mathbf{u}_k=\mathbf{0}$
> 由 $\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k$ independent 知：原方程 $\iff$ $d_1c_1=d_2c_2=\cdots=d_kc_k=0$
> 考虑到 $c_1,c_2,\cdots,c_k$ 均为非零标量，解得 $d_1=d_2=\cdots=d_k=0$
> 
> 【例3】$S=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}\subseteq\mathbb{R}^n$
> 求证：$S$ independent $\iff$ $\text{Span}\ S$ 中的任一向量写为 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k$ 的形式时，这组 $c_1,c_2,\cdots,c_k$ 是唯一的。
> 
> 证明：
> **左推右**：
> 任取 $\mathbf{v}\in \text{Span}\ S$，假设 $\mathbf{v}$ 有多种表示，任取其中两种：
> ① $\mathbf{v}=a_1\mathbf{u}_1+a_2\mathbf{u}_2+\cdots+a_k\mathbf{u}_k$
> ② $\mathbf{v}=b_1\mathbf{u}_1+b_2\mathbf{u}_2+\cdots+b_k\mathbf{u}_k$
> 其中 $\mathbf{a}=\begin{bmatrix}a_1 \\ a_2 \\ \vdots \\ a_k\end{bmatrix}$，$\mathbf{b}=\begin{bmatrix}b_1 \\ b_2 \\ \vdots \\ b_k\end{bmatrix}$, $\mathbf{a}\ne\mathbf{b}$ .
> ①-②得：$\mathbf{0}=(a_1-b_1)\mathbf{u}_1+(a_2-b_2)\mathbf{u}_2+\cdots+(a_k-b_k)\mathbf{u}_k$
> 由 $\mathbf{a}=\mathbf{b}$ 知 $a_i-b_i$ 不全为0
> 则 $\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k$ dependent，与已知条件矛盾！
> **右推左**：
> 只要证 $a_1\mathbf{u}_1+a_2\mathbf{u}_2+\cdots+a_k\mathbf{u}_k=\mathbf{0}$ 的唯一解是 $a_1=a_2=\cdots=a_k=0$
> 已知 $\forall \mathbf{v}\in \text{Span}\ S$，$\mathbf{v}=c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k$ 中 $c_1,c_2,\cdots,c_k$ 唯一
> $\mathbf{0}\in \text{Span}\ S$，故 $\mathbf{0}=c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k$ 中 $c_1,c_2,\cdots,c_k$ 唯一
> 显然 $c_1=c_2=\cdots=c_k=0$ 是方程的解
> 因此方程 $a_1\mathbf{u}_1+a_2\mathbf{u}_2+\cdots+a_k\mathbf{u}_k=\mathbf{0}$ 的唯一解是 $a_1=a_2=\cdots=a_k=0$
> 
> 【例4】$S=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}\subseteq\mathbb{R}^n$，$A$ 是 $m\times n$ 矩阵
> 求证：$S$ dependent $\implies$ $S'=\{A\mathbf{u}_1,A\mathbf{u}_2,\cdots,A\mathbf{u}_k\}$ dependent
> 
> 证明：$c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$，其中 $c_1,c_2,\cdots,c_k$ 不全为 $0$
> 两边同乘 $A$ 得：$A(c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k)=A\mathbf{0}=\mathbf{0}$
> 即 $A(c_1\mathbf{u}_1)+A(c_2\mathbf{u}_2)+\cdots+A(c_k\mathbf{u}_k)=\mathbf{0}$
> 即 $c_1(A\mathbf{u}_1)+c_2(A\mathbf{u}_2)+\cdots+c_k(A\mathbf{u}_k)=\mathbf{0}$，其中 $c_1,c_2,\cdots,c_k$ 不全为 $0$
> 故 $S'$ dependent.
> 
> 【例5】分析：如果例4中的 dependent 改为 independent，则命题是否成立？
> 
> 解：命题成立 $\iff$ $c_1(A\mathbf{u}_1)+c_2(A\mathbf{u}_2)+\cdots+c_k(A\mathbf{u}_k)=\mathbf{0}$ 的唯一解是 $c_1=c_2=\cdots=c_k=0$。
> 也就是说，要使命题成立，等价于使“原方程 $\iff$ $c_1=c_2=\cdots=c_k=0$”成立。
> - 正着推：$c_1(A\mathbf{u}_1)+c_2(A\mathbf{u}_2)+\cdots+c_k(A\mathbf{u}_k)=\mathbf{0}$ $\iff$ $A(c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k)=\mathbf{0}$
> - 逆着推：$c_1=c_2=\cdots=c_k=0$ $\iff$ $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$ （由 $S$ independent 知）
> 但 $A(c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k)=\mathbf{0}$ 不等价于 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$，因此命题不成立。
> 当且仅当“$A$ 的 columns 是 independent 的”时，上一行的命题才能等价，命题才成立。

# Rank / Nullity

$A$ 是一个 $m\times n$ 矩阵，矩阵中最多能选出多少个**列向量**构成 independent 向量组，这个个数称为矩阵的 ==rank==。记作 $\text{rank}\ A$。

矩阵的 ==nullity== 定义为：$n-\text{rank}\ A$。记作 $\text{nullity}\ A$。

![[Pasted image 20260213143024.png|500]]

> 例：求矩阵的 rank 和 nullity
> 
> 【例1】
> ![[Pasted image 20260213145222.png|550]]
> 最原始的做法：穷举所有可能（每个列选或不选，不能都不选，因此共 $2^n-1$ 种），依次判断是否为 independent 向量组。
> 
> 【例2】$A=\begin{bmatrix}1 & 3 & 4 \\ 2 & 6 & 8\end{bmatrix}$
> 
> 答：$\text{rank}\ A=1$，$\text{nullity}\ A=2$
> 
> 【例3】$A=\begin{bmatrix}0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0\end{bmatrix}$
> 
> 答：$\text{rank}\ A=0$，$\text{nullity}\ A=3$
> 
> 【例4】$A=\begin{bmatrix}0 & 3 \\ 0 & 5\end{bmatrix}$
> 
> 答：$\text{rank}\ A=1$，$\text{nullity}\ A=1$
> 
> 【例5】$A=\begin{bmatrix}5\\2\end{bmatrix}$
> 
> 答：$\text{rank}\ A=1$，$\text{nullity}\ A=0$

##### rank A = n 等价于 A 的列 independent；rank A < n 等价于 A 的列 dependent

> [!important] Theorem
> $A$ 是一个 $m\times n$ 矩阵，有以下等价关系：
> ![[Pasted image 20260213153617.png|400]]

##### 与solution of system of linear equations的关系
![[Pasted image 20260213154406.png]]

# Finding Solutions

### 原理

- 若两个线性方程组的解集完全相同，则称这两个线性方程组是**等价的**（equivalent）。

  ![[Pasted image 20260213175001.png|500]]

- 对线性方程组做以下三种操作，所得方程组与原方程组等价（即==不会改变原方程组的解集==）：
  ![[Pasted image 20260213175930.png|500]]

- Strategy of Finding Solutions
  通过对线性方程组做等价变换（前面提到的三种操作），直至得到一个足够简单的等价方程组，简单到可以一眼看出解集。
  ![[Pasted image 20260214103943.png|500]]

### Coefficient Matrix 和 Augmented Matrix

![[Pasted image 20260214093954.png|550]]

### Elementary Row Operation

前面提到，对线性方程组做三种操作，不会改变线性方程组的解集。
而每个线性方程组都可写作 augmented matrix。
因此，对 augmented matrix 做以下三种操作，不会改变 augmented matrix 对应的线性方程组的解集：
> [!important] Elementary Row Operation
> 对矩阵做下列三种操作中的任意一种，称为一次 elementary row operation：
> 
> ![[Pasted image 20260214100802.png|500]]

> [!NOTE] 
> interchange 的本质是**行顺序可自由调整**。因为线性方程组中方程的顺序不影响解集，所以对应 augmented matrix 的行顺序可自由调整。
> 
> 任何复杂的行顺序重排，都可以分解为若干次 interchange 操作。

### Strategy of Finding Solutions

① 将线性方程组写作 augmented matrix $A'$
② 对 $A'$ 做一系列 elementary row operation，直到它足够简单（假设为 $R$）
③ 把 $R$ 还原回线性方程组 $R'\mathbf{x}=\mathbf{b}'$，该方程组简单到可以一眼看出它的解集。

![[Pasted image 20260214110004.png|600]]

> [!question] 什么样的 augmented matrix “足够简单”？
> 当 augmented matrix 是 RREF 时，我们说它“足够简单”。

> 案例：
> ![[Pasted image 20260214104201.png|450]]

### RREF

A system of linear equations is ==easily solvable== if its augmented matrix is in **reduced row echelon form**.

> [!important] Row Echelon Form (REF)
> ![[Pasted image 20260214112146.png|500]]
> 
> 名词解释：若矩阵的一行中所有元素均为 $0$，则称该行为 **zero row**（零行）；否则称为 **nonzero row**（非零行）。非零行中最左边的非零元素称为该行的 **leading entry**。
> 
> **in echelon form**：每个非零行的 leading entry 都位于其上一行的 leading entry 的右侧。

> [!important] Reduced Row Echelon Form (RREF)
> ![[Pasted image 20260214123036.png|500]]

> [!important] Pivot Position / Pivot Column
> $R$ 是矩阵 $A$ 的 reduced row echelon form，把 $R$ 的所有 leading entry 所在的位置对应回原来的矩阵 $A$，这些位置就是矩阵 $A$ 的 **pivot position**。pivot position 所在的列就是矩阵 $A$ 的 **pivot column**。
> 
> ![[Pasted image 20260214124119.png|500]]

##### RREF is unique

一个矩阵可以通过一系列 elementary row operation 变为多个不同的 REF，但只能变为唯一的 RREF。（not going to proof）
![[Pasted image 20260214155425.png|600]]

> [!NOTE] 
> 任何矩阵都可以通过一系列 elementary row operation 变为 RREF，并且这个 RREF 是唯一的。

##### RREF 按列分块

> [!important] Theorem
> 把 RREF 竖着切成两块，**左半块**仍然是 RREF，且正是**原矩阵对应左半块的 RREF**。
> 
> ![[Pasted image 20260220120922.png|600]]

> 证明：（“把 RREF 竖着切成两块，左半块仍然是 RREF” is trivial，不做严格证明，只证“且正是原矩阵对应左半块的 RREF”）
> 
> ![[Pasted image 20260220123437.png|500]]
> 对 $\begin{bmatrix}A_1\ |\ A_2\end{bmatrix}$ 做一系列 elementary row operation 时，都是同时作用在 $A_1$ 和 $A_2$ 上
> 	知：$A_1$ 经过一系列 elementary row operation 变为了 $R_1$     ......①
> 把 RREF 竖着切成两块，左半块仍然是 RREF
> 	知：$R_1$ 是 RREF     ......②
> RREF 是唯一的     ......③
> 由①②③知：$R_1$ 正是 $A_1$ 的 RREF

##### 与solution of system of linear equations的关系

![[Pasted image 20260214164116.png|500]]

---

![[Pasted image 20260214172722.png|580]]

方程组有无穷多解时，无法为每一个变量都找到唯一的取值，可以将其中一些变量（称为 **basic variable**）用其余变量（称为 **free variable**）来表示。

通常把方程组中==最左侧的变量==（图中紫色方框所示，即 ==RREF 的 leading entry 对应的变量==）保留在等号左边，作为 basic variable；其他变量移到等号右边，作为 free variable。

不过还有其他的表示形式（例如选 $x_2,x_3,x_5$ 作为 basic variable，$x_1,x_4$ 作为 free variable），方程组解集的 parametric representation **可能**有多种，它们都是等价的。

---

![[Pasted image 20260214184250.png|550]]

##### 将矩阵化为RREF

![[Pasted image 20260215105356.png|600]]

先化为 REF（整个过程都可以在适当的时候做 ==scaling==）：
1. 最左侧的非零列一定是 pivot column，该列的最上方一定是 pivot position。期待该 pivot position 是非零值，如果不是，使用 ==interchange== 以将非零值挪到这里。最好选择列内其他数值的公因子（如果有 $1$ 是最好的），以便后续“消去非零值”的操作。
   ![[Pasted image 20260215124420.png|650]]
2. 期待 pivot position 的下方全为 $0$ 。如果不是，==从上往下做 row addition== 以消去非零值。
   ![[Pasted image 20260215125329.png|650]]
3. 忽略包含该 pivot position 的行及其上方的所有行，对剩余的子矩阵重复步骤1和2。
   ![[Pasted image 20260215125532.png|300]]

再化为 RREF：
1. 期待 pivot position 是 $1$。如果不是，使用 ==scaling==。
2. 期待 pivot position 上方全为 $0$。如果不是，==从下往上做 row addition== 以消去非零值。
