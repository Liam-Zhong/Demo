+++
title = '方程'
date = 2024-06-22T20:38:44+08:00
math = true                                
draft = false
comments = true
+++

## 差分方程

一阶线性差分方程的一般形式为：
$ y_{x+1} = ay_x + f(x)$

1. **齐次方程：**
   如果 $f(x) = 0$，方程变为齐次方程：
   $ y_{x+1} = ay_x $
   其解为：<br>
   $ \color{red}{y_x = C a^x} $

   

2. **非齐次方程：**

   - 如果 $f(x) = b$：

   递推得：

   $$ \color{red}{f(n) = \begin{cases} bx+c & \text{如果 } a = 1 \\\frac{b}{1-a}+C\cdot a^x & \text{如果 } a \neq 1 \end{cases}}$$

   - 如果 $f(x) = (a_0 + a_1x + \cdots + a_nx^n)b^x$

   其解为：
   
   $y_x^* = x^k((a_0 + a_1x + \cdots + a_nx^n)b^x)$
