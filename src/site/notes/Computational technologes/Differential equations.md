---
{"dg-publish":true,"permalink":"/computational-technologes/differential-equations/","created":"2025-12-25T20:44:41.860+08:00","updated":"2025-12-27T13:43:27.431+08:00"}
---

# 一.基本概念

## 1.微分方程

含有导数（或微分）的方程式，称为微分方程，比如$y''+y=x$

## 2.微分方程的阶 

微分方程中所含导数的最高阶数，称为该微分方程的阶，比如$y'+y=\sin x$是一阶微分方
{ #fd6530}

程，$y'+y''=x$是二阶微分方程. 

## 3.微分方程的解

使得微分方程恒成立的函数，称为该微分方程的解，比如 $y=x$ 就是 $y'+y''=x$ 的一个

解. 

## 4.通解与特解

若微分方程的解中，所含有的**独立任意常数**的**个数**恰好等于该微分方程的[阶数](#^fd6530)，则称这样
的解为该微分方程的通解；不含任意常数的解，称为特解.

# 二、一阶微分方程——*一阶导*

## （一）可分离变量的微分方程 

### 形式

$$
\displaystyle f(x)dx=g(y)dy
$$

### 解法

easy，直接积分

## （二）齐次微分方程 

### 形式

$$
\displaystyle f(\frac{y}{x})d\frac{y}{x}=g(y)dy
$$

### 解法

$$
令\frac{y}{x}=u
$$

解如下积分

$$
\int\frac{1}{f(u)-u}du=\int\frac{1}{x}dx
$$

## （三）一阶线性齐次微分方程 

*注 1：此处的“线性”，指的是**待求函数及其导数**的**幂次**均为1*

*注2：此处的“齐次”，指的是等号右边的**自由项**为0，和线性代数里“齐次方程组”中的“齐次”同义*

### 形式
$$\displaystyle y'+P(x)y=0$$

### 解法

$$\displaystyle y=Ce^{-\int P(x)dx}$$


## （四）一阶线性非齐次微分方程 
{ #f09730}


### 形式

$$\displaystyle y'+P(x)y=Q(x)$$

### 解法

$$\displaystyle y=e^{-\int P(x)\ dx}\ (\int Q(x)\ e^{\int P(x)dx}\ d\ x+C)$$
## （五）伯努利方程 

### 1. 形式

形如 $y' + P(x)y = Q(x)y^n$ （其中 $n \neq 0, 1$）的方程称为**伯努利方程**。

### 2. 解法步骤

1. 两边除以 $y^n$，得到：
   $$y^{-n}y' + y^{1-n}P(x) = Q(x)$$

2. 令 $z = y^{1-n}$，则 $\frac{dz}{dx} = (1-n)y^{-n}\frac{dy}{dx}$

3. 代入后方程变为：
   $$\frac{1}{1-n}\frac{dz}{dx} + P(x)z = Q(x)$$
4. 回到了[一阶线性非齐次方程](#^f09730)

## 三、可降阶的高阶微分方程

### （一）$y^n=f(x)$

没什么可说，一直求导就好

### （二）$f(x,y',y'')=0$ 

令$y'=p$ ,原式降阶为一阶微分方程

### （三）$f(y,y',y'')=0$

令$y'=p$ ,原式降阶为一阶微分方程

# 四、二阶常系数齐次线性微分方程

## 形式

$\displaystyle y''+py'+qy=0（其中p，q是常数）$的方程

## 解法——特征根

将$\lambda^2+p\lambda+q=0$作为特征方程，其根称为特征根. 

[[一些思考/Why can the characteristic root method be used to solve differential equations\|为什么能用特征根解微分方程？]]

### 1.$\lambda_1\neq \lambda_2$

$y=C_1e^{\lambda_1 x}+C_2e^{\lambda_2 x}$

### 2.$\lambda_1 = \lambda_2$

$y=(C_1+C_2x)e^{\lambda x}$

### 3. $\lambda_{1,2} = \alpha+i\beta$

$y=e^ax(C_1\sin\beta+C_2\cos\beta)$

# 五、二阶常系数非齐次线性微分方程

## 形式 $f(x) = P_n(x)e^{kx}$（$P_n(x)$代表关于$x$的$n$次多项式）

## 解法
① 当$k$不是特征根时，此时假设$y^* = (a_0 + a_1x + \dots + a_nx^n)e^{kx}$，其中$a_0,a_1,\dots,a_n$均是待求系数

对$y^*$求导，得到$(y^*)'$、$(y^*)''$以后，代回原方程，得到$(y^*)'' + p(y^*)' + qy^* = P_n(x)e^{kx}$，最后根据*等号左右两边对应系数相等* 的原则，可求出所有的系数$a_0,a_1,\dots,a_n$，便可求出$y^*$

② 当$k$是单特征根时，此时假设$y^* = x(a_0 + a_1x + \dots + a_nx^n)e^{kx}$；
 
③ 当$k$是二重特征根时，此时假设$y^* = x^2(a_0 + a_1x + \dots + a_nx^n)e^{kx}$

## 形式  若 $f(x) = e^{\alpha x}[P_l(x)\cos\beta x + P_s(x)\sin\beta x]$，记
$$
n = \max\{l, s\}
$$
 当$\alpha + i\beta$不是特征根时，设特解形式为：
$$
y^* = e^{\alpha x}[H_n(x)\cos\beta x + Q_n(x)\sin\beta x]
$$
    
 当$\alpha + i\beta$是特征根时，设特解形式为：
$$
y^* = xe^{\alpha x}[H_n(x)\cos\beta x + Q_n(x)\sin\beta x]
$$



# 六、n阶常系数齐次线性微分方程 