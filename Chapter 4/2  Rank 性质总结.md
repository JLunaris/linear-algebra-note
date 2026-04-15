
### 向量集经过线性变换，“倾向于” dependent

![[Pasted image 20260406172853.png|219]]
$S=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_k\}\subseteq\mathbb{R}^n$，$A$ 是 $m\times n$ 矩阵，$S'=\{A\mathbf{u}_1,A\mathbf{u}_2,\cdots,A\mathbf{u}_k\}$，有以下结论：

> [!important] 向量集经过线性变换，“倾向于” dependent
> - $S$ dependent $\implies$ $S'$ dependent
> - $S$ independent $\implies$ $S'$ 可能仍保持 independent，也可能变为 dependent

> 证明：
> **命题1**：$c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$，其中 $c_1,c_2,\cdots,c_k$ 不全为 $0$
> 两边同乘 $A$ 得：$A(c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k)=A\mathbf{0}=\mathbf{0}$
> 即 $A(c_1\mathbf{u}_1)+A(c_2\mathbf{u}_2)+\cdots+A(c_k\mathbf{u}_k)=\mathbf{0}$
> 即 $c_1(A\mathbf{u}_1)+c_2(A\mathbf{u}_2)+\cdots+c_k(A\mathbf{u}_k)=\mathbf{0}$，其中 $c_1,c_2,\cdots,c_k$ 不全为 $0$
> 故 $S'$ dependent.
> **命题2**：分别举出正反例即可

> [!important] Theorem
> 若 $A$ 的 columns 是 independent 的，则：==$S$ independent  $\implies$ $S'$ independent==

> 证明：只要证 $c_1(A\mathbf{u}_1)+c_2(A\mathbf{u}_2)+\dots+c_k(A\mathbf{u}_k)=\mathbf{0}$ 的唯一解是 $c_1=c_2=\cdots=c_k=0$
> 原方程 $\iff$ $A(c_1\mathbf{u}_1)+A(c_2\mathbf{u}_2)+\dots+A(c_k\mathbf{u}_k)=\mathbf{0}$（线性系统的 preserving scaling 性质）$\iff$ $A(c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k)=\mathbf{0}$ （线性系统的 preserving addition 性质）
> $A$ 的 columns 是 independent 的，故方程 $\iff$ $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$
> 由 $\{\mathbf{u}_1,\mathbf{u}_2,\dots,\mathbf{u}_k\}$ independent 知，方程的唯一解是 $c_1=c_2=\cdots=c_k=0$

> [!important] Theorem
> 若 $A$ is invertible，则：==$S$ independent  $\iff$ $S'$ independent==

> 证明：
> **左推右**：$A$ is invertible $\implies$ $A$ 的 columns 是 independent 的
> 由上一条定理知 $S$ independent  $\implies$ $S'$ independent
> **右推左**：只要证 $c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_k\mathbf{u}_k=\mathbf{0}$ 的唯一解是 $c_1=c_2=\cdots=c_k=0$
> 原方程 $\iff$ $A(c_1\mathbf{u}_1)+A(c_2\mathbf{u}_2)+\dots+A(c_k\mathbf{u}_k)=\mathbf{0}$
> $\iff$ $c_1(A\mathbf{u}_1)+c_2(A\mathbf{u}_2)+\dots+c_k(A\mathbf{u}_k)=\mathbf{0}$
> 由 $\{A\mathbf{u}_1,A\mathbf{u}_2,\cdots,A\mathbf{u}_k\}$ independent 知，方程的唯一解是 $c_1=c_2=\cdots=c_k=0$

### Matrix multiplication vs Rank

##### 矩阵相乘，rank 减小或保持不变

> [!important] Theorem
> $A$ 是 $m\times n$ 矩阵，$B$ 是 $n\times p$ 矩阵，有：
> - $\text{rank}\ AB \leq \text{rank}\ A$
> - $\text{rank}\ AB \leq \text{rank}\ B$
> 
> 上述定理可以统一写为：==$\text{rank}\ AB \leq \min(\text{rank}\ A, \text{rank}\ B)$==

> 助记：==矩阵相乘，rank 减小或保持不变==。

> 证明：

##### 矩阵乘 invertible matrix（无论左乘/右乘），rank 保持不变

> [!important] Theorem
> - $A$ 是 $m\times n$ 矩阵，$P$ 是 invertible 的 $m\times m$ 矩阵，则：==$\text{rank}\ PA=\text{rank}\ A$==
> - $A$ 是 $m\times n$ 矩阵，$Q$ 是 invertible 的 $n\times n$ 矩阵，则：==$\text{rank}\ AQ=\text{rank}\ A$==

> 助记：==矩阵乘可逆阵（无论左乘/右乘），rank 保持不变==。

> 证明：
> **命题1**：
> ① $\text{rank}\ PA \le \text{rank}\ A$
> ② $\text{rank}\ P^{-1}PA \le \text{rank}\ PA$，即 $\text{rank}\ A \le \text{rank}\ PA$
> 综上，$\text{rank}\ PA=\text{rank}\ A$
> **命题2**：
> ① $\text{rank}\ AQ \le \text{rank}\ A$
> ② $\text{rank}\ AQQ^{-1} \le \text{rank}\ AQ$，即 $\text{rank}\ A \le \text{rank}\ AQ$
> 综上，$\text{rank}\ AQ=\text{rank}\ A$
