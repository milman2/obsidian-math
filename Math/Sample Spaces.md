# <span class="header-prerequisite">Prerequisite</span>
- [[Borel Sigma Algebra]]
- Set theory (집합론 기초)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Sample space^[표본 공간]

**Sample space**^[표본 공간] (또는 outcome space) $\Omega$는 random experiment^[확률 실험]의 가능한 모든 결과들의 집합이다.

$\Omega$의 각 원소 $\omega \in \Omega$를 **outcome**^[결과] 또는 **sample point**^[표본점]이라 한다.

## Event^[사건]

**Event**^[사건]는 sample space의 부분집합이다. (a set of outcomes, not one outcome)

Formally, event는 sigma algebra^[시그마 대수] $\mathcal{F}$의 원소이다:
$$E \in \mathcal{F} \subseteq \mathcal{P}(\Omega)$$

### Event의 종류

- **Elementary event**^[근원사건]: 단일 outcome $\{\omega\}$
- **Certain event**^[확실한 사건]: $\Omega$ (항상 발생)
- **Impossible event**^[불가능 사건]: $\emptyset$ (절대 발생 안 함)
- **Compound event**^[복합사건]: 여러 outcomes의 합집합

## Probability space^[확률 공간]

**Probability space**^[확률 공간]는 triple $(\Omega, \mathcal{F}, P)$:

1. **Sample space** $\Omega$
2. **Event space** $\mathcal{F}$: Sigma algebra on $\Omega$
3. **Probability measure** $P: \mathcal{F} \rightarrow [0, 1]$

### Probability measure의 공리 (Kolmogorov axioms)

$P$는 다음을 만족:

1. **Non-negativity**^[비음성]: $P(E) \geq 0$ for all $E \in \mathcal{F}$
2. **Normalization**^[정규화]: $P(\Omega) = 1$
3. **Countable additivity**^[가산 가법성]: Disjoint events $E_1, E_2, \ldots$에 대해
   $$P\left(\displaystyle\bigcup_{n=1}^\infty E_n\right) = \displaystyle\sum_{n=1}^\infty P(E_n)$$

---

# <span class="header-properties">Properties</span>

## Basic properties of probability

1. **Empty set**: $P(\emptyset) = 0$

2. **Complement**^[여사건]: $P(E^c) = 1 - P(E)$

3. **Monotonicity**^[단조성]: $E \subseteq F \Rightarrow P(E) \leq P(F)$

4. **Union bound**^[합집합 한계] (Boole's inequality):
   $$P\left(\displaystyle\bigcup_{n=1}^\infty E_n\right) \leq \displaystyle\sum_{n=1}^\infty P(E_n)$$

5. **Inclusion-exclusion principle**^[포함-배제 원리]:
   $$P(E_1 \cup E_2) = P(E_1) + P(E_2) - P(E_1 \cap E_2)$$

## Discrete vs Continuous sample spaces

### Discrete^[이산]
$\Omega$가 countable^[가산]이면:
$$P(E) = \displaystyle\sum_{\omega \in E} P(\{\omega\})$$

특히 equally likely^[동등하게 가능한] outcomes일 때:
$$P(E) = \frac{|E|}{|\Omega|}$$

이 경우 확률 계산은 counting problem^[계수 문제]로 귀결됨.

**계수 기법**: [[Permutations and Combinations]]

### Continuous^[연속]
$\Omega \subseteq \mathbb{R}^n$이고 probability density function^[확률 밀도 함수] $f$가 있으면:
$$P(E) = \int_E f(x) \, dx$$

특히, single points: $P(\{\omega\}) = 0$ (almost always)

---

# <span class="header-examples">Examples</span>

## 1. Coin flip^[동전 던지기]

**Single flip**:
- $\Omega = \{H, T\}$ (Head, Tail)
- $\mathcal{F} = \mathcal{P}(\Omega) = \{\emptyset, \{H\}, \{T\}, \{H,T\}\}$
- Fair coin: $P(\{H\}) = P(\{T\}) = \frac{1}{2}$

**Two flips**:
- $\Omega = \{HH, HT, TH, TT\}$
- Event "at least one head": $E = \{HH, HT, TH\}$
- $P(E) = \frac{3}{4}$

## 2. Dice roll^[주사위 던지기]

**Single die**:
- $\Omega = \{1, 2, 3, 4, 5, 6\}$
- Event "even number": $E = \{2, 4, 6\}$
- Fair die: $P(E) = \frac{3}{6} = \frac{1}{2}$

**Two dice**:
- $\Omega = \{(i,j) : 1 \leq i,j \leq 6\}$, $|\Omega| = 36$
- Event "sum is 7": $E = \{(1,6), (2,5), (3,4), (4,3), (5,2), (6,1)\}$
- $P(E) = \frac{6}{36} = \frac{1}{6}$

## 3. Continuous uniform distribution^[연속 균등 분포]

$\Omega = [0, 1]$
- $\mathcal{F} = \mathcal{B}([0,1])$ ([[Borel Sigma Algebra]])
- $P([a,b]) = b - a$ for $0 \leq a \leq b \leq 1$
- Density: $f(x) = 1$ for $x \in [0,1]$

## 4. Normal distribution^[정규 분포]

$\Omega = \mathbb{R}$
- $\mathcal{F} = \mathcal{B}(\mathbb{R})$
- Density: $f(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{(x-\mu)^2}{2\sigma^2}}$
- $P(E) = \displaystyle\int_E f(x) \, dx$

## 5. Infinite coin flips^[무한 동전 던지기]

$\Omega = \{0, 1\}^\mathbb{N}$ (infinite sequences)
- Uncountable sample space!
- $\mathcal{F} = $ Cylinder sets의 sigma algebra
- Product measure

---

# <span class="header-remark">Remark</span>

## Conditional probability^[조건부 확률]

Event $B$가 주어졌을 때 event $A$의 조건부 확률:

$$P(A | B) = \frac{P(A \cap B)}{P(B)}, \quad P(B) > 0$$

### Bayes' theorem^[베이즈 정리]

$$P(A | B) = \frac{P(B | A) \cdot P(A)}{P(B)}$$

**더 자세한 내용**: [[Conditional Probability]] 참조

## Independence^[독립]

Events $A$, $B$가 **independent**^[독립]이다 $\Leftrightarrow$
$$P(A \cap B) = P(A) \cdot P(B)$$

이는 $P(A | B) = P(A)$ (if $P(B) > 0$)와 동치.

## Random variables^[확률 변수]

**Random variable**^[확률 변수] $X: \Omega \rightarrow \mathbb{R}$는 measurable function^[가측 함수]:

$$X^{-1}(B) \in \mathcal{F} \quad \forall B \in \mathcal{B}(\mathbb{R})$$

즉, $\{X \in B\} = \{\omega \in \Omega : X(\omega) \in B\}$는 event여야 한다.

### Distribution^[분포]

Random variable의 **distribution**^[분포]:
$$P_X(B) = P(\{\omega : X(\omega) \in B\}) = P(X^{-1}(B))$$

이는 $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$에서의 probability measure이다.

## Measure-theoretic view^[측도론적 관점]

Probability theory는 **measure theory with total measure 1**이다:

| Measure theory | Probability theory |
|----------------|-------------------|
| Measurable space $(X, \mathcal{F})$ | Sample space $(\Omega, \mathcal{F})$ |
| Measure $\mu$ | Probability measure $P$ |
| $\mu(X) < \infty$ | $P(\Omega) = 1$ |
| Measurable function | Random variable |
| Integration $\int f \, d\mu$ | Expectation $E[X] = \int X \, dP$ (see [[Expected Value]]) |

**상세한 내용**: [[Measure Space]]

## Finite vs Infinite sample spaces

### Finite $\Omega$
- $\mathcal{F} = \mathcal{P}(\Omega)$ (모든 부분집합이 event)
- Discrete probability
- Elementary combinatorics

### Countable $\Omega$
- Still discrete, but need series convergence
- $\displaystyle\sum_{\omega \in \Omega} P(\{\omega\}) = 1$

### Uncountable $\Omega$
- Need measure theory (Borel sets)
- $P(\{\omega\}) = 0$ for "most" $\omega$
- Density functions, distributions

## Law of large numbers^[큰 수의 법칙]

$X_1, X_2, \ldots$ i.i.d.^[독립 항등 분포] random variables, $E[X_i] = \mu$:

**Weak law**^[약한 법칙]:
$$\frac{1}{n}\displaystyle\sum_{i=1}^n X_i \xrightarrow{P} \mu$$

**Strong law**^[강한 법칙]:
$$\frac{1}{n}\displaystyle\sum_{i=1}^n X_i \xrightarrow{\text{a.s.}} \mu$$

## Central limit theorem^[중심극한정리]

$X_1, X_2, \ldots$ i.i.d., $E[X_i] = \mu$, $\text{Var}(X_i) = \sigma^2$:

$$\frac{\displaystyle\sum_{i=1}^n X_i - n\mu}{\sigma\sqrt{n}} \xrightarrow{d} N(0, 1)$$

---

# <span class="header-examples">확률 공간의 구조</span>

```
Sample space Ω (모든 가능한 결과)
    ↓
Event space F (측정 가능한 사건들)
    ↓
Probability measure P (확률 할당)
    ↓
Random variables X (실수값 함수)
    ↓
Distribution P_X (유도된 확률 측도)
```

## 계층 관계

```
Concrete experiment (구체적 실험)
    ↓ model
Sample space (추상적 모델)
    ↓ events
Sigma algebra (사건 공간)
    ↓ probability
Probability measure (확률)
    ↓ compute
Statistics, inference (통계, 추론)
```

## 핵심 아이디어

**"확률론은 측도 1인 측도론"**

- **Set theory**: 집합과 원소
- **Measure theory**: 크기 측정
- **Probability**: 불확실성 정량화
- **Statistics**: 데이터로부터 추론

---

**확률론 개관**: [[Probability]]
**기초 개념**: [[Borel Sigma Algebra]], [[Measure Space]], [[Subspace Measure]]
**관련 개념**: [[Random Variables]], [[Joint Probabilities]], [[Marginal Probabilities]], [[Conditional Probability]]
