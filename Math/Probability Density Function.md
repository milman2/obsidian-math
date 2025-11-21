# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Random Variables]]
- Calculus (미적분학)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Probability density function (PDF)^[확률 밀도 함수]

**Probability density function**^[확률 밀도 함수] (PDF)는 **continuous random variable**^[연속 확률 변수]의 확률 분포를 나타내는 함수이다.

Random variable $X$가 continuous이면, PDF $f_X: \mathbb{R} \rightarrow [0, \infty)$는 다음을 만족:

$$F_X(x) = P(X \leq x) = \int_{-\infty}^x f_X(t) \, dt$$

여기서 $F_X$는 cumulative distribution function (CDF)^[누적 분포 함수].

### "Density"의 의미

"Density"^[밀도]는 **단위 길이당 확률**:

$$P(x \leq X \leq x + dx) \approx f_X(x) \cdot dx \quad \text{(infinitesimal)}$$

- $f_X(x)$ 자체는 확률이 **아님**! (확률 밀도)
- $f_X(x) > 1$도 가능함
- 실제 확률은 구간에 대한 적분

**중요**: $P(X = x) = 0$ for all $x$ (continuous case의 특징!)

**참고**: Discrete case는 [[Probability Mass Function]] 참조

---

# <span class="header-properties">Properties</span>

## Axioms^[공리]

PDF $f_X(x)$는 다음을 만족:

### 1. Non-negativity^[비음성]

$$f_X(x) \geq 0 \quad \forall x \in \mathbb{R}$$

밀도는 음수가 될 수 없음.

### 2. Normalization^[정규화]

$$\int_{-\infty}^{\infty} f_X(x) \, dx = 1$$

전체 "면적"은 1.

**주의**: $f_X(x) \leq 1$이 항상 성립하는 것은 아님!

### 3. Absolute continuity^[절대 연속성]

CDF $F_X$가 absolutely continuous^[절대 연속]해야 함.

## Support^[지지집합]

PDF의 **support**^[지지집합]:

$$\text{Supp}(f_X) = \{x \in \mathbb{R} : f_X(x) > 0\}$$

(더 정확히는 closure)

$X$가 양의 밀도를 가지는 영역.

## Relation to CDF^[누적 분포 함수와의 관계]

### PDF from CDF

$$f_X(x) = \frac{d}{dx} F_X(x)$$

(미분 가능한 점에서)

### CDF from PDF

$$F_X(x) = \int_{-\infty}^x f_X(t) \, dt$$

**상세한 내용**: [[Random Variables]] (CDF 섹션)

## Probability calculation^[확률 계산]

### Single point

$$P(X = x) = 0 \quad \forall x$$

Continuous case의 핵심 특징!

### Interval

$$P(a \leq X \leq b) = \int_a^b f_X(x) \, dx$$

**Consequence**: 
$$P(a < X < b) = P(a \leq X \leq b) = P(a < X \leq b) = P(a \leq X < b)$$

끝점 포함 여부는 무관.

### Small interval^[작은 구간]

$$P(x < X < x + \epsilon) \approx f_X(x) \cdot \epsilon \quad \text{($\epsilon$ 작을 때)}$$

이것이 "density"의 의미.

---

# <span class="header-examples">Common Distributions</span>

## 1. Uniform distribution^[균등 분포]

**Parameters**: $a < b$

**Notation**: $X \sim \text{Uniform}(a, b)$ or $U(a, b)$

**Support**: $[a, b]$

**PDF**:
$$f_X(x) = \begin{cases}
\frac{1}{b-a} & x \in [a, b] \\
0 & \text{otherwise}
\end{cases}$$

**Moments**:
- $E[X] = \frac{a+b}{2}$
- $\text{Var}(X) = \frac{(b-a)^2}{12}$

**CDF**:
$$F_X(x) = \begin{cases}
0 & x < a \\
\frac{x-a}{b-a} & a \leq x \leq b \\
1 & x > b
\end{cases}$$

**Application**: 완전 무작위 선택, 시뮬레이션의 기본

## 2. Exponential distribution^[지수 분포]

**Parameter**: $\lambda > 0$ (rate)

**Notation**: $X \sim \text{Exponential}(\lambda)$ or $\text{Exp}(\lambda)$

**Support**: $[0, \infty)$

**PDF**:
$$f_X(x) = \begin{cases}
\lambda e^{-\lambda x} & x \geq 0 \\
0 & x < 0
\end{cases}$$

**Moments**:
- $E[X] = \frac{1}{\lambda}$
- $\text{Var}(X) = \frac{1}{\lambda^2}$

**CDF**:
$$F_X(x) = \begin{cases}
1 - e^{-\lambda x} & x \geq 0 \\
0 & x < 0
\end{cases}$$

**Memoryless property**^[무기억성]:
$$P(X > s + t | X > s) = P(X > t)$$

유일한 continuous memoryless distribution!

**Application**: 대기 시간, 수명 분석, Poisson process의 inter-arrival time

## 3. Normal (Gaussian) distribution^[정규 분포]

**Parameters**: $\mu \in \mathbb{R}$ (mean), $\sigma^2 > 0$ (variance)

**Notation**: $X \sim \mathcal{N}(\mu, \sigma^2)$ or $N(\mu, \sigma^2)$

**Support**: $(-\infty, \infty)$

**PDF**:
$$f_X(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)$$

**Moments**:
- $E[X] = \mu$
- $\text{Var}(X) = \sigma^2$

**Standard normal**: $\mu = 0$, $\sigma^2 = 1$
$$\phi(x) = \frac{1}{\sqrt{2\pi}} e^{-x^2/2}$$

**CDF**: No closed form, denoted $\Phi(x)$ for standard normal.

**Properties**:
- Symmetric about $\mu$
- Bell curve^[종 곡선]
- 68-95-99.7 rule

**Central Limit Theorem**: Many distributions converge to normal!

**Applications**: Ubiquitous in nature, statistics, signal processing

## 4. Beta distribution^[베타 분포]

**Parameters**: $\alpha, \beta > 0$

**Notation**: $X \sim \text{Beta}(\alpha, \beta)$

**Support**: $[0, 1]$

**PDF**:
$$f_X(x) = \frac{x^{\alpha-1}(1-x)^{\beta-1}}{B(\alpha, \beta)}, \quad x \in [0, 1]$$

여기서 $B(\alpha, \beta) = \frac{\Gamma(\alpha)\Gamma(\beta)}{\Gamma(\alpha+\beta)}$ (Beta function)

**Moments**:
- $E[X] = \frac{\alpha}{\alpha+\beta}$
- $\text{Var}(X) = \frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}$

**Special cases**:
- $\alpha = \beta = 1$: $U(0, 1)$
- $\alpha = \beta$: Symmetric about 0.5

**Application**: Bayesian statistics (prior for probabilities), proportion modeling

## 5. Gamma distribution^[감마 분포]

**Parameters**: $\alpha > 0$ (shape), $\beta > 0$ (rate)

**Notation**: $X \sim \text{Gamma}(\alpha, \beta)$

**Support**: $(0, \infty)$

**PDF**:
$$f_X(x) = \frac{\beta^\alpha}{\Gamma(\alpha)} x^{\alpha-1} e^{-\beta x}, \quad x > 0$$

**Moments**:
- $E[X] = \frac{\alpha}{\beta}$
- $\text{Var}(X) = \frac{\alpha}{\beta^2}$

**Special cases**:
- $\alpha = 1$: Exponential($\beta$)
- $\alpha = \frac{n}{2}$, $\beta = \frac{1}{2}$: Chi-squared($n$)

**Application**: 대기 시간의 합, reliability theory

## 6. Chi-squared distribution^[카이제곱 분포]

**Parameter**: $k \in \mathbb{N}$ (degrees of freedom^[자유도])

**Notation**: $X \sim \chi^2(k)$

**Support**: $(0, \infty)$

**PDF**:
$$f_X(x) = \frac{1}{2^{k/2}\Gamma(k/2)} x^{k/2-1} e^{-x/2}, \quad x > 0$$

**Moments**:
- $E[X] = k$
- $\text{Var}(X) = 2k$

**Connection**: $Z_1, \ldots, Z_k \sim \mathcal{N}(0, 1)$ i.i.d. $\Rightarrow$ $Z_1^2 + \cdots + Z_k^2 \sim \chi^2(k)$

**Application**: Hypothesis testing, confidence intervals

## 7. Student's t-distribution^[스튜던트 t-분포]

**Parameter**: $\nu \in \mathbb{N}$ (degrees of freedom)

**Notation**: $X \sim t(\nu)$

**Support**: $(-\infty, \infty)$

**PDF**:
$$f_X(x) = \frac{\Gamma\left(\frac{\nu+1}{2}\right)}{\sqrt{\nu\pi}\,\Gamma\left(\frac{\nu}{2}\right)} \left(1 + \frac{x^2}{\nu}\right)^{-(\nu+1)/2}$$

**Moments**:
- $E[X] = 0$ (if $\nu > 1$)
- $\text{Var}(X) = \frac{\nu}{\nu-2}$ (if $\nu > 2$)

**Properties**:
- Symmetric about 0
- Heavier tails than normal
- $\nu \to \infty \Rightarrow$ converges to $\mathcal{N}(0, 1)$

**Application**: Small sample inference, robust statistics

## 8. Cauchy distribution^[코시 분포]

**Parameters**: $x_0 \in \mathbb{R}$ (location), $\gamma > 0$ (scale)

**Notation**: $X \sim \text{Cauchy}(x_0, \gamma)$

**Support**: $(-\infty, \infty)$

**PDF**:
$$f_X(x) = \frac{1}{\pi\gamma\left[1 + \left(\frac{x-x_0}{\gamma}\right)^2\right]}$$

**Moments**: 
- $E[X]$ does not exist! (integral diverges)
- No finite moments

**Standard Cauchy**: $x_0 = 0$, $\gamma = 1$ (special case of $t(1)$)

**Application**: Physics (resonance), pathological example in statistics

---

# <span class="header-examples">Examples</span>

## 1. Random number generation^[난수 생성]

Uniform$(0, 1)$에서 값 뽑기:

$$P(0.3 \leq X \leq 0.7) = \int_{0.3}^{0.7} 1 \, dx = 0.4$$

40% 확률.

## 2. Waiting time^[대기 시간]

버스가 평균 10분마다 도착 (exponential):

$$X \sim \text{Exp}(1/10)$$

$$P(X \leq 15) = 1 - e^{-15/10} = 1 - e^{-1.5} \approx 0.777$$

15분 이내에 올 확률 77.7%.

## 3. Test scores^[시험 점수]

평균 70, 표준편차 10인 정규 분포:

$$X \sim \mathcal{N}(70, 100)$$

$$P(X > 80) = P\left(\frac{X-70}{10} > 1\right) = 1 - \Phi(1) \approx 0.159$$

80점 이상 받을 확률 약 15.9%.

## 4. Lifetime analysis^[수명 분석]

부품 수명이 Gamma$(2, 0.5)$ (시간 단위):

$$E[X] = \frac{2}{0.5} = 4 \text{ units}$$

평균 수명 4단위.

---

# <span class="header-properties">Operations on PDFs</span>

## Transformation^[변환]

$Y = g(X)$, $g$ strictly monotonic and differentiable:

$$f_Y(y) = f_X(g^{-1}(y)) \left|\frac{d}{dy}g^{-1}(y)\right|$$

또는:
$$f_Y(y) = \frac{f_X(x)}{|g'(x)|} \quad \text{where } x = g^{-1}(y)$$

### Example: Linear transformation

$Y = aX + b$ ($a \neq 0$):

$$f_Y(y) = \frac{1}{|a|} f_X\left(\frac{y-b}{a}\right)$$

**Normal case**: $X \sim \mathcal{N}(\mu, \sigma^2) \Rightarrow aX + b \sim \mathcal{N}(a\mu + b, a^2\sigma^2)$

## Convolution^[합성곱]

$Z = X + Y$, $X$, $Y$ independent:

$$f_Z(z) = \int_{-\infty}^{\infty} f_X(x) f_Y(z - x) \, dx = (f_X * f_Y)(z)$$

### Example: Sum of normals

$X \sim \mathcal{N}(\mu_1, \sigma_1^2)$, $Y \sim \mathcal{N}(\mu_2, \sigma_2^2)$ independent $\Rightarrow$
$$X + Y \sim \mathcal{N}(\mu_1 + \mu_2, \sigma_1^2 + \sigma_2^2)$$

## Mixture distribution^[혼합 분포]

Weight $w_1, \ldots, w_k$ ($\displaystyle\sum_i w_i = 1$)로 PDF들을 혼합:

$$f_X(x) = \displaystyle\sum_{i=1}^k w_i \cdot f_i(x)$$

**Example**: Gaussian Mixture Model (GMM)

---

# <span class="header-remark">Visualization</span>

## Curve plot^[곡선 그래프]

PDF를 시각화하는 표준 방법:
- $x$-axis: 값
- $y$-axis: 밀도 $f_X(x)$
- 연속 곡선

**주의**: $y$-axis는 확률이 아님! 밀도.

## Area under curve^[곡선 아래 면적]

확률은 곡선 아래 면적:

$$P(a \leq X \leq b) = \text{Area under } f_X(x) \text{ from } a \text{ to } b$$

## Quantile^[분위수]

$p$-th quantile $x_p$:
$$F_X(x_p) = p \Leftrightarrow \int_{-\infty}^{x_p} f_X(x) \, dx = p$$

**Examples**:
- Median: $x_{0.5}$ (50th percentile)
- Quartiles: $x_{0.25}$, $x_{0.75}$

---

# <span class="header-remark">Properties and Relationships</span>

## Expectation^[기댓값]

$$E[X] = \int_{-\infty}^{\infty} x \cdot f_X(x) \, dx$$

**Law of the unconscious statistician (LOTUS)**:
$$E[g(X)] = \int_{-\infty}^{\infty} g(x) \cdot f_X(x) \, dx$$

**상세한 내용**: [[Expected Value]]

## Variance^[분산]

$$\text{Var}(X) = \int_{-\infty}^{\infty} (x - E[X])^2 \cdot f_X(x) \, dx = E[X^2] - E[X]^2$$

## Moments^[적률]

$n$-th moment:
$$E[X^n] = \int_{-\infty}^{\infty} x^n \cdot f_X(x) \, dx$$

## Moment generating function (MGF)^[적률 생성 함수]

$$M_X(t) = E[e^{tX}] = \int_{-\infty}^{\infty} e^{tx} \cdot f_X(x) \, dx$$

(수렴 영역에서)

**Properties**:
- Uniquely determines distribution
- $M_X^{(n)}(0) = E[X^n]$

**상세한 내용**: [[Expected Value]]

## Characteristic function^[특성 함수]

$$\phi_X(t) = E[e^{itX}] = \int_{-\infty}^{\infty} e^{itx} \cdot f_X(x) \, dx$$

항상 존재 (even if MGF doesn't).

## Mode^[최빈값]

$$\text{mode} = \arg\max_x f_X(x)$$

PDF가 최대인 점.

---

# <span class="header-remark">Comparison with PMF</span>

| | **PDF** (Continuous) | **PMF** (Discrete) |
|---|---|---|
| **Definition** | $f_X(x)$ s.t. $F_X(x) = \int f_X$ | $p_X(x) = P(X = x)$ |
| **Interpretation** | Density at $x$ (not probability!) | Probability at $x$ |
| **Values** | $f_X(x) \in [0, \infty)$ | $p_X(x) \in [0, 1]$ |
| **Can exceed 1?** | Yes! | No |
| **Single point** | $P(X = x) = 0$ | $P(X = x) = p_X(x) > 0$ |
| **Support** | Uncountable set | Countable set |
| **Normalization** | $\displaystyle\int f_X(x) dx = 1$ | $\displaystyle\sum_x p_X(x) = 1$ |
| **Interval** | $P(X \in [a,b]) = \displaystyle\int_a^b f_X(x) dx$ | $P(X \in [a,b]) = \displaystyle\sum_{a \leq x \leq b} p_X(x)$ |
| **Expectation** | $E[X] = \displaystyle\int x \cdot f_X(x) dx$ | $E[X] = \displaystyle\sum_x x \cdot p_X(x)$ |

**상세한 내용**: [[Probability Mass Function]]

---

# <span class="header-remark">Advanced Topics</span>

## Mixed distributions^[혼합 분포]

일부는 discrete, 일부는 continuous:

$$F_X(x) = p \cdot F_{\text{discrete}}(x) + (1-p) \cdot F_{\text{continuous}}(x)$$

**Example**: 보험 청구 금액 (0 with some probability, continuous otherwise)

## Singular distributions^[특이 분포]

Neither discrete nor continuous: Cantor distribution

Continuous CDF이지만 PDF 없음 (derivative = 0 a.e.)

## Kernel density estimation^[커널 밀도 추정]

데이터 $x_1, \ldots, x_n$에서 PDF 추정:

$$\hat{f}(x) = \frac{1}{nh} \displaystyle\sum_{i=1}^n K\left(\frac{x - x_i}{h}\right)$$

여기서 $K$는 kernel function, $h$는 bandwidth.

## Maximum likelihood estimation (MLE)^[최대 가능도 추정]

데이터 $x_1, \ldots, x_n$이 주어졌을 때, parameter $\theta$ 추정:

$$\hat{\theta}_{\text{MLE}} = \arg\max_\theta \prod_{i=1}^n f_X(x_i; \theta) = \arg\max_\theta \displaystyle\sum_{i=1}^n \log f_X(x_i; \theta)$$

---

# <span class="header-remark">Applications</span>

## Statistics^[통계학]

- **Parameter estimation^[모수 추정]**: MLE, Method of moments
- **Hypothesis testing^[가설 검정]**: t-test, F-test
- **Confidence intervals^[신뢰 구간]**: Based on distribution of estimators
- **Regression analysis^[회귀 분석]**: Error distributions

## Machine learning

- **Generative models^[생성 모델]**: VAE, Normalizing flows
- **Density estimation^[밀도 추정]**: KDE, mixture models
- **Anomaly detection^[이상 탐지]**: Low-density regions
- **Bayesian deep learning**: Variational inference

## Signal processing^[신호 처리]

- **Noise modeling^[잡음 모델링]**: Gaussian noise
- **Filter design^[필터 설계]**: Based on signal distributions
- **Detection theory^[탐지 이론]**: Likelihood ratios

## Finance^[금융]

- **Asset returns^[자산 수익률]**: Log-normal, Student's t
- **Option pricing^[옵션 가격 결정]**: Black-Scholes (normal)
- **Risk modeling^[위험 모델링]**: Heavy-tailed distributions
- **Value at Risk (VaR)**: Quantile estimation

## Physics^[물리학]

- **Statistical mechanics^[통계 역학]**: Maxwell-Boltzmann distribution
- **Quantum mechanics^[양자 역학]**: Wave function squared = probability density
- **Measurement errors^[측정 오차]**: Normal distribution

## Engineering^[공학]

- **Reliability analysis^[신뢰성 분석]**: Weibull, exponential
- **Quality control^[품질 관리]**: Process variation modeling
- **Communications^[통신]**: Channel noise modeling

---

# <span class="header-examples">핵심 공식 요약</span>

| Distribution | PDF | Mean | Variance |
|--------------|-----|------|----------|
| Uniform($a, b$) | $\frac{1}{b-a}$ | $\frac{a+b}{2}$ | $\frac{(b-a)^2}{12}$ |
| Exponential($\lambda$) | $\lambda e^{-\lambda x}$ | $\frac{1}{\lambda}$ | $\frac{1}{\lambda^2}$ |
| Normal($\mu, \sigma^2$) | $\frac{1}{\sqrt{2\pi\sigma^2}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}$ | $\mu$ | $\sigma^2$ |
| Gamma($\alpha, \beta$) | $\frac{\beta^\alpha}{\Gamma(\alpha)}x^{\alpha-1}e^{-\beta x}$ | $\frac{\alpha}{\beta}$ | $\frac{\alpha}{\beta^2}$ |
| Beta($\alpha, \beta$) | $\frac{x^{\alpha-1}(1-x)^{\beta-1}}{B(\alpha,\beta)}$ | $\frac{\alpha}{\alpha+\beta}$ | $\frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}$ |

---

**기본 개념**: [[Sample Spaces]], [[Random Variables]]
**이산 버전**: [[Probability Mass Function]]
**관련 주제**: [[Joint Probabilities]], [[Marginal Probabilities]], [[Conditional Probability]]
**응용**: [[Expected Value]]

