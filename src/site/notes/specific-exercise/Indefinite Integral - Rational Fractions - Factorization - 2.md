---
{"dg-publish":true,"permalink":"/specific-exercise/indefinite-integral-rational-fractions-factorization-2/","created":"2025-12-18T01:04:53.342+08:00","updated":"2025-12-25T16:42:32.428+08:00"}
---


# 1.$\frac{bx+c}{(x^2 + px+q)^{1}}$
{ #4a37e8}


$\displaystyle \int\frac{x+3}{x^2+2x+4}\ dx$

$\displaystyle =\int \frac{\frac{1}{2}(2x + 2)+2}{x^2+2x+4}\ dx$

$\displaystyle = \frac{1}{2} \int \frac{2x+2}{x^2+2x+4}\ dx +2\int\frac{1}{x^2+2x+4}\ dx$

$\displaystyle = \frac{1}{2}\ln(x^2+2x+4) +2\int\frac{1}{(x+1)^2 +(\sqrt3)^2}\ dx$

$\displaystyle = \frac{1}{2}\ln(x^2 + 3x+4) + \frac{2}{\sqrt3}\arctan(\frac{x+1}{\sqrt3}) + C$


# 2.$\frac{bx+c}{(x^2 + px+q)^{2}}$

$\displaystyle \int\frac{x+2}{(x^2+2x+10）^2}\ d\ x$

$\displaystyle =\ -\frac{1}{2}\int 1\ d\ \frac{1}{x^2+2x+10}\ +\ \int\frac{1}{(x^2+2x+10）^2}\ d\ x$

$\displaystyle =\ -\frac{1}{2}\frac{1}{x^2+2x+10}\ + \int \frac{1}{((x+1)^2\ +3^2)^2}\ dx$

到这一步，后一项如何配凑已经呼之欲出了

[[specific-exercise/Indefinite Integral - Rational Fractions - Completing the Square\|Indefinite Integral - Rational Fractions - Completing the Square]]

###### *参考如下*

$\int \frac{1}{((x+1)^2\ +3^2)^2}\ dx$

$=\int\frac{1}{(t^2\ +3^2)^2}\ d\ t$

$=\frac{1}{9}\int\frac{9+t^2-t^2}{(t^2+3^2)^2}\ dt$
**然后分部积分降次分母**
[[specific-exercise/Indefinite Integral - Rational Fractions - Factorization - 1#^36ff0c\|Indefinite Integral - Rational Fractions - Factorization - 1#^36ff0c]]


# $\int \frac{1+x^4}{1+x^6}\ dx$
{ #afc446}


$\displaystyle= \int\frac{1+x^4+x^2-x^2}{(1+x^2)(1-x^2+x^4)}\ dx$

>[!info] 因式分解不要忘了 立方和/立方差 展开

$\displaystyle = \int \frac{1}{1+x^2}\ +\ \frac{x^2}{1+x^6}\ dx$




 

