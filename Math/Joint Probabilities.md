# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Random Variables]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Joint probability^[결합 확률]

**Joint probability**^[결합 확률]는 두 개 이상의 events^[사건] 또는 random variables^[확률 변수]가 **동시에** 발생하거나 특정 값을 가질 확률을 나타낸다.

### For events

Events $A$, $B$의 joint probability:

$$P(A \cap B) = P(A \text{ and } B)$$

두 사건이 **동시에** 발생할 확률.

### For random variables

Random variables $X$, $Y$의 joint probability:

$$P(X = x, Y = y) = P(\{\omega : X(\omega) = x \text{ and } Y(\omega) = y\})$$

$X$가 값 $x$를 가지고 **동시에** $Y$가 값 $y$를 가질 확률.

---

# <span class="header-definition">Joint Distributions</span>

## Discrete case^[이산 경우]

### Joint probability mass function (PMF)^[결합 확률 질량 함수]

$$p_{X,Y}(x, y) = P(X = x, Y = y)$$

**Properties^[성질]**:
1. $p_{X,Y}(x, y) \geq 0$ for all $(x, y)$
2. $\displaystyle\sum_x \displaystyle\sum_y p_{X,Y}(x, y) = 1$

### Multiple variables

$(X_1, \ldots, X_n)$의 joint PMF:

$$p_{X_1,\ldots,X_n}(x_1, \ldots, x_n) = P(X_1 = x_1, \ldots, X_n = x_n)$$

## Continuous case^[연속 경우]

### Joint probability density function (PDF)^[결합 확률 밀도 함수]

$$f_{X,Y}(x, y)$$

**Properties^[성질]**:
1. $f_{X,Y}(x, y) \geq 0$ for all $(x, y)$
2. $\displaystyle\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dx \, dy = 1$

### Probability of regions

$$P((X, Y) \in A) = \iint_A f_{X,Y}(x, y) \, dx \, dy$$

### Multiple variables

$(X_1, \ldots, X_n)$의 joint PDF:

$$f_{X_1,\ldots,X_n}(x_1, \ldots, x_n)$$

$$\int_{\mathbb{R}^n} f_{X_1,\ldots,X_n}(x_1, \ldots, x_n) \, dx_1 \cdots dx_n = 1$$

## Joint cumulative distribution function (CDF)^[결합 누적 분포 함수]

$$F_{X,Y}(x, y) = P(X \leq x, Y \leq y)$$

### Properties

1. **Non-decreasing**: $x_1 \leq x_2, y_1 \leq y_2 \Rightarrow F(x_1, y_1) \leq F(x_2, y_2)$
2. **Limits**: 
   - $F(-\infty, y) = F(x, -\infty) = 0$
   - $F(\infty, \infty) = 1$
3. **Right-continuous^[우연속]** in each argument

### Relation to PDF

$$f_{X,Y}(x, y) = \frac{\partial^2 F_{X,Y}(x, y)}{\partial x \, \partial y}$$

**상세한 내용**: [[Random Variables]] 참조

---

# <span class="header-properties">Properties and Relations</span>

## Chain rule^[연쇄 법칙] (Multiplication rule)

$$P(A \cap B) = P(A | B) \cdot P(B) = P(B | A) \cdot P(A)$$

For random variables:

$$p_{X,Y}(x, y) = p_{X|Y}(x | y) \cdot p_Y(y) = p_{Y|X}(y | x) \cdot p_X(x)$$

Continuous:

$$f_{X,Y}(x, y) = f_{X|Y}(x | y) \cdot f_Y(y) = f_{Y|X}(y | x) \cdot f_X(x)$$

**상세한 내용**: [[Conditional Probability]]

## General chain rule^[일반 연쇄 법칙]

$n$개 변수의 joint probability factorization^[인수분해]:

$$P(X_1, \ldots, X_n) = P(X_1) \cdot P(X_2 | X_1) \cdot P(X_3 | X_1, X_2) \cdots P(X_n | X_1, \ldots, X_{n-1})$$

이는 항상 성립 (conditional probability의 정의).

## Marginalization^[주변화]

Joint distribution에서 marginal distribution^[주변 분포] 추출:

### Discrete
$$p_X(x) = \displaystyle\sum_y p_{X,Y}(x, y)$$

### Continuous
$$f_X(x) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dy$$

**상세한 내용**: [[Marginal Probabilities]]

## Independence^[독립]

$X$와 $Y$가 **independent**^[독립] $\Leftrightarrow$ joint가 marginals의 곱으로 factorize:

### Discrete
$$p_{X,Y}(x, y) = p_X(x) \cdot p_Y(y) \quad \forall x, y$$

### Continuous
$$f_{X,Y}(x, y) = f_X(x) \cdot f_Y(y) \quad \forall x, y$$

### Multiple variables

$X_1, \ldots, X_n$이 **mutually independent**^[상호 독립] $\Leftrightarrow$

$$f_{X_1,\ldots,X_n}(x_1, \ldots, x_n) = f_{X_1}(x_1) \cdots f_{X_n}(x_n)$$

**상세한 내용**: [[Random Variables]] (Independence 섹션)

## Covariance^[공분산]

$$\text{Cov}(X, Y) = E[(X - E[X])(Y - E[Y])] = E[XY] - E[X]E[Y]$$

- $\text{Cov}(X, Y) = 0$ $\Leftrightarrow$ $X$, $Y$ are **uncorrelated**^[비상관]
- Independent $\Rightarrow$ Uncorrelated
- Uncorrelated $\not\Rightarrow$ Independent (일반적으로)

**상세한 내용**: [[Expected Value]]

## Correlation coefficient^[상관 계수]

$$\rho_{X,Y} = \frac{\text{Cov}(X, Y)}{\sqrt{\text{Var}(X)} \sqrt{\text{Var}(Y)}}$$

**Properties**:
- $-1 \leq \rho \leq 1$
- $\rho = 1$: Perfect positive linear relationship^[완전 양의 선형 관계]
- $\rho = -1$: Perfect negative linear relationship^[완전 음의 선형 관계]
- $\rho = 0$: Uncorrelated^[비상관] (not necessarily independent!)

---

# <span class="header-examples">Examples</span>

## 1. Discrete: Coin and die^[동전과 주사위]

동전 던지기 $C \in \{H, T\}$와 주사위 던지기 $D \in \{1, 2, 3, 4, 5, 6\}$:

Fair coin과 fair die가 independent하면:

$$P(C = H, D = 3) = P(C = H) \cdot P(D = 3) = \frac{1}{2} \cdot \frac{1}{6} = \frac{1}{12}$$

## 2. Discrete: Dependent example^[종속 예시]

두 변수 $X \in \{0, 1\}$, $Y \in \{0, 1\}$의 joint PMF:

| | $Y=0$ | $Y=1$ | Sum |
|---|---|---|---|
| $X=0$ | 0.2 | 0.3 | 0.5 |
| $X=1$ | 0.4 | 0.1 | 0.5 |
| Sum | 0.6 | 0.4 | 1.0 |

**Check independence**:
$$P(X=0, Y=0) = 0.2 \neq 0.5 \times 0.6 = 0.3 = P(X=0) \cdot P(Y=0)$$

따라서 **dependent**^[종속].

## 3. Continuous: Uniform on unit square^[단위 정사각형에서 균등]

$$f_{X,Y}(x, y) = \begin{cases}
1 & \text{if } 0 \leq x, y \leq 1 \\
0 & \text{otherwise}
\end{cases}$$

**Check independence**:
- Marginals: $f_X(x) = 1$ for $x \in [0, 1]$, $f_Y(y) = 1$ for $y \in [0, 1]$
- $f_{X,Y}(x, y) = 1 = 1 \times 1 = f_X(x) \cdot f_Y(y)$

따라서 **independent**^[독립].

## 4. Continuous: Uniform on triangle^[삼각형에서 균등]

Region: $\{(x, y) : 0 \leq x \leq 1, 0 \leq y \leq x\}$

$$f_{X,Y}(x, y) = \begin{cases}
2 & \text{if } 0 \leq y \leq x \leq 1 \\
0 & \text{otherwise}
\end{cases}$$

**Check independence**:
- Marginal of $X$: $f_X(x) = \int_0^x 2 \, dy = 2x$ for $x \in [0, 1]$
- Marginal of $Y$: $f_Y(y) = \int_y^1 2 \, dx = 2(1-y)$ for $y \in [0, 1]$
- $f_{X,Y}(0.5, 0.25) = 2 \neq 1 \times 1.5 = f_X(0.5) \cdot f_Y(0.25)$

따라서 **dependent**^[종속].

## 5. Bivariate normal distribution^[이변량 정규 분포]

$$f_{X,Y}(x, y) = \frac{1}{2\pi\sigma_X\sigma_Y\sqrt{1-\rho^2}} \exp\left(-\frac{Q(x, y)}{2(1-\rho^2)}\right)$$

여기서:
$$Q(x, y) = \frac{(x-\mu_X)^2}{\sigma_X^2} - \frac{2\rho(x-\mu_X)(y-\mu_Y)}{\sigma_X\sigma_Y} + \frac{(y-\mu_Y)^2}{\sigma_Y^2}$$

**Parameters**:
- $\mu_X, \mu_Y$: Means^[평균]
- $\sigma_X, \sigma_Y$: Standard deviations^[표준 편차]
- $\rho$: Correlation coefficient^[상관 계수] ($-1 \leq \rho \leq 1$)

**Special case**: $\rho = 0$ $\Rightarrow$ Independent normals!

$$f_{X,Y}(x, y) = \frac{1}{\sqrt{2\pi}\sigma_X} e^{-\frac{(x-\mu_X)^2}{2\sigma_X^2}} \cdot \frac{1}{\sqrt{2\pi}\sigma_Y} e^{-\frac{(y-\mu_Y)^2}{2\sigma_Y^2}}$$

## 6. Exponential: Waiting times^[대기 시간]

두 independent exponential random variables $X, Y \sim \text{Exp}(\lambda)$:

$$f_{X,Y}(x, y) = \lambda^2 e^{-\lambda(x + y)} \quad \text{for } x, y \geq 0$$

**Application**: 두 사건의 대기 시간.

---

# <span class="header-theorem">Important Results</span>

## Transformation of variables^[변수 변환]

$(X, Y)$에서 $(U, V)$로 변환: $U = g_1(X, Y)$, $V = g_2(X, Y)$

역변환이 존재하면:

$$f_{U,V}(u, v) = f_{X,Y}(x(u, v), y(u, v)) \cdot |J|$$

여기서 $J$는 **Jacobian**^[야코비안]:

$$J = \det \begin{pmatrix}
\frac{\partial x}{\partial u} & \frac{\partial x}{\partial v} \\
\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}
\end{pmatrix}$$

### Example: Sum and difference

$U = X + Y$, $V = X - Y$:

$$J = \det \begin{pmatrix}
\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & -\frac{1}{2}
\end{pmatrix} = -\frac{1}{2}$$

$$f_{U,V}(u, v) = f_{X,Y}\left(\frac{u+v}{2}, \frac{u-v}{2}\right) \cdot \frac{1}{2}$$

## Convolution^[합성곱]

$Z = X + Y$의 PDF (if $X$, $Y$ independent):

$$f_Z(z) = \int_{-\infty}^{\infty} f_X(x) f_Y(z - x) \, dx = (f_X * f_Y)(z)$$

**Example**: Sum of independent normals
$$X \sim \mathcal{N}(\mu_X, \sigma_X^2), Y \sim \mathcal{N}(\mu_Y, \sigma_Y^2) \Rightarrow X + Y \sim \mathcal{N}(\mu_X + \mu_Y, \sigma_X^2 + \sigma_Y^2)$$

## Copulas^[코퓰러]

Sklar's theorem: 임의의 joint distribution은 marginals와 copula^[코퓰러]로 분해 가능:

$$F_{X,Y}(x, y) = C(F_X(x), F_Y(y))$$

여기서 $C: [0, 1]^2 \rightarrow [0, 1]$은 copula.

**Interpretation**: Copula는 dependence structure^[의존 구조]를 포착, marginals와 독립적.

### Common copulas
- **Independence copula**: $C(u, v) = u \cdot v$
- **Gaussian copula**: Bivariate normal의 dependence structure
- **Archimedean copulas**: Clayton, Gumbel, Frank

**Applications**: Finance^[금융] (portfolio risk), Insurance^[보험]

---

# <span class="header-remark">Visualization</span>

## 2D representation

### Contour plot^[등고선 그림]

Joint PDF $f_{X,Y}(x, y)$의 level curves:

```
  Y
  ↑
  │     ╱─────╲
  │   ╱         ╲
  │  │           │  ← Contour lines
  │   ╲         ╱      (constant density)
  │     ╲─────╱
  └──────────────→ X
```

### Heatmap^[히트맵]

색상으로 density를 표현:
- 밝은 색: High density
- 어두운 색: Low density

## 3D surface

Joint PDF를 3D surface로:
- $x$-axis: $X$의 값
- $y$-axis: $Y$의 값
- $z$-axis: Density $f_{X,Y}(x, y)$

## Scatter plot with density^[밀도가 있는 산점도]

Samples $(x_i, y_i)$를 plot하면 joint distribution의 "모양" 파악 가능.

---

# <span class="header-remark">Applications</span>

## Statistics^[통계학]

### Multivariate analysis^[다변량 분석]
- Principal Component Analysis (PCA)
- Factor analysis^[요인 분석]
- Cluster analysis^[군집 분석]

### Regression^[회귀]
Joint distribution of $(X, Y)$에서 $E[Y | X]$ 추정.

### Hypothesis testing^[가설 검정]
Independence test^[독립성 검정]: Chi-square test, permutation test

## Machine learning

### Generative models^[생성 모델]
Joint distribution $p(x, y)$를 학습:
- Generative Adversarial Networks (GANs)
- Variational Autoencoders (VAEs)
- Normalizing flows

### Discriminative models^[판별 모델]
Conditional $p(y | x)$를 직접 학습 (종종 더 효율적).

### Graphical models^[그래프 모델]
- Bayesian networks^[베이지안 네트워크]: DAG로 joint distribution factorize
- Markov Random Fields: Undirected graph

## Finance^[금융]

### Portfolio theory^[포트폴리오 이론]
자산들의 joint distribution → Risk diversification^[위험 분산]

### Risk management^[위험 관리]
Copulas를 사용하여 extreme events^[극단 사건]의 joint behavior 모델링.

### Option pricing^[옵션 가격 결정]
Multi-asset options: Joint distribution of underlying assets.

## Physics^[물리학]

### Statistical mechanics^[통계 역학]
Particles의 joint distribution → Thermodynamic properties

### Quantum mechanics^[양자 역학]
Entangled states^[얽힌 상태]: Non-separable joint distribution

## Signal processing^[신호 처리]

Multiple signals의 joint distribution:
- Source separation^[신호원 분리]
- Sensor fusion^[센서 융합]
- Image processing^[이미지 처리] (pixel correlations)

---

# <span class="header-remark">Special Cases and Extensions</span>

## Conditional independence^[조건부 독립]

$X$와 $Y$가 $Z$가 주어졌을 때 **conditionally independent**^[조건부 독립]:

$$P(X, Y | Z) = P(X | Z) \cdot P(Y | Z)$$

즉, $Z$를 알면 $X$와 $Y$는 독립.

**Example**: $X$ = 키, $Y$ = 몸무게, $Z$ = 나이. 나이가 주어지면 키와 몸무게의 상관이 약해질 수 있음.

## Hierarchical models^[계층 모델]

$$p(x_1, x_2, \ldots, x_n, \theta) = p(\theta) \prod_{i=1}^n p(x_i | \theta)$$

$x_i$들은 $\theta$가 주어졌을 때 conditionally independent.

**Applications**: Bayesian inference^[베이지안 추론]

## Multivariate distributions^[다변량 분포]

### Multivariate normal^[다변량 정규]

$$\mathbf{X} \sim \mathcal{N}(\boldsymbol{\mu}, \boldsymbol{\Sigma})$$

$$f_{\mathbf{X}}(\mathbf{x}) = \frac{1}{(2\pi)^{n/2}|\boldsymbol{\Sigma}|^{1/2}} \exp\left(-\frac{1}{2}(\mathbf{x} - \boldsymbol{\mu})^T \boldsymbol{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu})\right)$$

### Multinomial distribution^[다항 분포]

$(X_1, \ldots, X_k)$ with $\displaystyle\sum_i X_i = n$:

$$P(X_1 = n_1, \ldots, X_k = n_k) = \frac{n!}{n_1! \cdots n_k!} p_1^{n_1} \cdots p_k^{n_k}$$

### Dirichlet distribution^[디리클레 분포]

Multivariate generalization of Beta distribution.

---

# <span class="header-examples">핵심 개념 요약</span>

```
Random Variables (X, Y, ...)
    ↓
Joint Distribution P(X, Y) or f_{X,Y}(x, y)
    ↓
    ├─ Marginalization → P(X) or f_X(x)
    ├─ Conditioning → P(X | Y) or f_{X|Y}(x|y)
    └─ Independence? → P(X, Y) = P(X)·P(Y)?
    ↓
Applications: Statistics, ML, Finance, Physics
```

## 핵심 공식

| Concept | Formula |
|---------|---------|
| Joint PMF | $p_{X,Y}(x, y) = P(X=x, Y=y)$ |
| Joint PDF | $f_{X,Y}(x, y)$, $\iint f_{X,Y} = 1$ |
| Chain rule | $p(X,Y) = p(X\|Y) \cdot p(Y)$ |
| Marginalization | $p_X(x) = \sum_y p_{X,Y}(x, y)$ |
| Independence | $p(X, Y) = p_X(x) \cdot p_Y(y)$ |
| Covariance | $\text{Cov}(X, Y) = E[XY] - E[X]E[Y]$ |
| Correlation | $\rho = \frac{\text{Cov}(X,Y)}{\sigma_X \sigma_Y}$ |

---

**기본 개념**: [[Sample Spaces]], [[Random Variables]]
**관련 주제**: [[Marginal Probabilities]], [[Conditional Probability]]
**응용**: [[Expected Value]], [[Bayes' Rule]]

