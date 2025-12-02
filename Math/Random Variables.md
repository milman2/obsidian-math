# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Borel Sigma Algebra]]
- Basic measure theory (기초 측도론)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Random variable^[확률 변수]

Probability space^[확률 공간] $(\Omega, \mathcal{F}, P)$에서, **random variable**^[확률 변수]는 measurable function^[가측 함수] $X: \Omega \rightarrow \mathbb{R}$이다:

$$X^{-1}(B) \in \mathcal{F} \quad \forall B \in \mathcal{B}(\mathbb{R})$$

즉, 모든 Borel set^[보렐 집합] $B$에 대해, $\{X \in B\} = \{\omega \in \Omega : X(\omega) \in B\}$는 event^[사건]여야 한다.

### Intuition^[직관]

Random variable은 실제로는 "variable"^[변수]이 아니라 **function**^[함수]이다:
- 각 outcome^[결과] $\omega \in \Omega$에 실수값 $X(\omega)$을 대응
- 확률 실험의 결과를 수치화

## Distribution^[분포]

Random variable $X$의 **distribution**^[분포] (또는 law^[법칙]) $P_X$는 $\mathbb{R}$ 위의 probability measure^[확률 측도]:

$$P_X(B) = P(\{\omega : X(\omega) \in B\}) = P(X \in B)$$

### Cumulative distribution function^[누적 분포 함수] (CDF)

$$F_X(x) = P(X \leq x) = P(\{\omega : X(\omega) \leq x\})$$

**Properties**:
1. **Non-decreasing**^[비감소]: $x_1 \leq x_2 \Rightarrow F_X(x_1) \leq F_X(x_2)$
2. **Right-continuous**^[우연속]: $\displaystyle\lim_{h \to 0^+} F_X(x + h) = F_X(x)$
3. **Limits**: $\displaystyle\lim_{x \to -\infty} F_X(x) = 0$, $\displaystyle\lim_{x \to \infty} F_X(x) = 1$

## Types of random variables

### Discrete random variable^[이산 확률 변수]

$X$가 **discrete**^[이산]이다 $\Leftrightarrow$ $X$의 range가 countable^[가산]

**Probability mass function**^[확률 질량 함수] (PMF):
$$p_X(x) = P(X = x)$$

Properties:
- $p_X(x) \geq 0$ for all $x$
- $\displaystyle\sum_{x} p_X(x) = 1$

**상세한 내용**: [[Probability Mass Function]]
- $P(X \in B) = \displaystyle\sum_{x \in B} p_X(x)$

### Continuous random variable^[연속 확률 변수]

$X$가 **continuous**^[연속]이다 $\Leftrightarrow$ CDF $F_X$가 absolutely continuous^[절대 연속]

**Probability density function**^[확률 밀도 함수] (PDF): $f_X$는 다음을 만족:
$$F_X(x) = \int_{-\infty}^x f_X(t) \, dt$$

Properties:
- $f_X(x) \geq 0$ for all $x$
- $\displaystyle\int_{-\infty}^\infty f_X(x) \, dx = 1$

**상세한 내용**: [[Probability Density Function]]
- $P(a \leq X \leq b) = \displaystyle\int_a^b f_X(x) \, dx$
- $P(X = x) = 0$ for any single point $x$

---

# <span class="header-properties">Properties</span>

## Expected value^[기댓값]

Random variable $X$의 **expected value**^[기댓값] (또는 mean^[평균], expectation):

### Discrete case
$$E[X] = \displaystyle\sum_{x} x \cdot P(X = x) = \displaystyle\sum_{x} x \cdot p_X(x)$$

### Continuous case
$$E[X] = \int_{-\infty}^\infty x \cdot f_X(x) \, dx$$

### General (measure-theoretic)
$$E[X] = \int_\Omega X(\omega) \, dP(\omega)$$

**더 자세한 내용**: [[Expected Value]] 참조

## Properties of expectation

1. **Linearity**^[선형성]:
   $$E[aX + bY] = aE[X] + bE[Y]$$

2. **Monotonicity**^[단조성]: $X \leq Y$ a.s.^[거의 확실히] $\Rightarrow E[X] \leq E[Y]$

3. **Law of the unconscious statistician**^[무의식적 통계학자의 법칙] (LOTUS):
   $$E[g(X)] = \begin{cases}
   \displaystyle\sum_x g(x) \cdot p_X(x) & \text{(discrete)} \\
   \displaystyle\int_{-\infty}^\infty g(x) \cdot f_X(x) \, dx & \text{(continuous)}
   \end{cases}$$

## Variance^[분산] and standard deviation^[표준편차]

**Variance**^[분산]:
$$\text{Var}(X) = E[(X - E[X])^2] = E[X^2] - (E[X])^2$$

**Standard deviation**^[표준편차]:
$$\sigma_X = \sqrt{\text{Var}(X)}$$

### Properties of variance

1. $\text{Var}(aX + b) = a^2 \text{Var}(X)$
2. $\text{Var}(X) \geq 0$, with equality iff $X$ is constant a.s.
3. If $X$, $Y$ independent^[독립]: $\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y)$

## Moments^[적률]

$k$-th **moment**^[적률]:
$$E[X^k] = \begin{cases}
\displaystyle\sum_x x^k \cdot p_X(x) & \text{(discrete)} \\
\displaystyle\int_{-\infty}^\infty x^k \cdot f_X(x) \, dx & \text{(continuous)}
\end{cases}$$

$k$-th **central moment**^[중심 적률]:
$$E[(X - E[X])^k]$$

---

# <span class="header-examples">Examples</span>

## Discrete distributions^[이산 분포]

### 1. Bernoulli distribution^[베르누이 분포]

**Parameter**: $p \in [0, 1]$

**PMF**:
$$P(X = k) = \begin{cases}
p & k = 1 \\
1-p & k = 0
\end{cases}$$

- $E[X] = p$
- $\text{Var}(X) = p(1-p)$

**Example**: Single coin flip (성공/실패)

### 2. Binomial distribution^[이항 분포]

**Parameters**: $n \in \mathbb{N}$, $p \in [0, 1]$

**Notation**: $X \sim \text{Binomial}(n, p)$ or $X \sim B(n, p)$

**PMF**:
$$P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}, \quad k = 0, 1, \ldots, n$$

- $E[X] = np$
- $\text{Var}(X) = np(1-p)$

**Example**: $n$번의 독립적인 시행에서 성공 횟수

### 3. Poisson distribution^[푸아송 분포]

**Parameter**: $\lambda > 0$

**Notation**: $X \sim \text{Poisson}(\lambda)$

**PMF**:
$$P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}, \quad k = 0, 1, 2, \ldots$$

- $E[X] = \lambda$
- $\text{Var}(X) = \lambda$

**Example**: 단위 시간당 사건 발생 횟수

### 4. Geometric distribution^[기하 분포]

**Parameter**: $p \in (0, 1]$

**PMF** (first success):
$$P(X = k) = (1-p)^{k-1} p, \quad k = 1, 2, 3, \ldots$$

- $E[X] = \frac{1}{p}$
- $\text{Var}(X) = \frac{1-p}{p^2}$

**Property**: **Memoryless**^[무기억성]: $P(X > m + n | X > m) = P(X > n)$

## Continuous distributions^[연속 분포]

### 1. Uniform distribution^[균등 분포]

**Parameters**: $a < b$

**Notation**: $X \sim \text{Uniform}(a, b)$ or $X \sim U(a, b)$

**PDF**:
$$f_X(x) = \begin{cases}
\frac{1}{b-a} & x \in [a, b] \\
0 & \text{otherwise}
\end{cases}$$

- $E[X] = \frac{a+b}{2}$
- $\text{Var}(X) = \frac{(b-a)^2}{12}$

### 2. Exponential distribution^[지수 분포]

**Parameter**: $\lambda > 0$

**Notation**: $X \sim \text{Exponential}(\lambda)$ or $X \sim \text{Exp}(\lambda)$

**PDF**:
$$f_X(x) = \begin{cases}
\lambda e^{-\lambda x} & x \geq 0 \\
0 & x < 0
\end{cases}$$

**CDF**:
$$F_X(x) = \begin{cases}
1 - e^{-\lambda x} & x \geq 0 \\
0 & x < 0
\end{cases}$$

- $E[X] = \frac{1}{\lambda}$
- $\text{Var}(X) = \frac{1}{\lambda^2}$

**Property**: **Memoryless**^[무기억성]: $P(X > s + t | X > s) = P(X > t)$

### 3. Normal (Gaussian) distribution^[정규 분포]

**Parameters**: $\mu \in \mathbb{R}$, $\sigma^2 > 0$

**Notation**: $X \sim N(\mu, \sigma^2)$

**PDF**:
$$f_X(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)$$

- $E[X] = \mu$
- $\text{Var}(X) = \sigma^2$

**Standard normal**: $Z \sim N(0, 1)$
$$\phi(z) = \frac{1}{\sqrt{2\pi}} e^{-z^2/2}$$

**Standardization**: If $X \sim N(\mu, \sigma^2)$, then $Z = \frac{X - \mu}{\sigma} \sim N(0, 1)$

---

# <span class="header-remark">Remark</span>

## Transformations of random variables

Random variable $X$와 function $g: \mathbb{R} \rightarrow \mathbb{R}$에 대해, $Y = g(X)$도 random variable이다.

### PDF transformation (continuous case)

$g$가 strictly monotonic^[순증가 또는 순감소]이고 differentiable^[미분가능]이면:
$$f_Y(y) = f_X(g^{-1}(y)) \left|\frac{d}{dy}g^{-1}(y)\right|$$

### Change of variables formula

$$E[g(X)] = \int_{-\infty}^\infty g(x) f_X(x) \, dx$$

함수를 먼저 적용한 후 기댓값 계산 가능!

## Independence^[독립]

Random variables $X$, $Y$가 **independent**^[독립]이다 $\Leftrightarrow$
$$P(X \in A, Y \in B) = P(X \in A) \cdot P(Y \in B) \quad \forall A, B \in \mathcal{B}(\mathbb{R})$$

### Equivalent conditions

1. $F_{X,Y}(x, y) = F_X(x) \cdot F_Y(y)$ (joint CDF^[결합 누적 분포 함수])
2. $f_{X,Y}(x, y) = f_X(x) \cdot f_Y(y)$ (joint PDF^[결합 확률 밀도 함수])
3. $E[XY] = E[X] \cdot E[Y]$ (단, 역은 성립 안 함!)

### Product of independent random variables

If $X$, $Y$ independent:
- $E[XY] = E[X] \cdot E[Y]$
- $\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y)$

## Joint distributions^[결합 분포]

Multiple random variables $(X_1, \ldots, X_n)$에 대해:

### Joint CDF
$$F_{X_1,\ldots,X_n}(x_1, \ldots, x_n) = P(X_1 \leq x_1, \ldots, X_n \leq x_n)$$

### Joint PDF (continuous)
$$f_{X_1,\ldots,X_n}(x_1, \ldots, x_n) \geq 0$$
$$\int_{\mathbb{R}^n} f_{X_1,\ldots,X_n}(x_1, \ldots, x_n) \, dx_1 \cdots dx_n = 1$$

**상세한 내용**: [[Joint Probabilities]]

### Marginal distribution^[주변 분포]

$$f_X(x) = \int_{\mathbb{R}^{n-1}} f_{X,Y_1,\ldots,Y_{n-1}}(x, y_1, \ldots, y_{n-1}) \, dy_1 \cdots dy_{n-1}$$

**상세한 내용**: [[Marginal Probabilities]]

## Conditional distributions^[조건부 분포]

Given $Y = y$:

### Conditional PDF
$$f_{X|Y}(x | y) = \frac{f_{X,Y}(x, y)}{f_Y(y)}$$

### Conditional expectation
$$E[X | Y = y] = \int_{-\infty}^\infty x \cdot f_{X|Y}(x | y) \, dx$$

**더 자세한 내용**: [[Conditional Probability]] 참조

## Important theorems

### Law of large numbers^[큰 수의 법칙]

$X_1, X_2, \ldots$ i.i.d.^[독립 항등 분포], $E[X_i] = \mu$:

**Weak law**^[약한 법칙] (convergence in probability^[확률 수렴]):
$$\frac{1}{n}\displaystyle\sum_{i=1}^n X_i \xrightarrow{P} \mu$$

**Strong law**^[강한 법칙] (convergence almost surely^[거의 확실한 수렴]):
$$P\left(\displaystyle\lim_{n \to \infty} \frac{1}{n}\displaystyle\sum_{i=1}^n X_i = \mu\right) = 1$$

### Central limit theorem^[중심극한정리]

$X_1, X_2, \ldots$ i.i.d., $E[X_i] = \mu$, $\text{Var}(X_i) = \sigma^2 < \infty$:

$$\frac{\displaystyle\sum_{i=1}^n X_i - n\mu}{\sigma\sqrt{n}} \xrightarrow{d} N(0, 1)$$

또는 equivalently:
$$\frac{\bar{X}_n - \mu}{\sigma/\sqrt{n}} \xrightarrow{d} N(0, 1)$$

where $\bar{X}_n = \frac{1}{n}\displaystyle\sum_{i=1}^n X_i$

## Generating functions^[생성 함수]

### Moment generating function^[적률 생성 함수] (MGF)

$$M_X(t) = E[e^{tX}] = \begin{cases}
\displaystyle\sum_x e^{tx} p_X(x) & \text{(discrete)} \\
\displaystyle\int_{-\infty}^\infty e^{tx} f_X(x) \, dx & \text{(continuous)}
\end{cases}$$

**Property**: $M_X(t)$가 존재하면, $E[X^n] = M_X^{(n)}(0)$ (n-th derivative at 0)

### Characteristic function^[특성 함수]

$$\phi_X(t) = E[e^{itX}]$$

항상 존재하며, distribution을 uniquely determine^[유일하게 결정]한다.

## Inequalities^[부등식]

### Markov's inequality^[마르코프 부등식]

$X \geq 0$이고 $a > 0$이면:
$$P(X \geq a) \leq \frac{E[X]}{a}$$

### Chebyshev's inequality^[체비셰프 부등식]

$$P(|X - E[X]| \geq \varepsilon) \leq \frac{\text{Var}(X)}{\varepsilon^2}$$

### Jensen's inequality^[옌센 부등식]

$g$ convex^[볼록]이면:
$$E[g(X)] \geq g(E[X])$$

---

# <span class="header-examples">계층 구조</span>

```
Probability space (Ω, F, P)
    ↓ measurable function
Random variable X: Ω → ℝ
    ↓ pushforward measure
Distribution P_X on (ℝ, B(ℝ))
    ↓ characterized by
CDF F_X(x) = P(X ≤ x)
    ↓ derivative (if continuous)
PDF f_X(x) = F'_X(x)
    ↓ integration
Expected value E[X] = ∫ x f_X(x) dx
```

## 핵심 개념 요약

| 개념 | Discrete | Continuous |
|------|----------|------------|
| Distribution | PMF $p_X(x)$ | PDF $f_X(x)$ |
| Probability | $P(X = x) = p_X(x)$ | $P(a \leq X \leq b) = \displaystyle\int_a^b f_X(x) dx$ |
| Expectation | $\displaystyle\sum_x x \cdot p_X(x)$ | $\displaystyle\int x \cdot f_X(x) dx$ |
| Variance | $\displaystyle\sum_x (x - \mu)^2 p_X(x)$ | $\displaystyle\int (x - \mu)^2 f_X(x) dx$ |

## Applications^[응용]

- **Statistics**^[통계학]: Hypothesis testing^[가설 검정], estimation^[추정]
- **Machine learning**: Probabilistic models, Bayesian inference
- **Finance**^[금융]: Option pricing, risk management^[리스크 관리]
- **Physics**: Statistical mechanics^[통계 역학], quantum mechanics^[양자 역학]
- **Engineering**: Signal processing^[신호 처리], reliability theory^[신뢰성 이론]

---

**확률론 개관**: [[Probability]]
**기초 개념**: [[Sample Spaces]], [[Borel Sigma Algebra]], [[Measure Space]]
**분포 함수**: [[Probability Mass Function]], [[Probability Density Function]]
**관련 주제**: [[Joint Probabilities]], [[Marginal Probabilities]], [[Conditional Probability]], [[Expected Value]]
