# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Homomorphism]]
- [[Permutation Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Rotman, An Introduction to the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Group Action^[군 작용]

Group $G$가 집합 $X$에 **act**^[작용]한다 $\Leftrightarrow$ 함수가 존재:

$$\cdot : G \times X \to X, \quad (g, x) \mapsto g \cdot x$$

다음을 만족:

### 1. Identity^[항등원]

$$e \cdot x = x \quad \forall x \in X$$

### 2. Compatibility^[양립성]

$$(g_1 g_2) \cdot x = g_1 \cdot (g_2 \cdot x) \quad \forall g_1, g_2 \in G, x \in X$$

### 표기법

- $g \cdot x$ or $gx$ or $g(x)$ or ${}^g x$
- $(X, G)$ or "$G$ acts on $X$"
- "$G$-set" or "$G$-space"

## Left Action vs Right Action

### Left Action^[왼쪽 작용]

위의 정의 (일반적)

$$(g_1 g_2) \cdot x = g_1 \cdot (g_2 \cdot x)$$

### Right Action^[오른쪽 작용]

$$x \cdot g : X \times G \to X$$

$$(x \cdot g_1) \cdot g_2 = x \cdot (g_1 g_2)$$

**관계**: Left action $\leftrightarrow$ Right action via $x \cdot g = g^{-1} \cdot x$

**관례**: 명시하지 않으면 left action

## Homomorphism Perspective

Group action $\Leftrightarrow$ Group homomorphism

$$\phi: G \to \text{Sym}(X)$$

where $\text{Sym}(X)$ = 모든 bijections $X \to X$의 group

**대응**: $\phi(g)(x) = g \cdot x$

**확인**:
- Identity: $\phi(e) = \text{id}_X$
- Compatibility: $\phi(g_1 g_2) = \phi(g_1) \circ \phi(g_2)$ 
## Faithful Action^[충실한 작용]

Action이 **faithful**^[충실]하다 $\Leftrightarrow$ 대응하는 homomorphism이 injective

$$\ker(\phi) = \{g \in G : g \cdot x = x \; \forall x \in X\} = \{e\}$$

**의미**: 서로 다른 $g$들이 서로 다르게 작용

## Transitive Action^[추이적 작용]

Action이 **transitive**^[추이적]이다 $\Leftrightarrow$

$$\forall x, y \in X, \; \exists g \in G : g \cdot x = y$$

**의미**: 모든 점들이 "동등하게" 보임

**Orbit**: 정확히 하나 (전체 $X$)

## Free Action^[자유 작용]

Action이 **free**^[자유]이다 $\Leftrightarrow$

$$g \cdot x = x \Rightarrow g = e \quad \forall x \in X$$

**의미**: Nontrivial element가 어떤 점도 fix하지 않음

**Stabilizer**: 모든 $x$에 대해 $G_x = \{e\}$

---

# <span class="header-examples">Examples</span>

## Example 1: Trivial Action

$$g \cdot x = x \quad \forall g \in G, x \in X$$

**모든 group과 집합**에 대해 정의 가능

**성질**:
- Not faithful (unless $|G| = 1$)
- Transitive (only if $|X| = 1$)
- Not free (unless $|G| = 1$)

## Example 2: Regular Action^[정칙 작용]

$G$ acts on itself by left multiplication:

$$g \cdot h = gh$$

**확인**:
- Identity: $e \cdot h = h$
- Compatibility: $(g_1 g_2) \cdot h = g_1 \cdot (g_2 \cdot h)$ 
**성질**:
- **Faithful**: $g \cdot h = h$ for all $h \Rightarrow g = e$
- **Transitive**: $\forall h_1, h_2 : h_1^{-1}h_2 \cdot h_1 = h_2$
- **Free**: $g \cdot h = h \Rightarrow g = e$ 
**Cayley's Theorem**: 모든 group은 자기 자신의 permutation group에 embedding

## Example 3: Conjugation Action

$G$ acts on itself by conjugation:

$$g \cdot h = ghg^{-1}$$

**Homomorphism**: $\phi: G \to \text{Aut}(G)$ (automorphisms of $G$)

**Kernel**: $\ker(\phi) = Z(G)$ (center)

**성질**:
- Faithful $\Leftrightarrow Z(G) = \{e\}$
- Transitive $\Leftrightarrow$ all elements conjugate (rare!)

**Orbits**: Conjugacy classes^[켤레류]

자세한 내용은 [[Normal Subgroup]] 참조

## Example 4: Coset Action

$H \leq G$, $G$ acts on left cosets $G/H = \{gH : g \in G\}$:

$$g \cdot (xH) = (gx)H$$

**확인**: Well-defined, satisfies axioms

**성질**:
- Always transitive
- Kernel = $\bigcap_{x \in G} xHx^{-1}$ (largest normal subgroup in $H$)
- Faithful $\Leftrightarrow$ no nontrivial normal subgroup contained in $H$

**응용**: Sylow theorems, Index calculations

자세한 내용은 [[Subgroup]] 참조

## Example 5: Symmetric Group on $\{1,2,\ldots,n\}$

$$S_n \text{ acts on } \{1,2,\ldots,n\}$$

$$\sigma \cdot i = \sigma(i)$$

**성질**:
- Faithful
- Transitive
- Not free (unless $n = 1$): $\text{id}$ fixes all

**정의에 의한** action

자세한 내용은 [[Symmetric Group]] 참조

## Example 6: Matrix Group on Vector Space

$$\text{GL}_n(\mathbb{R}) \text{ acts on } \mathbb{R}^n$$

$$A \cdot v = Av \quad \text{(matrix multiplication)}$$

**성질**:
- Faithful
- Transitive on $\mathbb{R}^n \setminus \{0\}$
- Not free: $I$ fixes all

**일반화**: Linear representations

자세한 내용은 [[Linear mapping]] 참조

## Example 7: Automorphism Group

$\text{Aut}(G)$ acts on $G$:

$$\phi \cdot g = \phi(g)$$

**성질**:
- Faithful (by definition)
- Generally not transitive

**Inner automorphisms**: $\text{Inn}(G) = \{\phi_g : h \mapsto ghg^{-1}\}$

## Example 8: Dihedral Group on Regular $n$-gon

$$D_n \text{ acts on vertices of regular } n\text{-gon}$$

**Rotations**: Cyclic permutation

**Reflections**: Reflection across axes

**성질**:
- Faithful
- Transitive
- Not free

자세한 내용은 [[Dihedral Group]] 참조

## Example 9: Galois Group on Roots

Galois group $\text{Gal}(K/F)$ acts on roots of polynomial:

$$\sigma \cdot \alpha = \sigma(\alpha)$$

**응용**: Galois theory의 핵심

자세한 내용은 [[Galois Theory]] 참조

---

# <span class="header-properties">Properties</span>

## Orbit^[궤도]

원소 $x \in X$의 **orbit**^[궤도]:

$$\mathcal{O}_x = G \cdot x = \{g \cdot x : g \in G\}$$

### 성질

1. **Partition**: Orbits partition $X$

$$X = \bigsqcup_{i} \mathcal{O}_{x_i}$$

2. **Equivalence relation**:

$$x \sim y \Leftrightarrow \exists g : g \cdot x = y$$

3. **Orbit size**: $|\mathcal{O}_x| = [G : G_x]$ (Orbit-Stabilizer Theorem)

## Stabilizer^[안정화군]

원소 $x \in X$의 **stabilizer**^[안정화군]:

$$G_x = \text{Stab}_G(x) = \{g \in G : g \cdot x = x\}$$

**Alternative names**: Isotropy group^[등방군], Little group

### 성질

1. $G_x \leq G$ (subgroup)

**증명**:
- Identity: $e \cdot x = x$ $\Rightarrow$ $e \in G_x$
- Closure: $g_1, g_2 \in G_x$ $\Rightarrow$ $(g_1g_2) \cdot x = g_1 \cdot (g_2 \cdot x) = g_1 \cdot x = x$
- Inverse: $g \cdot x = x$ $\Rightarrow$ $x = g^{-1} \cdot (g \cdot x) = g^{-1} \cdot x$ 
2. **Conjugate stabilizers**:

$$G_{g \cdot x} = g G_x g^{-1}$$

**증명**: $h \in G_{g \cdot x} \Leftrightarrow h \cdot (g \cdot x) = g \cdot x \Leftrightarrow (g^{-1}hg) \cdot x = x$ 
## Kernel of Action

$$\ker(\phi) = \{g \in G : g \cdot x = x \; \forall x \in X\} = \bigcap_{x \in X} G_x$$

**성질**:
- $\ker(\phi) \triangleleft G$ (normal subgroup)
- Faithful $\Leftrightarrow$ $\ker(\phi) = \{e\}$

## Fixed Points^[고정점]

집합 $X^g = \{x \in X : g \cdot x = x\}$ = **fixed points**^[고정점] of $g$

**Dual perspective**:
- Stabilizer: $g$를 고정 $\Rightarrow$ $g \in G_x$
- Fixed point: $x$를 고정 $\Rightarrow$ $x \in X^g$

## Orbit Representatives

$X = \bigsqcup_{i \in I} \mathcal{O}_{x_i}$

**Representative system**: $\{x_i : i \in I\}$ with one from each orbit

**Size formula**:

$$|X| = \sum_{i \in I} |\mathcal{O}_{x_i}| = \sum_{i \in I} [G : G_{x_i}]$$

---

# <span class="header-theorem">Theorem</span>

## Orbit-Stabilizer Theorem^[궤도-안정화군 정리]

$G$ acts on $X$, $x \in X$

$$|\mathcal{O}_x| = [G : G_x]$$

**Finite case**:

$$|\mathcal{O}_x| = \frac{|G|}{|G_x|}$$

### 증명

**Bijection**: $G/G_x \to \mathcal{O}_x$

$$\phi: gG_x \mapsto g \cdot x$$

**Well-defined**: $gG_x = hG_x \Leftrightarrow h^{-1}g \in G_x \Leftrightarrow (h^{-1}g) \cdot x = x \Leftrightarrow g \cdot x = h \cdot x$

**Injective**: $g \cdot x = h \cdot x \Rightarrow gG_x = hG_x$

**Surjective**: By definition of orbit 
### 따름정리

1. **Orbit size divides group order** (finite $G$)

$$|\mathcal{O}_x| \mid |G|$$

2. **Counting formula**:

$$|X| = \sum_{\text{orbits}} |\mathcal{O}_i| = \sum_{\text{orbits}} \frac{|G|}{|G_{x_i}|}$$

## Class Equation^[류 방정식]

$G$ acts on itself by conjugation

$$|G| = |Z(G)| + \sum_{i} [G : C_G(x_i)]$$

where sum is over representatives of non-central conjugacy classes

**의미**:
- $Z(G)$ = fixed points (center)
- $[G : C_G(x_i)]$ = orbit sizes of non-central elements

### 응용: $p$-groups

$|G| = p^n$, then $p \mid |G|$

Class equation:

$$p^n = |Z(G)| + \sum_i [G : C_G(x_i)]$$

$p \mid [G : C_G(x_i)]$ for $x_i \notin Z(G)$

$\Rightarrow p \mid |Z(G)|$ $\Rightarrow |Z(G)| \geq p$

**결론**: Non-trivial $p$-group has non-trivial center!

자세한 내용은 [[Nilpotent Group]] 참조

## Burnside's Lemma (Cauchy-Frobenius Lemma)

$G$ acts on finite set $X$

**Number of orbits**:

$$|\text{Orbits}| = \frac{1}{|G|} \sum_{g \in G} |X^g|$$

where $X^g = \{x \in X : g \cdot x = x\}$ (fixed points)

### 증명

Consider pairs $(g, x)$ with $g \cdot x = x$:

$$\sum_{g \in G} |X^g| = \sum_{x \in X} |G_x|$$

$$= \sum_{\text{orbits}} \sum_{x \in \mathcal{O}_i} |G_x| = \sum_{\text{orbits}} \sum_{x \in \mathcal{O}_i} \frac{|G|}{|\mathcal{O}_i|}$$

$$= \sum_{\text{orbits}} |\mathcal{O}_i| \cdot \frac{|G|}{|\mathcal{O}_i|} = \sum_{\text{orbits}} |G| = |G| \cdot |\text{Orbits}|$$

**따라서**: $|\text{Orbits}| = \frac{1}{|G|} \sum_{g \in G} |X^g|$ 
### 응용: Combinatorics

**Necklace counting**: Rotating necklace로 distinct한 개수

**Graph coloring**: Symmetry 고려한 coloring 수

**Pólya enumeration theorem**: 더 일반적 버전

## Cayley's Theorem

**정리**: 모든 group $G$는 어떤 symmetric group의 subgroup과 isomorphic

$$G \cong H \leq \text{Sym}(G)$$

### 증명

Regular action: $G$ acts on itself

$$\phi: G \to \text{Sym}(G), \quad \phi(g)(h) = gh$$

**Homomorphism**: 명백

**Injective**: $\phi(g) = \text{id} \Rightarrow gh = h$ for all $h \Rightarrow g = e$

**따라서**: $G \cong \phi(G) \leq \text{Sym}(G)$ 
### 의미

**Every finite group of order $n$** embeds in $S_n$

하지만: 보통 더 작은 $S_m$ ($m < n$)에도 embedding 가능

**예**: $\mathbb{Z}/3\mathbb{Z} \hookrightarrow S_3$ (regular action)

But also: $\mathbb{Z}/3\mathbb{Z} \cong \langle (123) \rangle \leq S_3$ (같은 것)

자세한 내용은 [[Permutation Group]] 참조

## Sylow Theorems via Group Actions

**Sylow theorems**: $p$-subgroups의 existence, conjugacy

**증명 방법**: Group action 사용
- $G$ acts on Sylow $p$-subgroups by conjugation
- Orbit-stabilizer theorem
- Counting arguments

자세한 내용은 [[Subgroup]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Group Action = "대칭성을 명시적으로 구현"**

### 메타포: 변환

**Group**: 추상적 대칭성

**Action**: 구체적으로 무언가를 변환

**예**: 
- $D_4$ (추상) → 정사각형 회전/반사 (구체)
- $S_3$ (추상) → 세 점 permutation (구체)

### 메타포: 배우와 무대

**Group** $G$: 배우들

**Set** $X$: 무대

**Action**: 배우들이 무대에서 움직이는 방식

## 왜 중요한가?

### 1. 추상 → 구체

추상적 group을 구체적 permutations로 실현

**Cayley's theorem**: 모든 group은 permutation group

### 2. Counting

**Burnside's lemma**: 대칭성 고려한 counting

**응용**: Combinatorics, Chemistry (molecular symmetry)

### 3. Structure Theory

**Class equation**: Center, Conjugacy classes 분석

**Sylow theorems**: $p$-subgroups 연구

### 4. Representation Theory

**Linear representations** = Actions on vector spaces

**Character theory**: Representation 분석

## Action Types Summary

| Type | Meaning | Example |
|------|---------|---------|
| **Transitive** | One orbit | $S_n$ on $\{1,\ldots,n\}$ |
| **Faithful** | Injective homomorphism | Regular action |
| **Free** | No fixed points | $\mathbb{Z}$ on $\mathbb{R}$ by translation |
| **Trivial** | Everything fixed | $g \cdot x = x$ |

## Orbit Types

### Single Orbit (Transitive)

$$X = \mathcal{O}_x \text{ for any } x$$

**예**: $S_n$ on $\{1,\ldots,n\}$

### Multiple Orbits

$$X = \mathcal{O}_{x_1} \sqcup \mathcal{O}_{x_2} \sqcup \cdots$$

**예**: $G$ on itself by conjugation (conjugacy classes)

## Stabilizer vs Fixed Point

**Dual concepts**:

| | **Stabilizer $G_x$** | **Fixed Points $X^g$** |
|---|---|---|
| **Fix** | Which $g$ fix $x$? | Which $x$ fixed by $g$? |
| **Type** | Subgroup of $G$ | Subset of $X$ |
| **Size** | $\|G_x\| = \|G\|/\|\mathcal{O}_x\|$ | $\|X^g\|$ (no formula) |

## Orbit-Stabilizer in Practice

**Problem**: Compute orbit size

**Method**: 
1. Find stabilizer $G_x$
2. Apply: $|\mathcal{O}_x| = |G|/|G_x|$

**예**: $S_4$ acts on unordered pairs

Stabilizer of $\{1,2\}$: $S_{\{1,2\}} \times S_{\{3,4\}} \cong S_2 \times S_2$ (order 4)

Orbit size: $|S_4|/4 = 24/4 = 6$ (consistent: $\binom{4}{2} = 6$)

## Class Equation Applications

### $p$-groups

$|G| = p^n \Rightarrow |Z(G)| \geq p$

**증명**: Class equation + divisibility

### Cauchy's Theorem

$p \mid |G| \Rightarrow \exists g$ with $|g| = p$

**증명**: Class equation으로 원소 개수 count

## Burnside's Lemma in Practice

**Necklace problem**: 3 beads, 2 colors, rotation symmetry

$G = \mathbb{Z}/3\mathbb{Z}$ acts on $\{0,1\}^3$

- $g = \text{id}$: $|X^g| = 2^3 = 8$
- $g = $ rotation by $120°$: $|X^g| = 2$ (all same color)
- $g = $ rotation by $240°$: $|X^g| = 2$

**Number of orbits**: $\frac{1}{3}(8 + 2 + 2) = 4$

## 표기법

| 표기 | 의미 |
|------|------|
| $g \cdot x$ | Action of $g$ on $x$ |
| $\mathcal{O}_x$ or $G \cdot x$ | Orbit of $x$ |
| $G_x$ or $\text{Stab}_G(x)$ | Stabilizer of $x$ |
| $X^g$ | Fixed points of $g$ |
| $G/H$ | Left cosets (set, not quotient group) |
| $\text{Sym}(X)$ | Symmetric group on $X$ |

## Common Pitfall^[흔한 실수]

### 1. Coset notation $G/H$

$H$ normal 아니어도 $G/H$ = set of cosets 사용 (quotient group 아님!)

### 2. Orbit size formula

$|\mathcal{O}_x| = [G : G_x]$ (not $|G_x|$!)

### 3. Burnside's lemma

Average over **group elements** (not orbits or $X$)

### 4. Faithful ≠ Free

- **Faithful**: Different $g$ act differently
- **Free**: No $g \neq e$ fixes any point

$S_n$ on $\{1,\ldots,n\}$: Faithful , Free ✗

### 5. Conjugation is action

$g \cdot h = ghg^{-1}$ (not $gh$!)

## 응용 분야

**Combinatorics**:
- Pólya enumeration
- Graph automorphisms
- Symmetry in counting

**Geometry**:
- Symmetry groups
- Lie groups on manifolds
- Isometries

**Physics**:
- Gauge theory
- Particle physics (representations)
- Crystal symmetry

**Chemistry**:
- Molecular symmetry
- Point groups

**Number Theory**:
- Galois theory
- Modular forms
- Algebraic geometry

자세한 내용은 [[Galois Theory]] 참조

## 역사적 배경

**1870s**: Jordan, Frobenius - Permutation groups

**1890s**: Burnside - Counting lemma

**1920s**: Schur - Representation theory

**현대**: Fundamental tool in all algebra

## 관련 개념

- [[Permutation Group]]: Natural actions
- [[Symmetric Group]]: Cayley's theorem
- [[Subgroup]]: Stabilizers, Normalizers
- [[Normal Subgroup]]: Conjugation action
- [[Galois Theory]]: Galois group actions
- [[Homomorphism]]: Action as homomorphism

## 추가 학습 주제

**기초**:
- Orbit-stabilizer theorem
- Cayley's theorem
- Conjugacy classes

**중급**:
- Burnside's lemma
- Pólya enumeration
- Semidirect products

**고급**:
- Representation theory
- Character theory
- $G$-sets and category theory

