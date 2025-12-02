# <span class="header-prerequisite">Prerequisite</span>
- [[Polynomial Ring]]
- [[Integral Domain]]
- [[Unique Factorization Domain]]
- [[Field]]
- [[Prime Ideal]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Artin, Algebra
- Jacobson, Basic Algebra I

---

# <span class="header-definition">Definition</span>

## Irreducible Polynomial^[기약 다항식]

Integral domain^[정역] $R$, polynomial^[다항식] $f(x) \in R[x]$ (nonzero, non-unit)가 **irreducible**^[기약]이다 $\Leftrightarrow$

$$f(x) = g(x) h(x) \quad \Rightarrow \quad g(x) \in R[x]^\times \text{ or } h(x) \in R[x]^\times$$

**의미**: Nontrivial factorization^[비자명한 인수분해]이 불가능

**단위원**^[Units]: $R[x]^\times$ = units in $R[x]$
- Field $k$에서: $k[x]^\times = k \setminus \{0\}$ (nonzero constants)
- $\mathbb{Z}[x]$에서: $\mathbb{Z}[x]^\times = \{\pm 1\}$

### Reducible Polynomial^[가약 다항식]

$f(x) \in R[x]$가 **reducible**^[가약]이다 $\Leftrightarrow$ irreducible이 **아니다**

$$\exists g, h \in R[x] \text{ (both non-units)}: \quad f(x) = g(x) h(x)$$

**의미**: Nontrivial factorization 가능

## Over Fields (가장 중요한 경우)

Field $k$, polynomial $f(x) \in k[x]$ (nonzero, nonconstant)

**Irreducible** $\Leftrightarrow$

$$f(x) = g(x) h(x) \quad \Rightarrow \quad \deg(g) = 0 \text{ or } \deg(h) = 0$$

**동등 표현**: 

$$\deg(g), \deg(h) \geq 1 \quad \Rightarrow \quad f(x) \neq g(x) h(x)$$

**핵심**: Degree 1 이상의 인수로는 분해 불가능

### Degree Classification

**Degree 1 polynomials**: **항상 irreducible** over any field

$$f(x) = ax + b \quad (a \neq 0)$$

**Degree $\geq 2$**: Field에 따라 다름

## Prime Polynomial^[소 다항식]

UFD $R$에서 polynomial $p(x) \in R[x]$가 **prime**^[소]이다 $\Leftrightarrow$

$$p(x) \mid f(x) g(x) \quad \Rightarrow \quad p(x) \mid f(x) \text{ or } p(x) \mid g(x)$$

**정리**: $k[x]$ (field $k$)에서:

$$p(x) \text{ is irreducible} \quad \Leftrightarrow \quad p(x) \text{ is prime}$$

자세한 내용은 [[Unique Factorization Domain]] 참조

---

# <span class="header-theorem">Theorems</span>

## Fundamental Theorem

**정리**: Field $k$에 대해, $k[x]$는 **UFD**^[유일 인수분해 정역]

**결과**: 모든 nonconstant polynomial은 irreducible polynomials의 곱으로 유일하게 분해

$$f(x) = c \cdot p_1(x)^{e_1} p_2(x)^{e_2} \cdots p_r(x)^{e_r}$$

where:
- $c \in k \setminus \{0\}$ (leading coefficient)
- $p_i(x)$ irreducible, monic^[최고차 계수가 1]
- $e_i \geq 1$

**유일성**: Irreducibles는 순서와 unit 배수를 제외하고 유일

## Irreducibility Criteria

### 1. Degree Test

**정리**: Field $k$, $f(x) \in k[x]$ with $\deg(f) \leq 3$

$$f(x) \text{ is irreducible over } k \quad \Leftrightarrow \quad f \text{ has no roots in } k$$

**증명**:
- Reducible이면 degree 1 factor 존재 → root 존재
- Root 존재하면 Factor Theorem으로 $(x-a) \mid f(x)$ → reducible

**주의**: Degree $\geq 4$에서는 **성립하지 않음**!

**반례**: $f(x) = (x^2 + 1)^2 = x^4 + 2x^2 + 1$ over $\mathbb{R}$
- No real roots
- But reducible: $f(x) = (x^2 + 1)(x^2 + 1)$

### 2. Eisenstein's Criterion^[아이젠슈타인 판정법]

**정리**: UFD $R$, $f(x) = a_0 + a_1 x + \cdots + a_n x^n \in R[x]$

Prime $p \in R$에 대해 다음 조건을 만족하면 $f(x)$는 $\text{Frac}(R)[x]$에서 irreducible:

1. $p \mid a_i$ for all $i = 0, 1, \ldots, n-1$
2. $p \nmid a_n$ (leading coefficient)
3. $p^2 \nmid a_0$ (constant term)

**직관**: "대부분의 계수가 $p$로 나누어지지만, 첫 항과 마지막 항은 특별함"

**예시**: $f(x) = x^3 + 2x + 2$ over $\mathbb{Q}$
- $p = 2$
- $2 \mid 2$, $2 \mid 2$ (coefficients of $x^0, x^1$)
- $2 \nmid 1$ (leading coefficient)
- $2^2 = 4 \nmid 2$ (constant term)
- 따라서 $f(x)$ is irreducible over $\mathbb{Q}$ 
자세한 내용은 [[Eisenstein Criterion]] 참조

### 3. Reduction Modulo $p$

**정리**: $f(x) \in \mathbb{Z}[x]$ primitive^[원시]

Prime $p$에 대해 $\bar{f}(x) \in \mathbb{F}_p[x]$ (reduction mod $p$)가 irreducible이고 $\deg(\bar{f}) = \deg(f)$이면:

$$f(x) \text{ is irreducible over } \mathbb{Q}$$

**주의**: 
- 역은 성립하지 않음!
- $\deg(\bar{f}) = \deg(f)$ 조건 필수 (leading coefficient $\not\equiv 0 \pmod{p}$)

**예시**: $f(x) = x^2 + x + 1$ over $\mathbb{Q}$
- Reduce mod 2: $\bar{f}(x) = x^2 + x + 1 \in \mathbb{F}_2[x]$
- Check in $\mathbb{F}_2 = \{0, 1\}$:
  - $\bar{f}(0) = 1 \neq 0$
  - $\bar{f}(1) = 1 + 1 + 1 = 1 \neq 0$
- No roots in $\mathbb{F}_2$, degree 2 → irreducible
- 따라서 $f(x)$ irreducible over $\mathbb{Q}$ 
### 4. Rational Root Test (Contrapositive)

**활용**: $f(x) \in \mathbb{Z}[x]$가 rational roots를 갖지 않으면

**Degree $\leq 3$**: Irreducible over $\mathbb{Q}$ 
**Degree $\geq 4$**: 추가 테스트 필요

자세한 내용은 [[Rational Root Theorem]] 참조

## Irreducibility over Different Fields

**정리**: Field extension^[체 확대] $K \subseteq F$

$$f(x) \text{ irreducible over } F \quad \Rightarrow \quad f(x) \text{ irreducible over } K$$

**역은 성립하지 않음**!

**예시**: $x^2 - 2$
- Irreducible over $\mathbb{Q}$ - Reducible over $\mathbb{R}$: $x^2 - 2 = (x - \sqrt{2})(x + \sqrt{2})$ ✗

**일반 원칙**: 더 큰 field에서는 더 많이 분해 가능

## Unique Factorization

**정리**: Field $k$, polynomial $f(x) \in k[x]$ (nonconstant)

$$f(x) = c \prod_{i=1}^{r} p_i(x)^{e_i}$$

where:
- $c \in k^\times$ (unit)
- $p_i(x)$ irreducible over $k$, monic
- Factorization은 순서를 제외하고 유일

**Monic factorization**: $c = 1$로 normalize 가능 (leading coefficient 조정)

---

# <span class="header-examples">Examples</span>

## Example 1: Linear Polynomials (Always Irreducible)

### Over $\mathbb{Q}$

$$f(x) = 3x + 5$$

**Irreducible**  (degree 1)

### Over $\mathbb{R}$

$$f(x) = -2x + 7$$

**Irreducible**  (degree 1)

**일반 규칙**: Degree 1은 항상 irreducible

## Example 2: Quadratic Polynomials

### Over $\mathbb{Q}$

**(a)** $f(x) = x^2 - 2$

**Test**: Rational roots? $\pm 1, \pm 2$

$$f(1) = -1, \quad f(-1) = -1, \quad f(2) = 2, \quad f(-2) = 2$$

No rational roots → **Irreducible over $\mathbb{Q}$** 
**(b)** $f(x) = x^2 - 4$

$$f(x) = (x - 2)(x + 2)$$

**Reducible over $\mathbb{Q}$** ✗

### Over $\mathbb{R}$

**(a)** $f(x) = x^2 + 1$

No real roots → **Irreducible over $\mathbb{R}$** 
**(b)** $f(x) = x^2 - 2$

$$f(x) = (x - \sqrt{2})(x + \sqrt{2})$$

**Reducible over $\mathbb{R}$** ✗

### Over $\mathbb{C}$

**(a)** $f(x) = x^2 + 1$

$$f(x) = (x - i)(x + i)$$

**Reducible over $\mathbb{C}$** ✗

**일반**: 모든 degree $\geq 2$ polynomial은 $\mathbb{C}$에서 reducible (Fundamental Theorem of Algebra)

## Example 3: Eisenstein's Criterion

### (a) $f(x) = x^4 + 10x^3 + 5$ over $\mathbb{Q}$

**Apply Eisenstein** with $p = 5$:
- $5 \mid 10$, $5 \mid 5$ (coefficients of $x^3, x^0$)
- $5 \nmid 1$ (leading coefficient)
- $5^2 = 25 \nmid 5$ (constant term)

**Irreducible over $\mathbb{Q}$** 
### (b) Cyclotomic Polynomial $\Phi_p(x) = 1 + x + x^2 + \cdots + x^{p-1}$

$$\Phi_p(x) = \frac{x^p - 1}{x - 1}$$

**Trick**: Substitute $x \to x + 1$

$$\Phi_p(x + 1) = \frac{(x+1)^p - 1}{x} = x^{p-1} + \binom{p}{1}x^{p-2} + \cdots + \binom{p}{p-1}$$

**Apply Eisenstein** with $p$:
- $p \mid \binom{p}{k}$ for $1 \leq k \leq p-1$
- $p \nmid 1$ (leading)
- $p^2 \nmid p$ (constant)

**$\Phi_p(x+1)$ irreducible** → **$\Phi_p(x)$ irreducible** 
자세한 내용은 [[Cyclotomic Polynomial]] 참조

## Example 4: Reduction Modulo $p$

### $f(x) = x^4 + x + 1$ over $\mathbb{Q}$

**Method**: Reduce mod 2

$$\bar{f}(x) = x^4 + x + 1 \in \mathbb{F}_2[x]$$

**Check irreducibility in $\mathbb{F}_2[x]$**:

**Roots**: $\mathbb{F}_2 = \{0, 1\}$
- $\bar{f}(0) = 1 \neq 0$
- $\bar{f}(1) = 1 + 1 + 1 = 1 \neq 0$

No linear factors 
**Quadratic factors**: $\mathbb{F}_2[x]$의 irreducible quadratic는 $x^2 + x + 1$만

$$(x^2 + x + 1)^2 = x^4 + x^2 + 1 \neq x^4 + x + 1$$

$$(x^2 + x + 1) \cdot (\text{other deg 2}) = ?$$

계산하면 $x^4 + x + 1$로 분해 안됨

**$\bar{f}(x)$ irreducible over $\mathbb{F}_2$** → **$f(x)$ irreducible over $\mathbb{Q}$** 
## Example 5: Degree 4 with No Roots but Reducible

### Over $\mathbb{Q}$

$$f(x) = (x^2 + 1)(x^2 + 2) = x^4 + 3x^2 + 2$$

**Roots**: $\pm i, \pm i\sqrt{2}$ (모두 complex)

**No rational roots** but **reducible over $\mathbb{Q}$** ✗

**교훈**: Degree $\geq 4$에서 "no roots" $\not\Rightarrow$ "irreducible"

## Example 6: Over Finite Fields

### $\mathbb{F}_2[x]$

**Irreducible polynomials of low degree**:

**Degree 1**: $x$, $x + 1$ (2개)

**Degree 2**: $x^2 + x + 1$ (1개)
- $x^2 = x \cdot x$ (reducible)
- $x^2 + 1 = (x+1)^2$ (reducible over $\mathbb{F}_2$)
- $x^2 + x = x(x+1)$ (reducible)

**Degree 3**: $x^3 + x + 1$, $x^3 + x^2 + 1$ (2개)

**개수 공식**: 

$$N_q(n) = \frac{1}{n} \sum_{d \mid n} \mu(d) q^{n/d}$$

where $\mu$ is Möbius function

자세한 내용은 [[Finite Field]] 참조

## Example 7: $x^p - a$ (Irreducibility Test)

### Over $\mathbb{Q}$

$p$ prime, $a \in \mathbb{Z}$ square-free

**Eisenstein criterion** with $p$ (if $p \mid a$):
- $f(x) = x^p - a$
- $p \mid (-a)$ but $p^2 \nmid a$ (square-free 조건)
- $p \nmid 1$

**Irreducible over $\mathbb{Q}$** 
**예시**: $x^5 - 2$, $x^7 - 3$ all irreducible over $\mathbb{Q}$

## Example 8: Splitting Field Construction

### $f(x) = x^2 + 1$ over $\mathbb{R}$

**Irreducible over $\mathbb{R}$** 
**Root**: $i \in \mathbb{C}$ where $i^2 = -1$

**Splitting field**: $\mathbb{R}(i) = \mathbb{C}$

$$f(x) = (x - i)(x + i)$$ over $\mathbb{C}$

자세한 내용은 [[Splitting Field]], [[Extension Field]] 참조

---

# <span class="header-properties">Properties</span>

## Irreducibility and Roots

**정리**: Field $k$, $f(x) \in k[x]$ with $\deg(f) = 2$ or $3$

$$f(x) \text{ irreducible over } k \quad \Leftrightarrow \quad f \text{ has no roots in } k$$

**증명**: Irreducible이면 linear factor 없음 $\Leftrightarrow$ no roots

**일반화**: Degree $\geq 4$에서는 성립하지 않음

## Maximal Ideal Characterization

**정리**: Field $k$, polynomial $p(x) \in k[x]$ (nonconstant)

$$p(x) \text{ irreducible} \quad \Leftrightarrow \quad \langle p(x) \rangle \text{ is maximal ideal}$$

**결과**: $k[x] / \langle p(x) \rangle$ is a field

**예시**: 
- $\mathbb{R}[x] / \langle x^2 + 1 \rangle \cong \mathbb{C}$
- $\mathbb{Q}[x] / \langle x^2 - 2 \rangle \cong \mathbb{Q}(\sqrt{2})$

자세한 내용은 [[Maximal Ideal]], [[Quotient Ring]] 참조

## Minimal Polynomial

**정의**: Field extension $F/K$, $\alpha \in F$ algebraic^[대수적]

**Minimal polynomial**^[최소 다항식] of $\alpha$ over $K$:
- Monic^[최고차 계수가 1]
- $f(\alpha) = 0$
- **Irreducible over $K$**
- Smallest degree

**유일성**: Minimal polynomial은 유일

**성질**: $g(\alpha) = 0$ for $g \in K[x]$ $\Leftrightarrow$ $m_\alpha(x) \mid g(x)$

자세한 내용은 [[Minimal Polynomial]] 참조

## Degree of Extension

**정리**: $K \subseteq K(\alpha)$, $\alpha$ algebraic over $K$

$$[K(\alpha) : K] = \deg(m_\alpha)$$

where $m_\alpha$ is minimal polynomial of $\alpha$ over $K$

**예시**: 
- $[\mathbb{Q}(\sqrt{2}) : \mathbb{Q}] = 2$ (minimal poly: $x^2 - 2$)
- $[\mathbb{Q}(\sqrt[3]{2}) : \mathbb{Q}] = 3$ (minimal poly: $x^3 - 2$)

## Factorization in Extension Fields

**정리**: $f(x) \in K[x]$ irreducible, $\alpha$ root of $f$ in extension $F$

$$f(x) = (x - \alpha) g(x)$$ in $F[x]$

where $g(x) \in F[x]$

**일반**: $f(x)$는 extension field에서 더 많이 분해될 수 있음

## Compositeness Test

**정리**: $f(x) = g(h(x))$ with $\deg(g), \deg(h) > 1$

$$\Rightarrow \quad f(x) \text{ is reducible}$$

**예시**: $f(x) = x^4 + 2x^2 + 1 = (x^2)^2 + 2(x^2) + 1 = (x^2 + 1)^2$

Composite → Reducible 
## Associates

**정의**: $f, g \in k[x]$ are **associates**^[동반] $\Leftrightarrow$

$$f(x) = c \cdot g(x)$$ 

for some $c \in k^\times$ (nonzero constant)

**Monic normalization**: 각 associate class는 unique monic representative

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Irreducible polynomial = "소수 다항식"**

**핵심 아이디어**:
- 정수의 소수 ↔ 다항식의 기약 다항식
- 소인수분해 ↔ 기약 인수분해
- Fundamental Theorem of Arithmetic ↔ Unique factorization in $k[x]$

**기하학적**:
- Irreducible polynomial = 기하학적으로 "단순한" algebraic variety
- Factorization = variety를 components로 분해

## 응용 분야

### 1. Field Extensions^[체 확대]

**Construction**: $K[x] / \langle p(x) \rangle$ (where $p$ irreducible)

**결과**: Algebraic extension of $K$

**예시**:
- $\mathbb{C} = \mathbb{R}[x] / \langle x^2 + 1 \rangle$
- $\mathbb{Q}(\sqrt{2}) \cong \mathbb{Q}[x] / \langle x^2 - 2 \rangle$
- $\mathbb{F}_{p^n} \cong \mathbb{F}_p[x] / \langle p(x) \rangle$ (degree $n$ irreducible)

자세한 내용은 [[Extension Field]] 참조

### 2. Galois Theory^[갈루아 이론]

**Splitting field**: Irreducible polynomial의 모든 roots 포함

**Galois group**: Automorphisms of splitting field

**응용**: Solvability by radicals

자세한 내용은 [[Galois Theory]] 참조

### 3. Algebraic Geometry^[대수기하학]

**Irreducible variety**: $I = \langle f(x) \rangle$ where $f$ irreducible

**Decomposition**: Variety를 irreducible components로 분해

### 4. Cryptography^[암호학]

**AES**: $\mathbb{F}_{2^8} = \mathbb{F}_2[x] / \langle x^8 + x^4 + x^3 + x + 1 \rangle$

**Finite field arithmetic**: Irreducible polynomial을 modulus로 사용

### 5. Coding Theory^[부호 이론]

**BCH codes**: Minimal polynomials of elements in finite fields

**CRC**: Polynomial division for error detection

## Testing Irreducibility: Strategy

**순서대로 시도**:

1. **Degree 1**: Always irreducible 
2. **Degree 2, 3**: 
   - Check for roots (Rational Root Theorem for $\mathbb{Q}$)
   - No roots → irreducible

3. **Eisenstein's Criterion**: 
   - Try various primes $p$
   - Try substitution $x \to x + a$

4. **Reduction mod $p$**:
   - Reduce to finite field
   - Test in smaller field

5. **Compositeness check**:
   - $f(x) = g(h(x))$? 
   - Polynomial substitution

6. **Direct factorization** (degree $\leq 4$):
   - Try all possible factorizations
   - For $\mathbb{Q}[x]$: only finitely many possibilities (Rational Root)

7. **Computer algebra systems**: Maple, Mathematica, Sage

## Common Irreducible Families

### 1. $x^n - a$ (Eisenstein)

$p$ prime, $a = p^k b$ with $\gcd(p, b) = 1$

**Irreducible over $\mathbb{Q}$** if $p^{k+1} \nmid a$ and $n = p$

### 2. Cyclotomic Polynomials

$$\Phi_n(x) = \prod_{\substack{1 \leq k \leq n \\ \gcd(k, n) = 1}} (x - e^{2\pi i k/n})$$

**Always irreducible over $\mathbb{Q}$**

### 3. $x^2 + 1$

- Irreducible over $\mathbb{R}$
- Reducible over $\mathbb{C}$

### 4. $x^p - x - a$ over $\mathbb{F}_p$

**Artin-Schreier polynomials**: Irreducible if $a \neq 0$

## Historical Context

**개발**:
- **Gauss** (1801): Cyclotomic polynomials, factorization in $\mathbb{Z}[x]$
- **Eisenstein** (1850): Eisenstein's criterion
- **Kronecker** (1882): Factorization algorithms
- **van der Waerden** (1930s): Modern abstract approach

**현대적 관점**: Commutative algebra, algebraic geometry

## Computational Complexity

**문제**: $f(x) \in \mathbb{Z}[x]$ irreducible인지 판정

**알고리즘**:
- **Berlekamp** (1967): Finite fields (polynomial time)
- **Zassenhaus** (1969): $\mathbb{Z}[x]$ (exponential worst case)
- **LLL** (1982): Polynomial time for $\mathbb{Z}[x]$

**실용**: Modern computer algebra systems는 빠르게 판정

## Connection to Prime Ideals

**정리**: Field $k$, $k[x]$ is PID

$$\text{Irreducible polynomials} \leftrightarrow \text{Nonzero prime ideals}$$

**1-1 correspondence** (up to associates)

$$\langle p(x) \rangle \text{ prime} \Leftrightarrow \langle p(x) \rangle \text{ maximal} \Leftrightarrow p(x) \text{ irreducible}$$

## Common Pitfalls

1. **"No roots" $\not\Rightarrow$ "Irreducible" (degree $\geq 4$)**
   - $x^4 + 2x^2 + 1$ over $\mathbb{Q}$: no rational roots but reducible

2. **Irreducibility depends on field**
   - $x^2 - 2$: irreducible over $\mathbb{Q}$, reducible over $\mathbb{R}$

3. **Units in polynomial ring**
   - $k[x]^\times = k \setminus \{0\}$ (nonzero constants)
   - $(2x + 1)$은 $\mathbb{Q}[x]$에서 $(x + 1/2)$와 associate

4. **Eisenstein requires checking $p^2 \nmid a_0$**
   - $x^2 + 4$ with $p = 2$: fails ($4 = 2^2$)

5. **Reduction mod $p$ only gives sufficient condition**
   - $\bar{f}$ reducible이어도 $f$는 irreducible 가능

## Comparison Table

| Field | $x^2 - 2$ | $x^2 + 1$ | $x^4 + 2x^2 + 1$ | $x^3 - 2$ |
|-------|-----------|-----------|------------------|-----------|
| $\mathbb{Q}$ | Irr. | Irr. | Red. | Irr. |
| $\mathbb{R}$ | Red. | Irr. | Red. | Irr. |
| $\mathbb{C}$ | Red. | Red. | Red. | Red. |
| $\mathbb{F}_3$ | Red. | Red. | Red. | Irr. |

**Irr.** = Irreducible, **Red.** = Reducible

