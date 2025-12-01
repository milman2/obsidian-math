# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Generator]]
- [[Subgroup]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Cyclic Group^[순환군]

Group $G$가 **cyclic^[순환]**이다 $\Leftrightarrow$ 단일 원소로 생성됨

$$\exists g \in G, \quad G = \langle g \rangle = \{g^n : n \in \mathbb{Z}\}$$

원소 $g$를 $G$의 **generator^[생성원]**라 함

### Additive Notation^[덧셈 표기]

Abelian groups (특히 cyclic groups)에서:

$$G = \langle g \rangle = \{ng : n \in \mathbb{Z}\}$$

## Finite Cyclic Group^[유한 순환군]

Order $n$인 cyclic group:

$$G = \langle g \rangle = \{e, g, g^2, \ldots, g^{n-1}\}$$

where $g^n = e$

**Properties**:
- $|G| = n$
- $\text{ord}(g) = n$ (generator의 위수 = 군의 위수)
- $g^i = g^j \Leftrightarrow i \equiv j \pmod{n}$

## Infinite Cyclic Group^[무한 순환군]

$$G = \langle g \rangle = \{\ldots, g^{-2}, g^{-1}, e, g, g^2, \ldots\}$$

**Properties**:
- $|G| = \infty$
- $\text{ord}(g) = \infty$
- $g^i = g^j \Leftrightarrow i = j$

## Generators^[생성원들]

### Finite Case

Order $n$인 cyclic group $G = \langle g \rangle$에 대해:

**정리**: $g^k$가 generator $\Leftrightarrow$ $\gcd(k, n) = 1$

**Generators 개수**: $\phi(n)$ (Euler's totient function^[오일러 파이 함수])

$$\phi(n) = n \prod_{p \mid n} \left(1 - \frac{1}{p}\right)$$

**예**: $\mathbb{Z}/12\mathbb{Z}$
- Generators: $[1], [5], [7], [11]$ (총 $\phi(12) = 4$개)

### Infinite Case

Infinite cyclic group $G = \langle g \rangle$의 generators:

**정확히 2개**: $g$와 $g^{-1}$

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$ (Integers under Addition)

$$\mathbb{Z} = \langle 1 \rangle = \langle -1 \rangle$$

**Generators**: $1$ and $-1$

**Structure**: Infinite cyclic group

**원소**: $\ldots, -2, -1, 0, 1, 2, \ldots$

## Example 2: $\mathbb{Z}/n\mathbb{Z}$ (Integers Modulo $n$)

$$\mathbb{Z}/n\mathbb{Z} = \{[0], [1], [2], \ldots, [n-1]\}$$

**Generator**: $[1]$ (표준 generator)

**Order**: $n$

**연산**: $[a] + [b] = [a+b \bmod n]$

### Specific Examples

**$\mathbb{Z}/6\mathbb{Z}$**:
- Generators: $[1], [5]$ ($\phi(6) = 2$)
- $\langle [1] \rangle = \{[0], [1], [2], [3], [4], [5]\}$
- $\langle [2] \rangle = \{[0], [2], [4]\}$ (not a generator, subgroup of order 3)

## Example 3: $(\mathbb{Z}/p\mathbb{Z})^\times$ for Prime $p$

$$(\mathbb{Z}/p\mathbb{Z})^\times = \{[1], [2], \ldots, [p-1]\}$$

**Cyclic**: 항상 cyclic (for prime $p$)

**Order**: $p-1$

**Generator**: **Primitive root modulo $p$^[원시근]**

**예**: $(\mathbb{Z}/7\mathbb{Z})^\times$
- Order 6
- Generator: $[3]$ (primitive root)
- $\langle [3] \rangle = \{[1], [3], [2], [6], [4], [5]\}$

## Example 4: Roots of Unity^[1의 거듭제곱근]

$n$-th roots of unity in $\mathbb{C}$:

$$\mu_n = \{z \in \mathbb{C} : z^n = 1\} = \{e^{2\pi i k/n} : k = 0, 1, \ldots, n-1\}$$

**Group structure**: Cyclic of order $n$

**Generator**: $\zeta_n = e^{2\pi i/n}$ (primitive $n$-th root)

**연산**: Complex multiplication

## Example 5: $\mathbb{R}/\mathbb{Z}$ (Circle Group)

$$\mathbb{R}/\mathbb{Z} = \{x + \mathbb{Z} : x \in \mathbb{R}\}$$

**Not cyclic!** (uncountable)

**Divisible**: 모든 원소가 $n$-th root를 가짐

**Isomorphic to**: $S^1 = \{z \in \mathbb{C} : |z| = 1\}$ (unit circle)

## Example 6: Subgroups of $\mathbb{Z}$

$$n\mathbb{Z} = \{nk : k \in \mathbb{Z}\} = \langle n \rangle$$

**All cyclic**: $\mathbb{Z}$의 모든 subgroup은 cyclic

**Lattice**:
```
     Z
    /|\
   / | \
  2Z 3Z 5Z ...
   \ | /
    \|/
    {0}
```

## Example 7: Subgroups of $\mathbb{Z}/n\mathbb{Z}$

Divisor $d \mid n$에 대해:

$$\langle [d] \rangle = \{[0], [d], [2d], \ldots\}$$

**Order**: $|\langle [d] \rangle| = n/d$

**All cyclic**: Cyclic group의 모든 subgroup은 cyclic

**Unique**: 각 divisor $d$에 대해 정확히 하나의 order $n/d$ subgroup

## Example 8: Klein Four-Group (NOT Cyclic)

$$V_4 = \{e, a, b, c\}$$ where $a^2 = b^2 = c^2 = e$, $ab = c$

**Not cyclic**: 모든 non-identity 원소가 order 2

**No generator**: 어떤 원소도 $V_4$ 전체를 생성 못함

**Abelian but not cyclic**

## Example 9: Quaternion Group (NOT Cyclic)

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

**Not cyclic**: Order 8 but no element of order 8

**Non-abelian**

## Example 10: $C_2 \times C_2$ vs $C_4$

**$C_2 \times C_2$** (Klein four-group):
- Order 4
- Not cyclic
- All elements have order $\leq 2$

**$C_4$** (Cyclic of order 4):
- Order 4
- Cyclic
- Has element of order 4

**Not isomorphic!**

---

# <span class="header-properties">Properties</span>

## Fundamental Properties^[기본 성질]

### 1. Abelian

**정리**: 모든 cyclic group은 abelian^[아벨]

**증명**: $G = \langle g \rangle$이면
$$g^m \cdot g^n = g^{m+n} = g^{n+m} = g^n \cdot g^m$$

### 2. Subgroups are Cyclic

**정리**: Cyclic group의 모든 subgroup은 cyclic

**증명**: $G = \langle g \rangle$, $H \leq G$이면
- $H = \{e\}$ $\Rightarrow$ $H = \langle e \rangle$ (trivial)
- $H \neq \{e\}$ $\Rightarrow$ $H = \langle g^d \rangle$ for some $d$

### 3. Order of Elements

Cyclic group $G = \langle g \rangle$, $|G| = n$에서:

$$\text{ord}(g^k) = \frac{n}{\gcd(k, n)}$$

**예**: $\mathbb{Z}/12\mathbb{Z}$에서
- $\text{ord}([3]) = 12/\gcd(3,12) = 12/3 = 4$
- $\text{ord}([8]) = 12/\gcd(8,12) = 12/4 = 3$

## Classification Theorem^[분류 정리]

### Finite Cyclic Groups

**정리**: Order $n$인 모든 cyclic group은 isomorphic

$$G \cong \mathbb{Z}/n\mathbb{Z}$$

**유일성**: Isomorphism을 제외하고 유일

### Infinite Cyclic Groups

**정리**: 모든 infinite cyclic group은 isomorphic

$$G \cong \mathbb{Z}$$

**유일성**: Isomorphism을 제외하고 유일

자세한 내용은 [[Isomorphism]] 참조

## Subgroup Structure^[부분군 구조]

### Lattice of Subgroups

Order $n$인 cyclic group $G = \langle g \rangle$:

**Subgroups**: Each divisor $d \mid n$에 대해 정확히 하나의 order $d$ subgroup

$$H_d = \langle g^{n/d} \rangle, \quad |H_d| = d$$

**개수**: $\tau(n)$ (number of divisors of $n$)

### Example: $\mathbb{Z}/12\mathbb{Z}$

Divisors of 12: $1, 2, 3, 4, 6, 12$

```
    ⟨[1]⟩ (order 12)
      |
  ----+----
  |   |   |
⟨[2]⟩⟨[3]⟩⟨[4]⟩
  |   |   |
  ----+----
      |
    ⟨[6]⟩ (order 2)
      |
    {[0]} (order 1)
```

## Direct Products of Cyclic Groups^[순환군의 직접곱]

### Chinese Remainder Theorem (CRT)

$$\gcd(m, n) = 1 \Rightarrow C_m \times C_n \cong C_{mn}$$

**More generally**:
$$\mathbb{Z}/n\mathbb{Z} \cong \mathbb{Z}/n_1\mathbb{Z} \times \cdots \times \mathbb{Z}/n_k\mathbb{Z}$$
where $n = n_1 \cdots n_k$ and $\gcd(n_i, n_j) = 1$ for $i \neq j$

**예**:
- $C_2 \times C_3 \cong C_6$ - $C_2 \times C_2 \not\cong C_4$ ✗ (not coprime to itself)

### Fundamental Theorem of Finite Abelian Groups

모든 finite abelian group은 cyclic groups의 direct sum:

$$G \cong C_{p_1^{a_1}} \times C_{p_2^{a_2}} \times \cdots \times C_{p_k^{a_k}}$$

자세한 내용은 [[Direct Sum]] 참조

## Automorphism Group^[자기동형군]

Cyclic group $G = \langle g \rangle$의 automorphism group:

### Finite Case

$$\text{Aut}(C_n) \cong (\mathbb{Z}/n\mathbb{Z})^\times$$

**Order**: $|\text{Aut}(C_n)| = \phi(n)$

**구조**: 
- $g \mapsto g^k$ ($\gcd(k,n) = 1$)이 automorphism
- 모든 automorphism이 이 형태

### Infinite Case

$$\text{Aut}(\mathbb{Z}) \cong C_2$$

**Automorphisms**: 
- Identity: $n \mapsto n$
- Negation: $n \mapsto -n$

---

# <span class="header-theorem">Theorem</span>

## Characterization of Cyclic Groups^[순환군의 특성화]

다음은 동등:

1. $G$ is cyclic
2. $G \cong \mathbb{Z}/n\mathbb{Z}$ (finite) or $G \cong \mathbb{Z}$ (infinite)
3. $G$의 모든 subgroup이 cyclic
4. $G$는 abelian이고 order $d$인 원소가 최대 $d$개 (for each $d \mid |G|$)

## Prime Order Groups^[소수 위수 군]

**정리**: $|G| = p$ (prime) $\Rightarrow$ $G \cong C_p$

**증명**: 
- Lagrange: $\forall g \neq e$, $\text{ord}(g) \mid p$
- Prime이므로 $\text{ord}(g) = p$
- $G = \langle g \rangle$ (cyclic)

**결과**: Prime order groups는 본질적으로 하나

## Cauchy's Theorem for Cyclic Groups

$p \mid |G|$ (prime)이면 order $p$인 원소 존재

Cyclic groups에서는 더 강함: **정확히 $\phi(p) = p-1$개**

## Generators and Relations^[생성원과 관계식]

### Presentation

$$C_n = \langle g \mid g^n = e \rangle$$

**의미**: 
- Generator: $g$
- Relation: $g^n = e$

### Infinite Cyclic

$$\mathbb{Z} = \langle g \mid \; \rangle$$

**No relations!** (free cyclic group)

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Cyclic Group**: "회전으로 생성되는 대칭"

**메타포**:
- **시계**: 12시간마다 반복 ($C_{12}$)
- **달력**: 7일마다 반복 ($C_7$)
- **수직선**: 정수 ($\mathbb{Z}$)
- **원**: 각도 ($\mathbb{R}/\mathbb{Z} \cong S^1$)

**핵심**: 단순하고 명확한 구조

## Cyclic vs Non-cyclic

| | **Cyclic** | **Non-cyclic** |
|---|---|---|
| Generators | 1개로 충분 | 2개 이상 필요 |
| Abelian | 항상 | Not always |
| Structure | Simple | Complex |
| 예 | $\mathbb{Z}/n\mathbb{Z}$ | $V_4$, $S_n$ |

## Why "Cyclic"?

**이름의 유래**: "Cycle" = 순환

원소들이 cycle을 형성:
$$e \to g \to g^2 \to \cdots \to g^{n-1} \to e$$

기하학적으로 원(circle)과 연관

## 표기법

| 표기 | 의미 |
|------|------|
| $C_n$ | Cyclic group of order $n$ |
| $\mathbb{Z}/n\mathbb{Z}$ | Integers modulo $n$ |
| $\langle g \rangle$ | Cyclic group generated by $g$ |
| $\text{ord}(g)$ | Order of element $g$ |
| $\phi(n)$ | Euler's totient function |
| $\mu_n$ | $n$-th roots of unity |

## Prime vs Composite Order

### Prime Order $p$

- **Simple structure**: $C_p$만 존재
- **All generators**: $p-1$개 ($\phi(p) = p-1$)
- **No proper subgroups**: $\{e\}$와 $C_p$만

### Composite Order $n = p_1^{a_1} \cdots p_k^{a_k}$

- **Rich structure**: Many subgroups
- **Some generators**: $\phi(n)$개
- **Proper subgroups**: Each divisor

## Common Pitfall^[흔한 실수]

### 1. Abelian = Cyclic?

✗ Abelian이라고 해서 cyclic은 아님!

**반례**: $V_4 = C_2 \times C_2$ (abelian but not cyclic)

 Cyclic $\Rightarrow$ Abelian (always)

### 2. All elements are generators?

✗ Only some elements!

Finite: $\phi(n)$개만 generator

### 3. $C_m \times C_n \cong C_{mn}$?

✗ 항상 성립하는 것은 아님!

 $\gcd(m,n) = 1$일 때만

**반례**: $C_2 \times C_2 \not\cong C_4$

### 4. Order of subgroup?

✗ Any divisor $\Rightarrow$ subgroup exists?

✓ Cyclic groups에서는 **yes**! (but not general groups)

### 5. Generators in infinite case?

✗ Infinite cyclic group has infinite generators?

✓ **No!** Exactly 2: $g$ and $g^{-1}$

## 응용

**Number Theory**:
- Modular arithmetic
- Primitive roots
- Euler's theorem

**Cryptography**:
- Diffie-Hellman key exchange
- Cyclic groups in finite fields
- Discrete logarithm problem

**Physics**:
- Periodic phenomena
- Crystal symmetries
- Quantum mechanics (phase)

**Chemistry**:
- Molecular symmetry
- Rotation groups

## 역사적 배경

**Ancient**: 
- Modular arithmetic (중국, 인도)
- Fermat, Euler: Number theory

**19th Century**:
- Gauss: Modular arithmetic 체계화
- Group theory 발전

**Modern**:
- Abstract algebra
- Applications in cryptography

## 관련 개념

- [[Group]]: Basic group theory
- [[Generator]]: Generating sets
- [[Subgroup]]: Subgroup structure
- [[Isomorphism]]: Classification
- [[Direct Sum]]: Products of cyclic groups

## 추가 학습 주제

**기초**:
- Generators and orders
- Subgroup lattice
- Euler's totient function

**중급**:
- Primitive roots
- Chinese remainder theorem
- Cyclotomic polynomials

**고급**:
- Profinite completion
- p-adic integers
- Infinite cyclic groups

