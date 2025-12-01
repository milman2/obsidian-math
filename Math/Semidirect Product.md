# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Normal Subgroup]]
- [[Direct Product]]
- [[Automorphism Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups
- Robinson, A Course in the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Semidirect Product^[반직곱]

**Semidirect product**^[반직곱] of $N$ and $H$ via $\phi$:

$$G = N \rtimes_{\phi} H$$

where:
- $N, H$ groups
- $\phi: H \to \text{Aut}(N)$ homomorphism (action of $H$ on $N$)

### Group Structure

**Set**: $G = N \times H$ (as sets)

**Operation**:

$$(n_1, h_1) \cdot (n_2, h_2) = (n_1 \phi(h_1)(n_2), h_1 h_2)$$

**의미**: $H$ "acts" on $N$ by automorphisms

**Identity**: $(e_N, e_H)$

**Inverse**: $(n, h)^{-1} = (\phi(h^{-1})(n^{-1}), h^{-1})$

자세한 내용은 [[Automorphism Group]] 참조

## Internal Semidirect Product

Group $G$ is **internal semidirect product**^[내부 반직곱] of $N$ by $H$ if:

1. $N \triangleleft G$ (normal subgroup)
2. $H \leq G$ (subgroup)
3. $N \cap H = \{e\}$
4. $NH = G$ (every $g = nh$ for some $n \in N, h \in H$)

**Notation**: $G = N \rtimes H$

**의미**: $G$ "splits" as product of $N$ and $H$

자세한 내용은 [[Normal Subgroup]] 참조

## Difference from Direct Product

**Direct product**: $N \times H$

$$(n_1, h_1)(n_2, h_2) = (n_1 n_2, h_1 h_2)$$

**Semidirect product**: $N \rtimes H$

$$(n_1, h_1)(n_2, h_2) = (n_1 \phi(h_1)(n_2), h_1 h_2)$$

**차이**: Direct product when $\phi$ trivial (identity)

$$N \times H = N \rtimes_{\text{id}} H$$

자세한 내용은 [[Direct Product]] 참조

## Split Exact Sequence^[분열 완전 수열]

**Exact sequence**^[완전 수열]:

$$1 \to N \xrightarrow{i} G \xrightarrow{\pi} H \to 1$$

is **split**^[분열]if $\exists$ homomorphism $s: H \to G$ with $\pi \circ s = \text{id}_H$

**정리**: Split exact sequence $\Leftrightarrow$ $G \cong N \rtimes H$

**의미**: Sequence "splits" = semidirect product structure

---

# <span class="header-properties">Properties</span>

## $N$ Normal in $N \rtimes H$

**정리**: In $G = N \rtimes H$, $N \triangleleft G$

**증명**: Identify $N \cong N \times \{e\} \leq G$

For $(n, e)$ and $(n', h)$:

$$(n', h)(n, e)(n', h)^{-1} = (n' \phi(h)(n) \phi(h)(n'^{-1}), e) \in N$$

따라서 $N$ normal 
## $H$ NOT Normal (Generally)

**주의**: $H \cong \{e\} \times H \leq G$ usually **not** normal!

**예**: $D_n = \mathbb{Z}/n\mathbb{Z} \rtimes \mathbb{Z}/2\mathbb{Z}$

$\mathbb{Z}/2\mathbb{Z}$ (reflections) not normal in $D_n$

**예외**: If $\phi$ trivial, then $H$ normal (direct product)

자세한 내용은 [[Dihedral Group]] 참조

## Conjugation Formula

In $G = N \rtimes H$,

$$h n h^{-1} = \phi(h)(n)$$

**의미**: Conjugation by $h$ = action $\phi(h)$

**증명**: $(e, h)(n, e)(e, h)^{-1} = (\phi(h)(n), e)$ 
## Uniqueness (NOT!)

**주의**: $G = N \rtimes_{\phi} H$ depends on $\phi$!

**Different $\phi$**: Different groups

**예**: Multiple non-isomorphic groups of order 8
- $\mathbb{Z}/8\mathbb{Z}, \mathbb{Z}/4\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}, D_4, Q_8$
- Some are semidirect products with different $\phi$

## Automorphism Action

**정리**: $\phi: H \to \text{Aut}(N)$ must be homomorphism

**Check**: 

$$\phi(h_1 h_2)(n) = \phi(h_1)(\phi(h_2)(n))$$

**의미**: Action compatible with group structure

---

# <span class="header-examples">Examples</span>

## Example 1: Dihedral Group

$$D_n = \mathbb{Z}/n\mathbb{Z} \rtimes \mathbb{Z}/2\mathbb{Z}$$

**Action**: $\phi: \mathbb{Z}/2\mathbb{Z} \to \text{Aut}(\mathbb{Z}/n\mathbb{Z})$

$$\phi(0)(r) = r, \quad \phi(1)(r) = r^{-1}$$

**의미**: Reflection inverts rotation

**Operation**:

$$(r^i, s^j)(r^k, s^\ell) = (r^{i + (-1)^j k}, s^{j+\ell})$$

자세한 내용은 [[Dihedral Group]] 참조

## Example 2: Affine Group

**$\text{Aff}(\mathbb{R})$**: Affine transformations $x \mapsto ax + b$

$$\text{Aff}(\mathbb{R}) = \mathbb{R} \rtimes \mathbb{R}^{\times}$$

**Action**: $\phi: \mathbb{R}^{\times} \to \text{Aut}(\mathbb{R})$

$$\phi(a)(b) = ab$$

**Operation**:

$$(b_1, a_1)(b_2, a_2) = (b_1 + a_1 b_2, a_1 a_2)$$

**의미**: $(b, a)$ represents $x \mapsto ax + b$

## Example 3: Holomorph

**Holomorph**^[완전] of $G$:

$$\text{Hol}(G) = G \rtimes \text{Aut}(G)$$

**Action**: $\phi: \text{Aut}(G) \to \text{Aut}(G)$ (identity map)

**의미**: All automorphisms combined with $G$

자세한 내용은 [[Automorphism Group]] 참조

## Example 4: $S_3$

$$S_3 \cong \mathbb{Z}/3\mathbb{Z} \rtimes \mathbb{Z}/2\mathbb{Z}$$

**$N = A_3 \cong \mathbb{Z}/3\mathbb{Z}$**: 3-cycles (normal)

**$H \cong \mathbb{Z}/2\mathbb{Z}$**: Transposition

**Action**: $\phi(1)$ inverts elements

자세한 내용은 [[Symmetric Group]] 참조

## Example 5: Direct Product (Trivial Action)

$$N \times H = N \rtimes_{\text{id}} H$$

**$\phi$ trivial**: $\phi(h)(n) = n$ for all $h, n$

**Operation**:

$$(n_1, h_1)(n_2, h_2) = (n_1 n_2, h_1 h_2)$$

**의미**: Direct product = special case of semidirect product

자세한 내용은 [[Direct Product]] 참조

## Example 6: Wreath Product

**$G \wr H$**: Wreath product

$$G \wr H = (G^n) \rtimes H$$

where $n = |H|$, and $H$ acts by permuting coordinates

**응용**: Sylow subgroups, group actions

자세한 내용은 [[Group Action]] 참조

## Example 7: Matrix Groups

**$\text{GL}_n(\mathbb{F})$**: General linear group

$$\text{GL}_n(\mathbb{F}) \supseteq \text{SL}_n(\mathbb{F}) \times \mathbb{F}^{\times} \text{ (nearly)}$$

Actually:

$$\text{GL}_n(\mathbb{F}) = \text{SL}_n(\mathbb{F}) \rtimes \mathbb{F}^{\times}$$

(for $n \geq 2$, up to center issues)

## Example 8: $p$-Groups

**Not all $p$-groups** are semidirect products!

**예**: $Q_8$ (quaternion) NOT a semidirect product

**이유**: No subgroup of order 4 complementing center

자세한 내용은 [[p-Group]] 참조

---

# <span class="header-theorem">Theorem</span>

## Recognition Theorem

**정리**: $G \cong N \rtimes H$ (internal) $\Leftrightarrow$

1. $N \triangleleft G$
2. $H \leq G$
3. $N \cap H = \{e\}$
4. $NH = G$

**증명**: Define $\phi: H \to \text{Aut}(N)$ by $\phi(h)(n) = hnh^{-1}$

Then $G \cong N \rtimes_{\phi} H$ 
## Split Extension

**정리**: Exact sequence

$$1 \to N \xrightarrow{i} G \xrightarrow{\pi} H \to 1$$

splits $\Leftrightarrow$ $\exists s: H \to G$ with $\pi \circ s = \text{id}_H$

$\Leftrightarrow$ $G \cong N \rtimes H$

**의미**: "Splitting" = semidirect product structure

## Classification (Special Cases)

**Groups of order $pq$ ($p < q$ primes)**:

If $p \nmid (q-1)$: Only $\mathbb{Z}/pq\mathbb{Z}$ (cyclic)

If $p \mid (q-1)$: Two groups
- $\mathbb{Z}/pq\mathbb{Z}$
- $\mathbb{Z}/q\mathbb{Z} \rtimes \mathbb{Z}/p\mathbb{Z}$ (non-abelian)

**예**: Order 15 → only $\mathbb{Z}/15\mathbb{Z}$

Order 21 → only $\mathbb{Z}/21\mathbb{Z}$ (since $3 \nmid 6$)

자세한 내용은 [[Sylow Theorem]] 참조

## Schur-Zassenhaus Theorem

**정리**: If $N \triangleleft G$ with $\gcd(|N|, [G:N]) = 1$,

$$\Rightarrow G = N \rtimes H$$

for some $H \leq G$

**의미**: Coprime orders → splits!

## Universal Property

**정리**: $N \rtimes_{\phi} H$ satisfies universal property

Given $f_N: N \to G$, $f_H: H \to G$ compatible with $\phi$,

$$\exists ! f: N \rtimes H \to G$$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Semidirect Product = "Twisted Direct Product"**

### 메타포: 회전과 반사

**Dihedral group** $D_n$:
- **$N$**: Rotations (normal, abelian)
- **$H$**: Reflection (acts on rotations)
- **Semidirect**: Reflection inverts rotations

$$srs^{-1} = r^{-1}$$

**Direct product**: Rotation and reflection independent

**Semidirect**: Reflection "twists" rotation

### 메타포: 좌표계 변환

**Affine group**: $x \mapsto ax + b$
- **Translation**: $b$ (normal subgroup)
- **Scaling**: $a$ (acts on translations)
- **Semidirect**: Scaling affects translation

$$(b_1, a_1)(b_2, a_2) = (b_1 + a_1 b_2, a_1 a_2)$$

**의미**: Composition 순서 중요!

## 왜 중요한가?

### 1. Construction

**Build groups**: From smaller pieces

**Classification**: Many groups are semidirect products

### 2. Split Extensions

**Exact sequences**: When do they split?

**Cohomology**: Non-split = non-trivial $H^2$

### 3. Group Actions

**Symmetries**: Often semidirect product structure

**Physics**: Gauge groups, spacetime symmetries

### 4. Computation

**Presentations**: Easier for semidirect products

**Algorithms**: Exploit structure

### 5. Representation Theory

**Induced representations**: From $N$ to $G = N \rtimes H$

**Mackey theory**: Irreducible representations

## Direct vs Semidirect

| | **Direct $N \times H$** | **Semidirect $N \rtimes H$** |
|---|---|---|
| **Normal** | Both $N, H$ normal | Only $N$ normal |
| **Abelian** | If $N, H$ abelian | Not necessarily |
| **Action** | Trivial | Non-trivial (generally) |
| **Uniqueness** | Unique | Depends on $\phi$ |
| **예** | $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$ | $D_3, D_4, \ldots$ |

**관계**: Direct product = semidirect with trivial action

자세한 내용은 [[Direct Product]] 참조

## 계산 방법

### Verify Semidirect Product

**Step 1**: Find $N \triangleleft G$, $H \leq G$

**Step 2**: Check $N \cap H = \{e\}$

**Step 3**: Check $NH = G$

**Step 4**: Compute $\phi: H \to \text{Aut}(N)$ via conjugation

### Construct Semidirect Product

**Step 1**: Choose $N, H$ groups

**Step 2**: Define $\phi: H \to \text{Aut}(N)$ (homomorphism!)

**Step 3**: Define operation $(n_1, h_1)(n_2, h_2) = (n_1 \phi(h_1)(n_2), h_1 h_2)$

**Step 4**: Verify associativity, identity, inverse

### Count Possibilities

**Given $N, H$**: How many semidirect products?

**Answer**: Number of homomorphisms $\phi: H \to \text{Aut}(N)$ (up to conjugacy)

**예**: $\mathbb{Z}/3\mathbb{Z} \rtimes \mathbb{Z}/2\mathbb{Z}$
- Trivial $\phi$ → $\mathbb{Z}/6\mathbb{Z}$
- Non-trivial $\phi$ → $S_3 \cong D_3$

## 표기법

| 표기 | 의미 |
|------|------|
| $N \rtimes H$ or $N \rtimes_{\phi} H$ | Semidirect product |
| $N \times H$ | Direct product |
| $\phi: H \to \text{Aut}(N)$ | Action homomorphism |
| $1 \to N \to G \to H \to 1$ | Short exact sequence |
| $G = NH$ | $G$ generated by $N$ and $H$ |

## Common Pitfall^[흔한 실수]

### 1. $\phi$ must be homomorphism

Cannot be arbitrary function!

$$\phi(h_1 h_2) = \phi(h_1) \circ \phi(h_2)$$

### 2. $H$ not normal (generally)

Only $N$ guaranteed normal

**예**: $D_n$ reflections not normal

### 3. Non-uniqueness

Different $\phi$ → different groups!

**예**: $\mathbb{Z}/6\mathbb{Z}$ vs $S_3$ (both $\mathbb{Z}/3\mathbb{Z} \rtimes \mathbb{Z}/2\mathbb{Z}$)

### 4. Not all groups split

**$Q_8$**: Cannot write as semidirect product

**General**: Cohomology obstruction

### 5. Order matters

$N \rtimes H \not\cong H \rtimes N$ (generally)

**예**: Structure depends on which is normal

## 응용 분야

**Group Theory**:
- Classification
- Construction

**Topology**:
- Fundamental groups
- Fiber bundles

**Physics**:
- Poincaré group (spacetime)
- Gauge theories

**Cryptography**:
- Group-based protocols
- Semidirect product groups

**Representation Theory**:
- Induced representations
- Mackey theory

## 관련 개념

- [[Direct Product]]: Special case ($\phi$ trivial)
- [[Normal Subgroup]]: $N$ must be normal
- [[Automorphism Group]]: $\phi: H \to \text{Aut}(N)$
- [[Dihedral Group]]: Classic example
- [[Group Action]]: Action of $H$ on $N$

## 추가 학습 주제

**기초**:
- Definition
- Examples
- Direct vs semidirect

**중급**:
- Split extensions
- Recognition theorem
- Classification

**고급**:
- Group cohomology
- Extension problem
- Wreath products
- Non-abelian cohomology
- Mackey theory
- Induced representations

