---
{"dg-publish":true,"permalink":"/specific-exercise/extreme-sign-preserving-property-and-the-scope-of-limits-continuity/","created":"2026-01-01T22:00:52.850+08:00","updated":"2026-01-02T13:43:39.930+08:00"}
---

![](/img/user/picture/Pasted%20image%2020260101230924.jpg)
### 保号性得到去心领域内x的特征

已知$\lim\limits_{x \to x_0} \frac{f(x)}{(x - x_0)^2}=1$，由极限的局部保号性可知：

若$\lim\limits_{x \to x_0} g(x)=A\gt0$，则在$x_0$的某去心邻域内，$g(x)\gt0$。

对于$g(x)=\frac{f(x)}{(x - x_0)^2}$，因$\lim\limits_{x \to x_0} \frac{f(x)}{(x - x_0)^2}=1\gt0$，
所以存在$x_0$的某去心邻域$\mathring{U}(x_0,\delta)（\delta\gt0）$，使得当$x\in\mathring{U}(x_0,\delta)$时，$\frac{f(x)}{(x - x_0)^2}\gt0$。

又因为在去心邻域$\mathring{U}(x_0,\delta)$内，$(x - x_0)^2\gt0$恒成立，那么由$\frac{f(x)}{(x - x_0)^2}\gt0$和$(x - x_0)^2\gt0$可得：$f(x)\gt0$。



### 极限\连续决定$f(x_0)=\lim_{x\to x_0}f(x)$


再根据函数$f(x)$在$x = x_0$处连续，即$\lim\limits_{x \to x_0} f(x)=f(x_0)$，且$\lim\limits_{x \to x_0} \frac{f(x)}{(x - x_0)^2}=1$，分母$\lim\limits_{x \to x_0}(x - x_0)^2 = 0$，要使分式极限存在且为1，则分子$\lim\limits_{x \to x_0}f(x)=0$，所以

$f(x_0)=0$

因此，在x_0的某去心邻域$\mathring{U}(x_0,\delta)$内，$f(x)\gt f(x_0)=0$。