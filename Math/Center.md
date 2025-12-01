# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Abelian Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Center^[중심]

Group $G$의 **center**^[중심]:

$$Z(G) = \{z \in G : zg = gz \; \forall g \in G\}$$

**의미**: 모든 원소와 교환하는 원소들의 집합

### Alternative Characterization

$$Z(G) = \bigcap_{g \in G} C_G(g)$$

where $C_G(g) = \{h \in G : hg = gh\}$ (centralizer^[중심화원])

## Centralizer^[중심화원]

원소 $g \in G$의 **centralizer**^[중심화원]:

$$C_G(g) = \{h \in G : hg = gh\}$$

**의미**: $g$와 교환하는 원소들

**관계**: $Z(G) = \bigcap_{g \in G} C_G(g)$

---

# <span class="header-properties">Properties</span>

## Subgroup

**정리**: $Z(G) \leq G$

**증명**:
- **Identity**: $e \in Z(G)$ (모든 것과 교환) - **Closure**: $z_1, z_2 \in Z(G)$ $\Rightarrow$ $(z_1z_2)g = z_1(z_2g) = z_1(gz_2) = (z_1g)z_2 = (gz_1)z_2 = g(z_1z_2)$ - **Inverse**: $z \in Z(G)$ $\Rightarrow$ $z^{-1}g = z^{-1}gzz^{-1} = z^{-1}zgz^{-1} = gz^{-1}$ 
## Normal Subgroup

**정리**: $Z(G) \triangleleft G$ (characteristic subgroup)

**증명**: $gZ(G)g^{-1} = Z(G)$ for all $g$

더 강하게: $\phi(Z(G)) = Z(G)$ for all $\phi \in \text{Aut}(G)$

**의미**: Center는 항상 normal (심지어 characteristic)

자세한 내용은 [[Normal Subgroup]] 참조

## Abelian $\Leftrightarrow$ Center is Everything

**정리**: $G$ abelian $\Leftrightarrow Z(G) = G$

**증명**:
- ($\Rightarrow$): Abelian이면 모든 원소가 교환 $\Rightarrow$ $Z(G) = G$ - ($\Leftarrow$): $Z(G) = G$ $\Rightarrow$ 모든 원소 쌍이 교환 $\Rightarrow$ abelian 
자세한 내용은 [[Abelian Group]] 참조

## Quotient by Center

$$G/Z(G)$$

**성질**:
- $Z(G/Z(G))$ 분석 가능
- If $G/Z(G)$ cyclic $\Rightarrow$ $G$ abelian

**정리**: $G/Z(G)$ cyclic $\Rightarrow G$ abelian

**증명**: $G/Z(G) = \langle \bar{g} \rangle$ cyclic

$\Rightarrow$ 모든 원소가 $gZ(G)$의 거듭제곱 형태

$\Rightarrow$ Central elements와 $g$의 powers로 표현

$\Rightarrow$ 교환 
## $p$-groups Have Non-trivial Center

**정리**: $|G| = p^n$ ($p$ prime), $n > 0$ $\Rightarrow Z(G) \neq \{e\}$

**증명**: Class equation

$$|G| = |Z(G)| + \sum_{i} [G : C_G(x_i)]$$

$p \mid |G|$, $p \mid [G : C_G(x_i)]$ $\Rightarrow$ $p \mid |Z(G)|$

$\Rightarrow |Z(G)| \geq p > 1$ 
자세한 내용은 [[p-Group]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Abelian Groups

$G$ abelian $\Rightarrow Z(G) = G$

**예**:
- $Z(\mathbb{Z}) = \mathbb{Z}$
- $Z(\mathbb{Z}/n\mathbb{Z}) = \mathbb{Z}/n\mathbb{Z}$
- $Z(\mathbb{R}^n) = \mathbb{R}^n$

## Example 2: $S_3$

$$Z(S_3) = \{e\}$$

**확인**: 모든 non-identity element가 어떤 것과는 교환 안 함

예: $(12)(13) = (132) \neq (123) = (13)(12)$

## Example 3: Dihedral Group $D_n$

$$D_n = \langle r, s : r^n = s^2 = e, srs = r^{-1} \rangle$$

### $n$ odd

$$Z(D_n) = \{e\}$$

### $n$ even

$$Z(D_n) = \{e, r^{n/2}\}$$

**확인**: $r^{n/2}$ commutes with all

자세한 내용은 [[Dihedral Group]] 참조

## Example 4: Quaternion Group $Q_8$

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

$$Z(Q_8) = \{1, -1\}$$

**확인**: 
- $-1$ commutes with all
- $i, j, k$ don't commute with each other

## Example 5: $\text{GL}_n(\mathbb{R})$

$$Z(\text{GL}_n(\mathbb{R})) = \{\lambda I : \lambda \in \mathbb{R}^\times\}$$

Scalar matrices (non-zero)

**증명**: $AB = BA$ for all $B$ $\Leftrightarrow$ $A = \lambda I$

## Example 6: Heisenberg Group $H_3$

$$H_3 = \left\{ \begin{pmatrix} 1 & a & c \\ 0 & 1 & b \\ 0 & 0 & 1 \end{pmatrix} : a,b,c \in \mathbb{R} \right\}$$

$$Z(H_3) = \left\{ \begin{pmatrix} 1 & 0 & c \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} : c \in \mathbb{R} \right\} \cong \mathbb{R}$$

---

# <span class="header-theorem">Theorem</span>

## Class Equation

$$|G| = |Z(G)| + \sum_{i} [G : C_G(x_i)]$$

where sum is over representatives of non-central conjugacy classes

**응용**: $p$-groups의 center 분석

자세한 내용은 [[Group Action]] 참조

## Grün's Theorem

$G$ finite, $p$ prime dividing $|Z(G)|$

$\Rightarrow$ $p$ divides $|G/Z(G)|$

## Schur's Lemma (related)

Irreducible representation: Center acts by scalars

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Center = "고요한 중심"**

### 메타포: 회전 중심

**회전**: Group 연산

**중심**: 모든 회전에 불변

**고정점**: 모든 것과 교환

### 메타포: 교통 허브

**Center**: 모든 경로와 연결

**Non-central**: 일부 경로만

## 왜 중요한가?

### 1. Abelianness 측정

$|Z(G)|$ 크다 ↔ $G$가 "더 abelian에 가까움"

### 2. Quotient 분석

$G/Z(G)$: Center "제거"한 구조

### 3. $p$-groups

Non-trivial center $\Rightarrow$ structure constraints

### 4. Classification

Center size는 중요한 invariant

## 계산 방법

**Step 1**: 각 원소 $g$에 대해

**Step 2**: 모든 $h \in G$와 교환하는지 확인

**Step 3**: 교환하는 원소들 = $Z(G)$

## 표기법

| 표기 | 의미 |
|------|------|
| $Z(G)$ | Center of $G$ |
| $C_G(g)$ | Centralizer of $g$ |
| $Z_i(G)$ | $i$-th term of upper central series |

## Common Pitfall^[흔한 실수]

### 1. Centralizer ≠ Center

$C_G(g)$ depends on $g$

$Z(G) = \bigcap_g C_G(g)$

### 2. Normal ≠ Central

Normal subgroup $\not\Rightarrow$ contained in center

### 3. Cyclic quotient

$G/Z(G)$ cyclic $\Rightarrow$ $G$ abelian

하지만 $Z(G)$ cyclic $\not\Rightarrow$ $G$ abelian

## 관련 개념

- [[Group]]: Basic structure
- [[Normal Subgroup]]: Center is normal
- [[Abelian Group]]: $Z(G) = G$
- [[Nilpotent Group]]: Upper central series
- [[p-Group]]: Non-trivial center

## 추가 학습 주제

**기초**:
- Definition
- Examples
- Computation

**중급**:
- Class equation
- $p$-groups
- Quotients

**고급**:
- Upper central series
- Schur multiplier
- Representation theory

