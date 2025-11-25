# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Nilpotent Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Robinson, A Course in the Theory of Groups
- Isaacs, Finite Group Theory

---

# <span class="header-definition">Definition</span>

## Fitting Subgroup^[피팅 부분군]

**Fitting subgroup**^[피팅 부분군] $F(G)$ of group $G$:

$$F(G) = \text{join of all normal nilpotent subgroups of } G$$

**즉**:

$$F(G) = \langle N : N \triangleleft G, N \text{ nilpotent} \rangle$$

**Alternative**: Largest normal nilpotent subgroup

$$F(G) = \max\{N \triangleleft G : N \text{ nilpotent}\}$$

자세한 내용은 [[Nilpotent Group]] 참조

### Properties of $F(G)$

**$F(G)$는 characteristic subgroup**:

$$\phi \in \text{Aut}(G) \Rightarrow \phi(F(G)) = F(G)$$

**의미**: 모든 automorphism에 대해 불변

자세한 내용은 [[Isomorphism]] 참조

## Frattini Subgroup^[프라티니 부분군]

**Frattini subgroup**^[프라티니 부분군] $\Phi(G)$ of group $G$:

$$\Phi(G) = \bigcap_{M \text{ maximal}} M$$

**의미**: 모든 maximal subgroup들의 교집합

**Convention**: If no maximal subgroups, $\Phi(G) = G$

### Maximal Subgroup

**Maximal subgroup**^[극대 부분군]: Proper subgroup $M < G$ such that

$$M < H \leq G \Rightarrow H = G$$

**의미**: $M$과 $G$ 사이에 다른 subgroup 없음

## Non-generators

**정리**: $g \in \Phi(G)$ $\Leftrightarrow$ $g$ is **non-generator**^[비생성원]

$$\text{If } G = \langle S, g \rangle \text{ then } G = \langle S \rangle$$

**의미**: $\Phi(G)$의 원소는 generating set에서 제거 가능

**Alternative name**: $\Phi(G)$ = **non-generating set**^[비생성 집합]

---

# <span class="header-properties">Properties</span>

## Properties of Fitting Subgroup

### 1. Normal and Nilpotent

$$F(G) \triangleleft G \quad \text{and} \quad F(G) \text{ is nilpotent}$$

**증명**: Join of normal nilpotent subgroups is nilpotent ✓

### 2. Characteristic

$$F(G) \text{ is characteristic in } G$$

**의미**: $\phi(F(G)) = F(G)$ for all $\phi \in \text{Aut}(G)$

### 3. Contains Center

$$Z(G) \subseteq F(G)$$

**증명**: $Z(G)$ abelian $\Rightarrow$ nilpotent $\Rightarrow$ $Z(G) \subseteq F(G)$ ✓

자세한 내용은 [[Center]] 참조

### 4. Solvable Groups

**정리**: If $G$ solvable, then

$$G / F(G) \text{ acts faithfully on } F(G)$$

**응용**: Structure theory of solvable groups

자세한 내용은 [[Solvable Group]] 참조

### 5. Finite Groups

**정리**: In finite group $G$,

$$F(G) = \text{direct product of all Sylow } p\text{-subgroups of } Z(G)$$

**의미**: $F(G)$는 center의 Sylow subgroups

자세한 내용은 [[Sylow Theorem]], [[p-Group]] 참조

## Properties of Frattini Subgroup

### 1. Characteristic

$$\Phi(G) \triangleleft G \quad \text{and} \quad \Phi(G) \text{ is characteristic}$$

**증명**: Intersection of all maximal (normal) subgroups ✓

### 2. Nilpotent (Finite Groups)

**정리**: If $G$ finite, then $\Phi(G)$ is nilpotent

**증명**: Non-trivial theorem!

### 3. Frattini Argument

**정리**: If $H \triangleleft G$ and $P \in \text{Syl}_p(H)$,

$$G = H \cdot N_G(P)$$

**의미**: $G$는 $H$와 $P$의 normalizer로 generate

**응용**: Structure theorems, classification

자세한 내용은 [[Sylow Theorem]] 참조

### 4. Product Property

$$\Phi(G \times H) = \Phi(G) \times \Phi(H)$$

자세한 내용은 [[Direct Product]] 참조

### 5. Cyclic Groups

$$\Phi(\mathbb{Z}/p^n\mathbb{Z}) = p \mathbb{Z}/p^n\mathbb{Z} \cong \mathbb{Z}/p^{n-1}\mathbb{Z}$$

$$\Phi(\mathbb{Z}) = \{0\}$$

자세한 내용은 [[Cyclic Group]] 참조

### 6. p-Groups

**정리**: For finite $p$-group $G$,

$$\Phi(G) = G' \cdot G^p$$

where $G' = [G,G]$ (commutator subgroup), $G^p = \{g^p : g \in G\}$

자세한 내용은 [[p-Group]], [[Commutator Subgroup]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Cyclic Groups

**$\mathbb{Z}$**:

$$F(\mathbb{Z}) = \mathbb{Z} \quad (\text{abelian} \Rightarrow \text{nilpotent})$$

$$\Phi(\mathbb{Z}) = \{0\} \quad (\text{no maximal subgroups})$$

**$\mathbb{Z}/n\mathbb{Z}$**:

$$F(\mathbb{Z}/n\mathbb{Z}) = \mathbb{Z}/n\mathbb{Z} \quad (\text{abelian})$$

$$\Phi(\mathbb{Z}/p^k\mathbb{Z}) = p\mathbb{Z}/p^k\mathbb{Z}$$

자세한 내용은 [[Cyclic Group]] 참조

## Example 2: Dihedral Group $D_8$

$$D_8 = \langle r, s \mid r^4, s^2, srs^{-1} = r^{-1} \rangle$$

**Fitting subgroup**:

$$F(D_8) = \langle r \rangle \cong \mathbb{Z}/4\mathbb{Z}$$

**Frattini subgroup**:

$$\Phi(D_8) = \langle r^2 \rangle \cong \mathbb{Z}/2\mathbb{Z}$$

자세한 내용은 [[Dihedral Group]] 참조

## Example 3: Symmetric Group $S_n$

**$S_3$**:

$$F(S_3) = \{e\} \quad (\text{no nontrivial normal nilpotent})$$

$$\Phi(S_3) = \{e\}$$

**$S_n$ (n≥3)**:

$$F(S_n) = \{e\}$$

$$\Phi(S_n) = \{e\}$$

자세한 내용은 [[Symmetric Group]] 참조

## Example 4: p-Groups

**$p$-group of order $p^2$**:

$$G \cong \mathbb{Z}/p^2\mathbb{Z} \text{ or } \mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z}$$

**Case 1**: $G = \mathbb{Z}/p^2\mathbb{Z}$

$$F(G) = G \quad (\text{abelian})$$

$$\Phi(G) = p\mathbb{Z}/p^2\mathbb{Z} \cong \mathbb{Z}/p\mathbb{Z}$$

**Case 2**: $G = \mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/p\mathbb{Z}$

$$F(G) = G$$

$$\Phi(G) = \{e\}$$

자세한 내용은 [[p-Group]] 참조

## Example 5: Quaternion Group $Q_8$

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

**Fitting subgroup**:

$$F(Q_8) = Q_8 \quad (\text{nilpotent})$$

**Frattini subgroup**:

$$\Phi(Q_8) = \langle -1 \rangle = Z(Q_8) \cong \mathbb{Z}/2\mathbb{Z}$$

자세한 내용은 [[Center]] 참조

## Example 6: Alternating Group $A_n$

**$A_4$**:

$$F(A_4) = V_4 = \{e, (12)(34), (13)(24), (14)(23)\}$$

(Klein four-group, normal and abelian)

$$\Phi(A_4) = \{e\}$$

**$A_n$ (n≥5)**:

$$F(A_n) = \{e\} \quad (\text{simple})$$

$$\Phi(A_n) = \{e\}$$

자세한 내용은 [[Alternating Group]] 참조

---

# <span class="header-theorem">Theorem</span>

## Fitting's Theorem

**정리**: If $G$ is finite nilpotent group,

$$F(G) = G$$

**의미**: Finite nilpotent groups are their own Fitting subgroup

**역**: $F(G) = G$ $\Rightarrow$ $G$ nilpotent ✓

## Frattini Argument

**정리**: Let $G$ be finite, $H \triangleleft G$, $P \in \text{Syl}_p(H)$

$$G = H \cdot N_G(P)$$

**증명**:

For any $g \in G$, $gPg^{-1} \in \text{Syl}_p(H)$ (conjugate of Sylow)

By Sylow's theorem, $\exists h \in H$ : $gPg^{-1} = hPh^{-1}$

$\Rightarrow$ $h^{-1}g \in N_G(P)$ $\Rightarrow$ $g \in H \cdot N_G(P)$ ✓

자세한 내용은 [[Sylow Theorem]] 참조

## Characterization via Non-generators

**정리**: $\Phi(G) = \{g \in G : g \text{ is non-generator}\}$

**증명**: 

$(\Rightarrow)$ If $g \in \Phi(G)$ and $G = \langle S, g \rangle$,

then $\langle S \rangle$ not contained in any maximal subgroup

$\Rightarrow$ $\langle S \rangle = G$ ✓

$(\Leftarrow)$ If $g \notin \Phi(G)$, $\exists$ maximal $M$ with $g \notin M$

Then $G = \langle M, g \rangle$ but $G \neq \langle M \rangle$ (contradiction) ✓

## Frattini for p-Groups

**정리**: For finite $p$-group $G$,

$$\Phi(G) = G' G^p$$

where $G' = [G,G]$, $G^p = \{g^p : g \in G\}$

**응용**: Minimal generating sets

## Baer's Theorem

**정리**: If $G/\Phi(G)$ is nilpotent, then $G$ is nilpotent

**의미**: Nilpotency "lifts" through Frattini quotient

## Fitting Chain

For solvable group $G$, define:

$$F_0(G) = \{e\}, \quad F_{i+1}(G)/F_i(G) = F(G/F_i(G))$$

**정리**: $\exists n$ : $F_n(G) = G$ (Fitting series)

자세한 내용은 [[Solvable Group]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### Fitting Subgroup = "Nilpotent Core"

**의미**: 가장 큰 normal nilpotent part

**메타포**: Group의 "중심적이고 안정적인" 부분

**예**: $D_8$에서 $F(D_8) = \langle r \rangle$ (rotations만, 가장 "중심적")

### Frattini Subgroup = "Non-essential Elements"

**의미**: 제거 가능한 원소들

**메타포**: "중복되는" 또는 "필수적이지 않은" 원소

**예**: Generating set에서 빼도 여전히 generate

## 왜 중요한가?

### 1. Structure Theory

**Fitting**: Nilpotent 부분 분석

**Frattini**: Minimal generating sets

### 2. Finite Group Classification

**Building blocks**: Simple groups, nilpotent groups

**Fitting**: 구조 분해

### 3. Representation Theory

**Fitting**: 표현론에서 중요한 역할

**Frattini**: Irreducible representations

### 4. Computational

**Algorithms**: 계산 가능한 invariants

**GAP, Magma**: 구현

## Fitting vs Frattini

| | **Fitting $F(G)$** | **Frattini $\Phi(G)$** |
|---|---|---|
| **정의** | Largest normal nilpotent | Intersection of maximal |
| **의미** | "Nilpotent core" | "Non-generators" |
| **Always nilpotent?** | Yes | Yes (if finite) |
| **포함 관계** | $Z(G) \subseteq F(G)$ | $\Phi(G) \subseteq F(G)$ (not always!) |
| **Cyclic $\mathbb{Z}$** | $\mathbb{Z}$ | $\{0\}$ |

**주의**: $\Phi(G) \subseteq F(G)$ 항상 성립하는 것 아님!

## 계산 방법

### Fitting Subgroup

**Step 1**: 모든 normal nilpotent subgroups 찾기

**Step 2**: Their join (product) 계산

**Step 3**: Verify nilpotency

### Frattini Subgroup

**Step 1**: 모든 maximal subgroups 찾기

**Step 2**: Intersection 계산

**Tip**: Use non-generator characterization

### Finite Groups

**Software**: GAP, Magma

**Command (GAP)**: `FittingSubgroup(G)`, `FrattiniSubgroup(G)`

## 표기법

| 표기 | 의미 |
|------|------|
| $F(G)$ | Fitting subgroup |
| $\Phi(G)$ | Frattini subgroup |
| $G'$ or $[G,G]$ | Commutator subgroup |
| $G^p$ | $\{g^p : g \in G\}$ |
| $N_G(H)$ | Normalizer of $H$ in $G$ |
| $Z(G)$ | Center of $G$ |

## Common Pitfall^[흔한 실수]

### 1. $\Phi(G) \not\subseteq F(G)$ (일반적으로)

항상 성립하는 것 아님!

**반례**: 일부 solvable but non-nilpotent groups

### 2. Frattini not always nilpotent

**Infinite groups**: $\Phi(G)$ may not be nilpotent

**Finite**: Always nilpotent ✓

### 3. Maximal subgroups

모든 maximal subgroup이 normal인 것 아님!

**Frattini**: All maximal의 교집합 (normal or not)

### 4. $F(G) = \{e\}$ possible

**Simple groups**: $F(S_n) = \{e\}$ (n≥3)

**의미**: No nontrivial normal nilpotent

### 5. $\Phi(\mathbb{Z}) = \{0\}$

$\mathbb{Z}$는 maximal subgroups 많음 ($p\mathbb{Z}$ for each prime $p$)

Intersection = $\{0\}$ ✓

## 관련 개념

- [[Nilpotent Group]]: Fitting의 핵심
- [[Solvable Group]]: 더 일반적인 개념
- [[Center]]: $Z(G) \subseteq F(G)$
- [[p-Group]]: Frattini 특별한 경우
- [[Sylow Theorem]]: Frattini Argument

## 추가 학습 주제

**기초**:
- Definitions
- Examples
- Basic properties

**중급**:
- Frattini Argument
- p-groups
- Computational methods

**고급**:
- Structure theory
- Representation theory
- Classification theorems
- Fitting series
- Generalized Fitting subgroup

