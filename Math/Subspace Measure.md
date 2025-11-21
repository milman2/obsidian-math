# <span class="header-prerequisite">Prerequisite</span>
- [[Measure Space]]
- [[Borel Sigma Algebra]]
- Set theory (집합론)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Trace sigma algebra^[추적 시그마 대수]

$(X, \mathcal{F})$가 measurable space이고 $Y \subseteq X$일 때, $Y$에서의 **trace sigma algebra**^[추적 시그마 대수] (또는 **subspace sigma algebra**^[부분공간 시그마 대수], **induced sigma algebra**^[유도 시그마 대수]):

$$\mathcal{F}_Y = \{A \cap Y : A \in \mathcal{F}\} = \{B \subseteq Y : B = A \cap Y \text{ for some } A \in \mathcal{F}\}$$

**Notation**: $\mathcal{F}_Y = \mathcal{F} \cap Y$ 또는 $\mathcal{F}|_Y$로도 표기.

### Verification as sigma algebra

$\mathcal{F}_Y$는 $Y$에서의 sigma algebra임을 확인할 수 있다:

1. **$Y \in \mathcal{F}_Y$**: $Y = X \cap Y$이고 $X \in \mathcal{F}$
2. **Complement**: $B = A \cap Y \in \mathcal{F}_Y$이면
   $$B^c_Y = Y \setminus B = Y \cap A^c = A^c \cap Y \in \mathcal{F}_Y$$
   (여기서 complement는 $Y$ 안에서)
3. **Countable unions**: $B_n = A_n \cap Y \in \mathcal{F}_Y$이면
   $$\displaystyle\bigcup_{n=1}^\infty B_n = \left(\displaystyle\bigcup_{n=1}^\infty A_n\right) \cap Y \in \mathcal{F}_Y$$

따라서 $(Y, \mathcal{F}_Y)$는 measurable space^[가측 공간]이다.

## Restricted measure^[제한 측도]

$(X, \mathcal{F}, \mu)$가 measure space이고 $Y \in \mathcal{F}$일 때, **restricted measure**^[제한 측도] (또는 **subspace measure**^[부분공간 측도]):

$$\mu_Y: \mathcal{F}_Y \rightarrow [0, \infty]$$
$$\mu_Y(B) = \mu(B) \quad \forall B \in \mathcal{F}_Y$$

**주의**: $B \subseteq Y$이고 $B \in \mathcal{F}$이므로 $\mu(B)$가 정의됨.

### Alternative notation

$$\mu|_Y \text{ or } \mu \restriction_Y$$

### Verification as measure

$\mu_Y$가 measure임을 확인:

1. **Non-negativity**: $\mu_Y(B) = \mu(B) \geq 0$
2. **Null empty set**: $\mu_Y(\emptyset) = \mu(\emptyset) = 0$
3. **Countable additivity**: Disjoint $B_1, B_2, \ldots \in \mathcal{F}_Y$에 대해
   $$\mu_Y\left(\displaystyle\bigcup_{n} B_n\right) = \mu\left(\displaystyle\bigcup_{n} B_n\right) = \displaystyle\sum_{n} \mu(B_n) = \displaystyle\sum_{n} \mu_Y(B_n)$$

따라서 $(Y, \mathcal{F}_Y, \mu_Y)$는 measure space^[측도 공간]이다.

## Normalized subspace measure^[정규화된 부분공간 측도]

$\mu(Y) > 0$이고 finite이면, **normalized measure**^[정규화된 측도]:

$$\mu_Y^{\text{norm}}(B) = \frac{\mu(B)}{\mu(Y)} \quad \forall B \in \mathcal{F}_Y$$

**Property**: $\mu_Y^{\text{norm}}(Y) = 1$ (probability measure on $Y$).

**Application**: Conditional probability^[조건부 확률]!

$$P(A \mid Y) = \frac{P(A \cap Y)}{P(Y)} = P_Y^{\text{norm}}(A \cap Y)$$

**상세한 내용**: [[Conditional Probability]]

---

# <span class="header-properties">Properties</span>

## Basic properties^[기본 성질]

### 1. Measurable sets in subspace

$B \in \mathcal{F}_Y \Leftrightarrow B \subseteq Y$ and $\exists A \in \mathcal{F}$ s.t. $B = A \cap Y$.

**주의**: $B \subseteq Y$이지만 $B \notin \mathcal{F}$일 수 있음 (단, $B \in \mathcal{F}_Y$).

### 2. Measure agrees on subspace

$B \in \mathcal{F}_Y$에 대해:

$$\mu_Y(B) = \mu(B)$$

즉, subspace measure는 원래 measure를 "그대로 제한"한 것.

### 3. $\sigma$-finiteness preserved^[시그마 유한성 보존]

$\mu$가 $\sigma$-finite이면 $\mu_Y$도 $\sigma$-finite:

$$X = \displaystyle\bigcup_{n} X_n, \mu(X_n) < \infty \Rightarrow Y = \displaystyle\bigcup_{n} (Y \cap X_n), \mu_Y(Y \cap X_n) < \infty$$

### 4. Completeness not preserved^[완비성 비보존]

$\mu$가 complete^[완비]이어도 $\mu_Y$는 complete 아닐 수 있음.

**Example**: Lebesgue measure on $\mathbb{R}$는 complete이지만, Borel measure restricted to subspace는 complete 아님.

### 5. Monotonicity^[단조성]

$Y_1 \subseteq Y_2$이면:

$$\mathcal{F}_{Y_1} \subseteq \mathcal{F}_{Y_2}$$

(containment of sigma algebras)

---

# <span class="header-properties">Measurable Functions on Subspaces</span>

## Restriction of measurable function^[가측 함수의 제한]

$f: X \rightarrow \mathbb{R}$ measurable w.r.t. $(X, \mathcal{F})$이면:

$$f|_Y: Y \rightarrow \mathbb{R} \text{ is measurable w.r.t. } (Y, \mathcal{F}_Y)$$

**Proof**: $B \in \mathcal{B}(\mathbb{R})$에 대해
$$(f|_Y)^{-1}(B) = f^{-1}(B) \cap Y \in \mathcal{F}_Y$$

## Integration on subspaces^[부분공간에서의 적분]

$f: X \rightarrow [0, \infty]$ measurable이고 $Y \in \mathcal{F}$이면:

$$\int_Y f \, d\mu = \int_X f \cdot \mathbb{1}_Y \, d\mu$$

여기서 $\mathbb{1}_Y$는 indicator function^[지시 함수]:

$$\mathbb{1}_Y(x) = \begin{cases}
1 & x \in Y \\
0 & x \notin Y
\end{cases}$$

**Interpretation**: Subspace에서의 적분 = 전체 공간에서 indicator로 제한된 적분.

### For subspace measure

$$\int_Y f \, d\mu_Y = \int_Y f \, d\mu$$

(notation은 다르지만 값은 같음)

---

# <span class="header-examples">Examples</span>

## 1. Borel subspace of $\mathbb{R}$

$Y = [0, 1] \subseteq \mathbb{R}$, $\mathcal{F} = \mathcal{B}(\mathbb{R})$.

**Trace sigma algebra**:

$$\mathcal{F}_Y = \{B \cap [0, 1] : B \in \mathcal{B}(\mathbb{R})\}$$

**Fact**: $\mathcal{F}_Y = \mathcal{B}([0, 1])$ (Borel sets of $[0, 1]$ with subspace topology).

**Lebesgue measure restricted**:

$$\lambda_{[0,1]}(A) = \lambda(A) \quad \forall A \in \mathcal{B}([0, 1])$$

**Example**: $\lambda_{[0,1]}([0, 1/2]) = 1/2$.

## 2. Probability on a subset

$(\Omega, \mathcal{F}, P)$ probability space, $E \in \mathcal{F}$ with $P(E) > 0$.

**Conditional probability as normalized subspace measure**:

$$P_E^{\text{norm}}(A) = \frac{P(A \cap E)}{P(E)} = P(A \mid E)$$

**Interpretation**: Conditioning on $E$ = working on subspace $E$ with normalized measure.

**상세한 내용**: [[Conditional Probability]]

## 3. Discrete subspace

$X = \mathbb{N}$, $\mathcal{F} = \mathcal{P}(\mathbb{N})$, $\mu$ = counting measure.

$Y = \{2, 4, 6, 8, \ldots\}$ (even numbers).

**Trace sigma algebra**: $\mathcal{F}_Y = \mathcal{P}(Y)$ (모든 부분집합).

**Restricted counting measure**:

$$\mu_Y(A) = |A| \quad \forall A \subseteq Y$$

**Example**: $\mu_Y(\{2, 4, 6\}) = 3$.

## 4. Surface measure on sphere

$X = \mathbb{R}^3$, $\mu = \lambda^3$ (3D Lebesgue measure).

$Y = S^2 = \{x \in \mathbb{R}^3 : \|x\| = 1\}$ (unit sphere).

**Problem**: $\lambda^3(S^2) = 0$ (sphere has measure zero in $\mathbb{R}^3$).

**Solution**: Define **surface measure**^[표면 측도] $\sigma$ on $S^2$ separately (not by restriction).

$$\sigma(S^2) = 4\pi$$

**Remark**: This is NOT a subspace measure, but a different measure on $S^2$.

## 5. Conditional distribution^[조건부 분포]

Random variable $X \sim \text{Uniform}([0, 2])$.

**Conditioning on $X \in [0, 1]$**:

$$P(X \in [a, b] \mid X \in [0, 1]) = \frac{P(X \in [a, b] \cap [0, 1])}{P(X \in [0, 1])} = \frac{\lambda([a, b] \cap [0, 1])}{\lambda([0, 1])}$$

For $[a, b] \subseteq [0, 1]$:

$$P(X \in [a, b] \mid X \in [0, 1]) = \frac{b - a}{1} = b - a$$

즉, conditional distribution은 $\text{Uniform}([0, 1])$.

**상세한 내용**: [[Expected Value]] (Conditional expectation)

---

# <span class="header-properties">Relationship with Conditional Probability</span>

## Conditioning as subspace measure

Probability space $(\Omega, \mathcal{F}, P)$, event $E \in \mathcal{F}$ with $P(E) > 0$.

**Conditional probability**^[조건부 확률]:

$$P(A \mid E) = \frac{P(A \cap E)}{P(E)}$$

이는 **normalized subspace measure on $E$**:

$$(E, \mathcal{F}_E, P_E^{\text{norm}}) \text{ where } P_E^{\text{norm}}(A \cap E) = \frac{P(A \cap E)}{P(E)}$$

### Properties

1. $P(\cdot \mid E)$는 $E$에서의 probability measure (total measure = 1)
2. $P(E \mid E) = 1$
3. For $A_1, A_2, \ldots$ disjoint:
   $$P\left(\displaystyle\bigcup_{n} A_n \mid E\right) = \displaystyle\sum_{n} P(A_n \mid E)$$

## Conditional expectation^[조건부 기댓값]

Random variable $X: \Omega \rightarrow \mathbb{R}$, event $E$ with $P(E) > 0$.

$$E[X \mid E] = \int_E X \, dP_E^{\text{norm}} = \frac{1}{P(E)} \int_E X \, dP = \frac{\int_E X \, dP}{P(E)}$$

**Interpretation**: Expected value on subspace $E$ with normalized measure.

**상세한 내용**: [[Expected Value]]

---

# <span class="header-properties">Advanced Topics</span>

## Universal measurability^[보편 가측성]

$Y \subseteq X$가 **universally measurable**^[보편 가측]이다 $\Leftrightarrow$:

$$Y \in \mathcal{F}_\mu := \text{completion of } \mathcal{F} \text{ w.r.t. } \mu \quad \forall \text{ measures } \mu$$

## Induced measure on quotient spaces^[몫공간의 유도 측도]

$(X, \mathcal{F}, \mu)$ measure space, $\sim$ equivalence relation on $X$.

**Quotient space**: $X/\sim = \{[x] : x \in X\}$

**Quotient map**: $\pi: X \rightarrow X/\sim$, $\pi(x) = [x]$

**Quotient sigma algebra**:

$$\mathcal{F}_{X/\sim} = \{B \subseteq X/\sim : \pi^{-1}(B) \in \mathcal{F}\}$$

**Quotient measure** (if well-defined):

$$\mu_{X/\sim}(B) = \mu(\pi^{-1}(B))$$

**Condition for well-definedness**: Equivalence classes have uniform measure.

## Disintegration of measures^[측도의 분해]

Measure space $(X, \mathcal{F}, \mu)$, measurable partition $\{Y_\alpha\}_{\alpha \in A}$ of $X$.

**Goal**: Decompose $\mu$ into measures on each $Y_\alpha$.

$$\mu(B) = \int_A \mu_\alpha(B \cap Y_\alpha) \, d\nu(\alpha)$$

여기서 $\mu_\alpha$는 $Y_\alpha$에서의 conditional measure^[조건부 측도].

**Application**: Regular conditional probability^[정칙 조건부 확률].

---

# <span class="header-examples">Applications</span>

## 1. Conditional probability^[조건부 확률]

**Main application**: Conditioning on events.

$$P(A \mid E) = P_E^{\text{norm}}(A \cap E)$$

**상세한 내용**: [[Conditional Probability]]

## 2. Integration on subsets^[부분집합에서의 적분]

Computing integrals over measurable subsets:

$$\int_Y f \, d\mu = \int_X f \cdot \mathbb{1}_Y \, d\mu$$

**Example**: $\int_{[0,1]} x^2 \, d\lambda = \int_{\mathbb{R}} x^2 \cdot \mathbb{1}_{[0,1]} \, d\lambda = 1/3$

## 3. Restriction to lower-dimensional subspaces

$\mathbb{R}^n$에서 lower-dimensional subspace로의 제한.

**Example**: $\mathbb{R}^2 \to \mathbb{R}$ (projection onto line).

**주의**: Lebesgue measure on $\mathbb{R}^2$를 line으로 restrict하면 measure zero!

## 4. Probability distributions on subsets

Truncated distributions^[절단 분포], censored data^[검열 데이터].

**Example**: $X \sim N(0, 1)$ conditioned on $X > 0$ (truncated normal).

## 5. Bayesian inference^[베이지안 추론]

Posterior distribution^[사후 분포]는 conditioning on observed data:

$$P(\theta \in A \mid \text{data}) = P_{\text{data}}^{\text{norm}}(\theta \in A)$$

**상세한 내용**: [[Bayes' Rule]]

## 6. Markov chains^[마르코프 체인]

State space $S$, subset $A \subseteq S$.

**Hitting time**^[도달 시간]: First time entering $A$.

**Hitting probability**: Related to subspace measures.

---

# <span class="header-remark">Remark</span>

## Difference from induced topology^[유도 위상과의 차이]

### In topology:

$(X, \tau)$ topological space, $Y \subseteq X$.

**Subspace topology**^[부분공간 위상]:

$$\tau_Y = \{U \cap Y : U \in \tau\}$$

### In measure theory:

$(X, \mathcal{F})$ measurable space, $Y \subseteq X$.

**Trace sigma algebra**:

$$\mathcal{F}_Y = \{A \cap Y : A \in \mathcal{F}\}$$

**Similarity**: Both use intersection with subspace!

**Connection**: For topological space $(X, \tau)$:

$$\mathcal{B}(Y, \tau_Y) = \mathcal{B}(X, \tau)|_Y$$

즉, Borel sigma algebra of subspace topology = trace of Borel sigma algebra.

## When $Y \notin \mathcal{F}$

$Y \subseteq X$이지만 $Y \notin \mathcal{F}$인 경우:

**Problem**: $\mu_Y(B)$를 직접 정의할 수 없음 ($B \subseteq Y$이고 $B \notin \mathcal{F}$일 수 있음).

**Solution 1**: Use **outer measure**^[외측도]:

$$\mu^*(Y) = \inf\{\mu(A) : A \in \mathcal{F}, Y \subseteq A\}$$

**Solution 2**: Complete the sigma algebra to include $Y$.

## Completion of measure space^[측도 공간의 완비화]

$(X, \mathcal{F}, \mu)$ measure space.

**Completion**^[완비화]: Extend $\mathcal{F}$ to $\overline{\mathcal{F}}$:

$$\overline{\mathcal{F}} = \{A \cup N : A \in \mathcal{F}, N \subseteq B, \mu(B) = 0\}$$

Define $\overline{\mu}(A \cup N) = \mu(A)$.

Then $(X, \overline{\mathcal{F}}, \overline{\mu})$ is **complete**^[완비].

**상세한 내용**: [[Measure Space]] (Complete measure)

---

# <span class="header-examples">핵심 개념 요약</span>

## Subspace construction

```
Measure space (X, F, μ)
    ↓ choose subset Y ⊆ X
Trace sigma algebra F_Y = F ∩ Y
    ↓ restrict measure
Subspace measure (Y, F_Y, μ_Y)
    ↓ normalize (if μ(Y) finite)
Normalized measure (probability on Y)
```

## 핵심 정의

| Concept | Definition |
|---------|------------|
| Trace sigma algebra | $\mathcal{F}_Y = \{A \cap Y : A \in \mathcal{F}\}$ |
| Restricted measure | $\mu_Y(B) = \mu(B)$ for $B \in \mathcal{F}_Y$ |
| Normalized measure | $\mu_Y^{\text{norm}}(B) = \frac{\mu(B)}{\mu(Y)}$ |
| Conditional probability | $P(A \mid E) = \frac{P(A \cap E)}{P(E)}$ |

## Key properties^[핵심 성질]

| Property | Statement |
|----------|-----------|
| Measure preservation | $\mu_Y(B) = \mu(B)$ for $B \in \mathcal{F}_Y$ |
| $\sigma$-finiteness | Preserved under restriction |
| Completeness | NOT preserved |
| Measurability | $f$ measurable $\Rightarrow$ $f\|_Y$ measurable |

---

**기초 개념**: [[Measure Space]], [[Borel Sigma Algebra]]
**응용**: [[Conditional Probability]], [[Expected Value]], [[Bayes' Rule]]
**확률론**: [[Sample Spaces]], [[Probability]]

