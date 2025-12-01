# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Commutative Ring]]
- [[Integral Domain]]
- [[Field]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Lang, Algebra

---

# <span class="header-definition">Definition</span>

## Polynomial Ring**^[다항식 환]

### Single Variable

Ring $R$에 대한 **polynomial ring**^[다항식 환] $R[x]$:

$$R[x] = \left\{ a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n : a_i \in R, n \geq 0 \right\}$$

**표기**: $R[x]$ (in variable $x$)

**원소**: Polynomials $f(x) = \displaystyle\sum_{i=0}^{n} a_i x^i$
- **Coefficients**^[계수]: $a_i \in R$
- **Indeterminate**^[미정원]: $x$ (formal symbol, not a number!)

### Multiple Variables

**여러 변수의 다항식 환**:

$$R[x_1, x_2, \ldots, x_n] = R[x_1][x_2] \cdots [x_n]$$

**예**: $R[x, y, z]$ = polynomials in three variables

**구조**: $(R[x])[y]$ = polynomials in $y$ with coefficients in $R[x]$

## Operations

### Addition

Coefficient-wise^[계수별]:

$$\left(\sum_{i} a_i x^i\right) + \left(\sum_{i} b_i x^i\right) = \sum_{i} (a_i + b_i) x^i$$

### Multiplication

Convolution of coefficients^[계수의 합성곱]:

$$\left(\sum_{i} a_i x^i\right) \cdot \left(\sum_{j} b_j x^j\right) = \sum_{k} \left(\sum_{i+j=k} a_i b_j\right) x^k$$

**예**:
$$(2 + 3x)(1 + x) = 2 \cdot 1 + (2 \cdot 1 + 3 \cdot 1)x + 3 \cdot 1 \cdot x^2 = 2 + 5x + 3x^2$$

## Degree

Polynomial $f(x) = a_0 + a_1 x + \cdots + a_n x^n$ (with $a_n \neq 0$)의 **degree**^[차수]:

$$\deg(f) = n$$

**Conventions**:
- $\deg(0) = -\infty$ (zero polynomial)
- **Leading coefficient**^[최고차 계수]: $a_n$
- **Monic**^[수석]: Leading coefficient = $1$

### Properties of Degree

1. $\deg(f + g) \leq \max(\deg(f), \deg(g))$

2. $\deg(fg) \leq \deg(f) + \deg(g)$

3. **If $R$ is integral domain**^[정역인 경우]:
   $$\deg(fg) = \deg(f) + \deg(g)$$

**증명** (3): $f, g \neq 0$이면
- Leading coefficients: $a_n, b_m \neq 0$
- $(fg)$의 leading coefficient = $a_n b_m \neq 0$ (no zero divisors)
- 따라서 $\deg(fg) = n + m = \deg(f) + \deg(g)$ 
## Universal Property

**정리**: Polynomial ring $R[x]$는 다음 universal property를 만족:

Ring $S$와 ring homomorphism $\phi: R \to S$, 그리고 $s \in S$가 주어지면, unique homomorphism $\Phi: R[x] \to S$ exists:

$$\Phi\left(\sum a_i x^i\right) = \sum \phi(a_i) s^i$$

$$\begin{array}{ccc}
R & \xrightarrow{\phi} & S \\
\downarrow & \nearrow_{\exists! \Phi} & \\
R[x] & &
\end{array}$$

**의미**: "$x$를 $s$로 대입" (evaluation homomorphism)

---

# <span class="header-properties">Properties</span>

## Ring Structure

### Theorem: $R[x]$ is a Ring

$R[x]$는 ring:
1. **Abelian group under addition**^[덧셈에 대한 아벨군]:    - Zero: $0$ (zero polynomial)
   - Additive inverse: $-f(x) = \sum (-a_i) x^i$

2. **Monoid under multiplication**^[곱셈에 대한 모노이드]:    - Identity: $1$ (constant polynomial)
   - Associativity: 
3. **Distributivity**^[분배법칙]: 
### Commutativity

**정리**: $R$ commutative $\Rightarrow$ $R[x]$ commutative

**증명**: Coefficient multiplication commutes 
## Units in Polynomial Rings

### Theorem: Units of $R[x]$

$$R[x]^\times = R^\times$$

**증명**: $f(x)g(x) = 1$이면
- $\deg(f) + \deg(g) = \deg(1) = 0$
- 따라서 $\deg(f) = \deg(g) = 0$
- $f, g$는 constant polynomials in $R^\times$ 
**결론**: Polynomial ring의 units = coefficient ring의 units (as constants)

**예**:
- $\mathbb{Z}[x]^\times = \{\pm 1\}$
- $\mathbb{Q}[x]^\times = \mathbb{Q}^\times = \mathbb{Q} \setminus \{0\}$
- $(\mathbb{Z}/6\mathbb{Z})[x]^\times = (\mathbb{Z}/6\mathbb{Z})^\times = \{\overline{1}, \overline{5}\}$

## Integral Domains

### Theorem

$$R \text{ integral domain} \quad \Leftrightarrow \quad R[x] \text{ integral domain}$$

**증명**:

($\Rightarrow$) $f, g \in R[x]$ nonzero이면
- Leading coefficients $a_n, b_m \neq 0$
- $(fg)$의 leading coefficient = $a_n b_m \neq 0$ (no zero divisors in $R$)
- 따라서 $fg \neq 0$ 
($\Leftarrow$) $R \subseteq R[x]$ (constant polynomials)
- $R[x]$ integral domain $\Rightarrow$ $R$ integral domain 
### Corollary

Field $k$에 대해:
$$k[x], \quad k[x, y], \quad k[x_1, \ldots, x_n]$$

모두 integral domains

## Irreducibility

Polynomial $f \in R[x]$ (nonzero, non-unit)가 **irreducible**^[기약]이다 $\Leftrightarrow$

$$f = gh \quad \Rightarrow \quad g \in R[x]^\times \text{ or } h \in R[x]^\times$$

**의미**: Nontrivial factorization이 불가능

**예** ($\mathbb{Q}[x]$):
- $x^2 - 2$ is irreducible
- $x^2 - 1 = (x-1)(x+1)$ is reducible

## Content and Primitive Polynomials

### Content (for $R = \text{UFD}$)

Polynomial $f(x) = a_0 + a_1 x + \cdots + a_n x^n \in R[x]$의 **content**^[용량]:

$$\text{cont}(f) = \gcd(a_0, a_1, \ldots, a_n)$$

### Primitive Polynomial

$f \in R[x]$가 **primitive**^[원시]이다 $\Leftrightarrow$ $\text{cont}(f) = 1$

**의미**: 계수들의 gcd가 1 (no common factor)

### Gauss's Lemma

**정리** ($R = \text{UFD}$): Primitive polynomials의 곱은 primitive

$$f, g \text{ primitive} \quad \Rightarrow \quad fg \text{ primitive}$$

**응용**: $R[x]$의 irreducibility를 $\text{Frac}(R)[x]$에서 테스트 가능

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}[x]$

**Integer coefficient polynomials**:

$$\mathbb{Z}[x] = \{a_0 + a_1 x + \cdots + a_n x^n : a_i \in \mathbb{Z}\}$$

**Properties**:
- Commutative - Integral domain - UFD - **NOT PID** ✗

**Units**: $\mathbb{Z}[x]^\times = \{\pm 1\}$

**Non-principal ideal**: $\langle 2, x \rangle$ (not generated by single element)

## Example 2: $k[x]$ (Field $k$)

**Polynomials over field**:

$$k[x] = \{a_0 + a_1 x + \cdots + a_n x^n : a_i \in k\}$$

**Properties**:
- Commutative - Integral domain - **PID**  (Principal Ideal Domain)
- **Euclidean domain** - UFD - Noetherian 
**Units**: $k[x]^\times = k^\times = k \setminus \{0\}$ (nonzero constants)

**Division algorithm**: Exists! (like $\mathbb{Z}$)

$$f(x) = q(x) g(x) + r(x), \quad \deg(r) < \deg(g)$$

### 정리: $k[x]$ is PID

Every ideal $I \triangleleft k[x]$는 principal:

$$I = \langle f(x) \rangle$$

where $f(x)$ = monic polynomial of minimal degree in $I$

**증명**: Division algorithm 
### 정리: $k[x]$ is UFD

Every $f \in k[x]$ factors uniquely:

$$f(x) = a \cdot p_1(x)^{e_1} \cdots p_r(x)^{e_r}$$

where $p_i$ are irreducible (up to associates)

## Example 3: $\mathbb{Q}[x]$

**Rational coefficient polynomials**:

$$\mathbb{Q}[x] = \left\{ \frac{a_0}{b_0} + \frac{a_1}{b_1} x + \cdots : a_i, b_i \in \mathbb{Z}, b_i \neq 0 \right\}$$

**Properties**: Same as $k[x]$ (field)

**Irreducibility test**: Eisenstein's criterion, rational root theorem

**예**:
- $x^2 - 2$ is irreducible over $\mathbb{Q}$
- $x^2 - 1 = (x-1)(x+1)$ is reducible

## Example 4: $\mathbb{R}[x]$, $\mathbb{C}[x]$

**Real/Complex polynomials**:

$$\mathbb{R}[x], \quad \mathbb{C}[x]$$

**Fundamental Theorem of Algebra**: $\mathbb{C}[x]$에서
- Every nonconstant polynomial has a root
- **Irreducibles**: Linear polynomials only! ($ax + b$)

**$\mathbb{R}[x]$에서**:
- **Irreducibles**: Linear or quadratic with no real roots
  - $x - a$
  - $x^2 + bx + c$ (with $b^2 - 4c < 0$)

## Example 5: $k[x, y]$ (Multivariate)

**Two-variable polynomials**:

$$k[x, y] = k[x][y]$$

**Properties**:
- Commutative - Integral domain - UFD - Noetherian - **NOT PID** ✗

**Non-principal ideal**: $\langle x, y \rangle$

**Applications**: Algebraic geometry (affine varieties)

**예**:
- $x^2 + y^2 - 1$ (circle)
- $y - x^2$ (parabola)

## Example 6: $\mathbb{Z}/6\mathbb{Z}[x]$

**Polynomials over ring with zero divisors**:

$$(\mathbb{Z}/6\mathbb{Z})[x] = \{\overline{a_0} + \overline{a_1} x + \cdots : a_i \in \mathbb{Z}/6\mathbb{Z}\}$$

**Properties**:
- Commutative - **NOT integral domain** ✗

**Zero divisors**: $(\overline{2}x)(\overline{3}) = \overline{0}$

**Units**: $(\mathbb{Z}/6\mathbb{Z})[x]^\times = \{\overline{1}, \overline{5}\}$

---

# <span class="header-properties">Special Results</span>

## Division Algorithm (for $k[x]$)

**정리**: Field $k$와 $f, g \in k[x]$ (with $g \neq 0$)에 대해, unique $q, r \in k[x]$ exist:

$$f(x) = q(x) g(x) + r(x)$$

with $\deg(r) < \deg(g)$ or $r = 0$

**증명**: Euclidean algorithm (leading coefficient 나누기)

**응용**:
- $k[x]$ is Euclidean domain
- $\gcd$ computation
- Polynomial interpolation

## Euclidean Algorithm

Field $k$에 대해 $k[x]$는 **Euclidean domain**^[유클리드 정역]:

**Norm function**: $N(f) = \deg(f)$

$$f = qg + r, \quad \deg(r) < \deg(g)$$

**GCD computation**: $\gcd(f, g)$ via Euclidean algorithm

자세한 내용은 [[Euclidean Domain]] 참조

## Hilbert Basis Theorem

**정리**: $R$ Noetherian $\Rightarrow$ $R[x]$ Noetherian

**귀납적으로**: $R[x_1, \ldots, x_n]$ Noetherian if $R$ is

**응용**: Algebraic geometry (varieties의 ideals는 finitely generated)

자세한 내용은 [[Noetherian Ring]] 참조

## Primitive Element Theorem

Field extension $k \subseteq K$에 대해:

$$k[x]/(f(x)) \cong K$$

(under suitable conditions)

**의미**: Polynomial rings의 quotients는 field extensions를 만듦

자세한 내용은 [[Field Extension]] 참조

---

# <span class="header-examples">Quotient Rings</span>

## $k[x]/(f(x))$

Field $k$와 polynomial $f(x) \in k[x]$에 대한 **quotient ring**^[몫환]:

$$k[x]/(f(x)) = \{g(x) + (f(x)) : g \in k[x]\}$$

### Properties

**정리**: $f$ irreducible $\Leftrightarrow$ $k[x]/(f(x))$ is field

**예**:
1. $\mathbb{R}[x]/(x^2 + 1) \cong \mathbb{C}$
2. $\mathbb{Q}[x]/(x^2 - 2) \cong \mathbb{Q}[\sqrt{2}]$
3. $\mathbb{F}_2[x]/(x^2 + x + 1) \cong \mathbb{F}_4$ (finite field)

### Construction of Field Extensions

**방법**: Adjoin root of irreducible polynomial

$$k(\alpha) \cong k[x]/(f(x))$$

where $f(\alpha) = 0$

자세한 내용은 [[Field Extension]] 참조

## $\mathbb{Z}[x]/(f(x))$

**Not always integral domain**:

**예**: $\mathbb{Z}[x]/(x^2 - 1)$
- $(x-1)(x+1) = 0$ in quotient
- Has zero divisors

---

# <span class="header-properties">Structure Theory</span>

## Relation to Function Rings

### Polynomial Functions

Polynomial $f(x) \in R[x]$는 **function** $f: R \to R$ 정의:

$$f(a) = a_0 + a_1 a + \cdots + a_n a^n$$

**주의**: Distinct polynomials may define same function!

**예**: $\mathbb{Z}/2\mathbb{Z}[x]$에서
- $x^2 \neq x$ (as polynomials)
- $f(0) = 0, f(1) = 1$ (same function!)

### Evaluation Homomorphism

$a \in R$에 대한 **evaluation**^[계산]:

$$\text{ev}_a: R[x] \to R, \quad f(x) \mapsto f(a)$$

Ring homomorphism 
**Kernel**: $\ker(\text{ev}_a) = \{f : f(a) = 0\}$

자세한 내용은 [[Ring Homomorphism]] 참조

## Hierarchy

$$\text{Field} \subsetneq k[x] \subsetneq k(x) \subsetneq \overline{k(x)}$$

- $k$: Field
- $k[x]$: Polynomial ring (integral domain)
- $k(x)$: Field of rational functions (field of fractions)
- $\overline{k(x)}$: Algebraic closure

---

# <span class="header-remark">Remark</span>

## Importance in Algebra

Polynomial rings는 대수학의 핵심:

1. **Field Extensions**^[체 확대]: $k[x]/(f(x))$ 구성
2. **Algebraic Geometry**^[대수기하학]: Coordinate rings of varieties
3. **Representation Theory**^[표현론]: Modules over $k[x]$
4. **Number Theory**^[정수론]: Diophantine equations

## $x$ is Formal

**중요**: $x$는 **indeterminate**^[미정원] (formal symbol)
- NOT a number!
- NOT a variable in calculus sense!

**의미**: $x$는 단순히 "placeholder" (형식적 기호)

## Polynomials vs. Polynomial Functions

**구별**:
1. **Polynomials**: Formal expressions (elements of $R[x]$)
2. **Polynomial functions**: Functions $R \to R$

Infinite fields에서는 일치하지만, finite fields에서는 다를 수 있음!

## Applications

### 1. Algebraic Geometry

Polynomial equations define **algebraic varieties**^[대수적 다양체]:

$$V(f_1, \ldots, f_r) = \{(a_1, \ldots, a_n) : f_i(a_1, \ldots, a_n) = 0\}$$

### 2. Coding Theory

**Reed-Solomon codes**: Polynomials over finite fields

### 3. Cryptography

**Polynomial-based crypto**: AES, lattice-based cryptography

### 4. Computer Algebra

Symbolic computation systems (Mathematica, Maple, etc.)

