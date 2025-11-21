# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Conditional Probability]]
- [[Law of Total Probability]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Expected value^[기댓값]

**Expected value**^[기댓값] (또는 Expectation^[기대], Mean^[평균])는 random variable^[확률 변수]의 평균적인 값을 나타내는 측도^[측도].

### Discrete case^[이산 경우]

Discrete random variable $X$가 값 $\{x_i\}$를 가지면:

$$E[X] = \displaystyle\sum_{i} x_i \cdot P(X = x_i)$$

(단, 급수가 absolutely convergent^[절대 수렴]해야 함)

### Continuous case^[연속 경우]

Continuous random variable $X$가 probability density function^[확률 밀도 함수] $f_X(x)$를 가지면:

$$E[X] = \int_{-\infty}^{\infty} x \cdot f_X(x) \, dx$$

(단, 적분이 absolutely convergent^[절대 수렴]해야 함)

### General definition^[일반적 정의]

Probability space^[확률 공간] $(\Omega, \mathcal{F}, P)$에서 measurable function^[가측 함수] $X: \Omega \rightarrow \mathbb{R}$에 대해:

$$E[X] = \int_\Omega X \, dP$$

이는 Lebesgue integral^[르베스그 적분]로 정의됨.

## Notation^[표기법]

- $E[X]$, $\mathbb{E}[X]$: Expected value
- $\mu_X$, $\langle X \rangle$: Mean (물리학에서 자주 사용)
- $\bar{X}$: Sample mean^[표본 평균] (통계학)

---

# <span class="header-properties">Properties</span>

## Linearity^[선형성]

Expected value는 **linear operator^[선형 연산자]**:

### 1. Additivity^[가법성]

$$E[X + Y] = E[X] + E[Y]$$

이는 $X$, $Y$가 **independent^[독립]이 아니어도** 성립!

### 2. Homogeneity^[동차성]

상수 $c$에 대해:

$$E[cX] = c \cdot E[X]$$

### Combined linearity

$$E\left[\displaystyle\sum_{i=1}^n a_i X_i\right] = \displaystyle\sum_{i=1}^n a_i E[X_i]$$

## Monotonicity^[단조성]

$X \leq Y$ (almost surely^[거의 확실히]) $\Rightarrow$ $E[X] \leq E[Y]$

특히:
- $X \geq 0$ $\Rightarrow$ $E[X] \geq 0$
- $|E[X]| \leq E[|X|]$ (Triangle inequality^[삼각 부등식])

## Constant^[상수]

$c$가 상수이면:

$$E[c] = c$$

## Product of independent variables^[독립 변수의 곱]

$X$, $Y$가 **independent^[독립]**이면:

$$E[XY] = E[X] \cdot E[Y]$$

**주의**: 역은 일반적으로 성립하지 않음!

## Conditional expectation^[조건부 기댓값]

Event $B$가 주어졌을 때:

$$E[X | B] = \int_\Omega X \, dP(\cdot | B)$$

**Measure-theoretic interpretation**^[측도론적 해석]: Normalized subspace measure에서의 적분.

**상세한 내용**: [[Subspace Measure]]

Discrete case:
$$E[X | B] = \displaystyle\sum_{x} x \cdot P(X = x | B)$$

**상세한 내용**: [[Conditional Probability]] 참조

---

# <span class="header-theorem">Theorem</span>

## Law of total expectation^[전기댓값 공식]

Partition^[분할] $\{B_i\}$에 대해:

$$E[X] = \displaystyle\sum_i E[X | B_i] \cdot P(B_i)$$

이는 **[[Law of Total Probability]]**의 expectation 버전.

### Tower property^[탑 성질]

Random variables $X$, $Y$에 대해:

$$E[E[X | Y]] = E[X]$$

이는 Law of total expectation의 일반화.

**상세한 내용**: [[Law of Total Probability]] 참조

## Jensen's inequality^[젠센 부등식]

Convex function^[볼록 함수] $\phi$에 대해:

$$\phi(E[X]) \leq E[\phi(X)]$$

Concave function^[오목 함수]이면 부등호 반대.

### Applications
- $\phi(x) = x^2$ (convex): $E[X]^2 \leq E[X^2]$ → Variance $\geq 0$
- $\phi(x) = -\log(x)$ (convex): $E[\log X] \leq \log E[X]$
- $\phi(x) = e^x$ (convex): $e^{E[X]} \leq E[e^X]$

## Markov's inequality^[마르코프 부등식]

$X \geq 0$이고 $a > 0$이면:

$$P(X \geq a) \leq \frac{E[X]}{a}$$

### Proof sketch
$$E[X] = \int_0^\infty x \, dP_X(x) \geq \int_a^\infty x \, dP_X(x) \geq a \int_a^\infty dP_X(x) = a \cdot P(X \geq a)$$

## Chebyshev's inequality^[체비셰프 부등식]

Variance^[분산] $\text{Var}(X) = E[(X - E[X])^2]$에 대해:

$$P(|X - E[X]| \geq a) \leq \frac{\text{Var}(X)}{a^2}$$

Markov's inequality를 $(X - E[X])^2$에 적용하여 유도.

---

# <span class="header-examples">Examples</span>

## 1. Discrete distributions

### Bernoulli distribution^[베르누이 분포]

$X \in \{0, 1\}$, $P(X = 1) = p$:

$$E[X] = 0 \cdot (1-p) + 1 \cdot p = p$$

### Binomial distribution^[이항 분포]

$X \sim \text{Binomial}(n, p)$, $X = $ (n번 중 성공 횟수):

$$E[X] = np$$

**유도**: $X = X_1 + \cdots + X_n$ (각 $X_i \sim \text{Bernoulli}(p)$)

$$E[X] = E[X_1] + \cdots + E[X_n] = np$$

### Geometric distribution^[기하 분포]

$X = $ (첫 성공까지 시도 횟수), $P(X = k) = (1-p)^{k-1} p$:

$$E[X] = \frac{1}{p}$$

### Poisson distribution^[푸아송 분포]

$X \sim \text{Poisson}(\lambda)$:

$$E[X] = \lambda$$

## 2. Continuous distributions

### Uniform distribution^[균등 분포]

$X \sim \text{Uniform}(a, b)$, $f_X(x) = \frac{1}{b-a}$ for $x \in [a, b]$:

$$E[X] = \int_a^b x \cdot \frac{1}{b-a} \, dx = \frac{a+b}{2}$$

### Exponential distribution^[지수 분포]

$X \sim \text{Exponential}(\lambda)$, $f_X(x) = \lambda e^{-\lambda x}$ for $x \geq 0$:

$$E[X] = \int_0^\infty x \lambda e^{-\lambda x} \, dx = \frac{1}{\lambda}$$

### Normal distribution^[정규 분포]

$X \sim \mathcal{N}(\mu, \sigma^2)$:

$$E[X] = \mu$$

정규 분포는 $\mu$를 중심으로 대칭이므로 기댓값이 $\mu$.

## 3. Non-existent expectation^[존재하지 않는 기댓값]

### Cauchy distribution^[코시 분포]

$f_X(x) = \frac{1}{\pi(1 + x^2)}$:

$$\int_{-\infty}^\infty |x| \cdot \frac{1}{\pi(1 + x^2)} \, dx = \infty$$

적분이 발산하므로 $E[X]$가 정의되지 않음!

## 4. St. Petersburg paradox^[상트페테르부르크 역설]

동전 던지기 게임:
- 첫 Heads가 $n$번째에 나오면: 상금 $2^n$

Expected payout:

$$E[\text{payout}] = \displaystyle\sum_{n=1}^\infty 2^n \cdot \frac{1}{2^n} = \displaystyle\sum_{n=1}^\infty 1 = \infty$$

기댓값이 무한대! 얼마를 내고 게임에 참여해야 하는가?

---

# <span class="header-remark">Remark</span>

## Relation to other concepts^[다른 개념과의 관계]

### Variance^[분산]

$$\text{Var}(X) = E[(X - E[X])^2] = E[X^2] - E[X]^2$$

Variance는 "expected value로부터의 평균 편차"를 측정.

**Properties**:
- $\text{Var}(aX + b) = a^2 \text{Var}(X)$ (not linear!)
- $X$, $Y$ independent: $\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y)$

### Moments^[적률]

$n$-th **moment^[n차 적률]**:

$$\mu_n = E[X^n]$$

$n$-th **central moment^[n차 중심 적률]**:

$$\mu_n' = E[(X - E[X])^n]$$

- 1st moment: Mean^[평균] = $E[X]$
- 2nd central moment: Variance^[분산] = $\text{Var}(X)$
- 3rd central moment: Skewness^[왜도] 관련
- 4th central moment: Kurtosis^[첨도] 관련

### Median vs Mean^[중앙값 vs 평균]

- **Mean^[평균]**: $E[X]$
- **Median^[중앙값]**: $P(X \leq m) = P(X \geq m) = \frac{1}{2}$

Mean은 outliers^[이상치]에 민감, Median은 robust^[견고].

### Mode^[최빈값]

Density가 최대인 값:

$$\text{mode} = \arg\max_x f_X(x)$$

## Interpretation^[해석]

### Frequentist interpretation^[빈도주의 해석]

Law of large numbers^[큰 수의 법칙]:

$$\frac{X_1 + \cdots + X_n}{n} \xrightarrow{n \to \infty} E[X]$$

$n$번 반복 실험의 평균이 expected value로 수렴.

### Center of mass^[질량 중심]

Expected value는 확률 분포의 "무게 중심"으로 해석 가능.

### Fair price^[공정 가격]

도박/게임에서 expected value는 장기적으로 "공정한" 가격.

## Conditional expectation as projection^[조건부 기댓값을 사영으로]

$L^2(\Omega, \mathcal{F}, P)$ Hilbert space^[힐베르트 공간]에서:

$$E[X | \mathcal{G}] = \text{Projection of } X \text{ onto } L^2(\Omega, \mathcal{G}, P)$$

이는 functional analysis^[함수해석학] 관점에서의 해석.

**참고**: [[Hilbert Space]], [[Riesz Representation Theorem]]

## Applications^[응용]

### Probability theory
- Law of large numbers^[큰 수의 법칙]
- Central limit theorem^[중심극한정리]
- Martingales^[마팅게일]

### Statistics
- Point estimation^[점 추정]: Sample mean^[표본 평균]
- Hypothesis testing^[가설 검정]
- Regression analysis^[회귀 분석]

### Economics and Finance
- Expected utility theory^[기대 효용 이론]
- Portfolio optimization^[포트폴리오 최적화]
- Option pricing^[옵션 가격 결정] (Black-Scholes)

### Machine learning
- Loss functions^[손실 함수]: $\min E[\text{loss}(X, \hat{X})]$
- Reinforcement learning^[강화 학습]: Expected reward^[기대 보상]
- Bayesian inference^[베이지안 추론]

### Engineering
- Signal processing^[신호 처리]: Mean filtering^[평균 필터링]
- Control theory^[제어 이론]: Expected cost^[기대 비용]
- Reliability theory^[신뢰성 이론]: Mean time to failure^[평균 고장 시간]

## Computing expectations^[기댓값 계산]

### Direct computation
- Discrete: Sum over all values
- Continuous: Integrate $x f_X(x)$

### Using moment generating function^[적률 생성 함수]

$$M_X(t) = E[e^{tX}] \Rightarrow E[X] = M_X'(0)$$

### Using characteristic function^[특성 함수]

$$\phi_X(t) = E[e^{itX}] \Rightarrow E[X] = -i \phi_X'(0)$$

### Simulation^[시뮬레이션]
Monte Carlo method^[몬테카를로 방법]: $E[X] \approx \frac{1}{n} \displaystyle\sum_{i=1}^n X_i$

---

# <span class="header-examples">핵심 공식 요약</span>

| 개념 | 공식 |
|------|------|
| Definition (discrete) | $E[X] = \displaystyle\sum_i x_i P(X = x_i)$ |
| Definition (continuous) | $E[X] = \int x f_X(x) \, dx$ |
| Linearity | $E[aX + bY] = aE[X] + bE[Y]$ |
| Independence | $E[XY] = E[X]E[Y]$ (if independent) |
| Law of total expectation | $E[X] = \displaystyle\sum_i E[X\|B_i] P(B_i)$ |
| Tower property | $E[E[X\|Y]] = E[X]$ |
| Variance | $\text{Var}(X) = E[X^2] - E[X]^2$ |
| Jensen's inequality | $\phi(E[X]) \leq E[\phi(X)]$ (convex $\phi$) |
| Markov's inequality | $P(X \geq a) \leq \frac{E[X]}{a}$ |
| Chebyshev's inequality | $P(\|X - E[X]\| \geq a) \leq \frac{\text{Var}(X)}{a^2}$ |

---

**확률론 개관**: [[Probability]]
**기본 정의**: [[Sample Spaces]], [[Random Variables]], [[Measure Space]]
**측도론적 관점**: [[Subspace Measure]]
**분포 함수**: [[Probability Mass Function]], [[Probability Density Function]]
**관련 분포**: [[Joint Probabilities]], [[Marginal Probabilities]], [[Conditional Probability]]
**전기댓값 공식**: [[Law of Total Probability]]
**재귀적 응용**: [[Recursive Thinking]]

