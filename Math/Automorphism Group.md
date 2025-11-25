# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Isomorphism]]
- [[Homomorphism]]
- [[Normal Subgroup]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups
- Robinson, A Course in the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Automorphism^[자기동형]

**Automorphism**^[자기동형] of group $G$:

$$\phi: G \to G \text{ isomorphism}$$

**의미**: Group의 자기 자신으로의 isomorphism

**성질**:
- Bijective
- Preserves group operation: $\phi(gh) = \phi(g)\phi(h)$

자세한 내용은 [[Isomorphism]] 참조

## Automorphism Group^[자기동형군]

**Automorphism group**^[자기동형군] $\text{Aut}(G)$:

$$\text{Aut}(G) = \{\phi: G \to G \mid \phi \text{ automorphism}\}$$

**Group operation**: Composition $\circ$

$$(\phi \circ \psi)(g) = \phi(\psi(g))$$

**Identity**: $\text{id}_G$

**Inverse**: $\phi^{-1}$ (exists since bijective)

## Inner Automorphism^[내부 자기동형]

**Inner automorphism**^[내부 자기동형] by $g \in G$:

$$\phi_g: G \to G, \quad \phi_g(h) = ghg^{-1}$$

**의미**: Conjugation by $g$

**표기**: Often write $c_g$ or $\text{Inn}_g$

### Inner Automorphism Group

$$\text{Inn}(G) = \{\phi_g : g \in G\} \leq \text{Aut}(G)$$

**정리**: $\text{Inn}(G) \triangleleft \text{Aut}(G)$ (normal subgroup!)

자세한 내용은 [[Normal Subgroup]] 참조

## Outer Automorphism Group^[외부 자기동형군]

**Outer automorphism group**^[외부 자기동형군]:

$$\text{Out}(G) = \text{Aut}(G) / \text{Inn}(G)$$

**의미**: "Non-inner" automorphisms의 group

**예**: $\text{Out}(S_n) = \{e\}$ for $n \neq 6$, but $\text{Out}(S_6) \cong \mathbb{Z}/2\mathbb{Z}$

자세한 내용은 [[Quotient Group, Factor Group]] 참조

---

# <span class="header-properties">Properties</span>

## $\text{Aut}(G)$ is a Group

**Associativity**: Composition associative ✓

**Identity**: $\text{id}_G \in \text{Aut}(G)$ ✓

**Inverse**: $\phi^{-1} \in \text{Aut}(G)$ if $\phi \in \text{Aut}(G)$ ✓

**Closure**: $\phi, \psi \in \text{Aut}(G)$ $\Rightarrow$ $\phi \circ \psi \in \text{Aut}(G)$ ✓

## $\text{Inn}(G) \cong G/Z(G)$

**정리**: Inner automorphism group은

$$\text{Inn}(G) \cong G / Z(G)$$

**증명**: Define $\phi: G \to \text{Inn}(G)$ by $g \mapsto \phi_g$

- $\phi$ surjective (정의에 의해)
- $\ker(\phi) = Z(G)$ (center!)
- By First Isomorphism Theorem: $G/Z(G) \cong \text{Inn}(G)$ ✓

자세한 내용은 [[Center]], [[Isomorphism Theorem]] 참조

## $\text{Inn}(G) \triangleleft \text{Aut}(G)$

**정리**: $\text{Inn}(G)$는 $\text{Aut}(G)$의 normal subgroup

**증명**: For $\phi \in \text{Aut}(G)$ and $\phi_g \in \text{Inn}(G)$,

$$\phi \circ \phi_g \circ \phi^{-1} = \phi_{\phi(g)} \in \text{Inn}(G)$$

따라서 $\phi \text{Inn}(G) \phi^{-1} = \text{Inn}(G)$ ✓

## Characteristic Subgroups

**정의**: $H$ is **characteristic**^[특성적]in $G$ if

$$\phi(H) = H \quad \text{for all } \phi \in \text{Aut}(G)$$

**정리**: Characteristic $\Rightarrow$ Normal

**예**:
- $Z(G)$ characteristic ✓
- $[G,G]$ characteristic ✓
- $G^p = \{g^p : g \in G\}$ characteristic ✓

자세한 내용은 [[Center]], [[Commutator Subgroup]] 참조

## Automorphisms Preserve Structure

For $\phi \in \text{Aut}(G)$:

**Order**: $|\phi(g)| = |g|$

**Center**: $\phi(Z(G)) = Z(G)$

**Commutator**: $\phi([g,h]) = [\phi(g), \phi(h)]$

**Subgroups**: $\phi(H) \leq G$ if $H \leq G$ (but $\phi(H) \neq H$ generally)

---

# <span class="header-examples">Examples</span>

## Example 1: Cyclic Groups

**$\mathbb{Z}/n\mathbb{Z}$**:

$$\text{Aut}(\mathbb{Z}/n\mathbb{Z}) \cong (\mathbb{Z}/n\mathbb{Z})^{\times}$$

**Units group**: $\{k : \gcd(k,n) = 1\}$

**Order**: $|\text{Aut}(\mathbb{Z}/n\mathbb{Z})| = \phi(n)$ (Euler's totient)

**예**: $\text{Aut}(\mathbb{Z}/8\mathbb{Z}) \cong (\mathbb{Z}/2\mathbb{Z})^2$ (order 4)

자세한 내용은 [[Cyclic Group]], [[Euler's theorem]] 참조

## Example 2: $\mathbb{Z}$

$$\text{Aut}(\mathbb{Z}) \cong \mathbb{Z}/2\mathbb{Z}$$

**Two automorphisms**:
- $\phi(n) = n$ (identity)
- $\phi(n) = -n$ (negation)

**이유**: Generator $1$ must map to $\pm 1$

## Example 3: Klein Four-Group

$$V_4 = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$$

$$\text{Aut}(V_4) \cong S_3$$

**설명**: 3 non-identity elements can be permuted

**Order**: $|\text{Aut}(V_4)| = 6$

## Example 4: Dihedral Group $D_n$

**$D_3 \cong S_3$**:

$$\text{Aut}(D_3) \cong \text{Aut}(S_3) \cong S_3$$

**General $D_n$ (n≥3)**:

$$|\text{Aut}(D_n)| = n \phi(n)/2 \quad \text{(if } n \text{ odd)}$$

자세한 내용은 [[Dihedral Group]] 참조

## Example 5: Symmetric Group $S_n$

**$n \neq 6$**:

$$\text{Out}(S_n) = \{e\}$$

**의미**: All automorphisms are inner!

**$n = 6$**: Exceptional case!

$$\text{Out}(S_6) \cong \mathbb{Z}/2\mathbb{Z}$$

**특별한 outer automorphism** 존재

자세한 내용은 [[Symmetric Group]] 참조

## Example 6: Quaternion Group $Q_8$

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

$$\text{Inn}(Q_8) \cong Q_8 / Z(Q_8) \cong V_4$$

$$|\text{Aut}(Q_8)| = 24 = S_4$$

**설명**: Permutations of $\{i, j, k\}$ with sign changes

## Example 7: p-Groups

**Elementary abelian**: $(\mathbb{Z}/p\mathbb{Z})^n$

$$\text{Aut}((\mathbb{Z}/p\mathbb{Z})^n) \cong \text{GL}_n(\mathbb{F}_p)$$

**General linear group** over field $\mathbb{F}_p$

**Order**: $(p^n - 1)(p^n - p) \cdots (p^n - p^{n-1})$

자세한 내용은 [[p-Group]] 참조

---

# <span class="header-theorem">Theorem</span>

## $\text{Inn}(G) \cong G/Z(G)$

**정리**: 

$$\text{Inn}(G) \cong G / Z(G)$$

**증명**: Map $\phi: G \to \text{Inn}(G)$ by $g \mapsto \phi_g$

$$\ker(\phi) = \{g : \phi_g = \text{id}\} = \{g : ghg^{-1} = h \text{ for all } h\} = Z(G)$$

By First Isomorphism Theorem ✓

자세한 내용은 [[Isomorphism Theorem]] 참조

## Abelian Groups

**정리**: If $G$ abelian,

$$\text{Inn}(G) = \{e\}$$

$$\text{Out}(G) = \text{Aut}(G)$$

**증명**: $Z(G) = G$ $\Rightarrow$ $\text{Inn}(G) \cong G/G = \{e\}$ ✓

자세한 내용은 [[Abelian Group]] 참조

## Simple Groups

**정리**: If $G$ simple, either:
- $\text{Inn}(G) = \{e\}$ (즉, $G$ abelian, $G \cong \mathbb{Z}/p\mathbb{Z}$)
- $\text{Inn}(G) = \text{Aut}(G)$ (즉, $\text{Out}(G) = \{e\}$, "complete")

**예**: $A_5$ is complete (all automorphisms inner)

자세한 내용은 [[Simple Group]] 참조

## Characteristic Subgroups

**정리**: If $H$ characteristic in $K$ and $K \triangleleft G$,

$$\Rightarrow H \triangleleft G$$

**증명**: For $g \in G$, conjugation $\phi_g$ is automorphism of $K$

$\Rightarrow$ $\phi_g(H) = H$ $\Rightarrow$ $gHg^{-1} = H$ ✓

## Holomorph

**정의**: **Holomorph**^[완전]of $G$:

$$\text{Hol}(G) = G \rtimes \text{Aut}(G)$$

**의미**: Semidirect product of $G$ and $\text{Aut}(G)$

자세한 내용은 [[Semidirect Product]] 참조

## Automorphism Tower

**정의**: Sequence

$$G, \text{Aut}(G), \text{Aut}(\text{Aut}(G)), \ldots$$

**Terminates** if eventually $G \cong \text{Aut}(G)$ (complete group)

**예**: $S_n$ (n≠6), $A_n$ (n≥5, n≠6) terminate quickly

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Automorphism = "대칭"**

### 메타포: 기하학적 대칭

**Group**: 기하학적 object

**Automorphisms**: 대칭 변환들

**Inner**: "자연스러운" 대칭 (내부에서 발생)

**Outer**: "특별한" 대칭 (외부 구조 필요)

**예**: 정육면체
- Inner automorphisms: 중심 고정 회전
- Outer: 특별한 대칭 (일반적으로 없음)

### 메타포: 재배치

**Automorphism**: 원소들을 재배치하되 구조 보존

**Inner**: Group 원소로 재배치 (conjugation)

**Outer**: 다른 방식으로 재배치

## 왜 중요한가?

### 1. Symmetry

**Automorphisms**: Group의 대칭성 측정

**$\text{Aut}(G)$**: "How symmetric is $G$?"

### 2. Structure

**Invariants**: Automorphism으로 보존되는 것들

**Characteristic subgroups**: 특별히 중요

### 3. Classification

**Simple groups**: $\text{Out}(G)$ 연구

**Sporadic groups**: Exceptional outer automorphisms

### 4. Galois Theory

**Field automorphisms**: Galois group의 기초

**응용**: Polynomial solvability

자세한 내용은 [[Galois Theory]] 참조

### 5. Representation Theory

**Automorphisms**: 표현들 사이 관계

**Equivalence**: Automorphism으로 연결

## Inner vs Outer

| | **Inner** | **Outer** |
|---|---|---|
| **정의** | Conjugation $\phi_g$ | Cosets in $\text{Aut}(G)/\text{Inn}(G)$ |
| **항상 존재** | Yes (적어도 identity) | Not necessarily |
| **개수** | $|G/Z(G)|$ | $|\text{Aut}(G)|/|G/Z(G)|$ |
| **예** | 모든 group | $S_6$ has nontrivial outer |

**직관**: Inner는 "내재적", Outer는 "예외적"

## 계산 방법

### $\text{Aut}(G)$ 계산

**Step 1**: Generators 찾기 (if finitely generated)

**Step 2**: Generator를 어디로 보낼 수 있는지 결정

**Step 3**: Verify 각 map이 homomorphism

**Step 4**: Count possibilities

### Cyclic Groups

$$\phi \in \text{Aut}(\mathbb{Z}/n\mathbb{Z}) \Leftrightarrow \phi(1) = k, \; \gcd(k,n) = 1$$

**개수**: $\phi(n)$

### Software

**GAP**: `AutomorphismGroup(G)`

**Magma**: `AutomorphismGroup(G)`

## 표기법

| 표기 | 의미 |
|------|------|
| $\text{Aut}(G)$ | Automorphism group |
| $\text{Inn}(G)$ | Inner automorphism group |
| $\text{Out}(G)$ | Outer automorphism group |
| $\phi_g$ or $c_g$ | Conjugation by $g$ |
| $Z(G)$ | Center |
| $\phi(n)$ | Euler's totient function |

## Common Pitfall^[흔한 실수]

### 1. $\text{Aut}(G)$ not always abelian

Even if $G$ abelian!

**예**: $\text{Aut}(\mathbb{Z}^2) \cong \text{GL}_2(\mathbb{Z})$ non-abelian

### 2. Inner ≠ Identity

$\text{Inn}(G) = \{e\}$ $\Leftrightarrow$ $G$ abelian

일반적으로 많은 inner automorphisms!

### 3. Characteristic ≠ Normal

Characteristic $\Rightarrow$ Normal ✓

하지만 역은 아님!

**예**: In some groups, normal subgroups not preserved by all automorphisms

### 4. $S_6$ is special!

$\text{Out}(S_n) = \{e\}$ for all $n$ **except $n = 6$**

$\text{Out}(S_6) \cong \mathbb{Z}/2\mathbb{Z}$

### 5. $\text{Aut}(G)$ can be much larger than $G$

**예**: $|\text{Aut}((\mathbb{Z}/p\mathbb{Z})^n)| = (p^n - 1)(p^n - p) \cdots$

Grows much faster than $|G| = p^n$

## 응용 분야

**Galois Theory**:
- Field automorphisms
- Galois groups

**Topology**:
- Mapping class groups
- Outer automorphisms of $\pi_1$

**Cryptography**:
- RSA (uses $\phi(n)$)
- Automorphism-based protocols

**Physics**:
- Symmetries
- Gauge transformations

## 관련 개념

- [[Isomorphism]]: Basic concept
- [[Center]]: $\text{Inn}(G) \cong G/Z(G)$
- [[Normal Subgroup]]: Characteristic subgroups
- [[Commutator Subgroup]]: Characteristic
- [[Semidirect Product]]: Holomorph

## 추가 학습 주제

**기초**:
- Definition
- Inner automorphisms
- Examples

**중급**:
- $\text{Out}(G)$
- Characteristic subgroups
- Holomorph

**고급**:
- Automorphism towers
- Outer automorphism of $S_6$
- Mapping class groups
- Automorphisms of free groups
- Mostow rigidity

