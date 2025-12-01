# <span class="header-prerequisite">Prerequisite</span>
- [[Field]]
- [[Extension Field]]
- [[Polynomial Ring]]
- [[Number Theory]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Hardy & Wright, An Introduction to the Theory of Numbers
- Kuipers & Niederreiter, Uniform Distribution of Sequences

---

# <span class="header-definition">Overview</span>

**Kronecker Theorem**이라는 이름의 정리는 여러 분야에 걸쳐 존재한다:

1. **Field Theory**: Extension field의 구성 (대수학)
2. **Diophantine Approximation**: 등분포 이론 (수론)
3. **Kronecker-Weber Theorem**: Abelian extensions of $\mathbb{Q}$ (대수적 수론)

본 문서는 주요 두 버전을 다룬다.

---

# <span class="header-theorem">Version 1: Field Theory</span>

## Kronecker's Theorem (Field Extension)

**정리** (**Kronecker's Extension Theorem**):

Field $K$와 irreducible polynomial^[기약 다항식] $f(x) \in K[x]$ (with $\deg(f) \geq 1$)에 대해:

$$\exists \text{ field extension } F/K \text{ and } \alpha \in F \text{ such that } f(\alpha) = 0$$

**구성**: 
$$F = K[x]/(f(x))$$

**성질**:
1. $F$는 field ($f$ irreducible이므로 $\langle f(x) \rangle$ maximal)
2. $[F : K] = \deg(f)$
3. $\alpha = x + (f(x))$ (coset)는 $f$의 근

**의미**: "임의의 기약 다항식에 근을 추가할 수 있다"

## Splitting Field Construction^[분해체 구성]

**정리** (**Existence of Splitting Fields**):

모든 non-constant polynomial $p(x) \in K[x]$는 **splitting field^[분해체]**를 가진다

**구성**:
1. $p(x)$의 irreducible factor $f_1(x)$ 선택
2. $K_1 = K[x]/(f_1(x))$ 구성 (Kronecker's theorem)
3. $K_1$에서 $p(x) = (x - \alpha_1)q_1(x)$
4. $q_1(x)$에 대해 반복
5. 모든 근을 포함할 때까지 계속

**결과**: $F = K(\alpha_1, \ldots, \alpha_n)$ where $\alpha_i$는 $p(x)$의 모든 근

$$p(x) = c(x - \alpha_1)(x - \alpha_2) \cdots (x - \alpha_n) \in F[x]$$

**Degree bound**: $[F : K] \leq n!$ where $n = \deg(p)$

## Kronecker's Construction Lemma

**정리**: Irreducible $f(x) \in K[x]$, $\deg(f) = n$에 대해:

$$K[x]/(f(x)) \cong K(\alpha)$$

where $\alpha$ is a root of $f$ in some extension field

**Basis**: $\{1, \alpha, \alpha^2, \ldots, \alpha^{n-1}\}$

**원소**: $a_0 + a_1\alpha + \cdots + a_{n-1}\alpha^{n-1}$ where $a_i \in K$

**연산**: $\alpha^n$을 $f(\alpha) = 0$를 이용해 lower degree로 환원

---

# <span class="header-theorem">Version 2: Number Theory</span>

## Kronecker's Approximation Theorem

**정리** (**Kronecker's Approximation Theorem**):

실수 $\theta_1, \ldots, \theta_n$이 $\mathbb{Q}$-linearly independent^[유리수 선형독립]이면:

임의의 $\alpha_1, \ldots, \alpha_n \in \mathbb{R}$와 $\epsilon > 0$에 대해 정수 $m$과 $p_1, \ldots, p_n \in \mathbb{Z}$가 존재하여:

$$|m\theta_i - p_i - \alpha_i| < \epsilon \quad \text{for all } i = 1, \ldots, n$$

**의미**: $\mathbb{Q}$-독립인 무리수들의 정수 배수는 $\mathbb{R}^n/\mathbb{Z}^n$ (torus)에서 dense^[조밀]

## Equidistribution Version^[등분포 버전]

**정리** (**Weyl's Equidistribution Theorem**):

$\theta$가 irrational이면 수열 $(n\theta \bmod 1)_{n=1}^{\infty}$는 $[0, 1)$에서 **equidistributed^[등분포]**:

$$\lim_{N \to \infty} \frac{1}{N} \#\{1 \leq n \leq N : n\theta \bmod 1 \in [a, b]\} = b - a$$

**의미**: "무리수의 배수는 균등하게 분포"

### 다차원 버전

$\theta_1, \ldots, \theta_k$가 $1, \theta_1, \ldots, \theta_k$와 함께 $\mathbb{Q}$-linearly independent이면:

$$(n\theta_1 \bmod 1, \ldots, n\theta_k \bmod 1)$$

는 $[0, 1)^k$ (unit cube)에서 equidistributed

## Diophantine Approximation Connection

**관련**: Diophantine approximation^[디오판토스 근사]

임의의 irrational $\theta$와 $\epsilon > 0$에 대해 무한히 많은 정수 $p, q$가 존재:

$$\left|\theta - \frac{p}{q}\right| < \frac{\epsilon}{q}$$

자세한 내용은 [[Diophantine Approximation]] 참조

---

# <span class="header-examples">Examples</span>

## Field Theory Examples

### Example 1: Adjoining $\sqrt{2}$ to $\mathbb{Q}$

$f(x) = x^2 - 2 \in \mathbb{Q}[x]$ (irreducible)

**Kronecker construction**:
$$F = \mathbb{Q}[x]/(x^2 - 2)$$

**Isomorphism**: $F \cong \mathbb{Q}(\sqrt{2})$

**Basis**: $\{1, \alpha\}$ where $\alpha = x + (x^2 - 2)$

**Properties**: $\alpha^2 = 2$ in $F$

**Degree**: $[F : \mathbb{Q}] = 2$

### Example 2: Adjoining $i$ to $\mathbb{R}$

$f(x) = x^2 + 1 \in \mathbb{R}[x]$ (irreducible)

**Construction**: $F = \mathbb{R}[x]/(x^2 + 1)$

**Isomorphism**: $F \cong \mathbb{C}$

**Identification**: $\alpha = x + (x^2 + 1) \leftrightarrow i$

**Property**: $\alpha^2 = -1$

### Example 3: Cubic Extension

$f(x) = x^3 - 2 \in \mathbb{Q}[x]$ (irreducible by Eisenstein)

**First extension**: $K_1 = \mathbb{Q}[x]/(x^3 - 2) \cong \mathbb{Q}(\sqrt[3]{2})$

**Degree**: $[K_1 : \mathbb{Q}] = 3$

**But**: Not splitting field! ($\omega\sqrt[3]{2}$ not included where $\omega = e^{2\pi i/3}$)

**Splitting field**: $F = \mathbb{Q}(\sqrt[3]{2}, \omega)$

**Degree**: $[F : \mathbb{Q}] = 6$

### Example 4: Finite Field Extension

$f(x) = x^2 + x + 1 \in \mathbb{F}_2[x]$ (irreducible)

**Construction**: $\mathbb{F}_4 = \mathbb{F}_2[x]/(x^2 + x + 1)$

**Elements**: $\{0, 1, \alpha, \alpha + 1\}$ where $\alpha^2 + \alpha + 1 = 0$

**Degree**: $[\mathbb{F}_4 : \mathbb{F}_2] = 2$

## Number Theory Examples

### Example 5: Equidistribution of $n\sqrt{2}$

$\theta = \sqrt{2}$ (irrational)

수열 $(n\sqrt{2} \bmod 1)_{n=1}^{\infty}$:

$$0.414..., 0.828..., 0.242..., 0.656..., 0.071..., \ldots$$

**Kronecker**: Dense in $[0, 1]$

**Weyl**: Equidistributed in $[0, 1]$

### Example 6: Multiples of $\pi$

$\theta = \pi$ (irrational, transcendental)

$(n\pi \bmod 2\pi)$ is equidistributed in $[0, 2\pi)$

**응용**: Quasi-random number generation

### Example 7: Two-Dimensional

$\theta_1 = \sqrt{2}$, $\theta_2 = \sqrt{3}$

$(\sqrt{2}, \sqrt{3})$가 $\mathbb{Q}$-linearly independent이므로:

$$(n\sqrt{2} \bmod 1, n\sqrt{3} \bmod 1)$$

는 $[0, 1)^2$에서 equidistributed

---

# <span class="header-properties">Properties and Applications</span>

## Algebraic Closure Construction

**정리**: Kronecker's theorem을 반복 적용하여 algebraic closure^[대수적 폐포] 구성 가능

**과정**:
1. $K_0 = K$
2. $K_{n+1}$: 모든 $f \in K_n[x]$ (irreducible)에 대해 근 추가
3. $\overline{K} = \bigcup_{n=0}^{\infty} K_n$

**결과**: $\overline{K}$는 algebraically closed

## Minimal Field with Roots

**정리**: $f(x) \in K[x]$, irreducible, $\deg(f) = n$

$K[x]/(f(x))$는 $f$의 근을 포함하는 **최소** field extension

**Minimality**: 
- $K \subseteq F$이고 $f(\alpha) = 0$ for some $\alpha \in F$
- $\Rightarrow$ $K(\alpha) \subseteq F$
- $K(\alpha) \cong K[x]/(f(x))$

## Equidistribution Criteria

**Weyl's Criterion**: $(x_n)$ is equidistributed in $[0, 1)$ $\Leftrightarrow$

$$\lim_{N \to \infty} \frac{1}{N} \sum_{n=1}^{N} e^{2\pi i k x_n} = 0$$

for all nonzero integers $k$

**응용**: Fourier analysis

---

# <span class="header-remark">Remark</span>

## 직관적 이해 (Field Theory)

**Kronecker's Theorem**: "다항식의 근을 만들 수 있다"

**방법**:
1. Irreducible polynomial $f(x)$ 선택
2. Quotient ring $K[x]/(f(x))$ 구성
3. $x + (f(x))$가 $f$의 "근" 역할

**메타포**: "근이 없으면 만들면 된다"

**기하학적**: Algebraic extension as "dimension increase"

## 직관적 이해 (Number Theory)

**Kronecker's Approximation**: "무리수 배수는 촘촘히 분포"

**시각화**: Number line에서 $n\theta \bmod 1$의 점들

**직관**:
- Rational: 주기적 (finite orbits)
- Irrational: 촘촘히 분포 (dense)

**응용**: Monte Carlo, quasi-random numbers

## 역사적 배경

**Leopold Kronecker** (1823-1897):
- German mathematician
- 대수학과 수론에 기여
- "God made the integers, all else is the work of man"

**Field Theory (1880s)**:
- Field extension 구성
- 대수적 방정식 이론
- Galois theory 발전에 기여

**Number Theory**:
- Diophantine approximation
- 등분포 이론의 선구

**영향**:
- Modern field theory
- Abstract algebra
- Analytic number theory

## Kronecker vs Dedekind

**Kronecker**:
- Constructive approach
- Explicit field extensions
- "Computable" mathematics

**Dedekind**:
- Ideal theory
- Abstract approach
- General theory

**대조**: 철학적 차이 (constructivism vs abstraction)

## 응용 분야

### 1. Galois Theory^[갈루아 이론]

Splitting fields의 존재성:
- Galois groups 정의
- Normal extensions
- Field automorphisms

자세한 내용은 [[Galois Theory]] 참조

### 2. Algebraic Number Theory^[대수적 수론]

**Number fields**: $\mathbb{Q}$의 finite extensions

**Construction**: Polynomials의 근 추가

**예**:
- $\mathbb{Q}(\sqrt{d})$ (quadratic fields)
- $\mathbb{Q}(\zeta_n)$ (cyclotomic fields)

### 3. Algebraic Geometry^[대수기하학]

**Function fields**: Extensions by algebraic functions

**Coordinate rings**: $K[x_1, \ldots, x_n]/I$

### 4. Coding Theory^[부호이론]

**Finite field extensions**: Error-correcting codes

**BCH codes**: Splitting fields of polynomials

### 5. Cryptography^[암호학]

**Finite fields**: $\mathbb{F}_{p^n}$ construction

**Elliptic curves**: Over extension fields

### 6. Quasi-Random Numbers

**Equidistribution**: Monte Carlo methods

**Low-discrepancy sequences**: Halton, Sobol sequences

**응용**: Numerical integration, simulation

---

# <span class="header-theorem">Related Theorems</span>

## Kronecker-Weber Theorem

**정리** (**Kronecker-Weber Theorem**):

$K/\mathbb{Q}$ finite abelian extension^[유한 아벨 확대] $\Leftrightarrow$ $K \subseteq \mathbb{Q}(\zeta_n)$ for some $n$

**의미**: $\mathbb{Q}$의 모든 abelian Galois extension은 cyclotomic^[원분]

**예**:
- $\mathbb{Q}(\sqrt{d}) \subseteq \mathbb{Q}(\zeta_m)$ for appropriate $m$
- $\mathbb{Q}(i) \subseteq \mathbb{Q}(\zeta_4)$

**중요성**: Class field theory의 특수 경우

## Primitive Element Theorem

**정리**: Finite separable extension $F/K$에 대해:

$$\exists \alpha \in F: \quad F = K(\alpha)$$

**연결**: Kronecker construction을 단일 원소로 축소

자세한 내용은 [[Extension Field]] 참조

## Fundamental Theorem of Algebra

**정리**: $\mathbb{C}$는 algebraically closed^[대수적으로 닫힘]

**연결**: 모든 polynomial이 이미 $\mathbb{C}$에서 split

Kronecker construction 불필요 (이미 모든 근 포함)

## Weyl's Equidistribution Theorem

**정리**: Polynomial $P(n)$ with at least one irrational coefficient (non-constant term):

$$(P(1) \bmod 1, P(2) \bmod 1, P(3) \bmod 1, \ldots)$$

is equidistributed in $[0, 1)$

**예**: $(n^2\sqrt{2} \bmod 1)$ is equidistributed

---

# <span class="header-proof">Proof Sketch (Field Theory)</span>

## Proof of Kronecker's Extension Theorem

**Given**: $K$ field, $f(x) \in K[x]$ irreducible

**Construct**: $F = K[x]/(f(x))$

### Step 1: $F$ is a Field

$f(x)$ irreducible in $K[x]$

$\Rightarrow$ $\langle f(x) \rangle$ is maximal ideal (in PID $K[x]$)

$\Rightarrow$ $F = K[x]/(f(x))$ is field ✓

### Step 2: $K$ embeds in $F$

Canonical map: $\phi: K \to F$, $\phi(a) = a + (f(x))$

**Injective**: $\ker(\phi) = K \cap (f(x)) = \{0\}$ (since $\deg(f) \geq 1$)

따라서 $K \cong \phi(K) \subseteq F$ ✓

### Step 3: Root Exists

$\alpha = x + (f(x)) \in F$

**Verification**:
$$f(\alpha) = f(x) + (f(x)) = 0 + (f(x)) = 0 \in F$$ ✓

### Step 4: Degree

**Basis**: $\{1, \alpha, \alpha^2, \ldots, \alpha^{n-1}\}$ where $n = \deg(f)$

**Independence**: Suppose $\sum_{i=0}^{n-1} a_i \alpha^i = 0$
- Then $g(x) = \sum a_i x^i \in (f(x))$
- But $\deg(g) < \deg(f)$
- 따라서 $g = 0$, 즉 $a_i = 0$ for all $i$ ✓

**Spanning**: $\alpha^n$을 $f(\alpha) = 0$로 환원 가능

따라서 $[F : K] = n$ ✓

---

# <span class="header-proof">Proof Sketch (Number Theory)</span>

## Proof of Kronecker's Approximation Theorem

**Given**: $\theta_1, \ldots, \theta_n$ are $\mathbb{Q}$-linearly independent

**Prove**: $\{(m\theta_1, \ldots, m\theta_n) : m \in \mathbb{Z}\}$ is dense in $\mathbb{R}^n/\mathbb{Z}^n$

### Step 1: Compactness

Torus $\mathbb{R}^n/\mathbb{Z}^n$ is compact^[컴팩트]

### Step 2: Subgroup

$H = \{(m\theta_1 \bmod 1, \ldots, m\theta_n \bmod 1) : m \in \mathbb{Z}\}$ is subgroup

### Step 3: Closure

$\overline{H}$ (closure) is also a subgroup

Compact subgroup of $\mathbb{R}^n/\mathbb{Z}^n$

### Step 4: Pontryagin Duality

**Character theory**: If $\overline{H} \neq \mathbb{R}^n/\mathbb{Z}^n$

Then $\exists$ nontrivial character $\chi: \mathbb{R}^n/\mathbb{Z}^n \to S^1$ vanishing on $H$

$$\chi(m\theta_1, \ldots, m\theta_n) = e^{2\pi i(k_1 m\theta_1 + \cdots + k_n m\theta_n)} = 1$$

for all $m \in \mathbb{Z}$, some $(k_1, \ldots, k_n) \neq (0, \ldots, 0)$

**Contradiction**: $k_1\theta_1 + \cdots + k_n\theta_n \in \mathbb{Z}$ (linear dependence!) ✗

따라서 $\overline{H} = \mathbb{R}^n/\mathbb{Z}^n$ ✓

---

# <span class="header-examples">Applications</span>

## 1. Construction of Number Fields

**Process**:
1. Irreducible polynomial over $\mathbb{Q}$
2. Kronecker construction
3. Number field obtained

**예**: All quadratic fields $\mathbb{Q}(\sqrt{d})$

## 2. Finite Field Construction

**$\mathbb{F}_{p^n}$ construction**:
1. Find irreducible $f(x) \in \mathbb{F}_p[x]$ of degree $n$
2. $\mathbb{F}_{p^n} = \mathbb{F}_p[x]/(f(x))$

**응용**: Cryptography (AES, ECC)

## 3. Computational Algebra

**Computer algebra systems**: Maxima, Mathematica, SageMath

**Implementation**: Kronecker construction for symbolic computation

## 4. Uniform Distribution

**Monte Carlo**: Pseudo-random number generation

**Quasi-Monte Carlo**: Low-discrepancy sequences

**Numerical integration**: Faster convergence than random

## 5. Dynamical Systems

**Irrational rotations**: $x \mapsto x + \theta \pmod{1}$

**Ergodic theory**: Equidistribution = ergodicity

---

# <span class="header-remark">Remark</span>

## Field Theory vs Number Theory

두 정리는 완전히 다른 분야:

| | Field Theory | Number Theory |
|---|--------------|---------------|
| **대상** | Fields, polynomials | Real numbers, integers |
| **목표** | Extension 구성 | Approximation, distribution |
| **도구** | Quotient rings | Fourier analysis |
| **응용** | Galois theory | Diophantine approximation |

**공통점**: Leopold Kronecker의 이름

## Constructive Mathematics

Kronecker는 **constructivist^[구성주의자]**:

**철학**: "존재"는 "구성"을 의미해야 함

**Kronecker's theorem**: 명시적 구성 제공
- $K[x]/(f(x))$ is explicit
- Computable in principle

**대조**: Existence proofs without construction

## Common Pitfalls^[흔한 실수]

### 1. Splitting Field = Kronecker Extension?

✗ $K[x]/(f(x))$가 splitting field?

✓ 일반적으로 아님! 한 개의 근만 추가

**반례**: $\mathbb{Q}[x]/(x^3 - 2)$ is not splitting field of $x^3 - 2$

### 2. Equidistribution = Uniform?

✗ $(n\theta \bmod 1)$이 균등 분포처럼 보인다?

✓ Asymptotically equidistributed (finite $N$에서는 gap 존재)

### 3. Rational Linear Combination?

✗ 모든 무리수에 대해 성립?

✓ $\mathbb{Q}$-linearly **independent** 필요!

**반례**: $\sqrt{2}, 2\sqrt{2}$는 linearly dependent

### 4. Irreducible ≠ No Roots

✗ Irreducible이면 근이 없다?

✓ **Base field에서** 근이 없음 (extension에서는 존재)

### 5. Uniqueness

✗ Extension field is unique?

✓ Up to **$K$-isomorphism**

Different constructions give isomorphic fields

## 관련 개념

### Field Theory

- [[Extension Field]]: General theory
- [[Splitting Field]]: All roots included
- [[Galois Theory]]: Symmetries of extensions
- [[Algebraic Closure]]: All polynomials split
- [[Polynomial Ring]]: $K[x]$ and quotients

### Number Theory

- [[Diophantine Approximation]]: Rational approximations
- [[Equidistribution]]: Uniform distribution theory
- [[Weyl's Theorem]]: Equidistribution criteria
- [[Ergodic Theory]]: Long-term behavior

### Applications

- [[Finite Fields]]: $\mathbb{F}_{p^n}$ construction
- [[Cyclotomic Fields]]: $\mathbb{Q}(\zeta_n)$
- [[Quadratic Fields]]: $\mathbb{Q}(\sqrt{d})$

