# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Ideal]]
- [[Prime Ideal]]
- [[Maximal Ideal]]

# <span class="header-reference">Reference</span>
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Eisenbud, Commutative Algebra with a View Toward Algebraic Geometry
- Dummit & Foote, Abstract Algebra

---

# <span class="header-definition">Definition</span>

## Radical of an Ideal**^[아이디얼의 근기]

Commutative ring $R$과 ideal $I \triangleleft R$에 대해, **radical of $I$**^[근기]:

$$\sqrt{I} = \{a \in R : a^n \in I \text{ for some } n \geq 1\}$$

**표기**: $\sqrt{I}$, $\text{rad}(I)$

**의미**: "거듭제곱하면 $I$에 들어가는" 원소들

**직관**: $I$의 "root" - 제곱근처럼 작동

## Radical Ideal**^[근기 아이디얼]

Ideal $I$가 **radical ideal**^[근기 아이디얼]이다 $\Leftrightarrow$ $I = \sqrt{I}$

즉:

$$a^n \in I \text{ for some } n \geq 1 \quad \Rightarrow \quad a \in I$$

**의미**: 거듭제곱이 들어있으면 원소 자체도 들어있음

**특징**: "이미 radical이 취해진" ideal

## Nilradical**^[멱영근기]

Ring $R$의 **nilradical**^[멱영근기]:

$$\text{Nil}(R) = \{a \in R : a^n = 0 \text{ for some } n \geq 1\}$$

**정리**: $\text{Nil}(R) = \sqrt{\{0\}}$ (radical of zero ideal)

**의미**: 모든 **nilpotent elements**^[멱영원]의 집합

자세한 내용은 [[Nilradical]] 참조

## Jacobson Radical**^[제이콥슨 근기]

Ring $R$의 **Jacobson radical**^[제이콥슨 근기]:

$$J(R) = \bigcap_{M \text{ maximal}} M$$

**의미**: 모든 maximal ideals의 교집합

**주의**: Jacobson radical $\neq$ Nilradical (일반적으로)

자세한 내용은 [[Jacobson Radical]] 참조

---

# <span class="header-properties">Properties</span>

## Basic Properties of $\sqrt{I}$

### 1. $\sqrt{I}$ is an Ideal

**정리**: $\sqrt{I} \triangleleft R$ (ideal)

**증명**:

**(a) $0 \in \sqrt{I}$**: $0^1 = 0 \in I$ ✓

**(b) Closed under subtraction**: $a, b \in \sqrt{I}$이면
- $a^n, b^m \in I$ for some $n, m$
- $(a - b)^{n+m} = \displaystyle\sum_{k=0}^{n+m} \binom{n+m}{k} a^k (-b)^{n+m-k}$
- 각 항이 $a^n$ 또는 $b^m$을 포함 (by pigeonhole)
- 따라서 $(a-b)^{n+m} \in I$ ✓

**(c) Closed under multiplication by $R$**: $a \in \sqrt{I}$, $r \in R$이면
- $a^n \in I$ for some $n$
- $(ra)^n = r^n a^n \in I$ (ideal property)
- 따라서 $ra \in \sqrt{I}$ ✓

### 2. $I \subseteq \sqrt{I}$

**증명**: $a \in I$이면 $a^1 = a \in I$, 따라서 $a \in \sqrt{I}$ ✓

### 3. $\sqrt{\sqrt{I}} = \sqrt{I}$

**정리**: Radical은 **idempotent**^[멱등]:

$$\sqrt{\sqrt{I}} = \sqrt{I}$$

**증명**:
- $\supseteq$: 자명 (Property 2)
- $\subseteq$: $a \in \sqrt{\sqrt{I}}$이면
  - $a^n \in \sqrt{I}$ for some $n$
  - $(a^n)^m \in I$ for some $m$
  - $a^{nm} \in I$
  - 따라서 $a \in \sqrt{I}$ ✓

**의미**: $\sqrt{I}$는 이미 radical ideal!

### 4. Monotonicity

**정리**: $I \subseteq J$ $\Rightarrow$ $\sqrt{I} \subseteq \sqrt{J}$

**증명**: $a \in \sqrt{I}$이면 $a^n \in I \subseteq J$, 따라서 $a \in \sqrt{J}$ ✓

### 5. Radical of Product

**정리**: $\sqrt{IJ} = \sqrt{I \cap J} = \sqrt{I} \cap \sqrt{J}$

**증명 핵심**: $a^n \in IJ \Rightarrow a^{2n} \in I \cap J$

### 6. Radical of Sum

**정리**: $\sqrt{I + J} = \sqrt{\sqrt{I} + \sqrt{J}}$

## Characterization via Prime Ideals

### 정리 (가장 중요!)

$$\sqrt{I} = \bigcap_{P \supseteq I, \; P \text{ prime}} P$$

**의미**: Radical = $I$를 포함하는 모든 prime ideals의 교집합

**증명**:

($\subseteq$) $a \in \sqrt{I}$이면 $a^n \in I$
- Prime ideal $P \supseteq I$에 대해
- $a^n = a \cdot a \cdots a \in P$
- Prime property: $a \in P$
- 따라서 $a \in \bigcap P$ ✓

($\supseteq$) $a \notin \sqrt{I}$이면
- $S = \{a^n : n \geq 1\}$ (multiplicative set)
- $S \cap I = \emptyset$ (by assumption)
- Zorn's Lemma: prime $P \supseteq I$ with $P \cap S = \emptyset$ exists
- $a \notin P$ (since $a^1 \in S$)
- 따라서 $a \notin \bigcap P$ ✓

**계**: $\sqrt{I}$는 smallest radical ideal containing $I$

## Radical and Quotients

### 정리

$$\sqrt{I/J} = \sqrt{I}/J \quad \text{(when } J \subseteq I \text{)}$$

More precisely:

$$\pi(\sqrt{I}) = \sqrt{\pi(I)}$$

where $\pi: R \to R/J$

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$

### (a) $\sqrt{\langle 12 \rangle}$

$$\sqrt{\langle 12 \rangle} = \sqrt{\langle 2^2 \cdot 3 \rangle} = \langle 6 \rangle = \langle 2 \cdot 3 \rangle$$

**이유**: $12 = 2^2 \cdot 3$의 square-free part = $6$

**확인**:
- $2 \in \sqrt{\langle 12 \rangle}$? $2^2 = 4 \nmid 12$, but $2^3 = 8$, $2^4 = 16$... Actually $2^2 = 4 \in \langle 12 \rangle$? No.
- Wait: $2^{\color{red}2} \cdot 3 = 12 \in \langle 12 \rangle$, but we need $2^n \in \langle 12 \rangle$...

Actually: $n \in \sqrt{\langle m \rangle}$ $\Leftrightarrow$ every prime factor of $n$ divides $m$

**Correct**: $\sqrt{\langle 12 \rangle} = \langle 6 \rangle$
- $6^2 = 36 = 3 \cdot 12 \in \langle 12 \rangle$ ✓
- $2 \in \sqrt{\langle 12 \rangle}$: $2^2 = 4$, but $12 = 4 \cdot 3$... Actually $2^3 = 8$, $2^4 = 16$... Hmm.

Let me reconsider: In $\mathbb{Z}$,

$$\sqrt{\langle n \rangle} = \langle \text{rad}(n) \rangle$$

where $\text{rad}(n)$ = product of distinct prime factors

So $\text{rad}(12) = \text{rad}(2^2 \cdot 3) = 2 \cdot 3 = 6$

Therefore $\sqrt{\langle 12 \rangle} = \langle 6 \rangle$ ✓

### (b) $\sqrt{\langle 0 \rangle}$

$$\sqrt{\langle 0 \rangle} = \text{Nil}(\mathbb{Z}) = \{0\}$$

**이유**: $\mathbb{Z}$는 integral domain (no nilpotents)

### (c) $\sqrt{\mathbb{Z}} = \mathbb{Z}$

Every ideal is radical ideal in $\mathbb{Z}$ (principal!)

Actually no: $\langle 4 \rangle$ is NOT radical ($2 \notin \langle 4 \rangle$ but $2^2 \in \langle 4 \rangle$)

**정정**: $\langle 4 \rangle$ is NOT radical, $\sqrt{\langle 4 \rangle} = \langle 2 \rangle$

## Example 2: $k[x]$ (Field $k$)

### (a) $\sqrt{\langle x^2 \rangle}$

$$\sqrt{\langle x^2 \rangle} = \langle x \rangle$$

**확인**: $(x)^2 = x^2 \in \langle x^2 \rangle$ ✓

### (b) $\sqrt{\langle x^2(x-1)^3 \rangle}$

$$\sqrt{\langle x^2(x-1)^3 \rangle} = \langle x(x-1) \rangle$$

**일반**: $\sqrt{\langle f \rangle} = \langle \text{square-free part of } f \rangle$

### (c) $\sqrt{\langle 0 \rangle}$

$$\sqrt{\langle 0 \rangle} = \{0\}$$

**이유**: $k[x]$ is integral domain

## Example 3: $\mathbb{Z}/12\mathbb{Z}$

### Nilradical

$$\text{Nil}(\mathbb{Z}/12\mathbb{Z}) = \langle \overline{6} \rangle = \{\overline{0}, \overline{6}\}$$

**확인**: $\overline{6}^2 = \overline{36} = \overline{0}$ ✓

### (a) $\sqrt{\langle \overline{4} \rangle}$

$$\sqrt{\langle \overline{4} \rangle} = \langle \overline{2} \rangle$$

**이유**: $\overline{2}^2 = \overline{4}$ ✓

### (b) $\sqrt{\langle \overline{0} \rangle}$

$$\sqrt{\langle \overline{0} \rangle} = \langle \overline{6} \rangle$$

Nilradical!

## Example 4: $k[x, y]$

### (a) $\sqrt{\langle x^2, xy \rangle}$

$$\sqrt{\langle x^2, xy \rangle} = \langle x \rangle$$

**증명**: 
- $x^2 \in I$ $\Rightarrow$ $x \in \sqrt{I}$ ✓
- Conversely: $\langle x \rangle \supseteq \langle x^2, xy \rangle$
- $\sqrt{\langle x \rangle} = \langle x \rangle$ (radical)
- By minimality: $\sqrt{I} = \langle x \rangle$ ✓

### (b) $\sqrt{\langle x^2, y^2 \rangle}$

$$\sqrt{\langle x^2, y^2 \rangle} = \langle x, y \rangle$$

**Geometric interpretation**: 
- $I = \langle x^2, y^2 \rangle$: Functions vanishing to order $\geq 2$ at origin
- $\sqrt{I} = \langle x, y \rangle$: Functions vanishing at origin

## Example 5: Product Ring

### $\mathbb{Z} \times \mathbb{Z}$

$I = \langle (2, 0) \rangle = \{(2a, 0) : a \in \mathbb{Z}\}$

$$\sqrt{I} = \mathbb{Z} \times \{0\}$$

**확인**: $(a, 0)^2 = (a^2, 0) \in I$ requires $2 | a^2$...

Actually: $(1, 0)^n = (1, 0) \notin I$ for all $n$.

**정정**: $\sqrt{\langle (2, 0) \rangle} = \langle (2, 0) \rangle$ (already radical? Let's check)

If $(a, b) \in \sqrt{I}$, then $(a, b)^n = (a^n, b^n) \in I$ for some $n$.

So $a^n = 2k$ and $b^n = 0$.

Therefore $b = 0$ and $2 | a^n$, so $2 | a$ (in $\mathbb{Z}$, since square-free).

Actually more carefully: $b^n = 0$ $\Rightarrow$ $b = 0$ ✓

$a^n \in 2\mathbb{Z}$ $\Rightarrow$ $a \in \sqrt{2\mathbb{Z}} = 2\mathbb{Z}$ ✓

Therefore $\sqrt{I} = 2\mathbb{Z} \times \{0\}$ ✓

---

# <span class="header-properties">Special Cases and Characterizations</span>

## Radical Ideals

### 정리: Prime $\Rightarrow$ Radical

Every prime ideal is radical

**증명**: $P$ prime이고 $a^n \in P$이면
- $a \cdot a \cdots a \in P$ ($n$ times)
- Prime property (repeatedly): $a \in P$ ✓

### 정리: Intersection of Primes is Radical

$$\sqrt{I} = \bigcap_{P \supseteq I, \; P \text{ prime}} P$$

따라서 $\sqrt{I}$는 radical ideal ✓

### Examples of Radical Ideals

**In $\mathbb{Z}$**:
- $\langle p \rangle$ (prime): radical ✓
- $\langle p^2 \rangle$: NOT radical ✗
- $\langle pq \rangle$ (distinct primes): radical ✓

**In $k[x]$**:
- $\langle x \rangle$: radical ✓
- $\langle x^2 \rangle$: NOT radical ✗
- $\langle (x-1)(x-2) \rangle$: radical ✓

**In $k[x, y]$**:
- $\langle x, y \rangle$: radical ✓
- $\langle x^2, y \rangle$: NOT radical ✗

## Nilradical Characterization

### 정리

$$\text{Nil}(R) = \sqrt{\{0\}} = \bigcap_{P \text{ prime}} P$$

**의미**: Nilradical = intersection of ALL prime ideals

**증명**: Apply general theorem with $I = \{0\}$ ✓

### 정리: Nilradical in Quotient

$$\text{Nil}(R/I) = \sqrt{I}/I$$

**의미**: Nilpotents in quotient = image of $\sqrt{I}$

## Reduced Rings

### 정의

Ring $R$이 **reduced**^[기약]이다 $\Leftrightarrow$ $\text{Nil}(R) = \{0\}$

즉, no nonzero nilpotents

**동치**: $\sqrt{\{0\}} = \{0\}$

### Examples

**Reduced**:
- $\mathbb{Z}$ ✓
- $k[x]$ (integral domain) ✓
- $\mathbb{Z} \times \mathbb{Z}$ ✓

**NOT Reduced**:
- $\mathbb{Z}/4\mathbb{Z}$ ✗ ($\overline{2}^2 = \overline{0}$)
- $k[x]/\langle x^2 \rangle$ ✗ ($\overline{x}^2 = 0$)
- $\mathbb{Z}/12\mathbb{Z}$ ✗ ($\overline{6}^2 = \overline{0}$)

### 정리: Reduced $\Leftrightarrow$ Intersection of Domains

$R$ is reduced $\Leftrightarrow$ $R$ embeds into product of integral domains

---

# <span class="header-examples">Applications</span>

## Algebraic Geometry

### Varieties and Radicals

**Coordinate ring**: $k[x_1, \ldots, x_n]/I$

**Variety**: $V(I) = \{(a_1, \ldots, a_n) : f(a_i) = 0 \; \forall f \in I\}$

### Hilbert's Nullstellensatz

**정리**: Over algebraically closed field $k$,

$$I(V(I)) = \sqrt{I}$$

**의미**: 
- $I$와 $\sqrt{I}$는 같은 variety를 정의
- Geometric objects는 radical ideals에 대응

자세한 내용은 [[Nullstellensatz]] 참조

### Example

$I = \langle x^2, xy \rangle \triangleleft \mathbb{C}[x, y]$

- $V(I) = \{(0, b) : b \in \mathbb{C}\}$ (y-axis)
- $\sqrt{I} = \langle x \rangle$
- $V(\sqrt{I}) = V(I)$ ✓

**의미**: $x^2 = 0$과 $x = 0$은 같은 locus!

## Commutative Algebra

### Primary Decomposition

**Lasker-Noether Theorem**: Noetherian ring에서 ideal은 primary ideals로 분해

$$I = Q_1 \cap Q_2 \cap \cdots \cap Q_n$$

**Associated primes**: $P_i = \sqrt{Q_i}$

$$\sqrt{I} = \sqrt{Q_1} \cap \cdots \cap \sqrt{Q_n} = P_1 \cap \cdots \cap P_r$$

자세한 내용은 [[Primary Decomposition]] 참조

## Minimal Primes

### 정의

Prime ideal $P$가 **minimal prime over $I$**^[최소 소 아이디얼]이다 $\Leftrightarrow$
- $P \supseteq I$
- $P' \supseteq I$ and $P'$ prime $\Rightarrow$ $P' \supseteq P$

### 정리

$$\sqrt{I} = \bigcap_{\text{minimal primes over } I} P$$

Finite intersection suffices (in Noetherian rings)!

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### Radical = "Square-free Part"

**In $\mathbb{Z}$**:

$$\sqrt{\langle n \rangle} = \langle \text{rad}(n) \rangle$$

where $\text{rad}(n)$ = product of distinct prime divisors

**예**: 
- $\sqrt{\langle 12 \rangle} = \langle 6 \rangle$
- $\sqrt{\langle 100 \rangle} = \langle 10 \rangle$

### Geometric Intuition

**Algebraic Geometry**:

$\sqrt{I}$ removes "multiplicity"

- $I = \langle x^2 \rangle$: Line with multiplicity 2
- $\sqrt{I} = \langle x \rangle$: Simple line

**Nullstellensatz**: $V(I) = V(\sqrt{I})$ (same geometric locus)

## 계산 방법

### Method 1: Factorization

**In $\mathbb{Z}$**: $\sqrt{\langle n \rangle} = \langle \text{rad}(n) \rangle$

**In $k[x]$**: $\sqrt{\langle f \rangle} = \langle \text{square-free part} \rangle$

### Method 2: Prime Decomposition

$$\sqrt{I} = \bigcap_{\text{minimal primes over } I} P_i$$

Find minimal primes, then intersect

### Method 3: Gröbner Basis

For polynomial rings, use Gröbner basis algorithms

## Common Pitfalls

### 1. $\sqrt{I + J} \neq \sqrt{I} + \sqrt{J}$ (generally)

**Counter-example**: $\mathbb{Z}$에서
- $I = \langle 2 \rangle$, $J = \langle 3 \rangle$
- $\sqrt{I} + \sqrt{J} = \langle 2 \rangle + \langle 3 \rangle = \langle 1 \rangle = \mathbb{Z}$
- $\sqrt{I + J} = \sqrt{\langle 1 \rangle} = \mathbb{Z}$ ✓

Actually this works! But in general:

$k[x, y]$에서:
- $I = \langle x^2 \rangle$, $J = \langle y^2 \rangle$
- $\sqrt{I} + \sqrt{J} = \langle x \rangle + \langle y \rangle = \langle x, y \rangle$ ✓
- $\sqrt{I + J} = \sqrt{\langle x^2, y^2 \rangle} = \langle x, y \rangle$ ✓

Hmm, seems to work... Actually:

$$\sqrt{I + J} = \sqrt{\sqrt{I} + \sqrt{J}}$$

So they have same radical!

### 2. Nilradical $\neq$ Jacobson Radical (generally)

**Example**: $\mathbb{Z}$
- $\text{Nil}(\mathbb{Z}) = \{0\}$
- $J(\mathbb{Z}) = \bigcap_{p \text{ prime}} \langle p \rangle = \{0\}$

Same here! But in general different.

**Example**: $k[x]_{(x)}$ (localization at $\langle x \rangle$)
- $\text{Nil} = \{0\}$
- $J = \langle x \rangle_{(x)}$ (unique maximal)

### 3. $\sqrt{IJ} \neq \sqrt{I} \cdot \sqrt{J}$ (generally)

**Truth**: $\sqrt{IJ} = \sqrt{I \cap J} = \sqrt{I} \cap \sqrt{J}$

## 관련 개념

- [[Ideal]]: General concept
- [[Prime Ideal]]: Building blocks of radicals
- [[Maximal Ideal]]: For Jacobson radical
- [[Nilradical]]: Special case $\sqrt{\{0\}}$
- [[Jacobson Radical]]: Different type of radical
- [[Nullstellensatz]]: Geometric application
- [[Primary Decomposition]]: Generalization
- [[Reduced Ring]]: Trivial nilradical

