# <span class="header-prerequisite">Prerequisite</span>
- [[Integral Domain]]
- [[Ring]]
- [[Prime Ideal]]
- [[Principal Ideal]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Lang, Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra

---

# <span class="header-definition">Definition</span>

## Irreducible Element^[기약 원소]

Integral domain^[정역] $R$에서 원소 $a \in R$ (nonzero, non-unit)가 **irreducible^[기약]**이다 $\Leftrightarrow$

$$a = bc \quad \Rightarrow \quad b \in R^\times \text{ or } c \in R^\times$$

**의미**: Nontrivial factorization^[비자명한 인수분해]이 불가능

**동등 조건**: $a$가 unit들의 곱을 제외하고는 더 이상 분해되지 않음

## Prime Element^[소 원소]

Integral domain $R$에서 원소 $p \in R$ (nonzero, non-unit)가 **prime^[소]**이다 $\Leftrightarrow$

$$p \mid ab \quad \Rightarrow \quad p \mid a \text{ or } p \mid b$$

**의미**: "소수처럼" 작동하는 원소

**동등 조건**: Principal ideal $\langle p \rangle$가 prime ideal^[소 아이디얼]

## Associates^[동반 원소]

원소 $a, b \in R$이 **associate^[동반]**이다 $\Leftrightarrow$

$$\exists u \in R^\times: \quad a = ub$$

**표기**: $a \sim b$

**의미**: "본질적으로 같음" (unit 배수 차이)

**예**: $\mathbb{Z}$에서 $6 \sim -6$ (unit = $-1$)

## Unique Factorization Domain^[유일 인수분해 정역]

Integral domain $R$이 **UFD** (또는 **factorial domain^[인수분해 정역]**)이다 $\Leftrightarrow$ 다음 두 조건을 만족:

### 1. Existence of Factorization^[인수분해의 존재성]

모든 nonzero non-unit $a \in R$은 irreducible elements^[기약 원소]의 곱으로 표현 가능:

$$a = p_1 p_2 \cdots p_n$$

where $p_i$ are irreducible

### 2. Uniqueness of Factorization^[인수분해의 유일성]

두 인수분해

$$a = p_1 p_2 \cdots p_n = q_1 q_2 \cdots q_m$$

가 있으면, $n = m$이고 적절한 재배열 후:

$$p_i \sim q_{\sigma(i)} \quad \text{for some permutation } \sigma$$

**의미**: 인수분해가 associate^[동반]와 순서를 제외하고 유일

---

# <span class="header-theorem">Theorems</span>

## Prime ⇔ Irreducible (in UFD)

**정리**: UFD에서 원소 $p$에 대해:

$$p \text{ is prime} \quad \Leftrightarrow \quad p \text{ is irreducible}$$

**증명**:

$(\Rightarrow)$ Prime $\Rightarrow$ Irreducible:
- $p = ab$라 하자
- $p \mid ab$이므로 (자명) $p \mid a$ 또는 $p \mid b$
- WLOG $p \mid a$라 하면 $a = pc$
- 따라서 $p = pcb$, 즉 $1 = cb$ (cancellation)
- 따라서 $b$ is unit ✓

$(\Leftarrow)$ Irreducible $\Rightarrow$ Prime (UFD에서):
- $p \mid ab$라 하자, 즉 $ab = pc$
- UFD이므로 양변을 irreducibles로 인수분해
- 유일성에 의해 $p$는 $a$ 또는 $b$의 인수분해에 나타남 (associate 포함)
- 따라서 $p \mid a$ 또는 $p \mid b$ ✓

**중요성**: UFD에서는 irreducible = prime (일반 integral domain에서는 다름!)

## PID ⇒ UFD

**정리**: 모든 Principal Ideal Domain^[주 아이디얼 정역]은 UFD

**증명 개요**:

**Step 1**: Existence of factorization
- ACC on principal ideals 이용
- Irreducibles로 분해 가능함을 귀납법으로 증명

**Step 2**: Uniqueness
- PID에서 irreducible $\Rightarrow$ prime (principal ideal 특성)
- Prime elements로 인수분해의 유일성 보장

자세한 내용은 [[Principal Ideal Domain]] 참조

## Gauss's Lemma^[가우스 보조정리]

**정리**: $R$ is UFD $\Rightarrow$ $R[x]$ is UFD

**증명**: Primitive polynomials^[원시 다항식]의 성질 이용

**따름정리**: 
$$\mathbb{Z} \text{ is UFD} \quad \Rightarrow \quad \mathbb{Z}[x], \mathbb{Z}[x, y], \ldots \text{ are UFDs}$$

$$k \text{ is field} \quad \Rightarrow \quad k[x_1, \ldots, x_n] \text{ is UFD}$$

### Content and Primitive Polynomials

UFD $R$에서 $f(x) = a_0 + a_1x + \cdots + a_nx^n \in R[x]$:

**Content^[용량]**: 
$$\text{cont}(f) = \gcd(a_0, a_1, \ldots, a_n)$$

**Primitive^[원시]**: $\text{cont}(f) \sim 1$

**Gauss's Lemma**: Primitive polynomials의 곱은 primitive

## Euclidean Domain ⇒ PID ⇒ UFD

**정리**: 다음 포함 관계가 성립:

$$\text{Field} \subsetneq \text{Euclidean Domain} \subsetneq \text{PID} \subsetneq \text{UFD} \subsetneq \text{Integral Domain}$$

**모든 포함은 strict**:
- UFD but not PID: $\mathbb{Z}[x]$, $k[x, y]$
- PID but not Euclidean: 특정 number rings
- Integral domain but not UFD: $\mathbb{Z}[\sqrt{-5}]$

자세한 내용은 [[Euclidean Domain]], [[Principal Ideal Domain]] 참조

## GCD in UFD^[최대공약수]

**정리**: UFD $R$에서 임의의 $a, b \in R$ (not both zero)는 **greatest common divisor^[최대공약수]** $d$를 가짐:

$$d = \gcd(a, b)$$

**정의**: 
1. $d \mid a$ and $d \mid b$
2. $c \mid a$ and $c \mid b$ $\Rightarrow$ $c \mid d$

**유일성**: Up to associates^[동반 원소]

**구성**: 인수분해로부터:
$$a = p_1^{e_1} \cdots p_k^{e_k}, \quad b = p_1^{f_1} \cdots p_k^{f_k}$$
$$\gcd(a, b) = p_1^{\min(e_1, f_1)} \cdots p_k^{\min(e_k, f_k)}$$

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$ (Integers)

**UFD**: Yes ✓

**인수분해**:
$$12 = 2^2 \cdot 3$$
$$-30 = -1 \cdot 2 \cdot 3 \cdot 5$$

**Irreducibles**: $\pm p$ where $p$ is prime number

**Units**: $\{\pm 1\}$

**Associates**: $n \sim -n$

**Fundamental Theorem of Arithmetic**: $\mathbb{Z}$는 UFD

## Example 2: $k[x]$ (Polynomial Ring)

Field $k$에 대해 $k[x]$:

**UFD**: Yes ✓

**Irreducibles**: 
- Over $\mathbb{C}$: Linear polynomials $(x - a)$
- Over $\mathbb{R}$: Linear and quadratic with no real roots
- Over $\mathbb{Q}$: More complex (Eisenstein, etc.)

**예**:
$$x^4 - 1 = (x-1)(x+1)(x^2+1)$$ over $\mathbb{R}$
$$x^4 - 1 = (x-1)(x+1)(x-i)(x+i)$$ over $\mathbb{C}$

**Units**: $k^\times = k \setminus \{0\}$ (nonzero constants)

## Example 3: Gaussian Integers $\mathbb{Z}[i]$

$$\mathbb{Z}[i] = \{a + bi : a, b \in \mathbb{Z}\}$$

**UFD**: Yes ✓

**Norm**: $N(a + bi) = a^2 + b^2$

**Units**: $\{\pm 1, \pm i\}$ (with $N = 1$)

**Prime factorization**:
$$5 = (2 + i)(2 - i)$$
$$2 = -i(1 + i)^2$$

**Irreducibles**:
- $1 + i$
- Primes $p \equiv 3 \pmod{4}$
- Factors of primes $p \equiv 1 \pmod{4}$

## Example 4: $\mathbb{Z}[x]$ (Integer Polynomials)

**UFD**: Yes ✓ (by Gauss's Lemma)

**Not PID**: Ideal $\langle 2, x \rangle$ is not principal

**예**:
$$6x^2 - 2x = 2x(3x - 1)$$

Irreducible over $\mathbb{Z}[x]$:
- $2$, $3$, $5$, ... (prime numbers)
- $x$, $x-1$, $x+1$, ...
- Irreducible polynomials over $\mathbb{Q}$ with integer coefficients

## Example 5: $k[x, y]$ (Multivariate)

Field $k$에 대해:

**UFD**: Yes ✓ (by repeated application of Gauss)

**Not PID**: $\langle x, y \rangle$ is not principal

**Irreducibles**:
- $x$, $y$
- Irreducible polynomials in two variables

**예**:
$$x^2 - y^2 = (x-y)(x+y)$$
$$x^2 + y^2$$ (irreducible over $\mathbb{R}$ but not over $\mathbb{C}$)

## Example 6: $\mathbb{Z}[\sqrt{-5}]$ (Not UFD!)

$$\mathbb{Z}[\sqrt{-5}] = \{a + b\sqrt{-5} : a, b \in \mathbb{Z}\}$$

**UFD**: No ✗

**반례**:
$$6 = 2 \cdot 3 = (1 + \sqrt{-5})(1 - \sqrt{-5})$$

**검증**: 
- $2$, $3$, $1 \pm \sqrt{-5}$ are all irreducible
- Not associates (check norms)
- 두 가지 본질적으로 다른 인수분해!

**Norm**: $N(a + b\sqrt{-5}) = a^2 + 5b^2$

## Example 7: $\mathbb{Z}[\sqrt{2}]$

$$\mathbb{Z}[\sqrt{2}] = \{a + b\sqrt{2} : a, b \in \mathbb{Z}\}$$

**UFD**: Yes ✓ (Euclidean domain)

**Units**: $\{\pm 1, \pm (1 + \sqrt{2})^n : n \in \mathbb{Z}\}$ (infinite!)

**Pell equation**: $x^2 - 2y^2 = 1$

## Example 8: $\mathbb{C}[x, y, z]/(xy - z^2)$

**UFD**: No ✗

Quotient by non-prime element destroys UFD property

---

# <span class="header-properties">Properties</span>

## Characterizations of UFD

**정리**: Integral domain $R$에 대해 다음은 동등:

1. $R$ is UFD
2. Every nonzero non-unit factors into irreducibles, uniquely (up to associates and order)
3. Every irreducible is prime, and factorization exists
4. $R$ satisfies ACCP^[상승 사슬 조건] on principal ideals, and every irreducible is prime

**ACCP** (Ascending Chain Condition on Principal Ideals):

$$\langle a_1 \rangle \subseteq \langle a_2 \rangle \subseteq \langle a_3 \rangle \subseteq \cdots \quad \Rightarrow \quad \exists n: \langle a_n \rangle = \langle a_{n+1} \rangle = \cdots$$

## Factorization Algorithms

UFD에서 factorization을 실제로 계산하는 것은 별개 문제!

**예**:
- $\mathbb{Z}$: Trial division, Pollard's rho, etc.
- $\mathbb{Z}[x]$: Content-primitive decomposition
- $k[x]$: Polynomial factorization algorithms

**Complexity**: 일반적으로 어려운 문제 (integer factorization is hard)

## GCD and LCM^[최대공약수와 최소공배수]

UFD $R$에서:

**GCD exists**: $\gcd(a, b)$ 항상 존재 (up to associates)

**LCM exists**: $\text{lcm}(a, b)$ 항상 존재

**관계**:
$$\gcd(a, b) \cdot \text{lcm}(a, b) \sim ab$$

**Bezout's identity는 일반적으로 성립 안 함**:
- PID에서는 성립: $\gcd(a, b) = ra + sb$
- UFD에서는 일반적으로 불가능

**예**: $\mathbb{Z}[x]$에서
$$\gcd(2, x) = 1$$
하지만 $1 \neq 2f(x) + xg(x)$ for any $f, g \in \mathbb{Z}[x]$

## Prime Factorization Uniqueness

**정리**: UFD에서 $a \in R$ (nonzero, non-unit)의 prime factorization:

$$a = u p_1^{e_1} p_2^{e_2} \cdots p_k^{e_k}$$

where:
- $u \in R^\times$ (unit)
- $p_i$ are non-associate primes
- $e_i \geq 1$

이는 **유일** (primes의 선택과 순서 제외)

## Atomic Domain^[원자 정역]

**정의**: 모든 nonzero non-unit이 irreducibles의 곱 (factorization exists, uniqueness not required)

$$\text{UFD} \Rightarrow \text{Atomic Domain}$$

역은 일반적으로 거짓!

**예**: Atomic but not UFD domains 존재

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**UFD = "정수처럼 작동하는 domain"**

**핵심 아이디어**:
- 모든 원소는 "소수"들의 곱으로 유일하게 분해
- Fundamental Theorem of Arithmetic의 일반화

**기하학적**: 
- Irreducibles = "Building blocks"
- Factorization = "분해하여 이해"

## Why "Unique" Factorization?

**"Unique"의 의미**:
- Associates 제외 (unit 배수는 "같다고" 봄)
- 순서 제외

**예**: $\mathbb{Z}$에서
$$12 = 2 \cdot 2 \cdot 3 = 3 \cdot 2 \cdot 2 = (-2) \cdot (-2) \cdot 3$$

모두 "같은" 인수분해

## Prime vs Irreducible^[소 원소 vs 기약 원소]

**일반 Integral Domain**:
- Prime $\Rightarrow$ Irreducible (항상)
- Irreducible $\not\Rightarrow$ Prime (일반적으로)

**UFD**:
- Prime $\Leftrightarrow$ Irreducible ✓

**예** (Not UFD): $\mathbb{Z}[\sqrt{-5}]$
- $3$ is irreducible
- $3 \mid (1 + \sqrt{-5})(1 - \sqrt{-5}) = 6$
- But $3 \nmid 1 + \sqrt{-5}$ and $3 \nmid 1 - \sqrt{-5}$
- 따라서 $3$ is NOT prime!

## Hierarchy^[계층]

```
Field ⊂ Euclidean Domain ⊂ PID ⊂ UFD ⊂ Integral Domain
```

**각 포함은 strict**:

| Domain | UFD? | PID? | Euclidean? |
|--------|------|------|------------|
| $\mathbb{Z}$ | ✓ | ✓ | ✓ |
| $k[x]$ | ✓ | ✓ | ✓ |
| $\mathbb{Z}[x]$ | ✓ | ✗ | ✗ |
| $k[x, y]$ | ✓ | ✗ | ✗ |
| $\mathbb{Z}[\sqrt{-5}]$ | ✗ | ✗ | ✗ |
| $\mathbb{Z}[\frac{1+\sqrt{-19}}{2}]$ | ✗ | ✓ | ✗ |

## 응용 분야

### 1. Number Theory^[정수론]

**Algebraic integers**: $\mathcal{O}_K$ (ring of integers in number field)

**Question**: UFD인가?
- $\mathbb{Z}$: Yes
- $\mathbb{Z}[i]$: Yes
- $\mathbb{Z}[\omega]$ (where $\omega = e^{2\pi i/3}$): Yes
- $\mathbb{Z}[\sqrt{-5}]$: No

**Class number**: UFD failure 측정

### 2. Algebraic Geometry^[대수기하학]

**Coordinate rings**: Affine varieties의 coordinate ring

**UFD ⇔ 기하학적 성질**:
- UFD $\Leftrightarrow$ Factorial variety
- Regular ring과 관련

### 3. Polynomial Factorization

**알고리즘**:
- $\mathbb{Z}[x]$: Zassenhaus algorithm
- $k[x]$: Berlekamp algorithm, Cantor-Zassenhaus

**응용**: 
- Cryptography
- Coding theory
- Computer algebra systems

### 4. Ideal Theory

**UFD에서**:
- Principal ideal $\langle p \rangle$ is prime $\Leftrightarrow$ $p$ is prime element
- Ideal structure 더 단순

### 5. Module Theory

**Structure theorems**:
- Finitely generated modules over PID
- Classification of abelian groups

## 역사적 배경

**고대**:
- Euclid: GCD algorithm
- Fundamental Theorem of Arithmetic (unique factorization in $\mathbb{Z}$)

**19세기**:
- **Kummer**: Failure of unique factorization in cyclotomic integers
- **Dedekind**: Ideal theory to "restore" unique factorization
- **Gauss**: Gaussian integers, polynomial rings

**20세기**:
- Abstract definition of UFD
- Characterization theorems
- Connection to algebraic geometry

## Common Patterns^[일반적 패턴]

### Pattern 1: Polynomial Rings

$$R \text{ is UFD} \quad \Rightarrow \quad R[x] \text{ is UFD}$$

**Iteration**:
$$k[x_1, \ldots, x_n] \text{ is UFD}$$

### Pattern 2: Localization

UFD $R$, multiplicative set $S$:

$$S^{-1}R \text{ is UFD (in general)}$$

### Pattern 3: Integral Closure

UFD는 **integrally closed**^[정수적으로 닫힘]:

$$R \subseteq \text{Frac}(R), \quad \alpha \text{ integral over } R \Rightarrow \alpha \in R$$

## Common Pitfalls^[흔한 실수]

### 1. Irreducible ≠ Prime (일반적으로)

✗ 모든 integral domain에서 irreducible = prime?

✓ UFD에서만!

**반례**: $\mathbb{Z}[\sqrt{-5}]$에서 $3$ is irreducible but not prime

### 2. UFD ≠ PID

✗ UFD이면 PID?

✓ 역: PID $\Rightarrow$ UFD

**반례**: $\mathbb{Z}[x]$ is UFD but not PID

### 3. Factorization Exists ≠ UFD

✗ Factorization 존재하면 UFD?

✓ **Uniqueness** 필요!

Atomic domain $\neq$ UFD

### 4. Polynomial Ring

✗ $R$ integral domain $\Rightarrow$ $R[x]$ UFD?

✓ $R$ UFD $\Rightarrow$ $R[x]$ UFD

### 5. GCD Representation

✗ UFD에서 $\gcd(a, b) = ra + sb$?

✓ PID에서만! (Bezout's identity)

UFD에서 GCD는 존재하지만 linear combination으로 표현 안 될 수 있음

## Why Study UFD?^[UFD를 공부하는 이유]

**1. Generalization**: $\mathbb{Z}$의 성질 일반화

**2. Factorization**: 인수분해 이론의 기초

**3. Ideal Theory**: Prime/maximal ideals 이해

**4. Applications**: Number theory, geometry, algebra

**5. Counterexamples**: Non-UFD로 한계 이해

## Non-UFD Domains

**중요한 예**:

1. **$\mathbb{Z}[\sqrt{-5}]$**: Classic example

2. **$k[x, y, z]/(xy - z^2)$**: Geometric example

3. **Certain number rings**: Class number $> 1$

**Dedekind domains**: Ideal factorization으로 "복구"

## Extensions and Generalizations

**Beyond UFD**:

1. **GCD domains**: GCD exists but not necessarily unique factorization

2. **Dedekind domains**: Ideal unique factorization

3. **Krull domains**: Divisorial ideals

4. **Factorial rings**: Non-domain generalization

## 관련 개념

- [[Integral Domain]]: Base concept
- [[Principal Ideal Domain]]: PID $\Rightarrow$ UFD
- [[Euclidean Domain]]: Euclidean $\Rightarrow$ PID $\Rightarrow$ UFD
- [[Prime Ideal]]: Prime elements generate prime ideals
- [[Polynomial Ring]]: UFD $\Rightarrow$ UFD[x]
- [[Field]]: Every field is UFD (trivially)
- [[Commutative Ring]]: General framework
- [[Ring]]: Basic structure

