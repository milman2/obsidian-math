# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Commutative Ring]]
- [[Ideal]]
- [[Field]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra

---

# <span class="header-definition">Definition</span>

## Integral Domain**^[정역]

Commutative ring**^[가환환] $R$ (with identity $1 \neq 0$)이 **integral domain**^[정역]이다 $\Leftrightarrow$ **zero divisor**^[영인자]가 없음

즉:

$$ab = 0 \quad \Rightarrow \quad a = 0 \text{ or } b = 0$$

**직관**: "정수처럼" 작동하는 환 - 0이 아닌 두 수를 곱하면 0이 아님

### 조건 요약

1. **Commutative**: $ab = ba$
2. **Identity**: $\exists 1 \neq 0$
3. **No zero divisors**: $ab = 0 \Rightarrow a = 0$ or $b = 0$

## Equivalent Characterizations

다음은 모두 동치:

**1. Definition**: Zero divisor가 없음
$$ab = 0 \Rightarrow a = 0 \text{ or } b = 0$$

**2. Cancellation Law**^[소거법칙]: 
$$ab = ac \text{ and } a \neq 0 \quad \Rightarrow \quad b = c$$

**3. Left/Right cancellation**: 양쪽 모두 성립
$$ab = ac, \; a \neq 0 \Rightarrow b = c$$
$$ba = ca, \; a \neq 0 \Rightarrow b = c$$

**증명 (1 $\Leftrightarrow$ 2)**:

($\Rightarrow$) $ab = ac$이고 $a \neq 0$이면
- $ab - ac = 0$
- $a(b - c) = 0$
- No zero divisors: $a \neq 0$ $\Rightarrow$ $b - c = 0$
- 따라서 $b = c$ 
($\Leftarrow$) $ab = 0$이고 $a \neq 0$이면
- $ab = a \cdot 0$
- Cancellation: $b = 0$ 
---

# <span class="header-properties">Properties</span>

## Characteristic

### 정리

Integral domain $R$의 **characteristic**^[표수] $\text{char}(R)$는 **0 또는 prime**

$$\text{char}(R) = 0 \quad \text{or} \quad \text{char}(R) = p \text{ (prime)}$$

### 증명

$\text{char}(R) = n > 0$이라 가정. $n = mk$로 분해하면 ($1 < m, k < n$):
- $n \cdot 1 = 0$
- $(m \cdot 1)(k \cdot 1) = mk \cdot 1 = n \cdot 1 = 0$
- 그런데 $m \cdot 1 \neq 0$, $k \cdot 1 \neq 0$ (minimality of $n$)
- Zero divisor 발생! ✗

따라서 $n$은 prime이어야 함 
## Multiplicative Cancellation

Integral domain에서 곱셈은 **injective**^[단사]:

$$a \neq 0 \Rightarrow \text{multiplication by } a \text{ is injective}$$

**의미**: $f_a: R \to R$, $f_a(x) = ax$는 단사함수

## No Proper Zero Divisors

Integral domain $R$에서:
- **Units**^[단원] $R^\times$: 곱셈 역원을 가진 원소들
- **Zero divisors**: 없음! (정의상)
- **Nilpotents**^[멱영원]: $0$만 존재

$$\text{Nil}(R) = \{a : \exists n, a^n = 0\} = \{0\}$$

**증명**: $a^n = 0$이면 $a \cdot a^{n-1} = 0$. No zero divisors $\Rightarrow$ $a = 0$ 
## Polynomial Rings

Integral domain $R$에 대해:

$$R \text{ is integral domain} \quad \Rightarrow \quad R[x] \text{ is integral domain}$$

**증명**: $f, g \in R[x]$ nonzero이면
- Leading coefficient: $a_n, b_m \neq 0$
- $(fg)$의 leading coefficient = $a_n b_m \neq 0$ (no zero divisors in $R$)
- 따라서 $fg \neq 0$ 
**귀납적으로**: $R[x_1, \ldots, x_n]$도 integral domain

---

# <span class="header-examples">Examples</span>

## Examples of Integral Domains

### 1. Fields

**정리**: Every field is an integral domain

**증명**: $ab = 0$이고 $a \neq 0$이면
- $a^{-1}$ exists (field)
- $b = a^{-1}(ab) = a^{-1} \cdot 0 = 0$ 
**예**:
- $\mathbb{Q}$, $\mathbb{R}$, $\mathbb{C}$ (fields)
- $\mathbb{Z}/p\mathbb{Z}$ ($p$ prime)
- $\mathbb{F}_q$ (finite field)

### 2. Integers

$\mathbb{Z}$ is an integral domain:
- Commutative - Identity: $1$ - No zero divisors 
### 3. Gaussian Integers

$$\mathbb{Z}[i] = \{a + bi : a, b \in \mathbb{Z}\}$$

Integral domain (norm argument)

### 4. Polynomial Rings

Field $k$에 대해:
- $k[x]$: polynomial ring over $k$
- $k[x_1, \ldots, x_n]$: multivariate polynomials

모두 integral domains

### 5. Subrings of Fields

**정리**: Field의 subring은 integral domain

**예**: $\mathbb{Z} \subseteq \mathbb{Q}$

## Non-Examples

### 1. Modular Arithmetic (Composite Modulus)

$\mathbb{Z}/6\mathbb{Z}$:
$$\overline{2} \cdot \overline{3} = \overline{0}$$

Zero divisors exist ✗

**일반**: $\mathbb{Z}/n\mathbb{Z}$는 integral domain $\Leftrightarrow$ $n$ is prime

### 2. Zero Ring

$R = \{0\}$: identity $1 = 0$ (excluded by definition)

### 3. Matrix Rings

$M_n(R)$ for $n \geq 2$:
- Not commutative ✗
- Has zero divisors

**예**: $M_2(\mathbb{R})$에서
$$\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$$

### 4. Product Rings

$R \times S$ (with $|R|, |S| > 1$):
$$(1, 0) \cdot (0, 1) = (0, 0)$$

Zero divisors exist ✗

### 5. Non-commutative Rings

Division ring (skew field)은 zero divisor는 없지만 **commutative**가 아니므로 정역이 아님

**예**: Quaternions $\mathbb{H}$

---

# <span class="header-properties">Structure Theory</span>

## Field of Fractions

### 정리

Every integral domain $R$은 field $F$에 **embedded**^[매장]될 수 있음:

$$R \hookrightarrow F$$

이 $F$를 **field of fractions**^[분수체] 또는 **quotient field**^[몫체]라 함

**표기**: $\text{Frac}(R)$, $\text{Quot}(R)$

### 구성

$R$의 원소들의 "formal fractions":

$$F = \left\{ \frac{a}{b} : a, b \in R, b \neq 0 \right\} / \sim$$

**동치관계**:
$$\frac{a}{b} \sim \frac{c}{d} \quad \Leftrightarrow \quad ad = bc$$

**예**:
- $\text{Frac}(\mathbb{Z}) = \mathbb{Q}$
- $\text{Frac}(k[x]) = k(x)$ (rational functions)
- $\text{Frac}(\mathbb{Z}[i]) = \mathbb{Q}[i]$

### Universal Property

Field $K$와 ring homomorphism $\phi: R \to K$가 주어지면, unique homomorphism $\Phi: F \to K$ exists:

$$\begin{array}{ccc}
R & \xrightarrow{\phi} & K \\
\downarrow & \nearrow_{\exists! \Phi} & \\
F & &
\end{array}$$

## Ideals in Integral Domains

### Prime Ideals

Integral domain $R$의 proper ideal $P$에 대해:

$$P \text{ is prime} \quad \Leftrightarrow \quad R/P \text{ is integral domain}$$

자세한 내용은 [[Prime Ideal]] 참조

### Maximal Ideals

$$M \text{ is maximal} \quad \Leftrightarrow \quad R/M \text{ is field}$$

**정리**: Maximal ideal $\Rightarrow$ Prime ideal (in integral domains)

자세한 내용은 [[Maximal Ideal]] 참조

---

# <span class="header-examples">Special Classes</span>

## Hierarchy of Integral Domains

다음은 포함 관계:

$$\text{Field} \subsetneq \text{Euclidean Domain} \subsetneq \text{PID} \subsetneq \text{UFD} \subsetneq \text{Integral Domain}$$

### Euclidean Domain**^[유클리드 정역]

- Euclidean algorithm이 작동하는 integral domain
- **예**: $\mathbb{Z}$, $k[x]$, $\mathbb{Z}[i]$

자세한 내용은 [[Euclidean Domain]] 참조

### PID (Principal Ideal Domain)**^[주 아이디얼 정역]

- 모든 ideal이 principal인 integral domain
- **예**: $\mathbb{Z}$, $k[x]$ (field $k$)

**정리**: Euclidean domain $\Rightarrow$ PID

자세한 내용은 [[Principal Ideal Domain]] 참조

### UFD (Unique Factorization Domain)**^[유일 인수분해 정역]

- 모든 원소가 irreducibles로 uniquely factor되는 integral domain
- **예**: $\mathbb{Z}$, $k[x_1, \ldots, x_n]$

**정리**: PID $\Rightarrow$ UFD

자세한 내용은 [[Unique Factorization Domain]] 참조

### Noetherian Domain**^[뇌터 정역]

- Ascending chain condition on ideals를 만족하는 integral domain

자세한 내용은 [[Noetherian Ring]] 참조

---

# <span class="header-remark">Remark</span>

## Importance in Algebra

Integral domains는 **algebraic number theory**^[대수적 수론]와 **algebraic geometry**^[대수기하학]의 핵심:

1. **Number Theory**: Rings of integers in number fields
   - $\mathbb{Z}$, $\mathbb{Z}[i]$, $\mathbb{Z}[\sqrt{-5}]$

2. **Algebraic Geometry**: Coordinate rings of varieties
   - $k[x_1, \ldots, x_n]/I$ (often integral domains)

3. **Commutative Algebra**: Study of ideals and modules

## Why "Integral"?

**이름의 유래**: "Integral" = "완전한", "온전한"

영인자가 없어서 곱셈이 "온전하게" 작동함 (0이 아닌 것끼리 곱해도 0이 안 됨)

독일어 "ganz" (whole, complete)에서 유래 → integral domain

## Relation to Fields

**핵심 정리들**:

1. Every field is an integral domain
2. Every finite integral domain is a field
3. Every integral domain embeds into its field of fractions

**Field와의 차이**: 
- Field: 모든 nonzero 원소가 unit
- Integral domain: 일부만 unit일 수 있음
  - 예: $\mathbb{Z}$의 units = $\{\pm 1\}$ only

## Cancellation in Practice

Integral domain에서 방정식 풀이:

$$ax = ay \text{ and } a \neq 0 \quad \Rightarrow \quad x = y$$

**주의**: General rings에서는 불가능!

예: $\mathbb{Z}/6\mathbb{Z}$에서
$$2 \cdot 1 = 2 \cdot 4 \quad \text{but} \quad 1 \neq 4$$

