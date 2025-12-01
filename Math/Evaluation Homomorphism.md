# <span class="header-prerequisite">Prerequisite</span>
- [[Polynomial Ring]]
- [[Ring]]
- [[Homomorphism]]
- [[Ideal]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Artin, Algebra
- Jacobson, Basic Algebra I

---

# <span class="header-definition">Definition</span>

## Evaluation Homomorphism^[평가 준동형사상]

Ring $R$과 원소 $a \in R$에 대해, **evaluation homomorphism^[평가 준동형사상]** (또는 **substitution homomorphism^[대입 준동형사상]**)은:

$$\text{ev}_a: R[x] \to R$$

$$\text{ev}_a(f(x)) = f(a)$$

**정의**: Polynomial $f(x) = a_0 + a_1x + \cdots + a_nx^n$에 대해:

$$\text{ev}_a(f(x)) = a_0 + a_1a + a_2a^2 + \cdots + a_na^n$$

**의미**: "다항식 $f(x)$에 $x = a$를 대입한 값"

**표기**:
- $\text{ev}_a(f(x))$
- $f(a)$
- $f|_{x=a}$

## More General Form

Ring homomorphism $\phi: R \to S$와 $s \in S$에 대해:

$$\text{ev}_{s, \phi}: R[x] \to S$$

$$\text{ev}_{s, \phi}\left(\sum_{i=0}^{n} a_i x^i\right) = \sum_{i=0}^{n} \phi(a_i) s^i$$

**특수 경우**: $\phi = \text{id}_R$이고 $s = a \in R$이면 위의 표준 evaluation homomorphism

---

# <span class="header-theorem">Theorems</span>

## Evaluation is Ring Homomorphism

**정리**: $\text{ev}_a: R[x] \to R$은 ring homomorphism^[환 준동형사상]

**증명**:

### 1. Preserves Addition^[덧셈 보존]

$$\text{ev}_a(f + g) = (f + g)(a) = f(a) + g(a) = \text{ev}_a(f) + \text{ev}_a(g)$$ ✓

### 2. Preserves Multiplication^[곱셈 보존]

$$\text{ev}_a(f \cdot g) = (f \cdot g)(a) = f(a) \cdot g(a) = \text{ev}_a(f) \cdot \text{ev}_a(g)$$ ✓

### 3. Preserves Identity^[항등원 보존]

$$\text{ev}_a(1) = 1(a) = 1$$ ✓

따라서 $\text{ev}_a$는 ring homomorphism ✓

## Kernel of Evaluation Homomorphism

**정리**: Integral domain^[정역] $R$에서:

$$\ker(\text{ev}_a) = (x - a)$$

즉, $a$에서 0이 되는 모든 다항식의 ideal = $(x-a)$로 생성되는 principal ideal^[주 아이디얼]

**증명**:

**($\supseteq$)**: $(x-a) \subseteq \ker(\text{ev}_a)$
- $(x-a)f(x) \in (x-a)$에 대해
- $\text{ev}_a((x-a)f(x)) = (a-a)f(a) = 0 \cdot f(a) = 0$ ✓

**($\subseteq$)**: $\ker(\text{ev}_a) \subseteq (x-a)$
- $f(x) \in \ker(\text{ev}_a)$이면 $f(a) = 0$
- Division algorithm: $f(x) = (x-a)q(x) + r$ where $\deg(r) < 1$
- $r$는 constant: $r \in R$
- $0 = f(a) = (a-a)q(a) + r = r$
- 따라서 $f(x) = (x-a)q(x) \in (x-a)$ ✓

### 표기법 주의

**$(x-a)$의 의미**:

1. **$x-a$**: 원소 하나 (polynomial in $R[x]$)
2. **$(x-a)$ 또는 $\langle x-a \rangle$**: Principal ideal^[주 아이디얼] (집합)

$$(x-a) = \langle x-a \rangle = \{(x-a)f(x) : f(x) \in R[x]\}$$

**의미**: $(x-a)$를 **인수로 갖는** 모든 다항식들의 집합

**예**: $\mathbb{R}[x]$에서 $(x-2)$의 원소들:
- $(x-2) \cdot 1 = x-2$
- $(x-2) \cdot x = x^2-2x$
- $(x-2) \cdot (x+3) = x^2+x-6$

**공통점**: 모두 $x=2$에서 0이 됨

**관습**: Ring theory에서 $(x-a)$는 관습적으로 ideal을 의미하지만, 더 명확하게 하려면 $\langle x-a \rangle$ 표기를 사용할 수도 있음

## Image of Evaluation Homomorphism

**정리**: $\text{ev}_a: R[x] \to R$는 **surjective^[전사]**

**증명**: 임의의 $r \in R$에 대해, constant polynomial $f(x) = r$은:

$$\text{ev}_a(r) = r$$ ✓

따라서 $\text{im}(\text{ev}_a) = R$ ✓

## First Isomorphism Theorem Applied

**정리**: 

$$R[x]/(x-a) \cong R$$

**증명**: First Isomorphism Theorem^[제1 동형 정리]:

$$R[x]/\ker(\text{ev}_a) \cong \text{im}(\text{ev}_a)$$

$$R[x]/(x-a) \cong R$$ ✓

**Isomorphism**: $\bar{f}(x) + (x-a) \mapsto f(a)$

## Universal Property of Polynomial Rings

**정리** (**Universal Property**):

Ring $S$, ring homomorphism $\phi: R \to S$, 그리고 $s \in S$가 주어지면:

**Unique** ring homomorphism $\Phi: R[x] \to S$ exists such that:

1. $\Phi|_R = \phi$ (extends $\phi$)
2. $\Phi(x) = s$

**명시적 형태**:

$$\Phi\left(\sum_{i=0}^{n} a_i x^i\right) = \sum_{i=0}^{n} \phi(a_i) s^i$$

**의미**: "$x$를 $s$로 대입하고, 계수는 $\phi$로 보냄"

**특수 경우**: $\phi = \text{id}_R$이면 $\Phi = \text{ev}_s$

**다이어그램**:

```
R ----φ---→ S
↓           ↗
↓ ι      Φ
↓       ↗
R[x] ---
```

where $\iota: R \to R[x]$ is inclusion

---

# <span class="header-examples">Examples</span>

## Example 1: Evaluation at 0

$$\text{ev}_0: \mathbb{R}[x] \to \mathbb{R}$$

$$f(x) = a_0 + a_1x + \cdots + a_nx^n \mapsto a_0$$

**Kernel**: $\ker(\text{ev}_0) = (x)$ = polynomials with zero constant term

**Image**: $\mathbb{R}$ ✓ (surjective)

**Interpretation**: "상수항 추출"

## Example 2: Evaluation at 1

$$\text{ev}_1: \mathbb{Z}[x] \to \mathbb{Z}$$

$$f(x) = a_0 + a_1x + \cdots + a_nx^n \mapsto a_0 + a_1 + \cdots + a_n$$

**Kernel**: $\ker(\text{ev}_1) = (x-1)$

**예**: $x^n - 1 \in (x-1)$ for all $n \geq 1$

**Interpretation**: "계수의 합"

## Example 3: Evaluation at $i$

$$\text{ev}_i: \mathbb{R}[x] \to \mathbb{C}$$

$$f(x) = a_0 + a_1x + \cdots + a_nx^n \mapsto a_0 + a_1i + a_2(-1) + a_3(-i) + \cdots$$

**Kernel**: $\ker(\text{ev}_i) = (x^2 + 1)$ in $\mathbb{R}[x]$

**Image**: $\mathbb{C}$ ✓

**예**: $x^2 + 1 \mapsto i^2 + 1 = -1 + 1 = 0$ ✓

## Example 4: Evaluation at Matrix

$$\text{ev}_A: \mathbb{R}[x] \to M_n(\mathbb{R})$$

where $A \in M_n(\mathbb{R})$

$$f(x) = a_0 + a_1x + \cdots + a_kx^k \mapsto a_0I + a_1A + \cdots + a_kA^k$$

**예**: $f(x) = x^2 - 3x + 2I$

$$\text{ev}_A(f) = A^2 - 3A + 2I$$

**Kernel**: Polynomials annihilating $A$ (includes minimal polynomial^[최소 다항식])

**응용**: Cayley-Hamilton Theorem

## Example 5: Evaluation in Quotient Ring

$$\text{ev}_{\bar{a}}: (\mathbb{Z}/n\mathbb{Z})[x] \to \mathbb{Z}/n\mathbb{Z}$$

$$f(x) \mapsto f(\bar{a})$$

**예**: $n = 5$, $a = 2$

$$f(x) = x^2 + 3x + 1 \mapsto \bar{2}^2 + 3\bar{2} + \bar{1} = \bar{4} + \bar{6} + \bar{1} = \bar{1}$$

## Example 6: Evaluation at Variable

$$\text{ev}_y: R[x] \to R[y]$$

$$f(x) \mapsto f(y)$$

**의미**: "변수 이름 바꾸기"

**Isomorphism**: $R[x] \cong R[y]$ ✓

## Example 7: Composition of Polynomials

$g(x) \in R[x]$ 고정, evaluation at $g(x)$:

$$\text{ev}_{g(x)}: R[x] \to R[x]$$

$$f(x) \mapsto f(g(x))$$

**예**: $g(x) = x^2$, $f(x) = x + 1$

$$\text{ev}_{x^2}(f) = f(x^2) = x^2 + 1$$

**주의**: 일반적으로 not surjective!

---

# <span class="header-properties">Properties</span>

## Functoriality^[함자성]

**정리**: Ring homomorphism $\phi: R \to S$에 대해, induced map:

$$\phi_*: R[x] \to S[x], \quad \sum a_i x^i \mapsto \sum \phi(a_i) x^i$$

다음 diagram이 commute:

```
R[x] --ev_a-→ R
 |             |
φ*|             |φ
 ↓             ↓
S[x] --ev_φ(a)-→ S
```

$$\phi \circ \text{ev}_a = \text{ev}_{\phi(a)} \circ \phi_*$$

## Evaluation Preserves Degree Bound

**정리**: $f(x) \in R[x]$, $\deg(f) \leq n$이면:

$$\deg(\text{ev}_a(f)) \leq 0$$

(evaluation의 결과는 constant)

## Evaluation and Roots

**정리** (Factor Theorem^[인수 정리]):

$R$ integral domain, $f(x) \in R[x]$, $a \in R$에 대해:

$$f(a) = 0 \quad \Leftrightarrow \quad (x-a) \mid f(x)$$

**증명**:
- ($\Rightarrow$): $f(a) = 0$ $\Rightarrow$ $f \in \ker(\text{ev}_a) = (x-a)$
- ($\Leftarrow$): $(x-a) \mid f$ $\Rightarrow$ $f = (x-a)g$ $\Rightarrow$ $f(a) = 0$ ✓

자세한 내용은 [[Factor Theorem]] 참조

## Number of Roots Bound

**정리**: Field $k$, $f(x) \in k[x]$ nonzero, $\deg(f) = n$

$f$는 최대 $n$개의 distinct roots in $k$

**증명**: Induction + Factor Theorem
- $a$ root $\Rightarrow$ $f(x) = (x-a)g(x)$
- $\deg(g) = n - 1$
- Induction on degree

## Evaluation at Multiple Points

**정리**: Distinct $a_1, \ldots, a_n \in R$에 대해:

$$\text{ev}: R[x] \to R^n, \quad f \mapsto (f(a_1), \ldots, f(a_n))$$

Ring homomorphism

**Kernel**: $\ker(\text{ev}) = \bigcap_{i=1}^{n} (x - a_i)$

Field $k$에서: $\ker(\text{ev}) = ((x-a_1) \cdots (x-a_n))$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Evaluation Homomorphism**: "다항식에 값 대입"

**핵심 아이디어**:
- Polynomial은 "formal expression^[형식적 표현]"
- Evaluation은 "실제 계산^[actual computation]"
- $x$는 placeholder → $a$는 실제 값

**메타포**:
- Polynomial = "recipe^[조리법]"
- Evaluation = "cooking^[실제 요리]"
- $x$ = ingredient placeholder
- $a$ = actual ingredient

## Polynomial vs Polynomial Function

**중요한 구별**:

1. **Polynomial** (element of $R[x]$): Formal expression
2. **Polynomial function** ($R \to R$): Actual function

**Infinite field에서**: One-to-one correspondence

**Finite field에서**: Different!

**예**: $\mathbb{F}_2 = \{0, 1\}$

- Polynomials: $x$, $x^2$ (distinct in $\mathbb{F}_2[x]$)
- Functions: Both give $(0 \mapsto 0, 1 \mapsto 1)$ (same function!)

$$x \neq x^2 \text{ in } \mathbb{F}_2[x]$$

$$\text{but } \text{ev}_0(x) = \text{ev}_0(x^2) = 0, \quad \text{ev}_1(x) = \text{ev}_1(x^2) = 1$$

**결론**: Evaluation homomorphism may not be injective for all polynomials!

## Universal Property Interpretation

**Universal Property**는 evaluation homomorphism을 특징짓는다:

"$R[x]$는 $R$에 formal element $x$를 추가한 것"

**의미**:
- $R \subseteq R[x]$ (constants)
- $x \in R[x]$ (indeterminate)
- 임의의 $s \in S$ (다른 ring)로 $x$를 "보낼 수 있음"

**철학**: $R[x]$는 "free object" over $R$ with one generator

## 역사적 배경

**Polynomial evaluation**:
- 고대부터 사용 (수치 계산)
- 대수적 형식화: 19세기

**Ring homomorphism 관점**:
- Modern abstract algebra (Emmy Noether, 1920s)
- Universal properties (Category theory, 1940s)

## 응용 분야

### 1. Field Extensions^[체 확대]

**Construction**: $k[x]/(f(x))$ where $f$ irreducible

Evaluation at root $\alpha$ in extension:

$$\text{ev}_\alpha: k[x] \to k(\alpha)$$

$$\ker(\text{ev}_\alpha) = (f(x))$$

자세한 내용은 [[Extension Field]], [[Kronecker Theorem]] 참조

### 2. Algebraic Geometry^[대수기하학]

**Variety**: $V = \{a \in k^n : f_i(a) = 0 \; \forall i\}$

Evaluation homomorphism:

$$\text{ev}: k[x_1, \ldots, x_n] \to k$$

at point $a = (a_1, \ldots, a_n)$

**응용**: Define coordinate ring, function ring

### 3. Representation Theory^[표현론]

**Module over $k[x]$**: Vector space $V$ with linear operator $T$

Evaluation at $T$:

$$\text{ev}_T: k[x] \to \text{End}(V)$$

$$f(x) \mapsto f(T)$$

**응용**: Minimal polynomial, Cayley-Hamilton

### 4. Interpolation^[보간]

**Lagrange interpolation**: Given $(a_i, b_i)$, find $f$ such that $f(a_i) = b_i$

Evaluation map:

$$\text{ev}: k[x]_{\leq n} \to k^{n+1}$$

$$f \mapsto (f(a_0), \ldots, f(a_n))$$

Bijection if $a_i$ distinct and $\deg(f) \leq n$

### 5. Numerical Analysis^[수치해석]

**Horner's method**: Efficient evaluation

$$f(x) = a_0 + x(a_1 + x(a_2 + \cdots + x(a_{n-1} + xa_n)))$$

**Complexity**: $O(n)$ operations

### 6. Computer Algebra Systems

**Symbolic computation**: Manipulate polynomials

**Evaluation**: Convert symbolic to numeric

**응용**: Mathematica, SageMath, SymPy

## Common Pitfalls^[흔한 실수]

### 1. Polynomial ≠ Polynomial Function

✗ "Polynomial = function $R \to R$"?

✓ Polynomial은 formal expression; evaluation이 function을 정의

**문제**: Finite fields에서 다를 수 있음!

### 2. Kernel in General Rings

✗ $\ker(\text{ev}_a) = (x-a)$ 항상 성립?

✓ Integral domain에서만 성립!

**반례**: $\mathbb{Z}/4\mathbb{Z}$

$f(x) = 2x$ has $f(0) = 0$ but $2x \notin (x)$ as ideals

### 3. Injectivity

✗ Evaluation은 항상 injective?

✓ **NO!** Kernel은 $(x-a)$ (nontrivial)

Evaluation은 surjective이지만 not injective

### 4. Composition

✗ $\text{ev}_b \circ \text{ev}_a = \text{ev}_{a+b}$?

✓ **NO!** Composition doesn't work this way

$\text{ev}_a: R[x] \to R$, $\text{ev}_b: R[x] \to R$ (domains don't match for composition!)

### 5. Matrix Evaluation

✗ $\text{ev}_A(f + g) = \text{ev}_A(f) + \text{ev}_A(g)$ for matrices?

✓ **YES** (homomorphism property holds)

But: Matrix multiplication is not commutative, so some care needed

## 관련 개념

- [[Polynomial Ring]]: Domain of evaluation homomorphism
- [[Homomorphism]]: General theory
- [[Ring]]: Structure being preserved
- [[Ideal]]: Kernel of evaluation
- [[Factor Theorem]]: Roots and factors
- [[Extension Field]]: Adjoining roots
- [[Kronecker Theorem]]: Construction using quotient
- [[First Isomorphism Theorem]]: $R[x]/(x-a) \cong R$

## Summary of Key Points

**Definition**: $\text{ev}_a: R[x] \to R$, $f(x) \mapsto f(a)$

**Ring homomorphism**: Preserves $+$, $\times$, $1$

**Kernel**: $(x-a)$ (in integral domain)

**Image**: $R$ (surjective)

**Isomorphism**: $R[x]/(x-a) \cong R$

**Universal property**: Unique extension of coefficient map

**Applications**: Field extensions, algebraic geometry, representation theory

**Philosophy**: "Substitution preserves algebraic structure"

