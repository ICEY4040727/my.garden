---
{"dg-publish":true,"permalink":"/computational-technologes/integrals-some-computational-methodologies-of-the-integrals/","tags":["计算技巧","高数上"],"created":"2025-12-17T23:53:43.902+08:00","updated":"2026-01-02T13:47:29.019+08:00"}
---

# 不定积分

## 笔记0.2

### 做完一遍笔记发现，其实有理函数的核心就是凑微分

$\displaystyle \int g\ [u(x)]\cdot u'(x)\ dx=\int g(u)\ du$

### 凑微分的三大步：换元、代数变换、分部

于是我重新整理了如下的笔记


#### 1.换元-打开局面
##### 1.三角换元
[[specific-exercise/Indefinite Integral - Rational Fractions - Substitution Method#^e103c6\|../specific-exercise/Indefinite Integral - Rational Fractions - Substitution Method#^e103c6]]
##### 2.倒代换
[[specific-exercise/Indefinite Integral - Rational Fractions - Substitution Method#^17a308\|../specific-exercise/Indefinite Integral - Rational Fractions - Substitution Method#^17a308]]



#### 2.分部积分

###### 1.避过难以计算的因式
[[specific-exercise/Indefinite Integral - Rational Fractions - Integration by Parts#^f1c7a1\|../specific-exercise/Indefinite Integral - Rational Fractions - Integration by Parts#^f1c7a1]]
###### 2.降次分母、升次分子
[[specific-exercise/Indefinite Integral - Rational Fractions - Factorization - 1\|分部积分降分母次数]]
###### 3.积分重现


#### 3.代数变换

###### 1.共轭
[[specific-exercise/Indefinite Integral - Rational Fractions - Partial Fractions#^2daebd\|共轭裂项]]
[[specific-exercise/Indefinite Integral - Rational Fractions - Partial Fractions#^8a000f\|三角函数同乘共轭，减分母项数]]
###### 2.配凑
[[specific-exercise/Indefinite Integral - Rational Fractions - Completing the Square\|../specific-exercise/Indefinite Integral - Rational Fractions - Completing the Square]]
[[specific-exercise/Indefinite Integral - Trigonometric Functions - Special Methods#^dcb34e\|不定积分-三角函数-配凑]]
###### 3.二倍角公式
[[specific-exercise/Indefinite Integral - Trigonometric Functions - Special Methods#^b945bc\|二倍角公式]]
###### 4.立方和/立方差 展开
[[specific-exercise/Indefinite Integral - Rational Fractions - Factorization - 2#^afc446\|立方展开]]
###### 5.换元法打开局面
[[specific-exercise/Indefinite Integral - Rational Fractions - Substitution Method\|../specific-exercise/Indefinite Integral - Rational Fractions - Substitution Method]]
###### 6.合理拆并项
[[specific-exercise/Reasonable split and merge items\|../specific-exercise/Reasonable split and merge items]]


# 定积分

## 1.使用N-L公式进行计算

### $\int_a^b f(x)dx = F(b) - F(a)$

#### 使用场景

函数 $f(x)$ 不仅在区间 $[a,b]$ 上**有原函数**，而且还**可积**，同时该原函数还是**初等函数** ( 即可以求出$F(x)$ 

#### 【1】先将不定积分全部算出（消除发散的定积分）
#### 【2】以无定义点为限拆分区间进行计算

### 结合N-L的一级技巧

#### 1.定积分的几何意义(局限性大)
[[specific-exercise/Definite Integral - Calculation Combining NL - Geometric Meaning\|../specific-exercise/Definite Integral - Calculation Combining NL - Geometric Meaning]]
#### 2.奇偶性

#### 3.周期性

#### 4.区间再现公式
[[specific-exercise/Interval reproduction\|../specific-exercise/Interval reproduction]]

##### 一种通过倒代换实现区间再现的方式

#### 5.Wallis公式
[[specific-exercise/Wallis公式\|../specific-exercise/Wallis公式]]
#### 6.教科公式
[[specific-exercise/Definite-Integral - Calculation-Combined-with-NL - Textbook-Formula\|../specific-exercise/Definite-Integral - Calculation-Combined-with-NL - Textbook-Formula]]

#### 二级技巧
##### 代换
###### 指数代换

###### 三角代换

###### 双曲代换

##### 含参积分

###### 引入参数求导（莱布尼茨公式）
[[Computational technologes/Integral with parameters\|Integral with parameters]]

###### 留数法

###### gamma与beta函数法



















## 笔记0.1

### 1.通用方法

#### - 裂项 + 待定系数

##### 1.对假分式进行通分
##### 3.对真分式因式分解

###### 待定系数型 *好像还有个什么列表法留数法回头学吧……*

###### $\frac{A}{(x-a)^k}$ 型

[[specific-exercise/Indefinite Integral - Rational Fractions - Factorization - 1#^be3592\|../specific-exercise/Indefinite Integral - Rational Fractions - Factorization - 1#^be3592]]
###### $\frac{bx+c}{(x^2 + px+q)^{1 or 2}}$型

[[specific-exercise/Indefinite Integral - Rational Fractions - Factorization - 2#^4a37e8\|../specific-exercise/Indefinite Integral - Rational Fractions - Factorization - 2#^4a37e8]]

##### 4.裂项
[[specific-exercise/Indefinite Integral - Rational Fractions - Partial Fractions\|../specific-exercise/Indefinite Integral - Rational Fractions - Partial Fractions]]


## 2.三角有理函数的积分

### 1.通法-万能公式换元

#### $\sin x=\frac{2t}{1+t^2}$

#### $\cos x=\frac{1-t^2}{1+t^2}$

#### $\tan x = \frac{2t}{1-t^2}$

#### $x=\frac{2}{1+t^2}\ dt$

### 2.特殊方法

#### 1.减分母
	三角函数中减分母的项数有三种方法：同乘共轭、二倍角、和差化积
##### 同乘共轭
[[specific-exercise/Indefinite Integral - Rational Fractions - Partial Fractions#^8a000f\|三角函数同乘共轭，减分母项数]]
##### 二倍角公式
[[不定积分-三角函数-二倍角\|不定积分-三角函数-二倍角]]
##### 和差化积
##### 诱导公式（过于基础了。。。）

#### 2.按照对称方式凑元