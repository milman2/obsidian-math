# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Nilpotent Group]]
- [[Group Action]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups
- Robinson, A Course in the Theory of Groups

---

# <span class="header-definition">Definition</span>

## $p$-group^[$p$-군]

Group $G$가 **$p$-group**^[$p$-군]이다 $\Leftrightarrow$

$$|G| = p^n \text{ for some prime } p \text{ and } n \geq 0$$

**의미**: Order가 prime $p$의 거듭제곱

### Finite vs Infinite

**Finite $p$-group**: $|G| = p^n < \infty$

**Infinite $p$-group**: 모든 원소의 order가 $p^k$ for some $k$

**관례**: "p-group"은 보통 finite를 의미

## $p$-element^[$p$-원소]

원소 $g \in G$가 **$p$-element**^[$p$-원소]이다 $\Leftrightarrow$

$$|g| = p^k \text{ for some } k \geq 0$$

**의미**: Order가 $p$의 거듭제곱

## $p$-subgroup^[$p$-부분군]

Subgroup $H \leq G$가 **$p$-subgroup**^[$p$-부분군]이다 $\Leftrightarrow$

$H$는 $p$-group

자세한 내용은 [[Sylow Theorem]] 참조

---

# <span class="header-properties">Properties</span>

## Fundamental Property: Non-trivial Center

**정리**: Nontrivial $p$-group은 nontrivial center를 가짐

$$G \text{ } p\text{-group}, |G| > 1 \Rightarrow Z(G) \neq \{e\}$$

### 증명 (Class Equation)

$$|G| = |Z(G)| + \sum_{i} [G : C_G(x_i)]$$

where sum is over non-central conjugacy classes

$|G| = p^n$이므로 $p \mid |G|$

각 $[G : C_G(x_i)]$는 $|G|$의 proper divisor이므로 $p \mid [G : C_G(x_i)]$

따라서:

$$p \mid |G| = |Z(G)| + \sum_{i} [G : C_G(x_i)]$$

$$p \mid |Z(G)|$$

$\Rightarrow |Z(G)| \geq p > 1$ ✓

자세한 내용은 [[Group Action]] 참조

## Nilpotency

**정리**: 모든 finite $p$-group은 nilpotent^[멱영]

**증명**: Induction on $|G|$

- Base: $|G| = p$ $\Rightarrow$ abelian $\Rightarrow$ nilpotent
- Step: $Z(G) \neq \{e\}$ $\Rightarrow$ $G/Z(G)$ smaller $p$-group $\Rightarrow$ nilpotent by induction
- Upper central series reaches $G$ ✓

자세한 내용은 [[Nilpotent Group]] 참조

## Maximal Subgroups

**정리**: $p$-group의 maximal subgroup은 index $p$를 가지며 normal

$$M < G \text{ maximal} \Rightarrow [G : M] = p \text{ and } M \triangleleft G$$

**증명**:
- $Z(G) \neq \{e\}$ $\Rightarrow$ $Z(G) \cap M$ nontrivial or $G = MZ(G)$
- If $G = MZ(G)$: $[G : M] = [MZ(G) : M] = [Z(G) : M \cap Z(G)]$ divides $|Z(G)|$
- Since $M$ maximal, $[G : M] = p$ ✓
- Index $p$ $\Rightarrow$ normal ✓

자세한 내용은 [[Normal Subgroup]] 참조

## Normalizer Condition

**정리**: $H < G$ proper subgroup $\Rightarrow H < N_G(H)$

**의미**: Proper subgroup은 자신의 normalizer에 strictly contained

**증명**: $Z(G) \not\subseteq H$ (since $|Z(G)| \geq p$, $H$ proper)

$\Rightarrow \exists z \in Z(G), z \notin H$

$z$ centralizes $H$ $\Rightarrow z \in N_G(H) \setminus H$ ✓

## Cauchy's Theorem (Automatic)

**정리**: $p \mid |G|$ $\Rightarrow$ $\exists g \in G$ with $|g| = p$

**$p$-group의 경우**: 자동! (모든 nontrivial element가 $p$-power order)

## Subgroup Lattice

**정리**: $p$-group의 subgroup lattice는 매우 "풍부"

모든 proper subgroup은 maximal subgroup에 포함

---

# <span class="header-examples">Examples</span>

## Example 1: Cyclic $p$-groups

$$\mathbb{Z}/p^n\mathbb{Z}$$

**Order**: $p^n$

**Structure**: Cyclic, 따라서 abelian

**Subgroups**: $\mathbb{Z}/p^k\mathbb{Z}$ for $0 \leq k \leq n$ (chain)

**Center**: Entire group (abelian)

자세한 내용은 [[Cyclic Group]] 참조

## Example 2: Klein Four-Group

$$V_4 = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$$

**Order**: $2^2 = 4$ (2-group)

**Elements**: All non-identity elements have order 2

**Center**: $Z(V_4) = V_4$ (abelian)

**Not cyclic**: No element of order 4

자세한 내용은 [[Abelian Group]] 참조

## Example 3: Dihedral Group $D_4$

$$D_4 = \langle r, s : r^4 = s^2 = e, srs = r^{-1} \rangle$$

**Order**: $2^3 = 8$ (2-group)

**Center**: $Z(D_4) = \{e, r^2\}$ (order 2)

**Non-abelian**: $rs \neq sr$

**Maximal subgroups**: Order 4, index 2

자세한 내용은 [[Dihedral Group]] 참조

## Example 4: Quaternion Group $Q_8$

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

**Order**: $2^3 = 8$ (2-group)

**Relations**: $i^2 = j^2 = k^2 = ijk = -1$

**Center**: $Z(Q_8) = \{1, -1\}$ (order 2)

**Unique**: 유일한 non-abelian group of order $p^3$ (up to isomorphism, for $p = 2$)

## Example 5: Heisenberg Group (mod $p$)

$$H_p = \left\{ \begin{pmatrix} 1 & a & c \\ 0 & 1 & b \\ 0 & 0 & 1 \end{pmatrix} : a, b, c \in \mathbb{Z}/p\mathbb{Z} \right\}$$

**Order**: $p^3$ ($p$-group)

**Center**: 
$$Z(H_p) = \left\{ \begin{pmatrix} 1 & 0 & c \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} : c \in \mathbb{Z}/p\mathbb{Z} \right\} \cong \mathbb{Z}/p\mathbb{Z}$$

**Nilpotent**: Class 2

## Example 6: Abelian $p$-groups

**정리**: Finite abelian $p$-group은 cyclic groups의 direct product

$$G \cong \mathbb{Z}/p^{a_1}\mathbb{Z} \times \cdots \times \mathbb{Z}/p^{a_k}\mathbb{Z}$$

**예**: Order $p^2$인 abelian groups (2개만):
- $\mathbb{Z}/p^2\mathbb{Z}$ (cyclic)
- $\mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z}$

자세한 내용은 [[Abelian Group]] 참조

---

# <span class="header-theorem">Theorem</span>

## Classification of Groups of Order $p^2$

**정리**: Order $p^2$인 group은 정확히 2개 (up to isomorphism):

1. $\mathbb{Z}/p^2\mathbb{Z}$ (cyclic)
2. $\mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z}$

**증명**: 
- Non-trivial center $\Rightarrow$ abelian (order $p^2$)
- Fundamental theorem of finite abelian groups ✓

## Classification of Groups of Order $p^3$

**정리**: Order $p^3$인 group은 5개 types (for $p$ odd):

**Abelian** (3):
1. $\mathbb{Z}/p^3\mathbb{Z}$
2. $\mathbb{Z}/p^2\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z}$
3. $\mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z}$

**Non-abelian** (2):
4. Heisenberg group $H_p$
5. $\mathbb{Z}/p^2\mathbb{Z} \rtimes \mathbb{Z}/p\mathbb{Z}$ (semidirect product)

**For $p = 2$**: 추가로 $Q_8$, $D_4$ 포함 (총 5개)

## Burnside's Basis Theorem

**정리**: Finite $p$-group $G$의 minimal generating set의 크기는 $d(G/\Phi(G))$

where $\Phi(G)$ = Frattini subgroup

**응용**: $p$-group의 generators 개수 계산

## $p$-groups are Solvable

**정리**: 모든 finite $p$-group은 solvable^[가해]

**증명**: Nilpotent $\Rightarrow$ Solvable ✓

자세한 내용은 [[Solvable Group]] 참조

## Sylow's First Theorem Application

**정리**: $|G| = p^k m$ where $\gcd(p, m) = 1$

$\Rightarrow$ $G$는 order $p^i$ subgroups를 가짐 for all $0 \leq i \leq k$

**의미**: $p$-subgroups의 완전한 chain 존재

자세한 내용은 [[Sylow Theorem]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**$p$-group = "가장 단순한 finite groups"**

### 메타포: 순수 물질

**$p$-group**: "순수한 $p$-성분"만 포함

**General group**: 여러 prime components 혼합

**분해**: Sylow subgroups = $p$-components

### 메타포: 계층 구조

**Center 기반**: 항상 non-trivial center

**Layer by layer**: $Z(G) \subseteq Z_2(G) \subseteq \cdots$ (upper central series)

**Nilpotent**: 유한 단계에 전체 도달

## 왜 중요한가?

### 1. Building Blocks

**Sylow subgroups**: 모든 finite group의 $p$-components

**Structure**: $p$-groups 이해 = finite groups 이해의 기초

### 2. Simplest Non-abelian Groups

**Small orders**: Most groups are $p$-groups

**Classification**: Order $p^n$에 대한 체계적 분류 가능

### 3. Nilpotent Groups

**모든 $p$-group은 nilpotent**

Nilpotency의 가장 자연스러운 예시

### 4. Representation Theory

**Modular representations**: $p$-groups의 특수한 성질

## $p$-groups의 특징

| 성질 | $p$-group | 일반 group |
|------|-----------|------------|
| **Center** | $\neq \{e\}$ (항상) | 임의 |
| **Nilpotent** | ✓ 항상 | ✗ 일반적으로 |
| **Solvable** | ✓ 항상 | ✗ 일반적으로 |
| **Maximal subgroups** | Index $p$, normal | 임의 |
| **Classification** | 가능 (small orders) | 매우 어려움 |

## Order별 분류

| Order | Abelian | Non-abelian | Total |
|-------|---------|-------------|-------|
| $p$ | 1 | 0 | 1 |
| $p^2$ | 2 | 0 | 2 |
| $p^3$ | 3 | 2 ($p$ odd) | 5 |
| $p^4$ | 5 | 10+ | 15+ |
| $p^5$ | 7 | 60+ | 67+ |

**경향**: Order 증가 → 급격히 증가

## 계산 예시

### Order 8 Groups (2-groups)

**5개의 groups** (up to isomorphism):

**Abelian**:
1. $\mathbb{Z}/8\mathbb{Z}$
2. $\mathbb{Z}/4\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$
3. $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$

**Non-abelian**:
4. $D_4$ (dihedral)
5. $Q_8$ (quaternion)

### Center 확인

- $Z(\mathbb{Z}/8\mathbb{Z}) = \mathbb{Z}/8\mathbb{Z}$ (전체)
- $Z(D_4) = \{e, r^2\}$ (order 2)
- $Z(Q_8) = \{1, -1\}$ (order 2)

모두 $|Z(G)| \geq 2$ ✓

## 응용 분야

**Group Theory**:
- Sylow theory
- Nilpotent groups
- Solvable groups

**Number Theory**:
- Class groups
- Galois groups
- $p$-adic analysis

**Representation Theory**:
- Modular representations
- Brauer theory

**Topology**:
- Fundamental groups
- Homology groups

**Algebraic Geometry**:
- Étale cohomology
- $p$-divisible groups

## 증명 기법

### Class Equation

**핵심 도구**: $|G| = |Z(G)| + \sum [G : C_G(x_i)]$

$p$-divisibility로 center 분석

### Induction

**Order로 귀납**: Smaller $p$-groups에서 성질 유도

### Group Actions

**Conjugation action**: Orbit-stabilizer theorem

자세한 내용은 [[Group Action]] 참조

## 역사적 배경

**Ludwig Sylow** (1872):
- Sylow theorems
- $p$-subgroups의 중요성

**Philip Hall** (1930s):
- $p$-groups 체계적 연구
- Nilpotent groups

**현대**:
- Classification programs
- Computational group theory

## 표기법

| 표기 | 의미 |
|------|------|
| $p$ | Prime number |
| $p^n$ | Power of prime |
| $Z(G)$ | Center |
| $\Phi(G)$ | Frattini subgroup |
| $d(G)$ | Minimal generators |

## Common Pitfall^[흔한 실수]

### 1. $p$-group ≠ Order $p$

Order $p$ = cyclic

Order $p^n$ ($n > 1$) = many possibilities

### 2. Abelian ≠ Cyclic

Order $p^2$: 둘 다 abelian, 하나만 cyclic

### 3. Center size

$|Z(G)| \geq p$ (not just $> 1$)

더 강한 조건!

### 4. Maximal subgroups

Index $p$ (not arbitrary)

항상 normal!

### 5. Nilpotency class

$p$-group의 nilpotency class는 bounded (by order)

하지만 order 증가 시 class도 증가 가능

## 연구 주제

**Classification**:
- Order $p^n$에 대한 완전 분류
- $n$이 커질수록 exponentially 증가

**Invariants**:
- Nilpotency class
- Derived length
- Frattini subgroup

**Automorphism groups**:
- $\text{Aut}(G)$ for $p$-groups
- 복잡한 구조

## 계산 도구

**Software**:
- GAP (Groups, Algorithms, Programming)
- Magma
- Small groups database

**Algorithms**:
- $p$-group generation
- Isomorphism testing
- Automorphism groups

## 관련 개념

- [[Nilpotent Group]]: $p$-groups는 nilpotent
- [[Sylow Theorem]]: $p$-subgroups
- [[Solvable Group]]: $p$-groups는 solvable
- [[Group Action]]: Class equation 증명
- [[Abelian Group]]: Abelian $p$-groups 분류

## 추가 학습 주제

**기초**:
- Center property
- Nilpotency
- Small order classification

**중급**:
- Frattini subgroup
- Burnside's basis theorem
- Automorphism groups

**고급**:
- $p$-group generation
- Coclass theory
- Descendant trees

