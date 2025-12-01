# <span class="header-prerequisite">Prerequisite</span>
- [[Polynomial Ring]]
- [[Ring]]
- [[Field]]
- [[Degree of Polynomial]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Division Algorithm for Polynomials^[다항식 나눗셈 알고리즘]

**정리**: $F$가 field이고 $f(x), g(x) \in F[x]$에서 $g(x) \neq 0$이면

$$\exists! \, q(x), r(x) \in F[x]: \quad f(x) = q(x) \cdot g(x) + r(x)$$

where $\deg(r) < \deg(g)$ or $r(x) = 0$

**용어**:
- $f(x)$: **dividend**^[피제수] (나눠지는 다항식)
- $g(x)$: **divisor**^[제수] (나누는 다항식)
- $q(x)$: **quotient**^[몫]
- $r(x)$: **remainder**^[나머지]

**표기**: 

$$f(x) = q(x) \cdot g(x) + r(x)$$

또는

$$f(x) \equiv r(x) \pmod{g(x)}$$

## Key Conditions

### 1. Existence^[존재성]

주어진 $f, g$에 대해 $q, r$이 **존재**함

### 2. Uniqueness^[유일성]

$q, r$은 조건 $\deg(r) < \deg(g)$을 만족하는 한 **유일**함

### 3. Degree Condition

**핵심**: $\deg(r) < \deg(g)$ or $r = 0$

**의미**: 나머지의 차수는 제수보다 작아야 함

## Comparison with Integers

정수의 나눗셈 알고리즘과 유사:

$$a = qb + r, \quad 0 \leq r < |b|$$

다항식에서:

$$f(x) = q(x)g(x) + r(x), \quad \deg(r) < \deg(g)$$

**유사점**: "크기" (절댓값 vs 차수)로 나머지 제한

---

# <span class="header-proof">Proof</span>

## Existence Proof^[존재성 증명]

**Induction on $\deg(f)$**

**Base case**: $\deg(f) < \deg(g)$
- $q(x) = 0$, $r(x) = f(x)$ - $f(x) = 0 \cdot g(x) + f(x)$

**Inductive step**: $\deg(f) \geq \deg(g)$

Let:
- $f(x) = a_n x^n + \cdots + a_0$, $a_n \neq 0$ ($\deg(f) = n$)
- $g(x) = b_m x^m + \cdots + b_0$, $b_m \neq 0$ ($\deg(g) = m$)
- $n \geq m$

**구성**:

$$f_1(x) = f(x) - \frac{a_n}{b_m} x^{n-m} \cdot g(x)$$

**관찰**:
- $\deg(f_1) < \deg(f) = n$ (leading term이 소거됨)
- Induction hypothesis: $f_1(x) = q_1(x) g(x) + r(x)$ where $\deg(r) < \deg(g)$

**따라서**:

$$f(x) = f_1(x) + \frac{a_n}{b_m} x^{n-m} \cdot g(x) = q_1(x) g(x) + r(x) + \frac{a_n}{b_m} x^{n-m} \cdot g(x)$$

$$= \left( q_1(x) + \frac{a_n}{b_m} x^{n-m} \right) g(x) + r(x)$$

Let $q(x) = q_1(x) + \frac{a_n}{b_m} x^{n-m}$ 
## Uniqueness Proof^[유일성 증명]

**가정**: $f(x) = q_1(x) g(x) + r_1(x) = q_2(x) g(x) + r_2(x)$

where $\deg(r_1), \deg(r_2) < \deg(g)$

**빼기**:

$$0 = (q_1 - q_2) g + (r_1 - r_2)$$

$$\Rightarrow \quad (q_1 - q_2) g = r_2 - r_1$$

**Degree 비교**:

**LHS**: $\deg((q_1 - q_2)g) \geq \deg(g)$ (if $q_1 \neq q_2$)

**RHS**: $\deg(r_2 - r_1) < \deg(g)$ (since both $< \deg(g)$)

**모순!** Therefore $q_1 = q_2$ and $r_1 = r_2$ 
---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Division in Field

**중요**: Field $F$ 위에서만 일반적으로 성립!

**이유**: Leading coefficient $b_m$의 역원 $b_m^{-1}$ 필요

**반례** ($\mathbb{Z}[x]$):

$$f(x) = x^2, \quad g(x) = 2x$$

나눗셈 불가능 ($2^{-1} \notin \mathbb{Z}$)

### 2. Degree Properties

**정리**: $f(x) = q(x) g(x) + r(x)$일 때

**(a)** $\deg(f) = \deg(q) + \deg(g)$ (if $r = 0$ or $\deg(r) < \deg(g)$)

**(b)** $\deg(q) = \deg(f) - \deg(g)$ (if $f$ divides evenly or remainder small)

**(c)** $\deg(r) < \deg(g)$ or $r = 0$

### 3. Divisibility

**정의**: $g | f$ (in $F[x]$) $\Leftrightarrow$ $r(x) = 0$

$$f(x) = q(x) g(x)$$

**예**: $(x - a) | f(x) \Leftrightarrow f(a) = 0$ (Factor Theorem)

### 4. Euclidean Domain Property

**정의**: $F[x]$ is **Euclidean domain**^[유클리드 정역]

**Euclidean function**: $\phi(f) = \deg(f)$

**Property**: Division algorithm with remainder "smaller" than divisor

자세한 내용은 [[Euclidean Domain]] 참조

## Algorithm (Long Division)

**Input**: $f(x)$, $g(x)$ in $F[x]$, $g \neq 0$

**Output**: $q(x)$, $r(x)$ such that $f = qg + r$, $\deg(r) < \deg(g)$

**Procedure**:

1. Initialize $q(x) = 0$, $r(x) = f(x)$

2. While $\deg(r) \geq \deg(g)$:
   - Let $c = \frac{\text{leading coeff of } r}{\text{leading coeff of } g}$
   - Let $d = \deg(r) - \deg(g)$
   - Update: $q(x) \leftarrow q(x) + cx^d$
   - Update: $r(x) \leftarrow r(x) - cx^d \cdot g(x)$

3. Return $q(x)$, $r(x)$

**Complexity**: $O((\deg(f) - \deg(g) + 1) \cdot \deg(g))$ field operations

## Remainder Theorem

**정리**: $f(x) \in F[x]$를 $(x - a)$로 나눈 나머지는 $f(a)$

**증명**:

$$f(x) = q(x)(x - a) + r$$

where $\deg(r) = 0$ (constant) or $r = 0$

$x = a$ 대입:

$$f(a) = q(a) \cdot 0 + r = r$$

따라서 $r = f(a)$ 
자세한 내용은 [[Remainder Theorem]] 참조

## Factor Theorem

**정리**: $(x - a) | f(x)$ $\Leftrightarrow$ $f(a) = 0$

**증명**:

($\Rightarrow$) $(x - a) | f(x)$ $\Rightarrow$ $r = 0$ $\Rightarrow$ $f(a) = 0$ 
($\Leftarrow$) $f(a) = 0$ $\Rightarrow$ $r = f(a) = 0$ $\Rightarrow$ $(x - a) | f(x)$ 
자세한 내용은 [[Factor Theorem]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Simple Division

**Problem**: Divide $f(x) = x^3 + 2x^2 - x + 3$ by $g(x) = x - 1$ in $\mathbb{Q}[x]$

**Solution** (long division):

```
         x^2 + 3x + 2
      ________________
x - 1 | x^3 + 2x^2 - x + 3
        x^3 -  x^2
        ___________
             3x^2 - x
             3x^2 - 3x
             _________
                  2x + 3
                  2x - 2
                  ______
                      5
```

**결과**:

$$f(x) = (x^2 + 3x + 2)(x - 1) + 5$$

- $q(x) = x^2 + 3x + 2$
- $r(x) = 5$

**검증**: Remainder Theorem: $f(1) = 1 + 2 - 1 + 3 = 5$ 
## Example 2: Exact Division

**Problem**: Divide $f(x) = x^3 - 1$ by $g(x) = x - 1$ in $\mathbb{R}[x]$

**Solution**:

```
         x^2 + x + 1
      _______________
x - 1 | x^3 + 0x^2 + 0x - 1
        x^3 -  x^2
        ___________
                x^2 + 0x
                x^2 -  x
                ________
                       x - 1
                       x - 1
                       _____
                           0
```

**결과**:

$$x^3 - 1 = (x^2 + x + 1)(x - 1) + 0$$

- $q(x) = x^2 + x + 1$
- $r(x) = 0$ (exact division!)

**Factorization**: $x^3 - 1 = (x - 1)(x^2 + x + 1)$ 
## Example 3: Higher Degree Divisor

**Problem**: Divide $f(x) = x^4 + 3x^3 - x + 1$ by $g(x) = x^2 + 1$ in $\mathbb{R}[x]$

**Solution**:

```
         x^2 + 3x - 1
      __________________
x^2+1 | x^4 + 3x^3 + 0x^2 - x + 1
        x^4 +      0x^2 + x^2
        _______________________
              3x^3 - x^2 - x
              3x^3      + 3x
              ______________
                   -x^2 - 4x + 1
                   -x^2      - 1
                   _____________
                          -4x + 2
```

**결과**:

$$f(x) = (x^2 + 3x - 1)(x^2 + 1) + (-4x + 2)$$

- $q(x) = x^2 + 3x - 1$
- $r(x) = -4x + 2$
- $\deg(r) = 1 < 2 = \deg(g)$ 
## Example 4: Synthetic Division

**Problem**: Divide $f(x) = 2x^3 - 3x^2 + x - 5$ by $g(x) = x - 2$ in $\mathbb{Q}[x]$

**Synthetic Division** (special case for $(x - a)$):

```
  2 |  2  -3   1  -5
    |     4   2   6
    _______________
      2   1   3   1
```

**결과**:

$$f(x) = (2x^2 + x + 3)(x - 2) + 1$$

- $q(x) = 2x^2 + x + 3$
- $r = 1$

**검증**: $f(2) = 16 - 12 + 2 - 5 = 1$ 
## Example 5: Over $\mathbb{F}_p$

**Problem**: Divide $f(x) = x^3 + x + 1$ by $g(x) = x + 1$ in $\mathbb{F}_2[x]$

**Solution** (in $\mathbb{F}_2$: $1 + 1 = 0$):

```
         x^2 + x
      ____________
x + 1 | x^3 + 0x^2 + x + 1
        x^3 +  x^2
        ___________
               x^2 + x
               x^2 + x
               _______
                   0 + 1
```

**결과**:

$$f(x) = (x^2 + x)(x + 1) + 1$$

- $q(x) = x^2 + x$
- $r(x) = 1$

**검증**: $f(1) = 1 + 1 + 1 = 1$ in $\mathbb{F}_2$ 
## Example 6: Non-Example (Non-Field)

**Problem**: Divide $f(x) = x^2$ by $g(x) = 2x$ in $\mathbb{Z}[x]$

**Attempt**:

$$q(x) = \frac{x}{2}?$$

**문제**: $\frac{1}{2} \notin \mathbb{Z}$!

**결론**: Division algorithm이 $\mathbb{Z}[x]$에서 일반적으로 작동하지 않음 ✗

**주의**: Field가 아닌 ring 위에서는 제약!

## Example 7: GCD Computation

**Problem**: Find $\gcd(x^3 - 1, x^2 - 1)$ in $\mathbb{Q}[x]$

**Euclidean Algorithm**:

Step 1:

$$x^3 - 1 = (x)(x^2 - 1) + (x - 1)$$

Step 2:

$$x^2 - 1 = (x + 1)(x - 1) + 0$$

**결과**: $\gcd(x^3 - 1, x^2 - 1) = x - 1$ 
**검증**: 
- $x^3 - 1 = (x - 1)(x^2 + x + 1)$
- $x^2 - 1 = (x - 1)(x + 1)$

## Example 8: Polynomial Interpolation

**Problem**: $f(x)$를 $(x - 1)(x - 2)(x - 3)$로 나눈 나머지 형태

**나머지**: $r(x) = ax^2 + bx + c$ (차수 $< 3$)

$$f(x) = q(x)(x - 1)(x - 2)(x - 3) + r(x)$$

**응용**: Lagrange interpolation, Chinese Remainder Theorem

자세한 내용은 [[Polynomial Interpolation]] 참조

## Example 9: Multiple Remainders

**Problem**: $f(x) = x^{100}$를 $x^2 - 1$로 나눈 나머지

**Solution**:

$$x^{100} = q(x)(x^2 - 1) + r(x)$$

where $\deg(r) < 2$, so $r(x) = ax + b$

$x^2 = 1$ 대입: $x^{100} = r(x)$

- $x = 1$: $1 = a + b$
- $x = -1$: $1 = -a + b$

Solving: $a = 0$, $b = 1$

**결과**: $r(x) = 1$

$$x^{100} = q(x)(x^2 - 1) + 1$$

## Example 10: Over $\mathbb{C}$

**Problem**: Divide $f(x) = x^3 + 1$ by $g(x) = x - i$ in $\mathbb{C}[x]$

**Solution** (synthetic division):

```
  i |  1   0   0   1
    |      i  -1  -i
    ________________
      1   i  -1  1-i
```

**결과**:

$$x^3 + 1 = (x^2 + ix - 1)(x - i) + (1 - i)$$

**검증**: $f(i) = i^3 + 1 = -i + 1 = 1 - i$ 
---

# <span class="header-theorem">Theorem</span>

## Division Algorithm (Main Theorem)

**정리**: $F$ field, $f, g \in F[x]$, $g \neq 0$이면

$$\exists! \, q, r \in F[x]: \quad f = qg + r, \quad \deg(r) < \deg(g) \text{ or } r = 0$$

## Remainder Theorem

**정리**: $f(x) \in F[x]$를 $(x - a)$로 나눈 나머지는 $f(a)$

$$f(x) = q(x)(x - a) + f(a)$$

## Factor Theorem

**정리**: $a \in F$일 때

$$(x - a) | f(x) \quad \Leftrightarrow \quad f(a) = 0$$

**응용**: Root finding $\Leftrightarrow$ Factorization

## Polynomial Euclidean Algorithm

**정리**: $F[x]$에서 GCD는 Euclidean algorithm으로 계산 가능

$$\gcd(f, g) = \gcd(g, r)$$

where $f = qg + r$

**종료**: $\deg(r)$이 strictly decreasing

**결과**: $\gcd$ 존재하고 계산 가능 
자세한 내용은 [[Euclidean Algorithm for Polynomials]] 참조

## Bézout's Identity

**정리**: $d = \gcd(f, g)$이면

$$\exists u, v \in F[x]: \quad d = uf + vg$$

**증명**: Extended Euclidean Algorithm 
## Chinese Remainder Theorem

**정리**: $f_1, \ldots, f_k$ pairwise coprime이면

$$F[x] / (f_1 \cdots f_k) \cong F[x]/f_1 \times \cdots \times F[x]/f_k$$

**응용**: Polynomial interpolation

자세한 내용은 [[Chinese Remainder Theorem]] 참조

## Degree Formula

**정리**: $F$ integral domain, $f, g \in F[x]$ nonzero이면

$$\deg(fg) = \deg(f) + \deg(g)$$

**계**: $F[x]$ is integral domain if $F$ is

## Number of Roots

**정리**: $f(x) \in F[x]$ nonzero, $\deg(f) = n$이면

$f$는 at most $n$ roots in $F$ (counting multiplicity)

**증명**: Induction using Factor Theorem
- If $f(a) = 0$: $f(x) = (x - a)g(x)$, $\deg(g) = n - 1$
- Apply induction to $g$ 
---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Division Algorithm = "Long Division for Polynomials"**

### 메타포: 정수 나눗셈

**정수**: $17 = 5 \cdot 3 + 2$ (나머지 $< 5$)

**다항식**: $x^3 + 2x^2 - x + 3 = (x^2 + 3x + 2)(x - 1) + 5$

**나머지 조건**:
- 정수: $0 \leq r < |b|$
- 다항식: $\deg(r) < \deg(g)$ or $r = 0$

### 왜 Field가 필요한가?

**핵심**: Leading coefficient의 역원 필요!

**과정**: $f(x) = a_n x^n + \cdots$를 $g(x) = b_m x^m + \cdots$로 나눌 때

첫 번째 step에서 $\frac{a_n}{b_m}$ 계산 필요

**Field**: $b_m^{-1}$ 존재 
**Non-field** ($\mathbb{Z}$): $b_m^{-1}$ 없을 수 있음 ✗

### Remainder의 의미

**작은 나머지**: $\deg(r) < \deg(g)$

**의미**:
- "g로 더 이상 나눌 수 없음"
- $r$이 $g$보다 "작음" (차수로 측정)

## Field Requirement

**중요**: Division algorithm은 **field** $F$ 위에서만 일반적으로 성립!

### Why Field?

**필요**: Leading coefficient $b_m$의 역원 $b_m^{-1}$

**과정**:

$$f(x) - \frac{a_n}{b_m} x^{n-m} \cdot g(x)$$

여기서 $\frac{a_n}{b_m}$ 계산!

### Counterexample: $\mathbb{Z}[x]$

$\mathbb{Z}[x]$는 **NOT** Euclidean domain (일반적으로)

**예**: $x^2$ divided by $2x$

$$x^2 = q(x) \cdot 2x + r(x)?$$

$q(x) = \frac{x}{2}$ 필요하지만 $\frac{1}{2} \notin \mathbb{Z}$ ✗

### Monic Divisor

**예외**: $g(x)$ **monic**^[최고차 계수가 1]이면 일반 ring에서도 가능!

**이유**: Leading coefficient = 1, 역원 계산 불필요

**예** ($\mathbb{Z}[x]$):

$$x^3 + 2x^2 - x + 3 = q(x)(x - 1) + r$$

작동함! ($x - 1$은 monic)

## Long Division Process

**Algorithm**:

1. **Compare degrees**: $\deg(f)$ vs $\deg(g)$
   - If $\deg(f) < \deg(g)$: Done! $q = 0$, $r = f$

2. **Eliminate leading term**: 
   - Compute $c = \frac{\text{leading}(f)}{\text{leading}(g)}$
   - Compute $d = \deg(f) - \deg(g)$
   - Form $cx^d \cdot g(x)$

3. **Subtract**: $f_{\text{new}} = f - cx^d \cdot g$

4. **Repeat**: Until $\deg(f_{\text{new}}) < \deg(g)$

**시각적**: 중학교 long division과 동일!

## Applications

### 1. Root Finding

**Factor Theorem**: $(x - a) | f(x) \Leftrightarrow f(a) = 0$

**Process**:
- Find root $a$: $f(a) = 0$
- Factor: $f(x) = (x - a)g(x)$
- Repeat on $g(x)$

### 2. GCD Computation

**Euclidean Algorithm**:

$$\gcd(f, g) = \gcd(g, r)$$

where $f = qg + r$

**Example**: 
- $\gcd(x^3 - 1, x^2 - 1)$
- Apply division repeatedly
- Get $\gcd = x - 1$

### 3. Polynomial Interpolation

**Given**: Points $(x_1, y_1), \ldots, (x_n, y_n)$

**Find**: Polynomial $f$ with $f(x_i) = y_i$

**Method**: Lagrange, Newton, or CRT approach

자세한 내용은 [[Polynomial Interpolation]] 참조

### 4. Modular Arithmetic

**Polynomials mod $g(x)$**:

$$F[x] / \langle g(x) \rangle$$

**Remainder**: Representatives of cosets

**Example**: $\mathbb{F}_2[x] / \langle x^8 + x^4 + x^3 + x + 1 \rangle$ (AES)

### 5. Coding Theory

**Error correction codes**: Reed-Solomon, BCH

**Division**: Syndrome computation

### 6. Cryptography

**AES**: Polynomial arithmetic mod irreducible

**Example**: $\mathbb{F}_{2^8} = \mathbb{F}_2[x] / \langle x^8 + x^4 + x^3 + x + 1 \rangle$

## Synthetic Division

**Special case**: Dividing by $(x - a)$

**Advantage**: Faster, simpler notation

**Process**: Use coefficients only

**Example**: Divide $2x^3 - 3x^2 + x - 5$ by $x - 2$

```
  2 |  2  -3   1  -5
    |     4   2   6
    _______________
      2   1   3   1
```

**Result**: $q(x) = 2x^2 + x + 3$, $r = 1$

**Limitation**: Only works for $(x - a)$ form

## Common Pitfall^[흔한 실수]

### 1. Non-Field Base Ring

Division algorithm이 $\mathbb{Z}[x]$에서 항상 작동? **NO!**

**예**: $x^2$ divided by $2x$ in $\mathbb{Z}[x]$ ✗

**해결**: Field 사용 또는 monic divisor

### 2. Degree Comparison

$\deg(r) < \deg(g)$ **or** $r = 0$

**실수**: "$\deg(r) < \deg(g)$만" 생각

**사실**: $r = 0$일 때 $\deg(0)$ undefined!

### 3. Remainder in $F$ vs $F[x]$

$(x - a)$로 나눈 나머지: $r \in F$ (constant!)

**실수**: "$r(x)$는 polynomial"이라고 생각

**사실**: Degree 0 polynomial = constant = element of $F$

### 4. Uniqueness of $q, r$

$q, r$은 조건 하에서 유일!

**조건**: $\deg(r) < \deg(g)$ or $r = 0$

**없으면**: 여러 representation 가능

예: $f = qg + r = (q - 1)g + (r + g)$

### 5. Leading Coefficient

**주의**: $g(x)$의 leading coefficient $\neq 1$일 때

$$\frac{a_n}{b_m}$$ 계산 필요!

**실수**: 항상 1로 가정

### 6. Over Finite Fields

$\mathbb{F}_p$에서 $1 + 1 + \cdots + 1 = 0$ (p번)

**Arithmetic**: Modular!

**예** ($\mathbb{F}_2$): $1 + 1 = 0$

### 7. Multiple Variables

$F[x, y]$에서는 어떤 변수로 나눌지 선택!

**예**: $x^2 + xy + y^2$ divided by $x + y$?

View as polynomial in $x$ (coefficients in $F[y]$)

## Complexity

**Division algorithm**: $O(nm)$ field operations

where $n = \deg(f)$, $m = \deg(g)$

**Fast methods**: FFT-based, Karatsuba

**Asymptotic**: $O(n \log n)$ possible

## Historical Background

**Ancient**: Known to Greek mathematicians

**Al-Khwarizmi** (9th century): Polynomial methods

**Renaissance**: Development of symbolic algebra

**Modern**: Algorithmic complexity, computer algebra

## 관련 개념

- [[Polynomial Ring]]: $F[x]$ structure
- [[Euclidean Domain]]: Generalization
- [[Euclidean Algorithm for Polynomials]]: GCD computation
- [[Remainder Theorem]]: Special case $(x - a)$
- [[Factor Theorem]]: Roots and factors
- [[Chinese Remainder Theorem]]: Multiple divisors
- [[Polynomial Interpolation]]: Applications
- [[GCD and LCM]]: Using division
- [[Principal Ideal Domain]]: $F[x]$ is PID
- [[Quotient Ring]]: $F[x] / \langle g(x) \rangle$

## 추가 학습 주제

**기초**:
- Division algorithm statement
- Long division process
- Remainder vs Factor Theorem
- Examples in $\mathbb{Q}[x]$, $\mathbb{R}[x]$

**중급**:
- Synthetic division
- Euclidean algorithm
- GCD computation
- Polynomial interpolation
- Over finite fields $\mathbb{F}_p[x]$

**고급**:
- Fast polynomial division
- Multivariate division
- Gröbner bases
- Applications in coding theory
- Computer algebra systems
- Complexity analysis

