# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Symmetric Group]]
- [[Permutation Group]]
- [[Normal Subgroup]]
- [[Simple Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Rotman, An Introduction to the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Alternating Group^[교대군]

**정의**: Symmetric group $S_n$의 even permutations의 subgroup

$$A_n = \{\sigma \in S_n : \text{sgn}(\sigma) = 1\}$$

where $\text{sgn}$ = sign^[부호] homomorphism

### Sign of Permutation^[순열의 부호]

$$\text{sgn}: S_n \to \{1, -1\}$$

$$\text{sgn}(\sigma) = \begin{cases}
1 & \text{if } \sigma \text{ is even} \\
-1 & \text{if } \sigma \text{ is odd}
\end{cases}$$

**Even permutation**^[짝순열]: 짝수 개의 transpositions의 곱

**Odd permutation**^[홀순열]: 홀수 개의 transpositions의 곱

### Alternative Definition

$$\text{sgn}(\sigma) = \prod_{i<j} \frac{\sigma(i) - \sigma(j)}{i - j}$$

**또는**: 
$$\text{sgn}(\sigma) = (-1)^{\text{number of inversions}}$$

## Order of $A_n$

$$|A_n| = \frac{n!}{2}$$

**증명**: $\text{sgn}: S_n \to \{1, -1\}$ surjective

$A_n = \ker(\text{sgn})$

$[S_n : A_n] = |S_n|/|A_n| = 2$

따라서 $|A_n| = n!/2$ 
---

# <span class="header-properties">Properties</span>

## Normal Subgroup

**정리**: $A_n \triangleleft S_n$ for all $n \geq 2$

**증명**: Index 2 subgroups are always normal

$$[S_n : A_n] = 2$$

자세한 내용은 [[Normal Subgroup]] 참조

## Simplicity of $A_n$ ($n \geq 5$)

**정리**: $A_n$ is simple for $n \geq 5$

$$n \geq 5 \Rightarrow A_n \text{ has no proper nontrivial normal subgroups}$$

**의미**: $A_5, A_6, A_7, \ldots$ are simple groups

**중요성**: 가장 기본적인 non-abelian simple groups

자세한 내용은 [[Simple Group]] 참조

### Non-simple Cases

- **$A_1 = \{e\}$**: Trivial
- **$A_2 = \{e\}$**: Trivial
- **$A_3 \cong \mathbb{Z}/3\mathbb{Z}$**: Cyclic of order 3 (simple, abelian)
- **$A_4$**: NOT simple (has $V_4 \triangleleft A_4$)

## Generators

**정리**: $A_n$은 3-cycles로 generate됨 ($n \geq 3$)

$$A_n = \langle (abc) : a, b, c \text{ distinct in } \{1, \ldots, n\} \rangle$$

**증명**: 
- Even permutation = even number of transpositions
- $(ab)(cd) = (abc)(bcd)$ (disjoint case)
- $(ab)(bc) = (abc)$
- $(ab)(ab) = e$

**개수**: $\binom{n}{3} \cdot 2 = \frac{n(n-1)(n-2)}{3}$ 3-cycles

## Quotient

$$S_n / A_n \cong \mathbb{Z}/2\mathbb{Z}$$

**Isomorphism**: $\text{sgn}: S_n \to \{1, -1\} \cong \mathbb{Z}/2\mathbb{Z}$

**Kernel**: $\ker(\text{sgn}) = A_n$

**First Isomorphism Theorem**: $S_n/A_n \cong \text{im}(\text{sgn}) = \{1, -1\}$ 
자세한 내용은 [[Isomorphism]] 참조

## Conjugacy Classes

$A_n$의 conjugacy classes ≠ $S_n$의 conjugacy classes (일반적으로)

**경우 1**: $S_n$ conjugacy class가 $A_n$에서 split

**경우 2**: $S_n$ conjugacy class가 $A_n$에서 그대로

**예** ($A_5$): (12345)와 (12354)는 $S_5$에서 conjugate이지만 $A_5$에서는 아님

---

# <span class="header-examples">Examples</span>

## Example 1: $A_3$

$$A_3 = \{e, (123), (132)\}$$

**Order**: $|A_3| = 3!/2 = 3$

**Structure**: Cyclic group $\mathbb{Z}/3\mathbb{Z}$

**Simple**: Yes (prime order)

**Abelian**: Yes (order 3)

## Example 2: $A_4$

$$|A_4| = 4!/2 = 12$$

**Elements**:
- Identity: $e$
- 3-cycles (8): $(123), (132), (124), (142), (134), (143), (234), (243)$
- Double transpositions (3): $(12)(34), (13)(24), (14)(23)$

**Klein four-group**: $V_4 = \{e, (12)(34), (13)(24), (14)(23)\}$

**Normal subgroup**: $V_4 \triangleleft A_4$

**따라서**: $A_4$ is NOT simple

**Quotient**: $A_4/V_4 \cong \mathbb{Z}/3\mathbb{Z}$

## Example 3: $A_5$

$$|A_5| = 5!/2 = 60$$

**Simple**: Yes! (첫 번째 non-abelian simple group)

**Order 60인 유일한 simple group** (up to isomorphism)

**Conjugacy classes in $A_5$**:
1. Identity: 1 element
2. 3-cycles: 20 elements (2 classes of 20 each in some counts)
3. 5-cycles: 24 elements (2 classes)
4. Double transpositions: 15 elements

**응용**: 5차 방정식의 일반 해가 없음 (Galois theory)

자세한 내용은 [[Galois Theory]] 참조

## Example 4: $A_6$

$$|A_6| = 6!/2 = 360$$

**Simple**: Yes

**특이점**: $A_6$는 outer automorphism을 가짐

$$|\text{Aut}(A_6)|/|A_6| = 4$$

**유일**: $n \neq 6$일 때 $\text{Aut}(A_n) \cong S_n$

## Example 5: Even Permutations in $S_4$

$$A_4 \subseteq S_4$$

**Even permutations**:
- $e$
- 8 3-cycles
- 3 double transpositions

**Total**: 12 = $4!/2$ 
---

# <span class="header-theorem">Theorem</span>

## Simplicity of $A_n$ ($n \geq 5$)

**정리**: $n \geq 5$일 때 $A_n$은 simple

### 증명 스케치

1. **3-cycles generate**: $A_n = \langle 3\text{-cycles} \rangle$
2. **Normal subgroup contains 3-cycle**: $N \triangleleft A_n$, $N \neq \{e\}$ $\Rightarrow$ $N$ contains a 3-cycle
3. **All 3-cycles conjugate**: One 3-cycle $\Rightarrow$ all 3-cycles (in $N$)
4. **Therefore**: $N = A_n$ 
## Galois Theory Application

**정리**: 일반 5차 방정식은 근의 공식이 없음

**증명**:
- 일반 5차 방정식의 Galois group = $S_5$ (또는 $A_5$)
- $S_5$는 solvable이 아님 ($A_5$ simple)
- Solvable by radicals $\Leftrightarrow$ Galois group solvable
- 따라서 근의 공식 없음 
자세한 내용은 [[Galois Theory]] 참조

## Isomorphisms

### $A_4 \cong \text{PSL}_2(\mathbb{F}_3)$

Projective special linear group

### $A_5 \cong \text{PSL}_2(\mathbb{F}_5)$

Also: $A_5 \cong$ Icosahedral group (회전 대칭)

### $A_6 \cong \text{PSL}_2(\mathbb{F}_9)$

Exceptional isomorphism

## Schur Multiplier

**$H^2(A_n, \mathbb{Z})$** (Schur multiplier):
- $n \geq 4$: $H^2(A_n, \mathbb{Z}) \cong \mathbb{Z}/2\mathbb{Z}$
- $n = 6, 7$: 예외적 행동

**응용**: Central extensions, Covering groups

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Alternating Group = "Even permutations"**

### 메타포: 스위치

**Transposition**: 두 개 스위치

**Even**: 짝수 번 스위치 = 원래 "parity" 유지

**Odd**: 홀수 번 스위치 = "parity" 변경

### 메타포: 회전 vs 반사

**$A_n$**: "순수 회전" (orientation-preserving)

**$S_n \setminus A_n$**: "반사 포함" (orientation-reversing)

## 왜 중요한가?

### 1. Simple Groups

**$A_n$ ($n \geq 5$)**: 무한 family of simple groups

**Classification**: Simple groups 분류의 핵심 family

### 2. Galois Theory

**5차 방정식**: $A_5$ simple $\Rightarrow$ no general formula

**Solvability**: Group structure ↔ Equation solvability

### 3. Geometry

**Icosahedral symmetry**: $A_5 \cong$ Rotations of icosahedron

**Platonic solids**: Symmetry groups 연결

### 4. Representation Theory

**Irreducible representations**: Well-understood structure

## $A_n$의 특별한 점

| $n$ | $\|A_n\|$ | Simple? | 특징 |
|-----|----------|---------|------|
| 1, 2 | 1 | Trivial | - |
| 3 | 3 | Yes | Abelian, cyclic |
| 4 | 12 | **No** | Has $V_4 \triangleleft A_4$ |
| 5 | 60 | Yes | **첫 non-abelian simple** |
| $\geq 6$ | $n!/2$ | Yes | Infinite family |

## Sign Homomorphism

**$\text{sgn}: S_n \to \{1, -1\}$**

**성질**:
- Homomorphism: $\text{sgn}(\sigma\tau) = \text{sgn}(\sigma)\text{sgn}(\tau)$
- Surjective: Transposition은 sign $-1$
- Kernel: $A_n$

**응용**:
- Determinant와 연결: $\det(P_\sigma) = \text{sgn}(\sigma)$
- Exterior algebra

## 계산 예시

### $(123)(45)$의 sign

**방법 1**: Transpositions로 분해

$(123) = (13)(12)$ (2개)

$(45)$ (1개)

Total: 3개 (홀수) $\Rightarrow$ sign = $-1$

**방법 2**: Sign 곱셈

$\text{sgn}(123) = 1$ (3-cycle, even)

$\text{sgn}(45) = -1$ (transposition)

$\text{sgn}((123)(45)) = 1 \cdot (-1) = -1$ 
**결론**: $(123)(45) \notin A_5$

## 응용 분야

**Galois Theory**:
- Polynomial equations
- Solvability by radicals

자세한 내용은 [[Galois Theory]] 참조

**Geometry**:
- Symmetry groups
- Platonic solids
- Icosahedral group

**Topology**:
- Covering spaces
- Braid groups

**Physics**:
- Particle statistics (fermions)
- Quantum mechanics

## 역사적 배경

**Évariste Galois** (1811-1832):
- Alternating groups 연구
- Simplicity of $A_5$
- Unsolvability of quintic

**Camille Jordan** (1870s):
- Jordan-Hölder theorem
- Composition series

**현대**:
- Classification of finite simple groups
- $A_n$ as fundamental examples

## 표기법

| 표기 | 의미 |
|------|------|
| $A_n$ | Alternating group |
| $\text{sgn}(\sigma)$ | Sign of permutation |
| $V_4$ | Klein four-group (in $A_4$) |
| $\text{PSL}_n$ | Projective special linear group |

## Common Pitfall^[흔한 실수]

### 1. $A_4$ is simple?

✗ No! $V_4 \triangleleft A_4$

Simple from $n \geq 5$

### 2. Sign calculation

$(abc)$ = 3-cycle = even (not 3 transpositions!)

$(abc) = (ac)(ab)$ (2개)

### 3. Conjugacy in $A_n$ vs $S_n$

Different! Some conjugacy classes split

### 4. $|A_n| = n!/2$

Not $n/2$ or $(n-1)!/2$

### 5. Generators

3-cycles generate $A_n$ (not just cycles)

## 관련 개념

- [[Symmetric Group]]: $A_n \leq S_n$
- [[Permutation Group]]: Even permutations
- [[Normal Subgroup]]: $A_n \triangleleft S_n$
- [[Simple Group]]: $A_n$ ($n \geq 5$)
- [[Galois Theory]]: Quintic unsolvability

## 추가 학습 주제

**기초**:
- Sign of permutation
- Even vs odd
- $A_3, A_4, A_5$ 구조

**중급**:
- Simplicity proof
- Conjugacy classes
- Generators

**고급**:
- Outer automorphisms
- Schur multiplier
- Covering groups

