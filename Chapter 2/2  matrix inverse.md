
# Matrix vs Function

Matrix-Vector Product 中，可以将矩阵看作一个函数：对于 $m\times n$ 的矩阵 $A$，其对应关系为 $f(\mathbf{x})=A\mathbf{x}$，输入 $n$ 维向量，输出 $m$ 维向量，即 $f: \mathbb{R}^n \to \mathbb{R}^m$。

> 助记：$m\times n$ 中，$n$ 是输入向量的维数，$m$ 是输出向量的维数。

# 基本概念

### domain / codomain / range

> [!quote] domain / codomain / range
> 函数 $f:A\to B$ 是一种**对应关系**，它将 $A$ 中的==每个==元素 $a$ 对应到 $B$ 中的一个元素 $f(a)$。$A$ 称为函数的 **domain**，$B$ 称为函数的 **codomain**，集合 $\{f(x)|x\in A\}$ 称为函数的 **range**。
> 
> 显然，函数的 range 总是其 codomain 的子集：$\text{range}(f)\subseteq \text{codomain}(f)$。
> 
> ![[Pasted image 20260305162741.png|400]]

> 【案例1】函数 $h:\mathbb{R} \to \mathbb{R}$，对应关系为 $h(x)=x^2$，它的：
> - domain：$\mathbb{R}$
> - codomain：$\mathbb{R}$
> - range：$[0,+\infty]$
> 
> 【案例2】矩阵 $A = \begin{bmatrix} 2 & 4 \\ 0 & 3 \\ 0 & 0 \end{bmatrix}$，它对应的函数是 $f:\mathbb{R}^2\to \mathbb{R}^3$，对应关系为 $f(\mathbf{x}) = A\mathbf{x}$，它的：
> - domain：$\mathbb{R}^2$
> - codomain：$\mathbb{R}^3$
> - range：$\text{Span}\{\mathbf{a}_1,\mathbf{a}_2\}=\{\begin{bmatrix} x_1 \\ x_2 \\ 0 \end{bmatrix} \mid x_1, x_2 \in \mathbb{R}\}$

### one-to-one / onto

> [!quote] one-to-one / onto
> 对于函数 $f:A\to B$：
> - 若 $\forall a_1,a_2 \in A$，$a_1\neq a_2$，都有 $f(a_1)\neq f(a_2)$，则称 $f$ is **one-to-one**.
> - 若 $\forall b\in B$，均存在 $a\in A$ 使 $f(a)=b$，则称 $f$ is **onto**.
>   这等价于 ==$\text{range}(f)=\text{codomain}(f)$==。
> 
> ![[Pasted image 20260311151248.png|500]]

> 把 domain 看作*萝卜*的集合，codomain 看作*坑*的集合：
> - **one-to-one**：一个萝卜一个坑（不允许多个萝卜占同一个坑）
> - **onto**：所有的坑都被占满

上述定义对应到矩阵中是：

> [!example] one-to-one / onto
> 对于 $m\times n$ 的矩阵 $A$，它对应的函数是 $f: \mathbb{R}^n \to \mathbb{R}^m$，表达式为 $f(\mathbf{x})=A\mathbf{x}$。
> - 若 $\forall \mathbf{v}_1,\mathbf{v}_2\in \mathbb{R}^n$，$\mathbf{v}_1\neq\mathbf{v}_2$，都有 $A\mathbf{v}_1\neq A\mathbf{v}_2$，则称 $A$ is **one-to-one**.
> - 若 $\forall \mathbf{b}\in\mathbb{R}^m$，均存在 $\mathbf{v}\in \mathbb{R}^n$ 使 $A\mathbf{v}=\mathbf{b}$，则称 $A$ is **onto**.
>    这等价于 ==$\text{Span}\ \{\mathbf{a}_1,\mathbf{a}_2,\cdots,\mathbf{a}_n\}=\mathbb{R}^m$==

##### 与方程 f(x)=b 的解的关系

> [!quote] Theorem
> 对于函数 $f:A\to B$：
> - $f$ 是 one-to-one 的 $\iff$ $\forall b\in B$，方程 $f(x)=b$ **最多有 1 解**
> - $f$ 是 onto 的 $\iff$ $\forall b\in B$，方程 $f(x)=b$ **总是有解**

> 命题1的说明：one-to-one 没有要求每个坑都必须有萝卜，因此可能无解。

> 证明思路（trivial）：“左推右”采用反证法，例如对结论1，假设 $\exists b\in B$，方程 $f(x)=b$ 有两个不同解，推出 $f$ 不是 one-to-one 的，矛盾；“右推左”只需证明其符合 one-to-one/onto 定义。

上述定理对应到矩阵中是：

> [!important] Theorem
> 对于 $m\times n$ 的矩阵 $A$：
> - $A$ 是 one-to-one 的 $\iff$ $\forall \mathbf{b}\in \mathbb{R}^m$，方程 $A\mathbf{x}=\mathbf{b}$ **最多有 1 解**
> - $A$ 是 onto 的 $\iff$ $\forall \mathbf{b}\in \mathbb{R}^m$，方程 $A\mathbf{x}=\mathbf{b}$ **总是有解**

##### 与 domain/codomain 的关系

> [!quote] Theorem
> - 若 $f$ 的 **codomain 小于 domain**，则 $f$ 不可能是 one-to-one 的。
> - 若 $f$ 的 **codomain 大于 domain**，则 $f$ 不可能是 onto 的。

> 命题1的说明：坑比萝卜少，则必然会有多个萝卜对应到同一个坑，因此不可能 one-to-one
> 命题2的说明：坑的数目大于萝卜的数目，因此坑不可能都被占满

上述定理对应到矩阵中是：

> [!important] Theorem
> - **矮胖矩阵**不可能是 one-to-one 的。
> - **高瘦矩阵**不可能是 onto 的。

> 证明：矮胖矩阵（$m<n$）的 domain 是 $\mathbb{R}^n$，codomain 是 $\mathbb{R}^m$。其 codomain 小于 domain，因此不可能是 one-to-one 的。同理，高瘦矩阵（$m>n$）不可能是 onto 的。

### invertible / inverse

##### 定义

> [!quote] invertible / inverse
> ![[Pasted image 20260304185055.png|374]]
> 
> 对于函数 $f: A \to B$，若存在一个函数 $g: B \to A$ 使以下条件同时成立：
> 1. $\forall \mathbf{v}\in A,\ g(f(\mathbf{v}))=\mathbf{v}$
> 2. $\forall \mathbf{v}\in B,\ f(g(\mathbf{v}))=\mathbf{v}$
> 
> 则称函数 $f$ is **invertible**（可逆的），称 $g$ 是 $f$ 的 **inverse**（逆），记作 $f^{-1}$。
> 
> 根据定义知，$f$ 也是 $g$ 的逆，称 $f$、$g$ 互逆。

上述定义对应到矩阵中是：

> [!example] invertible / inverse
> ![[Pasted image 20260315154313.png|374]]
> 
> 对于 $m\times n$ 的矩阵 $A$（即函数 $f_A: \mathbb{R}^n \to \mathbb{R}^m$），若存在一个 $n\times m$ 的矩阵 $B$（即函数 $f_B: \mathbb{R}^m \to \mathbb{R}^n$）使以下条件同时成立：
> 
> 1. ==$\forall \mathbf{v}\in \mathbb{R}^n,\ B(A\mathbf{v})=\mathbf{v}$==
> 2. ==$\forall \mathbf{v}\in \mathbb{R}^m,\ A(B\mathbf{v})=\mathbf{v}$==
> 
> 则称矩阵 $A$ is **invertible**，称 $B$ 是 $A$ 的 **inverse**，记作 $A^{-1}$。
> 
> 根据定义知，$A$ 也是 $B$ 的逆，称 ==$A$、$B$ 互逆==。

> 其他称呼：
> - Invertible = **Non-singular**（非奇异）
> - Not invertible = **Singular**（奇异）

##### Invertible ⟺ AB=I 且 BA=I

> [!important] Theorem
> 矩阵 $A$ is invertible ⟺ 存在矩阵 $B$ 使 $AB=I$ 且 $BA=I$

> 证明：对于 $m\times n$ 的矩阵 $A$，若存在一个 $n\times m$ 的矩阵 $B$ 使以下条件同时成立：
> 1. $\forall \mathbf{v}\in \mathbb{R}^n,\ B(A\mathbf{v})=\mathbf{v}$ $\iff$ $\forall \mathbf{v}\in \mathbb{R}^n,\ (BA)\mathbf{v}=\mathbf{v}$ $\iff$ $BA=I$
> 2. $\forall \mathbf{v}\in \mathbb{R}^m,\ A(B\mathbf{v})=\mathbf{v}$ $\iff$ $\forall \mathbf{v}\in \mathbb{R}^m,\ (AB)\mathbf{v}=\mathbf{v}$ $\iff$ $AB=I$
> 则称矩阵 $A$ is invertible.   ■
> ![[Pasted image 20260315165420.png]]

##### Invertible ⟺ one-to-one 且 onto

> [!quote] Theorem
> 函数 $f$ is invertible ⟺ 函数 $f$ **one-to-one** 且 **onto**

> 证明：对于函数 $f: A \to B$，若存在一个函数 $g: B \to A$ 使以下条件同时成立：
> 1. $\forall \mathbf{v}\in A,\ g(f(\mathbf{v}))=\mathbf{v}$ $\iff$ $f$ is one-to-one （证明见“引理1”）
> 2. $\forall \mathbf{v}\in B,\ f(g(\mathbf{v}))=\mathbf{v}$ $\iff$ $f$ is onto （证明见“引理2”）
> 则称函数 $f$ is invertible.   ■
> 
> **引理1**：对于函数 $f: A \to B$：
> 存在函数 $g: B \to A$ 使 $\forall \mathbf{v}\in A,\ g(f(\mathbf{v}))=\mathbf{v}$ $\iff$ $f$ is one-to-one
> **证明**：
> 左推右：只要证 $\forall a_1,a_2\in A$，$a_1\neq a_2$，都有 $f(a_1)\neq f(a_2)$
> 取 $a_1,a_2\in A$，知 $g(f(a_1))=a_1$，$g(f(a_2))=a_2$
> 又因为 $a_1\neq a_2$，故 $g(f(a_1))\neq g(f(a_2))$
> $\implies$ $f(a_1)\neq f(a_2)$
> 右推左：构造 $g:B\to A$ 将 $f$ 的每个映射逆过来即可（对于 $b\notin f(A)$，可以任意指定 $A$ 中的某个值作为其函数值）。
> 
> **引理2**：对于函数 $f: A \to B$：
> 存在函数 $g: B \to A$ 使 $\forall \mathbf{v}\in B,\ f(g(\mathbf{v}))=\mathbf{v}$ $\iff$ $f$ is onto
> **证明**：
> 左推右：只要证 $\forall b\in B$，方程 $f(x)=b$ 总是有解
> 由已知条件知，该方程总是有 $g(b)$ 作为它的解
> 右推左：构造 $g:B\to A$ 将 $f$ 的每个映射逆过来即可（如果有多对一的情况，任选其中一个作为函数值即可。不论选取哪个元素，经过 $f$ 后都可以恢复原来的值）。

上述定理对应到矩阵中是：

> [!important] Theorem
> 矩阵 $A$ is invertible ⟺ 矩阵 $A$ **one-to-one** 且 **onto**

# Invertible Matrix

> [!example] Summary：矩阵 invertible 的三个等价定义
> 对于 $m\times n$ 的矩阵 $A$，若存在一个 $n\times m$ 的矩阵 $B$ 使以下条件同时成立：
>   1.  ==$\forall \mathbf{v}\in \mathbb{R}^n,\ B(A\mathbf{v})=\mathbf{v}$== $\iff$ ==$BA=I$== $\iff$ ==$A$ is one-to-one==
>   2.  ==$\forall \mathbf{v}\in \mathbb{R}^m,\ A(B\mathbf{v})=\mathbf{v}$==$\iff$ ==$AB=I$== $\iff$ ==$A$ is onto==
> 
> 则称矩阵 $A$ is **invertible**.

### 只有 square matrix 才有可能可逆

> [!NOTE] 
> - Non-square matrix **一定不可逆**
> - Square matrix 可能可逆，也可能不可逆

> 证明：
> 
> 命题1：①矮胖矩阵不可能 one-to-one；②高瘦矩阵不可能 onto；③invertible $\iff$ one-to-one 且 onto。综上，non-square matrix 一定不可逆。
> 
> 命题2：
> - 可逆的例子：$A=\begin{bmatrix}1 & 2 \\ 3 & 5\end{bmatrix}$，$B=\begin{bmatrix}-5 & 2 \\ 3 & -1\end{bmatrix}$，则 $AB=\begin{bmatrix}1 & 0 \\ 0 & 1\end{bmatrix}$，$BA=\begin{bmatrix}1 & 0 \\ 0 & 1\end{bmatrix}$
> - 不可逆的例子：$\begin{bmatrix}1 & 2 \\ 0 & 0\end{bmatrix}$，它右乘任何方阵都不等于 $I$：$\begin{bmatrix}1 & 2 \\ 0 & 0\end{bmatrix} \begin{bmatrix}a & b \\ c & d\end{bmatrix}=\begin{bmatrix}a+2c & b+2d \\ 0 & 0\end{bmatrix}\neq I$

### 对于 square matrix：one-to-one ⟺ onto，AB=I ⟺ BA=I

> [!important] Theorem
> $A$ 是一个 $n\times n$ 方阵：$A$ is **one-to-one** $\iff$ $A$ is **onto**

> 说明：square matrix 的 **domain = codomain**，即萝卜和坑的数量一样多。若 one-to-one，即每个萝卜都对应了不同的坑，而萝卜和坑的数量一样多，因而所有的坑都被占满了（onto）；若 onto，即所有的坑都被占满了，而萝卜和坑的数量一样多，则只能一个萝卜占一个不同的坑。

> [!important] 推论
> $A$ 是一个 $n\times n$ 方阵：
> - 存在一个 $n\times n$ 方阵 $B$ 使 $AB=I$ $\implies$ $BA=I$
> - 存在一个 $n\times n$ 方阵 $B$ 使 $BA=I$ $\implies$ $AB=I$

### Invertible Matrix Theorem

> [!important] invertible 的等价条件
> $A$ 是一个 $n\times n$ 矩阵（**方阵**），$A$ is invertible **等价于**以下任一条件：
> 
> 1. $A$ is one-to-one
>    $\xLeftrightarrow{1.1}$ 存在一个 $n\times n$ 矩阵 $B$ 使 $BA=I_n$
>    $\xLeftrightarrow{1.2}$ $\forall \mathbf{b}\in \mathbb{R}^n$，方程 $A\mathbf{x}=\mathbf{b}$ 最多有 1 解
>    $\xLeftrightarrow{1.2.1}$ ==$A$ 的 columns 是 independent 的==
>    $\xLeftrightarrow{1.2.2}$ $\text{rank}\ A=n$
>    $\xLeftrightarrow{1.2.3}$ $\text{nullity}\ A=0$
>    $\xLeftrightarrow{1.2.4}$ ==方程 $A\mathbf{x}=\mathbf{0}$ 的唯一解是 $\mathbf{0}$==
>    $\xLeftrightarrow{1.2.1.1}$ $A$ 的 RREF 是 $I_n$
> 2. $A$ is onto
>    $\xLeftrightarrow{2.1}$ 存在一个 $n\times n$ 矩阵 $B$ 使 $AB=I_n$
>    $\xLeftrightarrow{2.2}$ $\forall \mathbf{b}\in \mathbb{R}^n$，方程 $A\mathbf{x}=\mathbf{b}$ 总是有解
>    $\xLeftrightarrow{2.2.1}$ $\text{Span}\ \{\mathbf{a}_1,\mathbf{a}_2,\dots,\mathbf{a}_n\}=\mathbb{R}^n$
>    $\xLeftrightarrow{2.2.2}$ $\text{rank}\ A=n$
> 3. $A$ 是若干 elementary matrix 的乘积
> 4. ==$\forall \mathbf{b}\in \mathbb{R}^n$，方程 $A\mathbf{x}=\mathbf{b}$ 有唯一解==

联想关系如图所示：
![[Pasted image 20260318171552.png]]

> 证明：
> **1** $A$ is one-to-one $\implies$ $A$ is onto $\implies$ $A$ is invertible，反之也成立
> **1.1** 见本节"Summary：矩阵 invertible 的三个等价定义"，证明见本节"Invertible ⟺ one-to-one 且 onto"中引理1、2的证明
> **1.2** 见本节"one-to-one/onto 与方程 f(x)=b 的解的关系"
> **1.2.1~1.2.4** 1.2 等价于 1.2.1（证明见[[6  solution]]的"dependent/independent"的"与线性方程组解的关系"部分）, 1.2.1 等价于其他。
> **1.2.1.1** 不用说
> **2** $A$ is onto $\implies$ $A$ is one-to-one $\implies$ $A$ is invertible，反之也成立
> **2.1** 同 1.1 的证明
> **2.2** 同 1.2 的证明
> **2.2.1~2.2.2** 见 [[7  RREF#是否总是有解？]]
> **3** 
> ![[Pasted image 20260317094921.png|672]]
> **4** 左推右：由1.2和2.2共同推出；右推左：右侧可推得1.2或2.2，而它们等价于 invertible。

> 案例：Invertible 性质的应用
> 
> 【例1】$Q$ 是一个 invertible 的 $n\times n$ 矩阵。
> 求证：$\{\mathbf{u}_1,\mathbf{u}_2,\dots,\mathbf{u}_k\}\subseteq \mathbb{R}^n$ independent $\iff$ $\{Q\mathbf{u}_1,Q\mathbf{u}_2,\dots,Q\mathbf{u}_k\}$ independent
> 
> 证明：
> **左推右**：只要证 $c_1(Q\mathbf{u}_1)+c_2(Q\mathbf{u}_2)+\dots+c_k(Q\mathbf{u}_k)=\mathbf{0}$ 的唯一解是 $c_1=c_2=\cdots=c_k=0$
> 原方程 $\iff$ $Q(c_1\mathbf{u}_1)+Q(c_2\mathbf{u}_2)+\dots+Q(c_k\mathbf{u}_k)=\mathbf{0}$ （线性系统的 preserving scaling 性质）
> $\iff$ $Q(c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k)=\mathbf{0}$ （线性系统的 preserving addition 性质）
> 由 $Q$ is invertible 的性质知，方程的唯一解是 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$
> 由于 $\{\mathbf{u}_1,\mathbf{u}_2,\dots,\mathbf{u}_k\}$ independent，故方程的唯一解是 $c_1=c_2=\cdots=c_k=0$
> **右推左**：只要证 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$ 的唯一解是 $c_1=c_2=\cdots=c_k=0$
> 原方程 $\iff$ $Q(c_1\mathbf{u}_1)+Q(c_2\mathbf{u}_2)+\dots+Q(c_k\mathbf{u}_k)=\mathbf{0}$
> $\iff$ $c_1(Q\mathbf{u}_1)+c_2(Q\mathbf{u}_2)+\dots+c_k(Q\mathbf{u}_k)=\mathbf{0}$
> 由于 $\{Q\mathbf{u}_1,Q\mathbf{u}_2,\dots,Q\mathbf{u}_k\}$ independent，故方程的唯一解是 $c_1=c_2=\cdots=c_k=0$
> 
> 【例2】$A$ 是一个 invertible 的 $n\times n$ 矩阵，令 $e_j$ 是 $\mathbb{R}^n$ 的第 $j$ 个 standard vector。
> 求证：$A^{-1}$ 的第 $j$ 个 column 是方程 $A\mathbf{x}=e_j$ 的一个解。
> 
> 证明：$A^{-1}$ 的第 $j$ 个 column = $A^{-1}e_j$
> 只要把它代入方程验证即可：左边 = $AA^{-1}e_j$ = $e_j$ = 右边
> 
> 【例3】$A$ 是一个 $n\times n$ 矩阵。
> 求证：当且仅当 $A$ is invertible 时，命题"$AB=AC \iff B=C$"才成立。
> 
> 证明：相当于要证明以下两个命题
> ①已知 $A$ is invertible，求证 $AB=AC \iff B=C$。
>    左推右：$AB=AC$ $\iff$ $A^{-1}AB=A^{-1}AC$ $\iff$ $B=C$
>    右推左：trivial
> ②已知 $AB=AC \iff B=C$，求证 $A$ is invertible。
>    证明：逆着推：$A$ is invertible $\iff$ 方程 $A\mathbf{x}=\mathbf{0}$ 的唯一解是 $\mathbf{0}$
>    因此正着推时可以朝着“$A\mathbf{x}=\mathbf{0} \iff \mathbf{x}=\mathbf{0}$”这个方向
>    取 $B=\mathbf{x}$，$C=\mathbf{0}$，则 $A\mathbf{x}=A\mathbf{0} \iff \mathbf{x}=\mathbf{0}$
>    即 $A\mathbf{x}=\mathbf{0} \iff \mathbf{x}=\mathbf{0}$

# Inverse of Matrix

### Properties

##### 唯一性

> [!NOTE] 
> 矩阵的 inverse 是**唯一的**

> 证明：对于任意方阵 $A$，设 $B$ 和 $C$ 都是 $A$ 的逆阵。
> 则 $AB=BA=I$，$AC=CA=I$
> 则 $B=BI=B(AC)=(BA)C=IC=C$
> 因此矩阵的 inverse 是唯一的。

##### Inverse vs Transpose

> [!important] Theorem
> ==若 $A$ 可逆，则 $A^T$ 也可逆==，且
> $$(A^T)^{-1}=(A^{-1})^T$$

> 证明：
> $A^{-1}A=I$ $\implies$ $(A^{-1}A)^T=I$ $\implies$ $A^T(A^{-1})^T=I$
> 故 $(A^{-1})^T$ 是 $A^T$ 的 inverse。

##### Inverse vs Matrix multiplication

> [!important] Theorem
> ==若 $A$ 和 $B$ 可逆，则 $AB$ 也可逆==，且
> $$(AB)^{-1}=B^{-1}A^{-1}$$

> 证明：
> $AA^{-1}=I$，$BB^{-1}=I$ $\implies$ $A(BB^{-1})A^{-1}=I$ $\implies$ $(AB)(B^{-1}A^{-1})=I$
> 故 $B^{-1}A^{-1}$ 是 $AB$ 的 inverse。

> [!NOTE] 
> 推广：若矩阵 $A_1,A_2,\dots,A_k$ 均可逆，则它们的乘积 $A_1A_2\dots A_k$ 也可逆，且
> $$(A_1 A_2 \dots A_k)^{-1} = A_k^{-1} A_{k-1}^{-1} \dots A_1^{-1}$$

> 证明：trivial，递归应用已有结论 $(AB)^{-1}=B^{-1}A^{-1}$。

### 应用

##### 求解 system of linear equations

> [!NOTE] 
> 对于线性方程组 $A\mathbf{x}=\mathbf{b}$，若 $A$ 可逆，则 ==$\mathbf{x}=A^{-1}\mathbf{b}$==。

> 推导：$A\mathbf{x}=\mathbf{b}$ $\iff$ $A^{-1}(A\mathbf{x})=A^{-1}\mathbf{b}$ $\iff$ $\mathbf{x}=A^{-1}\mathbf{b}$

用此方法求解线性方程组通常**计算上更麻烦**（因为求 $A^{-1}$ 本身需要把 $[A \mid I]$ 化为 RREF，而在解方程组时，只需把 $[A\mid \mathbf{b}]$ 化为 RREF 就已经可以看出解集）。

该方法适用于同一个矩阵解很多次的情况（$A\mathbf{x}=\mathbf{b}_1,A\mathbf{x}=\mathbf{b}_2,\dots$），先求 $A^{-1}$，再对不同的 $\mathbf{b}$ 套用 $\mathbf{x}=A^{-1}\mathbf{b}$。

##### 逆变换

Matrix-Vector Product $A\mathbf{x}$ 中，矩阵 $A$ 表示一个线性变换。若 $A$ 可逆，则 $A^{-1}$ 表示该线性变换的**逆变换**。

# Elementary Matrix

> [!important] Theorem
> 任何 elementary row operation 都可以通过**矩阵乘法**来实现：对 $m\times n$ 的矩阵 $A$ 做一次 elementary row operation，等价于在 $A$ 的**左侧**乘以一个特定的矩阵 $E$：
> $$EA$$
> 其中 $E$ 是通过==在单位矩阵 $I_m$ 上执行同样的 elementary row operation== 得到的矩阵，称为 **elementary matrix**。

> 证明：验证即可，见复旦大学《高等代数学》P84~86（提示：从“矩阵相乘 = Linear Combination of B's Rows”的观点做验证）

> 示例：
> ![[Pasted image 20260316200149.png|585]]

> [!NOTE] 
> 1. 每个 elementary row operation 都对应一个 elementary matrix
> 2. elementary matrix 一定是方阵（$m\times n$ 矩阵的 elementary matrix 是 $m\times m$ 矩阵）

> [!NOTE] RREF vs Elementary matrix
> 矩阵 $A$ 经过 $k$ 次 elementary row operation 变为 RREF $R$，该过程可以用矩阵乘法表示为：
> $$E_k\dots E_2E_1A=R$$
> 其中 $E_1,E_2,\dots,E_k$ 分别是这 $k$ 次 elementary row operation 对应的 elementary matrix。

### Inverse of Elementary Matrix

所有 elementary row operation 都有逆操作，并且逆操作也属于 elementary row operation。具体来说：

- Interchange：$r_i\leftrightarrow r_j$ 的逆操作仍是 $r_i\leftrightarrow r_j$
- Scaling：$cr_i$ 的逆操作是 $\cfrac{1}{c}r_i$
- Row Addition：$cr_j+r_j$ 的逆操作是 $(-c)r_i+r_j$

由于每个 elementary row operation 都对应一个 elementary matrix，因此：

> [!important] Theorem
> elementary matrix 一定 invertible，并且其 inverse 也是 elementary matrix。
> 
> ---
> 
> elementary matrix 的 inverse = 它对应的 elementary row operation 的**逆操作**对应的 elementary matrix。

> 证明：
> 对任意矩阵 $A$，执行某 elementary row operation 得到 $A'$，再执行逆操作将它还原回 $A$。记这两次 elementary row operation 对应的 elementary matrix 分别为 $E$、$E'$，则有 $E'EA=A$。由于 $A$ 可以是任意矩阵，因此 $E'E=I$。由于 $E$ 是方阵，因此 $E'E=I$ $\implies$ $E$ 可逆，并且其 inverse 是 $E'$。前面说过，$E'$ 也是 elementary matrix，$E'$ 对应的 elementary row operation 正是 $E$ 对应的 elementary row operation 的逆操作。

> 示例：求 $E_1$、$E_2$、$E_3$ 的 inverse。
> ![[Pasted image 20260318101847.png|388]]

# Finding Inverse

若 $A$ is invertible，则 $A$ 的 RREF 是 $I_n$，则存在 elementary matrix $E_1,E_2,\dots,E_k$ 使得
$$E_k\dots E_2 E_1 A=I_n$$
故 $E_k\dots E_2 E_1$ 正是 $A^{-1}$。由此启发我们可以这样来求 inverse：

> [!important] 求任意方阵的 inverse
> 对**任意的** $n\times n$ 方阵 $A$：构造矩阵 $\begin{bmatrix}A \mid I_n\end{bmatrix}$，将其化为 RREF $\begin{bmatrix}R \mid B\end{bmatrix}$。
> - 若 $R=I_n$，则 $A$ 可逆，且 $B$ 就是 $A^{-1}$。
> - 若 $R\neq I_n$，则 $A$ 不可逆。

> 证明：
> $\begin{bmatrix}A \mid I_n\end{bmatrix} \xrightarrow{RREF} \begin{bmatrix}R \mid B\end{bmatrix}$，则
> ①存在 elementary matrix $E_1,E_2,\dots,E_k$ 使得：$E_k\dots E_2 E_1 \begin{bmatrix}A \mid I_n\end{bmatrix} = \begin{bmatrix}R \mid B\end{bmatrix}$
> ②由 RREF 按列分块性质知：$R$ 正是 $A$ 的 RREF
> 由②知，若 $R\neq I_n$，则 $A$ 不可逆；若 $R=I_n$，则 $A$ 可逆。
> $R=I_n$ 时，有 $E_k\dots E_2 E_1 \begin{bmatrix}A \mid I_n\end{bmatrix} = \begin{bmatrix}I_n \mid B\end{bmatrix}$
> elementary row operation 同时作用在左右两块矩阵上，故：
> ①左半边：$E_k\dots E_2 E_1 A=I_n$，故 $E_k\dots E_2 E_1$ 正是 $A^{-1}$
> ②右半边：$E_k\dots E_2 E_1 I_n = B$，故 $B=E_k\dots E_2 E_1=A^{-1}$

> 案例：$A=\begin{bmatrix}1 & 2 & 3 \\ 2 & 5 & 6 \\ 3 & 4 & 8\end{bmatrix}$，判断 $A$ 是否可逆。若可逆，求 $A^{-1}$。
> 解：
> ![[Pasted image 20260313151844.png|588]]
> 化为 RREF 后，左半边是 identity matrix，因此 $A$ 可逆，且右半边就是 $A^{-1}$。

> [!NOTE] 求 $A^{-1}C$
> $A$ 是可逆的 $n\times n$ 方阵，$C$ 是任意的 $n\times n$ 方阵，求 $A^{-1}C$.
> 
> 构造矩阵 $\begin{bmatrix}A \mid C\end{bmatrix}$，将其化为 RREF $\begin{bmatrix}I_n\mid C'\end{bmatrix}$，则 $C'$ 就是 $A^{-1}C$.
