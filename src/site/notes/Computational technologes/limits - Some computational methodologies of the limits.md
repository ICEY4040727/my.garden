---
{"dg-publish":true,"permalink":"/computational-technologes/limits-some-computational-methodologies-of-the-limits/","tags":["计算技巧","高数上"],"created":"2025-12-14T18:44:11.578+08:00","updated":"2026-01-02T13:31:28.810+08:00"}
---

# 极限的计算

## 函数极限的计算

### 两个重要极限

#### 1. $\lim_{x\rightarrow 0}\ \frac{\sin x}{x}=1$

#### 2.  $\lim_{x\rightarrow 0}(1+x)^{\frac{1}{x}} =e$
,由此也可推出 $\lim_{x\rightarrow _infty} (1+\frac{1}{x})^x=e$

### 三个等价无穷小

#### 1.$x\sim\sin x\sim\tan x\sim\arcsin x\sim\arctan x\sim\ln(1+x)\sim e^x-1\sim\ln(x+\sqrt{1+x^2})$

#### 2. $1-\cos x \sim \frac{1}{2}x^2， 1-\cos^k x\sim\frac{k}{2}x$

#### 3. $(1+x)^a -1\sim ax$

应用
[[specific-exercise/等价无穷小代换\|../specific-exercise/等价无穷小代换]]


### 洛必达法则

1. 其实只要分母是$\infty$，就可以直接洛必达了
2. 洛必达法则中等号右侧的结果，可以是具体的数字，也可以是$\infty$，结论均成立； 
3. 若 $\lim\frac{f'(x)}{g'(x)}$ 振荡，则 $\lim\frac{f(x)}{g(x)}$ 可能存在，也可能不存在，此时洛必达法则失效，须更换计算方法.
4. 利用洛必达法则，可以轻松判断常见函数的趋向速度.当 $x\rightarrow +\infty$ 时，有$e^x >> x^a >> \ln x$
5. 当n足够大时，有$n^n>>n!>>2^n>>n^2>>\ln n>>\ln\ln n$
### 抓大头

[[specific-exercise/无穷大根式估值1\|../specific-exercise/无穷大根式估值1]]

#### 七种极限未定式求解

##### 1. $\frac{0}{0}$

约分-非零代入-有理化-等价无穷小-洛必达

##### 2. $\frac{\infty}{\infty}$

有理化-抓大头-洛必达

##### 3. $\infty - \infty$

- 分式-通分 → $\frac{0}{0}$
- 根式-有理化 → $\frac{\infty}{\infty}$
- 倒代换
- 负代换

##### 4. $0*\infty$

取倒数 → $\frac{0}{0}$ 或 $\frac{\infty}{\infty}$

##### 5. $1^{\infty}$

$$
\lim_{x\to0}(1+A)^B = e ^ {\lim_{x\to0} \ (\ A*B\ )}
$$
##### 6. $\infty ^{0}或0^{0}$
$$
\lim f(x)^{g(x)} = e^{\lim g(x)\ *\ \ln {f(x)}}
$$

### 泰勒展开

![](/img/user/picture/Pasted%20image%2020251228171651.png)
![](/img/user/picture/Pasted%20image%2020251228171709.png)
![](/img/user/picture/Pasted%20image%2020251228171727.png)



## 数列的极限

### 概念理解

1. 数列极限只有一个方向
2. 数列极限不能用洛必达求
3. 函数极限→数列极限，数列极限不能推函数极限
4. 数列极限收敛的充要条件是数列的奇偶项都收敛于同一数字

### 极限的存在准则

#### 单调有界准则

**若$\{a_n\}$单调递增且有上界，则$\{a_n\}$收敛; 若单调递减且有下界，则收敛

**如何证明单调性和有界性**

1.  一般用来证明"$a_{n+1}=f(a_n)$"这类递推式的极限存在

#### 夹逼准则

若 $a_n\leq b_n\leq c_n$，且 $a_n=c_n=A$ 则 $\lim b_n$一定存在且 $\lim b_n = A$

1. 可以推广到函数极限
2. 一般用来计算数列极限的 和
3.


