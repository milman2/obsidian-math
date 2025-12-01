# <span class="header-prerequisite">Prerequisite</span>
- [[Field]]
- [[Ring]]
- [[Group]]
- [[Polynomial Ring]]
- [[Irreducible Polynomial]]
- [[Cyclic Group]]

# <span class="header-reference">Reference</span>
- Lidl & Niederreiter, Finite Fields
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Finite Field^[유한체]

Field^[체] $\mathbb{F}$가 **finite field^[유한체]** (또는 **Galois field^[갈루아체]**)이다 $\Leftrightarrow$ $|\mathbb{F}| < \infty$

**표기**: $\mathbb{F}_q$ 또는 $GF(q)$ where $q = |\mathbb{F}|$

**핵심 성질**: 모든 finite field는 특별한 구조를 가짐

## Characteristic^[표수]

Field $\mathbb{F}$의 **characteristic^[표수]** $\text{char}(\mathbb{F})$:

$$\text{char}(\mathbb{F}) = \begin{cases}
\min\{n > 0 : n \cdot 1 = 0\} & \text{if exists} \\
0 & \text{otherwise}
\end{cases}$$

**정리**: Field의 characteristic는 $0$ 또는 prime

**Finite field**: $\text{char}(\mathbb{F}) = p$ (some prime)

## Prime Subfield^[소체]

Field $\mathbb{F}$의 **prime subfield^[소체]**:

모든 subfield의 교집합 = 최소 subfield

**Finite field의 경우**:
- $\text{char}(\mathbb{F}) = p$ (prime)
- Prime subfield $\cong \mathbb{F}_p = \mathbb{Z}/p\mathbb{Z}$

## Order^[위수]

Finite field $\mathbb{F}$의 **order^[위수]**: $q = |\mathbb{F}|$

**정리**: $q = p^n$ where $p = \text{char}(\mathbb{F})$, $n = [\mathbb{F} : \mathbb{F}_p]$

---

# <span class="header-theorem">Theorems</span>

## Existence and Uniqueness^[존재성과 유일성]

**정리**: Prime power $q = p^n$ (where $p$ prime, $n \geq 1$)에 대해:

1. **Existence^[존재성]**: Order $q$인 finite field 존재
2. **Uniqueness^[유일성]**: Order $q$인 모든 finite field는 isomorphic^[동형]

**표기**: Unique field (up to isomorphism) = $\mathbb{F}_q$ 또는 $\mathbb{F}_{p^n}$

**증명 개요**:
- **Existence**: $\mathbb{F}_q$는 $x^q - x$의 splitting field^[분해체]
- **Uniqueness**: Splitting field의 유일성

## Structure of Multiplicative Group^[곱셈군의 구조]

**정리**: $\mathbb{F}_q^\times = \mathbb{F}_q \setminus \{0\}$는 **cyclic group^[순환군]**

$$\mathbb{F}_q^\times \cong C_{q-1}$$

**중요성**: Multiplicative group이 cyclic이므로 **generator 존재**!

### Primitive Element^[원시 원소]

$\alpha \in \mathbb{F}_q^\times$가 **primitive element^[원시 원소]** (또는 **generator^[생성원]**)이다 $\Leftrightarrow$

$$\mathbb{F}_q^\times = \langle \alpha \rangle = \{1, \alpha, \alpha^2, \ldots, \alpha^{q-2}\}$$

**Order**: $|\alpha| = q - 1$

**개수**: $\phi(q-1)$개 (Euler's totient function)

## Frobenius Endomorphism^[프로베니우스 자기준동형사상]

**정의**: Characteristic $p$ field에서:

$$\text{Frob}: \mathbb{F}_q \to \mathbb{F}_q, \quad \text{Frob}(x) = x^p$$

**성질**:

1. **Field homomorphism^[체 준동형사상]**:
   - $(x + y)^p = x^p + y^p$ (characteristic $p$에서 binomial expansion)
   - $(xy)^p = x^p y^p$

2. **Automorphism**: Finite field에서 injective $\Rightarrow$ surjective

3. **Order**: $\text{Frob}^n = \text{id}$ where $q = p^n$

4. **Cyclic**: $\langle \text{Frob} \rangle = \text{Gal}(\mathbb{F}_q / \mathbb{F}_p)$

## Subfield Structure^[부분체 구조]

**정리**: Subfield lattice^[부분체 격자]

$$\mathbb{F}_{p^m} \subseteq \mathbb{F}_{p^n} \quad \Leftrightarrow \quad m \mid n$$

**직관**: $\mathbb{F}_{p^n}$의 모든 subfield는 $\mathbb{F}_{p^d}$ 형태 (where $d \mid n$)

**개수**: $n$의 divisor 개수 = $\mathbb{F}_{p^n}$의 subfield 개수

### Example

$\mathbb{F}_{2^{12}}$의 subfields:
- $\mathbb{F}_2$ ($2^1$)
- $\mathbb{F}_4$ ($2^2$)
- $\mathbb{F}_8$ ($2^3$)
- $\mathbb{F}_{16}$ ($2^4$)
- $\mathbb{F}_{64}$ ($2^6$)
- $\mathbb{F}_{4096}$ ($2^{12}$)

Divisors of 12: $\{1, 2, 3, 4, 6, 12\}$ → 6개 subfields

## Primitive Polynomial^[원시 다항식]

**정리**: $\mathbb{F}_{p^n} \cong \mathbb{F}_p[x]/(f(x))$ 

where $f(x) \in \mathbb{F}_p[x]$ is **irreducible^[기약]** polynomial of degree $n$

### Primitive Polynomial Definition

$f(x) \in \mathbb{F}_p[x]$ (degree $n$)가 **primitive^[원시]**이다 $\Leftrightarrow$

1. $f(x)$ is irreducible
2. 어떤 root $\alpha$가 $\mathbb{F}_{p^n}^\times$의 generator

**개수**: Primitive polynomials of degree $n$ over $\mathbb{F}_p$ = $\frac{\phi(p^n - 1)}{n}$

## Galois Group^[갈루아 군]

**정리**: $\mathbb{F}_{p^n}/\mathbb{F}_p$는 Galois extension^[갈루아 확대]

$$\text{Gal}(\mathbb{F}_{p^n}/\mathbb{F}_p) \cong C_n$$

**Generator**: Frobenius automorphism $\text{Frob}(x) = x^p$

$$\text{Gal}(\mathbb{F}_{p^n}/\mathbb{F}_p) = \{\text{id}, \text{Frob}, \text{Frob}^2, \ldots, \text{Frob}^{n-1}\}$$

자세한 내용은 [[Galois Theory]] 참조

## Irreducible Polynomials Count^[기약 다항식 개수]

**정리**: $\mathbb{F}_q$ 위의 degree $n$ monic^[최고차 계수가 1] irreducible polynomials 개수:

$$N_q(n) = \frac{1}{n} \sum_{d \mid n} \mu(d) q^{n/d}$$

where $\mu$ is Möbius function^[뫼비우스 함수]

### Examples

**Over $\mathbb{F}_2$**:
- Degree 1: $N_2(1) = 2$ ($x$, $x+1$)
- Degree 2: $N_2(2) = 1$ ($x^2 + x + 1$)
- Degree 3: $N_2(3) = 2$ ($x^3 + x + 1$, $x^3 + x^2 + 1$)
- Degree 4: $N_2(4) = 3$

**Over $\mathbb{F}_3$**:
- Degree 1: $N_3(1) = 3$
- Degree 2: $N_3(2) = 3$

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{F}_2$ (Smallest Finite Field)

$$\mathbb{F}_2 = \{0, 1\}$$

**Addition table**:
| + | 0 | 1 |
|---|---|---|
| 0 | 0 | 1 |
| 1 | 1 | 0 |

**Multiplication table**:
| · | 0 | 1 |
|---|---|---|
| 0 | 0 | 0 |
| 1 | 0 | 1 |

**Characteristic**: $\text{char}(\mathbb{F}_2) = 2$

**Multiplicative group**: $\mathbb{F}_2^\times = \{1\} \cong C_1$

## Example 2: $\mathbb{F}_3$

$$\mathbb{F}_3 = \{0, 1, 2\} \cong \mathbb{Z}/3\mathbb{Z}$$

**Arithmetic**: Modulo 3

**Multiplicative group**: $\mathbb{F}_3^\times = \{1, 2\} \cong C_2$

**Generator**: $2$ (since $2^1 = 2$, $2^2 = 1$)

## Example 3: $\mathbb{F}_4$

$\mathbb{F}_4$ 는 prime이 아니므로 $\mathbb{Z}/4\mathbb{Z}$와 **다름**!

**Construction**: $\mathbb{F}_4 = \mathbb{F}_2[x]/(x^2 + x + 1)$

**Elements**: $\{0, 1, \alpha, \alpha + 1\}$ where $\alpha^2 + \alpha + 1 = 0$

**Relation**: $\alpha^2 = \alpha + 1$

**Multiplicative group**: $\mathbb{F}_4^\times = \{1, \alpha, \alpha + 1\}$

**Orders**:
- $|1| = 1$
- $|\alpha| = 3$ (generator!)
- $|\alpha + 1| = 3$

**Powers of $\alpha$**:
- $\alpha^0 = 1$
- $\alpha^1 = \alpha$
- $\alpha^2 = \alpha + 1$
- $\alpha^3 = 1$ (cyclic!)

## Example 4: $\mathbb{F}_5$

$$\mathbb{F}_5 = \{0, 1, 2, 3, 4\} \cong \mathbb{Z}/5\mathbb{Z}$$

**Multiplicative group**: $\mathbb{F}_5^\times = \{1, 2, 3, 4\} \cong C_4$

**Generators**: $2$ and $3$

**Powers of 2**:
- $2^0 = 1$
- $2^1 = 2$
- $2^2 = 4$
- $2^3 = 3$
- $2^4 = 1$

## Example 5: $\mathbb{F}_8$

**Construction**: $\mathbb{F}_8 = \mathbb{F}_2[x]/(x^3 + x + 1)$

**Elements**: $\{0, 1, \alpha, \alpha^2, \alpha + 1, \alpha^2 + 1, \alpha^2 + \alpha, \alpha^2 + \alpha + 1\}$

where $\alpha^3 + \alpha + 1 = 0$, 즉 $\alpha^3 = \alpha + 1$

**Multiplicative group**: $\mathbb{F}_8^\times \cong C_7$ (cyclic of order 7)

**Generator**: $\alpha$

**Powers**:
- $\alpha^0 = 1$
- $\alpha^1 = \alpha$
- $\alpha^2 = \alpha^2$
- $\alpha^3 = \alpha + 1$
- $\alpha^4 = \alpha^2 + \alpha$
- $\alpha^5 = \alpha^2 + \alpha + 1$
- $\alpha^6 = \alpha^2 + 1$
- $\alpha^7 = 1$

## Example 6: $\mathbb{F}_9$

**Construction**: $\mathbb{F}_9 = \mathbb{F}_3[x]/(x^2 + 1)$

(Note: $x^2 + 1$ is irreducible over $\mathbb{F}_3$)

**Elements**: $\{0, 1, 2, \alpha, \alpha+1, \alpha+2, 2\alpha, 2\alpha+1, 2\alpha+2\}$

where $\alpha^2 + 1 = 0$, 즉 $\alpha^2 = -1 = 2$ (in $\mathbb{F}_3$)

**Multiplicative group**: $\mathbb{F}_9^\times \cong C_8$

**Generator**: $\alpha + 1$

## Example 7: $\mathbb{F}_{16}$

**Construction**: $\mathbb{F}_{16} = \mathbb{F}_2[x]/(x^4 + x + 1)$

**Size**: $|\mathbb{F}_{16}| = 16 = 2^4$

**Characteristic**: 2

**Multiplicative group**: $\mathbb{F}_{16}^\times \cong C_{15}$

**Subfields**:
- $\mathbb{F}_2$ (divisor: 1)
- $\mathbb{F}_4$ (divisor: 2)
- $\mathbb{F}_{16}$ (divisor: 4)

## Example 8: Subfield Chain

$$\mathbb{F}_2 \subseteq \mathbb{F}_4 \subseteq \mathbb{F}_{16} \subseteq \mathbb{F}_{256} \subseteq \cdots$$

Corresponding to divisibility: $1 \mid 2 \mid 4 \mid 8 \mid \cdots$

---

# <span class="header-properties">Properties</span>

## Additive Structure

**정리**: $(\mathbb{F}_q, +) \cong (C_p)^n$ where $q = p^n$

Additive group은 elementary abelian $p$-group^[기본 아벨 p-군]

**직관**: $\mathbb{F}_{p^n}$를 $\mathbb{F}_p$-vector space로 보면 dimension $n$

## Roots of Unity^[단위근]

Order $n$인 모든 roots of unity는 $\mathbb{F}_q$에 존재 $\Leftrightarrow$ $n \mid (q-1)$

**$n$-th roots of unity**: Solutions to $x^n = 1$

**Primitive $n$-th root**: $\zeta_n$ with $|\zeta_n| = n$

**개수**: $\phi(n)$개 (Euler totient)

## Trace and Norm^[대각합과 노름]

### Trace Function

$$\text{Tr}: \mathbb{F}_{p^n} \to \mathbb{F}_p, \quad \text{Tr}(x) = x + x^p + x^{p^2} + \cdots + x^{p^{n-1}}$$

**Properties**:
1. $\mathbb{F}_p$-linear
2. Surjective
3. $\text{Tr}(x) = 0$의 해: $p^{n-1}$개

### Norm Function

$$N: \mathbb{F}_{p^n} \to \mathbb{F}_p, \quad N(x) = x \cdot x^p \cdot x^{p^2} \cdots x^{p^{n-1}}$$

**Properties**:
1. Multiplicative homomorphism
2. Surjective (onto $\mathbb{F}_p^\times$)
3. $N(x) = x^{(p^n - 1)/(p - 1)}$

## Quadratic Residues^[이차잉여]

$a \in \mathbb{F}_q^\times$가 **quadratic residue^[이차잉여]**이다 $\Leftrightarrow$ $\exists x \in \mathbb{F}_q: x^2 = a$

**개수**: 
- $q$ odd: $(q-1)/2$개
- $q$ even: 모든 원소 (characteristic 2)

**Legendre symbol**: $\left(\frac{a}{p}\right) = a^{(p-1)/2}$ (for odd prime $p$)

## Wedderburn's Theorem^[웨더번 정리]

**정리**: 모든 finite division ring^[유한 나눗셈환]은 commutative^[가환]

**결과**: Finite division ring = finite field

**증명**: Wedderburn (1905), 비자명!

## Polynomial Factorization^[다항식 인수분해]

**정리**: $x^q - x = \prod_{\alpha \in \mathbb{F}_q} (x - \alpha)$

모든 $\alpha \in \mathbb{F}_q$는 $x^q - x$의 근

**Fermat's Little Theorem의 일반화**:

$$a^q = a \quad \forall a \in \mathbb{F}_q$$

## Irreducibility Test^[기약성 판정]

$f(x) \in \mathbb{F}_q[x]$ (degree $n$)가 irreducible $\Leftrightarrow$

1. $\gcd(f(x), x^{q^d} - x) = 1$ for all $d < n$ with $d \mid n$
2. $f(x) \mid x^{q^n} - x$

자세한 내용은 [[Irreducible Polynomial]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Finite field = "유한한 사칙연산 구조"**

**핵심 아이디어**:
- Prime $p$ → characteristic
- Power $n$ → dimension over prime field
- Total size: $p^n$

**기하학적**:
- $\mathbb{F}_{p^n}$는 $\mathbb{F}_p$-vector space (dimension $n$)
- Frobenius는 "회전" automorphism

## Construction Methods^[구성 방법]

### Method 1: Quotient Ring

$$\mathbb{F}_{p^n} = \mathbb{F}_p[x]/(f(x))$$

where $f(x)$ is irreducible of degree $n$

**장점**: 구체적, 계산 가능

### Method 2: Splitting Field

$$\mathbb{F}_{p^n} = \text{splitting field of } x^{p^n} - x$$

**장점**: 이론적으로 깔끔, 유일성 명확

### Method 3: Algebraic Closure

$$\mathbb{F}_{p^n} \subseteq \overline{\mathbb{F}_p}$$

$\overline{\mathbb{F}_p}$에서 order $p^n - 1$인 cyclic subgroup

## 응용 분야

### 1. Cryptography^[암호학]

**AES**: $\mathbb{F}_{2^8}$ (Rijndael field)

$$\mathbb{F}_{256} = \mathbb{F}_2[x]/(x^8 + x^4 + x^3 + x + 1)$$

**Elliptic Curve Cryptography**: Curves over $\mathbb{F}_p$ or $\mathbb{F}_{2^n}$

**Diffie-Hellman**: Discrete log in $\mathbb{F}_p^\times$

### 2. Coding Theory^[부호 이론]

**BCH Codes**: Based on minimal polynomials in $\mathbb{F}_{2^m}$

**Reed-Solomon Codes**: Evaluation codes over $\mathbb{F}_q$

**Linear codes**: Vector spaces over $\mathbb{F}_q$

### 3. Algebraic Geometry^[대수기하학]

**Varieties over finite fields**: Weil conjectures

**Zeta functions**: Counting points over $\mathbb{F}_{p^n}$

### 4. Number Theory^[정수론]

**Quadratic reciprocity**: Via $\mathbb{F}_p$

**Diophantine equations**: Solutions modulo $p$

### 5. Combinatorics^[조합론]

**Design theory**: Blocks in $\mathbb{F}_q^n$

**Graph theory**: Paley graphs over $\mathbb{F}_q$

## Historical Context

**Évariste Galois** (1811-1832):
- 처음으로 finite fields 연구
- Galois theory의 창시자
- "Galois fields" $GF(p^n)$

**Leonard Dickson** (1874-1954):
- Finite fields의 체계적 이론 발전
- Linear groups over finite fields

**André Weil** (1906-1998):
- Weil conjectures (finite fields 위의 varieties)

## Advanced Topics

### Algebraic Closure

$$\overline{\mathbb{F}_p} = \bigcup_{n=1}^{\infty} \mathbb{F}_{p^n}$$

**Properties**:
- Infinite field
- Algebraically closed
- All finite subfields are $\mathbb{F}_{p^n}$

### Absolute Galois Group

$$\text{Gal}(\overline{\mathbb{F}_p}/\mathbb{F}_p) \cong \widehat{\mathbb{Z}} = \varprojlim \mathbb{Z}/n\mathbb{Z}$$

Profinite completion of $\mathbb{Z}$

### Weil Conjectures

Smooth projective variety $X$ over $\mathbb{F}_q$:

$$\zeta_X(s) = \exp\left(\sum_{n=1}^{\infty} \frac{|X(\mathbb{F}_{q^n})|}{n} q^{-ns}\right)$$

Proved by Deligne (1974)

## Computational Aspects

### Polynomial Arithmetic

Addition: $O(n)$

Multiplication: $O(n^2)$ (naive), $O(n \log n)$ (FFT)

Inversion: Extended Euclidean algorithm $O(n^2)$

### Irreducibility Testing

**Berlekamp's algorithm**: $O(n^3 + n^2 \log q)$

**Rabin's test**: Probabilistic, $O(n^3 \log q)$

### Discrete Logarithm

**Problem**: Given $g, h \in \mathbb{F}_q^\times$, find $x$ with $g^x = h$

**Algorithms**:
- Baby-step giant-step: $O(\sqrt{q})$
- Index calculus: Subexponential
- Pollard's rho: $O(\sqrt{q})$

## Common Pitfalls

### 1. $\mathbb{Z}/n\mathbb{Z}$ is NOT always a field

✗ "$\mathbb{Z}/4\mathbb{Z}$ is a field"?

✓ $\mathbb{Z}/n\mathbb{Z}$ is a field $\Leftrightarrow$ $n$ is prime

**Only** $\mathbb{F}_p = \mathbb{Z}/p\mathbb{Z}$ for prime $p$

### 2. Order must be prime power

✗ "Finite field of order 6 exists"?

✓ Order must be $p^n$ (prime power)

$6 = 2 \times 3$ is not a prime power → No $\mathbb{F}_6$

### 3. $\mathbb{F}_{p^n} \neq (\mathbb{F}_p)^n$

✗ "$\mathbb{F}_4 = \mathbb{F}_2 \times \mathbb{F}_2$"?

✓ $\mathbb{F}_4$ is a **field**, not a product!

Cartesian product is NOT a field (zero divisors)

### 4. Frobenius Power

✗ "$\text{Frob}^n(x) = x^{p^n}$"?

✓ $\text{Frob}^n(x) = x^{p^n}$ (correct!)

But $\text{Frob}^n = \text{id}$ on $\mathbb{F}_{p^n}$ (important!)

### 5. Primitive Polynomial ≠ Primitive Element

✗ "Primitive polynomial = polynomial of primitive element"?

✓ Different concepts:
- **Primitive polynomial**: Irreducible + root is generator
- **Primitive element**: Generator of $\mathbb{F}_q^\times$

## Comparison Table

| Field | Order | Char | $\mathbb{F}^\times$ | Subfields |
|-------|-------|------|---------------------|-----------|
| $\mathbb{F}_2$ | 2 | 2 | $C_1$ | None |
| $\mathbb{F}_3$ | 3 | 3 | $C_2$ | None |
| $\mathbb{F}_4$ | 4 | 2 | $C_3$ | $\mathbb{F}_2$ |
| $\mathbb{F}_5$ | 5 | 5 | $C_4$ | None |
| $\mathbb{F}_8$ | 8 | 2 | $C_7$ | $\mathbb{F}_2$ |
| $\mathbb{F}_9$ | 9 | 3 | $C_8$ | $\mathbb{F}_3$ |
| $\mathbb{F}_{16}$ | 16 | 2 | $C_{15}$ | $\mathbb{F}_2, \mathbb{F}_4$ |

## Related Concepts

- [[Field]]: General definition
- [[Galois Theory]]: Galois group of finite fields
- [[Cyclic Group]]: Structure of $\mathbb{F}_q^\times$
- [[Irreducible Polynomial]]: Construction via quotient
- [[Polynomial Ring]]: $\mathbb{F}_p[x]$
- [[Extension Field]]: $\mathbb{F}_{p^n}/\mathbb{F}_p$
- [[Isomorphism Theorem]]: Quotient construction
- [[Ring]]: General algebraic structure

