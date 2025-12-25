---
{"dg-publish":true,"permalink":"/concept/the-concept-and-properties-of-definite-integrals/","tags":["概念","高数上"]}
---

---
aliases: 定积分概念
---
#概念 



# The Concept and Properties of Definite Integrals
## 1.Definition and Geometric Meaning
### 1.Definition of Calculus

设函数在[a, b]上**有界**，在[a, b]中任意插入若干个分点

$a=x_1<x_2<…<x_{n-1} < x_{n} =b$

为了使所有区间的长度无限缩小，我们取$n\rightarrow\infty$，然后对每段区间求和

$S=\lim_{n\rightarrow\infty} \sum_{i=1}^{n} f(\xi_i)\Delta x_{i}$

称记对该和（黎曼和）的极限为大区间的定积分

$I=\int_{a}^{b} f(x)dx=\lim_{\lambda\rightarrow0}\sum_{i=1}^{n} f(\xi_i)\Delta x_i$

#### 一些名词

- **被积函数** $f(x)$
- **被积表达式** $f(x)dx$
- **积分变量** $x$ 
- **积分上、下限** $a, b$
- **积分区间** $[a,b]$

#### 概念辨析：在区间$[a,b]$上存在原函数 or 在区间$[a,b]$上可积分

在区间$[a, b]$上函数可以存在原函数却不可积；也能够可积却不存在原函数；即使存在原函数，其原函数也可能非初等函数。
### 2.Geometric properties
<p>积分是函数与x轴形成的的闭合有向面积之和</p>
![Pasted image 20251214180608.png](/img/user/picture/Pasted%20image%2020251214180608.png)

## 2.Judgment rules(Determine if points can be earned)

### 定理1
设$f(x)$在区间$[a, b]$上连续，则$f(x)$在$[a, b]$上可积。

### 定理2
设$f(x)$在区间$[a, b]$上有界，且只有有限个间断点，则$f(X)$在$[a, b]$上可积

## 3.Computational rules
### 1.前置规则
1.设$f(x)$在区间\[a, b]上连续，则$f(x)$在\[a, b]上可积。
2.设$f(x)$在区间$[a, b]$上有界，且只有有限个间断点

#### 1.积分的加法

**设$\alpha$与$\beta$均为常数，则**
 
$\int_{a}^{b}[ \alpha f(x)+\beta g(x) ] dx = \alpha\int_{a}^{b}f(x)dx + \int_{a}^{b}g(x)dx$

- 证明方法即：将积分符号拆分为求和极限符号后利用 [[Computational technologes/limits - Some computational methodologies of the limits\|极限计算技巧]] 来拆分

#### 2.积分的区间加法

**设$a<c<b$，则**

$\int_{a}^{b} f(x)dx = \int_{a}^{c} f(x)dx+ \int_{c}^{b} f(x)dx$

#### 3.积分的线性性质对常函数的推论

**如果在区间$[a,b]$上**$f(x)\equiv1$

$\Rightarrow \int_{a}^{b}1dx = \int_{a}^{b} dx = b-a$

- 证明方法：利用积分的线性性质，被积函数恒等于某数，则被积函数为一个常数，可以将该常数 ”提出“到积分式子外。

#### 4.【被积函数】 和 【对被积函数的积分】 具有同号性

**在区间$[a, b]$上**$f(x)\geq0$  $\Rightarrow \int_{a}^{b} f(x)dx \geq 0$

- 证明：$\because$在区间$[a,b]$上$f(x)\geq0$
	
	$\therefore f(\xi_i)\geq0    \qquad(i=1,2,…,n)$
	
	又$\because\Delta x_i\geq0\quad(i=1,2,…,n)$

	$\therefore \sum_{i=1}^{n} f(\xi_i) \Delta x_i \geq0$，

	##### 1.推论1 【被积函数】的大小影响【对被积函数的积分】的大小（用于两对积分与被积函数的大小比较）
	
	##### 2.推论2 【积分的绝对值】$\leq$【绝对值的积分】
	
	$\lvert\int_{a}^{b} f(x)dx\rvert \leq \int_{a}^{b} \lvert f(x) \rvert dx \quad(a<b)$


#### 5.用最大值最小值估计积分值

**设M和m分别是函数$f(x)$在区间$[a,b]$上的最大值和最小值，则**

$m(b-a) \leq \int_{a}^{b} f(x)dx \leq M(b-a) \quad (a<b)$

#### 6.定积分中值定理

**如果函数$f(x)$在积分区间$[a,b]$上连续，那么在$[a,b]$上至少存在一个点$\xi$，使得：**

$\int_{a}^{b} f(x)dx = f(\xi) (b-a) \quad(a<\xi<b)$

该式为积分中值公式


### 2.基本规则

#### 1.如果函数$f(x)$在区间$[a,b]$上连续，那么，$f(x)$在区间$[a,b]$上的定积分= $f(x)$原函数在区间$[a,b]$上的增量

**$F(b)-F(a)$**

#### 2.积分上限的函数及导数

为了建立积分与微分的关系，我们对变上限积分（$f(x)$的一个原函数）进行探讨。

*关于为什么要探讨变上限积分的思考在这里*[[一些思考/Definite integral, indefinite integral and differential\|Definite integral, indefinite integral and differential]]










