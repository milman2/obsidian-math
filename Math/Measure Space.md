# <span class="header-prerequisite">Prerequisite</span>
- [[Borel Sigma Algebra]]
- Set theory (집합론)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Measure space^[측도 공간]

**Measure space**^[측도 공간]는 triple $(X, \mathcal{F}, \mu)$:

1. $X$: Non-empty set (전체 공간)
2. $\mathcal{F}$: Sigma algebra^[시그마 대수] on $X$
3. $\mu$: Measure^[측도] on $(X, \mathcal{F})$

$(X, \mathcal{F})$를 **measurable space**^[가측 공간]라 하고, $\mathcal{F}$의 원소를 **measurable sets**^[가측 집합]이라 한다.

**상세한 내용**: [[Borel Sigma Algebra]] (Measurable space 정의)

## Measure^[측도]

함수 $\mu: \mathcal{F} \rightarrow [0, \infty]$가 **measure**^[측도]이다 $\Leftrightarrow$ 다음을 만족:

### 1. Non-negativity^[비음성]

$$\mu(A) \geq 0 \quad \forall A \in \mathcal{F}$$

### 2. Null empty set^[공집합의 영]

$$\mu(\emptyset) = 0$$

### 3. Countable additivity^[가산 가법성]

Disjoint sets^[서로소 집합] $A_1, A_2, \ldots \in \mathcal{F}$ (즉, $A_i \cap A_j = \emptyset$ for $i \neq j$)에 대해:

$$\mu\left(\displaystyle\bigcup_{n=1}^\infty A_n\right) = \displaystyle\sum_{n=1}^\infty \mu(A_n)$$

**주의**: 무한합이 정의되어야 함 (단조 수렴).

---

# <span class="header-properties">Properties</span>

## Basic properties^[기본 성질]

### 1. Monotonicity^[단조성]

$$A \subseteq B \Rightarrow \mu(A) \leq \mu(B)$$

**Proof**: $B = A \cup (B \setminus A)$ (disjoint union).

### 2. Finite additivity^[유한 가법성]

Disjoint $A_1, \ldots, A_n$에 대해:

$$\mu\left(\displaystyle\bigcup_{i=1}^n A_i\right) = \displaystyle\sum_{i=1}^n \mu(A_i)$$

### 3. Subadditivity^[부가법성]

임의의 $A_1, A_2, \ldots \in \mathcal{F}$ (disjoint 아니어도):

$$\mu\left(\displaystyle\bigcup_{n=1}^\infty A_n\right) \leq \displaystyle\sum_{n=1}^\infty \mu(A_n)$$

**Boole's inequality**^[부울 부등식]라고도 함.

### 4. Continuity from below^[아래로부터의 연속성]

$A_1 \subseteq A_2 \subseteq A_3 \subseteq \cdots$ (increasing sequence)이면:

$$\mu\left(\displaystyle\bigcup_{n=1}^\infty A_n\right) = \lim_{n \to \infty} \mu(A_n)$$

### 5. Continuity from above^[위로부터의 연속성]

$A_1 \supseteq A_2 \supseteq A_3 \supseteq \cdots$ (decreasing sequence)이고 $\mu(A_1) < \infty$이면:

$$\mu\left(\displaystyle\bigcap_{n=1}^\infty A_n\right) = \lim_{n \to \infty} \mu(A_n)$$

**주의**: $\mu(A_1) < \infty$ 조건 필요!

### 6. Complement rule^[여집합 규칙]

$\mu(X) < \infty$이면:

$$\mu(A^c) = \mu(X) - \mu(A)$$

---

# <span class="header-definition">Types of Measures</span>

## Finite measure^[유한 측도]

$\mu(X) < \infty$이면 **finite measure**.

**Example**: Probability measure^[확률 측도] ($\mu(X) = 1$).

## $\sigma$-finite measure^[시그마 유한 측도]

$X = \displaystyle\bigcup_{n=1}^\infty A_n$ where $\mu(A_n) < \infty$ for all $n$이면 **$\sigma$-finite**.

**Interpretation**: "Countably many finite pieces"로 분해 가능.

**Examples**:
- Lebesgue measure on $\mathbb{R}$: $\mathbb{R} = \bigcup_{n=1}^\infty [-n, n]$
- Counting measure on $\mathbb{N}$: $\mathbb{N} = \bigcup_{n=1}^\infty \{n\}$

## Complete measure^[완비 측도]

Measure space $(X, \mathcal{F}, \mu)$가 **complete**^[완비]이다 $\Leftrightarrow$:

$$\mu(A) = 0, B \subseteq A \Rightarrow B \in \mathcal{F} \text{ and } \mu(B) = 0$$

즉, measure zero sets^[측도 0 집합]의 모든 부분집합도 measurable.

**Example**: Lebesgue measure는 complete, Borel measure는 complete 아님.

### Completion^[완비화]

임의의 measure space는 completion을 가짐:

$$\mathcal{F}^\mu = \{A \cup N : A \in \mathcal{F}, N \subseteq B, \mu(B) = 0\}$$

---

# <span class="header-examples">Examples</span>

## 1. Counting measure^[계수 측도]

$X$ = 임의의 집합, $\mathcal{F} = \mathcal{P}(X)$ (power set).

$$\mu(A) = |A| = \begin{cases}
\text{number of elements in } A & \text{if } A \text{ finite} \\
\infty & \text{if } A \text{ infinite}
\end{cases}$$

**Properties**:
- Discrete한 상황 모델링
- $\sigma$-finite $\Leftrightarrow$ $X$ countable

## 2. Dirac measure^[디랙 측도]

$x_0 \in X$ 고정, **point mass**^[점 질량] at $x_0$:

$$\delta_{x_0}(A) = \begin{cases}
1 & \text{if } x_0 \in A \\
0 & \text{if } x_0 \notin A
\end{cases}$$

**Properties**:
- Probability measure (total mass = 1)
- Concentrated at single point

**Application**: Distribution of deterministic random variable.

## 3. Lebesgue measure^[르베스그 측도]

$(\mathbb{R}, \mathcal{B}(\mathbb{R}), \lambda)$ 또는 $(\mathbb{R}, \mathcal{L}, \lambda)$ (Lebesgue measurable sets).

**Definition**: 
$$\lambda([a, b]) = b - a$$

이를 모든 Borel (또는 Lebesgue) sets로 확장.

**Properties**:
- **Translation invariant**^[평행이동 불변]: $\lambda(A + x) = \lambda(A)$
- **Scaling**: $\lambda(cA) = |c| \lambda(A)$
- $\sigma$-finite: $\mathbb{R} = \bigcup_{n} [-n, n]$

**Higher dimensions**: $\lambda^n$ on $\mathbb{R}^n$ (volume^[부피]).

## 4. Probability measure^[확률 측도]

$(\Omega, \mathcal{F}, P)$ where $P(\Omega) = 1$.

**Kolmogorov axioms**^[콜모고로프 공리]:
1. $P(A) \geq 0$
2. $P(\Omega) = 1$
3. Countable additivity

**상세한 내용**: [[Sample Spaces]]

## 5. Discrete measures^[이산 측도]

$X = \{x_1, x_2, \ldots\}$ countable, weights $w_1, w_2, \ldots \geq 0$:

$$\mu(A) = \displaystyle\sum_{x_i \in A} w_i$$

**Example**: Probability mass function^[확률 질량 함수]
$$\mu(A) = \displaystyle\sum_{x_i \in A} p_i \quad \text{where } \displaystyle\sum_i p_i = 1$$

**상세한 내용**: [[Probability Mass Function]]

## 6. Continuous measures^[연속 측도]

Probability density function^[확률 밀도 함수] $f: \mathbb{R} \rightarrow [0, \infty)$에 대해:

$$\mu(A) = \int_A f(x) \, d\lambda(x)$$

여기서 $\lambda$는 Lebesgue measure.

**Example**: Normal distribution^[정규 분포]
$$f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$$

**상세한 내용**: [[Probability Density Function]]

## 7. Empirical measure^[경험 측도]

Data points $x_1, \ldots, x_n$:

$$\mu_n = \frac{1}{n} \displaystyle\sum_{i=1}^n \delta_{x_i}$$

**Application**: Statistics (sample distribution approximates population).

---

# <span class="header-definition">Measurable Functions</span>

## Definition^[정의]

$(X, \mathcal{F})$, $(Y, \mathcal{G})$ measurable spaces.

함수 $f: X \rightarrow Y$가 **measurable**^[가측]이다 $\Leftrightarrow$:

$$f^{-1}(B) \in \mathcal{F} \quad \forall B \in \mathcal{G}$$

즉, measurable sets의 preimage^[역상]가 measurable.

### For real-valued functions

$f: X \rightarrow \mathbb{R}$가 measurable $\Leftrightarrow$:

$$\{x : f(x) \leq a\} \in \mathcal{F} \quad \forall a \in \mathbb{R}$$

(다른 equivalent conditions도 많음)

## Properties^[성질]

### 1. Composition^[합성]

$f: X \rightarrow Y$ measurable, $g: Y \rightarrow Z$ measurable $\Rightarrow$ $g \circ f$ measurable.

### 2. Arithmetic operations^[산술 연산]

$f, g: X \rightarrow \mathbb{R}$ measurable $\Rightarrow$:
- $f + g$, $f - g$, $f \cdot g$ measurable
- $f / g$ measurable (where $g \neq 0$)
- $\max(f, g)$, $\min(f, g)$ measurable

### 3. Limits^[극한]

$f_n: X \rightarrow \mathbb{R}$ measurable이고 $f_n \to f$ pointwise^[점별] $\Rightarrow$ $f$ measurable.

### 4. Continuous functions^[연속 함수]

$f: \mathbb{R} \rightarrow \mathbb{R}$ continuous $\Rightarrow$ $f$ Borel measurable.

**Reason**: $f^{-1}(\text{open set})$ is open, thus Borel.

## Random variables^[확률 변수]

Probability space $(\Omega, \mathcal{F}, P)$에서:

**Random variable** = measurable function $X: \Omega \rightarrow \mathbb{R}$.

$$X^{-1}(B) \in \mathcal{F} \quad \forall B \in \mathcal{B}(\mathbb{R})$$

**상세한 내용**: [[Random Variables]]

---

# <span class="header-definition">Integration Theory</span>

## Lebesgue integral^[르베스그 적분]

Measure space $(X, \mathcal{F}, \mu)$와 measurable function $f: X \rightarrow [0, \infty]$에 대해:

$$\int_X f \, d\mu$$

### Construction steps^[구성 단계]

1. **Simple functions**^[단순 함수]: $\displaystyle\sum_{i=1}^n a_i \mathbb{1}_{A_i}$
   $$\int \displaystyle\sum_{i} a_i \mathbb{1}_{A_i} \, d\mu = \displaystyle\sum_{i} a_i \mu(A_i)$$

2. **Non-negative functions**: Supremum of simple functions
   $$\int f \, d\mu = \sup \left\{\int s \, d\mu : s \text{ simple}, s \leq f\right\}$$

3. **General functions**: $f = f^+ - f^-$
   $$\int f \, d\mu = \int f^+ \, d\mu - \int f^- \, d\mu$$

## Key theorems^[핵심 정리]

### Monotone Convergence Theorem (MCT)

$0 \leq f_1 \leq f_2 \leq \cdots$ and $f_n \to f$ pointwise:

$$\int f \, d\mu = \lim_{n \to \infty} \int f_n \, d\mu$$

### Dominated Convergence Theorem (DCT)

$f_n \to f$ pointwise, $|f_n| \leq g$ where $\int g \, d\mu < \infty$:

$$\int f \, d\mu = \lim_{n \to \infty} \int f_n \, d\mu$$

### Fatou's Lemma

$$\int \liminf_{n \to \infty} f_n \, d\mu \leq \liminf_{n \to \infty} \int f_n \, d\mu$$

## Expected value^[기댓값]

Probability space에서 random variable $X$:

$$E[X] = \int_\Omega X \, dP$$

**상세한 내용**: [[Expected Value]]

---

# <span class="header-properties">Relationship Between Measures</span>

## Absolutely continuous measures^[절대 연속 측도]

$\mu$가 $\nu$에 대해 **absolutely continuous**^[절대 연속]이다 ($\mu \ll \nu$) $\Leftrightarrow$:

$$\nu(A) = 0 \Rightarrow \mu(A) = 0$$

즉, $\nu$-null sets은 $\mu$-null sets.

### Radon-Nikodym theorem^[라돈-니코딤 정리]

$\mu \ll \nu$ and $\nu$ $\sigma$-finite $\Rightarrow$ $\exists$ measurable $f \geq 0$ s.t.:

$$\mu(A) = \int_A f \, d\nu$$

$f$를 **Radon-Nikodym derivative**^[라돈-니코딤 도함수]라 하고 $\frac{d\mu}{d\nu}$로 표기.

**Application**: Probability density functions!

$$dP_X = f_X \, d\lambda \quad \text{where } f_X = \frac{dP_X}{d\lambda}$$

## Singular measures^[특이 측도]

$\mu$와 $\nu$가 **mutually singular**^[상호 특이]이다 ($\mu \perp \nu$) $\Leftrightarrow$:

$$\exists A : \mu(A) = 0 \text{ and } \nu(A^c) = 0$$

**Example**: Dirac measure $\delta_0$ and Lebesgue measure $\lambda$ on $\mathbb{R}$.

## Lebesgue decomposition^[르베스그 분해]

$\mu$, $\nu$ $\sigma$-finite $\Rightarrow$:

$$\mu = \mu_{ac} + \mu_s$$

여기서:
- $\mu_{ac} \ll \nu$ (absolutely continuous part)
- $\mu_s \perp \nu$ (singular part)

Uniquely determined!

---

# <span class="header-remark">Applications</span>

## Probability theory^[확률론]

- Sample space $\Omega$
- Events $\mathcal{F}$ (sigma algebra)
- Probability $P$ (measure with $P(\Omega) = 1$)

**상세한 내용**: [[Probability]], [[Sample Spaces]]

## Integration theory^[적분 이론]

- Riemann integral → Lebesgue integral
- More general, more powerful
- Convergence theorems (MCT, DCT)

## Functional analysis^[함수해석학]

- $L^p$ spaces: $L^p(X, \mu) = \{f : \int |f|^p \, d\mu < \infty\}$
- Hilbert spaces: $L^2$ with inner product

**상세한 내용**: [[Hilbert Space]]

## Ergodic theory^[에르고딕 이론]

- Measure-preserving transformations^[측도 보존 변환]
- Invariant measures^[불변 측도]
- Birkhoff ergodic theorem

## Stochastic processes^[확률 과정]

- Filtrations^[여과]: Increasing sigma algebras
- Martingales^[마팅게일]
- Brownian motion^[브라운 운동]

## Analysis^[해석학]

- Differentiation and integration
- Fubini's theorem (product measures)
- Change of variables

---

# <span class="header-remark">Comparison with Riemann Integration</span>

| | **Riemann** | **Lebesgue** |
|---|---|---|
| **Domain** | Intervals in $\mathbb{R}$ | Measure spaces |
| **Partition** | Domain (x-axis) | Range (y-axis) |
| **Measurable** | Continuous functions (mainly) | Much broader class |
| **Convergence** | Requires uniform convergence | Pointwise + domination |
| **Power** | Elementary | General and powerful |
| **Example** | $\int_a^b f(x) dx$ | $\int_X f \, d\mu$ |

**Key advantage of Lebesgue**: Better convergence theorems (MCT, DCT).

---

# <span class="header-examples">핵심 개념 요약</span>

## Measure space의 구조

```
Set X
    ↓ define
Sigma algebra F
    ↓ define
Measure μ
    ↓ construct
Measurable functions
    ↓ integrate
Lebesgue integral
```

## 핵심 정의

| Concept | Definition |
|---------|------------|
| Measure space | $(X, \mathcal{F}, \mu)$ |
| Measure | $\mu: \mathcal{F} \rightarrow [0, \infty]$ |
| Countable additivity | $\mu(\bigcup A_n) = \sum \mu(A_n)$ |
| Measurable function | $f^{-1}(B) \in \mathcal{F}$ |
| Integral | $\int f \, d\mu$ |

## 중요한 측도들

| Measure | Space | Definition |
|---------|-------|------------|
| Counting | Discrete | $\mu(A) = \|A\|$ |
| Dirac | Any | $\delta_{x_0}(A) = \mathbb{1}_A(x_0)$ |
| Lebesgue | $\mathbb{R}^n$ | $\lambda([a,b]) = b-a$ |
| Probability | $\Omega$ | $P(\Omega) = 1$ |

---

**기초 개념**: [[Borel Sigma Algebra]]
**응용**: [[Sample Spaces]], [[Random Variables]], [[Expected Value]], [[Hilbert Space]]
**확률론**: [[Probability]], [[Probability Mass Function]], [[Probability Density Function]]

