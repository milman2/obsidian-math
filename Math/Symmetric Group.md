# <span class="header-prerequisite">Prerequisite</span>
- [[Permutation Group]]
- [[Group]]
- [[Subgroup]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- James & Kerber, The Representation Theory of the Symmetric Group

---

# <span class="header-definition">Definition</span>

## Symmetric Group $S_n$^[대칭군]

집합 $\{1, 2, \ldots, n\}$의 모든 permutations의 group:

$$S_n = \{\sigma : \{1, \ldots, n\} \to \{1, \ldots, n\} \text{ bijective}\}$$

**Order**: $|S_n| = n!$

**연산**: Function composition

### Small Cases

- $S_1 = \{e\}$ (trivial, order 1)
- $S_2 = \{e, (12)\}$ (cyclic, order 2)
- $S_3$ (order 6, smallest non-abelian)
- $S_4$ (order 24)
- $S_5$ (order 120)

## Notation Conventions^[표기 관례]

### Cycle Notation

$$(1 \; 2 \; 3) \in S_3: \quad 1 \to 2 \to 3 \to 1$$

자세한 내용은 [[Permutation Group]] 참조

### Two-line Notation

$$\begin{pmatrix} 1 & 2 & 3 & 4 \\ 3 & 1 & 4 & 2 \end{pmatrix}$$

### Product (Composition)

$$\sigma \tau: \quad (\sigma \tau)(x) = \sigma(\tau(x))$$

**Convention**: Right-to-left (본 노트)

---

# <span class="header-examples">Examples</span>

## Example 1: $S_3$ in Detail

### Elements (6개)

**Identity**: $e$

**Transpositions** (3개):
- $(12)$: $1 \leftrightarrow 2$
- $(13)$: $1 \leftrightarrow 3$
- $(23)$: $2 \leftrightarrow 3$

**3-cycles** (2개):
- $(123)$: $1 \to 2 \to 3 \to 1$
- $(132) = (321)$: $1 \to 3 \to 2 \to 1$

### Multiplication Table

| $\circ$ | $e$ | $(12)$ | $(13)$ | $(23)$ | $(123)$ | $(132)$ |
|---------|-----|--------|--------|--------|---------|---------|
| $e$ | $e$ | $(12)$ | $(13)$ | $(23)$ | $(123)$ | $(132)$ |
| $(12)$ | $(12)$ | $e$ | $(132)$ | $(123)$ | $(23)$ | $(13)$ |
| $(13)$ | $(13)$ | $(123)$ | $e$ | $(132)$ | $(12)$ | $(23)$ |
| $(23)$ | $(23)$ | $(132)$ | $(123)$ | $e$ | $(13)$ | $(12)$ |
| $(123)$ | $(123)$ | $(13)$ | $(23)$ | $(12)$ | $(132)$ | $e$ |
| $(132)$ | $(132)$ | $(23)$ | $(12)$ | $(13)$ | $e$ | $(123)$ |

### Subgroups

**Order 1**: $\{e\}$

**Order 2**:
- $\langle (12) \rangle = \{e, (12)\}$
- $\langle (13) \rangle = \{e, (13)\}$
- $\langle (23) \rangle = \{e, (23)\}$

**Order 3**:
- $A_3 = \langle (123) \rangle = \{e, (123), (132)\}$ (normal!)

**Order 6**: $S_3$

## Example 2: $S_4$ Structure

**Order**: $24 = 2^3 \cdot 3$

### Cycle Types and Counts

| Cycle Type | Example | Count | Order |
|------------|---------|-------|-------|
| $[1^4]$ | $e$ | 1 | 1 |
| $[2, 1^2]$ | $(12)$ | 6 | 2 |
| $[2^2]$ | $(12)(34)$ | 3 | 2 |
| $[3, 1]$ | $(123)$ | 8 | 3 |
| $[4]$ | $(1234)$ | 6 | 4 |

**Total**: $1 + 6 + 3 + 8 + 6 = 24$ ✓

### Notable Subgroups

**$V_4$ (Klein four-group)**:
$$V_4 = \{e, (12)(34), (13)(24), (14)(23)\} \triangleleft S_4$$

Normal subgroup!

**$A_4$ (Alternating group)**:
$$A_4 \triangleleft S_4, \quad |A_4| = 12$$

**$D_4$ (Dihedral group)**:
$$D_4 \leq S_4, \quad |D_4| = 8$$

Symmetries of square

## Example 3: Generators

### All Transpositions

$$S_n = \langle (12), (13), \ldots, (1n) \rangle$$

### Adjacent Transpositions

$$S_n = \langle (12), (23), \ldots, (n-1, n) \rangle$$

**Minimal**: $n-1$ generators needed

### Two Elements

$$S_n = \langle (12), (123 \cdots n) \rangle$$

One transposition + one $n$-cycle

## Example 4: Conjugacy Class Representatives

### In $S_4$

**[1, 1, 1, 1]**: $e$ (size 1)

**[2, 1, 1]**: $(12)$ (size 6)

**[2, 2]**: $(12)(34)$ (size 3)

**[3, 1]**: $(123)$ (size 8)

**[4]**: $(1234)$ (size 6)

**Total**: $1 + 6 + 3 + 8 + 6 = 24$ ✓

## Example 5: Dihedral Group in $S_n$

정 $n$각형의 대칭군 $D_n \leq S_n$:

**$D_3 \cong S_3$**: 정삼각형의 대칭 = $S_3$

**$D_4 \leq S_4$**: 정사각형의 대칭 (order 8)

자세한 내용은 [[Dihedral Group]] 참조

---

# <span class="header-properties">Properties</span>

## Non-Abelian for $n \geq 3$

**정리**: $S_n$은 $n \geq 3$일 때 non-abelian

**증명**: $(12)(13) = (132) \neq (123) = (13)(12)$

**특수한 경우**:
- $S_1$: Trivial (abelian)
- $S_2 \cong C_2$: Cyclic (abelian)

## Center^[중심]

$$Z(S_n) = \begin{cases} S_n & \text{if } n \leq 2 \\ \{e\} & \text{if } n \geq 3 \end{cases}$$

**의미**: $n \geq 3$일 때 center는 trivial

**증명**: $n \geq 3$일 때 모든 non-identity element는 어떤 원소와 non-commute

## Alternating Group^[교대군]

$$A_n = \{\sigma \in S_n : \text{sgn}(\sigma) = +1\} \triangleleft S_n$$

**Properties**:
- $|A_n| = n!/2$
- $[S_n : A_n] = 2$ (index 2이므로 normal!)
- $A_n$ is simple for $n \geq 5$

### Quotient

$$S_n/A_n \cong C_2$$

Isomorphic to $\mathbb{Z}/2\mathbb{Z}$

## Conjugacy in $S_n$

**정리**: $\sigma, \tau \in S_n$가 conjugate $\Leftrightarrow$ same cycle type

$$\sigma \sim \tau \Leftrightarrow \text{same partition of } n$$

**예**: $S_4$에서
- $(12)$ ~ $(34)$ (both type [2, 1, 1])
- $(123)$ ~ $(142)$ (both type [3, 1])
- $(12)$ ≁ $(123)$ (different types)

### Conjugation Formula

$$\tau (a_1 \; a_2 \; \cdots \; a_k) \tau^{-1} = (\tau(a_1) \; \tau(a_2) \; \cdots \; \tau(a_k))$$

**예**: $(12)(134)(12) = (234)$

## Sylow Subgroups^[실로우 부분군]

$|S_n| = n!$의 prime factorization으로 Sylow subgroups 결정

### $p = 2$ (Sylow 2-subgroups)

복잡한 구조, 많은 Sylow 2-subgroups

### $p > n$ (Sylow $p$-subgroups)

Cyclic of order $p$

**예**: $S_5$에서 Sylow 5-subgroup
- $\langle (12345) \rangle$ (order 5)
- 다른 5-cycles도 Sylow 5-subgroups

## Automorphism Group^[자기동형군]

$$\text{Aut}(S_n) \cong \begin{cases} S_n & \text{if } n \neq 6 \\ S_n \rtimes C_2 & \text{if } n = 6 \end{cases}$$

**특이한 경우**: $S_6$는 **outer automorphism** 있음!

**Inner automorphisms**: Conjugation

**Outer**: $S_6$만 존재

---

# <span class="header-theorem">Theorem</span>

## Cayley's Theorem^[케일리 정리]

**정리**: 모든 group $G$는 $S_{|G|}$의 subgroup과 isomorphic

$$G \hookrightarrow S_{|G|}$$

**증명**: Regular representation
$$\phi: G \to S_G, \quad \phi(g)(x) = gx$$

**의미**: Symmetric groups는 "universal" - 모든 군 포함

자세한 내용은 [[Permutation Group]], [[Isomorphism]] 참조

## Simplicity of $A_n$ ($n \geq 5$)

**정리**: $A_n$ is simple for $n \geq 5$

**의미**: Nontrivial proper normal subgroups 없음

**중요성**:
- 5차 이상 방정식의 근의 공식 불가능 (Abel-Ruffini theorem)
- Galois theory의 핵심

**특수한 경우**:
- $A_4$: NOT simple ($V_4 \triangleleft A_4$)
- $A_5$: Smallest non-abelian simple group (order 60)

자세한 내용은 [[Galois Theory]] 참조

## Classification of Subgroups

### Transitive Subgroups

$G \leq S_n$이 **transitive^[추이적]**이다 $\Leftrightarrow$

$$\forall i, j \in \{1, \ldots, n\}, \; \exists \sigma \in G, \; \sigma(i) = j$$

**예**: $S_n$, $A_n$, $D_n$ (for appropriate $n$)

### Primitive vs Imprimitive

**Primitive group^[원시군]**: No non-trivial block system

**Imprimitive group^[비원시군]**: Has block system

## Representation Theory

$S_n$의 **irreducible representations^[기약 표현]**: Young tableaux^[영 타블로]로 분류

**Dimension formula**: Hook length formula

**Applications**: 
- Combinatorics
- Symmetric functions
- Quantum mechanics

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Symmetric Group**: "모든 가능한 재배열"

**메타포**:
- **$n$명 줄 세우기**: $n!$ 가지 방법
- **카드 섞기**: 모든 가능한 순서
- **자리 배치**: 모든 가능한 arrangement

**핵심**: 완전한 대칭성

## Why "Symmetric"?

**이름의 유래**: "Symmetry" = 대칭

모든 permutations = 모든 대칭성

**기하학적**: 정$n$각형의 일부 대칭 (when embedded appropriately)

## $S_n$ as Universal Group

**Cayley's theorem**: 모든 finite group $\hookrightarrow$ $S_n$

**의미**: $S_n$은 충분히 "큰" group

**하지만**: 
- Embedding not unique
- Usually not minimal
- Structure not preserved

## Growth of $|S_n|$

$$|S_n| = n! = 1 \cdot 2 \cdot 3 \cdots n$$

**매우 빠른 성장**:
- $|S_5| = 120$
- $|S_10| = 3,628,800$
- $|S_20| \approx 2.4 \times 10^{18}$

**Stirling's approximation**:
$$n! \sim \sqrt{2\pi n} \left(\frac{n}{e}\right)^n$$

## 표기법

| 표기 | 의미 |
|------|------|
| $S_n$ | Symmetric group on $n$ elements |
| $A_n$ | Alternating group |
| $(a_1 \; \cdots \; a_k)$ | $k$-cycle |
| $\text{sgn}(\sigma)$ | Sign of permutation |
| $\text{Aut}(S_n)$ | Automorphism group |
| $[k_1, \ldots, k_r]$ | Cycle type (partition) |

## $S_n$ vs $A_n$

| | $S_n$ | $A_n$ |
|---|---|---|
| Order | $n!$ | $n!/2$ |
| Even/Odd | Both | Even only |
| Simple | No ($A_n \triangleleft S_n$) | Yes ($n \geq 5$) |
| Index | - | 2 |

## Common Pitfall^[흔한 실수]

### 1. $S_n$ is abelian?

✗ Only for $n \leq 2$!

$S_3$ is smallest non-abelian group

### 2. All subgroups are normal?

✗ $S_n$은 many non-normal subgroups

예: $\langle (12) \rangle$ is not normal in $S_3$

### 3. $|S_n|$ calculation

✗ $|S_n| = 2^n$?

✓ $|S_n| = n!$

### 4. Cycle type = conjugacy class?

✓ In $S_n$: YES!

✗ In subgroups: Not always

### 5. $A_n$ is always simple?

✗ $A_4$ is NOT simple

✓ $A_n$ is simple for $n \geq 5$

## 응용

**Mathematics**:
- Galois theory (solvability of polynomials)
- Representation theory
- Combinatorics (permutation statistics)
- Algebraic topology

**Computer Science**:
- Sorting algorithms
- Complexity theory (permutation group algorithms)
- Cryptography
- Graph isomorphism

**Physics**:
- Quantum mechanics (identical particles)
- Statistical mechanics (Bose-Einstein, Fermi-Dirac)
- Molecular symmetry

**Chemistry**:
- Stereochemistry
- Molecular orbitals
- NMR spectroscopy

## 역사적 배경

**18-19th Century**:
- Lagrange: 방정식 연구에서 permutations 사용
- Ruffini, Abel: 5차 방정식 불가능성
- Galois: Group theory 창시

**발전**:
- Cayley (1854): Abstract groups, Cayley's theorem
- Jordan (1870): Traité des substitutions
- 20th century: Representation theory

**현대**:
- Classification of finite simple groups
- Computational group theory

## 관련 개념

- [[Permutation Group]]: General theory
- [[Group]]: Basic group theory
- [[Subgroup]]: Subgroup structure
- [[Normal Subgroup]]: $A_n \triangleleft S_n$
- [[Galois Theory]]: Applications
- [[Dihedral Group]]: Geometric subgroups

## 추가 학습 주제

**기초**:
- Cycle notation
- Conjugacy classes
- Alternating group

**중급**:
- Sylow subgroups of $S_n$
- Transitive and primitive groups
- Wreath products

**고급**:
- Representation theory
- Young tableaux
- Outer automorphism of $S_6$
- Computational group theory

