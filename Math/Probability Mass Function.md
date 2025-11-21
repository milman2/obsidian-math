# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Random Variables]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Probability mass function (PMF)^[확률 질량 함수]

**Probability mass function**^[확률 질량 함수] (PMF)는 **discrete random variable**^[이산 확률 변수]의 확률 분포를 나타내는 함수이다.

Random variable $X$가 discrete이면, PMF $p_X: \mathbb{R} \rightarrow [0, 1]$은:

$$p_X(x) = P(X = x) = P(\{\omega \in \Omega : X(\omega) = x\})$$

$X$가 정확히 값 $x$를 가질 확률.

### "Mass"의 의미

"Mass"^[질량]라는 용어는 물리학에서 유래:
- 각 값 $x$에 확률 "질량" $p_X(x)$가 배정됨
- 전체 질량의 합은 1 (전확률)
- Discrete points에 질량이 집중됨

**참고**: Continuous case는 [[Probability Density Function]] 참조

---

# <span class="header-properties">Properties</span>

## Axioms^[공리]

PMF $p_X(x)$는 다음을 만족:

### 1. Non-negativity^[비음성]

$$p_X(x) \geq 0 \quad \forall x \in \mathbb{R}$$

모든 값에서 확률은 0 이상.

### 2. Normalization^[정규화]

$$\displaystyle\sum_{x \in \text{Range}(X)} p_X(x) = 1$$

또는 더 일반적으로:

$$\displaystyle\sum_{x \in \mathbb{R}} p_X(x) = 1$$

(대부분의 $x$에서 $p_X(x) = 0$)

### 3. At most countable support^[기껏해야 가산 개의 지지집합]

$\{x : p_X(x) > 0\}$는 countable^[가산]이다.

## Support^[지지집합]

PMF의 **support**^[지지집합]:

$$\text{Supp}(p_X) = \{x \in \mathbb{R} : p_X(x) > 0\}$$

$X$가 양의 확률로 가질 수 있는 값들의 집합.

## Relation to CDF^[누적 분포 함수와의 관계]

$$F_X(x) = P(X \leq x) = \displaystyle\sum_{t \leq x} p_X(t)$$

CDF는 PMF의 누적합^[cumulative sum].

역으로:
$$p_X(x) = F_X(x) - F_X(x^-)$$

여기서 $F_X(x^-) = \displaystyle\lim_{t \to x^-} F_X(t)$.

**상세한 내용**: [[Random Variables]] (CDF 섹션)

## Probability calculation^[확률 계산]

### Single point

$$P(X = x) = p_X(x)$$

Discrete case의 특징: 단일 점의 확률이 0이 아님!

### Set of values

Event $A \subseteq \mathbb{R}$에 대해:

$$P(X \in A) = \displaystyle\sum_{x \in A} p_X(x)$$

### Interval

$$P(a \leq X \leq b) = \displaystyle\sum_{a \leq x \leq b} p_X(x)$$

---

# <span class="header-examples">Common Distributions</span>

## 1. Bernoulli distribution^[베르누이 분포]

**Parameter**: $p \in [0, 1]$ (success probability)

**Support**: $\{0, 1\}$

**PMF**:
$$p_X(k) = \begin{cases}
1-p & k = 0 \\
p & k = 1 \\
0 & \text{otherwise}
\end{cases}$$

또는 간결하게: $p_X(k) = p^k (1-p)^{1-k}$ for $k \in \{0, 1\}$

**Moments**:
- $E[X] = p$
- $\text{Var}(X) = p(1-p)$

**Application**: Single trial (동전 던지기, 성공/실패)

## 2. Binomial distribution^[이항 분포]

**Parameters**: $n \in \mathbb{N}$ (trials), $p \in [0, 1]$ (success probability)

**Notation**: $X \sim \text{Binomial}(n, p)$ or $B(n, p)$

**Support**: $\{0, 1, 2, \ldots, n\}$

**PMF**:
$$p_X(k) = \binom{n}{k} p^k (1-p)^{n-k}, \quad k = 0, 1, \ldots, n$$

**Moments**:
- $E[X] = np$
- $\text{Var}(X) = np(1-p)$

**Application**: $n$번 독립 시행에서 성공 횟수

**Connection**: $X_1, \ldots, X_n \sim \text{Bernoulli}(p)$ i.i.d. $\Rightarrow$ $X_1 + \cdots + X_n \sim \text{Binomial}(n, p)$

## 3. Poisson distribution^[푸아송 분포]

**Parameter**: $\lambda > 0$ (rate)

**Notation**: $X \sim \text{Poisson}(\lambda)$

**Support**: $\{0, 1, 2, 3, \ldots\}$ (non-negative integers)

**PMF**:
$$p_X(k) = \frac{\lambda^k e^{-\lambda}}{k!}, \quad k = 0, 1, 2, \ldots$$

**Moments**:
- $E[X] = \lambda$
- $\text{Var}(X) = \lambda$

특이하게 평균과 분산이 같음!

**Applications**:
- 단위 시간/공간당 발생 횟수 (전화 통화, 웹사이트 방문, 방사성 붕괴)
- Rare events^[희귀 사건]

**Poisson limit theorem**: $n \to \infty$, $p \to 0$, $np = \lambda$ (고정)이면,
$$\text{Binomial}(n, p) \xrightarrow{d} \text{Poisson}(\lambda)$$

## 4. Geometric distribution^[기하 분포]

**Parameter**: $p \in (0, 1]$ (success probability)

**Support**: $\{1, 2, 3, \ldots\}$ (첫 성공까지 시행 횟수)

**PMF**:
$$p_X(k) = (1-p)^{k-1} p, \quad k = 1, 2, 3, \ldots$$

**Moments**:
- $E[X] = \frac{1}{p}$
- $\text{Var}(X) = \frac{1-p}{p^2}$

**Memoryless property**^[무기억성]:
$$P(X > n + m | X > n) = P(X > m)$$

과거를 "기억하지 않음" (유일한 discrete memoryless distribution!)

**Application**: 첫 성공까지 대기 시간

**Alternative**: Support $\{0, 1, 2, \ldots\}$ (실패 횟수)도 사용됨.

## 5. Negative binomial distribution^[음이항 분포]

**Parameters**: $r \in \mathbb{N}$ (목표 성공 횟수), $p \in (0, 1]$

**Support**: $\{r, r+1, r+2, \ldots\}$

**PMF**:
$$p_X(k) = \binom{k-1}{r-1} p^r (1-p)^{k-r}, \quad k = r, r+1, \ldots$$

**Moments**:
- $E[X] = \frac{r}{p}$
- $\text{Var}(X) = \frac{r(1-p)}{p^2}$

**Application**: $r$번째 성공까지 시행 횟수

**Connection**: $r = 1$이면 Geometric distribution

## 6. Hypergeometric distribution^[초기하 분포]

**Parameters**: 
- $N$: 전체 개수
- $K$: 성공 상태 개수
- $n$: 추출 개수

**Support**: $\{\max(0, n-N+K), \ldots, \min(n, K)\}$

**PMF**:
$$p_X(k) = \frac{\binom{K}{k}\binom{N-K}{n-k}}{\binom{N}{n}}$$

**Application**: 비복원 추출 (without replacement)

**Connection**: $N \to \infty$, $K/N \to p$이면 $\text{Binomial}(n, p)$로 근사

## 7. Discrete uniform distribution^[이산 균등 분포]

**Parameter**: Finite set $\{a, a+1, \ldots, b\}$

**PMF**:
$$p_X(k) = \frac{1}{b-a+1}, \quad k = a, a+1, \ldots, b$$

**Moments**:
- $E[X] = \frac{a+b}{2}$
- $\text{Var}(X) = \frac{(b-a+1)^2 - 1}{12}$

**Application**: Fair die^[공정한 주사위], random selection

---

# <span class="header-examples">Examples</span>

## 1. Coin flips^[동전 던지기]

Fair coin 10번 던져서 앞면 횟수 $X$:

$$X \sim \text{Binomial}(10, 0.5)$$

$$P(X = 7) = \binom{10}{7} (0.5)^7 (0.5)^3 = 120 \times \frac{1}{1024} = \frac{15}{128} \approx 0.117$$

## 2. Quality control^[품질 관리]

불량률 2%인 제품에서 첫 불량품 찾을 때까지 검사 횟수 $X$:

$$X \sim \text{Geometric}(0.02)$$

$$P(X \leq 10) = 1 - P(X > 10) = 1 - (0.98)^{10} \approx 0.183$$

## 3. Customer arrivals^[고객 도착]

시간당 평균 5명 도착하는 상점, 한 시간에 정확히 3명 도착할 확률:

$$X \sim \text{Poisson}(5)$$

$$P(X = 3) = \frac{5^3 e^{-5}}{3!} = \frac{125 e^{-5}}{6} \approx 0.140$$

## 4. Lottery^[복권]

52장 카드에서 5장 뽑을 때 하트 개수 $X$ (하트 13장):

$$X \sim \text{Hypergeometric}(52, 13, 5)$$

$$P(X = 2) = \frac{\binom{13}{2}\binom{39}{3}}{\binom{52}{5}} = \frac{78 \times 9139}{2598960} \approx 0.274$$

---

# <span class="header-properties">Operations on PMFs</span>

## Sum of independent variables

$X$, $Y$ independent discrete random variables:

$$p_{X+Y}(z) = \displaystyle\sum_{x} p_X(x) \cdot p_Y(z - x)$$

이는 **convolution**^[합성곱]이다: $p_{X+Y} = p_X * p_Y$

### Example
$X \sim \text{Binomial}(n, p)$, $Y \sim \text{Binomial}(m, p)$ independent $\Rightarrow$
$$X + Y \sim \text{Binomial}(n+m, p)$$

## Transformation

$Y = g(X)$이면:

$$p_Y(y) = \displaystyle\sum_{x: g(x) = y} p_X(x)$$

역함수가 unique하면:
$$p_Y(y) = p_X(g^{-1}(y))$$

## Mixture distribution^[혼합 분포]

Weight $w_1, \ldots, w_k$ ($\displaystyle\sum_i w_i = 1$)로 PMF들을 혼합:

$$p_X(x) = \displaystyle\sum_{i=1}^k w_i \cdot p_i(x)$$

---

# <span class="header-remark">Visualization</span>

## Bar chart^[막대 그래프]

PMF를 시각화하는 표준 방법:
- $x$-axis: 가능한 값들
- $y$-axis: 확률 $p_X(x)$
- 각 값에 막대 (bar)

```
p(x)
  ↑
  │    ▂
  │  ▂ █     ▂
  │  █ █   ▂ █
  │▂ █ █ ▂ █ █ ▂
  └─────────────→ x
   0 1 2 3 4 5 6
```

## Stem plot^[줄기 그래프]

각 점에서 수직선:
- Discrete nature 강조
- 연속이 아님을 명확히 표현

## Cumulative plot^[누적 그래프]

CDF $F_X(x) = \displaystyle\sum_{t \leq x} p_X(t)$:
- Step function^[계단 함수]
- Jump size = $p_X(x)$

---

# <span class="header-remark">Properties and Relationships</span>

## Expectation^[기댓값]

$$E[X] = \displaystyle\sum_{x} x \cdot p_X(x)$$

**Law of the unconscious statistician (LOTUS)**:
$$E[g(X)] = \displaystyle\sum_{x} g(x) \cdot p_X(x)$$

**상세한 내용**: [[Expected Value]]

## Variance^[분산]

$$\text{Var}(X) = \displaystyle\sum_{x} (x - E[X])^2 \cdot p_X(x) = E[X^2] - E[X]^2$$

## Moments^[적률]

$n$-th moment:
$$E[X^n] = \displaystyle\sum_{x} x^n \cdot p_X(x)$$

## Probability generating function (PGF)^[확률 생성 함수]

Non-negative integer-valued $X$에 대해:

$$G_X(s) = E[s^X] = \displaystyle\sum_{k=0}^\infty p_X(k) \cdot s^k$$

**Properties**:
- $G_X(1) = 1$
- $G_X'(1) = E[X]$
- $p_X(k) = \frac{G_X^{(k)}(0)}{k!}$

**Application**: 독립 변수 합의 분포 계산이 쉬움
$$X + Y \text{ independent} \Rightarrow G_{X+Y}(s) = G_X(s) \cdot G_Y(s)$$

## Moment generating function (MGF)^[적률 생성 함수]

$$M_X(t) = E[e^{tX}] = \displaystyle\sum_{x} e^{tx} \cdot p_X(x)$$

(수렴 영역에서)

**상세한 내용**: [[Expected Value]]

---

# <span class="header-remark">Comparison with PDF</span>

| | **PMF** (Discrete) | **PDF** (Continuous) |
|---|---|---|
| **Definition** | $p_X(x) = P(X = x)$ | $f_X(x)$ s.t. $F_X(x) = \int f_X$ |
| **Interpretation** | Probability at $x$ | Density at $x$ (not probability!) |
| **Single point** | $P(X = x) = p_X(x) > 0$ | $P(X = x) = 0$ |
| **Support** | Countable set | Uncountable set |
| **Normalization** | $\displaystyle\sum_x p_X(x) = 1$ | $\displaystyle\int f_X(x) dx = 1$ |
| **Interval** | $P(X \in [a,b]) = \displaystyle\sum_{a \leq x \leq b} p_X(x)$ | $P(X \in [a,b]) = \displaystyle\int_a^b f_X(x) dx$ |
| **Expectation** | $E[X] = \displaystyle\sum_x x \cdot p_X(x)$ | $E[X] = \displaystyle\int x \cdot f_X(x) dx$ |

**상세한 내용**: [[Probability Density Function]]

---

# <span class="header-remark">Applications</span>

## Statistics^[통계학]

- **Parameter estimation^[모수 추정]**: Maximum likelihood estimation (MLE)
- **Hypothesis testing^[가설 검정]**: Chi-square goodness-of-fit test
- **Bayesian inference^[베이지안 추론]**: Prior/posterior distributions

## Machine learning

- **Classification^[분류]**: Categorical output distributions
- **Naive Bayes**: Class-conditional PMFs
- **Language models^[언어 모델]**: Word/token probabilities
- **Discrete latent variables^[이산 잠재 변수]**: Mixture models

## Computer science^[컴퓨터 과학]

- **Algorithm analysis^[알고리즘 분석]**: Randomized algorithms
- **Hashing**: Collision probabilities
- **Data compression^[데이터 압축]**: Huffman coding (entropy)
- **Simulation^[시뮬레이션]**: Random number generation

## Operations research^[운영 과학]

- **Queueing theory^[대기 행렬 이론]**: Poisson arrivals
- **Inventory management^[재고 관리]**: Demand distributions
- **Reliability^[신뢰성]**: Component failure counts

## Biology and medicine^[생물학과 의학]

- **Genetics^[유전학]**: Allele distributions
- **Epidemiology^[역학]**: Disease spread (SIR models)
- **Clinical trials^[임상 시험]**: Success/failure counts

---

# <span class="header-examples">핵심 공식 요약</span>

| Distribution | PMF | Mean | Variance |
|--------------|-----|------|----------|
| Bernoulli($p$) | $p^k(1-p)^{1-k}$ | $p$ | $p(1-p)$ |
| Binomial($n, p$) | $\binom{n}{k}p^k(1-p)^{n-k}$ | $np$ | $np(1-p)$ |
| Poisson($\lambda$) | $\frac{\lambda^k e^{-\lambda}}{k!}$ | $\lambda$ | $\lambda$ |
| Geometric($p$) | $(1-p)^{k-1}p$ | $\frac{1}{p}$ | $\frac{1-p}{p^2}$ |
| Discrete Uniform($a, b$) | $\frac{1}{b-a+1}$ | $\frac{a+b}{2}$ | $\frac{(b-a+1)^2-1}{12}$ |

---

**기본 개념**: [[Sample Spaces]], [[Random Variables]]
**연속 버전**: [[Probability Density Function]]
**관련 주제**: [[Joint Probabilities]], [[Marginal Probabilities]], [[Conditional Probability]]
**응용**: [[Expected Value]]

