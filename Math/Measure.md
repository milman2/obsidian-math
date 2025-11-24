# <span class="header-prerequisite">Prerequisite</span>
- [[Borel Sigma Algebra]]
- [[Measure Space]]

# <span class="header-reference">Reference</span>
- Rudin, Real and Complex Analysis
- Folland, Real Analysis
- Halmos, Measure Theory

---

# <span class="header-definition">Definition</span>

Measurable space^[가측 공간] $(X, \mathcal{F})$에 대해, 함수 $\mu: \mathcal{F} \to [0, \infty]$가 **measure^[측도]**이다 $\Leftrightarrow$ 다음 세 가지 조건을 만족:

## 1. Non-negativity^[비음성]

$$\mu(A) \geq 0 \quad \forall A \in \mathcal{F}$$

## 2. Null Empty Set^[공집합의 영]

$$\mu(\emptyset) = 0$$

## 3. Countable Additivity^[가산 가법성]

Disjoint sets^[서로소 집합] $A_1, A_2, A_3, \ldots \in \mathcal{F}$ (즉, $A_i \cap A_j = \emptyset$ for $i \neq j$)에 대해:

$$\mu\left(\bigcup_{n=1}^{\infty} A_n\right) = \sum_{n=1}^{\infty} \mu(A_n)$$

삼중쌍 $(X, \mathcal{F}, \mu)$를 **measure space^[측도 공간]**이라 한다.

---

# <span class="header-properties">Properties</span>

### Monotonicity^[단조성]

$$A \subseteq B \Rightarrow \mu(A) \leq \mu(B)$$

**증명**: $B = A \cup (B \setminus A)$ (disjoint union)이므로:
$$\mu(B) = \mu(A) + \mu(B \setminus A) \geq \mu(A)$$

### Finite Additivity^[유한 가법성]

Disjoint sets $A_1, \ldots, A_n$에 대해:

$$\mu\left(\bigcup_{i=1}^{n} A_i\right) = \sum_{i=1}^{n} \mu(A_i)$$

### Subadditivity^[부가법성]

임의의 $A_1, A_2, \ldots \in \mathcal{F}$ (disjoint 필요 없음):

$$\mu\left(\bigcup_{n=1}^{\infty} A_n\right) \leq \sum_{n=1}^{\infty} \mu(A_n)$$

이를 **Boole's inequality^[부울 부등식]**이라고도 한다.

### Continuity from Below^[아래로부터의 연속성]

$A_1 \subseteq A_2 \subseteq A_3 \subseteq \cdots$ (increasing sequence^[증가 수열])이면:

$$\mu\left(\bigcup_{n=1}^{\infty} A_n\right) = \lim_{n \to \infty} \mu(A_n)$$

**직관**: 집합이 커질수록 measure도 증가

### Continuity from Above^[위로부터의 연속성]

$A_1 \supseteq A_2 \supseteq A_3 \supseteq \cdots$ (decreasing sequence^[감소 수열])이고 **$\mu(A_1) < \infty$**이면:

$$\mu\left(\bigcap_{n=1}^{\infty} A_n\right) = \lim_{n \to \infty} \mu(A_n)$$

**주의**: $\mu(A_1) < \infty$ 조건이 필수!

**반례**: $A_n = [n, \infty) \subseteq \mathbb{R}$에 Lebesgue measure 적용 시:
- $\mu(A_n) = \infty$ for all $n$
- $\bigcap_{n=1}^{\infty} A_n = \emptyset$이므로 $\mu(\bigcap A_n) = 0 \neq \infty$

### Complement Rule^[여집합 규칙]

$\mu(X) < \infty$이면:

$$\mu(A^c) = \mu(X) - \mu(A)$$

---

# <span class="header-examples">Examples</span>

## 1. Counting Measure^[계수 측도]

집합 $X$와 $\mathcal{F} = 2^X$ (power set^[멱집합])에 대해:

$$\mu(A) = \begin{cases}
|A| & \text{if } A \text{ is finite} \\
\infty & \text{if } A \text{ is infinite}
\end{cases}$$

**직관**: 집합의 원소 개수를 세는 측도

**예시**:
- $\mu(\{1, 2, 3\}) = 3$
- $\mu(\mathbb{N}) = \infty$

## 2. Dirac Measure^[디랙 측도]

점 $x_0 \in X$에 대한 **point mass^[점 질량]**:

$$\delta_{x_0}(A) = \begin{cases}
1 & \text{if } x_0 \in A \\
0 & \text{if } x_0 \notin A
\end{cases}$$

**직관**: 한 점에 모든 질량이 집중

**응용**: 결정론적 확률 변수, impulse function

## 3. Lebesgue Measure^[르베스그 측도]

$\mathbb{R}^n$의 Borel sigma algebra $\mathcal{B}(\mathbb{R}^n)$에 대해:

$$\lambda^n([a_1, b_1] \times \cdots \times [a_n, b_n]) = \prod_{i=1}^{n} (b_i - a_i)$$

**1차원**: $\lambda([a, b]) = b - a$ (길이)
**2차원**: $\lambda^2(R) = \text{area}$ (넓이)
**3차원**: $\lambda^3(V) = \text{volume}$ (부피)

**주요 성질**:
- **Translation invariance^[평행이동 불변]**: $\lambda(A + x) = \lambda(A)$
- **Scaling**: $\lambda(cA) = |c|^n \lambda(A)$
- **Rotation invariance^[회전 불변]**: $\lambda(RA) = \lambda(A)$ for orthogonal $R$

## 4. Probability Measure^[확률 측도]

Sample space^[표본 공간] $\Omega$와 event sigma algebra^[사건 시그마 대수] $\mathcal{F}$에 대해:

$$P: \mathcal{F} \to [0, 1] \quad \text{with } P(\Omega) = 1$$

**Kolmogorov Axioms^[콜모고로프 공리]**:
1. $P(A) \geq 0$ for all $A \in \mathcal{F}$
2. $P(\Omega) = 1$
3. Countable additivity for disjoint events

자세한 내용은 [[Probability]], [[Sample Spaces]] 참조

## 5. Weighted Counting Measure^[가중 계수 측도]

Countable set $X = \{x_1, x_2, \ldots\}$와 weights $w_1, w_2, \ldots \geq 0$:

$$\mu(A) = \sum_{x_i \in A} w_i$$

**특수한 경우**:
- $w_i = 1$ for all $i$ → counting measure
- $w_i = p_i$ with $\sum p_i = 1$ → discrete probability measure

**응용**: [[Probability Mass Function]]

## 6. Absolutely Continuous Measure^[절대 연속 측도]

Base measure $\nu$와 non-negative measurable function $f$에 대해:

$$\mu(A) = \int_A f \, d\nu$$

**예시**: Probability density function^[확률 밀도 함수]
$$P(A) = \int_A f(x) \, dx \quad \text{where } \int_{\mathbb{R}} f(x) \, dx = 1$$

자세한 내용은 [[Probability Density Function]] 참조

---

# <span class="header-definition">Types of Measures</span>

## Finite Measure^[유한 측도]

$$\mu(X) < \infty$$

**예시**: Probability measures, Dirac measure, measure on bounded sets

## $\sigma$-Finite Measure^[시그마 유한 측도]

$X = \bigcup_{n=1}^{\infty} X_n$ where $\mu(X_n) < \infty$ for all $n$

**직관**: "Countably many finite pieces"로 분해 가능

**예시**:
- Lebesgue measure on $\mathbb{R}$: $\mathbb{R} = \bigcup_{n=1}^{\infty} [-n, n]$
- Counting measure on $\mathbb{N}$: $\mathbb{N} = \bigcup_{n=1}^{\infty} \{n\}$

**중요성**: 많은 정리들이 $\sigma$-finite measure에서만 성립 (Radon-Nikodym theorem 등)

## Complete Measure^[완비 측도]

Measure space $(X, \mathcal{F}, \mu)$가 **complete^[완비]** $\Leftrightarrow$:

$$\mu(A) = 0 \text{ and } B \subseteq A \Rightarrow B \in \mathcal{F}$$

즉, measure zero sets^[측도 0 집합]의 모든 부분집합도 measurable

**예시**:
- Lebesgue measure (completed) ✓ complete
- Borel measure ✗ not complete

### Completion^[완비화]

임의의 measure space는 completion을 가짐:

$$\overline{\mathcal{F}} = \{A \cup N : A \in \mathcal{F}, N \subseteq B \text{ for some } B \in \mathcal{F} \text{ with } \mu(B) = 0\}$$

$\mu$를 $\overline{\mathcal{F}}$로 확장하면 complete measure space를 얻음

## Signed Measure^[부호 측도]

$\mu: \mathcal{F} \to [-\infty, \infty]$ (양수와 음수 모두 가능)

단, $+\infty$와 $-\infty$를 동시에 가질 수 없음

**Hahn Decomposition^[한 분해]**: $X = P \cup N$ (disjoint)로 분해 가능:
- $\mu(A) \geq 0$ for all $A \subseteq P$
- $\mu(A) \leq 0$ for all $A \subseteq N$

## Complex Measure^[복소 측도]

$\mu: \mathcal{F} \to \mathbb{C}$

$$\mu = \mu_1 + i\mu_2$$

여기서 $\mu_1, \mu_2$는 signed measures

---

# <span class="header-theorem">Theorem</span>

### Carathéodory Extension Theorem^[카라테오도리 확장 정리]

Pre-measure^[전측도] $\mu_0$가 algebra^[대수] $\mathcal{A}$에 정의되어 있고 $\sigma$-finite이면, $\sigma(\mathcal{A})$로의 유일한 확장이 존재

**응용**: Lebesgue measure의 존재를 보이는 핵심 정리

### Radon-Nikodym Theorem^[라돈-니코딤 정리]

$\nu$가 $\sigma$-finite measure이고 $\mu \ll \nu$ (absolutely continuous^[절대 연속])이면, non-negative measurable function $f$가 존재하여:

$$\mu(A) = \int_A f \, d\nu \quad \forall A \in \mathcal{F}$$

$f$를 **Radon-Nikodym derivative^[라돈-니코딤 도함수]**라 하고 $\frac{d\mu}{d\nu}$로 표기

**응용**: Probability density functions의 이론적 근거

### Lebesgue Decomposition Theorem^[르베스그 분해 정리]

$\mu, \nu$가 $\sigma$-finite measures이면, unique decomposition:

$$\mu = \mu_{ac} + \mu_s$$

여기서:
- $\mu_{ac} \ll \nu$ (absolutely continuous part^[절대 연속 부분])
- $\mu_s \perp \nu$ (singular part^[특이 부분])

---

# <span class="header-remark">Remark</span>

### 직관적 이해

Measure는 집합의 **"크기"**를 일반화한 개념:

| 개념 | 측도 | 해석 |
|------|------|------|
| 길이 | Lebesgue measure (1D) | 구간의 길이 |
| 넓이 | Lebesgue measure (2D) | 영역의 넓이 |
| 부피 | Lebesgue measure (3D) | 입체의 부피 |
| 개수 | Counting measure | 원소 개수 |
| 확률 | Probability measure | 사건의 가능성 |
| 질량 | Physical measure | 물체의 질량 분포 |

### Countable Additivity의 중요성

**Finite additivity만으로는 부족**:
- Continuity properties 없음
- Convergence theorems 성립 안 함
- Integration theory 개발 불가

**Countable additivity**:
- Limit과 measure를 교환 가능
- [[Monotone Convergence Theorem]], [[Dominated Convergence Theorem]] 등 성립
- Modern analysis의 기초

### Measure vs Length/Area/Volume

**고전적 개념**:
- 길이, 넓이, 부피는 기하학적 직관
- 특정 "좋은" 집합에만 정의

**Measure theory**:
- 일반적이고 추상적
- 광범위한 집합에 정의 (measurable sets)
- 공리적 접근으로 엄밀한 이론 구축

### Non-measurable Sets^[비가측 집합]

Lebesgue measure에서 **모든** 부분집합이 measurable한 것은 아님!

**Vitali Set^[비탈리 집합]** (Axiom of Choice 필요):
- $A \subseteq [0, 1]$
- $A \notin \mathcal{L}$ (Lebesgue measurable이 아님)

Translation invariance와 countable additivity가 모순을 일으킴

### 응용 분야

**해석학^[Analysis]**:
- Lebesgue integration^[르베스그 적분]
- $L^p$ spaces
- [[Dominated Convergence Theorem]], [[Monotone Convergence Theorem]]

**확률론^[Probability Theory]**:
- Probability spaces
- Random variables
- [[Expected Value]], distributions

**함수해석학^[Functional Analysis]**:
- [[Hilbert Space]], $L^2$ spaces
- Spectral theory

**편미분방정식^[PDE]**:
- Weak solutions
- Sobolev spaces

**에르고딕 이론^[Ergodic Theory]**:
- Measure-preserving transformations^[측도 보존 변환]
- Invariant measures^[불변 측도]

### 역사적 배경

**19세기 후반**: 
- Riemann integration의 한계 인식
- Cantor set 등 병리적 집합 발견

**1902**: **Henri Lebesgue**
- Lebesgue measure와 Lebesgue integration 개발
- Dominated Convergence Theorem

**1933**: **Andrey Kolmogorov**
- Probability theory의 공리적 정립
- Measure theory를 probability의 기초로 사용

**현대**: Measure theory는 현대 해석학과 확률론의 필수 기초

### Measure Space와의 관계

**Measure Space** $(X, \mathcal{F}, \mu)$는 세 가지 구성 요소:
1. $X$: 전체 공간 (set)
2. $\mathcal{F}$: Measurable sets (sigma algebra)
3. $\mu$: Measure (function)

이 노트는 주로 **$\mu$ (measure)**에 집중
전체 구조는 [[Measure Space]] 참조

