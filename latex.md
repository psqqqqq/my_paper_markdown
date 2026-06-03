# 基本用法


| 用途           | 可直接复制的 LaTeX                                             | 显示效果                                                     |
| -------------- | -------------------------------------------------------------- | ------------------------------------------------------------ |
| 行内公式       | `$a+b=c$`                                                    | $a+b=c$                                                    |
| 独立公式       | `\[a+b=c\]`                                                  | \[a+b=c\]                                                    |
| 上标           | `$x^2$`                                                      | $x^2$                                                      |
| 多字符上标     | `$x^{10}$`                                                   | $x^{10}$                                                   |
| 下标           | `$x_i$`                                                      | $x_i$                                                      |
| 多字符下标     | `$x_{ij}$`                                                   | $x_{ij}$                                                   |
| 上下标         | `$x_i^2$`                                                    | $x_i^2$                                                    |
| 复杂上下标     | `$x_{ij}^{(t)}$`                                             | $x_{ij}^{(t)}$                                             |
| 分数           | `$\frac{a}{b}$`                                              | $\frac{a}{b}$                                              |
| 复杂分数       | `$\frac{x^2+1}{y_i-3}$`                                      | $\frac{x^2+1}{y_i-3}$                                      |
| 平方根         | `$\sqrt{x}$`                                                 | $\sqrt{x}$                                                 |
| n 次根         | `$\sqrt[3]{x}$`                                              | $\sqrt[3]{x}$                                              |
| 加法           | `$a+b$`                                                      | $a+b$                                                      |
| 减法           | `$a-b$`                                                      | $a-b$                                                      |
| 乘号           | `$a\times b$`                                                | $a\times b$                                                |
| 点乘           | `$a\cdot b$`                                                 | $a\cdot b$                                                 |
| 除号           | `$a\div b$`                                                  | $a\div b$                                                  |
| 正负号         | `$x=1\pm2$`                                                  | $x=1\pm2$                                                  |
| 大于等于       | `$x\geq0$`                                                   | $x\geq0$                                                   |
| 小于等于       | `$x\leq0$`                                                   | $x\leq0$                                                   |
| 不等于         | `$x\neq0$`                                                   | $x\neq0$                                                   |
| 约等于         | `$x\approx1$`                                                | $x\approx1$                                                |
| 无穷大         | `$\infty$`                                                   | $\infty$                                                   |
| 圆括号         | `$(a+b)$`                                                    | $(a+b)$                                                    |
| 自动放大圆括号 | `$\left(\frac{a}{b}\right)$`                                 | $\left(\frac{a}{b}\right)$                                 |
| 方括号         | `$\left[\frac{a}{b}\right]$`                                 | $\left[\frac{a}{b}\right]$                                 |
| 大括号         | `$\left\{\frac{a}{b}\right\}$`                               | $\left\{\frac{a}{b}\right\}$                               |
| 绝对值         | `$\lvert x\rvert$`                                           | $\lvert x\rvert$                                           |
| 自动放大绝对值 | `$\left\lvert\frac{a}{b}\right\rvert$`                       | $\left\lvert\frac{a}{b}\right\rvert$                       |
| 求和           | `$\sum_{i=1}^{n}x_i$`                                        | $\sum_{i=1}^{n}x_i$                                        |
| 连乘           | `$\prod_{i=1}^{n}x_i$`                                       | $\prod_{i=1}^{n}x_i$                                       |
| 积分           | `$\int_a^b f(x)\,dx$`                                        | $\int_a^b f(x)\,dx$                                        |
| 极限           | `$\lim_{x\to0}f(x)$`                                         | $\lim_{x\to0}f(x)$                                         |
| 导数           | `$\frac{dy}{dx}$`                                            | $\frac{dy}{dx}$                                            |
| 偏导数         | `$\frac{\partial y}{\partial x}$`                            | $\frac{\partial y}{\partial x}$                            |
| 正弦函数       | `$\sin x$`                                                   | $\sin x$                                                   |
| 余弦函数       | `$\cos x$`                                                   | $\cos x$                                                   |
| 正切函数       | `$\tan x$`                                                   | $\tan x$                                                   |
| 对数           | `$\log x$`                                                   | $\log x$                                                   |
| 自然对数       | `$\ln x$`                                                    | $\ln x$                                                    |
| 指数函数       | `$\exp x$`                                                   | $\exp x$                                                   |
| alpha          | `$\alpha$`                                                   | $\alpha$                                                   |
| beta           | `$\beta$`                                                    | $\beta$                                                    |
| gamma          | `$\gamma$`                                                   | $\gamma$                                                   |
| delta          | `$\delta$`                                                   | $\delta$                                                   |
| epsilon        | `$\epsilon$`                                                 | $\epsilon$                                                 |
| theta          | `$\theta$`                                                   | $\theta$                                                   |
| lambda         | `$\lambda$`                                                  | $\lambda$                                                  |
| mu             | `$\mu$`                                                      | $\mu$                                                      |
| pi             | `$\pi$`                                                      | $\pi$                                                      |
| sigma          | `$\sigma$`                                                   | $\sigma$                                                   |
| omega          | `$\omega$`                                                   | $\omega$                                                   |
| 大写 Delta     | `$\Delta$`                                                   | $\Delta$                                                   |
| 大写 Sigma     | `$\Sigma$`                                                   | $\Sigma$                                                   |
| 大写 Omega     | `$\Omega$`                                                   | $\Omega$                                                   |
| 向量箭头       | `$\vec{x}$`                                                  | $\vec{x}$                                                  |
| 粗体向量       | `$\mathbf{x}$`                                               | $\mathbf{x}$                                               |
| 粗体矩阵       | `$\mathbf{X}$`                                               | $\mathbf{X}$                                               |
| 属于           | `$x\in A$`                                                   | $x\in A$                                                   |
| 不属于         | `$x\notin A$`                                                | $x\notin A$                                                |
| 子集           | `$A\subset B$`                                               | $A\subset B$                                               |
| 并集           | `$A\cup B$`                                                  | $A\cup B$                                                  |
| 交集           | `$A\cap B$`                                                  | $A\cap B$                                                  |
| 实数集         | `$\mathbb{R}$`                                               | $\mathbb{R}$                                               |
| n × p 维矩阵  | `$\mathbf{X}\in\mathbb{R}^{n\times p}$`                      | $\mathbf{X}\in\mathbb{R}^{n\times p}$                      |
| 均值           | `$\bar{x}$`                                                  | $\bar{x}$                                                  |
| 估计值         | `$\hat{x}$`                                                  | $\hat{x}$                                                  |
| 均值 ± 标准差 | `$\bar{x}\pm s$`                                             | $\bar{x}\pm s$                                             |
| P 值小于 0.05  | `$P<0.05$`                                                   | $P<0.05$                                                   |
| 具体 P 值      | `$P=0.032$`                                                  | $P=0.032$                                                  |
| 95% CI         | `$95\%\ \mathrm{CI}:1.12-2.18$`                              | $95\%\ \mathrm{CI}:1.12-2.18$                              |
| OR             | `$\mathrm{OR}=1.56$`                                         | $\mathrm{OR}=1.56$                                         |
| HR             | `$\mathrm{HR}=0.72$`                                         | $\mathrm{HR}=0.72$                                         |
| OR + CI + P    | `$\mathrm{OR}=1.56,\ 95\%\ \mathrm{CI}:1.12-2.18,\ P=0.006$` | $\mathrm{OR}=1.56,\ 95\%\ \mathrm{CI}:1.12-2.18,\ P=0.006$ |
| HR + CI + P    | `$\mathrm{HR}=0.72,\ 95\%\ \mathrm{CI}:0.55-0.94,\ P=0.017$` | $\mathrm{HR}=0.72,\ 95\%\ \mathrm{CI}:0.55-0.94,\ P=0.017$ |
| 样本量         | `$n=36$`                                                     | $n=36$                                                     |
| R 平方         | `$R^2=0.87$`                                                 | $R^2=0.87$                                                 |
| 预测值         | `$\hat{y}=f(x)$`                                             | $\hat{y}=f(x)$                                             |
| 损失函数       | `$\mathcal{L}=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2$`   | $\mathcal{L}=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2$   |
| 贝叶斯公式     | `$p(y\mid x)=\frac{p(x\mid y)p(y)}{p(x)}$`                   | $p(y\mid x)=\frac{p(x\mid y)p(y)}{p(x)}$                   |
| 参数最优化     | `$\theta^*=\arg\min_{\theta}\mathcal{L}(\theta)$`            | $\theta^*=\arg\min_{\theta}\mathcal{L}(\theta)$            |
| 标签向量       | `$\mathbf{y}\in\mathbb{R}^{n}$`                              | $\mathbf{y}\in\mathbb{R}^{n}$                              |
