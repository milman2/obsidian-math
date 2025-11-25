# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Quotient Group]]
- [[Homomorphism]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Rotman, An Introduction to the Theory of Groups
- Gorenstein, The Classification of Finite Simple Groups

---

# <span class="header-definition">Definition</span>

## Simple Group^[단순군]

Group $G$가 **simple**^[단순]이다 $\Leftrightarrow$

$$G \neq \{e\} \text{ and } G \text{ has no proper nontrivial normal subgroups}$$

**즉**: $N \triangleleft G \Rightarrow N = \{e\}$ 또는 $N = G$

### 동등한 정의

**Alternative 1**: $G \neq \{e\}$이고 $G$가 어떤 nontrivial group의 nontrivial quotient이 아님

**Alternative 2**: $G \neq \{e\}$이고 모든 surjective homomorphism $\phi: G \to H$가 isomorphism이거나 $H = \{e\}$

**Alternative 3**: $G$의 composition series가 $\{e\} \triangleleft G$ (길이 1)

### 의미

**Simple group = "원자적" group**

- 더 이상 quotient로 분해 불가능
- Group theory의 "building blocks"
- 모든 finite group은 simple groups로부터 구성됨 (Jordan-Hölder)

### Abelian Simple Groups

**정리**: Abelian group이 simple $\Leftrightarrow$ Cyclic of prime order

$$G \text{ abelian and simple} \Leftrightarrow G \cong \mathbb{Z}/p\mathbb{Z} \text{ for some prime } p$$

**증명**:
- ($\Leftarrow$): $|\mathbb{Z}/p\mathbb{Z}| = p$ prime $\Rightarrow$ only subgroups are $\{[0]\}, G$ (Lagrange) ✓
- ($\Rightarrow$): Abelian이므로 모든 subgroup이 normal. Simple이므로 nontrivial proper subgroup 없음 $\Rightarrow$ prime order cyclic ✓

**결론**: Nontrivial simple groups는 대부분 non-abelian!

---

# <span class="header-examples">Examples</span>

## Example 1: Cyclic Groups of Prime Order

$$\mathbb{Z}/p\mathbb{Z} \quad (p \text{ prime})$$

**유일한 abelian simple groups**

**Subgroups**: $\{[0]\}, \mathbb{Z}/p\mathbb{Z}$ only

**예**:
- $\mathbb{Z}/2\mathbb{Z}$
- $\mathbb{Z}/3\mathbb{Z}$
- $\mathbb{Z}/5\mathbb{Z}$
- etc.

자세한 내용은 [[Cyclic Group]] 참조

## Example 2: Alternating Group $A_n$ ($n \geq 5$)

$$A_n = \{\sigma \in S_n : \sigma \text{ is even permutation}\}$$

**정리**: $A_n$ is simple for $n \geq 5$

**Non-simple cases**:
- $A_3 \cong \mathbb{Z}/3\mathbb{Z}$ (simple, abelian)
- $A_4$ (not simple): Has normal subgroup $V_4 = \{e, (12)(34), (13)(24), (14)(23)\}$

**중요성**: 가장 잘 알려진 infinite family of non-abelian simple groups

자세한 내용은 [[Symmetric Group]] 참조

## Example 3: Projective Special Linear Group $\text{PSL}_n(\mathbb{F})$

$$\text{PSL}_n(\mathbb{F}) = \text{SL}_n(\mathbb{F})/Z(\text{SL}_n(\mathbb{F}))$$

where:
- $\text{SL}_n(\mathbb{F}) = \{A \in \text{GL}_n(\mathbb{F}) : \det(A) = 1\}$
- $Z(\text{SL}_n(\mathbb{F}))$ = center^[중심] (scalar matrices with determinant 1)

**정리**: $\text{PSL}_n(\mathbb{F})$ is simple for:
- $n \geq 2$, except $\text{PSL}_2(\mathbb{F}_2) \cong S_3$ and $\text{PSL}_2(\mathbb{F}_3) \cong A_4$

**특별한 경우**:
- $\text{PSL}_2(\mathbb{F}_5) \cong A_5$ (order 60)
- $\text{PSL}_2(\mathbb{F}_7)$ (order 168)

## Example 4: Non-examples

### $\mathbb{Z}/4\mathbb{Z}$

**Not simple**: Has proper nontrivial subgroup $\{[0], [2]\} \cong \mathbb{Z}/2\mathbb{Z}$

$|\mathbb{Z}/4\mathbb{Z}| = 4$ not prime

### $S_n$ for $n \geq 3$

**Not simple**: $A_n \triangleleft S_n$ (index 2)

### $\mathbb{Z}$

**Not simple**: $2\mathbb{Z} \triangleleft \mathbb{Z}$ (infinite cyclic)

### Klein Four-Group $V_4$

$$V_4 = \{e, a, b, c\} \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$$

**Not simple**: Has proper subgroups $\{e, a\}$, $\{e, b\}$, $\{e, c\}$ (all normal, abelian group)

## Example 5: Sporadic Groups

**26 sporadic simple groups**^[26개의 산발적 단순군]:

가장 작은 것:
- **Mathieu groups**: $M_{11}, M_{12}, M_{22}, M_{23}, M_{24}$
- $M_{11}$: order $7920 = 2^4 \cdot 3^2 \cdot 5 \cdot 11$

가장 큰 것:
- **Monster group** $\mathbb{M}$: order approximately $8 \times 10^{53}$

$$|\mathbb{M}| = 2^{46} \cdot 3^{20} \cdot 5^9 \cdot 7^6 \cdot 11^2 \cdot 13^3 \cdot 17 \cdot 19 \cdot 23 \cdot 29 \cdot 31 \cdot 41 \cdot 47 \cdot 59 \cdot 71$$

---

# <span class="header-properties">Properties</span>

## Quotient by Simple Group

$G$ simple이고 $\phi: G \to H$ homomorphism이면:

### 1. $\phi$ is injective or trivial

**증명**: $\ker(\phi) \triangleleft G$이고 $G$ simple

$\Rightarrow$ $\ker(\phi) = \{e\}$ (injective) or $\ker(\phi) = G$ (trivial) ✓

### 2. Image is isomorphic to $G$ or trivial

$\text{im}(\phi) \cong G/\ker(\phi)$

$\ker(\phi) = \{e\} \Rightarrow \text{im}(\phi) \cong G$

$\ker(\phi) = G \Rightarrow \text{im}(\phi) = \{e\}$

## Normal Subgroups and Simplicity

**정리**: $H \triangleleft G$이고 $G$ simple $\Rightarrow$ $H = \{e\}$ or $H = G$

**응용**: Simple group은 nontrivial quotient group을 가질 수 없음

## Composition Series^[합성 열]

$$\{e\} = G_0 \triangleleft G_1 \triangleleft \cdots \triangleleft G_n = G$$

where each $G_{i+1}/G_i$ is simple

**Jordan-Hölder Theorem**: Composition factors $G_{i+1}/G_i$는 순서를 제외하고 유일

**의미**: 모든 finite group은 simple groups로 유일하게 분해됨

**Simple group의 경우**: Composition series = $\{e\} \triangleleft G$ (길이 1)

## Maximal Normal Subgroups^[극대 정규 부분군]

**정리**: $M \triangleleft G$ maximal normal $\Leftrightarrow$ $G/M$ simple

**증명**: Correspondence theorem으로

$M$ maximal $\Leftrightarrow$ $G/M$이 proper nontrivial normal subgroup 없음 $\Leftrightarrow$ $G/M$ simple ✓

## Simplicity and Index 2

**정리**: $H \triangleleft G$ with $[G : H] = 2$ $\Rightarrow$ $G$ not simple (unless $|G| = 2$)

**이유**: $H$는 proper nontrivial normal subgroup

**예**: $A_n \triangleleft S_n$ with $[S_n : A_n] = 2$ $\Rightarrow$ $S_n$ not simple (for $n \geq 3$)

## Simple implies No Nontrivial Quotients

$G$ simple, $N \triangleleft G$이면:

$$G/N \cong G \text{ or } G/N \cong \{e\}$$

**의미**: Simple group은 자기 자신 외에 nontrivial quotient 없음

---

# <span class="header-theorem">Theorem</span>

## Classification of Finite Simple Groups (CFSG)

**역사상 가장 큰 수학 정리 중 하나**

**정리**: 모든 finite simple group은 다음 중 하나:

### 1. Cyclic Groups of Prime Order

$$\mathbb{Z}/p\mathbb{Z} \quad (p \text{ prime})$$

Infinite family

### 2. Alternating Groups

$$A_n \quad (n \geq 5)$$

Infinite family

### 3. Groups of Lie Type^[리 타입 군]

**Classical groups**:
- $A_n(q) = \text{PSL}_{n+1}(\mathbb{F}_q)$ (Linear)
- $B_n(q) = \text{O}_{2n+1}(\mathbb{F}_q)$ (Orthogonal)
- $C_n(q) = \text{PSp}_{2n}(\mathbb{F}_q)$ (Symplectic)
- $D_n(q) = \text{O}_{2n}^+(\mathbb{F}_q)$ (Orthogonal)

**Exceptional groups**:
- $G_2(q), F_4(q), E_6(q), E_7(q), E_8(q)$
- Twisted types: ${}^2A_n(q), {}^2D_n(q), {}^3D_4(q), {}^2E_6(q)$

16 infinite families

### 4. Sporadic Groups^[산발적 군]

**26개의 예외적 simple groups**:

**Mathieu groups** (5):
- $M_{11}, M_{12}, M_{22}, M_{23}, M_{24}$

**Janko groups** (4):
- $J_1, J_2, J_3, J_4$

**Conway groups** (3):
- $Co_1, Co_2, Co_3$

**Fischer groups** (3):
- $Fi_{22}, Fi_{23}, Fi_{24}'$

**Higman-Sims**: $HS$

**McLaughlin**: $McL$

**Held**: $He$

**Rudvalis**: $Ru$

**Suzuki**: $Suz$

**O'Nan**: $O'N$

**Harada-Norton**: $HN$

**Lyons**: $Ly$

**Thompson**: $Th$

**Baby Monster**: $\mathbb{B}$

**Monster**: $\mathbb{M}$ (가장 큰 sporadic group)

**Happy Family**: Monster와 관련된 20개 sporadic groups

**Pariahs**: Monster와 무관한 6개 ($J_1, J_3, J_4, O'N, Ru, Ly$)

### 증명

**1950s-2004**: 수백 명의 수학자가 참여

**총 증명 길이**: 약 15,000 페이지

**2차 증명 프로젝트** (Gorenstein-Lyons-Solomon): 진행 중

## Simplicity of $A_n$ ($n \geq 5$)

**정리**: $A_n$ is simple for $n \geq 5$

**증명 스케치**:

1. $A_n$은 3-cycles로 generate됨
2. $N \triangleleft A_n$ nontrivial이면 $N$도 3-cycles 포함해야
3. 3-cycle 하나 포함하면 conjugation으로 모든 3-cycles 포함
4. 따라서 $N = A_n$ ✓

**$A_4$ not simple**: $V_4 = \{e, (12)(34), (13)(24), (14)(23)\} \triangleleft A_4$

## Burnside's $p^aq^b$ Theorem

**정리**: $|G| = p^a q^b$ (where $p, q$ prime) $\Rightarrow$ $G$ not simple (except $p^a$ or $q^b$ case)

**응용**: Order가 두 소수의 거듭제곱곱인 group은 simple이 아님

**예**: $|G| = 60 = 2^2 \cdot 3 \cdot 5$이면... wait, $A_5$ is simple!

Actually, theorem은 정확히: $|G| = p^a q^b$ $\Rightarrow$ $G$ solvable

Simple groups of order $p^a q^b$는 존재하지 않음 (except cyclic of prime order)

## Feit-Thompson Theorem (Odd Order Theorem)

**정리**: Odd order group ($|G|$ odd)은 solvable^[가해]

**따름정리**: Odd order이면서 simple인 group은 cyclic of prime order뿐

**증명**: 255 페이지 (1963)

**의미**: Non-abelian simple groups는 모두 even order

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Simple Group = "원자"**

- **화학**: 원소 → 분자
- **Group theory**: Simple groups → Arbitrary groups

**Jordan-Hölder**: 모든 finite group은 simple groups의 "층층이 쌓인" 구조

### 메타포: 소수 분해

**정수**: $n = p_1^{a_1} \cdot p_2^{a_2} \cdots p_k^{a_k}$ (소인수분해)

**Group**: Composition series with simple factors

**차이점**:
- 정수: 곱셈은 commutative (unique up to order)
- Group: Extension은 non-commutative (factors 순서 중요, 하지만 multiset는 유일)

## 왜 중요한가?

### 1. Building Blocks

모든 finite group을 이해하려면 먼저 simple groups를 이해해야

**전략**:
- Step 1: Simple groups 분류 (CFSG)
- Step 2: Extensions 이해 (어떻게 simple groups를 쌓아 올리는가?)

### 2. Classification Theorem

**CFSG = 20세기 수학의 최대 업적 중 하나**

- 100년 이상의 노력
- 수백 명의 수학자
- 15,000+ 페이지

### 3. 응용

**Group theory**:
- Representation theory
- Character theory
- Modular forms

**Number theory**:
- Galois groups
- Class field theory

**Geometry**:
- Symmetry groups
- Lie groups

**Combinatorics**:
- Design theory
- Coding theory

**Physics**:
- Particle physics (gauge groups)
- Crystal structure

## Simple vs Abelian

| | **Abelian** | **Non-Abelian** |
|---|---|---|
| **Simple** | $\mathbb{Z}/p\mathbb{Z}$ only | $A_n$ ($n \geq 5$), Lie type, Sporadic |
| **Not Simple** | $\mathbb{Z}/n\mathbb{Z}$ ($n$ composite) | Most groups |

**관찰**: "Interesting" simple groups는 대부분 non-abelian

## 난이도

**Abelian case**: Elementary (Lagrange's theorem)

**$A_n$ case**: Undergraduate level

**Lie type**: Graduate level (Linear algebra, Field theory)

**Sporadic**: Research level (각각이 독특한 구조)

**CFSG 전체**: Decades of research

## Historical Development^[역사적 발전]

**1832**: Galois - Simple groups의 개념 (via $A_5$)

**1870s**: Jordan - Composition series

**1890s**: Hölder - Jordan-Hölder theorem

**1892**: Otto Hölder - $\text{PSL}_2$ simple

**1896**: Burnside - $p^a q^b$ conjecture

**1955**: Chevalley - Groups of Lie type 구성

**1963**: Feit-Thompson - Odd order theorem

**1970s-1980s**: CFSG 완성 발표

**2004**: Aschbacher-Smith - 마지막 gap 해결

**현재**: Second-generation proof 진행 중

## Monster Group^[괴물군]

**가장 큰 sporadic simple group**

$$|\mathbb{M}| \approx 8 \times 10^{53}$$

**발견**: 1973 (Fischer-Griess)

**구성**: 1982 (Griess) - 196,883 차원 algebra

**연결**:
- **Monstrous moonshine**: j-function과 Monster의 표현론
- **String theory**: 24차원 bosonic string
- **Vertex operator algebras**

**McKay-Thompson series**: Modular functions

## Simplicity Tests^[단순성 검증]

실제로 group이 simple인지 확인하는 방법:

### 1. Order Check

- Prime order $\Rightarrow$ Simple (cyclic)
- $p^a q^b$ with $a, b > 0$ $\Rightarrow$ Not simple

### 2. Normal Subgroup Search

모든 proper subgroup이 normal인지 확인

### 3. Center Check

$Z(G) \neq \{e\} \Rightarrow$ Not simple (unless $|G|$ prime)

### 4. Known Families

$A_n$ ($n \geq 5$), $\text{PSL}_n$, etc.

### 5. Computational

GAP, Magma 등 소프트웨어 사용

## Non-simplicity Indicators

Group이 simple이 **아닌** 증거:

1. **Center nontrivial**: $Z(G) \neq \{e\}$ (unless prime order)
2. **Index 2 subgroup**: $[G : H] = 2$
3. **Composite order with structure**: $|G| = p^a q^b$ (Burnside)
4. **Abelian and not prime order**
5. **Sylow subgroup normal**: $P$ normal $\Rightarrow$ not simple

## 표기법

| 표기 | 의미 |
|------|------|
| $A_n$ | Alternating group |
| $\text{PSL}_n(\mathbb{F}_q)$ | Projective special linear group |
| $\mathbb{M}$ | Monster group |
| $\mathbb{B}$ | Baby Monster group |
| CFSG | Classification of Finite Simple Groups |
| $G_2, F_4, E_6, E_7, E_8$ | Exceptional Lie groups |

## 관련 개념

- [[Normal Subgroup]]: Simple = 최소 normal subgroups
- [[Quotient Group]]: Simple = no nontrivial quotients
- [[Composition Series]]: Simple = building blocks
- [[Solvable Group]]: Opposite extreme
- [[Symmetric Group]]: $A_n$ is simple
- [[Galois Theory]]: Solvability by radicals

## 추가 학습 주제

**기초**:
- Cyclic groups of prime order
- $A_5$ simplicity proof
- Composition series

**중급**:
- Lie type groups
- Character theory
- Sylow theorems applications

**고급**:
- CFSG details
- Sporadic groups construction
- Moonshine conjectures

## Open Problems

**CFSG 검증**: 2차 증명 프로젝트 완성

**Monster moonshine 일반화**: 다른 sporadic groups

**Computational complexity**: Simple group 인식 알고리즘

**응용**: Physics, Coding theory에서의 새로운 응용

