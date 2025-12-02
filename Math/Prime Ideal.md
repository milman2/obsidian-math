# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Ideal]]
- [[Integral Domain]]
- [[Quotient Ring]]

# <span class="header-reference">Reference</span>
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Eisenbud, Commutative Algebra with a View Toward Algebraic Geometry
- Dummit & Foote, Abstract Algebra

---

# <span class="header-definition">Definition</span>

## Prime Ideal^[소 아이디얼]

Commutative ring $R$의 proper ideal^[진 아이디얼] $P$가 **prime ideal**^[소 아이디얼]이다 $\Leftrightarrow$

$$ab \in P \quad \Rightarrow \quad a \in P \text{ or } b \in P$$

**표기**: $P \in \text{Spec}(R)$

**직관**: "소수처럼" 작동하는 ideal

## Equivalent Characterizations

다음은 모두 동치:

**1. Definition**: $ab \in P \Rightarrow a \in P$ or $b \in P$

**2. Quotient ring**: $R/P$가 **integral domain**^[정역]

**3. Complement**: $R \setminus P$가 **multiplicatively closed**^[곱셈에 닫혀있음]

$$a, b \notin P \quad \Rightarrow \quad ab \notin P$$

**4. Ideal product**: $IJ \subseteq P \Rightarrow I \subseteq P$ or $J \subseteq P$ (ideals $I, J$)

**증명**:

**(1 $\Leftrightarrow$ 2)**: 

($\Rightarrow$) $P$ prime이면, $(a + P)(b + P) = 0 + P$일 때
- $ab \in P$
- $\Rightarrow$ $a \in P$ or $b \in P$
- $\Rightarrow$ $a + P = 0$ or $b + P = 0$
- 따라서 $R/P$는 integral domain 
($\Leftarrow$) $R/P$ integral domain이면, $ab \in P$일 때
- $(a + P)(b + P) = 0 + P$
- $\Rightarrow$ $a + P = 0$ or $b + P = 0$
- $\Rightarrow$ $a \in P$ or $b \in P$ 
**(1 $\Leftrightarrow$ 3)**: Contrapositive 
**(1 $\Rightarrow$ 4)**: $IJ \subseteq P$이고 $I \not\subseteq P$이면
- $\exists a \in I \setminus P$
- 모든 $b \in J$에 대해 $ab \in IJ \subseteq P$
- Prime property: $ab \in P$ and $a \notin P$ $\Rightarrow$ $b \in P$
- 따라서 $J \subseteq P$ 
## Prime Element

Ring $R$의 원소 $p$가 **prime element**^[소원]이다 $\Leftrightarrow$

1. $p$는 non-unit, non-zero
2. $p | ab \Rightarrow p | a$ or $p | b$

**관계**: $\langle p \rangle$가 prime ideal $\Leftrightarrow$ $p$가 prime element (in integral domain)

자세한 내용은 [[Prime Element]] 참조

## Minimal Prime Ideal

Ideal $I$에 대한 **minimal prime over $I$**^[최소 소 아이디얼]:

Prime ideal $P \supseteq I$로 다음을 만족:

$$I \subseteq Q \subseteq P, \quad Q \text{ prime} \quad \Rightarrow \quad Q = P$$

**의미**: $I$를 포함하는 "가장 작은" prime ideal

**존재성**: Zorn's Lemma로 보장 (Noetherian에서는 직접 증명 가능)

## Associated Prime

Noetherian ring $R$의 ideal $I$에 대한 **associated prime**^[결합 소 아이디얼]:

$$\text{Ass}(I) = \{P \text{ prime} : P = \text{ann}(r + I) \text{ for some } r \in R\}$$

**의미**: $I$의 구조를 "나타내는" prime ideals

자세한 내용은 [[Associated Prime]] 참조

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Proper Ideal

**정리**: Prime ideal은 항상 proper ideal

**증명**: $P = R$이면 $1 \in P$
- 모든 $a \in R$에 대해 $a = a \cdot 1 \in P$
- 따라서 $P = R$ 
하지만 정의상 prime ideal은 proper 
### 2. Contains a Product

**정리**: $a_1 \cdots a_n \in P$ (prime ideal)이면

$$\exists i: \quad a_i \in P$$

**증명**: Induction on $n$
- $n = 2$: definition - $n > 2$: $(a_1 \cdots a_{n-1}) a_n \in P$
  - $\Rightarrow$ $a_1 \cdots a_{n-1} \in P$ or $a_n \in P$
  - If first: induction hypothesis 
### 3. Prime vs Maximal

**정리**: Every maximal ideal is prime

**증명**: $M$ maximal $\Rightarrow$ $R/M$ is field $\Rightarrow$ $R/M$ is integral domain $\Rightarrow$ $M$ is prime 
**역 거짓**: Prime ideal이 maximal은 아님!

예: $\langle x \rangle \triangleleft \mathbb{Z}[x]$ is prime but not maximal

자세한 내용은 [[Maximal Ideal]] 참조

### 4. Prime in PID

**정리**: $R$이 PID이고 $P = \langle p \rangle$ nonzero prime ideal이면 $P$는 maximal

**증명**: $P \subseteq I \subseteq R$이고 $I = \langle a \rangle$이면
- $p = ab$ for some $b$
- $p$ prime $\Rightarrow$ $p | a$ or $p | b$
- If $p | a$: $I = R$
- If $p | b$: $I = P$
- 따라서 $P$ maximal 
자세한 내용은 [[Principal Ideal Domain]] 참조

### 5. Union of Prime Ideals

**정리 (Prime Avoidance)**: Ideal $I$가 prime ideals $P_1, \ldots, P_n$의 합집합에 포함되면

$$I \subseteq \bigcup_{i=1}^{n} P_i \quad \Rightarrow \quad \exists i: I \subseteq P_i$$

**의미**: Ideal은 한 prime에 완전히 포함

## Spectrum

**정의**: Ring $R$의 **spectrum**^[스펙트럼]

$$\text{Spec}(R) = \{\text{all prime ideals of } R\}$$

### Zariski Topology

$\text{Spec}(R)$에 **Zariski topology**^[자리스키 위상] 부여:

**Closed sets**: 

$$V(I) = \{P \in \text{Spec}(R) : P \supseteq I\}$$

for ideal $I$

**Open sets**: Complements of closed sets

**Basic opens**:

$$D(f) = \{P \in \text{Spec}(R) : f \notin P\} = \text{Spec}(R) \setminus V(\langle f \rangle)$$

자세한 내용은 [[Spectrum]], [[Algebraic Geometry]] 참조

## Localization

**정리**: $P$ prime ideal이면 $S = R \setminus P$는 multiplicatively closed

**Localization**:

$$R_P = S^{-1}R = \left\{ \frac{r}{s} : r \in R, s \notin P \right\}$$

**성질**: $R_P$는 **local ring**^[국소환]
- Unique maximal ideal: $P R_P = \{\frac{p}{s} : p \in P, s \notin P\}$

자세한 내용은 [[Localization]], [[Local Ring]] 참조

## Height and Dimension

**정의**: Prime ideal $P$의 **height**^[높이]

$$\text{ht}(P) = \sup\{n : P_0 \subsetneq P_1 \subsetneq \cdots \subsetneq P_n = P\}$$

**의미**: $P$에 이르는 prime ideals의 최대 사슬 길이

**Krull dimension**: 

$$\dim(R) = \sup\{\text{ht}(P) : P \in \text{Spec}(R)\}$$

자세한 내용은 [[Krull Dimension]] 참조

## Operations on Prime Ideals

### Extension and Contraction

$\phi: R \to S$ ring homomorphism일 때:

**Extension**: $P \triangleleft R$ $\mapsto$ $P^e = PS$

**Contraction**: $Q \triangleleft S$ $\mapsto$ $Q^c = \phi^{-1}(Q)$

**정리**: $P$ prime $\Rightarrow$ $P^c$ prime 
하지만: $P$ prime $\not\Rightarrow$ $P^e$ prime (일반적으로)

### Intersection

**정리**: Prime ideals의 교집합은 일반적으로 prime이 아님!

예: $\langle 2 \rangle \cap \langle 3 \rangle = \langle 6 \rangle$ in $\mathbb{Z}$

$\langle 6 \rangle$은 prime 아님 ($2 \cdot 3 \in \langle 6 \rangle$ but $2, 3 \notin \langle 6 \rangle$)

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$

**Prime ideals**: $\langle p \rangle$ where $p$ is prime (또는 $\langle 0 \rangle$)

- $\langle 0 \rangle$: Zero ideal  ($\mathbb{Z}$ is integral domain)
- $\langle 2 \rangle$: $ab \in \langle 2 \rangle \Rightarrow 2 | ab \Rightarrow 2 | a$ or $2 | b$ - $\langle 3 \rangle$, $\langle 5 \rangle$, $\langle 7 \rangle$, ... (all primes)

**NOT prime**: $\langle 4 \rangle$
- $2 \cdot 2 \in \langle 4 \rangle$ but $2 \notin \langle 4 \rangle$ ✗

**모든 nonzero prime ideals는 maximal** (PID!)

## Example 2: $\mathbb{Z}/12\mathbb{Z}$

**Prime ideals**:
- $\langle \overline{2} \rangle = \{0, 2, 4, 6, 8, 10\}$
- $\langle \overline{3} \rangle = \{0, 3, 6, 9\}$

**Check $\langle \overline{2} \rangle$**:

$$\mathbb{Z}/12\mathbb{Z} / \langle \overline{2} \rangle \cong \mathbb{Z}/2\mathbb{Z}$$ (field!) 
**Check $\langle \overline{3} \rangle$**:

$$\mathbb{Z}/12\mathbb{Z} / \langle \overline{3} \rangle \cong \mathbb{Z}/3\mathbb{Z}$$ (field!) 
**둘 다 maximal이기도 함!**

## Example 3: $k[x]$ (Polynomial Ring)

**Prime ideals** (field $k$):
- $\langle 0 \rangle$: Zero ideal  ($k[x]$ is integral domain)
- $\langle f(x) \rangle$ where $f$ is irreducible polynomial

**예**:
- $\langle x \rangle$ in $\mathbb{R}[x]$ - $\langle x^2 + 1 \rangle$ in $\mathbb{R}[x]$ - $\langle x - a \rangle$ in $k[x]$  (linear polynomials)

**NOT prime**: $\langle x^2 - 1 \rangle$ in $\mathbb{R}[x]$
- $x^2 - 1 = (x-1)(x+1)$ (reducible) ✗

**모든 nonzero prime ideals는 maximal** (PID!)

## Example 4: $\mathbb{Z}[x]$

**Prime ideals**:
- $\langle 0 \rangle$: Zero ideal - $\langle p \rangle$: $p$ prime number - $\langle f(x) \rangle$: $f$ irreducible in $\mathbb{Z}[x]$ - $\langle p, f(x) \rangle$: $p$ prime, $f$ irreducible mod $p$ 
**예**:
- $\langle 2 \rangle$ is prime - $\langle x \rangle$ is prime - $\langle 2, x \rangle$ is prime AND maximal 
**Hierarchy**:

$$\langle 0 \rangle \subsetneq \langle 2 \rangle \subsetneq \langle 2, x \rangle$$

(chain of prime ideals!)

**Not all primes are maximal**: $\langle x \rangle$ is prime but not maximal
- $\mathbb{Z}[x] / \langle x \rangle \cong \mathbb{Z}$ (integral domain, not field)

## Example 5: $k[x, y]$ (Two Variables)

**Prime ideals**:
- $\langle 0 \rangle$ - $\langle f(x, y) \rangle$: $f$ irreducible - $\langle f, g \rangle$: (sometimes) 
**예**:
- $\langle x \rangle$  (prime, not maximal)
- $\langle y \rangle$  (prime, not maximal)
- $\langle x - a, y - b \rangle$  (maximal!)
- $\langle x^2 + y^2 - 1 \rangle$  (circle!)

**Geometric interpretation**:
- $\langle 0 \rangle$: Whole space $k^2$
- $\langle f \rangle$: Irreducible curve
- $\langle f, g \rangle$ (maximal): Point (intersection)

자세한 내용은 [[Algebraic Geometry]] 참조

## Example 6: $\mathbb{Z}[i]$ (Gaussian Integers)

**Prime ideals**:
- $\langle 0 \rangle$ - $\langle \pi \rangle$: $\pi$ Gaussian prime

**Gaussian primes**:
- $1 + i$ (since $N(1+i) = 2$, prime in $\mathbb{Z}[i]$)
- $2 + i$, $2 - i$
- Rational primes $p \equiv 3 \pmod{4}$
- Factors of $p \equiv 1 \pmod{4}$

**모든 nonzero prime ideals는 maximal** (PID!)

자세한 내용은 [[Gaussian Integers]] 참조

## Example 7: Non-Commutative (주의!)

**Matrix ring $M_2(\mathbb{R})$**:

Prime ideal 정의가 **작동하지 않음**!

이유: Non-commutative ring에서는 다른 정의 필요

본 문서는 **commutative rings만** 다룸

## Example 8: Direct Product

**$R = R_1 \times R_2$**

**Prime ideals**:
- $P_1 \times R_2$ where $P_1$ prime in $R_1$
- $R_1 \times P_2$ where $P_2$ prime in $R_2$

**예**: $\mathbb{Z} \times \mathbb{Z}$
- $2\mathbb{Z} \times \mathbb{Z}$ - $\mathbb{Z} \times 3\mathbb{Z}$ 
**Check**: 

$$(R_1 \times R_2) / (P_1 \times R_2) \cong R_1/P_1 \times R_2/R_2 \cong R_1/P_1 \times \{0\}$$

Wait, this needs correction. Actually:

**Correct prime ideals** in $R_1 \times R_2$:
- $P \times R_2$ where $P$ prime in $R_1$ **and $R_2$ is integral domain**
- $R_1 \times Q$ where $Q$ prime in $R_2$ **and $R_1$ is integral domain**

For $\mathbb{Z} \times \mathbb{Z}$:
- $p\mathbb{Z} \times \mathbb{Z}$ (NOT prime!) since quotient has zero divisors

Actually, direct product of two nontrivial rings has **no prime ideals except when one factor is 0**!

## Example 9: Localization Example

**$R = \mathbb{Z}$, $P = \langle 2 \rangle$**

**Localization**:

$$\mathbb{Z}_{(2)} = \left\{ \frac{a}{b} : 2 \nmid b \right\}$$

**Elements**: $\frac{1}{1}, \frac{2}{1}, \frac{1}{3}, \frac{2}{3}, \frac{4}{3}, \ldots$

**Maximal ideal**: $2\mathbb{Z}_{(2)} = \left\{ \frac{2k}{b} : 2 \nmid b \right\}$

## Example 10: $C([0,1])$ (Continuous Functions)

**Prime ideals**: 

$$M_x = \{f \in C([0,1]) : f(x) = 0\}$$

for each $x \in [0,1]$

**Check**: $fg \in M_x$ (즉 $f(x)g(x) = 0$)
- $\Rightarrow$ $f(x) = 0$ or $g(x) = 0$ (실수의 성질)
- $\Rightarrow$ $f \in M_x$ or $g \in M_x$ 
**모든 prime ideals는 이 형태** (Gelfand-Naimark)

**모두 maximal이기도 함!**

---

# <span class="header-theorem">Theorem</span>

## Krull's Theorem

**정리**: Nontrivial commutative ring $R$은 적어도 하나의 prime ideal을 가짐

**증명**: Zorn's Lemma
- Proper ideals의 collection에서 maximal element 선택
- Maximal ideal은 prime 
## Prime Ideal Principle

**정리**: Ideal $I$가 multiplicatively closed set $S$와 disjoint이면

$$\exists P \text{ prime}: \quad I \subseteq P, \quad P \cap S = \emptyset$$

**응용**: Prime ideal 존재성 증명

## Lying Over

**정리**: $R \subseteq S$ integral extension이고 $P$ prime in $R$이면

$$\exists Q \text{ prime in } S: \quad Q \cap R = P$$

**의미**: Prime ideal이 "위로 확장"됨

자세한 내용은 [[Integral Extension]] 참조

## Going-Up Theorem

**정리**: $R \subseteq S$ integral extension이고 $P_1 \subseteq P_2$ primes in $R$, $Q_1$ prime in $S$ with $Q_1 \cap R = P_1$이면

$$\exists Q_2 \text{ prime in } S: \quad Q_1 \subseteq Q_2, \quad Q_2 \cap R = P_2$$

## Going-Down Theorem

**정리**: $R \subseteq S$ flat extension이고 $P_1 \supseteq P_2$ primes in $R$, $Q_1$ prime in $S$ with $Q_1 \cap R = P_1$이면

$$\exists Q_2 \text{ prime in } S: \quad Q_1 \supseteq Q_2, \quad Q_2 \cap R = P_2$$

## Primary Decomposition

**정리**: Noetherian ring $R$에서 ideal $I$는 **primary ideals**의 교집합으로 표현 가능

$$I = Q_1 \cap \cdots \cap Q_n$$

where each $Q_i$ is $P_i$-primary for some prime $P_i$

자세한 내용은 [[Primary Decomposition]] 참조

## Dimension Theorems

**Krull's Principal Ideal Theorem**: $R$ Noetherian, $x$ non-unit이면

$$\text{ht}(\langle x \rangle) \leq 1$$

**Krull's Height Theorem**: $I = \langle x_1, \ldots, x_n \rangle$이면

$$\text{ht}(I) \leq n$$

자세한 내용은 [[Krull Dimension]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Prime Ideal = "소수처럼 작동"**

### 소수의 성질

**정수에서**: $p$ prime이면

$$p | ab \quad \Rightarrow \quad p | a \text{ or } p | b$$

**Ideal에서**: $P$ prime이면

$$ab \in P \quad \Rightarrow \quad a \in P \text{ or } b \in P$$

**완벽한 유사성!**

### 메타포: 필터

**Prime ideal**: "소수만 통과"시키는 필터

**작동 방식**:
- 곱 $ab$가 필터를 통과하면
- 적어도 하나의 인자가 필터를 통과해야 함

### Quotient = Integral Domain

**$R/P$ is integral domain**

**의미**:
- $P$로 나누면 "zero divisors 제거"
- "깨끗한" domain 얻음

## Prime vs Maximal

| | Prime Ideal | Maximal Ideal |
|---|-------------|---------------|
| **정의** | $ab \in P \Rightarrow a \in P$ or $b \in P$ | 더 큰 proper ideal 없음 |
| **Quotient** | Integral domain | Field |
| **관계** | Maximal $\Rightarrow$ Prime | Prime $\not\Rightarrow$ Maximal |
| **예 ($\mathbb{Z}$)** | $\langle 0 \rangle$, $\langle p \rangle$ | $\langle p \rangle$ only |
| **예 ($\mathbb{Z}[x]$)** | $\langle 0 \rangle$, $\langle x \rangle$, ... | $\langle p, f \rangle$ |

**핵심**: 
- Maximal은 "가장 큰" proper ideal
- Prime은 "소수 성질" 가진 ideal
- PID에서: Nonzero prime = Maximal

자세한 내용은 [[Maximal Ideal]] 참조

## 기하학적 해석

**Algebraic Geometry**:

**Prime ideal $P \subseteq k[x_1, \ldots, x_n]$** $\leftrightarrow$ **Irreducible variety**

$$V(P) = \{(a_1, \ldots, a_n) : f(a_1, \ldots, a_n) = 0 \text{ for all } f \in P\}$$

**의미**:
- Prime ideal: "나눌 수 없는" geometric object
- Maximal ideal: Point
- Height: Dimension

**예**:
- $\langle 0 \rangle$: Whole space (irreducible)
- $\langle f \rangle$: Irreducible curve/hypersurface
- $\langle x - a, y - b \rangle$: Point

## 응용 분야

### 1. Algebraic Geometry

**Spectrum**: $\text{Spec}(R)$ = geometric object

**Properties**:
- Prime ideals = points
- Zariski topology
- Sheaf of functions

### 2. Number Theory

**Prime ideals in $\mathcal{O}_K$** (ring of integers):

- Generalize prime numbers
- Unique factorization of ideals
- Class field theory

### 3. Commutative Algebra

**Localization**: At prime ideals

**Primary decomposition**: Into primary ideals

**Dimension theory**: Chains of primes

### 4. Algebraic Topology

**Cohomology rings**: Prime ideals in $H^*(X)$

## 계산 방법

### Prime Test

**방법 1**: Check quotient is integral domain
- Compute $R/P$
- Check no zero divisors

**방법 2**: Check definition directly
- For all $a, b$: $ab \in P \Rightarrow a \in P$ or $b \in P$

**방법 3**: Use generators (polynomial rings)
- Gröbner basis methods
- Computer algebra systems

### Finding Primes

**In $\mathbb{Z}$**: $\langle p \rangle$ for primes $p$, plus $\langle 0 \rangle$

**In $k[x]$**: $\langle f \rangle$ for irreducible $f$, plus $\langle 0 \rangle$

**In $\mathbb{Z}[x]$**: More complex, use height considerations

## Common Pitfall^[흔한 실수]

### 1. Prime $\neq$ Maximal

$\langle x \rangle \triangleleft \mathbb{Z}[x]$ is prime but NOT maximal!

**이유**: $\mathbb{Z}[x] / \langle x \rangle \cong \mathbb{Z}$ (domain, not field)

### 2. Zero Ideal

$\langle 0 \rangle$이 prime인지 확인!

**답**: $R$이 integral domain이면 prime 
### 3. Intersection of Primes

Prime ideals의 교집합이 prime? **NO!**

예: $\langle 2 \rangle \cap \langle 3 \rangle = \langle 6 \rangle$ (not prime in $\mathbb{Z}$)

### 4. Extension of Primes

$P$ prime in $R$, $\phi: R \to S$ homomorphism

**Contraction**: $\phi^{-1}(Q)$ always prime if $Q$ prime 
**Extension**: $\phi(P)$ generally NOT prime! ✗

### 5. Prime in Non-commutative

Non-commutative rings에서는 다른 정의 필요!

왼쪽/오른쪽 구분 등 복잡

### 6. Reducible vs Prime

**Reducible element** $\neq$ **prime element**

- Reducible: $a = bc$ (nontrivial factorization)
- Prime: $a | bc \Rightarrow a | b$ or $a | c$

In UFD: Irreducible $\Leftrightarrow$ Prime

## 관련 개념

- [[Ideal]]: General concept
- [[Maximal Ideal]]: Strongest type
- [[Principal Ideal]]: Generated by one element
- [[Integral Domain]]: Ring with no zero divisors
- [[Quotient Ring]]: $R/P$ construction
- [[Spectrum]]: Set of all primes
- [[Localization]]: Inverting complement
- [[Primary Decomposition]]: Decomposition into primaries

## 추가 학습 주제

**기초**:
- Definition and examples
- Prime vs maximal
- Quotient characterization
- Examples in $\mathbb{Z}$, $k[x]$

**중급**:
- Spectrum and Zariski topology
- Localization at primes
- Height and dimension
- Minimal primes

**고급**:
- Associated primes
- Primary decomposition
- Going-Up/Down theorems
- Dimension theory
- Schemes in algebraic geometry

