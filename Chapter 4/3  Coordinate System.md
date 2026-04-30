
# Coordinate System

Coordinate System 是一种表示向量的“观点”：
- 同一个向量，在不同的 coordinate system（观点）下，其表示是不同的
- 不同的向量，在不同的 coordinate system（观点）下，可能具有相同的表示

> [!example] coordinate system
> 若向量集 $B$ 是 ==$\mathbb{R}^n$ 的一个 basis==，则称 $B$ 为 $\mathbb{R}^n$ 引入了一个 **coordinate system**。

> [!example] coordinate vector
> 设向量集 $\mathcal{B}=\{\mathbf{u}_1,\mathbf{u}_2,\cdots,\mathbf{u}_n\}$ 是 $\mathbb{R}^n$ 的一个 basis，则对 $\mathbb{R}^n$ 中的任一向量 $\mathbf{v}$，都存在唯一一组标量 $c_1,c_2,\cdots,c_n$ 使 $\mathbf{v}=c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_n\mathbf{u}_n$。
> 
> ---
> 
> 向量 $\begin{bmatrix}c_1 \\ c_2 \\ \vdots \\ c_n\end{bmatrix}$ 称为 $\mathbf{v}$ 的 **$\mathcal{B}$-coordinate vector**，记作 ==$[\mathbf{v}]_\mathcal{B}$==。

> $[\mathbf{v}]_\mathcal{B}$ 的含义：在 $\mathcal{B}$ 引入的 coordinate system（观点）下，$\mathbf{v}$ 的表示。

> 证明：
> **存在性**：$B$ 是 $\mathbb{R}^n$ 的 basis $\implies$ $\text{Span}\ B=\mathbb{R}^n$ $\implies$ $\mathbb{R}^n$ 中的任一向量都可以写为 $B$ 中向量的 linear combination。
> **唯一性**：$B$ 是 $\mathbb{R}^n$ 的 basis $\implies$ $B$ 中向量 independent
> $\mathbf{v}=c_1\mathbf{u}_1+c_2\mathbf{u}_2+\cdots+c_n\mathbf{u}_n$ 可以写为 $B\mathbf{x}=\mathbf{v}$（$\mathbf{x}=\begin{bmatrix}c_1 \\ c_2 \\ \vdots \\ c_n\end{bmatrix}$），由 $B$ 中向量 independent 可知在有解的前提下必有唯一解。

> [!example] Cartesian Coordinate System
> 向量集 $\mathcal{E}=\{ \mathbf{e}_1,\mathbf{e}_2,\cdots,\mathbf{e}_n \}$ 为 $\mathbb{R}^n$ 引入了一个 coordinate system，该 coordinate system 称为 Cartesian Coordinate System。
> 
> 

表示向量时，如果没有指定 coordinate system，则==默认是 Cartesian Coordinate System==。

> 例如 $\mathbf{v}=\begin{bmatrix}3 \\ 5\end{bmatrix}$ 没有指定 coordinate system，则默认是在 Cartesian Coordinate System 下的表示；而 $[\mathbf{v}]_\mathcal{B}=\begin{bmatrix}3 \\ 5\end{bmatrix}$ 意为向量 $\mathbf{v}$ 在 $\mathcal{B}$ 这一 coordinate system 下的表示。

> [!NOTE] 
> $B=\{\mathbf{b}_1, \mathbf{b}_2, \cdots, \mathbf{b}_n\}$ 是 $\mathbb{R}^n$ 的 basis，则 ==$[\mathbf{b}_i]_B=\mathbf{e}_i$==.

> 【示例1：同一个向量，在不同的 coordinate system（观点）下，其表示是不同的】
> 
> 左图和右图中，同一个向量 $\mathbf{v}=\begin{bmatrix}8 \\ 4\end{bmatrix}$：
> - 在 $\mathcal{E} = \{ \mathbf{e}_1, \mathbf{e}_2 \}$ 引入的 coordinate system 下，$\mathbf{v}=8\mathbf{e}_1+4\mathbf{e}_2$，记作 $[\mathbf{v}]_\mathcal{E}=\begin{bmatrix}8 \\ 4\end{bmatrix}$
> - 在 $\mathcal{B} = \{ \begin{bmatrix}1 \\ 1\end{bmatrix}, \begin{bmatrix}-1 \\ 1\end{bmatrix} \}$ 引入的 coordinate system 下，$\mathbf{v}=6\begin{bmatrix}1 \\ 1\end{bmatrix}+(-2)\begin{bmatrix}-1 \\ 1\end{bmatrix}$，记作 $[\mathbf{v}]_\mathcal{B}=\begin{bmatrix}6 \\ -2\end{bmatrix}$
> ![[Pasted image 20260424143823.png|650]]
> 
> 【示例2：不同的向量，在不同的 coordinate system（观点）下，可能具有相同的表示】
> 
> 左图向量 = $\begin{bmatrix}2 \\ 3\end{bmatrix}$，右图向量 = $2\mathbf{b}_1+3\mathbf{b}_2=\begin{bmatrix}4 \\ 2.5\end{bmatrix}$，它们是不同的向量。但在不同的坐标系下，它们具有相同的表示。
> 
> ![[Pasted image 20260424150744.png|500]]

### Change Coordinate System

> [!important] Theorem
> 设 $\mathcal{B}=\{\mathbf{b}_1, \mathbf{b}_2, \cdots, \mathbf{b}_n\}$ 为 $\mathbb{R}^n$ 引入了一个 coordinate system，则对于 $\mathbb{R}^n$ 中任一向量 $\mathbf{v}$：
> $$B[\mathbf{v}]_\mathcal{B}=\mathbf{v}$$
> 其中 $B=\begin{bmatrix}\mathbf{b}_1 & \mathbf{b}_2 & \cdots & \mathbf{b}_n\end{bmatrix}$。显然 $B$ is invertible，因此上式等价于：$[\mathbf{v}]_B=B^{-1}\mathbf{v}$。

> 证明：设 $[\mathbf{v}]_\mathcal{B}=\begin{bmatrix}c_1 \\ c_2 \\ \vdots \\ c_n\end{bmatrix}$，则 $\mathbf{v}=c_1\mathbf{b}_1+c_2\mathbf{b}_2+\cdots+c_n\mathbf{b}_n=B[\mathbf{v}]_\mathcal{B}$
> 由 $B$ 是 basis 知 $B$ 的 columns 是 independent 的，结合 $B$ 是方阵知 $B$ is invertible。

> 【例】$B=\left\{ \begin{bmatrix} 1 \\ 1 \\ 1\end{bmatrix},\begin{bmatrix} 1 \\ -1 \\ 1\end{bmatrix},\begin{bmatrix} 1 \\ 2 \\ 2\end{bmatrix}\right\}$ 是 $\mathbb{R}^n$ 的 basis，$\mathbf{v}=\begin{bmatrix}1 \\ -4 \\ 4\end{bmatrix}$，求 $[\mathbf{v}]_B$。
> 
> 解：
> 法1：$B[\mathbf{v}]_B=\mathbf{v}$，解线性方程组，解得 $[\mathbf{v}]_B=\begin{bmatrix}-6 \\ 4 \\ 3\end{bmatrix}$
> 法2：$[\mathbf{v}]_B=B^{-1}\mathbf{v}$，先求 $B^{-1}$，再做矩阵乘法（该方法适用于计算机，将多个向量的 cartesian 坐标系下的表示转换为 $B$ 坐标系下的表示，不必每次都解线性方程组，仅需求一次 $B^{-1}$，以后只需做 matrix-vector product 即可）

##### Equation/Function in Different Coordinate Systems

> 【例1】已知在 cartesian 坐标系下双曲线的方程，求在 $B=\{\mathbf{b}_1, \mathbf{b}_2\}=\left\{ \begin{bmatrix}\cfrac{\sqrt{3}}{2} \\ \cfrac{1}{2}\end{bmatrix}, \begin{bmatrix}-\cfrac{1}{2} \\ \cfrac{\sqrt{3}}{2}\end{bmatrix} \right\}$ 构成的坐标系下该双曲线的方程。
> ![[Pasted image 20260429151308.png|274]]
> 
> 解：对于该双曲线上的任一向量 $\mathbf{v}=\begin{bmatrix}x \\ y\end{bmatrix}$，都有 $[\mathbf{v}]_B=\begin{bmatrix}x' \\ y'\end{bmatrix}$。
> $\mathbf{v}=B[\mathbf{v}]_B$，即 $\begin{bmatrix}x \\ y\end{bmatrix}=\begin{bmatrix} \cfrac{\sqrt{3}}{2} & -\cfrac{1}{2} \\ \cfrac{1}{2} & \cfrac{\sqrt{3}}{2} \end{bmatrix} \begin{bmatrix}x' \\ y'\end{bmatrix}=\begin{bmatrix} \cfrac{\sqrt{3}}{2}x'-\cfrac{1}{2}y' \\ \cfrac{1}{2}x'+\cfrac{\sqrt{3}}{2}y'\end{bmatrix}$
> 代入双曲线方程得：$x'y'=3$
> 
> 【例2】
> ![[Pasted image 20260428193633.png|406]]
> 解：
> ![[Pasted image 20260428204847.png|211]]
> 选取 $B=\{\mathbf{b}_1, \mathbf{b}_2\}=\left\{ \begin{bmatrix}\cfrac{\sqrt{2}}{2} \\ \cfrac{\sqrt{2}}{2}\end{bmatrix}, \begin{bmatrix}-\cfrac{\sqrt{2}}{2} \\ \cfrac{\sqrt{2}}{2}\end{bmatrix} \right\}$ 构成 $\mathbb{R}^2$ 的一个 coordinate system，在 $B$ 坐标系下，该椭圆方程为 $\cfrac{(x')^2}{3^2}+\cfrac{(y')^2}{2^2}=1$。 对于该椭圆上的任一向量 $\mathbf{v}=\begin{bmatrix}x \\ y\end{bmatrix}$，都有 $[\mathbf{v}]_B=\begin{bmatrix}x' \\ y'\end{bmatrix}$。
> 由 $B[\mathbf{v}]_B=\mathbf{v}$ 知，$[\mathbf{v}]_B=B^{-1}\mathbf{v}$，即 $\begin{bmatrix}x' \\ y'\end{bmatrix}=B^{-1}\begin{bmatrix}x \\ y\end{bmatrix} = \begin{bmatrix} \cfrac{\sqrt{2}}{2} & \cfrac{\sqrt{2}}{2} \\ -\cfrac{\sqrt{2}}{2} & \cfrac{\sqrt{2}}{2} \end{bmatrix}\begin{bmatrix}x \\ y\end{bmatrix}=\begin{bmatrix} \cfrac{\sqrt{2}}{2}x+\cfrac{\sqrt{2}}{2}y \\ -\cfrac{\sqrt{2}}{2}x+\cfrac{\sqrt{2}}{2}y\end{bmatrix}$
> 代入椭圆方程得：$\cfrac{(\cfrac{\sqrt{2}}{2}x+\cfrac{\sqrt{2}}{2}y)^2}{3^2}+\cfrac{(-\cfrac{\sqrt{2}}{2}x+\cfrac{\sqrt{2}}{2}y)^2}{2^2}=1$

##### Linear Function in Different Coordinate Systems

一个坐标系中复杂的函数，在另一个坐标系中可能很简单。

![[Pasted image 20260430170036.png|411]]

> [!example] $[T]_B$
> 设 $B=\{\mathbf{b}_1, \mathbf{b}_2, \cdots, \mathbf{b}_n\}$ 为 $\mathbb{R}^n$ 引入了一个 coordinate system，对于线性变换 ==$T:\mathbb{R}^n \to \mathbb{R}^n$==，从 $B$ 坐标系下看到的 $T$ 记作 ==$[T]_B$==。

> [!important] Theorem
> 设 $B=\{\mathbf{b}_1, \mathbf{b}_2, \cdots, \mathbf{b}_n\}$ 为 $\mathbb{R}^n$ 引入了一个 coordinate system，对于线性变换 $T:\mathbb{R}^n \to \mathbb{R}^n$，有：
> $$T=B[T]_BB^{-1}$$
> 上式等价于 $[T]_B=B^{-1}TB$。
> > ![[Pasted image 20260430174311.png|450]]

> 证明：如图中所示。把线性变换串起来，等同于把它们对应的矩阵从后向前依次乘起来。

> [!example] 相似矩阵
> 对于==方阵== $A$ 和 $B$，若存在==可逆阵== $P$ 使得 $B=P^{-1}AP$，则称 $A$ 与 $B$ **相似**。

> 相似矩阵定义的来源：
> 若 $A$ 和 $B$ 相似，则 $A$ 和 $B$ 是同一个线性变换，在不同 coordinate system 下看到的结果。
> 
> ![[Pasted image 20260430181755.png|391]]

---

> 【例1】关于直线 $\mathcal{L}:y=\cfrac{1}{2}x$ 的反射是一个函数 $T: \mathbb{R}^2 \to \mathbb{R}^2$，定义如下：
> 设 $\mathbf{v}\in\mathbb{R}^2$，其终点为 $P$。过点 $P$ 作直线 $\mathcal{L}$ 的垂线，设 $F$ 为该垂线与直线 $\mathcal{L}$ 的交点。将线段 $\overline{PF}$ 经过 $F$ 延长至点 $P'$，使得 $\overline{PF} = \overline{FP'}$。那么以 $P'$ 为终点的向量即为 $T(\mathbf{v})$。
> 显然 $T$ 是线性变换，求 $T$ 对应的矩阵。
> ![[Pasted image 20260430153429.png|315]]
> 
> 解：选取 $B=\{\mathbf{b}_1, \mathbf{b}_2\}=\left\{ \begin{bmatrix}2 \\ 1 \end{bmatrix}, \begin{bmatrix}-1 \\ 2 \end{bmatrix} \right\}$ 构成 $\mathbb{R}^2$ 的一个 coordinate system，在 $B$ 坐标系下，该线性变换对应的矩阵 $[T]_B=\begin{bmatrix}1 & 0 \\ 0 & -1\end{bmatrix}$（求解过程：$[\mathbf{b}_1]_B=\mathbf{e}_1$，$[\mathbf{b}_2]_B=\mathbf{e}_2$，分别把 $\mathbf{e}_1$、$\mathbf{e}_2$ 代入线性变换 $[T]_B$ 即可得到矩阵 $[T]_B$ 的每一列，结果为 $[T]_B(\mathbf{e}_1)=\mathbf{e}_1$，$[T]_B(\mathbf{e}_2)=-\mathbf{e}_2$）
> ![[Pasted image 20260430160144.png|220]]
> 故 $T=B[T]_BB^{-1}=\begin{bmatrix}2 & -1 \\ 1 & 2\end{bmatrix}\begin{bmatrix}1 & 0 \\ 0 & -1\end{bmatrix}\begin{bmatrix}0.4 & 0.2 \\ -0.2 & 0.4\end{bmatrix}=\begin{bmatrix}0.6 & 0.8 \\ 0.8 & -0.6\end{bmatrix}$
> 
> 【例2】线性变换 $T\left(\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}\right) = \begin{bmatrix} 3x_1 + x_3 \\ x_1 + x_2 \\ -x_1 - x_2 + 3x_3 \end{bmatrix}$，求它在 $\mathcal{B} = \left\{ \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}, \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}, \begin{bmatrix} 2 \\ 1 \\ 1 \end{bmatrix} \right\}$ 引入的 coordinate system 下看到的结果 $[T]_B$。
> 
> 解：$T = \begin{bmatrix} 3 & 0 & 1 \\ 1 & 1 & 0 \\ -1 & -1 & 3 \end{bmatrix}$，由 $B[T]_BB^{-1}=T$ 知 $[T]_B=B^{-1}TB=\begin{bmatrix} 3 & -9 & 8 \\ -1 & 3 & -3 \\ 1 & 6 & 1 \end{bmatrix}$.
> 
> 【例3】线性变换 $T:\mathbb{R}^3 \to \mathbb{R}^3$ 使得 $T\left(\begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}\right) = \begin{bmatrix} 1 \\ 2 \\ -1 \end{bmatrix}$，$T\left(\begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}\right) = \begin{bmatrix} 3 \\ -1 \\ 1 \end{bmatrix}$，$T\left(\begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}\right) = \begin{bmatrix} 2 \\ 0 \\ 1 \end{bmatrix}$.
> 求 $T$ 对应的矩阵。
> 
> 解：
> ![[Pasted image 20260430185035.png|557]]
> $\mathbf{b}_1$、$\mathbf{b}_2$、$\mathbf{b}_3$ 是 $\mathbb{R}^3$ 的 basis，可以构成 $\mathbb{R}^3$ 的 coordinate system。
> 设 $B=\{ \mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3\}$，则 $[T]_B([\mathbf{b}_1]_B)=[\mathbf{c}_1]_B$，其中 $[\mathbf{b}_1]_B=\mathbf{e}_1$，因此 $[\mathbf{c}_1]_B$ 就是 $[T]_B$ 的第1列。而 $[\mathbf{c}_1]_B=B^{-1}\mathbf{c}_1$. 同理可得 $[T]_B=\begin{bmatrix} B^{-1}\mathbf{c}_1 & B^{-1}\mathbf{c}_2 & B^{-1}\mathbf{c}_3 \end{bmatrix}=B^{-1}C$（记 $C=\begin{bmatrix} \mathbf{c}_1 & \mathbf{c}_2 & \mathbf{c}_3 \end{bmatrix}$）。
> 由 $B[T]_BB^{-1}=T$ 知 $T=BB^{-1}CB^{-1}=CB^{-1}=\begin{bmatrix} 1 & 0 & 2 \\ 0.5 & 1.5 & -1.5 \\ -0.5 & -0.5 & 1.5 \end{bmatrix}$.
