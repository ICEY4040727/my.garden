---
{"dg-publish":true,"permalink":"/specific-exercise/equivalence-of-infinitesimals-transitivity/","created":"2026-01-01T21:31:16.958+08:00","updated":"2026-01-02T13:29:45.763+08:00"}
---

# 结果
### 被积函数的等价无穷小可传递到积分结果

当计算变上限积分的无穷小阶数时，若被积函数f(t)在$t\to0$时可等价于一个幂函数$g(t)\sim at^m（a\neq0，m>0）$，则：

$$\int_0^x f(t)dt \sim \int_0^x g(t)dt \quad (x\to0)$$

即积分的等价无穷小等于被积函数等价无穷小的积分。

## 推导

我们从极限的定义出发，证明这一传递性：

1. 已知条件

设 $f(t)$ 和 $g(t)$ 在$t=0$附近连续（保证积分存在），且：
$$
\lim_{t \to 0} \frac{f(t)}{g(t)} = 1 \implies f(t) = g(t) \cdot [1 + \alpha(t)]
$$
其中 $\alpha(t) \to 0（t \to 0）$（这是等价无穷小的定义式变形）。

2. 展开积分

将 $f(t)$ 代入积分 $I(x)$：
$$
I(x) 
= \int_0^x f(t)dt 
= \int_0^x g(t) \cdot [1 + \alpha(t)]dt 
= \int_0^x g(t)dt + \int_0^x g(t)\alpha(t)dt
$$
3. 分析第二项的阶数（关键！）

我们需要证明第二项是比第一项更高阶的无穷小（即第二项除以第一项的极限为0），这样第一项就主导了积分的结果，从而 $I(x) \sim \int_0^x g(t)dt$。

假设 g(t) 是幂函数（这是无穷小比较的常见场景）：$g(t) = at^m（a \neq 0，m > 0）$，则：

第一项：$\int_0^x g(t)dt = a \cdot \frac{x^{m+1}}{m+1}$（幂函数积分，阶数为 m+1）；

第二项：$\int_0^x g(t)\alpha(t)dt = a \int_0^x t^m \cdot \alpha(t)dt$。

现在分析第二项的阶数：

由于 $\alpha(t) \to 0（t \to 0）$，对任意$\epsilon > 0$，存在$\delta > 0$，当 $|t| < \delta$时，$|\alpha(t)| < \epsilon$。因此：
$$
\left| \int_0^x t^m \alpha(t)dt \right| \leq \int_0^{|x|} t^m |\alpha(t)|dt < \epsilon \int_0^{|x|} t^m dt = \epsilon \cdot \frac{|x|^{m+1}}{m+1}
$$
两边除以第一项的绝对值 $|a| \cdot \frac{|x|^{m+1}}{m+1}$，得：
$$
\left| \frac{\int_0^x g(t)\alpha(t)dt}{\int_0^x g(t)dt} \right| < \epsilon
$$
由于 $\epsilon$ 是任意小的正数，因此：
$$
\lim_{x \to 0} \frac{\int_0^x g(t)\alpha(t)dt}{\int_0^x g(t)dt} = 0
$$
4. 结论：传递性成立

回到积分的展开式：
$$
I(x) = \underbrace{\int_0^x g(t)dt}_{主导项} + \underbrace{\int_0^x g(t)\alpha(t)dt}_{高阶无穷小}
$$
因此：
$$
\lim_{x \to 0} \frac{I(x)}{\int_0^x g(t)dt} = \lim_{x \to 0} \left[ 1 + \frac{\text{高阶无穷小}}{\text{主导项}} \right] = 1
$$
这就证明了等价无穷小的传递性：积分的等价无穷小等于被积函数等价无穷小的积分。

三、直观理解：“低阶项主导，高阶项可忽略”

无穷小的比较本质是“谁衰减得更快”——阶数越高（幂次越大），衰减越快。

对于选项B的被积函数 $\ln(1 + t^2) \sim t^2$：
$t^2$ 是2阶无穷小（衰减速度：$t^2$ 比 t 快）
