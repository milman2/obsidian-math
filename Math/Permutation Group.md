# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Function]]
- [[One-to-On, Onto]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Rotman, An Introduction to the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Permutation^[순열]

Set $X$의 **permutation^[순열]**: $X$에서 $X$로의 bijection^[전단사 함수]

$$\sigma: X \to X \text{ bijective}$$

**의미**: $X$의 원소들의 재배열 (rearrangement)

## Permutation Group^[순열군]

Set $X$의 모든 permutations의 집합:

$$\text{Sym}(X) = \{\sigma : X \to X \text{ bijective}\}$$

**연산**: Function composition^[함수 합성] $\sigma \circ \tau$

**Group structure**:
- **Identity**: $\text{id}_X$
- **Inverse**: $\sigma^{-1}$ (bijection의 역함수)
- **Closure**: Composition of bijections is bijection
- **Associativity**: Function composition

## Symmetric Group^[대칭군]

Finite set $\{1, 2, \ldots, n\}$의 permutation group:

$$S_n = \text{Sym}(\{1, 2, \ldots, n\})$$

**Order**: $|S_n| = n!$

**Examples**:
- $S_1 = \{e\}$ (trivial)
- $S_2 = \{e, (12)\}$ (order 2)
- $S_3$ (order 6)
- $S_4$ (order 24)

자세한 내용은 [[Symmetric Group]] 참조

## Cycle Notation^[순환 표기]

### Cycle^[순환]

Permutation $\sigma$가 **$k$-cycle^[k-순환]** (or **cycle of length $k$^[길이 k의 순환]**)이다 $\Leftrightarrow$

$$\exists a_1, \ldots, a_k \text{ distinct}, \quad \sigma(a_i) = a_{i+1}, \sigma(a_k) = a_1$$

나머지 원소는 고정

**표기**: $(a_1 \; a_2 \; \cdots \; a_k)$

**읽기**: "$a_1$을 $a_2$로, $a_2$를 $a_3$로, ..., $a_k$를 $a_1$로"

### Examples

**(1 2 3)**: 
- $1 \to 2$
- $2 \to 3$
- $3 \to 1$
- 다른 원소 고정

**(1 2)**: Transposition^[호환] (2-cycle)
- $1 \leftrightarrow 2$
- 다른 원소 고정

### Disjoint Cycles^[서로소 순환]

Two cycles $(a_1 \; \cdots \; a_k)$와 $(b_1 \; \cdots \; b_m)$이 **disjoint^[서로소]**이다 $\Leftrightarrow$

$$\{a_1, \ldots, a_k\} \cap \{b_1, \ldots, b_m\} = \emptyset$$

**Property**: Disjoint cycles commute^[교환 가능]!

$$(a_1 \; \cdots \; a_k)(b_1 \; \cdots \; b_m) = (b_1 \; \cdots \; b_m)(a_1 \; \cdots \; a_k)$$

## Transposition^[호환]

**Transposition^[호환]**: 2-cycle $(i \; j)$

두 원소를 교환하는 permutation

**Examples**:
- $(1 \; 2)$: $1 \leftrightarrow 2$
- $(3 \; 5)$: $3 \leftrightarrow 5$

**중요성**: 모든 permutation은 transpositions의 곱

## Even and Odd Permutations^[짝순열과 홀순열]

### Sign of Permutation^[순열의 부호]

$$\text{sgn}(\sigma) = \begin{cases} +1 & \text{if } \sigma \text{ is even} \\ -1 & \text{if } \sigma \text{ is odd} \end{cases}$$

### Even Permutation^[짝순열]

Permutation $\sigma$가 **even^[짝]**이다 $\Leftrightarrow$ 짝수 개의 transpositions의 곱

$$\text{sgn}(\sigma) = +1$$

### Odd Permutation^[홀순열]

Permutation $\sigma$가 **odd^[홀]**이다 $\Leftrightarrow$ 홀수 개의 transpositions의 곱

$$\text{sgn}(\sigma) = -1$$

### Sign Homomorphism

$$\text{sgn}: S_n \to \{\pm 1\}, \quad \text{sgn}(\sigma\tau) = \text{sgn}(\sigma)\text{sgn}(\tau)$$

Group homomorphism!

## Alternating Group^[교대군]

$$A_n = \{\sigma \in S_n : \sigma \text{ is even}\} = \ker(\text{sgn})$$

모든 even permutations의 집합

**Properties**:
- $A_n \triangleleft S_n$ (normal subgroup)
- $|A_n| = n!/2$
- $[S_n : A_n] = 2$

**Simple**: $A_n$ is simple for $n \geq 5$

---

# <span class="header-examples">Examples</span>

## Example 1: $S_3$ (Symmetric Group on 3 Elements)

**원소** (6개):
- Identity: $e$
- 3 transpositions: $(12)$, $(13)$, $(23)$
- 2 three-cycles: $(123)$, $(132)$

**Structure**:
$$S_3 = \{e, (12), (13), (23), (123), (132)\}$$

**Order**: $|S_3| = 3! = 6$

**Non-abelian**: $(12)(13) = (132) \neq (123) = (13)(12)$

## Example 2: Cycle Decomposition

Permutation in $S_7$:

$$\sigma = \begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 & 7 \\ 3 & 4 & 1 & 2 & 7 & 6 & 5 \end{pmatrix}$$

**Cycle notation**:
$$\sigma = (1 \; 3)(2 \; 4)(5 \; 7)(6) = (1 \; 3)(2 \; 4)(5 \; 7)$$

**Disjoint cycles**: $(1 \; 3)$, $(2 \; 4)$, $(5 \; 7)$ 모두 disjoint

## Example 3: Composition of Cycles

**(1 2 3)(2 3 4)** (NOT disjoint):

계산 (오른쪽부터):
- $1 \xrightarrow{(234)} 1 \xrightarrow{(123)} 2$
- $2 \xrightarrow{(234)} 3 \xrightarrow{(123)} 1$
- $3 \xrightarrow{(234)} 4 \xrightarrow{(123)} 4$
- $4 \xrightarrow{(234)} 2 \xrightarrow{(123)} 3$

**Result**: $(1 \; 2 \; 3)(2 \; 3 \; 4) = (1 \; 2)(3 \; 4)$

## Example 4: Transposition Decomposition

**(1 2 3 4)**:

$$( 1 \; 2 \; 3 \; 4) = (1 \; 4)(1 \; 3)(1 \; 2)$$

**Verification**:
- $1 \xrightarrow{(12)} 2 \xrightarrow{(13)} 2 \xrightarrow{(14)} 2$
- $2 \xrightarrow{(12)} 1 \xrightarrow{(13)} 1 \xrightarrow{(14)} 1$... (wait, this is wrong)

Actually:
$$(1 \; 2 \; 3 \; 4) = (1 \; 2)(2 \; 3)(3 \; 4)$$

더 정확하게 (일반 공식):
$$(a_1 \; a_2 \; \cdots \; a_k) = (a_1 \; a_k)(a_1 \; a_{k-1}) \cdots (a_1 \; a_2)$$

## Example 5: Even vs Odd

**Even permutations in $S_3$**:
- $e$ (0 transpositions)
- $(123) = (12)(23)$ (2 transpositions)
- $(132) = (13)(23)$ (2 transpositions)

**Odd permutations in $S_3$**:
- $(12)$ (1 transposition)
- $(13)$ (1 transposition)
- $(23)$ (1 transposition)

$$A_3 = \{e, (123), (132)\}, \quad |A_3| = 3$$

## Example 6: Conjugation

$$\sigma (1 \; 2 \; 3) \sigma^{-1} = (\sigma(1) \; \sigma(2) \; \sigma(3))$$

**예**: $\sigma = (1 \; 4)$
$$\sigma (1 \; 2 \; 3) \sigma^{-1} = ((1 \; 4)(1) \; (1 \; 4)(2) \; (1 \; 4)(3)) = (4 \; 2 \; 3)$$

**일반**: Conjugation은 cycle structure 보존

## Example 7: Order of Permutations

**(1 2 3)(4 5)**: Disjoint cycles

$$\text{ord}((1 \; 2 \; 3)(4 \; 5)) = \text{lcm}(3, 2) = 6$$

**일반 규칙**: Disjoint cycles의 곱의 order = lcm of cycle lengths

## Example 8: Cayley's Theorem

Every group $G$는 permutation group의 subgroup과 isomorphic

**Construction**: Regular representation
$$\phi: G \to \text{Sym}(G), \quad \phi(g)(x) = gx$$

**예**: $C_3 \hookrightarrow S_3$

## Example 9: Rubik's Cube Group

Rubik's cube의 symmetries: Permutation group

**Order**: ~$4.3 \times 10^{19}$

**Structure**: Complicated subgroup of $S_{48}$

## Example 10: Musical Chairs

$n$명, $n$ chairs: $S_n$ permutations

**Interpretation**: Person $i$ sits in chair $\sigma(i)$

---

# <span class="header-properties">Properties</span>

## Cycle Decomposition Theorem^[순환 분해 정리]

**정리**: 모든 permutation은 disjoint cycles의 곱으로 **유일하게** 표현

$$\sigma = c_1 c_2 \cdots c_k$$

where $c_i$는 disjoint cycles

**유일성**: Cycle 순서와 1-cycles (고정점) 제외하고 유일

**예**:
$$\begin{pmatrix} 1 & 2 & 3 & 4 & 5 \\ 2 & 3 & 1 & 5 & 4 \end{pmatrix} = (1 \; 2 \; 3)(4 \; 5)$$

## Transposition Decomposition^[호환 분해]

**정리**: 모든 permutation은 transpositions의 곱

$$\sigma = t_1 t_2 \cdots t_m$$

**Non-unique**: 표현이 유일하지 않음!

**Parity**: $m$의 parity (짝/홀)는 유일 (well-defined)

### Standard Decomposition

$k$-cycle:
$$(a_1 \; a_2 \; \cdots \; a_k) = (a_1 \; a_k)(a_1 \; a_{k-1}) \cdots (a_1 \; a_2)$$

**Transpositions 개수**: $k - 1$

## Order of Permutations^[순열의 위수]

Permutation $\sigma = c_1 \cdots c_k$ (disjoint cycles):

$$\text{ord}(\sigma) = \text{lcm}(\text{length}(c_1), \ldots, \text{length}(c_k))$$

**예**:
- $\text{ord}((1 \; 2 \; 3 \; 4 \; 5)) = 5$
- $\text{ord}((1 \; 2)(3 \; 4 \; 5)) = \text{lcm}(2, 3) = 6$
- $\text{ord}((1 \; 2)(3 \; 4)(5 \; 6 \; 7)) = \text{lcm}(2, 2, 3) = 6$

## Conjugacy Classes^[켤레류]

**정리**: $S_n$에서 conjugacy class는 **cycle type**^[순환 유형]으로 결정

**Cycle type**: Cycle lengths의 partition of $n$

**예**: $S_5$
- $(1 \; 2 \; 3)(4 \; 5)$의 cycle type: $[3, 2]$
- $(1 \; 2)(3 \; 4 \; 5)$의 cycle type: $[3, 2]$ (같음!)
- Same cycle type $\Rightarrow$ conjugate

### Size of Conjugacy Class

Cycle type $[k_1, k_2, \ldots]$의 conjugacy class 크기:

$$\frac{n!}{\prod_i k_i \cdot \prod_j m_j!}$$

where $m_j$ = multiplicity of length $j$

## Sign Properties^[부호 성질]

### 1. Multiplicativity

$$\text{sgn}(\sigma\tau) = \text{sgn}(\sigma) \cdot \text{sgn}(\tau)$$

Group homomorphism

### 2. Inverse

$$\text{sgn}(\sigma^{-1}) = \text{sgn}(\sigma)$$

### 3. Cycle Sign

$k$-cycle의 sign:
$$\text{sgn}(k\text{-cycle}) = (-1)^{k-1}$$

**예**:
- Transposition: $\text{sgn}((12)) = -1$ (odd)
- 3-cycle: $\text{sgn}((123)) = (-1)^2 = +1$ (even)

## Generators of $S_n$^[$S_n$의 생성원]

### Transpositions

$$S_n = \langle (12), (13), \ldots, (1n) \rangle$$

모든 transpositions $(1i)$로 생성

### Adjacent Transpositions

$$S_n = \langle (12), (23), \ldots, (n-1 \; n) \rangle$$

인접한 transpositions만으로 생성

### Two Elements

$$S_n = \langle (12), (123 \cdots n) \rangle$$

Transposition 하나 + $n$-cycle 하나로 생성

---

# <span class="header-theorem">Theorem</span>

## Cayley's Theorem^[케일리 정리]

**정리**: 모든 group $G$는 어떤 permutation group의 subgroup과 isomorphic

$$G \cong \text{subgroup of } \text{Sym}(G)$$

**증명**: Regular representation
$$\phi: G \to \text{Sym}(G), \quad \phi(g)(x) = gx$$

**의미**: 모든 군을 permutation group으로 볼 수 있음!

자세한 내용은 [[Isomorphism]] 참조

## Simplicity of $A_n$^[$A_n$의 단순성]

**정리**: $A_n$ is simple for $n \geq 5$

**의미**: $A_5, A_6, \ldots$는 nontrivial proper normal subgroups가 없음

**중요성**:
- 5차 이상 방정식의 근의 공식 불가능
- Galois theory의 핵심

**특수한 경우**:
- $A_1, A_2$: Trivial
- $A_3 \cong C_3$: Simple (cyclic of prime order)
- $A_4$: NOT simple (has $V_4$ as normal subgroup)

## Lagrange's Theorem Application

$H \leq S_n$ $\Rightarrow$ $|H| \mid n!$

**예**: $S_4$ (order 24)의 가능한 subgroup orders:
$1, 2, 3, 4, 6, 8, 12, 24$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Permutation**: "재배열"

**메타포**:
- **Card shuffling**: 카드 섞기
- **Rearranging books**: 책 재배열
- **Seating arrangement**: 좌석 배치
- **Rubik's cube**: 큐브 돌리기

**핵심**: 물체의 위치 변경

## Cycle Notation의 장점

### Two-line Notation

$$\begin{pmatrix} 1 & 2 & 3 & 4 & 5 \\ 3 & 1 & 4 & 5 & 2 \end{pmatrix}$$

**장점**: 명시적
**단점**: 길고 계산 어려움

### Cycle Notation

$$(1 \; 3 \; 4 \; 5 \; 2)$$

**장점**: 
- Compact
- Composition 쉬움
- Structure 명확

## Composition Convention^[합성 관례]

**주의**: 책마다 다를 수 있음!

### Right-to-left (대부분)

$$(\sigma \circ \tau)(x) = \sigma(\tau(x))$$

오른쪽부터 적용

### Left-to-right (일부)

$$(\sigma \tau)(x) = \tau(\sigma(x))$$

왼쪽부터 적용

**본 노트**: Right-to-left 사용

## 표기법

| 표기 | 의미 |
|------|------|
| $S_n$ | Symmetric group |
| $(a_1 \; a_2 \; \cdots \; a_k)$ | $k$-cycle |
| $(i \; j)$ | Transposition |
| $A_n$ | Alternating group |
| $\text{sgn}(\sigma)$ | Sign of permutation |
| $\text{Sym}(X)$ | Permutations of $X$ |

## Common Pitfall^[흔한 실수]

### 1. Composition order

✗ $(12)(23) = (123)$?

✓ Depends on convention! (Right-to-left: Yes)

**Check**: $1 \xrightarrow{(23)} 1 \xrightarrow{(12)} 2$ 
### 2. Disjoint cycles commute

 $(12)(34) = (34)(12)$ 
✗ $(12)(23) \neq (23)(12)$ (NOT disjoint)

### 3. Cycle length vs order

✗ Order of $(12)(34)$ = ?

✗ Not 2! It's $\text{lcm}(2,2) = 2$ (happens to be same)

 Order of $(123)(45)$ = $\text{lcm}(3,2) = 6$

### 4. Sign of cycle

✗ $k$-cycle has sign $(-1)^k$?

✓ Sign is $(-1)^{k-1}$ (not $k$)

### 5. $S_n$ is abelian?

✗ $S_n$ is abelian for $n \geq 3$?

✓ **No!** Only $S_1, S_2$ are abelian

## 응용

**Mathematics**:
- Group theory
- Galois theory
- Combinatorics
- Representation theory

**Computer Science**:
- Sorting algorithms
- Cryptography
- Graph isomorphism
- Complexity theory

**Physics**:
- Quantum mechanics (identical particles)
- Statistical mechanics
- Crystal structures

**Chemistry**:
- Molecular symmetry
- Stereochemistry

**Games & Puzzles**:
- Rubik's cube
- 15-puzzle
- Card games

## 역사적 배경

**19th Century**:
- Lagrange, Cauchy: 순열 연구
- Galois: 방정식과 permutations

**발전**:
- Cayley (1854): Cayley's theorem
- Jordan (1870): Group theory systematization
- 20th century: Abstract group theory

## 관련 개념

- [[Group]]: Basic group theory
- [[Symmetric Group]]: $S_n$ in detail
- [[Generator]]: Generating sets
- [[Normal Subgroup]]: $A_n \triangleleft S_n$
- [[Galois Theory]]: Applications

## 추가 학습 주제

**기초**:
- Cycle notation
- Transpositions
- Sign of permutations

**중급**:
- Conjugacy classes
- Sylow subgroups of $S_n$
- Wreath products

**고급**:
- Representation theory of $S_n$
- Young tableaux
- Symmetric functions

