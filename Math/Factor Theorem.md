# <span class="header-prerequisite">Prerequisite</span>
- [[Division Algorithm for Polynomials]]
- [[Polynomial]]
- [[Ring]]
- [[Field]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Hungerford, Algebra
- Lang, Algebra

---

# <span class="header-definition">Definition</span>

## Factor Theorem

$F$를 field^[체]라고 하고, $f(x) \in F[x]$를 polynomial^[다항식]이라고 하자.

$a \in F$에 대해 다음이 성립:

$$(x - a) \text{ divides } f(x) \quad \Leftrightarrow \quad f(a) = 0$$

**동치 표현**:

$$f(a) = 0 \quad \Leftrightarrow \quad f(x) = (x - a) q(x)$$

for some $q(x) \in F[x]$

**용어**:
- $f(a) = 0$: $a$는 $f(x)$의 **root**^[근] (또는 **zero**^[영점])
- $(x - a) \mid f(x)$: $(x - a)$는 $f(x)$의 **factor**^[인수]

**핵심**:

> **Root** $\Leftrightarrow$ **Linear factor**
> 
> "근"과 "일차 인수"는 일대일 대응

## Remainder Theorem

**정리** (**Remainder Theorem**^[나머지 정리]):

$f(x) \in F[x]$를 $g(x) = x - a$로 나눈 나머지는 $f(a)$

$$f(x) = (x - a) q(x) + r$$

where $r = f(a)$ (constant)

**증명**:

Division Algorithm에 의해:

$$f(x) = (x - a) q(x) + r$$

where $\deg(r) < \deg(x - a) = 1$

따라서 $r$은 상수

$x = a$를 대입:

$$f(a) = (a - a) q(a) + r = 0 + r = r$$

따라서 $r = f(a)$ ✓

**관계**: Factor Theorem은 Remainder Theorem의 특수한 경우 ($r = 0$)

## Multiple Roots

**정의**: $a$가 $f(x)$의 **root of multiplicity $m$**^[중근도 $m$인 근]이면:

$$(x - a)^m \mid f(x) \quad \text{but} \quad (x - a)^{m+1} \nmid f(x)$$

**동치 표현**:

$$f(x) = (x - a)^m q(x)$$

where $q(a) \neq 0$

**용어**:
- $m = 1$: **simple root**^[단순근]
- $m = 2$: **double root**^[중근]
- $m = 3$: **triple root**^[삼중근]
- $m \geq 2$: **multiple root**^[중근]

## Complete Factorization

**정리**: $f(x) \in F[x]$가 degree $n$이고 $a_1, \ldots, a_k$가 서로 다른 roots with multiplicities $m_1, \ldots, m_k$이면:

$$f(x) = c(x - a_1)^{m_1} (x - a_2)^{m_2} \cdots (x - a_k)^{m_k} g(x)$$

where:
- $c \in F$ (leading coefficient)
- $g(x) \in F[x]$ has no roots in $F$
- $m_1 + m_2 + \cdots + m_k \leq n$

**특수한 경우** ($F$ algebraically closed, e.g., $\mathbb{C}$):

$$f(x) = c(x - a_1)^{m_1} (x - a_2)^{m_2} \cdots (x - a_k)^{m_k}$$

where $m_1 + m_2 + \cdots + m_k = n$

---

# <span class="header-proof">Proof</span>

## Proof of Factor Theorem

### ($\Rightarrow$) If $(x - a) \mid f(x)$, then $f(a) = 0$

**가정**: $(x - a) \mid f(x)$

따라서:

$$f(x) = (x - a) q(x)$$

for some $q(x) \in F[x]$

$x = a$를 대입:

$$f(a) = (a - a) q(a) = 0 \cdot q(a) = 0$$

따라서 $f(a) = 0$ ✓

### ($\Leftarrow$) If $f(a) = 0$, then $(x - a) \mid f(x)$

**가정**: $f(a) = 0$

Division Algorithm에 의해:

$$f(x) = (x - a) q(x) + r$$

where $r \in F$ (constant, since $\deg(r) < 1$)

Remainder Theorem에 의해:

$$r = f(a) = 0$$

따라서:

$$f(x) = (x - a) q(x)$$

즉, $(x - a) \mid f(x)$ ✓

## Uniqueness of Factorization

**정리**: Root의 multiplicity는 유일하게 결정됨

**증명**: $F[x]$는 **unique factorization domain**^[유일 인수분해 정역]이므로

$(x - a)^m$의 exponent $m$은 유일 ✓

자세한 내용은 [[Unique Factorization Domain]] 참조

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Number of Roots

**정리**: Degree $n$ polynomial은 최대 $n$개의 roots (multiplicity 포함)

**증명**: 

$f(x)$가 degree $n$이고 $a_1, \ldots, a_k$가 multiplicities $m_1, \ldots, m_k$인 roots이면:

$$f(x) = (x - a_1)^{m_1} \cdots (x - a_k)^{m_k} g(x)$$

where $g(x)$는 $F$에 root가 없음

Degree comparison:

$$n = \deg(f) = m_1 + \cdots + m_k + \deg(g) \geq m_1 + \cdots + m_k$$

**Counting multiplicities**: Total number of roots $\leq n$ ✓

**주의**: 
- In $\mathbb{C}$: exactly $n$ roots (Fundamental Theorem of Algebra)
- In $\mathbb{R}$: at most $n$ roots (some may be complex)
- In $\mathbb{Q}$: possibly 0 roots (e.g., $x^2 - 2$)

### 2. Iterated Application

**정리**: $a_1, a_2, \ldots, a_k$가 distinct roots이면:

$$(x - a_1)(x - a_2) \cdots (x - a_k) \mid f(x)$$

**증명** (Induction):

**Base**: $k = 1$: Factor Theorem ✓

**Step**: $f(a_1) = 0 \Rightarrow f(x) = (x - a_1) g(x)$

$f(a_2) = 0 \Rightarrow (a_2 - a_1) g(a_2) = 0$

$a_2 \neq a_1$ (distinct) $\Rightarrow g(a_2) = 0$

By induction: $(x - a_2) \cdots (x - a_k) \mid g(x)$

따라서: $(x - a_1)(x - a_2) \cdots (x - a_k) \mid f(x)$ ✓

### 3. Polynomial Equality

**정리**: $f, g \in F[x]$가 degree $\leq n$이고 $n+1$개의 점에서 같으면 $f = g$

**증명**:

$h(x) = f(x) - g(x)$라고 하자

$h(x)$는 $n+1$개의 roots를 가짐

But $\deg(h) \leq n$

따라서 $h(x) = 0$ (zero polynomial) ✓

**응용**: Polynomial interpolation의 uniqueness

### 4. Derivative Criterion for Multiple Roots

**정리**: $a$가 multiplicity $m \geq 2$인 root $\Leftrightarrow$ $f(a) = 0$ and $f'(a) = 0$

**증명**:

$f(x) = (x - a)^m q(x)$ where $q(a) \neq 0$

**Derivative**:

$$f'(x) = m(x - a)^{m-1} q(x) + (x - a)^m q'(x)$$

$$= (x - a)^{m-1} [m q(x) + (x - a) q'(x)]$$

**$m \geq 2$이면**:

$$f'(a) = (a - a)^{m-1} \cdot [\ldots] = 0$$

**Conversely**: $f(a) = f'(a) = 0 \Rightarrow (x-a)^2 \mid f(x)$ ✓

**일반화**: $a$가 multiplicity $m$인 root $\Leftrightarrow$

$$f(a) = f'(a) = f''(a) = \cdots = f^{(m-1)}(a) = 0$$

and $f^{(m)}(a) \neq 0$

### 5. Sum and Product of Roots

$f(x) = a_n x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0$가 roots $r_1, \ldots, r_n$ (with multiplicity)를 가지면:

**Vieta's formulas**^[비에타 공식]:

$$\text{Sum of roots}: \quad r_1 + r_2 + \cdots + r_n = -\frac{a_{n-1}}{a_n}$$

$$\text{Product of roots}: \quad r_1 r_2 \cdots r_n = (-1)^n \frac{a_0}{a_n}$$

**일반**: 

$$\sum_{i_1 < i_2 < \cdots < i_k} r_{i_1} r_{i_2} \cdots r_{i_k} = (-1)^k \frac{a_{n-k}}{a_n}$$

자세한 내용은 [[Vieta's Formulas]] 참조

## Factorization Properties

### 6. Irreducible Factors

**정의**: $p(x) \in F[x]$가 **irreducible**^[기약]이면:

$$p(x) = a(x) b(x) \quad \Rightarrow \quad \deg(a) = 0 \text{ or } \deg(b) = 0$$

**관계 with roots**:
- Degree 1: Always irreducible, has root in $F$
- Degree $\geq 2$ irreducible over $F$: No roots in $F$

**예시**:
- $x^2 + 1$ irreducible over $\mathbb{R}$ (no real roots)
- $x^2 + 1 = (x - i)(x + i)$ over $\mathbb{C}$ (has complex roots)

### 7. Factorization over Different Fields

**예시**: $f(x) = x^4 - 2$

**(a) Over $\mathbb{Q}$**:

$$x^4 - 2 \text{ is irreducible}$$

(no rational roots, Eisenstein criterion)

**(b) Over $\mathbb{R}$**:

$$x^4 - 2 = (x^2 - \sqrt{2})(x^2 + \sqrt{2})$$

Real roots: $\pm \sqrt[4]{2}$

**(c) Over $\mathbb{C}$**:

$$x^4 - 2 = (x - \sqrt[4]{2})(x + \sqrt[4]{2})(x - i\sqrt[4]{2})(x + i\sqrt[4]{2})$$

Four complex roots

**교훈**: Factorization depends on the field!

---

# <span class="header-examples">Examples</span>

## Example 1: Simple Root

$f(x) = x^2 - 5x + 6$

**Find roots**:

Try $x = 2$:

$$f(2) = 4 - 10 + 6 = 0$$ ✓

By Factor Theorem: $(x - 2) \mid f(x)$

**Division**:

$$f(x) = (x - 2)(x - 3)$$

**Roots**: $x = 2, 3$

## Example 2: Multiple Root

$f(x) = x^3 - 6x^2 + 12x - 8$

**Observation**: $f(2) = 8 - 24 + 24 - 8 = 0$

**Check multiplicity**:

$$f'(x) = 3x^2 - 12x + 12$$

$$f'(2) = 12 - 24 + 12 = 0$$

$$f''(x) = 6x - 12$$

$$f''(2) = 12 - 12 = 0$$

$$f'''(x) = 6 \neq 0$$

따라서 $x = 2$는 **triple root**!

**Factorization**:

$$f(x) = (x - 2)^3$$

## Example 3: Using Factor Theorem to Find Polynomial

**Problem**: Find $f(x)$ of degree 3 with:
- $f(1) = 0$
- $f(2) = 0$  
- $f(3) = 0$
- $f(0) = 6$

**Solution**:

By Factor Theorem:

$$f(x) = c(x - 1)(x - 2)(x - 3)$$

Use $f(0) = 6$:

$$6 = c(-1)(-2)(-3) = -6c$$

$$c = -1$$

**Answer**:

$$f(x) = -(x - 1)(x - 2)(x - 3) = -x^3 + 6x^2 - 11x + 6$$

## Example 4: Rational Root Theorem

$f(x) = 2x^3 - x^2 - 4x + 2$

**Possible rational roots**: $\pm 1, \pm 2, \pm \frac{1}{2}$

**Test**:

$$f(1) = 2 - 1 - 4 + 2 = -1 \neq 0$$

$$f(-1) = -2 - 1 + 4 + 2 = 3 \neq 0$$

$$f(2) = 16 - 4 - 8 + 2 = 6 \neq 0$$

$$f\left(\frac{1}{2}\right) = \frac{2}{8} - \frac{1}{4} - 2 + 2 = \frac{1}{4} - \frac{1}{4} = 0$$ ✓

**Factor out**:

$$f(x) = \left(x - \frac{1}{2}\right)(2x^2 - 4)$$

$$= 2\left(x - \frac{1}{2}\right)(x^2 - 2)$$

$$= (2x - 1)(x - \sqrt{2})(x + \sqrt{2})$$

**Roots**: $\frac{1}{2}, \pm\sqrt{2}$

자세한 내용은 [[Rational Root Theorem]] 참조

## Example 5: Complex Roots

$f(x) = x^4 + 4$

**(a) Over $\mathbb{R}$**: No real roots

$$f(x) > 0 \text{ for all } x \in \mathbb{R}$$

**(b) Over $\mathbb{C}$**: Find complex roots

$$x^4 = -4 = 4e^{i\pi}$$

$$x = \sqrt[4]{4} e^{i(\pi + 2\pi k)/4}, \quad k = 0, 1, 2, 3$$

**Roots**:

$$x = \sqrt{2} e^{i\pi/4}, \quad \sqrt{2} e^{i3\pi/4}, \quad \sqrt{2} e^{i5\pi/4}, \quad \sqrt{2} e^{i7\pi/4}$$

$$= \sqrt{2}(\cos\frac{\pi}{4} + i\sin\frac{\pi}{4}), \ldots$$

$$= 1 + i, \quad -1 + i, \quad -1 - i, \quad 1 - i$$

**Factorization over $\mathbb{C}$**:

$$x^4 + 4 = (x - (1+i))(x - (1-i))(x - (-1+i))(x - (-1-i))$$

**Factorization over $\mathbb{R}$**:

$$x^4 + 4 = (x^2 - 2x + 2)(x^2 + 2x + 2)$$

## Example 6: Polynomial Division Application

**Problem**: Find remainder when $f(x) = x^{100} - 2x^{51} + 1$ is divided by $g(x) = x^2 - 1$

**Solution**:

$$g(x) = x^2 - 1 = (x-1)(x+1)$$

By Remainder Theorem:

$$f(x) = (x^2 - 1) q(x) + ax + b$$

where $\deg(ax + b) < 2$

**Evaluate at roots**:

$$f(1) = 1 - 2 + 1 = 0 = a + b$$

$$f(-1) = 1 + 2 + 1 = 4 = -a + b$$

**Solve**:

$$a + b = 0$$
$$-a + b = 4$$

$$2b = 4 \Rightarrow b = 2, \quad a = -2$$

**Remainder**: $-2x + 2$

## Example 7: Constructing Polynomial from Roots

**Problem**: Find monic polynomial^[최고차 계수가 1인 다항식] with roots $1, 2, 3$ (simple) and $-1$ (double)

**Solution**:

$$f(x) = (x - 1)(x - 2)(x - 3)(x + 1)^2$$

**Expand**:

$$(x - 1)(x - 2)(x - 3) = x^3 - 6x^2 + 11x - 6$$

$$(x + 1)^2 = x^2 + 2x + 1$$

**Multiply**:

$$f(x) = (x^3 - 6x^2 + 11x - 6)(x^2 + 2x + 1)$$

$$= x^5 + 2x^4 + x^3 - 6x^4 - 12x^3 - 6x^2 + 11x^3 + 22x^2 + 11x - 6x^2 - 12x - 6$$

$$= x^5 - 4x^4 + 10x^2 - x - 6$$

## Example 8: Non-existence of Rational Roots

$f(x) = x^3 - 2$

**Claim**: No rational roots

**Proof** (Rational Root Theorem):

Possible rational roots: $\pm 1, \pm 2$

$$f(1) = -1 \neq 0$$
$$f(-1) = -3 \neq 0$$
$$f(2) = 6 \neq 0$$
$$f(-2) = -10 \neq 0$$

**Conclusion**: $f(x)$ is irreducible over $\mathbb{Q}$

**But**: $f(x) = (x - \sqrt[3]{2})(x^2 + \sqrt[3]{2}x + \sqrt[3]{4})$ over $\mathbb{R}$

---

# <span class="header-theorem">Theorem</span>

## Fundamental Theorem of Algebra

**정리**: Every non-constant polynomial over $\mathbb{C}$ has at least one root

**Consequence**: Degree $n$ polynomial over $\mathbb{C}$ has exactly $n$ roots (counting multiplicity)

**Complete factorization over $\mathbb{C}$**:

$$f(x) = a_n (x - r_1)(x - r_2) \cdots (x - r_n)$$

where $r_i \in \mathbb{C}$ (possibly repeated)

**의미**: $\mathbb{C}$ is **algebraically closed**^[대수적으로 닫힘]

자세한 내용은 [[Fundamental Theorem of Algebra]] 참조

## Rational Root Theorem

**정리**: $f(x) = a_n x^n + \cdots + a_1 x + a_0$ with integer coefficients

If $\frac{p}{q}$ is a rational root (in lowest terms), then:
- $p \mid a_0$ (numerator divides constant term)
- $q \mid a_n$ (denominator divides leading coefficient)

**증명**:

$$a_n \left(\frac{p}{q}\right)^n + \cdots + a_1 \frac{p}{q} + a_0 = 0$$

Multiply by $q^n$:

$$a_n p^n + a_{n-1} p^{n-1} q + \cdots + a_1 p q^{n-1} + a_0 q^n = 0$$

**Rearrange**:

$$a_n p^n = -q(a_{n-1} p^{n-1} + \cdots + a_0 q^{n-1})$$

$$\Rightarrow q \mid a_n p^n$$

$\gcd(p, q) = 1 \Rightarrow q \mid a_n$ ✓

Similarly: $p \mid a_0$ ✓

**응용**: Find rational roots systematically!

## Eisenstein's Criterion

**정리**: $f(x) = a_n x^n + \cdots + a_1 x + a_0 \in \mathbb{Z}[x]$

If there exists prime $p$ such that:
- $p \nmid a_n$ (doesn't divide leading coefficient)
- $p \mid a_i$ for all $i < n$ (divides all other coefficients)
- $p^2 \nmid a_0$ (doesn't divide constant term twice)

Then $f(x)$ is irreducible over $\mathbb{Q}$

**예시**: $f(x) = x^3 + 2x^2 + 2x + 2$

Take $p = 2$:
- $2 \nmid 1$ ✓
- $2 \mid 2$ ✓
- $2^2 = 4 \nmid 2$ ✓

따라서 $f(x)$ is irreducible over $\mathbb{Q}$ (no rational roots!)

자세한 내용은 [[Eisenstein Criterion]] 참조

## Descartes' Rule of Signs

**정리**: $f(x) \in \mathbb{R}[x]$에서

**(a) Positive roots**: Number of positive real roots $\leq$ number of sign changes in $f(x)$

**(b) Negative roots**: Number of negative real roots $\leq$ number of sign changes in $f(-x)$

**예시**: $f(x) = x^3 - 2x^2 - 5x + 6$

Sign sequence: $+, -, -, +$ → 2 sign changes

$\Rightarrow$ At most 2 positive roots

$f(-x) = -x^3 - 2x^2 + 5x + 6$

Sign sequence: $-, -, +, +$ → 1 sign change

$\Rightarrow$ At most 1 negative root

자세한 내용은 [[Descartes Rule of Signs]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### Why Factor Theorem Works

**Intuition**: "Root = graph crosses x-axis"

**Algebraically**: $f(a) = 0$ means remainder is 0 when dividing by $(x-a)$

**Geometric picture**:
- $f(x)$의 graph가 $x = a$에서 x-축을 지남
- $(x - a)$로 "factoring out" 가능
- Reduced polynomial $q(x)$는 degree 1 감소

### Multiple Roots

**Geometric**: Graph "touches" x-axis without crossing

**Algebraic**: $(x - a)^m$ divides $f(x)$

**Calculus connection**: 
- Simple root: $f(a) = 0$, $f'(a) \neq 0$ (crosses)
- Double root: $f(a) = 0$, $f'(a) = 0$, $f''(a) \neq 0$ (touches)
- Triple root: Inflection point at x-axis

### Number of Roots

**Why at most $n$ roots?**

**Intuition**: Each root "uses up" one degree

**Formal**: 

$$f(x) = (x - a_1) \cdots (x - a_k) g(x)$$

$$\deg(f) = k + \deg(g) \geq k$$

**Complete factorization** (over $\mathbb{C}$):

$$f(x) = a_n(x - r_1) \cdots (x - r_n)$$

Exactly $n$ factors for degree $n$!

## Connection to Other Concepts

### 1. Division Algorithm

Factor Theorem is special case of Division Algorithm:

$$f(x) = (x - a) q(x) + r$$

where $r = f(a)$ (Remainder Theorem)

$f(a) = 0 \Leftrightarrow r = 0 \Leftrightarrow (x-a) \mid f(x)$

### 2. Ideal Theory

**Ring theory perspective**:

$$(x - a) \mid f(x) \quad \Leftrightarrow \quad f(x) \in (x - a)$$

$(x - a)$ is **principal ideal**^[주 이데알] in $F[x]$

$f(a) = 0 \Leftrightarrow$ evaluation homomorphism $\phi_a: F[x] \to F$ has $f \in \ker(\phi_a)$

자세한 내용은 [[Principal Ideal]] 참조

### 3. Field Extensions

**Roots outside $F$**: Need field extension!

**예시**: $x^2 - 2$ over $\mathbb{Q}$

No rational roots $\Rightarrow$ extend to $\mathbb{Q}(\sqrt{2})$

$$x^2 - 2 = (x - \sqrt{2})(x + \sqrt{2})$$

**General**: Given $f(x)$ irreducible over $F$

Construct $F[x]/(f(x))$: field containing root of $f$

자세한 내용은 [[Field Extension]] 참조

### 4. Algebraic Geometry

**Zeros of polynomials** = **Geometric objects**

**1-variable**: Roots = points on line

**2-variables**: $f(x, y) = 0$ defines curve

**n-variables**: $f(x_1, \ldots, x_n) = 0$ defines hypersurface

**Factor Theorem generalization**: Hilbert's Nullstellensatz

자세한 내용은 [[Algebraic Geometry]] 참조

## Different Fields

### Over $\mathbb{Q}$ (Rationals)

**Tools**:
- Rational Root Theorem: Test possible rational roots
- Eisenstein's Criterion: Show irreducibility
- Many polynomials have NO rational roots!

**예시**: $x^2 - 2$, $x^3 - 2$ have no rational roots

### Over $\mathbb{R}$ (Reals)

**Factorization**:

$$f(x) = c \cdot (\text{linear}) \cdot (\text{irreducible quadratics})$$

**Irreducible over $\mathbb{R}$**: Degree 1 or degree 2 with negative discriminant

**예시**: $x^2 + 1 = (x - i)(x + i)$ (needs $\mathbb{C}$!)

**Intermediate Value Theorem**: Odd degree polynomials have at least one real root

### Over $\mathbb{C}$ (Complex)

**Fundamental Theorem of Algebra**: Complete factorization!

$$f(x) = a_n (x - r_1) \cdots (x - r_n)$$

**Every polynomial factors completely into linear factors**

**$\mathbb{C}$ is algebraically closed**: No irreducible polynomials of degree $> 1$

### Over Finite Fields

**예시**: $\mathbb{F}_p = \mathbb{Z}/p\mathbb{Z}$

**Different behavior**:

$$x^p - x = x(x-1)(x-2) \cdots (x-(p-1))$$

over $\mathbb{F}_p$ (Fermat's Little Theorem!)

**Every element is a root!**

자세한 내용은 [[Finite Field]] 참조

## Finding Roots: Practical Methods

### 1. Rational Root Theorem

**Step 1**: List possible rational roots $\frac{p}{q}$ where $p \mid a_0$, $q \mid a_n$

**Step 2**: Test each candidate

**Step 3**: Factor out $(x - r)$ if $f(r) = 0$

**Limitation**: Only finds rational roots!

### 2. Descartes' Rule of Signs

Bound number of positive/negative real roots

**Not exact**: Gives upper bound only

### 3. Newton's Method

**Numerical**: Approximate roots

$$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}$$

**Converges quickly** (quadratic convergence)

자세한 내용은 [[Newton's Method]] 참조

### 4. Factorization Algorithms

**Computer algebra**: Sophisticated algorithms

- Berlekamp's algorithm (finite fields)
- LLL algorithm (integer polynomials)
- Symbolic computation packages (Mathematica, Maple, etc.)

### 5. Galois Theory

**Theory of solvability**: Which polynomials have "closed-form" roots?

**Degree $\leq 4$**: Formulas exist (quadratic, cubic, quartic formulas)

**Degree $\geq 5$**: No general formula! (Abel-Ruffini theorem)

자세한 내용은 [[Galois Theory]] 참조

## Special Cases

### Quadratic Formula

$ax^2 + bx + c = 0$

$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

**Discriminant**: $\Delta = b^2 - 4ac$
- $\Delta > 0$: Two distinct real roots
- $\Delta = 0$: One repeated root
- $\Delta < 0$: Two complex conjugate roots

**Factorization**:

$$ax^2 + bx + c = a(x - r_1)(x - r_2)$$

where $r_1, r_2 = \frac{-b \pm \sqrt{\Delta}}{2a}$

### Cubic Formula

$ax^3 + bx^2 + cx + d = 0$

**Exists but complicated!** (Cardano's formula)

**Discriminant**: Determines nature of roots

**Depressed cubic**: $t^3 + pt + q = 0$ (eliminate $x^2$ term)

자세한 내용은 [[Cubic Formula]] 참조

### Quartic Formula

$ax^4 + bx^3 + cx^2 + dx + e = 0$

**Even more complicated!** (Ferrari's method)

**Strategy**: Reduce to cubic

자세한 내용은 [[Quartic Formula]] 참조

### Quintic and Higher

**No general formula!** (Abel-Ruffini theorem)

**Some special cases solvable**: 
- $x^5 - 1 = 0$ (roots of unity)
- $x^n - a = 0$ (radicals)

**General case**: Numerical methods or Galois theory

## Common Mistakes

### 1. Assuming All Roots are Real

**실수**: $f(x) = x^2 + 1$ has no roots (over $\mathbb{R}$)

**정확**: Has two complex roots $x = \pm i$

**교훈**: Always specify the field!

### 2. Forgetting Multiplicity

**실수**: $f(x) = (x-1)^3$ has "one root"

**정확**: Has one root with multiplicity 3

**Counting**: Degree $n \Rightarrow$ at most $n$ roots (with multiplicity)

### 3. Division vs Factor

**실수**: $(x-a) \mid f(x)$ means $f(x)/(x-a)$ exists

**주의**: Must be polynomial division, not just rational function!

### 4. Rational Root Theorem Limitations

**실수**: Rational Root Theorem finds all roots

**정확**: Only finds rational roots! Most roots are irrational/complex

**예시**: $x^2 - 2 = 0$ has roots $\pm\sqrt{2}$ (not rational)

### 5. Irreducibility Depends on Field

$x^2 + 1$ is:
- Irreducible over $\mathbb{R}$ ✓
- Reducible over $\mathbb{C}$: $(x-i)(x+i)$ ✓

**교훈**: Always specify "irreducible over ___"

## Applications

### 1. Solving Polynomial Equations

**Direct application**: Find roots of $f(x) = 0$

### 2. Polynomial Interpolation

**Lagrange interpolation**: Find polynomial through given points

**Uses**: Polynomial equality (Property 3)

### 3. Cryptography

**RSA encryption**: Uses polynomial factorization difficulty

**Finite fields**: Polynomial arithmetic in $\mathbb{F}_p[x]$

자세한 내용은 [[Cryptography]] 참조

### 4. Control Theory

**Transfer functions**: Poles and zeros

**Stability**: Root locations in complex plane

자세한 내용은 [[Control Theory]] 참조

### 5. Signal Processing

**Filter design**: Polynomial roots determine frequency response

**Z-transform**: Zeros and poles

자세한 내용은 [[Signal Processing]] 참조

### 6. Computer Graphics

**Bézier curves**: Polynomial parametrization

**Root finding**: Ray-surface intersections

### 7. Numerical Analysis

**Polynomial approximation**: Taylor series, Chebyshev polynomials

**Root finding algorithms**: Newton, secant methods

자세한 내용은 [[Numerical Analysis]] 참조

## Historical Note

**Factor Theorem**: Known since ancient times

**Ancient Babylonians**: Solved quadratic equations (geometric methods)

**Persian mathematicians** (Al-Khwarizmi, 9th century): Systematic algebra

**Italian Renaissance** (16th century):
- Cardano: Cubic formula (1545)
- Ferrari: Quartic formula

**19th century**:
- Abel & Ruffini: No quintic formula
- Galois: Galois theory (solvability by radicals)

**Fundamental Theorem of Algebra**:
- Stated: D'Alembert (1746)
- First proof: Gauss (1799, multiple proofs)

**Modern era**: Computer algebra systems, numerical methods

## 관련 개념

- [[Division Algorithm for Polynomials]]: Foundation of Factor Theorem
- [[Remainder Theorem]]: Special case $r = f(a)$
- [[Polynomial]]: Objects being factored
- [[Ring]]: Algebraic structure of $F[x]$
- [[Field]]: Coefficient domain $F$
- [[Fundamental Theorem of Algebra]]: Complete factorization over $\mathbb{C}$
- [[Rational Root Theorem]]: Finding rational roots
- [[Eisenstein Criterion]]: Proving irreducibility
- [[Field Extension]]: Adjoining roots
- [[Galois Theory]]: Solvability by radicals
- [[Unique Factorization Domain]]: $F[x]$ is UFD
- [[Principal Ideal]]: $(x-a)$ in $F[x]$
- [[Algebraic Geometry]]: Zeros of polynomials

## 추가 학습 주제

**기초**:
- Factor Theorem statement and proof
- Finding simple roots
- Polynomial division
- Remainder Theorem

**중급**:
- Multiple roots and derivatives
- Rational Root Theorem
- Vieta's formulas
- Factorization over different fields
- Irreducibility tests

**고급**:
- Galois theory
- Algebraic closure
- Resultants and discriminants
- Polynomial factorization algorithms
- Computational algebra
- Abel-Ruffini theorem

