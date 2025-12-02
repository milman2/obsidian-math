# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Automorphism]]
- [[Homomorphism]]
- [[Conjugate]]
- [[Center]]
- [[Normal Subgroup]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Hungerford, Algebra

---

# <span class="header-definition">Definition</span>

## Conjugation Automorphism^[켤레 자기동형사상]

Group $G$와 원소 $g \in G$에 대해, **conjugation automorphism**^[켤레 자기동형사상] (또는 **inner automorphism**^[내부 자기동형사상])은:

$$\phi_g: G \to G, \quad \phi_g(h) = ghg^{-1}$$

**의미**: 원소 $g$에 의한 conjugation^[켤레]

**표기**: 
- $\phi_g$
- $c_g$ (conjugation by $g$)
- $\text{Inn}_g$
- $\text{Ad}_g$ (adjoint representation, Lie theory에서)

## Verification of Automorphism

$\phi_g$가 automorphism^[자기동형사상]임을 확인:

### 1. Homomorphism^[준동형사상]

$$\phi_g(h_1h_2) = g(h_1h_2)g^{-1} = (gh_1g^{-1})(gh_2g^{-1}) = \phi_g(h_1)\phi_g(h_2)$$

### 2. Bijective^[전단사]

**Injective**: 
$$\phi_g(h_1) = \phi_g(h_2) \Rightarrow gh_1g^{-1} = gh_2g^{-1} \Rightarrow h_1 = h_2$$

(left/right cancellation)

**Surjective**: 
$$\forall h \in G, \; \phi_g(g^{-1}hg) = g(g^{-1}hg)g^{-1} = h$$

**Inverse function**: $\phi_g^{-1} = \phi_{g^{-1}}$

$$\phi_{g^{-1}} \circ \phi_g = \phi_{g^{-1}g} = \phi_e = \text{id}_G$$

따라서 $\phi_g \in \text{Aut}(G)$

## Effect on Elements

$\phi_g$의 작용:

$$h \mapsto ghg^{-1}$$

**직관**: 
- $h$를 $g$의 "관점"에서 본 것
- "Change of viewpoint" or "coordinate transformation"
- $g$로 "재해석"

## Composition of Conjugation Automorphisms

**정리**: 

$$\phi_g \circ \phi_h = \phi_{gh}$$

**증명**:

$$(\phi_g \circ \phi_h)(x) = \phi_g(hxh^{-1}) = g(hxh^{-1})g^{-1} = (gh)x(gh)^{-1} = \phi_{gh}(x)$$

**결과**: Conjugation automorphisms의 composition은 다시 conjugation automorphism

## Inner Automorphism Group^[내부 자기동형군]

$$\text{Inn}(G) = \{\phi_g : g \in G\} \leq \text{Aut}(G)$$

**성질**:
1. Subgroup of $\text{Aut}(G)$
2. **Normal subgroup**: $\text{Inn}(G) \triangleleft \text{Aut}(G)$

자세한 내용은 [[Automorphism Group]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Abelian Groups

$G$ abelian이면:

$$\phi_g(h) = ghg^{-1} = gg^{-1}h = h$$

**모든 conjugation automorphism = identity**

$$\text{Inn}(G) = \{\text{id}\}$$

**결과**: Abelian groups have no nontrivial inner automorphisms

## Example 2: Symmetric Group $S_n$

Permutation $\sigma \in S_n$:

$$\phi_\sigma: S_n \to S_n, \quad \phi_\sigma(\tau) = \sigma \tau \sigma^{-1}$$

**Effect on cycles**:

$$(i_1 \; i_2 \; \cdots \; i_k) \mapsto (\sigma(i_1) \; \sigma(i_2) \; \cdots \; \sigma(i_k))$$

**직관**: "Relabeling" of indices

**예**: $\sigma = (12)$, $\tau = (13)$

$$\phi_{(12)}((13)) = (12)(13)(12) = (23)$$

## Example 3: Dihedral Group $D_n$

$$D_n = \langle r, s \mid r^n = s^2 = e, srs = r^{-1} \rangle$$

**Conjugation by $s$**:

$$\phi_s(r) = srs^{-1} = r^{-1}$$

$$\phi_s(r^k) = (r^{-1})^k = r^{-k}$$

**Effect**: Reflection "inverts" rotation

**Conjugation by $r$**:

$$\phi_r(s) = rsr^{-1} = sr^{-2}$$

(using relation $rs = sr^{-1}$)

## Example 4: Matrix Conjugation

$GL_n(\mathbb{F})$, invertible matrix $P$:

$$\phi_P(A) = PAP^{-1}$$

**Interpretation**: Change of basis transformation

**Preserved invariants**:
- Trace: $\text{tr}(PAP^{-1}) = \text{tr}(A)$
- Determinant: $\det(PAP^{-1}) = \det(A)$
- Eigenvalues: same eigenvalues
- Characteristic polynomial: same polynomial

**Similarity classes**: Orbits under conjugation

## Example 5: Quaternion Group $Q_8$

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

**Conjugation by $i$**:

$$\phi_i(j) = iji^{-1} = i \cdot j \cdot (-i) = -k$$

$$\phi_i(k) = iki^{-1} = i \cdot k \cdot (-i) = j$$

**Effect**: Cyclic permutation of $\{i, j, k\}$

**Center**: $Z(Q_8) = \{\pm 1\}$

$$|\text{Inn}(Q_8)| = |Q_8/Z(Q_8)| = 8/2 = 4$$

## Example 6: Conjugation in $GL_n(\mathbb{R})$

Diagonal matrix $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$:

$$\phi_P(D) = PDP^{-1}$$

**Effect**: 
- If $P$ orthogonal: Rotation of coordinate system
- General $P$: Change of basis

**Jordan normal form**: Canonical form under conjugation

## Example 7: Normalizer Action

Subgroup $H \leq G$, $g \in N_G(H)$ (normalizer):

$$\phi_g|_H: H \to H, \quad \phi_g(h) = ghg^{-1}$$

**Restriction**: $\phi_g$ restricts to automorphism of $H$

**Homomorphism**:

$$N_G(H) \to \text{Aut}(H), \quad g \mapsto \phi_g|_H$$

**Kernel**: $C_G(H)$ (centralizer)

$$N_G(H)/C_G(H) \hookrightarrow \text{Aut}(H)$$

## Example 8: Trivial Conjugation

**Center elements**: $z \in Z(G)$

$$\phi_z(h) = zhz^{-1} = hzz^{-1} = h$$

**결과**: $\phi_z = \text{id}$ for all $z \in Z(G)$

**의미**: Center elements give trivial conjugation automorphisms

---

# <span class="header-properties">Properties</span>

## Conjugation Preserves Order

**정리**: $\phi_g(h) = ghg^{-1}$이면:

$$|ghg^{-1}| = |h|$$

**증명**:

$$(ghg^{-1})^n = gh^ng^{-1}$$

따라서 $(ghg^{-1})^n = e \Leftrightarrow h^n = e$

## Conjugation Preserves Structure

**정리**: Conjugation automorphism은 다음을 보존:

1. **Element order**: $|\phi_g(h)| = |h|$
2. **Subgroups**: $K \leq G \Rightarrow \phi_g(K) \leq G$
3. **Normal subgroups**: $N \triangleleft G \Rightarrow \phi_g(N) = N$
4. **Commutativity**: $ab = ba \Leftrightarrow \phi_g(a)\phi_g(b) = \phi_g(b)\phi_g(a)$

## Kernel of Conjugation Map

**정리**: Homomorphism $\Phi: G \to \text{Aut}(G)$, $\Phi(g) = \phi_g$

$$\ker(\Phi) = Z(G)$$

**증명**:

$$g \in \ker(\Phi) \Leftrightarrow \phi_g = \text{id} \Leftrightarrow ghg^{-1} = h \; \forall h \Leftrightarrow g \in Z(G)$$

자세한 내용은 [[Center]] 참조

## First Isomorphism Theorem Application

**정리**: 

$$\text{Inn}(G) \cong G/Z(G)$$

**증명**:
- Homomorphism: $\Phi: G \to \text{Inn}(G)$, $g \mapsto \phi_g$
- Surjective: By definition of $\text{Inn}(G)$
- Kernel: $\ker(\Phi) = Z(G)$
- First Isomorphism Theorem: $G/\ker(\Phi) \cong \text{im}(\Phi)$

따라서 $G/Z(G) \cong \text{Inn}(G)$

자세한 내용은 [[Isomorphism Theorem]] 참조

## Conjugation Commutes with Conjugation

**정리**: 

$$\phi_g \circ \phi_h \circ \phi_g^{-1} = \phi_{ghg^{-1}}$$

**증명**:

$$(\phi_g \circ \phi_h \circ \phi_g^{-1})(x) = \phi_g(\phi_h(g^{-1}xg)) = g(h(g^{-1}xg)h^{-1})g^{-1}$$

$$= (ghg^{-1})x(ghg^{-1})^{-1} = \phi_{ghg^{-1}}(x)$$

**의미**: Conjugation of automorphisms = automorphism by conjugate element

## Fixed Points

**정리**: Fixed points of $\phi_g$:

$$\text{Fix}(\phi_g) = \{h \in G : ghg^{-1} = h\} = C_G(g)$$

**의미**: Centralizer^[중심화군] = fixed point set of conjugation

## Normal Subgroups Characterization

**정리**: $N \leq G$

$$N \triangleleft G \quad \Leftrightarrow \quad \phi_g(N) = N \; \forall g \in G$$

**증명**: 

$$N \triangleleft G \Leftrightarrow gNg^{-1} = N \; \forall g \Leftrightarrow \phi_g(N) = N \; \forall g$$

**의미**: Normal subgroups = subgroups invariant under all conjugation automorphisms

자세한 내용은 [[Normal Subgroup]] 참조

## Characteristic Subgroups

**정의**: $H \leq G$가 **characteristic**^[특성]이다 $\Leftrightarrow$

$$\phi(H) = H \quad \forall \phi \in \text{Aut}(G)$$

**비교**:
- **Normal**: $\phi_g(H) = H$ for all $g \in G$ (inner automorphisms만)
- **Characteristic**: $\phi(H) = H$ for all $\phi \in \text{Aut}(G)$ (모든 automorphisms)

**관계**: Characteristic $\Rightarrow$ Normal (stronger condition!)

---

# <span class="header-theorem">Theorems</span>

## Conjugation Map is Homomorphism

**정리**: 

$$\Phi: G \to \text{Aut}(G), \quad \Phi(g) = \phi_g$$

는 group homomorphism^[군 준동형사상]

**증명**:

$$\Phi(g_1g_2) = \phi_{g_1g_2} = \phi_{g_1} \circ \phi_{g_2} = \Phi(g_1) \circ \Phi(g_2)$$

## Image is Inner Automorphism Group

**정리**: 

$$\text{im}(\Phi) = \text{Inn}(G) \leq \text{Aut}(G)$$

**의미**: Conjugation automorphisms = exactly inner automorphisms

## $\text{Inn}(G)$ is Normal in $\text{Aut}(G)$

**정리**: 

$$\text{Inn}(G) \triangleleft \text{Aut}(G)$$

**증명**: $\psi \in \text{Aut}(G)$, $\phi_g \in \text{Inn}(G)$

$$(\psi \circ \phi_g \circ \psi^{-1})(h) = \psi(g\psi^{-1}(h)g^{-1}) = \psi(g)\psi(\psi^{-1}(h))\psi(g^{-1})$$

$$= \psi(g) \cdot h \cdot \psi(g)^{-1} = \phi_{\psi(g)}(h)$$

따라서 $\psi \circ \phi_g \circ \psi^{-1} = \phi_{\psi(g)} \in \text{Inn}(G)$

## Outer Automorphism Group

**정의**: 

$$\text{Out}(G) = \text{Aut}(G) / \text{Inn}(G)$$

**의미**: "Non-conjugation" automorphisms를 측정

**Trivial outer automorphism group**: $\text{Out}(G) = \{e\}$

$\Leftrightarrow$ 모든 automorphism이 conjugation으로 설명됨

자세한 내용은 [[Automorphism Group]] 참조

## Conjugation in Normal Subgroups

**정리**: $N \triangleleft G$, $g \in G$

$$\phi_g(N) = N$$

**증명**: Normality의 정의

**결과**: Conjugation restricts to automorphism of $N$

$$\phi_g|_N: N \to N$$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Conjugation = "내부적 변환"**

**핵심 아이디어**:
- $ghg^{-1}$ = "$g$의 관점에서 본 $h$"
- Group 원소로 정의되는 자연스러운 automorphism
- "내재적" 대칭성의 표현

**기하학적**:
- Matrix: Change of basis
- Geometric transformation: Coordinate change
- Symmetry: View from different perspective

## Inner vs Outer

| Aspect | Inner Automorphism | Outer Automorphism |
|--------|-------------------|-------------------|
| **정의** | $\phi_g(h) = ghg^{-1}$ | Not inner |
| **Source** | Group elements ($g \in G$) | External structure |
| **Always exist** | Yes (at least identity) | Not necessarily |
| **Collection** | $\text{Inn}(G)$ | $\text{Out}(G) = \text{Aut}(G)/\text{Inn}(G)$ |
| **예** | Most groups | $S_6$ has exceptional outer |

## Why "Inner"?

**"Inner"의 의미**:
- Group **내부** 원소로 정의됨
- Group 구조에 **내재**된 대칭성
- "자연스러운" automorphism

**"Outer"의 의미**:
- 내부 원소로 설명 **안** 됨
- "예외적" 대칭성
- 더 깊은 구조 필요

## 응용 분야

### 1. Group Theory^[군론]

**Conjugacy classes**: $\text{cl}(a) = \{\phi_g(a) : g \in G\}$

**Class equation**: Conjugation action으로 유도

**Normal subgroups**: Conjugation-invariant subgroups

자세한 내용은 [[Class Equation]], [[Conjugate]] 참조

### 2. Representation Theory^[표현론]

**Adjoint representation**: $\text{Ad}: G \to \text{Aut}(G)$, $g \mapsto \phi_g$

**Kernel**: Center $Z(G)$

**Image**: Inner automorphisms

### 3. Lie Theory^[리 이론]

**Adjoint action**: Lie group의 conjugation

$$\text{Ad}_g: \mathfrak{g} \to \mathfrak{g}$$

on Lie algebra $\mathfrak{g}$

**Infinitesimal version**: Bracket operation

### 4. Algebraic Geometry^[대수기하학]

**Conjugation of varieties**: Automorphism groups acting

**Moduli spaces**: Quotients by conjugation

### 5. Physics^[물리학]

**Gauge transformations**: Conjugation by gauge group elements

**Symmetry**: Internal symmetries via conjugation

## Computing Conjugation

### For Finite Groups

**Direct computation**: Apply $ghg^{-1}$ for each $g, h$

**Software**: GAP, Magma

```gap
ConjugacyClass(G, g)
```

### For Matrix Groups

**Similarity transformation**: $PAP^{-1}$

**Eigenvalues**: Conjugation invariant

**Jordan form**: Canonical form under conjugation

### For Permutations

**Cycle structure preserved**: $(i_1 \; \cdots \; i_k) \mapsto (\sigma(i_1) \; \cdots \; \sigma(i_k))$

**Algorithm**: Apply permutation to indices

## Common Pitfalls

### 1. Conjugation ≠ Commutation

✗ "$ghg^{-1} = hgh^{-1}$"?

✓ Generally **NO!**

Only true if $g$ and $h$ commute

### 2. All Automorphisms ≠ Inner

✗ "모든 automorphism이 conjugation"?

✓ Only if $\text{Out}(G) = \{e\}$

Many groups have outer automorphisms

### 3. Abelian Groups

✗ "Abelian group has many inner automorphisms"?

✓ **NO!** $\text{Inn}(G) = \{\text{id}\}$ for abelian $G$

All conjugations are trivial

### 4. Order of Conjugate

✗ "Conjugate has different order"?

✓ **Same order**: $|ghg^{-1}| = |h|$

Conjugation preserves order!

### 5. Kernel of Conjugation Map

✗ "$\ker(\Phi) = \{e\}$"?

✓ $\ker(\Phi) = Z(G)$ (center)

Elements that commute with everything

## Key Formulas

**Conjugation**:
$$\phi_g(h) = ghg^{-1}$$

**Composition**:
$$\phi_g \circ \phi_h = \phi_{gh}$$

**Inverse**:
$$\phi_g^{-1} = \phi_{g^{-1}}$$

**Identity**:
$$\phi_e = \text{id}_G$$

**Kernel**:
$$\{g : \phi_g = \text{id}\} = Z(G)$$

**Image**:
$$\{\phi_g : g \in G\} = \text{Inn}(G)$$

**Quotient**:
$$G/Z(G) \cong \text{Inn}(G)$$

## Conjugation in Different Structures

| Structure | Conjugation | Effect |
|-----------|-------------|--------|
| **Groups** | $ghg^{-1}$ | Element transformation |
| **Matrices** | $PAP^{-1}$ | Change of basis |
| **Permutations** | $\sigma\tau\sigma^{-1}$ | Relabel indices |
| **Rings** | $gRg^{-1}$ | Not always defined |
| **Fields** | N/A | Not meaningful |

**주의**: Conjugation은 주로 **group structure**에서 의미 있음!

## Conjugation vs Similarity

**Linear algebra context**:

**Similar matrices**: $A \sim B \Leftrightarrow B = PAP^{-1}$

**Conjugation in $GL_n$**: Same as similarity!

**Invariants under similarity**:
- Rank
- Trace
- Determinant
- Eigenvalues
- Characteristic polynomial
- Minimal polynomial

## Historical Note

**Sophus Lie** (1842-1899):
- Conjugation in continuous groups
- Adjoint representation
- Lie algebras

**Wilhelm Killing** (1847-1923):
- Root systems
- Conjugacy in Lie groups

**Emmy Noether** (1882-1935):
- Abstract formulation
- Inner automorphism groups

## Related Concepts

- [[Conjugate]]: Conjugacy relation
- [[Automorphism]]: General automorphisms
- [[Automorphism Group]]: $\text{Inn}(G)$, $\text{Out}(G)$
- [[Center]]: Kernel of conjugation map
- [[Centralizer]]: Fixed points of conjugation
- [[Normalizer]]: Preserves subgroup under conjugation
- [[Normal Subgroup]]: Conjugation-invariant
- [[Class Equation]]: Counting conjugacy classes
- [[Isomorphism Theorem]]: $G/Z(G) \cong \text{Inn}(G)$
- [[Group Action]]: Conjugation as action

