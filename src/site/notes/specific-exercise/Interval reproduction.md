---
{"dg-publish":true,"permalink":"/specific-exercise/interval-reproduction/","created":"2025-12-15T01:12:13.176+08:00","updated":"2025-12-25T16:11:20.182+08:00"}
---

# 区间再现公式

## $\int_a^b f(x)dx = \int_a^b f(a+b-x) dx= \frac{x}{2} \int_a^b [f(x) + f(a+b-x)]dx$
## 证明区间再现公式

若我们能证明第一个等号成立，那么第二个等号自然成立

#### 证明 

$\int_a^b f(a+b-x)dx$

令 $a+b-x = t$ 可证。

## 从几何意义上理解该公式为何成立

$y=f(x)$  与  $y=f(a+b-x)$  显然是关于 $x = \frac{a+b}{2}$ 是对称的 

$y=f(x)=f(a+b-x)$  则该函数自身关于 $x = \frac{a+b}{2}$ 是对称的

![Pasted image 20251215030713.png](/img/user/Pasted%20image%2020251215030713.png)
## 从几何意义上理解为何转换后会更好算