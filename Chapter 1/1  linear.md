
# Linear System

- **System**：根据输入产生输出（也称为**function**、**transformation**、**operator**）
- **Linear System**：线性系统

### 线性系统的两大特征

1. ==Preserving Scaling==：输入乘上`k`倍，输出也会乘上`k`倍
   ![[Pasted image 20260203165900.png]]

2. ==Preserving Addition==：输入`x1`输出`y1`，输入`x2`输出`y2`，则输入`x1+x2`输出`y1+y2`
   ![[Pasted image 20260203170041.png]]
   
> [!NOTE] Note
> 线性系统的两大特征：
> 1. 齐次性（Homogeneity）：若$f(x)=y$，则$f(k \cdot x)=k \cdot y$
> 2. 叠加性（Additivity）：若 $f(x_1) = y_1$ 且 $f(x_2) = y_2$，则有：$f(x_1 + x_2) = y_1 + y_2$

> 案例：判断是否为线性系统。
> 
> 【例1】$f(x)=x^2$ 不是线性系统：
> 
> 因为$f(k \cdot x)=k^2 x^2 \ne k \cdot x^2$，不满足“Preserving Scaling”
> 已知 $f(x_1)=x_1^2$，$f(x_2)=x_2^2$，而$f(x_1+x_2)=(x_1+x_2)^2 \ne x_1^2+x_2^2$，不满足“Preserving Addition”
> 
> 【例2】假设有如下系统，对矩阵进行transpose：
> ![[Pasted image 20260203175417.png]]
> 是否为线性系统？
> 
> 答案：是。
> 
> 【例3】假设有如下系统，接收一个函数，输出该函数的导数：
> ![[Pasted image 20260203175953.png]]
> 是否为线性系统？
> 
> 因为$[k \cdot f(x)]'=k \cdot f'(x)$，满足Preserving Scaling
> 因为$[f(x)+g(x)]'=f'(x)+g'(x)$，满足Preserving Addition
> 
> 综上，是线性系统。
> 
> 【例4】假设有如下系统，接收一个函数，输出该函数的定积分：
> ![[Pasted image 20260203181303.png]]
> 是否为线性系统？
> ![[Pasted image 20260203182741.png]]
> 
> 综上，是线性系统。

> [!NOTE] Note
> 微分和积分系统都属于线性系统

