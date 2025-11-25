# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Cyclic Group]]
- [[Abelian Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups
- Robinson, A Course in the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Finitely Generated Group^[유한 생성 군]

Group $G$가 **finitely generated**^[유한 생성]이다 $\Leftrightarrow$

$$\exists S \subseteq G \text{ finite such that } G = \langle S \rangle$$

**의미**: 유한 개의 원소들로 전체 group을 generate

### Generating Set^[생성 집합]

$$\langle S \rangle = \{\text{finite products of elements from } S \cup S^{-1}\}$$

where $S^{-1} = \{s^{-1} : s \in S\}$

**예**: $\langle a, b \rangle = \{a^{i_1}b^{j_1} \cdots a^{i_n}b^{j_n} : i_k, j_k \in \mathbb{Z}\}$

자세한 내용은 [[Generator]] 참조

## Rank^[계수]

Finitely generated group $G$의 **rank**^[계수] $r(G)$:

$$r(G) = \min\{|S| : G = \langle S \rangle\}$$

**의미**: 최소 generating set의 크기

---

# <span class="header-properties">Properties</span>

## Cyclic Groups

**정리**: Cyclic group은 rank 1

$$G \cong \mathbb{Z} \text{ or } \mathbb{Z}/n\mathbb{Z} \Rightarrow r(G) = 1$$

**증명**: $G = \langle g \rangle$ for some $g$ ✓

자세한 내용은 [[Cyclic Group]] 참조

## Quotients

**정리**: $G$ finitely generated, $N \triangleleft G$

$$\Rightarrow G/N \text{ finitely generated}$$

**증명**: $G = \langle S \rangle$ $\Rightarrow$ $G/N = \langle \{\bar{s} : s \in S\} \rangle$ ✓

## Subgroups (Not Always!)

**주의**: Finitely generated의 subgroup이 finitely generated인 것은 **아님**!

**반례**: Free group $F_2 = \langle a, b \rangle$

Subgroup $[F_2, F_2]$ (commutator subgroup)은 infinitely generated

**예외**: Abelian groups, Free groups (of finite rank)

## Direct Products

**정리**: $G, H$ finitely generated

$$\Rightarrow G \times H \text{ finitely generated}$$

**Rank**: $r(G \times H) \leq r(G) + r(H)$

자세한 내용은 [[Direct Product]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$

$$\mathbb{Z} = \langle 1 \rangle$$

**Rank**: $r(\mathbb{Z}) = 1$

**Finitely generated**: Yes ✓

## Example 2: $\mathbb{Z}^n$

$$\mathbb{Z}^n = \mathbb{Z} \times \cdots \times \mathbb{Z} \quad (n \text{ times})$$

$$= \langle (1,0,\ldots,0), (0,1,0,\ldots,0), \ldots, (0,\ldots,0,1) \rangle$$

**Rank**: $r(\mathbb{Z}^n) = n$

**Finitely generated**: Yes ✓

## Example 3: Finite Groups

**정리**: 모든 finite group은 finitely generated

**증명**: $G = \langle G \rangle$ (자기 자신으로) ✓

하지만 더 작은 generating set 존재 가능

**예**: $S_n = \langle (12), (123\cdots n) \rangle$ (2 generators)

자세한 내용은 [[Symmetric Group]] 참조

## Example 4: $\mathbb{Q}$ (Additive)

$$\mathbb{Q} = \{\frac{m}{n} : m, n \in \mathbb{Z}, n \neq 0\}$$

**NOT finitely generated**!

**증명**: 어떤 유한 집합 $S$도 $\mathbb{Q}$ 전체를 generate 못 함

유한 개의 분모들 → 최소공배수 $d$ → $1/(d+1)$ not in $\langle S \rangle$ ✗

## Example 5: $\mathbb{R}$ (Additive)

**NOT finitely generated**

**이유**: Uncountable이지만, finitely generated는 countable

## Example 6: $\text{GL}_n(\mathbb{Z})$

$$\text{GL}_n(\mathbb{Z}) = \{n \times n \text{ matrices with det } = \pm 1\}$$

**Finitely generated**: Yes (for $n = 2$)

**$n \geq 3$**: More complex

---

# <span class="header-theorem">Theorem</span>

## Fundamental Theorem of Finitely Generated Abelian Groups

**정리**: Finitely generated abelian group은

$$G \cong \mathbb{Z}^r \times \mathbb{Z}/n_1\mathbb{Z} \times \cdots \times \mathbb{Z}/n_k\mathbb{Z}$$

where $n_i \mid n_{i+1}$ (invariant factors)

**Parameters**:
- $r$ = free rank^[자유 계수]
- Torsion part^[비틀림 부분]: $\mathbb{Z}/n_i\mathbb{Z}$

자세한 내용은 [[Abelian Group]] 참조

## Nielsen-Schreier Theorem

**정리**: Subgroup of free group is free

$F$ free, $H \leq F$ $\Rightarrow$ $H$ free

**Rank**: If $[F : H] = n$ finite, $r(H) = 1 + n(r(F) - 1)$

자세한 내용은 [[Free Group]] 참조

## Hopfian Groups

Group $G$가 **Hopfian**^[호프]이다 $\Leftrightarrow$

Every surjective endomorphism is injective

**정리**: Finitely generated residually finite groups are Hopfian

**예**: Finite groups, $\mathbb{Z}^n$

## Growth of Groups

Finitely generated group의 **growth function**:

$$\gamma_G(n) = |\{g \in G : |g| \leq n\}|$$

where $|g|$ = word length with respect to fixed generating set

**Types**:
- Polynomial growth
- Exponential growth
- Intermediate growth (존재! Grigorchuk group)

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Finitely Generated = "유한 개의 building blocks"**

### 메타포: 레고 블록

**Generators**: 기본 블록들 (유한 개)

**Group**: 블록들을 조합해서 만들 수 있는 모든 구조

**Finitely generated**: 유한 종류의 블록만 필요

### 메타포: 알파벳

**Generators**: 알파벳 글자들

**Words**: 글자들의 조합

**Language**: 모든 가능한 단어들 = Group

## 왜 중요한가?

### 1. Computational

**Finitely presented**: 컴퓨터로 다룰 수 있음

**Infinite generated**: 다루기 매우 어려움

### 2. Classification

**Structure theorems**: Finitely generated abelian groups 완전 분류

### 3. Geometric Group Theory

**Cayley graphs**: Finitely generated groups의 기하학

**응용**: Topology, Dynamics

### 4. Representation

**Practical**: 유한 개의 generators로 전체 describe

## Finitely Generated vs Finite

| | **Finite** | **Finitely Generated** |
|---|---|---|
| **크기** | Finite | Possibly infinite |
| **Generators** | Finite | Finite |
| **예** | $S_3, \mathbb{Z}/n\mathbb{Z}$ | $\mathbb{Z}, \mathbb{Z}^2, S_3$ |
| **비-예** | $\mathbb{Z}, \mathbb{Q}$ | $\mathbb{Q}, \mathbb{R}$ |

**관계**: Finite $\Rightarrow$ Finitely generated (but not converse!)

## 계산 방법

### Generators 찾기

**Step 1**: Candidates 선택

**Step 2**: Products로 모든 원소 표현 가능한지 확인

**Step 3**: Minimality 확인 (rank 계산)

### Rank 계산

**Abelian case**: Structure theorem 사용

**Non-abelian**: Abelianization $G/G'$ 분석 (lower bound)

## 예외: Subgroups

**일반적으로**: $H \leq G$ finitely generated $\not\Rightarrow$ $H$ finitely generated

**예외**:
- **Abelian groups**: Subgroups finitely generated ✓
- **Free groups**: Subgroups free (Nielsen-Schreier) ✓
- **Finite index**: $[G : H] < \infty$ $\Rightarrow$ $H$ finitely generated ✓

## 응용 분야

**Geometric Group Theory**:
- Cayley graphs
- Quasi-isometry
- Hyperbolic groups

**Topology**:
- Fundamental groups
- Covering spaces

**Number Theory**:
- Units in number fields
- Class groups

**Combinatorics**:
- Word problems
- Automata

## 표기법

| 표기 | 의미 |
|------|------|
| $\langle S \rangle$ | Subgroup generated by $S$ |
| $r(G)$ | Rank of $G$ |
| $G = \langle g_1, \ldots, g_n \rangle$ | Generators |
| $\mathbb{Z}^n$ | Free abelian group of rank $n$ |

## Common Pitfall^[흔한 실수]

### 1. Subgroups

Finitely generated $\not\Rightarrow$ subgroups finitely generated

**예외**: Abelian groups

### 2. Quotients

Quotients는 항상 finitely generated ✓

### 3. $\mathbb{Q}$ not finitely generated

유리수는 infinitely generated!

### 4. Rank ≠ Minimal relations

Rank = minimal generators (not relations)

### 5. Finite vs Finitely generated

Finite groups는 finitely generated

하지만 역은 아님: $\mathbb{Z}$ infinite but finitely generated

## 관련 개념

- [[Generator]]: Basic concept
- [[Free Group]]: Freely generated
- [[Abelian Group]]: Structure theorem
- [[Group Presentation]]: Relations
- [[Cyclic Group]]: Rank 1 case

## 추가 학습 주제

**기초**:
- Definition
- Examples
- Rank

**중급**:
- Structure theorems
- Cayley graphs
- Word problem

**고급**:
- Growth of groups
- Geometric group theory
- Quasi-isometry

