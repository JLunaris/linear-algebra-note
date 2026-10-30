
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
