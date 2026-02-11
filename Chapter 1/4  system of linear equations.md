# System of Linear Equations

![[Pasted image 20260204124325.png|500]]

##### System of Linear Equations是一个Linear System

==把`n`维向量 $(x_1,\dots,x_n)$ 当作输入，把`m`维向量 $(b_1,\dots,b_m)$ 当作输出==，则它是一个Linear System。

![[Pasted image 20260204163243.png|350]]

证明：trivial，很容易证明它满足Linear System的两大特征。

##### 所有的Linear System都可以写为System of Linear Equations

若输入为`n`维向量 $(x_1,\dots,x_n)$，输出为`m`维向量 $(b_1,\dots,b_m)$，则它可以写为System of Linear Equations。

证明：

①将单位向量依次输入Linear System，将输出结果记作 $a_{ij}$ .
![[Pasted image 20260204174354.png]]
> 这一步确定了系统在每个独立“维度”上的基本行为。

> [!NOTE] Note
> ![[Pasted image 20260204183337.png]]
> **单位向量**（unit vector）：只有一个分量是`1`，其他分量都是`0`。
> 记作 $\mathbf{e}_i$，其中`i`表示第几个数值是`0`。

②利用Linear System的**齐次性**进行缩放：例如输入乘上 $x_1$，则输出也会乘上 $x_1$.
![[Pasted image 20260204181816.png]]

③利用Linear System的**叠加性**组合成方程组：红框部分相加得到红框，绿框部分相加得到绿框.
![[Pasted image 20260204182555.png]]

##### System of Linear Equations可以写为Matrix-Vector Product的形式

![[Pasted image 20260205174936.png]]

> [!important] Note
> 每个矩阵都表示了一个 Linear System.

# Matrix-Vector Product

![[Pasted image 20260205161050.png|400]]
要使矩阵 $A$ 与向量 $\mathbf{x}$ 能够相乘（$A\mathbf{x}$），必须满足前提：==矩阵 $A$ 的列数=向量 $\mathbf{x}$ 的行数==。

##### 行观点：Inner Product with Row

矩阵 $A$ 的**每一行**分别与**向量 $\mathbf{x}$** 做内积。
![[Pasted image 20260205163216.png|500]]

> 【例】
> ![[Pasted image 20260205164757.png|200]]
> 则 $A\mathbf{x}=\begin{bmatrix}2\times 4 & 3\times 1 & 1\times3 \\ 1\times 4 & 5\times 1 & 3 \times 3\end{bmatrix}$

##### 列观点：Weighted sum of Columns

矩阵 $A$ 的**每一列**分别与**向量 $\mathbf{x}$ 的对应分量**相乘，做 weighted sum.

![[Pasted image 20260205170054.png|500]]

# Properties of Matrix-Vector Product

> [!important] 性质
> $A$、$B$ 是 $m \times n$ 矩阵，$\mathbf{u}$、$\mathbf{v}$ 是 $\mathbb{R}^n$ 中的向量，$c$ 为标量。则：
> 1. $A(\mathbf{u}+\mathbf{v})=A\mathbf{u}+A\mathbf{v}$
> 2. $A(c\mathbf{u})=c(A\mathbf{u})=(cA)\mathbf{u}$
> 3. $(A+B)\mathbf{u}=A\mathbf{u}+B\mathbf{u}$
> 4. $A\mathbf{0}=\mathbf{0}$ （其中第一个 $\mathbf{0} \in \mathbb{R}^n$，第二个 $\mathbf{0} \in \mathbb{R}^m$）
> 5. $O\mathbf{v}=\mathbf{0}$ （其中零矩阵 $O_{m\times n}$，$\mathbf{0}\in \mathbb{R}^m$）
> 6. $I_n \mathbf{v}=\mathbf{v}$
> 7. $A\mathbf{e}_j=\mathbf{a}_j$  （其中单位向量 $\mathbf{e}_j \in \mathbb{R}^n$，$\mathbf{a}_j$ 是 $A$ 的第 j 列）
> 8. 若 $\forall \mathbf{w} \in \mathbf{R}^n, A\mathbf{w}=B\mathbf{w}$，则 $A=B$

证明：

- 矩阵代表了一个 Linear System，因此**性质1**和**性质2的第1个等式**分别对应 Linear System 的两个特征。

- 其他等式的证法：矩阵写为这种形式 $A=\begin{bmatrix} \mathbf{a_1} & \mathbf{a_2} & \cdots & \mathbf{a_n}\end{bmatrix}$，向量写为这种形式 $\mathbf{u}=\begin{bmatrix} u_1 \\ u_2 \\ \vdots \\ u_n \end{bmatrix}$，然后将Matrix-Vector Product展开，即可很容易证明。

  以性质2的第2个等式为例：
  $$\begin{aligned}
c(A\mathbf{u})&=c(u_1 \mathbf{a}_1+u_2 \mathbf{a}_2+\cdots+u_n \mathbf{a}_n) \\ 
&=u_1 (c\mathbf{a}_1)+u_2 (c\mathbf{a}_2)+\cdots+u_n (c\mathbf{a}_n) \\
&=\begin{bmatrix} c\mathbf{a}_1 & c\mathbf{a}_2 & \cdots & c\mathbf{a}_n\end{bmatrix} \begin{bmatrix} u_1 \\ u_2 \\ \vdots \\ u_n \end{bmatrix} \\
&=(cA)\mathbf{u}
\end{aligned}$$
- 性质8的证明：
  要证矩阵相等，只要证它们的**每一列都对应相等**。
  选取单位向量 $\mathbf{e}_j$，其中 $j = 1, 2, \dots, n$。
  对于每一个 $j$ ，根据已知条件可得：$A\mathbf{e}_j=B\mathbf{e}_j$ 
  根据性质7有：
  ![[Pasted image 20260206172816.png|500]]
  