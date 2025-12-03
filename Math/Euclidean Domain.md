# <span class="header-prerequisite">Prerequisite</span>

- [[Integral Domain]]
- [[Principal Ideal Domain]]
- [[Unique Factorization Domain]]
- [[Division Algorithm]]
- [[Greatest Common Divisor]]

# <span class="header-reference">Reference</span>

- Dummit & Foote, *Abstract Algebra*, Chapter 8
- Atiyah & MacDonald, *Introduction to Commutative Algebra*
- Jacobson, *Basic Algebra I*

---

# <span class="header-definition">Definition</span>

## Euclidean Domain^[유클리드 정역]

**Euclidean domain**^[유클리드 정역]은 integral domain^[정역] $R$로, **Euclidean function**^[유클리드 함수] (또는 **norm**^[노름])이 존재하는 것:

$$\phi: R \setminus \{0\} \to \mathbb{Z}_{\geq 0}$$

다음 성질을 만족:

**Division with remainder**^[나머지가 있는 나눗셈]: 모든 $a, b \in R$ ($b \neq 0$)에 대해, $q, r \in R$이 존재하여:

$$a = bq + r$$

where $r = 0$ or $\phi(r) < \phi(b)$

## Key Components

### 1. Euclidean Function

**목적**: "크기"의 개념 제공

**성질**:
- $\phi(a) \geq 0$ for all $a \neq 0$
- Division이 가능하도록 "감소" 보장

**비고**: Euclidean function은 **유일하지 않음**

### 2. Division Algorithm

$$a = bq + r, \quad \phi(r) < \phi(b)$$

**의미**: $b$로 나눈 나머지 $r$이 $b$보다 "작음"

### 3. Quotient and Remainder

- **Quotient**^[몫]: $q$
- **Remainder**^[나머지]: $r$
- $q$와 $r$은 유일하지 않을 수 있음

---

# <span class="header-properties">Properties</span>

## Fundamental Theorem

**정리**: Every Euclidean domain is a PID^[주 아이디얼 정역]

**증명 스케치**:

1. $I \subseteq R$ be nonzero ideal
2. Choose $b \in I \setminus \{0\}$ with **minimal** $\phi(b)$
3. Claim: $I = (b)$
   - $(\subseteq)$: For any $a \in I$, divide: $a = bq + r$
   - $r = a - bq \in I$ (since $a, bq \in I$)
   - If $r \neq 0$: $\phi(r) < \phi(b)$ contradicts minimality of $\phi(b)$
   - Thus $r = 0$, so $a = bq \in (b)$

**결론**: $I = (b)$ is principal

## Hierarchy Theorem

$$\text{Euclidean Domain} \Rightarrow \text{PID} \Rightarrow \text{UFD}$$

**중요**: 
- 모든 PID가 Euclidean인 것은 **아님**
- 모든 UFD가 PID인 것은 **아님**

## GCD and Bezout's Identity

**정리**: Euclidean domain에서 GCD가 존재하고, **Bezout's identity**^[베주 항등식]가 성립:

$$\gcd(a, b) = d \quad \Rightarrow \quad \exists x, y \in R: \quad ax + by = d$$

**증명**: Euclidean algorithm 적용

## Euclidean Algorithm

**알고리즘**: $\gcd(a, b)$ 계산

1. $a = bq_1 + r_1$, $\phi(r_1) < \phi(b)$
2. $b = r_1 q_2 + r_2$, $\phi(r_2) < \phi(r_1)$
3. $r_1 = r_2 q_3 + r_3$, $\phi(r_3) < \phi(r_2)$
4. Continue until $r_n = 0$

**결과**: $\gcd(a, b) = r_{n-1}$ (last nonzero remainder)

**시간 복잡도**: $O(\log \min(a, b))$ for $\mathbb{Z}$

## Irreducible = Prime

**정리**: Euclidean domain에서:

$$\text{Irreducible} \Leftrightarrow \text{Prime}$$

**이유**: Euclidean $\Rightarrow$ PID $\Rightarrow$ UFD

---

# <span class="header-examples">Examples</span>

## Example 1: The Integers $\mathbb{Z}$

**Euclidean function**: $\phi(n) = |n|$ (absolute value)

**Division algorithm**: $a = bq + r$, $0 \leq r < |b|$

**Classic Euclidean domain**

## Example 2: Polynomial Ring $F[x]$ over Field $F$

**Euclidean function**: $\phi(f) = \deg(f)$ (degree)

**Division algorithm**: Polynomial long division

$$f(x) = g(x) q(x) + r(x), \quad \deg(r) < \deg(g)$$

**응용**: Factor Theorem, Remainder Theorem

## Example 3: Gaussian Integers $\mathbb{Z}[i]$

$$\mathbb{Z}[i] = \{a + bi : a, b \in \mathbb{Z}\}$$

**Euclidean function**: $\phi(a + bi) = a^2 + b^2$ (norm)

**Division algorithm**: Use complex division and rounding

**응용**: Fermat's two-square theorem

## Example 4: Any Field $F$

**모든 field는 Euclidean domain**

**Euclidean function**: $\phi(a) = 1$ for all $a \neq 0$

**Division**: $a = b \cdot (ab^{-1}) + 0$

**자명한 경우**

## Example 5: $\mathbb{Z}[\omega]$ where $\omega = e^{2\pi i/3}$

$$\mathbb{Z}[\omega] = \{a + b\omega : a, b \in \mathbb{Z}\}$$

**Euclidean function**: $\phi(a + b\omega) = |a + b\omega|^2 = a^2 - ab + b^2$

**Also known as**: Eisenstein integers

**응용**: Cubic reciprocity

## Example 6: $\mathbb{Z}[\sqrt{-2}]$

$$\mathbb{Z}[\sqrt{-2}] = \{a + b\sqrt{-2} : a, b \in \mathbb{Z}\}$$

**Euclidean function**: $\phi(a + b\sqrt{-2}) = a^2 + 2b^2$

**증명**: Similar to Gaussian integers

## Example 7: $\mathbb{Z}[\sqrt{2}]$

$$\mathbb{Z}[\sqrt{2}] = \{a + b\sqrt{2} : a, b \in \mathbb{Z}\}$$

**Euclidean function**: $\phi(a + b\sqrt{2}) = |a^2 - 2b^2|$

**주의**: Norm can be negative, take absolute value

## Example 8: $\mathbb{Q}[x, y]/(xy)$ is NOT Euclidean

**이유**: Not even an integral domain (zero divisors)

$xy = 0$ in quotient

**대조**: Euclidean domain은 반드시 integral domain

---

# <span class="header-properties">Key Properties</span>

## 1. Principal Ideals

**Every ideal is principal**

$$I = (a) \text{ for some } a \in R$$

Follows from Euclidean $\Rightarrow$ PID

## 2. GCD Always Exists

**Greatest common divisor**: For any $a, b \in R$, $\gcd(a, b)$ exists

**Computation**: Euclidean algorithm

## 3. Factorization

**Unique factorization**: Every nonzero non-unit factors uniquely into irreducibles

Follows from PID $\Rightarrow$ UFD

## 4. Bezout's Identity

$$\gcd(a, b) = ax + by$$

**Extended Euclidean algorithm** computes $x, y$

## 5. Prime Ideals

**Maximal ideals = Nonzero prime ideals**

In Euclidean domain (which is PID):

$$(p) \text{ maximal} \Leftrightarrow p \text{ irreducible} \Leftrightarrow p \text{ prime}$$

## 6. Noetherian

**Every Euclidean domain is Noetherian**

Follows from being PID

## 7. Simplicity of Computations

**Euclidean algorithm provides explicit computations**
- GCD computation
- Bezout coefficients
- Factorization algorithms

---

# <span class="header-examples">Applications</span>

## 1. Number Theory

**Diophantine equations**: $ax + by = c$

Solvable $\Leftrightarrow$ $\gcd(a, b) | c$

**Bezout's identity** provides solutions

## 2. Cryptography

**RSA algorithm**: Uses Euclidean algorithm in $\mathbb{Z}$

**Extended Euclidean algorithm**: Compute modular inverses

$$\gcd(e, \phi(n)) = 1 \quad \Rightarrow \quad ed \equiv 1 \pmod{\phi(n)}$$

## 3. Polynomial Factorization

**Factor polynomials** over $F[x]$

**Euclidean algorithm**: Compute $\gcd$ of polynomials

**응용**: Partial fractions, root finding

## 4. Linear Algebra

**Smith normal form**: Uses Euclidean algorithm

**Applications**: 
- Module structure
- Linear systems over PIDs

## 5. Algebraic Number Theory

**Quadratic integers**: $\mathbb{Z}[\sqrt{d}]$

**Determine when Euclidean**: Classify by $d$

**Known Euclidean**: $d \in \{-11, -7, -3, -2, -1, 2, 3, 5, 6, 7, \ldots\}$

자세한 내용은 [[Quadratic Integer Ring]] 참조

## 6. Coding Theory

**Error correction codes**: BCH codes use $F[x]$

**Euclidean algorithm**: Decode errors

## 7. Computer Algebra

**Symbolic computation**: GCD of polynomials

**Groebner bases**: Generalization to polynomial rings

---

# <span class="header-examples">Non-Examples and Counterexamples</span>

## Non-Example 1: $\mathbb{Z}[\sqrt{-5}]$ is NOT Euclidean

**이유**: Not even a UFD

**반례**: $6 = 2 \cdot 3 = (1 + \sqrt{-5})(1 - \sqrt{-5})$

Two distinct factorizations

## Non-Example 2: $\mathbb{Z}[x]$ is NOT Euclidean

**이유**: Not a PID (though it is a UFD)

**반례 ideal**: $(2, x)$ is not principal

## Non-Example 3: Some PIDs are NOT Euclidean

**Example**: $\mathbb{Z}\left[\frac{1 + \sqrt{-19}}{2}\right]$

**증명됨**: PID이지만 Euclidean이 아님 (hard to prove)

## Non-Example 4: $\mathbb{Z}[\sqrt{10}]$ is NOT Euclidean

**이유**: Not a UFD

**반례**: Norm $a^2 - 10b^2$ doesn't satisfy Euclidean property

---

# <span class="header-theorem">Important Theorems</span>

## Theorem 1: Euclidean Implies PID

**Statement**: Every Euclidean domain is a PID

**증명**: Via minimality of Euclidean function

## Theorem 2: Classification of Euclidean Quadratic Rings

**Statement**: $\mathbb{Z}[\sqrt{d}]$ is Euclidean for:

$$d \in \{2, 3, 5, 6, 7, 11, 13, 17, 19, 21, 29, 33, 37, 41, 57, 73\}$$

(real quadratic case, incomplete list)

**Complex case**: $\mathbb{Z}[\sqrt{d}]$ for $d < 0$:

$$d \in \{-1, -2, -3, -7, -11\}$$

완전한 분류는 어려움

## Theorem 3: Motzkin's Theorem

**Statement**: There exists a PID that is NOT a Euclidean domain

**Example**: $\mathbb{Z}\left[\frac{1 + \sqrt{-19}}{2}\right]$

## Theorem 4: Non-uniqueness of Euclidean Function

**Statement**: Euclidean function이 존재하면, 무수히 많이 존재

**예**: $\mathbb{Z}$에서 $\phi(n) = |n|$, $\phi(n) = n^2$, etc.

---

# <span class="header-remark">Common Pitfalls</span>

## 1. PID ≠ Euclidean

✗ "모든 PID는 Euclidean"?

✓ 대부분의 PID는 Euclidean이지만, 예외 존재

**반례**: $\mathbb{Z}\left[\frac{1 + \sqrt{-19}}{2}\right]$

## 2. Euclidean Function Uniqueness

✗ "Euclidean function은 유일"?

✓ 무수히 많은 Euclidean functions 가능

**예**: $\mathbb{Z}$에서 $|n|$, $n^2$, $|n| + 1$, etc.

## 3. Quotient and Remainder Uniqueness

✗ "몫과 나머지는 유일"?

✓ $\mathbb{Z}$에서는 유일 (with $0 \leq r < |b|$)

✓ 일반적으로는 **유일하지 않음**

**예**: Gaussian integers

## 4. Norm Must Be Multiplicative

✗ "Euclidean function은 multiplicative"?

✓ **필요 없음!** Division property만 필요

## 5. $\mathbb{Z}[\sqrt{d}]$ Always Euclidean?

✗ "모든 $\mathbb{Z}[\sqrt{d}]$는 Euclidean"?

✓ 특정 $d$에 대해서만!

**Counter**: $\mathbb{Z}[\sqrt{-5}]$, $\mathbb{Z}[\sqrt{10}]$ not even UFD

## 6. Division Algorithm Always Computable

✗ "Euclidean algorithm은 항상 효율적"?

✓ 계산 복잡도는 ring에 따라 다름

$\mathbb{Z}$: $O(\log n)$, 다른 rings: 더 느릴 수 있음

---

# <span class="header-examples">Comparison Table</span>

## Property Comparison

| Property | Field | Euclidean | PID | UFD | Domain |
|----------|-------|-----------|-----|-----|--------|
| Division algorithm | ✓ | ✓ | ✗ | ✗ | ✗ |
| Every ideal principal | ✓ | ✓ | ✓ | ✗ | ✗ |
| Unique factorization | ✓ | ✓ | ✓ | ✓ | ✗ |
| GCD exists | ✓ | ✓ | ✓ | ✓ | ✗ |
| Bezout's identity | ✓ | ✓ | ✓ | ✗ | ✗ |
| Irred = Prime | ✓ | ✓ | ✓ | ✓ | ✗ |

## Examples by Type

| Ring | Euclidean? | PID? | UFD? | Domain? |
|------|------------|------|------|---------|
| $\mathbb{Z}$ | ✓ | ✓ | ✓ | ✓ |
| $F[x]$ | ✓ | ✓ | ✓ | ✓ |
| $\mathbb{Z}[i]$ | ✓ | ✓ | ✓ | ✓ |
| $\mathbb{Z}[\omega]$ | ✓ | ✓ | ✓ | ✓ |
| $\mathbb{Z}\left[\frac{1+\sqrt{-19}}{2}\right]$ | ✗ | ✓ | ✓ | ✓ |
| $\mathbb{Z}[x]$ | ✗ | ✗ | ✓ | ✓ |
| $\mathbb{Z}[\sqrt{-5}]$ | ✗ | ✗ | ✗ | ✓ |
| $\mathbb{Z}/6\mathbb{Z}$ | ✗ | ✗ | ✗ | ✗ |

---

# <span class="header-remark">Historical Context</span>

**Euclid** (c. 300 BCE):
- *Elements*, Book VII: Euclidean algorithm for $\mathbb{Z}$
- First systematic algorithm in mathematics
- GCD computation

**Carl Friedrich Gauss** (1777-1855):
- *Disquisitiones Arithmeticae* (1801)
- Gaussian integers $\mathbb{Z}[i]$
- Generalization to quadratic forms

**Ernst Kummer** (1810-1893):
- Cyclotomic integers
- Failed attempt at Fermat's Last Theorem
- Led to development of ideal theory

**Richard Dedekind** (1831-1916):
- Abstract ideal theory
- Replaced Euclidean property with ideal-theoretic approach
- Dedekind domains

**20th Century**:
- Classification of Euclidean domains
- Motzkin (1949): First example of non-Euclidean PID
- Computer algebra: Efficient algorithms

---

# <span class="header-remark">Related Concepts</span>

## Ring Theory

- [[Integral Domain]]: Base structure
- [[Principal Ideal Domain]]: Euclidean $\Rightarrow$ PID
- [[Unique Factorization Domain]]: PID $\Rightarrow$ UFD
- [[Field]]: Every field is Euclidean
- [[Polynomial Ring]]: $F[x]$ is Euclidean

## Number Theory

- [[Gaussian Integer]]: $\mathbb{Z}[i]$
- [[Quadratic Integer Ring]]: $\mathbb{Z}[\sqrt{d}]$
- [[Algebraic Integer]]: Generalizations
- [[Euclidean Algorithm]]: Computational tool
- [[Greatest Common Divisor]]: Existence and computation

## Ideal Theory

- [[Principal Ideal]]: Every ideal in Euclidean domain
- [[Prime Ideal]]: Generated by primes
- [[Maximal Ideal]]: In PID, prime = maximal (nonzero)
- [[Dedekind Domain]]: Generalization of PID

## Algorithms

- [[Euclidean Algorithm]]: GCD computation
- [[Extended Euclidean Algorithm]]: Bezout coefficients
- [[Chinese Remainder Theorem]]: Applications
- [[RSA Cryptosystem]]: Modular arithmetic

## Advanced Topics

- [[Dedekind Domain]]: Weaker than PID
- [[Discrete Valuation Ring]]: Local PIDs
- [[Class Number]]: Measures failure of being PID
- [[Ideal Class Group]]: When not PID

