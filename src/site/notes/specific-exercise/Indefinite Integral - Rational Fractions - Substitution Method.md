---
{"dg-publish":true,"permalink":"/specific-exercise/indefinite-integral-rational-fractions-substitution-method/","created":"2025-12-18T01:51:04.286+08:00","updated":"2026-01-02T02:49:16.758+08:00"}
---


## 大概就是。。。遇到长得怪怪拆不开的东西都先换一下元试试。。


$\displaystyle \int \frac{1}{\sqrt \tan x}\ dx$

$令t=\sqrt \tan x$

$= \displaystyle\int \frac{1}{t} \ d\ \arctan\ (t^2)$

$\displaystyle = 2 \int \frac{1}{1+t^4} \ dt$

## 三角换元
{ #e103c6}


$\displaystyle \int\frac{x^2}{(a^2+x^2)^2}dx\ (a>0)$

$\displaystyle令x=atant$

$\displaystyle=\int\frac{a^2\ (\tan t)^2}{a^4(\sec t)^4}\cdot a (\sec t)^2\ d\ t$

$\displaystyle= \frac{1}{a}\int(\sin t)^2  dt$

### 三角万能公式换元

#### $\displaystyle\sin x=\frac{2t}{1+t^2}$

#### $\displaystyle\cos x=\frac{1-t^2}{1+t^2}$

#### $\displaystyle\tan x = \frac{2t}{1-t^2}$

#### $\displaystyle x=\frac{2}{1+t^2}\ dt$


#### 1.$\displaystyle\int \frac{1}{3+5\cos x}\ dx$

$\displaystyle= \int \frac{1}{3+5\frac{(1-t^2)}{1+t^2}}\ \cdot \frac{2}{1+t^2}dt$

$\displaystyle= \int\frac{1}{4-t^2}\ dt$

$\displaystyle= -\ln|\frac{t-2}{t+2}|+C$

$\displaystyle=-\ln|\frac{\tan \frac{x}{2}-2}{\tan\frac{x}{2}+2}|+C$

#### 2.$\displaystyle\int\frac{1}{1+\sin x+\cos x}\ dx$

$令t=\tan\frac{x}{2}$

$\displaystyle =\int\frac{1}{1+\frac{2t}{t^2+1}+\frac{1-t^2}{t^2+1}}\ \cdot\frac{2}{1+t^2}dt$

$\displaystyle = \int \frac{1}{t+1}d\ t$


## 倒代换
{ #17a308}



### $\displaystyle \int \frac{1}{x^8 (1+x^2)}\ dx$

$令x=\frac{1}{t}$

$\displaystyle = \int{t^8(1+\frac{1}{t^2})}\ d\frac{1}{t}$

$\displaystyle = -\int t^6 - \int \frac{1}{x^4} dt$


### $\displaystyle I = \int_0^{+\infty} \frac{1}{(1+x^2)(1+x^\alpha)} \, dx, \quad \alpha \ne 0$

$$
令x = \frac{1}{t} \Rightarrow dx = -\frac{1}{t^2} dt
$$

$$当 x \to 0^+ 时，t \to +\infty；$$$$
当 x \to +\infty 时，t \to 0^+。
$$
所以积分变为：
$$
I = \int_{+\infty}^{0} \frac{1}{(1+(1/t)^2)(1+(1/t)^\alpha)} \cdot \left(-\frac{1}{t^2}\right) dt = \int_0^{+\infty} \frac{1}{(1 + \frac{1}{t^2})(1 + t^{-\alpha})} \cdot \frac{1}{t^2} dt
$$
代入：
$$
I = \int_0^{+\infty} \frac{1}{\frac{t^2 + 1}{t^2} \cdot \frac{t^\alpha + 1}{t^\alpha}} \cdot \frac{1}{t^2} dt = \int_0^{+\infty} \frac{t^2 \cdot t^\alpha}{(t^2 + 1)(t^\alpha + 1)} \cdot \frac{1}{t^2} dt = \int_0^{+\infty} \frac{t^\alpha}{(t^2 + 1)(t^\alpha + 1)} dt
$$
即：
$$
I = \int_0^{+\infty} \frac{x^\alpha}{(1+x^2)(1+x^\alpha)} dx \tag{2}
$$
和原式相加：
$$
2I = \int_0^{+\infty} \left[ \frac{1}{(1+x^2)(1+x^\alpha)} + \frac{x^\alpha}{(1+x^2)(1+x^\alpha)} \right] dx = \int_0^{+\infty} \frac{1 + x^\alpha}{(1+x^2)(1+x^\alpha)} dx = \int_0^{+\infty} \frac{1}{1+x^2} dx
$$
这个积分是标准结果：
$$
\int_0^{+\infty} \frac{1}{1+x^2} dx = \left. \arctan x \right|_0^{+\infty} = \frac{\pi}{2} - 0 = \frac{\pi}{2}
$$
所以：
$2I = \frac{\pi}{2} \Rightarrow I = \frac{\pi}{4}$
