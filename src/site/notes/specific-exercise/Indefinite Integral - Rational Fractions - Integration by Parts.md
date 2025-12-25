---
{"dg-publish":true,"permalink":"/specific-exercise/indefinite-integral-rational-fractions-integration-by-parts/","created":"2025-12-21T20:54:07.734+08:00","updated":"2025-12-25T16:42:22.282+08:00"}
---

# 口诀

## 对--反--幂--指--三

**保留易求导的部分,积入易积分的部分**

### 1.用以避免难积分因式
{ #f1c7a1}


#### 1.$\displaystyle\int x\arctan x\ dx$

$\displaystyle = \int \arctan x\ d\ \frac{1}{2}x^2$

$\displaystyle= \frac{1}{2}(x\cdot\arctan x)-\int x^2\cdot\frac{1}{1+x^2}\ dx$

#### 2.$\displaystyle\int x\ln(1+x^2)\arctan x\ d\ x$

$\displaystyle=\frac{1}{2}\int\ln(1+x^2)\arctan x\ d\ x^2$

$\displaystyle=\frac{1}{2}[\ln(1+x^2)\arctan x\cdot\ x^2]-\int x^2\ d\  \ln(1+x^2)\arctan x$

>[!info] 记得乘法的求导法则：前导后不导……

### 2.降次分母、升次分子
[[specific-exercise/Indefinite Integral - Rational Fractions - Factorization - 1\|分部积分降分母次数]]

### 3.积分重现

**出现$e^x \cdot \sin x / e^x \cdot \cos x$等，一直将$e^x$向后提

#### 1.$\displaystyle\int e^x\sin x\ dx$

$\displaystyle=\int\sin x\ d\ e^x$

$\displaystyle=e^x\cdot\sin x-\int e^x\cos x\ d\ x$

$\displaystyle=e^x\cdot\sin x-\int \cos x\ d\ e^x$

$\displaystyle=e^x\cdot\sin x-\cos x\ \cdot e^x-\textcolor{red}{\underline{\int e^x\sin x\ dx}}$

#### 2.$\displaystyle \int \ln\ln x + \frac{1}{\ln x}\ d\ x$

$\displaystyle=\int\ln\ln x dx+\int x\ d\ \ln\ln x$

$\displaystyle = \int\ln\ln x\ d\ x + x\cdot\ln\ln x-\textcolor{\red}{\underline{\int\ln\ln x\ d\ x}}$

#### 3.$f''(x)$连续，$f'(x)\neq0$，求$\displaystyle\int[\frac{f(x)}{f'(x)}-\frac{f^2(x)\cdot f''(x)}{[f'(x)]^3}]\ d\ x$

$\displaystyle=\int\frac{f(x)}{f'(x)}\ dx-\int\frac{f^2(x)\cdot f''(x)}{[f'(x)]^3}\ dx$

$\displaystyle=\int\frac{f(x)}{f'(x)}\ dx+\frac{1}{2}\int{f^2(x)}\ d\ \frac{1}{[f'(x)]^2}$

$\displaystyle=\textcolor{\red}{\int\frac{f(x)}{f'(x)}\ dx}+\frac{1}{2}{f^2(x)}\cdot \frac{1}{[f'(x)]^2}-\textcolor{\red}{\int\ \frac{1}{[f'(x)]^2}\cdot f(x)\cdot f'(x)\ dx}$



