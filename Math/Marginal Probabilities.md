# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Random Variables]]
- [[Law of Total Probability]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Marginal probability^[주변 확률]

**Marginal probability**^[주변 확률]는 joint probability distribution^[결합 확률 분포]에서 일부 변수를 "integrate out"^[적분하여 제거]하여 얻는 확률 분포이다.

직관적으로, 관심 없는 변수들을 **marginalize out**^[주변화]하여 관심 변수만의 확률 분포를 얻는 것.

**Joint distribution 상세**: [[Joint Probabilities]]

### Origin of the term^[용어의 유래]

전통적으로 joint probability table^[결합 확률 표]의 **margin**^[여백]에 합을 적어서 marginal probability를 계산했기 때문에 이런 이름이 붙음.

---

# <span class="header-definition">Mathematical Formulation</span>

## Discrete case^[이산 경우]

Random variables $X$, $Y$의 joint PMF^[결합 확률 질량 함수] $P(X, Y)$에서:

### Marginal PMF of $X$

$$P_X(x) = P(X = x) = \displaystyle\sum_{y} P(X = x, Y = y)$$

모든 가능한 $Y$ 값에 대해 합산.

### Marginal PMF of $Y$

$$P_Y(y) = P(Y = y) = \displaystyle\sum_{x} P(X = x, Y = y)$$

모든 가능한 $X$ 값에 대해 합산.

## Continuous case^[연속 경우]

Random variables $X$, $Y$의 joint PDF^[결합 확률 밀도 함수] $f_{X,Y}(x, y)$에서:

### Marginal PDF of $X$

$$f_X(x) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dy$$

$Y$에 대해 적분하여 제거.

### Marginal PDF of $Y$

$$f_Y(y) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dx$$

$X$에 대해 적분하여 제거.

## Multiple variables^[다변수]

Random variables $X_1, \ldots, X_n$의 joint distribution에서 $X_1, \ldots, X_k$의 marginal:

### Discrete
$$P(X_1 = x_1, \ldots, X_k = x_k) = \displaystyle\sum_{x_{k+1}} \cdots \displaystyle\sum_{x_n} P(X_1 = x_1, \ldots, X_n = x_n)$$

### Continuous
$$f_{X_1,\ldots,X_k}(x_1, \ldots, x_k) = \int_{\mathbb{R}^{n-k}} f_{X_1,\ldots,X_n}(x_1, \ldots, x_n) \, dx_{k+1} \cdots dx_n$$

**상세한 내용**: [[Random Variables]] 참조

---

# <span class="header-properties">Properties</span>

## Relation to Law of Total Probability

Marginalization은 **[[Law of Total Probability]]**의 특수 경우:

$$P(X = x) = \displaystyle\sum_{y} P(X = x | Y = y) \cdot P(Y = y)$$

$\{Y = y\}$들이 partition^[분할]을 형성하므로.

## Successive marginalization^[연속적 주변화]

여러 변수를 순차적으로 marginalize 가능:

$$f_X(x) = \int \int f_{X,Y,Z}(x, y, z) \, dy \, dz = \int \left[\int f_{X,Y,Z}(x, y, z) \, dz\right] dy$$

순서는 상관없음 (Fubini's theorem).

## Marginals don't determine joint^[주변 분포가 결합 분포를 결정하지 않음]

**중요**: $P_X(x)$와 $P_Y(y)$를 알아도 $P(X, Y)$를 복원할 수 없음!

Counter-example: 서로 다른 dependence structure^[의존 구조]를 가진 두 joint distribution이 같은 marginals를 가질 수 있음.

**예외**: $X$, $Y$가 **independent**^[독립]이면:
$$P(X, Y) = P_X(x) \cdot P_Y(y)$$

**상세한 내용**: [[Random Variables]] (Independence 섹션) 참조

## Conservation of probability^[확률 보존]

Marginalization 후에도 확률의 합은 1:

$$\displaystyle\sum_x P_X(x) = \displaystyle\sum_x \displaystyle\sum_y P(X = x, Y = y) = 1$$

$$\int_{-\infty}^{\infty} f_X(x) \, dx = 1$$

---

# <span class="header-examples">Examples</span>

## 1. Discrete example: Two dice^[두 개의 주사위]

두 주사위 $X$, $Y$를 던져서 합 $S = X + Y$를 관찰.

### Joint distribution table

|  | $Y=1$ | $Y=2$ | $Y=3$ | $Y=4$ | $Y=5$ | $Y=6$ | $P_X(x)$ |
|---|---|---|---|---|---|---|---|
| $X=1$ | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | **1/6** |
| $X=2$ | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | **1/6** |
| $X=3$ | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | **1/6** |
| $X=4$ | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | **1/6** |
| $X=5$ | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | **1/6** |
| $X=6$ | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | 1/36 | **1/6** |
| $P_Y(y)$ | **1/6** | **1/6** | **1/6** | **1/6** | **1/6** | **1/6** | 1 |

- **Marginal of $X$**: 오른쪽 열 (행 합)
- **Marginal of $Y$**: 아래 행 (열 합)
- 각각 uniform distribution^[균등 분포] on $\{1, 2, 3, 4, 5, 6\}$

## 2. Continuous example: Uniform on unit square

Joint PDF on $[0, 1] \times [0, 1]$:

$$f_{X,Y}(x, y) = \begin{cases}
1 & \text{if } 0 \leq x, y \leq 1 \\
0 & \text{otherwise}
\end{cases}$$

### Marginal of $X$

$$f_X(x) = \int_0^1 f_{X,Y}(x, y) \, dy = \int_0^1 1 \, dy = 1 \quad \text{for } x \in [0, 1]$$

즉, $X \sim \text{Uniform}(0, 1)$.

마찬가지로 $Y \sim \text{Uniform}(0, 1)$.

이 경우 $X$와 $Y$는 independent^[독립].

## 3. Dependent variables example^[종속 변수 예시]

Joint PMF:

| | $Y=0$ | $Y=1$ | $P_X(x)$ |
|---|---|---|---|
| $X=0$ | 0.3 | 0.1 | **0.4** |
| $X=1$ | 0.2 | 0.4 | **0.6** |
| $P_Y(y)$ | **0.5** | **0.5** | 1 |

### Check independence^[독립성 확인]

$$P(X=0) \cdot P(Y=0) = 0.4 \times 0.5 = 0.2 \neq 0.3 = P(X=0, Y=0)$$

따라서 $X$와 $Y$는 **dependent**^[종속].

Marginals만으로는 dependence structure를 알 수 없음!

## 4. Triangular region^[삼각형 영역]

Joint PDF on triangular region $\{(x, y) : 0 \leq x \leq 1, 0 \leq y \leq x\}$:

$$f_{X,Y}(x, y) = \begin{cases}
2 & \text{if } 0 \leq y \leq x \leq 1 \\
0 & \text{otherwise}
\end{cases}$$

(Total probability = $\int_0^1 \int_0^x 2 \, dy \, dx = 1$)

### Marginal of $X$

$$f_X(x) = \int_0^x 2 \, dy = 2x \quad \text{for } x \in [0, 1]$$

### Marginal of $Y$

$$f_Y(y) = \int_y^1 2 \, dx = 2(1 - y) \quad \text{for } y \in [0, 1]$$

서로 다른 marginals! $X$와 $Y$는 dependent.

## 5. Normal distribution example^[정규 분포 예시]

Bivariate normal^[이변량 정규] $(X, Y)$ with correlation^[상관계수] $\rho$:

$$f_{X,Y}(x, y) = \frac{1}{2\pi\sigma_X\sigma_Y\sqrt{1-\rho^2}} \exp\left(-\frac{1}{2(1-\rho^2)}\left[\frac{(x-\mu_X)^2}{\sigma_X^2} - \frac{2\rho(x-\mu_X)(y-\mu_Y)}{\sigma_X\sigma_Y} + \frac{(y-\mu_Y)^2}{\sigma_Y^2}\right]\right)$$

### Marginals

$$X \sim \mathcal{N}(\mu_X, \sigma_X^2), \quad Y \sim \mathcal{N}(\mu_Y, \sigma_Y^2)$$

각각 normal distribution^[정규 분포]!

**중요**: 두 marginals가 normal이라고 해서 joint가 bivariate normal인 것은 아님. 그러나 bivariate normal의 marginals는 항상 normal.

---

# <span class="header-remark">Visualization</span>

## 2D joint distribution to 1D marginals

```
        Joint PDF f(x,y)
              ↓
    ┌─────────────────┐
    │    ╱╲           │
    │   ╱  ╲          │ ← Integrate over y
    │  ╱____╲         │    to get f_X(x)
    │                 │
    └─────────────────┘
           ↑
    Integrate over x
    to get f_Y(y)
```

3D surface (joint) → 2D curves (marginals)

## Marginal as projection^[사영으로서의 주변 분포]

기하학적으로, marginalization은 고차원 분포를 저차원으로 **projection**^[사영]하는 것:

- Joint distribution: $(x, y)$ 공간의 확률 밀도
- Marginal: $x$-축 (또는 $y$-축)으로 "그림자" 투영

## Probability table interpretation

```
Joint Table:
        Y₁    Y₂    Y₃   │ Marginal X
    ┌─────────────────────┼───────────
  X₁│ p₁₁   p₁₂   p₁₃   │ Σⱼ p₁ⱼ
  X₂│ p₂₁   p₂₂   p₂₃   │ Σⱼ p₂ⱼ
  X₃│ p₃₁   p₃₂   p₃₃   │ Σⱼ p₃ⱼ
    ├─────────────────────┼───────────
Marg│ Σᵢpᵢ₁ Σᵢpᵢ₂ Σᵢpᵢ₃ │   1
  Y │
```

- 행 합 → Marginal of $X$
- 열 합 → Marginal of $Y$

---

# <span class="header-remark">Applications</span>

## Statistical inference^[통계적 추론]

관심 있는 parameter^[모수]에 대한 marginal distribution을 얻기 위해 nuisance parameters^[불필요 모수]를 marginalize out.

**Bayesian statistics**:
$$p(\theta | \text{data}) = \int p(\theta, \phi | \text{data}) \, d\phi$$

## Machine learning

### Latent variable models^[잠재 변수 모델]

Observable $X$와 latent $Z$:
$$p(x) = \int p(x, z) \, dz = \int p(x | z) p(z) \, dz$$

Examples:
- Gaussian Mixture Models (GMM)
- Variational Autoencoders (VAE)
- Hidden Markov Models (HMM)

### Expectation-Maximization (EM) algorithm

E-step에서 latent variables를 marginalize out하여 expected log-likelihood 계산.

## Causal inference^[인과 추론]

Confounders^[교란 변수] $Z$를 control하기 위해:

$$P(Y | \text{do}(X = x)) = \displaystyle\sum_z P(Y | X = x, Z = z) \cdot P(Z = z)$$

## Graphical models^[그래프 모델]

Bayesian networks^[베이지안 네트워크]에서 일부 변수를 marginalize하여 query 계산:

$$P(X_i) = \displaystyle\sum_{X_1, \ldots, X_{i-1}, X_{i+1}, \ldots, X_n} P(X_1, \ldots, X_n)$$

**Sum-product algorithm**^[합곱 알고리즘] (message passing) 사용.

## Probability theory^[확률론]

### Mixture distributions^[혼합 분포]

$$f_X(x) = \int f_{X|Z}(x | z) \cdot f_Z(z) \, dz$$

이는 marginalization의 다른 표현.

### Change of variables^[변수 변환]

$(X, Y)$에서 $Z = g(X, Y)$의 분포를 구할 때 marginalization 사용.

---

# <span class="header-remark">Computational Aspects</span>

## Computational complexity^[계산 복잡도]

### Discrete case
$n$개 변수, 각각 $k$개 값:
- Joint: $k^n$ entries
- Marginal 계산: $O(k^n)$ operations

### Curse of dimensionality^[차원의 저주]

고차원에서는 marginalization이 계산적으로 매우 비쌈.

## Approximation methods^[근사 방법]

### Monte Carlo integration^[몬테카를로 적분]

$$f_X(x) = \int f_{X,Y}(x, y) \, dy \approx \frac{1}{N} \displaystyle\sum_{i=1}^N f_{X,Y}(x, y_i)$$

여기서 $y_i \sim f_Y(y | x)$.

### Variational inference^[변분 추론]

True marginal $p(x)$를 tractable distribution $q(x)$로 근사.

### Markov Chain Monte Carlo (MCMC)

Gibbs sampling, Metropolis-Hastings 등을 사용하여 marginal distribution sampling.

---

# <span class="header-remark">Related Concepts</span>

## Marginal vs Conditional^[주변 확률 vs 조건부 확률]

| | **Marginal** | **Conditional** |
|---|---|---|
| **Question** | "What is $P(X)$?" | "What is $P(X \| Y)$?" |
| **Formula** | $\displaystyle\sum_y P(X, Y)$ | $\frac{P(X, Y)}{P(Y)}$ |
| **Interpretation** | Unconditional probability | Probability given information |
| **Dependency** | Integrates out other variables | Fixes other variables |

**관계식**:
$$P(X) = \displaystyle\sum_y P(X | Y = y) \cdot P(Y = y)$$

**상세한 내용**: [[Conditional Probability]]

## Marginal vs Joint^[주변 확률 vs 결합 확률]

- **Joint**: 여러 변수의 동시 분포 $P(X, Y, Z, \ldots)$
- **Marginal**: Joint에서 일부 변수를 제거 $P(X)$

Joint $\rightarrow$ Marginal (가능)
Marginal $\rightarrow$ Joint (일반적으로 불가능, 독립일 때만 가능)

**상세한 내용**: [[Joint Probabilities]]

## Connection to expectation^[기댓값과의 연결]

Marginalization은 일종의 **expectation**^[기댓값]:

$$f_X(x) = \int f_{X,Y}(x, y) \, dy = E_Y[f_{X,Y}(x, Y)]$$

$Y$에 대한 평균을 취하는 것.

**상세한 내용**: [[Expected Value]]

---

# <span class="header-examples">핵심 공식 요약</span>

| Case | Formula | Description |
|------|---------|-------------|
| Discrete (sum) | $P_X(x) = \displaystyle\sum_y P(X=x, Y=y)$ | $Y$에 대해 합산 |
| Continuous (integrate) | $f_X(x) = \int f_{X,Y}(x, y) \, dy$ | $Y$에 대해 적분 |
| Via Law of Total Prob. | $P(X) = \displaystyle\sum_y P(X\|Y=y) P(Y=y)$ | 조건부 확률 사용 |
| Multiple variables | $P(X) = \displaystyle\sum_{y,z,\ldots} P(X,Y,Z,\ldots)$ | 여러 변수 제거 |
| Independence | $P(X,Y) = P_X(x) \cdot P_Y(y)$ | 독립일 때 factorization |

---

**기본 개념**: [[Sample Spaces]], [[Random Variables]]
**관련 정리**: [[Law of Total Probability]], [[Conditional Probability]]
**응용**: [[Expected Value]], [[Bayes' Rule]]

