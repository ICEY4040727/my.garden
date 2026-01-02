---
{"dg-publish":true,"permalink":"/specific-exercise/examples-of-applying-leibniz-s-rule-for-differentiation/","created":"2026-01-02T11:29:26.384+08:00","updated":"2026-01-02T13:47:39.209+08:00"}
---

求：
$$
\frac{d}{dx} \left[ \int_{a}^{x} (x - t) f'(t) \, dt \right]
$$
莱布尼茨法则对形如：
$$
\frac{d}{dx} \int_{a(x)}^{b(x)} g(x, t) \, dt 
$$
$$
= g(x, b(x)) \cdot b'(x) - g(x, a(x)) \cdot a'(x) +$$

$$
\int_{a(x)}^{b(x)} \frac{\partial}{\partial x} g(x, t) \, dt
$$
本题中：

$a(x) = a，常数 → a'(x) = 0$

$b(x) = x → b'(x) = 1$

$g(x, t) = (x - t) f'(t)$

代入：
$$
\frac{d}{dx} \int_{a}^{x} (x - t) f'(t) \, dt = (x - x) f'(x) \cdot 1 - 0 + \int_{a}^{x} \frac{\partial}{\partial x}[(x - t) f'(t)] \, dt
$$
第一项为0，第二项偏导：
$$
\frac{\partial}{\partial x}[(x - t) f'(t)] = f'(t)
$$
所以：
$$
= 0 + \int_{a}^{x} f'(t) \, dt = f(x) - f(a)
$$
结果一致。
综上，答案是f(x) - f(a)