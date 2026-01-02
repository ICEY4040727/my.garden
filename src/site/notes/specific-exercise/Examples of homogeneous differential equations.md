---
{"dg-publish":true,"permalink":"/specific-exercise/examples-of-homogeneous-differential-equations/","created":"2026-01-02T10:08:21.022+08:00","updated":"2026-01-02T13:44:52.559+08:00"}
---

$$
xy \frac{dy}{dx} = x^2 + y^2
$$
两边同时除以  $x （注意  x \ne 0 ）$：
$$
y \frac{dy}{dx} = x + \frac{y^2}{x}
$$
整理为：

$$
\frac{dy}{dx} = \frac{x}{y} + \frac{y}{x}
$$
观察右边： $\frac{x}{y} + \frac{y}{x}$  是关于  $\frac{y}{x}$  的函数，说明这是齐次微分方程。

2. 使用变量代换法

令   $y = ux$  ，其中   $u = u(x)$   是新未知函数。

则：
$$
\frac{dy}{dx} = u + x \frac{du}{dx}
$$


$$
x \frac{du}{dx} = \frac{1}{u}
$$
3. 分离变量并积分

分离变量：
$$
u\, du = \frac{1}{x}\, dx
$$
两边积分：
$$
\int u\, du = \int \frac{1}{x}\, dx
$$
$$
\frac{1}{2} u^2 = \ln|x| + C
$$
代回  $u = \frac{y}{x}$ ：
$$
\frac{1}{2} \left( \frac{y}{x} \right)^2 = \ln|x| + C
$$
两边乘以  $2x^2$ ：
$$
y^2 = 2x^2 (\ln|x| + C)
$$
4. 利用初始条件求常数  C 

已知：当  x=1  时， y=2 ，代入：
$$
2^2 = 2 \cdot 1^2 (\ln 1 + C)
\Rightarrow 4 = 2(0 + C)
\Rightarrow C = 2
$$
5. 写出特解

代入  C=2 ：
$$
y^2 = 2x^2 (\ln|x| + 2)
$$
6. 对照选项

- A.   y = x^2(\ln|x| + 2)   → 形式错误，应是  y^2 
- B.   y^2 = x^2(\ln|x| + 4)   → 系数不对，应是2
- C.   y = \frac{1}{2}x^2(\ln|x| + 4)   → 形式错误
- D.   y^2 = 2x^2(\ln|x| + 2)   → ✅ 完全匹配

综上，答案是D。
