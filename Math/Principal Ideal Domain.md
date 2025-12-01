# <span class="header-prerequisite">Prerequisite</span>
- [[Integral Domain]]
- [[Principal Ideal]]
- [[Ideal]]
- [[Unique Factorization Domain]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Lang, Algebra
- Jacobson, Basic Algebra I

---

# <span class="header-definition">Definition</span>

## Principal Ideal Domain^[주 아이디얼 정역]

Integral domain^[정역] $R$이 **Principal Ideal Domain** (줄여서 **PID**)이다 $\Leftrightarrow$ 모든 ideal^[아이디얼]이 principal^[주]

$$\forall I \triangleleft R: \quad \exists a \in R \text{ such that } I = \langle a \rangle$$

**의미**: 모든 ideal이 단 하나의 원소로 생성됨

**필수 조건**:
1. Integral domain (no zero divisors)
2. Every ideal is principal

## Principal Ideal Ring^[주 아이디얼 환]

**정의**: Ring $R$ (not necessarily domain) where every ideal is principal

**차이점**:
- **PIR**: 모든 ideal이 principal (zero divisors 가능)
- **PID**: PIR + integral domain

**예**: $\mathbb{Z}/4\mathbb{Z}$ is PIR but not PID (has zero divisors)

---

# <span class="header-theorem">Theorems</span>

## Euclidean Domain ⇒ PID

**정리**: 모든 Euclidean domain^[유클리드 정역]은 PID

**증명**:

Euclidean domain $R$, ideal $I \triangleleft R$ (nonzero)

**Step 1**: $I \neq \{0\}$이면 nonzero 원소 $b \in I$ 선택
- Euclidean function $N: R \setminus \{0\} \to \mathbb{N}$
- $N(b)$가 최소가 되도록 $b$ 선택

**Step 2**: $I = \langle b \rangle$ 증명
- $\langle b \rangle \subseteq I$는 자명 ($b \in I$이고 $I$ is ideal)
- $I \subseteq \langle b \rangle$ 증명: 임의의 $a \in I$에 대해
  - Division algorithm: $a = qb + r$ where $N(r) < N(b)$ 또는 $r = 0$
  - $r = a - qb \in I$ (since $a, b \in I$)
  - $N(b)$의 최소성: $r \neq 0$이면 모순
  - 따라서 $r = 0$, 즉 $a = qb \in \langle b \rangle$ 
**따름정리**:
- $\mathbb{Z}$ is PID (Euclidean with $N(a) = |a|$)
- $k[x]$ is PID (Euclidean with $N(f) = \deg(f)$)
- $\mathbb{Z}[i]$ is PID (Euclidean with $N(a+bi) = a^2 + b^2$)

자세한 내용은 [[Euclidean Domain]] 참조

## PID ⇒ UFD

**정리**: 모든 PID는 UFD^[유일 인수분해 정역]

**증명 개요**:

### Part 1: Existence of Factorization

**Lemma**: PID satisfies **ACCP** (Ascending Chain Condition on Principal ideals)

$$\langle a_1 \rangle \subseteq \langle a_2 \rangle \subseteq \langle a_3 \rangle \subseteq \cdots$$

implies eventually constant

**증명**:
- $I = \bigcup_{n=1}^{\infty} \langle a_n \rangle$ is ideal
- PID이므로 $I = \langle a \rangle$
- $a \in \langle a_N \rangle$ for some $N$
- 따라서 $\langle a_N \rangle = \langle a_{N+1} \rangle = \cdots$ 
**Factorization exists**: ACCP로부터 귀납적으로 증명

### Part 2: Irreducible ⇒ Prime (in PID)

**Lemma**: PID에서 irreducible element는 prime

**증명**: $p$ irreducible, $p \mid ab$라 하자
- $\langle p, a \rangle$는 ideal containing $p$
- PID: $\langle p, a \rangle = \langle d \rangle$
- $p \in \langle d \rangle$이므로 $p = cd$
- $p$ irreducible: $c$ unit 또는 $d$ unit
  
**Case 1**: $d$ unit이면 $\langle d \rangle = R$
- $1 = rp + sa$ for some $r, s \in R$ (Bezout)
- $b = rpb + sab$
- $p \mid ab$이므로 $p \mid b$ 
**Case 2**: $c$ unit이면 $d \sim p$
- $\langle d \rangle = \langle p \rangle$
- $a \in \langle p \rangle$
- 즉 $p \mid a$ 
### Part 3: Uniqueness

Prime factorization의 uniqueness는 표준 논증 
자세한 내용은 [[Unique Factorization Domain]] 참조

## Hierarchy of Domains^[정역의 계층]

**정리**:

$$\text{Field} \subsetneq \text{Euclidean Domain} \subsetneq \text{PID} \subsetneq \text{UFD} \subsetneq \text{Integral Domain}$$

**모든 포함은 strict**:

| Domain | Example | Euclidean? | PID? | UFD? |
|--------|---------|------------|------|------|
| Field | $\mathbb{Q}$, $\mathbb{R}$ | ✓ | ✓ | ✓ |
| Euclidean, not field | $\mathbb{Z}$, $k[x]$ | ✓ | ✓ | ✓ |
| PID, not Euclidean | $\mathbb{Z}[\frac{1+\sqrt{-19}}{2}]$ | ✗ | ✓ | ✓ |
| UFD, not PID | $\mathbb{Z}[x]$, $k[x,y]$ | ✗ | ✗ | ✓ |
| Domain, not UFD | $\mathbb{Z}[\sqrt{-5}]$ | ✗ | ✗ | ✗ |

## GCD and Bezout's Identity

**정리**: PID $R$에서 $a, b \in R$ (not both zero)에 대해:

$$\langle a, b \rangle = \langle d \rangle$$

where $d = \gcd(a, b)$

**Bezout's Identity**: 

$$\exists r, s \in R: \quad d = ra + sb$$

**증명**:
- $\langle a, b \rangle = \{ra + sb : r, s \in R\}$ is ideal
- PID: $\langle a, b \rangle = \langle d \rangle$ for some $d$
- $d \in \langle a, b \rangle$이므로 $d = ra + sb$ - $a, b \in \langle d \rangle$이므로 $d \mid a$ and $d \mid b$ 
**중요성**: GCD를 linear combination으로 표현!

## Structure Theorem for Finitely Generated Modules

**정리** (**Fundamental Theorem**): PID $R$, finitely generated $R$-module $M$에 대해:

$$M \cong R^r \oplus R/(d_1) \oplus R/(d_2) \oplus \cdots \oplus R/(d_n)$$

where $d_1 \mid d_2 \mid \cdots \mid d_n$

**응용**:
1. **Finitely generated abelian groups**: $R = \mathbb{Z}$인 경우
   $$G \cong \mathbb{Z}^r \oplus \mathbb{Z}/d_1\mathbb{Z} \oplus \cdots \oplus \mathbb{Z}/d_n\mathbb{Z}$$

2. **Rational canonical form**: Linear algebra

3. **Jordan canonical form**: Over algebraically closed fields

## Prime and Maximal Ideals in PID

**정리**: PID $R$에서 nonzero prime ideal $P$:

$$P \text{ is prime} \quad \Leftrightarrow \quad P \text{ is maximal}$$

**증명**:

$(\Rightarrow)$ Prime $\Rightarrow$ Maximal:
- $P = \langle p \rangle$ (PID)
- $P \subseteq I \triangleleft R$, $I \neq R$
- $I = \langle a \rangle$ (PID)
- $p \in \langle a \rangle$이므로 $p = ab$
- $P$ prime + nonzero: $p$ prime element
- $p = ab$: $a$ unit 또는 $b$ unit
- $a$ unit: $\langle a \rangle = R$ (모순)
- $b$ unit: $\langle a \rangle = \langle p \rangle = P$
- 따라서 $P$ is maximal 
$(\Leftarrow)$ Maximal $\Rightarrow$ Prime: 일반적으로 성립 (commutative ring)

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$ (Integers)

**PID**: Yes 
**모든 ideal**: $n\mathbb{Z} = \langle n \rangle$

**Proof**: Division algorithm
- Ideal $I \triangleleft \mathbb{Z}$, $I \neq \{0\}$
- $n = $ smallest positive element in $I$
- For any $m \in I$: $m = qn + r$ where $0 \leq r < n$
- $r = m - qn \in I$
- Minimality of $n$: $r = 0$
- 따라서 $I = n\mathbb{Z}$ 
**GCD**: $\gcd(a, b) = d$ where $\langle a, b \rangle = \langle d \rangle$

**Bezout**: $d = ra + sb$ (Extended Euclidean algorithm)

## Example 2: $k[x]$ (Polynomial Ring over Field)

Field $k$에 대해:

**PID**: Yes 
**모든 ideal**: $\langle f(x) \rangle$ where $f$ monic of minimal degree

**Proof**: Polynomial division algorithm

**예**:
- $\langle x^2 - 1, x + 1 \rangle = \langle x + 1 \rangle$ in $\mathbb{R}[x]$
- $\langle x^2, x^3 \rangle = \langle x^2 \rangle$ in $k[x]$

**Irreducibles**: Irreducible polynomials over $k$

**Units**: $k^\times = k \setminus \{0\}$

## Example 3: Gaussian Integers $\mathbb{Z}[i]$

$$\mathbb{Z}[i] = \{a + bi : a, b \in \mathbb{Z}\}$$

**PID**: Yes  (Euclidean domain)

**Norm**: $N(a + bi) = a^2 + b^2$

**Division algorithm**: Using norm function

**Ideals**: 
- $\langle 0 \rangle$
- $\langle 1 + i \rangle$
- $\langle 2 + i \rangle$
- $\langle p \rangle$ (primes in $\mathbb{Z}[i]$)

**Prime elements**:
- $1 + i$ (since $2 = -i(1+i)^2$)
- Primes $p \equiv 3 \pmod{4}$ (remain prime)
- Factors of primes $p \equiv 1 \pmod{4}$

## Example 4: $\mathbb{Z}[x]$ (Not PID!)

**PID**: No ✗

**Counterexample**: $I = \langle 2, x \rangle$

**Proof it's not principal**:
- Suppose $I = \langle f(x) \rangle$
- $2 \in I$이므로 $2 = g(x) f(x)$
- Degree: $0 = \deg(g) + \deg(f)$
- 따라서 $\deg(f) = 0$, 즉 $f \in \mathbb{Z}$
- $f \mid 2$ in $\mathbb{Z}$: $f \in \{\pm 1, \pm 2\}$
- $f = \pm 1$: $I = R$ (모순)
- $f = \pm 2$: $x \notin \langle 2 \rangle$ (모순)
- 따라서 $I$ is not principal ✗

**But**: $\mathbb{Z}[x]$ is UFD  (by Gauss's Lemma)

## Example 5: $k[x, y]$ (Multivariate Polynomials)

Field $k$에 대해:

**PID**: No ✗

**Counterexample**: $\langle x, y \rangle$

**Proof**: Similar to $\mathbb{Z}[x]$

**But**: $k[x, y]$ is UFD 
## Example 6: $\mathbb{Z}[\sqrt{2}]$

$$\mathbb{Z}[\sqrt{2}] = \{a + b\sqrt{2} : a, b \in \mathbb{Z}\}$$

**PID**: Yes  (Euclidean domain)

**Norm**: $N(a + b\sqrt{2}) = |a^2 - 2b^2|$

**Division algorithm**: Via norm

**Units**: $\{\pm (1 + \sqrt{2})^n : n \in \mathbb{Z}\}$ (infinitely many!)

## Example 7: $\mathbb{Z}[\sqrt{-5}]$ (Not Even UFD!)

$$\mathbb{Z}[\sqrt{-5}] = \{a + b\sqrt{-5} : a, b \in \mathbb{Z}\}$$

**PID**: No ✗

**UFD**: No ✗

**Failure**: $6 = 2 \cdot 3 = (1 + \sqrt{-5})(1 - \sqrt{-5})$

**Ideal**: $\langle 2, 1 + \sqrt{-5} \rangle$ is not principal

## Example 8: $\mathbb{Z}/n\mathbb{Z}$

**PIR**: Yes  (all ideals are principal)

**PID**: No ✗ (has zero divisors if $n$ not prime)

**예**: $\mathbb{Z}/6\mathbb{Z}$
- $\bar{2} \cdot \bar{3} = \bar{0}$ (zero divisors)
- All ideals principal
- But not integral domain

---

# <span class="header-properties">Properties</span>

## Every Nonzero Prime Ideal is Maximal

앞서 정리에서 증명

**의미**: Prime ideals와 maximal ideals가 일치 (except $\langle 0 \rangle$)

## Noetherian

**정리**: 모든 PID는 Noetherian^[뇌터 환]

**증명**: ACC on principal ideals (PID ⇒ UFD 증명에서 사용)

**의미**: 
- Ascending chain condition on ideals
- Every ideal is finitely generated

## Dedekind Domain

**정리**: PID는 Dedekind domain^[데데킨트 정역]

**Dedekind domain 조건**:
1. Noetherian 2. Integrally closed 3. Every nonzero prime ideal is maximal 
**역은 거짓**: Dedekind domain $\not\Rightarrow$ PID

**예**: $\mathbb{Z}[\sqrt{-5}]$ is Dedekind but not PID

## Factorization of Ideals

**정리**: PID $R$에서 모든 nonzero ideal은 **uniquely** factors into prime ideals

$$I = P_1 P_2 \cdots P_n$$

**Proof**: $I = \langle a \rangle$이고 $a = p_1 p_2 \cdots p_n$ (prime factorization)

$$\langle a \rangle = \langle p_1 \rangle \langle p_2 \rangle \cdots \langle p_n \rangle$$

## Chinese Remainder Theorem

**정리**: PID $R$에서 $\langle a_1 \rangle, \ldots, \langle a_n \rangle$ pairwise coprime^[서로소]이면:

$$R/\langle a_1 \cdots a_n \rangle \cong R/\langle a_1 \rangle \times \cdots \times R/\langle a_n \rangle$$

**Coprime**: $\langle a_i \rangle + \langle a_j \rangle = R$ for $i \neq j$

**동등 조건**: $\gcd(a_i, a_j) = 1$ (up to units)

자세한 내용은 [[Chinese Remainder Theorem]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**PID = "가장 단순한 구조"**

**핵심 아이디어**:
- 모든 ideal은 단 하나의 원소로 표현
- $\mathbb{Z}$처럼 "깔끔한" 구조
- Division algorithm 가능 (대부분)

**메타포**: 
- Principal ideal = "하나의 원소가 모든 것을 결정"
- GCD = "두 ideal의 합"
- LCM = "두 ideal의 교집합"

## Why Study PID?^[PID를 공부하는 이유]

**1. Simplicity**: 가장 다루기 쉬운 non-field domains

**2. Examples**: $\mathbb{Z}$, $k[x]$ 등 중요한 예시들

**3. Structure**: Module theory의 기초

**4. Algorithms**: Division algorithm 사용 가능

**5. Gateway**: UFD와 Dedekind domain 사이

## PID vs UFD vs Euclidean

| Property | Field | Euclidean | PID | UFD | Domain |
|----------|-------|-----------|-----|-----|--------|
| No zero divisors |  |  |  |  |  |
| All invertible (except 0) |  | ✗ | ✗ | ✗ | ✗ |
| Division algorithm |  |  | ? | ✗ | ✗ |
| All ideals principal |  |  |  | ✗ | ✗ |
| Unique factorization |  |  |  |  | ✗ |
| Bezout identity |  |  |  | ✗ | ✗ |
| Prime = Maximal (nonzero) | N/A |  |  | ✗ | ✗ |

## 응용 분야

### 1. Number Theory^[정수론]

**$\mathbb{Z}$**: 정수론의 기초

**응용**:
- GCD and LCM algorithms
- Diophantine equations
- Modular arithmetic
- Bezout's identity

### 2. Polynomial Algebra

**$k[x]$**: 다항식 이론

**응용**:
- Polynomial division
- Factorization
- Irreducibility tests
- Roots and factors

### 3. Module Theory^[가군론]

**Structure theorem**: Finitely generated modules over PID

**응용**:
- Classification of abelian groups
- Rational canonical form
- Jordan canonical form

### 4. Algebraic Number Theory

**Rings of integers**: Number field의 정수환

**응용**:
- Quadratic fields
- Cyclotomic fields
- Class groups (non-PID 측정)

### 5. Linear Algebra

**$k[x]$-modules**: Vector spaces with linear transformation

**응용**:
- Canonical forms
- Similarity of matrices
- Minimal/characteristic polynomials

### 6. Coding Theory^[부호이론]

**Cyclic codes**: Ideals in $\mathbb{F}_q[x]/(x^n - 1)$

**BCH codes**: Using polynomial ideals

## 역사적 배경

**19세기**:
- **Gauss**: Gaussian integers $\mathbb{Z}[i]$
- **Dedekind**: Ideal theory

**20세기**:
- **Emmy Noether**: Abstract algebra
- Structure theorems
- Module theory over PID

## Common Patterns^[일반적 패턴]

### Pattern 1: Division Algorithm

Euclidean domain $\Rightarrow$ Division algorithm $\Rightarrow$ PID

**핵심**: "Smallest" element로 generator

### Pattern 2: Bezout Identity

PID $\Rightarrow$ $\gcd(a, b) = ra + sb$

**응용**: Extended Euclidean algorithm

### Pattern 3: Prime = Maximal

PID $\Rightarrow$ Nonzero prime ideal = Maximal

**기하학적**: "1차원" 구조

## Common Pitfalls^[흔한 실수]

### 1. PID ≠ PIR

✗ PID = PIR?

 PID = PIR + Integral domain

**반례**: $\mathbb{Z}/4\mathbb{Z}$ is PIR but not PID

### 2. Ideal Principal ≠ Generated by Prime

✗ Principal ideal = generated by prime?

 Principal = generated by one element (any)

### 3. UFD ≠ PID

✗ UFD이면 PID?

 역: PID $\Rightarrow$ UFD

**반례**: $\mathbb{Z}[x]$, $k[x,y]$ are UFD but not PID

### 4. All Domains with Division Algorithm are PID?

✗ Division algorithm exists $\Rightarrow$ PID?

 **Euclidean** division algorithm $\Rightarrow$ PID

Division algorithm 자체만으로는 부족!

### 5. Generator Uniqueness

✗ Generator는 유일?

 Up to units! $\langle a \rangle = \langle b \rangle \Leftrightarrow a = ub$ (unit $u$)

### 6. Polynomial Rings

✗ $R$ PID $\Rightarrow$ $R[x]$ PID?

 일반적으로 거짓!

**반례**: $\mathbb{Z}$ is PID but $\mathbb{Z}[x]$ is not

**맞는 경우**: $k$ field $\Rightarrow$ $k[x]$ PID (but $k[x,y]$ not PID!)

## Characterizations Summary

PID $R$ 특징:

1. **Definition**: Every ideal is principal
2. **GCD**: $\langle a, b \rangle = \langle \gcd(a, b) \rangle$
3. **Bezout**: $\gcd(a, b) = ra + sb$
4. **Prime = Maximal**: Nonzero prime ideals are maximal
5. **Factorization**: Unique factorization (UFD)
6. **Noetherian**: ACC on ideals
7. **Structure theorem**: For finitely generated modules

## Non-PID Examples

**중요한 반례**:

1. **$\mathbb{Z}[x]$**: UFD but not PID
   - $\langle 2, x \rangle$ not principal

2. **$k[x, y]$**: UFD but not PID
   - $\langle x, y \rangle$ not principal

3. **$\mathbb{Z}[\sqrt{-5}]$**: Not even UFD
   - Not PID, not UFD

4. **$\mathbb{C}[x, y]/(xy - 1)$**: Domain but not UFD
   - Not PID

## Extensions and Generalizations

**Beyond PID**:

1. **Dedekind domains**: Ideal factorization
   - Every nonzero ideal factors uniquely into primes
   - $\mathbb{Z}[\sqrt{-5}]$ is Dedekind but not PID

2. **Bezout domains**: Finitely generated ideals are principal
   - Weaker than PID

3. **GCD domains**: GCD exists
   - Weaker than PID

4. **Valuation rings**: Local PIDs
   - Important in algebraic geometry

## 관련 개념

- [[Integral Domain]]: Base concept
- [[Principal Ideal]]: Building block
- [[Euclidean Domain]]: Euclidean ⇒ PID
- [[Unique Factorization Domain]]: PID ⇒ UFD
- [[Ideal]]: General theory
- [[Prime Ideal]]: Prime = Maximal in PID
- [[Maximal Ideal]]: Structure
- [[Commutative Ring]]: Framework
- [[Field]]: Trivial PID

