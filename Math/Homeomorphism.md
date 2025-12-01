# <span class="header-prerequisite">Prerequisite</span>
- [[Topology]]
- [[Open Set]]
- [[Continuous Function]]
- [[One-to-On, Onto]]

# <span class="header-reference">Reference</span>
- Munkres, Topology
- Hatcher, Algebraic Topology
- Lee, Introduction to Topological Manifolds
- Willard, General Topology

---

# <span class="header-definition">Definition</span>

## Homeomorphism^[위상동형사상]

Topological spaces^[위상공간] $(X, \tau_X)$, $(Y, \tau_Y)$ 사이의 함수 $f: X \to Y$가 **homeomorphism^[위상동형사상]**이다 $\Leftrightarrow$

1. $f$는 **bijective^[전단사]** (injective + surjective)
2. $f$는 **continuous^[연속]**
3. $f^{-1}: Y \to X$도 **continuous^[연속]**

**표기**: $f: X \xrightarrow{\cong} Y$ 또는 $f: X \overset{\sim}{\to} Y$

## Homeomorphic Spaces^[위상동형 공간]

두 topological space $X$, $Y$가 **homeomorphic^[위상동형]**이다 $\Leftrightarrow$

$$\exists \text{ homeomorphism } f: X \to Y$$

**표기**: $X \cong Y$ 또는 $X \approx Y$

**의미**: "위상적으로 같음", "topologically indistinguishable^[위상적으로 구별 불가능]"

## Alternative Characterizations^[동등한 특징화]

다음은 모두 동등:

1. $f: X \to Y$는 homeomorphism
2. $f$는 continuous bijection이고 $f^{-1}$도 continuous
3. $f$는 bijection이고 모든 open set $U \subseteq X$에 대해 $f(U)$가 open in $Y$
4. $f$는 bijection이고 모든 closed set $C \subseteq X$에 대해 $f(C)$가 closed in $Y$
5. $f$는 continuous open map^[연속 열린 사상]이고 bijective
6. $f$는 continuous closed map^[연속 닫힌 사상]이고 bijective

---

# <span class="header-examples">Examples</span>

## Example 1: Open Interval and Real Line

$$(0, 1) \cong \mathbb{R}$$

**Homeomorphism**: $f: (0, 1) \to \mathbb{R}$, $f(x) = \tan\left(\pi\left(x - \frac{1}{2}\right)\right)$

또는: $f(x) = \frac{2x - 1}{x(1-x)}$

**증명**:
- $f$는 bijective ✓
- $f$는 continuous ✓
- $f^{-1}$도 continuous ✓

**의미**: 유계 구간과 전체 실수선이 위상적으로 같음!

## Example 2: Any Two Open Intervals

$$(a, b) \cong (c, d)$$

**Homeomorphism**: Linear map

$$f(x) = c + \frac{d - c}{b - a}(x - a)$$

**일반화**: 모든 open interval은 위상동형

## Example 3: Circle and Square

**Unit circle** $S^1 = \{(x, y) \in \mathbb{R}^2 : x^2 + y^2 = 1\}$

**Unit square boundary**: $\partial([0,1]^2)$

$$S^1 \cong \partial([0,1]^2)$$

**직관**: 고무줄을 늘려서 원을 사각형으로 (또는 그 반대)

## Example 4: Coffee Cup and Donut (Torus)

$$\text{Coffee cup} \cong \text{Donut (torus)}$$

**의미**: "Topology는 coffee를 donut으로 변형 가능"

**핵심**: 둘 다 "hole 1개" (genus = 1)

**비유**: "A topologist cannot distinguish a coffee cup from a donut"

## Example 5: $\mathbb{R}^n$ and Open Unit Ball

$$\mathbb{R}^n \cong B^n = \{x \in \mathbb{R}^n : \|x\| < 1\}$$

**Homeomorphism**: $f(x) = \frac{x}{1 + \|x\|}$

**Inverse**: $f^{-1}(y) = \frac{y}{1 - \|y\|}$

## Example 6: Cylinder and Annulus

**Open cylinder**: $S^1 \times (0, 1)$

**Open annulus**: $\{(x, y) \in \mathbb{R}^2 : 1 < x^2 + y^2 < 4\}$

$$S^1 \times (0, 1) \cong \{(x, y) : 1 < x^2 + y^2 < 4\}$$

## Example 7: Möbius Strip (자명하지 않음)

**Möbius strip** $\not\cong$ **Cylinder** $S^1 \times [0, 1]$

**이유**: Möbius strip은 non-orientable^[방향불가능], Cylinder는 orientable^[방향가능]

**의미**: Homeomorphism은 orientability를 보존

## Example 8: Graph of Continuous Function

$f: \mathbb{R} \to \mathbb{R}$ continuous이면:

**Graph**: $\text{Graph}(f) = \{(x, f(x)) : x \in \mathbb{R}\}$

$$\mathbb{R} \cong \text{Graph}(f)$$

**Homeomorphism**: $\phi(x) = (x, f(x))$

---

# <span class="header-theorem">Theorems</span>

## Homeomorphism is Equivalence Relation

**정리**: $\cong$ (homeomorphic)은 equivalence relation^[동치 관계]

**증명**:

**1. Reflexive^[반사성]**: $X \cong X$ (identity map)

**2. Symmetric^[대칭성]**: $X \cong Y$ $\Rightarrow$ $Y \cong X$ (inverse map)

**3. Transitive^[추이성]**: $X \cong Y$, $Y \cong Z$ $\Rightarrow$ $X \cong Z$ (composition)

**의미**: Topological spaces를 equivalence class로 분류 가능

## Topological Invariants^[위상 불변량]

**정리**: Homeomorphism은 **topological properties^[위상적 성질]**을 보존

$X \cong Y$이면:

1. **Compactness^[컴팩트성]**: $X$ compact $\Leftrightarrow$ $Y$ compact
2. **Connectedness^[연결성]**: $X$ connected $\Leftrightarrow$ $Y$ connected
3. **Hausdorff**: $X$ Hausdorff $\Leftrightarrow$ $Y$ Hausdorff
4. **Separability**: $X$ separable $\Leftrightarrow$ $Y$ separable
5. **Second-countability**: $X$ second-countable $\Leftrightarrow$ $Y$ second-countable
6. **Metrizability**: $X$ metrizable $\Leftrightarrow$ $Y$ metrizable

**응용**: Topological invariants로 "not homeomorphic" 증명 가능

## Continuous Bijection on Compact Hausdorff

**정리**: $X$ compact, $Y$ Hausdorff, $f: X \to Y$ continuous bijection이면:

$$f \text{ is homeomorphism}$$

**증명**: Continuous bijection from compact to Hausdorff is closed map

따라서 $f$는 closed map이고 bijective $\Rightarrow$ $f^{-1}$ continuous ✓

**중요성**: Compact Hausdorff 공간에서는 inverse의 continuity 자동!

## Open Mapping Theorem (General Topology)

**정리**: $f: X \to Y$ continuous bijection이고 $f$가 **open map^[열린 사상]**이면:

$$f \text{ is homeomorphism}$$

**증명**: Open bijection $\Rightarrow$ $f^{-1}$ continuous ✓

**Dually**: Closed map + bijection $\Rightarrow$ homeomorphism

## Local Homeomorphism^[국소 위상동형사상]

함수 $f: X \to Y$가 **local homeomorphism^[국소 위상동형사상]**이다 $\Leftrightarrow$

$$\forall x \in X, \exists U \ni x \text{ (open)}, \exists V \subseteq Y \text{ (open)}: f|_U: U \to V \text{ is homeomorphism}$$

**예**:
- Covering maps^[덮개 사상] (e.g., $\mathbb{R} \to S^1$, $t \mapsto e^{2\pi i t}$)
- Quotient maps (locally)

**주의**: Local homeomorphism $\not\Rightarrow$ homeomorphism

---

# <span class="header-examples">Non-Examples</span>

## Example 1: Continuous Bijection Not Homeomorphism

**$X = [0, 1)$** with subspace topology from $\mathbb{R}$

**$Y = S^1$** (unit circle)

**함수**: $f: [0, 1) \to S^1$, $f(t) = e^{2\pi i t}$

**Check**:
- $f$ is bijective ✓
- $f$ is continuous ✓
- $f^{-1}$ is **NOT continuous** ✗

**이유**: $f^{-1}([0, 1/2))$ is not open in $[0, 1)$

**핵심**: $[0, 1)$ is not compact, $S^1$ is compact

## Example 2: $(0, 1]$ and $S^1$

$$(0, 1] \not\cong S^1$$

**이유**: 
- $S^1$은 compact
- $(0, 1]$은 not compact (in usual topology)
- Homeomorphism preserves compactness

## Example 3: $\mathbb{R}$ and $\mathbb{R}^2$

$$\mathbb{R} \not\cong \mathbb{R}^2$$

**증명**: Removing a point
- $\mathbb{R} \setminus \{0\}$는 disconnected (두 component)
- $\mathbb{R}^2 \setminus \{p\}$는 connected (any point $p$)

**Topological invariant**: "한 점 제거 후의 connectedness"

## Example 4: Any Interval and Circle

$$[0, 1] \not\cong S^1$$

**이유**: 
- $[0, 1]$에서 두 점 제거: disconnected (최대 3 components)
- $S^1$에서 두 점 제거: still connected

## Example 5: Different Genus

**Torus** (genus 1) $\not\cong$ **2-hole torus** (genus 2)

**Invariant**: Genus (number of holes)

**일반화**: Surfaces classified by genus and orientability

## Example 6: Discrete vs Indiscrete

$X = \{a, b\}$ with:
- **Discrete topology**: $\tau_1 = \{\emptyset, \{a\}, \{b\}, \{a, b\}\}$
- **Indiscrete topology**: $\tau_2 = \{\emptyset, \{a, b\}\}$

$$(X, \tau_1) \not\cong (X, \tau_2)$$

**이유**: Identity map $\text{id}: (X, \tau_1) \to (X, \tau_2)$는 continuous이지만, $\text{id}^{-1} = \text{id}: (X, \tau_2) \to (X, \tau_1)$는 not continuous

---

# <span class="header-properties">Properties</span>

## Composition of Homeomorphisms

**정리**: $f: X \to Y$, $g: Y \to Z$ homeomorphisms이면:

$$g \circ f: X \to Z \text{ is homeomorphism}$$

**증명**:
- $(g \circ f)^{-1} = f^{-1} \circ g^{-1}$ (bijection)
- Composition of continuous maps is continuous ✓

## Restriction to Subspaces

**정리**: $f: X \to Y$ homeomorphism, $A \subseteq X$이면:

$$f|_A: A \to f(A) \text{ is homeomorphism}$$

(with subspace topologies)

## Product of Homeomorphisms

**정리**: $f: X_1 \to Y_1$, $g: X_2 \to Y_2$ homeomorphisms이면:

$$f \times g: X_1 \times X_2 \to Y_1 \times Y_2 \text{ is homeomorphism}$$

where $(f \times g)(x, y) = (f(x), g(y))$

## Quotient by Homeomorphism

**정리**: $f: X \to Y$ homeomorphism, $\sim$ equivalence relation on $X$

Define $\sim'$ on $Y$ by: $y_1 \sim' y_2$ $\Leftrightarrow$ $f^{-1}(y_1) \sim f^{-1}(y_2)$

Then: $X/\sim \; \cong Y/\sim'$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Homeomorphism**: "위상을 보존하는 변형"

**메타포**: "고무 시트 변형" (rubber sheet geometry)
- 늘리기, 구부리기, 비틀기 허용 ✓
- 찢기, 붙이기, 구멍 뚫기 금지 ✗

**핵심 아이디어**: "Shape는 바뀌어도 topological properties는 보존"

## Homeomorphism vs Other Morphisms

| Concept | Structure | Bijection? | Preserves? |
|---------|-----------|------------|------------|
| **Homeomorphism** | Topology | ✓ | Topological properties |
| **Isomorphism** (algebra) | Group/Ring/Field | ✓ | Algebraic structure |
| **Isometry** | Metric space | ✓ | Distance |
| **Diffeomorphism** | Smooth manifold | ✓ | Smooth structure |
| **Linear isomorphism** | Vector space | ✓ | Linear structure |
| **Continuous map** | Topology | ✗ | Preimage of open sets |

**계층**:
$$\text{Isometry} \Rightarrow \text{Homeomorphism} \Rightarrow \text{Continuous}$$

## Why Inverse Continuity Matters

**Continuous bijection $\neq$ Homeomorphism!**

**반례**: $f: [0, 1) \to S^1$, $f(t) = e^{2\pi i t}$

**이유**:
- $f$ preserves "forward" topology
- But $f^{-1}$ breaks topology (open sets $\not\to$ open sets)

**의미**: Homeomorphism requires **both directions** preserve topology

## Classification of Spaces

**목표**: Classify topological spaces up to homeomorphism

**도구**: Topological invariants
- Compactness
- Connectedness
- Homotopy groups
- Homology groups
- Fundamental group

**예**: Surfaces classified by:
- Genus (number of holes)
- Orientability
- Boundary components

## 역사적 배경

**Topology의 탄생** (19-20세기):
- **Leonhard Euler** (1736): Seven Bridges of Königsberg
- **August Möbius** (1858): Möbius strip
- **Henri Poincaré** (1895): Analysis Situs (Algebraic Topology)
- **Felix Hausdorff** (1914): Grundzüge der Mengenlehre

**Homeomorphism**:
- Greek: "homoios" (similar) + "morphe" (form/shape)
- "Same shape" in topological sense

## 응용 분야

### 1. Algebraic Topology^[대수적 위상수학]

**Fundamental group^[기본군]**: $\pi_1(X)$

$X \cong Y$ $\Rightarrow$ $\pi_1(X) \cong \pi_1(Y)$ (as groups)

**Homology groups^[호몰로지군]**: $H_n(X)$

Homeomorphism invariant

자세한 내용은 [[Algebraic Topology]] 참조

### 2. Differential Topology^[미분위상수학]

**Smooth manifolds^[매끄러운 다양체]**

Homeomorphic $\not\Rightarrow$ Diffeomorphic

**예**: Exotic $\mathbb{R}^4$ (homeomorphic but not diffeomorphic to standard $\mathbb{R}^4$)

### 3. Knot Theory^[매듭 이론]

**Knots**: Embeddings $S^1 \hookrightarrow \mathbb{R}^3$ up to ambient isotopy

**Classification**: Knot invariants (polynomial invariants)

### 4. Dynamical Systems^[역학계]

**Phase space**: Homeomorphic spaces have similar dynamics

**Topological conjugacy**: Homeomorphism preserving orbits

### 5. Data Analysis^[데이터 분석]

**Topological Data Analysis (TDA)**:
- Persistent homology
- Shape of data
- Clustering

### 6. Computer Graphics^[컴퓨터 그래픽스]

**Mesh deformation**: Homeomorphic transformations

**Texture mapping**: Homeomorphism from 2D to surface

## Common Pitfalls^[흔한 실수]

### 1. Continuous Bijection ≠ Homeomorphism

✗ "Continuous + bijective = homeomorphism"?

✓ **Inverse의 continuity 필요!**

### 2. Metric Properties

✗ Homeomorphism preserves distance?

✓ **NO!** Only topological properties (boundedness도 보존 안 됨)

**예**: $(0, 1) \cong \mathbb{R}$ (bounded $\not\leftrightarrow$ unbounded)

### 3. Cardinality ≠ Homeomorphism

✗ Same cardinality $\Rightarrow$ homeomorphic?

✓ **NO!** Discrete vs indiscrete topology on same set

### 4. Homotopy ≠ Homeomorphism

**Homotopy equivalence** $\not\Leftrightarrow$ **Homeomorphism**

**예**: Point $\simeq$ $\mathbb{R}^n$ (homotopy equivalent) but not homeomorphic

### 5. Open Map

✗ Continuous open map = homeomorphism?

✓ **Bijective** + open map = homeomorphism

**반례**: Projection $\mathbb{R}^2 \to \mathbb{R}$ is open but not bijective

## 관련 개념

### Topology

- [[Topology]]: Topological space 정의
- [[Open Set]]: Topology의 기본 개념
- [[Continuous Function]]: Continuity 정의
- [[Compact Set]]: Compactness (topological invariant)
- [[Connected Space]]: Connectedness (topological invariant)

### Related Morphisms

- [[Isomorphism]]: Algebraic structures
- [[Diffeomorphism]]: Smooth manifolds
- [[Homotopy Equivalence]]: Weaker than homeomorphism
- [[Covering Space]]: Local homeomorphism

### Advanced Topics

- [[Fundamental Group]]: Topological invariant
- [[Homology]]: Algebraic topology
- [[Manifold]]: Locally homeomorphic to $\mathbb{R}^n$
- [[Quotient Topology]]: Quotient by equivalence relation

## Homeomorphism Testing

**How to prove $X \cong Y$?**

1. **Construct explicit homeomorphism** $f: X \to Y$
2. **Verify**:
   - Bijective (injective + surjective)
   - Continuous
   - Inverse continuous

**How to prove $X \not\cong Y$?**

1. **Find topological invariant** that differs:
   - Compactness
   - Connectedness
   - Cardinality of path components
   - Fundamental group
   - Homology groups

2. **Check specific properties**:
   - Remove points and check connectedness
   - Cut spaces and count components
   - Compute Euler characteristic

## Summary of Key Points

**Definition**: Continuous bijection with continuous inverse

**Equivalence relation**: Reflexive, symmetric, transitive

**Invariants**: Compactness, connectedness, Hausdorff, etc.

**Not preserved**: Distance, boundedness, diameter

**Special case**: Compact Hausdorff에서 continuous bijection $\Rightarrow$ homeomorphism

**Classification**: Topological spaces up to homeomorphism

**Philosophy**: "Topology studies properties preserved under continuous deformation"

