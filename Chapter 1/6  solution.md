
# 求解system of linear equations

如下图所示，**给定** $A$ 和 $\mathbf{b}$，寻找所有可能的 $\mathbf{x}$ ，这个过程称为==求解线性方程组==。
![[Pasted image 20260206182936.png]]

线性方程组的解只能是以下3种情况：①无解 ②唯一解 ③无穷多解

![[Pasted image 20260207101748.png|280]]

有解的线性方程组被称为相容的(**consistent**)，无解的线性方程组被称为不相容的(**inconsistent**)。

> [!NOTE] Only Unique and Infinite?
> 如果线性方程组有解，则要么只有唯一解，要么有无穷多解。
> 
> ![[Pasted image 20260207111012.png|500]]

# Overview

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

##### 与求解system of linear equations的关系

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
> `VectorSet V = span(S)`，称”`S` ==generates== `V`“。

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

##### 与求解system of linear equations的关系

![[Pasted image 20260208122948.png]]

> [!summary] Summary
> 线性方程组 $A \vec{x} = \vec{b}$ 是否有解（线性方程组 $x_1 \vec{a_1} + x_2 \vec{a_2} + \cdots + x_n \vec{a_n} = \vec{b}$ 是否有解）
> $\iff$ $\vec{b}$ 是不是 $\vec{a_1}, \vec{a_2}, \cdots, \vec{a_n}$ 的线性组合
> $\iff$ $\vec{b}$ 是否 $\in \text{Span}\ \{\vec{a_1}, \vec{a_2}, \cdots, \vec{a_n}\}$

##### Span冗余向量

> 案例：冗余的向量
> ![[Pasted image 20260209123731.png|500]]

> [!important] Theorem
> ![[Pasted image 20260209110717.png|600]]

> 证明：
> 【左推右】
>   $\vec{v} =b_1 \vec{u_1} + b_2 \vec{u_2} + \cdots + b_k \vec{u_k}$
> 
> $\begin{aligned}\forall \vec{z}\in \text{Span}\ \{\vec{u_1}, \vec{u_2}, \cdots, \vec{u_k}, \vec{v} \},\ \vec{z}&=c_1 \vec{u_1} + c_2 \vec{u_2} +\cdots+c_k \vec{u_k}+c\vec{v} \\ &=c_1 \vec{u_1} + c_2 \vec{u_2} +\cdots+c_k \vec{u_k}+c(b_1 \vec{u_1} + b_2 \vec{u_2} + \cdots + b_k \vec{u_k}) \\ &=(c_1+cb_1)\vec{u_1}+(c_2+cb_2)\vec{u_2}+\cdots+(c_k+cb_k)\vec{u_k} \\ &\in \text{Span}\ S \end{aligned}$
> 
>  $\begin{aligned}\forall \vec{z}\in \text{Span}\ S,\ \vec{z}&=c_1 \vec{u_1} + c_2 \vec{u_2} +\cdots+c_k \vec{u_k}\\ &=c_1 \vec{u_1} + c_2 \vec{u_2} +\cdots+c_k \vec{u_k}+0\vec{v}\\ &\in \text{Span}\ \{\vec{u_1}, \vec{u_2}, \cdots, \vec{u_k}, \vec{v} \}\end{aligned}$
>  
> 【右推左】
>   $\vec{v} = 0\vec{u_1} + 0\vec{u_2} + \cdots + 0\vec{u_k} + \vec{v} \in \text{Span}\ \{\vec{u_1}, \vec{u_2}, \cdots, \vec{u_k}, \vec{v} \}=\text{Span}\ S$

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
> 【例3】$\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \in \mathbb{R}^n$ 且 $c_1, c_2, \cdots, c_k$ 是**非零**标量，求证 $\text{Span} \ \{\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k\}=\text{Span} \ \{c_1\mathbf{u}_1, c_2\mathbf{u}_2, \cdots, c_k\mathbf{u}_k\}$ .
> 
> 证明：方法同例2。
> 
> 【例4】$\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k \in \mathbb{R}^n$ 且 $c$ 是标量，求证 $\text{Span} \ \{\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k\}=\text{Span} \ \{\mathbf{u}_1+c\mathbf{u}_2, \mathbf{u}_2, \cdots, \mathbf{u}_k\}$ .
> 
> 证明：方法同例2。
> 
> 【例5】设矩阵 $B$ 是通过对矩阵 $A$ 进行**一次elementary row operation**得到的。求证 $\text{Span}\ \{B\ \text{的各行}\}=\text{Span}\ \{A\ \text{的各行}\}$.
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
则称 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 线性相关（==linearly dependent==），否则称 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 线性无关（==linearly independent==）。

换句话说，若方程 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$ 的**唯一解**是 $c_1=c_2=\cdots=c_k=0$，则称 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ **线性无关**。

> [!tip] 
> 找得到一组**不全为零**的 $c_1,c_2,\cdots,c_k$ 使 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$ 成立，就可以找到**无穷多组**（给这组解乘上任意常数 $\lambda$ 即可获得一组新的解）。

另一种表述形式：**向量集**线性相关/线性无关，指的是**向量集中的所有向量**线性相关/线性无关。

> 案例：判断向量组是linearly dependent还是linearly independent
> 
> 【例1】
> ![[Pasted image 20260210161138.png|500]]
> 
> 【例2】
> ![[Pasted image 20260210161222.png|500]]

> [!NOTE] 
> 任何包含**零向量**的向量组都是**线性相关**的。

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
> 知 $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 线性相关.

> [!summary] 
> 向量个数 $k > 1$ 时：
>  - $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ dependent $\iff$ $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 中存在Span冗余向量
>  - $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ independent $\iff$ $\mathbf{u}_1, \mathbf{u}_2, \cdots, \mathbf{u}_k$ 中没有Span冗余向量
>
> 向量个数 $k = 1$ 时：
>  - $\{\mathbf{u}\}$ dependent $\iff$ $\mathbf{u}=\mathbf{0}$
>  - $\{\mathbf{u}\}$ independent $\iff$ $\mathbf{u}\neq \mathbf{0}$

##### 与求解system of linear equations的关系

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
> 因此，**对命题1取否定，等价关系仍然成立**。

> [!NOTE] homogeneous system of linear equations
> 线性方程组 $A\mathbf{x}=\mathbf{b}$ 在 $\mathbf{b}=\mathbf{0}$ 时被称为 **homogeneous**（齐次的），否则被称为 **nonhomogeneous**（非齐次的）。
> 
> 性质：齐次线性方程组总是有 $\mathbf{x}=\mathbf{0}$ 作为它的一个解。

# Rank / Nullity





