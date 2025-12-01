# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Coset]]
- [[Group Action]]
- [[Lagrange's theorem]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Orbit-Stabilizer Theorem^[궤도-안정화군 정리]

**정리**: $G$ acts on set $X$, $x \in X$

$$|\mathcal{O}_x| = [G : G_x]$$

**Finite case**:

$$|\mathcal{O}_x| = \frac{|G|}{|G_x|}$$

where:
- $\mathcal{O}_x = G \cdot x$ = orbit of $x$
- $G_x = \text{Stab}_G(x)$ = stabilizer of $x$

### 용어

**Orbit**^[궤도]: $\mathcal{O}_x = \{g \cdot x : g \in G\}$

**Stabilizer**^[안정화군]: $G_x = \{g \in G : g \cdot x = x\}$

자세한 내용은 [[Group Action]] 참조

---

# <span class="header-proof">Proof</span>

## 증명

**목표**: Bijection $G/G_x \to \mathcal{O}_x$ 구성

### Step 1: Map 정의

$$\phi: G/G_x \to \mathcal{O}_x$$

$$\phi(gG_x) = g \cdot x$$

### Step 2: Well-defined

$gG_x = hG_x$일 때 $g \cdot x = h \cdot x$인가?

$$gG_x = hG_x \Leftrightarrow h^{-1}g \in G_x \Leftrightarrow h^{-1}g \cdot x = x$$

$$\Leftrightarrow g \cdot x = h \cdot x$$ 
### Step 3: Injective

$$\phi(gG_x) = \phi(hG_x) \Rightarrow g \cdot x = h \cdot x$$

$$\Rightarrow h^{-1}g \cdot x = x \Rightarrow h^{-1}g \in G_x$$

$$\Rightarrow gG_x = hG_x$$ 
### Step 4: Surjective

$y \in \mathcal{O}_x$ $\Rightarrow$ $y = g \cdot x$ for some $g \in G$

$$\Rightarrow \phi(gG_x) = g \cdot x = y$$ 
**결론**: $\phi$는 bijection

$$\Rightarrow |G/G_x| = |\mathcal{O}_x|$$

$$\Rightarrow [G : G_x] = |\mathcal{O}_x|$$ 
---

# <span class="header-examples">Examples</span>

## Example 1: $S_n$ on $\{1, \ldots, n\}$

$G = S_n$ acts on $X = \{1, \ldots, n\}$

**Fix $x = 1$**:

**Orbit**: $\mathcal{O}_1 = \{1, 2, \ldots, n\}$ (transitive)

**Stabilizer**: $G_1 = \{\sigma \in S_n : \sigma(1) = 1\} \cong S_{n-1}$

**Check**:

$$|\mathcal{O}_1| = n, \quad [S_n : S_{n-1}] = \frac{n!}{(n-1)!} = n$$ 
자세한 내용은 [[Symmetric Group]] 참조

## Example 2: Dihedral Group on Vertices

$D_n$ acts on vertices of regular $n$-gon

**Fix vertex $v_1$**:

**Orbit**: All $n$ vertices (transitive)

**Stabilizer**: $G_{v_1} = \{e, s_1\}$ (identity and one reflection) of order 2

**Check**:

$$|\mathcal{O}_{v_1}| = n, \quad [D_n : G_{v_1}] = \frac{2n}{2} = n$$ 
자세한 내용은 [[Dihedral Group]] 참조

## Example 3: Conjugation Action

$G$ acts on itself by conjugation: $g \cdot h = ghg^{-1}$

**Orbit**: Conjugacy class $\text{Cl}(h)$

**Stabilizer**: Centralizer $C_G(h) = \{g : gh = hg\}$

**Orbit-Stabilizer**:

$$|\text{Cl}(h)| = [G : C_G(h)]$$

**응용**: Class equation

$$|G| = |Z(G)| + \sum_i [G : C_G(x_i)]$$

자세한 내용은 [[Center]] 참조

## Example 4: $G$ on Cosets $G/H$

$G$ acts on left cosets $G/H$ by $g \cdot (xH) = (gx)H$

**Fix coset $H$**:

**Orbit**: All of $G/H$ (transitive)

**Stabilizer**: $G_H = H$

**Check**:

$$|G/H| = [G : H] = \frac{|G|}{|H|}$$ 
자세한 내용은 [[Coset]] 참조

## Example 5: Rotation Group on Sphere

$\text{SO}(3)$ acts on unit sphere $S^2$

**Fix point $p = (0, 0, 1)$ (north pole)**:

**Orbit**: Entire sphere $S^2$ (transitive)

**Stabilizer**: $\text{SO}(2) \subset \text{SO}(3)$ (rotations around $z$-axis)

**결과**: $S^2 \cong \text{SO}(3)/\text{SO}(2)$

---

# <span class="header-properties">Properties</span>

## Corollaries^[따름정리]

### 1. Orbit Size Divides Group Order

Finite $G$:

$$|\mathcal{O}_x| \mid |G|$$

**증명**: $|\mathcal{O}_x| = |G|/|G_x|$, $|G_x| \mid |G|$ (Lagrange) 
자세한 내용은 [[Lagrange's theorem]] 참조

### 2. Fixed Points and Divisibility

$$|X^G| \equiv |X| \pmod{|G|}$$

where $X^G = \{x : g \cdot x = x \; \forall g\}$ (fixed points)

### 3. Burnside's Lemma Connection

$$|\text{Orbits}| = \frac{1}{|G|} \sum_{g \in G} |X^g|$$

Combined with orbit-stabilizer theorem

자세한 내용은 [[Group Action]] 참조

## Multiple Orbits

$$|X| = \sum_{\text{orbits}} |\mathcal{O}_{x_i}| = \sum_{\text{orbits}} [G : G_{x_i}]$$

**Partition**: Orbits partition $X$

## Transitive Action

**정의**: Action is transitive $\Leftrightarrow$ single orbit

$$\mathcal{O}_x = X \text{ for any } x$$

**Orbit-Stabilizer**: $|X| = [G : G_x]$ for any $x$

---

# <span class="header-theorem">Theorem</span>

## Class Equation

**정리**: $G$ acts on itself by conjugation

$$|G| = |Z(G)| + \sum_{i} [G : C_G(x_i)]$$

where sum over non-central conjugacy class representatives

**증명**: Orbit-stabilizer + partition by orbits

자세한 내용은 [[Center]] 참조

## Sylow Theorems Application

**정리**: Number of Sylow $p$-subgroups

$$n_p = [G : N_G(P)]$$

where $P \in \text{Syl}_p(G)$, $N_G(P)$ = normalizer

**증명**: $G$ acts on $\text{Syl}_p(G)$ by conjugation

Stabilizer of $P$ = $N_G(P)$

Orbit-stabilizer: $n_p = [G : N_G(P)]$ 
자세한 내용은 [[Sylow Theorem]] 참조

## Cauchy's Theorem

**정리**: $p \mid |G|$ (prime) $\Rightarrow \exists g$ with $|g| = p$

**증명 (using group action)**:

$G$ acts on $X = G \times \cdots \times G$ ($p$ copies) by cyclic permutation

Orbit-stabilizer analysis → element of order $p$ 
---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Orbit-Stabilizer = "이동 공간 × 고정 공간 = 전체"**

### 메타포: 회전과 축

**Orbit**: 점이 갈 수 있는 모든 위치

**Stabilizer**: 점을 고정하는 변환들

**관계**: 크게 움직임 ↔ 적게 고정 (trade-off)

### 메타포: 자유도

**$|G|$**: 전체 자유도

**$|\mathcal{O}_x|$**: 움직임의 자유도

**$|G_x|$**: 고정의 자유도

$$\text{움직임} \times \text{고정} = \text{전체}$$

## 왜 중요한가?

### 1. Counting Tool

**Orbit 크기 계산**: Stabilizer 찾기 → Orbit size

**역으로**: Orbit size 알면 → Stabilizer size

### 2. Structure Analysis

**Transitive actions**: $|X| = [G : G_x]$ (homogeneous space)

**Class equation**: Group structure 분석

### 3. Existence Proofs

**Element 존재성**: Orbit/stabilizer counting으로

**예**: Cauchy's theorem, Sylow theorems

### 4. 응용 분야 광범위

Combinatorics, Geometry, Number Theory 등

## 계산 전략

### Given: $|G|$, $|G_x|$

**Find**: $|\mathcal{O}_x| = |G|/|G_x|$

### Given: $|G|$, $|\mathcal{O}_x|$

**Find**: $|G_x| = |G|/|\mathcal{O}_x|$

### Given: Action description

1. Stabilizer 계산 (definition으로)
2. Orbit-stabilizer로 orbit size

## 특수한 경우들

| Action Type | Orbit | Stabilizer | Relation |
|-------------|-------|------------|----------|
| **Transitive** | $\|X\|$ | Varies | $\|X\| = [G : G_x]$ |
| **Free** | Varies | $\{e\}$ | $\|\mathcal{O}_x\| = \|G\|$ |
| **Trivial** | $\{x\}$ | $G$ | $1 = [G : G]$ |

## 응용 예시

### $S_4$ on Unordered Pairs

$S_4$ acts on $\binom{4}{2} = 6$ unordered pairs

**Stabilizer of $\{1,2\}$**: $\cong S_2 \times S_2$ (order 4)

**Orbit size**: $24/4 = 6$  (전체 pairs)

### Rotations of Cube

Rotation group acts on:
- **Vertices** (8): Stabilizer order $3$, $|G| = 24$
- **Edges** (12): Stabilizer order $2$
- **Faces** (6): Stabilizer order $4$

Check: $8 \cdot 3 = 12 \cdot 2 = 6 \cdot 4 = 24$ 
## 표기법

| 표기 | 의미 |
|------|------|
| $\mathcal{O}_x$ or $G \cdot x$ | Orbit of $x$ |
| $G_x$ or $\text{Stab}_G(x)$ | Stabilizer of $x$ |
| $[G : H]$ | Index |
| $X^g$ | Fixed points of $g$ |

## Common Pitfall^[흔한 실수]

### 1. Orbit size formula

$$|\mathcal{O}_x| = \frac{|G|}{|G_x|} \quad \text{(not } |G_x|\text{!)}$$

Reciprocal!

### 2. Multiple orbits

Orbit-stabilizer는 **각 orbit**에 대해 적용

전체 $X$가 아님!

### 3. Stabilizer is subgroup

$G_x \leq G$ (항상 subgroup)

Lagrange's theorem 적용 가능

### 4. Well-definedness

$\phi(gG_x) = g \cdot x$ 확인 필요

Representative independence

### 5. Transitive ≠ Free

- **Transitive**: One orbit
- **Free**: Trivial stabilizers

Different concepts!

## 관련 개념

- [[Group Action]]: Basic framework
- [[Coset]]: $G/G_x$ structure
- [[Lagrange's theorem]]: $[G : G_x]$ divides $|G|$
- [[Sylow Theorem]]: Application
- [[Burnside's Lemma]]: Counting orbits

## 추가 학습 주제

**기초**:
- Orbit and stabilizer definitions
- Basic examples
- Counting applications

**중급**:
- Class equation
- Burnside's lemma
- Sylow theorems

**고급**:
- Transitive actions
- Primitive actions
- Homogeneous spaces

