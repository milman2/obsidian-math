# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Group Action]]
- [[Center]]
- [[Orbit-Stabilizer Theorem]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups
- Isaacs, Finite Group Theory

---

# <span class="header-definition">Definition</span>

## Conjugacy Class^[켤레류]

**Conjugacy class**^[켤레류] of $g \in G$:

$$\text{cl}(g) = \{xgx^{-1} : x \in G\}$$

**의미**: $g$의 모든 conjugates

**표기**: Often write $\mathcal{C}(g)$ or $[g]$

### Conjugate Elements

$g, h \in G$ are **conjugate**^[켤레]if

$$\exists x \in G : h = xgx^{-1}$$

**Equivalence relation**:
- Reflexive: $g = ege^{-1}$ ✓
- Symmetric: $h = xgx^{-1}$ $\Rightarrow$ $g = x^{-1}hx$ ✓
- Transitive ✓

자세한 내용은 [[Equivalence Relation and Partitions]] 참조

## Centralizer^[중심화 부분군]

**Centralizer**^[중심화 부분군] of $g$ in $G$:

$$C_G(g) = \{x \in G : xg = gx\}$$

**의미**: $g$와 commute하는 원소들

**Subgroup**: $C_G(g) \leq G$ ✓

자세한 내용은 [[Subgroup]] 참조

## Class Equation^[류 방정식]

**Class equation**^[류 방정식] for finite group $G$:

$$|G| = |Z(G)| + \sum_{i} [G : C_G(g_i)]$$

where:
- Sum over representatives $g_i$ of non-central conjugacy classes
- $[G : C_G(g_i)]$ = index of centralizer = $|G|/|C_G(g_i)|$

**Alternative form**:

$$|G| = |Z(G)| + \sum_{i} |\text{cl}(g_i)|$$

where $|\text{cl}(g_i)| > 1$ (non-central classes)

자세한 내용은 [[Center]] 참조

---

# <span class="header-properties">Properties</span>

## Conjugacy as Group Action

**Action**: $G$ acts on itself by conjugation

$$g \cdot x = gxg^{-1}$$

**Orbits**: Conjugacy classes

$$\text{Orb}(x) = \text{cl}(x) = \{gxg^{-1} : g \in G\}$$

**Stabilizer**: Centralizer

$$\text{Stab}(x) = C_G(x) = \{g : gxg^{-1} = x\}$$

자세한 내용은 [[Group Action]], [[Orbit-Stabilizer Theorem]] 참조

## Size of Conjugacy Class

**정리**: By Orbit-Stabilizer Theorem,

$$|\text{cl}(g)| = [G : C_G(g)] = \frac{|G|}{|C_G(g)|}$$

**의미**: 
- Large centralizer → small conjugacy class
- Small centralizer → large conjugacy class

## Central Elements

**정리**: $g \in Z(G)$ $\Leftrightarrow$ $|\text{cl}(g)| = 1$

**증명**:

$$g \in Z(G) \Leftrightarrow C_G(g) = G \Leftrightarrow |\text{cl}(g)| = 1$$

**의미**: Center = singleton conjugacy classes

## Conjugacy Classes Partition $G$

**정리**: Conjugacy classes partition $G$

$$G = \bigsqcup_{i} \text{cl}(g_i)$$

**증명**: Conjugacy is equivalence relation ✓

**Size**: $|G| = \sum_i |\text{cl}(g_i)|$

## Divisibility

**정리**: For any $g \in G$,

$$|\text{cl}(g)| \mid |G|$$

**증명**: $|\text{cl}(g)| = [G : C_G(g)]$ divides $|G|$ by Lagrange ✓

자세한 내용은 [[Lagrange's theorem]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Abelian Groups

**모든 abelian group**: $G = Z(G)$

$$\text{cl}(g) = \{g\} \quad \text{for all } g$$

**Class equation**:

$$|G| = |G|$$

(모든 class가 singleton)

자세한 내용은 [[Abelian Group]] 참조

## Example 2: $S_3$

$$S_3 = \{e, (12), (13), (23), (123), (132)\}$$

**Conjugacy classes**:
- $\{e\}$ (size 1)
- $\{(12), (13), (23)\}$ (size 3) - transpositions
- $\{(123), (132)\}$ (size 2) - 3-cycles

**Center**: $Z(S_3) = \{e\}$

**Class equation**:

$$6 = 1 + 3 + 2$$

자세한 내용은 [[Symmetric Group]] 참조

## Example 3: $D_4$

$$D_4 = \langle r, s \mid r^4, s^2, srs^{-1} = r^{-1} \rangle$$

**Elements**: $\{e, r, r^2, r^3, s, sr, sr^2, sr^3\}$

**Conjugacy classes**:
- $\{e\}$ (size 1)
- $\{r^2\}$ (size 1) - central
- $\{r, r^3\}$ (size 2)
- $\{s, sr^2\}$ (size 2)
- $\{sr, sr^3\}$ (size 2)

**Center**: $Z(D_4) = \{e, r^2\}$

**Class equation**:

$$8 = 2 + 2 + 2 + 2$$

자세한 내용은 [[Dihedral Group]] 참조

## Example 4: Quaternion Group $Q_8$

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

**Conjugacy classes**:
- $\{1\}$ (size 1)
- $\{-1\}$ (size 1) - central
- $\{i, -i\}$ (size 2)
- $\{j, -j\}$ (size 2)
- $\{k, -k\}$ (size 2)

**Center**: $Z(Q_8) = \{1, -1\}$

**Class equation**:

$$8 = 2 + 2 + 2 + 2$$

## Example 5: $S_n$ (General)

**Conjugacy classes in $S_n$**: Determined by cycle type

**예**: In $S_4$,
- $(1234)$ conjugate to $(1243), (1324), \ldots$ (all 4-cycles)
- $(12)(34)$ conjugate to $(13)(24), (14)(23)$

**Size**: $\displaystyle|\text{cl}(\sigma)| = \frac{n!}{\prod_i i^{a_i} a_i!}$

where $a_i$ = number of $i$-cycles in cycle type

자세한 내용은 [[Symmetric Group]] 참조

## Example 6: $\text{GL}_n(\mathbb{F})$

**Conjugacy classes**: Determined by Jordan normal form

**Similar matrices**: Same conjugacy class

**Invariant**: Characteristic polynomial, Jordan blocks

---

# <span class="header-theorem">Theorem</span>

## Class Equation

**정리**: For finite group $G$,

$$|G| = |Z(G)| + \sum_{i} [G : C_G(g_i)]$$

**증명**:

Conjugacy classes partition $G$:

$$|G| = \sum_{\text{all classes}} |\text{cl}(g)|$$

Separate central (size 1) and non-central:

$$= |Z(G)| + \sum_{|\text{cl}(g_i)| > 1} |\text{cl}(g_i)|$$

$$= |Z(G)| + \sum_{i} [G : C_G(g_i)]$$ ✓

## Center of p-Group is Non-trivial

**정리**: If $G$ is finite $p$-group with $|G| > 1$,

$$Z(G) \neq \{e\}$$

**증명**: Class equation:

$$|G| = |Z(G)| + \sum_i [G : C_G(g_i)]$$

- $p \mid |G|$ (p-group)
- $p \mid [G : C_G(g_i)]$ for each $i$ (divides $|G|$)
- Therefore $p \mid |Z(G)|$
- Since $e \in Z(G)$, we have $|Z(G)| \geq p$ ✓

자세한 내용은 [[p-Group]] 참조

## Cauchy's Theorem (via Class Equation)

**정리**: If prime $p \mid |G|$, then $\exists g \in G$ with $|g| = p$

**증명 sketch**: Use class equation and induction

자세한 내용은 [[Lagrange's theorem]] 참조

## Groups of Order $p^2$

**정리**: If $|G| = p^2$, then $G$ abelian

**증명**: 

Class equation: $|G| = |Z(G)| + \sum_i [G : C_G(g_i)]$

$p^2 = |Z(G)| + \sum_i [G : C_G(g_i)]$

Each $[G : C_G(g_i)] \in \{p, p^2\}$ (divides $p^2$)

Cannot all be $p$ (doesn't sum to $p^2$)

Therefore $|Z(G)| = p$ or $p^2$

If $|Z(G)| = p^2$, then $Z(G) = G$ (abelian) ✓

If $|Z(G)| = p$, then $|G/Z(G)| = p$ (cyclic)

$\Rightarrow$ $G$ abelian (contradiction with $|Z(G)| = p$) ✓

자세한 내용은 [[Abelian Group]] 참조

## Conjugacy in Symmetric Groups

**정리**: In $S_n$, two permutations conjugate $\Leftrightarrow$ same cycle type

**증명**: Conjugation preserves cycle structure ✓

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Conjugacy Class = "유사한 원소들"**

### 메타포: 관점의 변화

**Conjugation**: 좌표계 변환

$$xgx^{-1} = \text{"$g$ seen from $x$'s perspective"}$$

**Conjugacy class**: 모든 관점에서 본 $g$

**Center**: 관점 독립적인 원소들

### 메타포: 기하학

**Conjugate**: 같은 "모양"이지만 다른 "위치"

**예**: Rotation matrices
- 같은 각도 회전 → conjugate
- 다른 축 중심 → 다른 element

**Center**: 모든 회전과 commute (예: scalar matrices)

## Class Equation의 의미

$$|G| = |Z(G)| + \sum_i [G : C_G(g_i)]$$

**해석**:

$$\text{전체} = \text{중심적} + \text{비-중심적}$$

**비-중심적**: 각 class의 크기 = group의 구조 반영

**응용**: p-groups, structure theorems

## 왜 중요한가?

### 1. Structure of p-Groups

**Non-trivial center**: $p \mid |Z(G)|$

**Classification**: p-groups의 구조

자세한 내용은 [[p-Group]] 참조

### 2. Burnside's Lemma

**Counting orbits**: Conjugacy classes 사용

자세한 내용은 [[Group Action]] 참조

### 3. Character Theory

**Representations**: Conjugacy classes와 irreducible characters

**One-to-one**: Classes ↔ Irreducible representations (rough)

### 4. Simplicity

**Simple groups**: Small center, few classes

### 5. Computational

**Algorithms**: Class equation으로 group 분석

## 계산 방법

### Conjugacy Classes 찾기

**Step 1**: Generators의 conjugates 계산

**Step 2**: Products의 conjugates (closure)

**Step 3**: Partition into classes

### Centralizer 계산

$$C_G(g) = \{x \in G : xg = gx\}$$

**Method**: Check each element or use structure

### Class Equation 검증

$$\sum_i |\text{cl}(g_i)| = |G|$$

**Check**: 모든 classes cover $G$ exactly once

## 표기법

| 표기 | 의미 |
|------|------|
| $\text{cl}(g)$ or $\mathcal{C}(g)$ | Conjugacy class of $g$ |
| $C_G(g)$ | Centralizer of $g$ |
| $Z(G)$ | Center of $G$ |
| $[G : H]$ | Index of $H$ in $G$ |
| $g \sim h$ | $g, h$ conjugate |

## Common Pitfall^[흔한 실수]

### 1. Conjugacy ≠ Equality

$xgx^{-1}$ might equal $g$, but generally doesn't

Only for $g \in Z(G)$

### 2. Class size divides $|G|$

By Lagrange's theorem ✓

Cannot be arbitrary!

### 3. Center always included

Class equation starts with $|Z(G)|$, not 0

### 4. $C_G(g) \geq Z(G)$

Centralizer contains center!

### 5. Conjugation is NOT homomorphism

$$\phi_x(gh) = xghx^{-1} = (xgx^{-1})(xhx^{-1}) = \phi_x(g)\phi_x(h)$$

Wait, it IS a homomorphism! (Actually automorphism)

Mistake: Confusing map $g \mapsto xgx^{-1}$ (automorphism) with relation "conjugate" (equivalence)

## 응용 예시

### p-Groups

**정리**: $|G| = p^n$ $\Rightarrow$ $p \mid |Z(G)|$

**응용**: Classification, Sylow theorems

### Nilpotent Groups

**Upper central series**: Uses class equation iteratively

자세한 내용은 [[Nilpotent Group]] 참조

### Simple Groups

**No normal subgroups**: Class structure constrained

자세한 내용은 [[Simple Group]] 참조

### Burnside's $p^a q^b$ Theorem

**사용**: Class equation + representation theory

**결과**: Groups of order $p^a q^b$ solvable

자세한 내용은 [[Solvable Group]] 참조

## Symmetric Groups의 Conjugacy

**Cycle type determines class**:

**예**: $(12)(345)$ and $(13)(245)$ conjugate

**Formula**: 

$$|\text{cl}(\sigma)| = \frac{n!}{\prod_i i^{a_i} a_i!}$$

where cycle type has $a_i$ cycles of length $i$

## 관련 개념

- [[Group Action]]: Conjugation action
- [[Orbit-Stabilizer Theorem]]: $|\text{cl}(g)| = [G : C_G(g)]$
- [[Center]]: Central elements
- [[p-Group]]: Non-trivial center
- [[Normal Subgroup]]: Union of conjugacy classes

## 추가 학습 주제

**기초**:
- Conjugacy classes
- Centralizer
- Class equation

**중급**:
- Applications to p-groups
- Burnside's lemma
- Cycle type in $S_n$

**고급**:
- Character theory
- Conjugacy classes in Lie groups
- Rational conjugacy
- Class functions
- Burnside's $p^a q^b$ theorem

