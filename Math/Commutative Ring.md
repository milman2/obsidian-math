# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]

# <span class="header-reference">Reference</span>
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Eisenbud, Commutative Algebra with a View Toward Algebraic Geometry
- Matsumura, Commutative Ring Theory
- Zariski & Samuel, Commutative Algebra

---

# <span class="header-definition">Definition</span>

## Commutative Ring^[가환환]

Ring $R$이 **commutative^[가환]**이다 $\Leftrightarrow$

$$\forall a, b \in R: \quad ab = ba$$

**의미**: 곱셈의 순서가 중요하지 않음

**표준 가정**: 특별한 언급이 없으면 commutative ring은 **multiplicative identity^[곱셈 항등원]** $1$을 가진다고 가정

## Commutative Ring with Unity

**정의**: Commutative ring $R$ with unity^[단위원을 가진 가환환]

$$\exists 1 \in R: \quad \forall a \in R, \quad 1 \cdot a = a \cdot 1 = a$$

**추가 조건**: $1 \neq 0$ (nontrivial ring)

**본 문서**: 달리 명시하지 않으면 commutative ring = commutative ring with unity

## Notation

**Standard notation for operations**:
- Addition: $+$ (항상 가환)
- Multiplication: $\cdot$ or juxtaposition (가환!)
- Additive identity: $0$
- Multiplicative identity: $1$

**중요**: $ab = ba$ 항상 성립!

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Simplification of Ideal Theory

**정리**: Commutative ring에서

$$\text{left ideal} = \text{right ideal} = \text{two-sided ideal}$$

**증명**: $ra \in I$이면 $ar = ra \in I$ (commutativity) 
**의미**: "Ideal"만 고려하면 충분 (left/right 구분 불필요)

자세한 내용은 [[Ideal]] 참조

### 2. Principal Ideals

Commutative ring $R$에서 원소 $a$에 의한 **principal ideal^[주 아이디얼]**:

$$\langle a \rangle = aR = Ra = \{ra : r \in R\}$$

**특징**: Left/right 구분 없음

**예**: $n\mathbb{Z} = \langle n \rangle$ in $\mathbb{Z}$

### 3. Polynomial Rings

**정리**: $R$이 commutative이면 $R[x_1, \ldots, x_n]$도 commutative

$$f(x) \cdot g(x) = g(x) \cdot f(x)$$

자세한 내용은 [[Polynomial Ring]] 참조

### 4. Localization

**정리**: Commutative ring $R$과 multiplicative set $S$에 대해 **localization^[국소화]** $S^{-1}R$ 정의 가능

$$S^{-1}R = \left\{ \frac{r}{s} : r \in R, s \in S \right\}$$

**의미**: $S$의 원소들을 "가역"으로 만듦

**비가환환에서**: Localization이 일반적으로 불가능!

자세한 내용은 [[Localization]] 참조

### 5. Spectrum

Commutative ring $R$의 **spectrum^[스펙트럼]**:

$$\text{Spec}(R) = \{\text{prime ideals of } R\}$$

**Zariski topology**: Prime ideals에 위상 구조 부여

**응용**: Algebraic geometry의 핵심 개념

자세한 내용은 [[Spectrum]], [[Algebraic Geometry]] 참조

### 6. Chinese Remainder Theorem

**정리**: $I_1, \ldots, I_n$ pairwise coprime ideals이면

$$R / (I_1 \cap \cdots \cap I_n) \cong R/I_1 \times \cdots \times R/I_n$$

**Coprime**: $I_i + I_j = R$ for $i \neq j$

**응용**: Number theory, coding theory

자세한 내용은 [[Chinese Remainder Theorem]] 참조

## Ideal Properties

### Sum and Product

**Sum**: $I + J = \{a + b : a \in I, b \in J\}$

**Product**: $IJ = \left\{ \displaystyle\sum_{k} a_k b_k : a_k \in I, b_k \in J \right\}$

**성질**:
- $IJ = JI$ (commutativity!)
- $IJ \subseteq I \cap J$
- If coprime: $IJ = I \cap J$

### Ideal Operations Commute

**정리**: Commutative ring에서 ideal operations는 교환 가능

$$I + J = J + I$$

$$IJ = JI$$

$$I \cap J = J \cap I$$

## Units and Zero Divisors

### Units^[단원]

$$U(R) = \{u \in R : \exists v \in R, uv = 1\}$$

**Group structure**: $(U(R), \cdot)$는 **abelian group^[아벨군]**

**증명**: $uv = vu = 1$ (commutativity) 
자세한 내용은 [[Units]] 참조

### Zero Divisors^[영인자]

$$\text{ZD}(R) = \{a \in R \setminus \{0\} : \exists b \neq 0, ab = 0\}$$

**Commutative**: $ab = 0$ $\Leftrightarrow$ $ba = 0$

**의미**: 0이 아닌데 곱하면 0이 되는 원소

### Nilpotent Elements^[멱영원]

$$\text{Nil}(R) = \{a \in R : \exists n \geq 1, a^n = 0\}$$

**성질**: $\text{Nil}(R)$는 ideal (commutativity 필요!)

자세한 내용은 [[Nilradical]] 참조

## Special Types of Commutative Rings

### Integral Domain^[정역]

**정의**: Commutative ring with no zero divisors

$$ab = 0 \quad \Rightarrow \quad a = 0 \text{ or } b = 0$$

**예**: $\mathbb{Z}$, $\mathbb{Z}[i]$, $\mathbb{Q}$, $k[x]$

자세한 내용은 [[Integral Domain]] 참조

### Field^[체]

**정의**: Commutative ring where every nonzero element is a unit

$$\forall a \neq 0: \quad \exists a^{-1} \in R, \quad aa^{-1} = 1$$

**예**: $\mathbb{Q}$, $\mathbb{R}$, $\mathbb{C}$, $\mathbb{Z}/p\mathbb{Z}$ ($p$ prime)

자세한 내용은 [[Field]] 참조

### UFD (Unique Factorization Domain)^[유일 인수분해 정역]

**정의**: Integral domain where every element factors uniquely into irreducibles

**예**: $\mathbb{Z}$, $k[x]$, $\mathbb{Z}[i]$

자세한 내용은 [[Unique Factorization Domain]] 참조

### PID (Principal Ideal Domain)^[주 아이디얼 정역]

**정의**: Integral domain where every ideal is principal

$$\forall I \triangleleft R: \quad \exists a \in R, \quad I = \langle a \rangle$$

**예**: $\mathbb{Z}$, $k[x]$ (field $k$)

**정리**: PID $\Rightarrow$ UFD

자세한 내용은 [[Principal Ideal Domain]] 참조

### Euclidean Domain^[유클리드 정역]

**정의**: Integral domain with Euclidean algorithm

**예**: $\mathbb{Z}$, $k[x]$, $\mathbb{Z}[i]$ (Gaussian integers)

**정리**: Euclidean domain $\Rightarrow$ PID $\Rightarrow$ UFD

자세한 내용은 [[Euclidean Domain]] 참조

### Noetherian Ring^[뇌터 환]

**정의**: Ring satisfying **ascending chain condition^[상승 사슬 조건]** on ideals

$$I_1 \subseteq I_2 \subseteq I_3 \subseteq \cdots \quad \Rightarrow \quad \exists n: I_n = I_{n+1} = \cdots$$

**동치 조건**: 모든 ideal이 finitely generated

**예**: $\mathbb{Z}$, $k[x_1, \ldots, x_n]$

**Hilbert Basis Theorem**: $R$ Noetherian $\Rightarrow$ $R[x]$ Noetherian

자세한 내용은 [[Noetherian Ring]] 참조

### Artinian Ring^[아르틴 환]

**정의**: Ring satisfying **descending chain condition^[하강 사슬 조건]** on ideals

$$I_1 \supseteq I_2 \supseteq I_3 \supseteq \cdots \quad \Rightarrow \quad \exists n: I_n = I_{n+1} = \cdots$$

**예**: Finite rings, $\mathbb{Z}/n\mathbb{Z}$

**정리**: Artinian ring은 Noetherian

자세한 내용은 [[Artinian Ring]] 참조

### Dedekind Domain^[데데킨트 정역]

**정의**: Noetherian integral domain of dimension 1 where every nonzero prime ideal is maximal

**특징**: 모든 ideal이 uniquely factor into prime ideals

**예**: $\mathbb{Z}$, ring of integers in number field

**응용**: Algebraic number theory

자세한 내용은 [[Dedekind Domain]] 참조

### Local Ring^[국소환]

**정의**: Commutative ring with unique maximal ideal

$$\exists ! M \triangleleft R \text{ maximal}$$

**동치 조건**: Non-units form an ideal

**예**: 
- $\mathbb{Z}_{(p)} = \left\{ \frac{a}{b} : p \nmid b \right\}$
- $k[[x]]$ (formal power series)
- Localization at prime ideal

자세한 내용은 [[Local Ring]] 참조

### Regular Ring^[정칙환]

**정의**: Noetherian ring where all localizations are regular local rings

**의미**: "Geometrically smooth"

**예**: Polynomial rings over fields

**응용**: Algebraic geometry (smooth varieties)

자세한 내용은 [[Regular Ring]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$ (Integers)

**Properties**:
- Commutative - Integral domain - PID - UFD - Euclidean domain - Noetherian - Dedekind domain 
**Units**: $U(\mathbb{Z}) = \{1, -1\}$

**Prime elements**: $\pm p$ (ordinary primes)

## Example 2: $\mathbb{Q}$, $\mathbb{R}$, $\mathbb{C}$ (Fields)

**Properties**:
- Commutative - Field - Every nonzero element is unit

**Ideals**: Only $\{0\}$ and $R$ (trivial)

## Example 3: $\mathbb{Z}/n\mathbb{Z}$

**Properties**:
- Commutative - Finite ring
- Artinian - Noetherian 
**Field?**: $\mathbb{Z}/n\mathbb{Z}$ is field $\Leftrightarrow$ $n$ is prime

**Units**: $U(\mathbb{Z}/n\mathbb{Z}) = \{k : \gcd(k, n) = 1\}$

**Size**: $|U(\mathbb{Z}/n\mathbb{Z})| = \phi(n)$ (Euler's totient)

## Example 4: Polynomial Ring $k[x]$

**Properties** (for field $k$):
- Commutative - Integral domain - PID - UFD - Euclidean domain - Noetherian 
**Units**: $U(k[x]) = k^* = k \setminus \{0\}$ (constant polynomials)

**Irreducibles**: Irreducible polynomials

## Example 5: Multivariable Polynomial Ring $k[x, y]$

**Properties**:
- Commutative - Integral domain - UFD - Noetherian 
**NOT PID**: $\langle x, y \rangle$ is not principal

**Ideals**: Correspond to algebraic varieties

## Example 6: Gaussian Integers $\mathbb{Z}[i]$

$$\mathbb{Z}[i] = \{a + bi : a, b \in \mathbb{Z}\}$$

**Properties**:
- Commutative - Integral domain - UFD - PID - Euclidean domain 
**Norm**: $N(a + bi) = a^2 + b^2$

**Units**: $U(\mathbb{Z}[i]) = \{1, -1, i, -i\}$

자세한 내용은 [[Gaussian Integers]] 참조

## Example 7: $\mathbb{Z}[\sqrt{-5}]$

$$\mathbb{Z}[\sqrt{-5}] = \{a + b\sqrt{-5} : a, b \in \mathbb{Z}\}$$

**Properties**:
- Commutative - Integral domain - **NOT UFD** ✗

**Failure of unique factorization**:

$$6 = 2 \cdot 3 = (1 + \sqrt{-5})(1 - \sqrt{-5})$$

(두 가지 본질적으로 다른 인수분해!)

## Example 8: $\mathbb{Z}_{(p)}$ (Localization)

$$\mathbb{Z}_{(p)} = \left\{ \frac{a}{b} : a, b \in \mathbb{Z}, p \nmid b \right\}$$

**Properties**:
- Commutative - Local ring  (unique maximal ideal $p\mathbb{Z}_{(p)}$)
- Noetherian 
**Units**: $\frac{a}{b}$ where $p \nmid a$

## Example 9: Formal Power Series $k[[x]]$

$$k[[x]] = \left\{ \displaystyle\sum_{i=0}^{\infty} a_i x^i : a_i \in k \right\}$$

**Properties**:
- Commutative - Local ring  (maximal ideal $\langle x \rangle$)
- Integral domain  (if $k$ is)
- Noetherian 
**Units**: $f \in U(k[[x]])$ $\Leftrightarrow$ $a_0 \neq 0$

자세한 내용은 [[Formal Power Series]] 참조

## Example 10: Continuous Functions $C(X)$

**$X$ compact Hausdorff space**

$$C(X) = \{f : X \to \mathbb{R} \text{ continuous}\}$$

**Operations**: Pointwise addition and multiplication

**Properties**:
- Commutative - Unity: constant function $1$

**Ideals**: 
- Maximal ideals $\leftrightarrow$ points of $X$
- $M_x = \{f : f(x) = 0\}$

**Gelfand-Naimark Theorem**: Correspondence between spaces and rings

## Example 11: $\mathbb{Z} \times \mathbb{Z}$ (Direct Product)

**Properties**:
- Commutative - **Has zero divisors**: $(1, 0) \cdot (0, 1) = (0, 0)$
- NOT integral domain ✗

**Units**: $U(\mathbb{Z} \times \mathbb{Z}) = \{1, -1\} \times \{1, -1\}$

**Ideals**: $I \times J$ where $I \triangleleft \mathbb{Z}$, $J \triangleleft \mathbb{Z}$

## Example 12: $\mathbb{Z}/6\mathbb{Z}$

**Properties**:
- Commutative - **Has zero divisors**: $\overline{2} \cdot \overline{3} = \overline{0}$
- NOT integral domain ✗

**Units**: $U(\mathbb{Z}/6\mathbb{Z}) = \{\overline{1}, \overline{5}\}$

**Zero divisors**: $\{\overline{2}, \overline{3}, \overline{4}\}$

**Decomposition**: $\mathbb{Z}/6\mathbb{Z} \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$

자세한 내용은 [[Chinese Remainder Theorem]] 참조

## Example 13: Coordinate Ring

**Variety**: $V = \{(x, y) : y = x^2\}$ in $\mathbb{C}^2$

**Coordinate ring**:

$$\mathbb{C}[V] = \mathbb{C}[x, y] / \langle y - x^2 \rangle \cong \mathbb{C}[t]$$

**Interpretation**: Functions on variety

자세한 내용은 [[Algebraic Geometry]] 참조

---

# <span class="header-theorem">Theorem</span>

## Hierarchy Theorem

**정리**: Commutative rings의 포함 관계

$$\text{Field} \subsetneq \text{Euclidean Domain} \subsetneq \text{PID} \subsetneq \text{UFD} \subsetneq \text{Integral Domain}$$

**모두**: Commutative rings with unity

**역 포함 거짓**: 각 단계마다 counterexample 존재

## Krull's Principal Ideal Theorem

**정리**: $R$ Noetherian ring, $x \in R$ non-unit이면

$$\text{ht}(P) \leq 1$$

for every minimal prime $P$ containing $x$

**의미**: Principal ideal의 height 제한

자세한 내용은 [[Krull Dimension]] 참조

## Nullstellensatz (Hilbert)

**정리**: $k$ algebraically closed field, $I \triangleleft k[x_1, \ldots, x_n]$이면

$$\sqrt{I} = I(V(I))$$

**의미**: Ideals $\leftrightarrow$ Varieties correspondence

**응용**: Algebraic geometry의 기초

자세한 내용은 [[Nullstellensatz]] 참조

## Going-Up Theorem

**정리**: $R \subseteq S$ integral extension이고 $P_1 \subseteq P_2$ prime ideals in $R$이면

$$\exists Q_1 \subseteq Q_2 \text{ primes in } S: \quad Q_i \cap R = P_i$$

**응용**: Dimension theory

자세한 내용은 [[Integral Extension]] 참조

## Going-Down Theorem

**정리**: $R \subseteq S$ flat extension이고 $P_1 \supseteq P_2$ primes in $R$이면

$$\exists Q_1 \supseteq Q_2 \text{ primes in } S: \quad Q_i \cap R = P_i$$

**조건**: Flatness 필요

## Structure Theorem for Artinian Rings

**정리**: $R$ Artinian ring이면

$$R \cong R_1 \times \cdots \times R_n$$

where each $R_i$ is Artinian local ring

**의미**: Artinian rings는 local rings의 직곱으로 분해

## Wedderburn's Theorem

**정리**: Finite division ring is commutative (hence a field)

**의미**: 유한 나눗셈환은 자동으로 가환!

**응용**: Finite fields theory

## Nakayama's Lemma

**정리**: $M$ finitely generated $R$-module, $I \subseteq J(R)$이면

$$IM = M \quad \Rightarrow \quad M = 0$$

**응용**: Module theory, local rings

자세한 내용은 [[Nakayama's Lemma]] 참조

## Krull's Intersection Theorem

**정리**: $(R, \mathfrak{m})$ Noetherian local ring이면

$$\bigcap_{n=1}^{\infty} \mathfrak{m}^n = \{0\}$$

**의미**: Powers of maximal ideal의 교집합은 0

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Commutative Ring = "교환법칙이 성립하는 환"**

### 메타포: 물건 쌓기

**Commutative**: 
- $a \times b = b \times a$
- 블록 $a$와 블록 $b$를 쌓는 순서 무관
- 결과는 동일

**Non-commutative**:
- $a \times b \neq b \times a$
- Matrix multiplication처럼 순서 중요
- 결과가 다를 수 있음

### 왜 Commutativity가 중요한가?

**1. Ideal Theory 단순화**:
- Left ideal = Right ideal = Two-sided ideal
- 이론이 훨씬 간결

**2. Localization 가능**:
- "분수" $\frac{r}{s}$ 정의 가능
- Local properties 연구 가능

**3. Geometric Interpretation**:
- Spectrum $\text{Spec}(R)$ 정의
- Algebraic geometry 연결

**4. 계산 편의성**:
- 많은 알고리즘이 commutativity 가정
- Gröbner basis, etc.

## Commutative vs Non-commutative

| 측면 | Commutative | Non-commutative |
|------|-------------|-----------------|
| **곱셈** | $ab = ba$ | $ab \neq ba$ 가능 |
| **Ideal** | One type | Left/right/two-sided |
| **예** | $\mathbb{Z}$, $k[x]$ | $M_n(k)$, group algebras |
| **기하** | Algebraic geometry | Noncommutative geometry |
| **응용** | Number theory | Quantum mechanics |

## 응용 분야

### 1. Algebraic Geometry

**핵심**: Commutative rings $\leftrightarrow$ Geometric objects

**Correspondence**:
- Ring: Coordinate ring of variety
- Ideal: Vanishing conditions
- Prime ideal: Irreducible subvariety
- Maximal ideal: Point

**Foundation**: Grothendieck's scheme theory

### 2. Algebraic Number Theory

**Ring of integers**: $\mathcal{O}_K$ in number field $K$

**Properties**:
- Commutative - Dedekind domain
- Ideal factorization

**응용**:
- Fermat's Last Theorem
- Class field theory

### 3. Coding Theory

**Cyclic codes**: Ideals in $\mathbb{F}_q[x] / \langle x^n - 1 \rangle$

**Reed-Solomon codes**: Evaluation codes

**응용**: Error correction

### 4. Cryptography

**RSA**: Properties of $\mathbb{Z}/n\mathbb{Z}$

**Elliptic curves**: Points form abelian group

**Lattice cryptography**: Ideal lattices in number fields

### 5. Computer Algebra

**Gröbner bases**: Algorithm for ideal membership

**Polynomial system solving**: Elimination theory

**Software**: Mathematica, Sage, Macaulay2

## 역사적 배경

**19세기**:
- **Gauss**: $\mathbb{Z}[i]$ (Gaussian integers)
- **Kummer**: Ideal numbers
- **Dedekind**: Modern ideal theory

**20세기 초**:
- **Hilbert**: Basis theorem, Nullstellensatz
- **Noether**: Ascending chain condition
- **Krull**: Dimension theory

**20세기 중반**:
- **Zariski**: Algebraic geometry
- **Grothendieck**: Scheme theory
- **Atiyah-Macdonald**: Standard textbook

**현대**:
- Computational commutative algebra
- Derived categories
- Noncommutative geometry (contrast!)

## Commutative Algebra의 핵심 주제

### 기초
- Ideals and operations
- Quotient rings
- Prime and maximal ideals
- Localization

### 중급
- Noetherian rings
- Primary decomposition
- Integral extensions
- Dimension theory

### 고급
- Homological algebra
- Depth and Cohen-Macaulay rings
- Regular rings
- Gorenstein rings
- Scheme theory

## 표기법

| 표기 | 의미 |
|------|------|
| $R$ | Commutative ring (보통 unity 가정) |
| $R^*$ or $R \setminus \{0\}$ | Nonzero elements |
| $U(R)$ | Units (group) |
| $\text{Spec}(R)$ | Spectrum (prime ideals) |
| $\text{MaxSpec}(R)$ | Maximal spectrum |
| $R_{(p)}$ | Localization at prime $p$ |
| $R[x]$ | Polynomial ring |
| $R[[x]]$ | Power series ring |

## Common Pitfall^[흔한 실수]

### 1. Commutativity는 곱셈에만!

덧셈은 **모든** ring에서 가환:

$$a + b = b + a$$ (always!)

Commutative ring: **곱셈**도 가환

$$ab = ba$$

### 2. Field $\neq$ Commutative Ring

모든 field는 commutative

하지만: 모든 commutative ring이 field는 아님

예: $\mathbb{Z}$ (commutative, not field)

### 3. Integral Domain 판별

**$\mathbb{Z}/n\mathbb{Z}$가 integral domain인가?**

답: $n$ prime일 때만! (그때 field)

$n$ composite이면 zero divisors 존재

### 4. PID vs UFD

**PID $\Rightarrow$ UFD** 
**UFD $\not\Rightarrow$ PID** ✗

예: $k[x, y]$ is UFD but not PID

### 5. Noetherian $\neq$ Artinian

**일반적으로**: 독립적 개념

**예외**: Artinian $\Rightarrow$ Noetherian

하지만: Noetherian $\not\Rightarrow$ Artinian

예: $\mathbb{Z}$ is Noetherian but not Artinian

### 6. Localization 표기

**$S^{-1}R$**: General localization

**$R_p$**: Localization at prime $p$ (maximal ideal $pR_p$)

**$R_{(p)}$**: 때때로 이 표기 사용 (혼동 주의)

## 학습 로드맵

**Step 1: 기초** (학부 수준)
- Ring, ideal, quotient
- Prime, maximal ideals
- PID, UFD
- Polynomial rings

**Step 2: 중급** (대학원 초급)
- Noetherian rings
- Localization
- Integral extensions
- Hilbert Basis Theorem

**Step 3: 고급** (대학원 중급)
- Primary decomposition
- Dimension theory
- Dedekind domains
- Homological methods

**Step 4: 전문** (연구 수준)
- Cohen-Macaulay rings
- Regular rings
- Scheme theory
- Derived categories

## 추천 교재

**입문**:
- Atiyah & Macdonald, *Introduction to Commutative Algebra*
- Reid, *Undergraduate Commutative Algebra*

**중급**:
- Eisenbud, *Commutative Algebra with a View Toward Algebraic Geometry*
- Matsumura, *Commutative Ring Theory*

**고급**:
- Zariski & Samuel, *Commutative Algebra* (2 volumes)
- Bruns & Herzog, *Cohen-Macaulay Rings*

**기하 관점**:
- Hartshorne, *Algebraic Geometry*
- Mumford, *Red Book of Varieties and Schemes*

## 관련 개념

- [[Ring]]: General concept
- [[Ideal]]: Ideals in commutative rings
- [[Quotient Ring]]: Construction
- [[Localization]]: Making elements invertible
- [[Integral Domain]]: No zero divisors
- [[Principal Ideal Domain]]: All ideals principal
- [[Unique Factorization Domain]]: Unique factorization
- [[Noetherian Ring]]: Chain condition
- [[Field]]: All nonzero elements units
- [[Spectrum]]: Geometric interpretation
- [[Algebraic Geometry]]: Main application

## 추가 학습 주제

**기초**:
- Definition and examples
- Ideal operations
- Prime and maximal ideals
- Quotient rings

**중급**:
- Localization
- Chinese Remainder Theorem
- Nakayama's Lemma
- Hilbert Basis Theorem
- Primary decomposition

**고급**:
- Krull dimension
- Cohen-Macaulay rings
- Regular local rings
- Gorenstein rings
- Castelnuovo-Mumford regularity
- Syzygies
- Free resolutions
- Ext and Tor

