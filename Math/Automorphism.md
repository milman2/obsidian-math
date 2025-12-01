# <span class="header-prerequisite">Prerequisite</span>
- [[Isomorphism]]
- [[Homomorphism]]
- [[Group]]
- [[Ring]]
- [[Field]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Artin, Algebra
- Hungerford, Algebra

---

# <span class="header-definition">Definition</span>

## Automorphism^[자기동형사상]

**Automorphism^[자기동형사상]**은 algebraic structure^[대수 구조]의 **자기 자신으로의 isomorphism^[동형사상]**

### General Definition

Algebraic structure $A$에 대해, map $\phi: A \to A$가 **automorphism^[자기동형]**이다 $\Leftrightarrow$

1. $\phi$는 bijective^[전단사]
2. $\phi$는 structure-preserving^[구조 보존] (homomorphism)
3. Domain = Codomain (자기 자신으로)

**핵심**: "자기 자신과 같다"를 보여주는 isomorphism

## Group Automorphism^[군 자기동형]

Group $G$에 대해, $\phi: G \to G$가 **group automorphism^[군 자기동형]**이다 $\Leftrightarrow$

$$\phi(gh) = \phi(g)\phi(h) \quad \text{and} \quad \phi \text{ is bijective}$$

**Properties**:
- $\phi(e) = e$ (identity preserved)
- $\phi(g^{-1}) = \phi(g)^{-1}$ (inverses preserved)
- $\phi(g^n) = \phi(g)^n$ (powers preserved)

**직관**: Group의 "대칭성"을 나타냄

## Ring Automorphism^[환 자기동형]

Ring $R$에 대해, $\phi: R \to R$가 **ring automorphism^[환 자기동형]**이다 $\Leftrightarrow$

$$\phi(a + b) = \phi(a) + \phi(b)$$
$$\phi(ab) = \phi(a)\phi(b)$$
$$\phi \text{ is bijective}$$

**추가 조건** (unital rings):
- $\phi(1) = 1$ (identity preserved)

## Field Automorphism^[체 자기동형]

Field $\mathbb{F}$에 대해, $\phi: \mathbb{F} \to \mathbb{F}$가 **field automorphism^[체 자기동형]**이다 $\Leftrightarrow$

Ring automorphism조건 만족

**중요**: Field homomorphism은 자동으로 injective이므로, surjective만 확인하면 됨!

### Field Automorphism Fixing Subfield

Field extension $\mathbb{F}/K$에서, $\phi: \mathbb{F} \to \mathbb{F}$가 **$K$-automorphism^[K-자기동형]**이다 $\Leftrightarrow$

1. $\phi$는 field automorphism
2. $\phi|_K = \text{id}_K$ (fixes $K$ pointwise)

$$\phi(k) = k \quad \forall k \in K$$

**표기**: $\text{Aut}(\mathbb{F}/K)$ 또는 $\text{Gal}(\mathbb{F}/K)$

자세한 내용은 [[Galois Theory]] 참조

## Vector Space Automorphism^[벡터 공간 자기동형]

Vector space $V$ over field $\mathbb{F}$에 대해, $T: V \to V$가 **vector space automorphism^[벡터 공간 자기동형]**이다 $\Leftrightarrow$

$$T(av + w) = aT(v) + T(w)$$
$$T \text{ is bijective}$$

**동등 조건**: Invertible linear transformation^[가역 선형 변환]

**표기**: $GL(V)$ = General Linear Group^[일반 선형군]

## Inner Automorphism^[내부 자기동형]

### For Groups

Group $G$, 원소 $g \in G$에 대해, **inner automorphism^[내부 자기동형]** by $g$:

$$\phi_g: G \to G, \quad \phi_g(h) = ghg^{-1}$$

**의미**: Conjugation^[켤레] by $g$

**표기**: $c_g$, $\text{Inn}_g$, $\text{Ad}_g$ (Lie theory에서)

### Verification

$\phi_g$가 automorphism임을 확인:

1. **Homomorphism**:
$$\phi_g(h_1h_2) = g(h_1h_2)g^{-1} = (gh_1g^{-1})(gh_2g^{-1}) = \phi_g(h_1)\phi_g(h_2)$$

2. **Bijective**: 
   - Inverse: $\phi_{g^{-1}}$
   - $\phi_{g^{-1}} \circ \phi_g = \phi_e = \text{id}$

## Outer Automorphism^[외부 자기동형]

**Outer automorphism^[외부 자기동형]**: Inner automorphism이 **아닌** automorphism

**정확한 정의**: $\text{Out}(G) = \text{Aut}(G) / \text{Inn}(G)$의 nontrivial coset

**의미**: "Group 자체의 구조로 설명 안 되는" 대칭성

자세한 내용은 [[Automorphism Group]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Identity Automorphism

**모든 structure $A$**:

$$\text{id}_A: A \to A, \quad \text{id}_A(a) = a$$

**Trivial automorphism**: 항상 존재

## Example 2: Group Inversion (Abelian Groups)

Abelian group $G$:

$$\phi: G \to G, \quad \phi(g) = g^{-1}$$

**Automorphism**:
- Bijective: Inverse of inverse is itself
- Homomorphism: $\phi(gh) = (gh)^{-1} = h^{-1}g^{-1} = g^{-1}h^{-1} = \phi(g)\phi(h)$ (abelian!)

**Note**: Non-abelian groups에서는 일반적으로 homomorphism 아님!

## Example 3: Cyclic Group $\mathbb{Z}/n\mathbb{Z}$

$$\phi_k: \mathbb{Z}/n\mathbb{Z} \to \mathbb{Z}/n\mathbb{Z}, \quad \phi_k([a]) = [ka]$$

**Automorphism** $\Leftrightarrow$ $\gcd(k, n) = 1$

**이유**:
- Bijective $\Leftrightarrow$ $k$ is unit in $\mathbb{Z}/n\mathbb{Z}$ $\Leftrightarrow$ $\gcd(k, n) = 1$
- Homomorphism: $\phi_k([a + b]) = [k(a+b)] = [ka + kb] = \phi_k([a]) + \phi_k([b])$

**개수**: $|\text{Aut}(\mathbb{Z}/n\mathbb{Z})| = \phi(n)$ (Euler totient function)

## Example 4: Infinite Cyclic Group $\mathbb{Z}$

$$\text{Aut}(\mathbb{Z}) = \{\text{id}, \phi_{-1}\} \cong \mathbb{Z}/2\mathbb{Z}$$

where $\phi_{-1}(n) = -n$

**이유**: Generator $1$을 $\pm 1$로만 보낼 수 있음

## Example 5: Complex Conjugation

$$\sigma: \mathbb{C} \to \mathbb{C}, \quad \sigma(a + bi) = a - bi$$

**Field automorphism**:
- $\sigma(z + w) = \overline{z + w} = \bar{z} + \bar{w} = \sigma(z) + \sigma(w)$
- $\sigma(zw) = \overline{zw} = \bar{z}\bar{w} = \sigma(z)\sigma(w)$
- Bijective: $\sigma^2 = \text{id}$

**$\mathbb{R}$-automorphism**: Fixes $\mathbb{R}$ pointwise

**Order**: $|\sigma| = 2$

$$\text{Gal}(\mathbb{C}/\mathbb{R}) = \{\text{id}, \sigma\} \cong C_2$$

## Example 6: Real Numbers $\mathbb{R}$

$$\text{Aut}(\mathbb{R}) = \{\text{id}\}$$

**Surprising fact**: $\mathbb{R}$는 nontrivial automorphism이 없음!

**이유**: 
- Positive elements must map to positive ($\phi(x^2) = \phi(x)^2 \geq 0$)
- Order preserving ($a < b \Rightarrow \phi(a) < \phi(b)$)
- Density + continuity → $\phi = \text{id}$

## Example 7: Rational Numbers $\mathbb{Q}$

$$\text{Aut}(\mathbb{Q}) = \{\text{id}\}$$

**이유**:
- $\phi(n) = n$ for all $n \in \mathbb{Z}$ (characteristic 0)
- $\phi(p/q) = \phi(p)/\phi(q) = p/q$

## Example 8: Frobenius Automorphism

Finite field $\mathbb{F}_{p^n}$:

$$\text{Frob}: \mathbb{F}_{p^n} \to \mathbb{F}_{p^n}, \quad \text{Frob}(x) = x^p$$

**Field automorphism**:
- $(x + y)^p = x^p + y^p$ (characteristic $p$!)
- $(xy)^p = x^p y^p$
- Bijective (finite field)

**Properties**:
- $\text{Frob}^n = \text{id}$
- Generates $\text{Gal}(\mathbb{F}_{p^n}/\mathbb{F}_p) \cong C_n$

자세한 내용은 [[Finite Field]] 참조

## Example 9: Conjugation in $S_n$

Permutation $\sigma \in S_n$에 대해:

$$\phi_\sigma: S_n \to S_n, \quad \phi_\sigma(\tau) = \sigma \tau \sigma^{-1}$$

**Inner automorphism**

**Effect**: 
- $(i_1 \; i_2 \; \cdots \; i_k) \mapsto (\sigma(i_1) \; \sigma(i_2) \; \cdots \; \sigma(i_k))$
- "Relabeling" of elements

## Example 10: Matrix Similarity

$GL_n(\mathbb{F})$, invertible matrix $P$:

$$\phi_P: GL_n(\mathbb{F}) \to GL_n(\mathbb{F}), \quad \phi_P(A) = PAP^{-1}$$

**Inner automorphism** (conjugation)

**Interpretation**: Change of basis

**Invariants**: Trace, determinant, eigenvalues

## Example 11: Dihedral Group $D_n$

$$D_n = \langle r, s \mid r^n = s^2 = e, srs = r^{-1} \rangle$$

**Automorphism** determined by $\phi(r)$ and $\phi(s)$:
- $\phi(r)$ must have order $n$ → $\phi(r) = r^k$ where $\gcd(k, n) = 1$
- $\phi(s)$ must have order $2$ → $\phi(s) \in \{s, sr, sr^2, \ldots\}$

**Size**: $|\text{Aut}(D_n)|$ varies with $n$

자세한 내용은 [[Dihedral Group]] 참조

## Example 12: Quaternion Group $Q_8$

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

**Inner automorphisms**: 4개 ($|Q_8/Z(Q_8)| = 8/2 = 4$)

**All automorphisms**: $|\text{Aut}(Q_8)| = 24 \cong S_4$

**Outer automorphisms**: $|\text{Out}(Q_8)| = 24/4 = 6$

## Example 13: Transpose Map

$$T: M_n(\mathbb{F}) \to M_n(\mathbb{F}), \quad T(A) = A^T$$

**Ring automorphism**:
- $(A + B)^T = A^T + B^T$
- $(AB)^T = B^T A^T$ (anti-homomorphism for multiplication!)

**Not** a ring automorphism (reverses multiplication order)

**Is** a ring **anti-automorphism^[반자기동형]**

---

# <span class="header-properties">Properties</span>

## Basic Properties

**정리**: Automorphism $\phi: G \to G$는 다음을 만족:

1. **Identity**: $\phi(e) = e$

2. **Inverses**: $\phi(g^{-1}) = \phi(g)^{-1}$

3. **Powers**: $\phi(g^n) = \phi(g)^n$

4. **Order**: $|\phi(g)| = |g|$ (element order preserved)

5. **Subgroups**: $H \leq G \Rightarrow \phi(H) \leq G$

6. **Normal subgroups**: $N \triangleleft G \Rightarrow \phi(N) \triangleleft G$

## Composition

**정리**: Automorphisms의 composition은 automorphism

$$\phi, \psi \in \text{Aut}(G) \Rightarrow \phi \circ \psi \in \text{Aut}(G)$$

**증명**:
- Bijective: Composition of bijections
- Homomorphism: $(\phi \circ \psi)(gh) = \phi(\psi(gh)) = \phi(\psi(g)\psi(h)) = \phi(\psi(g))\phi(\psi(h))$

## Inverse

**정리**: Automorphism의 inverse는 automorphism

$$\phi \in \text{Aut}(G) \Rightarrow \phi^{-1} \in \text{Aut}(G)$$

이미 isomorphism 성질에서 보장됨

## Inner Automorphisms are Automorphisms

**정리**: Inner automorphism $\phi_g$는 automorphism

**증명**: Example 9에서 확인

## Fixed Points^[고정점]

**정의**: $\text{Fix}(\phi) = \{g \in G : \phi(g) = g\}$

**성질**:
- $\text{Fix}(\phi) \leq G$ (subgroup)
- Identity automorphism: $\text{Fix}(\text{id}) = G$
- $K$-automorphism: $\text{Fix}(\phi) \supseteq K$

## Characteristic Subgroups^[특성 부분군]

**정의**: $H \leq G$가 **characteristic^[특성]**이다 $\Leftrightarrow$

$$\phi(H) = H \quad \forall \phi \in \text{Aut}(G)$$

**예**:
- $Z(G)$ (center)
- $G'$ (commutator subgroup)
- $\text{Frattini}(G)$

**성질**: Characteristic $\Rightarrow$ Normal (stronger condition!)

## Preservation of Structure

**정리**: Automorphism은 모든 group-theoretic properties 보존

**보존되는 것들**:
- Abelianness
- Cyclicity  
- Simplicity
- Solvability
- Nilpotency

**Not preserved** (일반적으로):
- Specific elements (unless fixed)

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Automorphism = "구조를 보존하는 재배치"**

**핵심 아이디어**:
- Group을 "섞지만" 구조는 유지
- "내부적으로 같은" 구조의 다른 표현
- 대칭성의 수학적 표현

**기하학적**:
- 도형의 symmetry operations
- Rotation, reflection (preserving shape)

## Inner vs Outer Automorphisms

### Inner Automorphisms

**특징**:
- Group 원소로 정의됨 ($\phi_g$)
- "내재적" 대칭성
- 항상 존재 (적어도 identity)

**직관**: "내부에서 보이는" 대칭성

### Outer Automorphisms

**특징**:
- Group 원소로 설명 안 됨
- "예외적" 대칭성
- 존재하지 않을 수 있음

**직관**: "밖에서 봐야 보이는" 대칭성

**Famous example**: $S_6$의 exceptional outer automorphism

자세한 내용은 [[Symmetric Group]] 참조

## 응용 분야

### 1. Galois Theory^[갈루아 이론]

**Field automorphisms**: Galois group의 원소

$$\text{Gal}(\mathbb{F}/K) = \text{Aut}_K(\mathbb{F})$$

**응용**: Polynomial solvability, ruler-and-compass constructions

자세한 내용은 [[Galois Theory]] 참조

### 2. Group Theory^[군론]

**Classification**: Automorphism group으로 groups 분류

**Simple groups**: Outer automorphism group 연구

### 3. Representation Theory^[표현론]

**Equivalence**: Automorphism으로 연결된 representations

**Character theory**: Automorphism-invariant

### 4. Cryptography^[암호학]

**Elliptic curves**: Automorphisms of curves

**Isogeny-based crypto**: Structure-preserving maps

### 5. Topology^[위상수학]

**Fundamental group**: Automorphisms from basepoint change

**Covering spaces**: Deck transformations

### 6. Algebraic Geometry^[대수기하학]

**Varieties**: Automorphism groups of varieties

**Moduli spaces**: Parametrizing automorphisms

## Relation to Automorphism Group

**Individual** automorphism $\phi$:
- Single structure-preserving bijection
- Element of $\text{Aut}(G)$

**Automorphism group** $\text{Aut}(G)$:
- **Set** of all automorphisms
- Group under composition
- Measures "total symmetry"

자세한 내용은 [[Automorphism Group]] 참조

## Computing Automorphisms

### Strategy

**Step 1**: Identify generators (if finitely generated)

**Step 2**: Determine where generators can map
- Must preserve order
- Must preserve relations

**Step 3**: Verify each candidate is homomorphism

**Step 4**: Check bijectivity

### For Cyclic Groups

$G = \langle g \rangle$ cyclic:
- $\phi$ determined by $\phi(g)$
- $\phi(g)$ must have same order as $g$
- $\phi(g) = g^k$ where $\gcd(k, |g|) = 1$

### For Symmetric Groups

$S_n$ ($n \neq 6$):
- All automorphisms are inner
- $\text{Out}(S_n) = \{e\}$

$S_6$:
- Exceptional outer automorphism exists
- $\text{Out}(S_6) \cong \mathbb{Z}/2\mathbb{Z}$

## Common Pitfalls

### 1. Composition Order

✗ "$(\phi \circ \psi)(g) = \psi(\phi(g))$"?

✓ $(\phi \circ \psi)(g) = \phi(\psi(g))$ (apply $\psi$ first!)

Convention varies - be consistent!

### 2. Inner ≠ All

✗ "모든 automorphism이 inner"?

✓ 일반적으로 아님! Outer automorphisms 존재 가능

$\text{Out}(G) = \{e\}$ $\not\Leftrightarrow$ trivial for all groups

### 3. Inverse Map

✗ "$\phi(g)^{-1} = \phi(g^{-1})$는 정의"?

✓ 이것은 **성질** (증명 필요)

Automorphism이기 때문에 성립

### 4. Fixed Subfield

✗ "Field automorphism은 모든 원소 고정"?

✓ **Subfield** 고정! 전체 field는 움직일 수 있음

$\mathbb{R}$-automorphism of $\mathbb{C}$: $\mathbb{R}$ 고정, $i$ 움직임

### 5. Anti-automorphism

✗ "Transpose는 matrix automorphism"?

✓ **Anti-automorphism** (reverses multiplication)

$(AB)^T = B^T A^T$ (order reversed!)

## Comparison: Automorphism vs Isomorphism

| Aspect | Isomorphism | Automorphism |
|--------|-------------|--------------|
| Domain | $G$ | $G$ |
| Codomain | $H$ | $G$ (same!) |
| Meaning | "G and H are same" | "G is symmetric" |
| Properties | Equivalence relation | Group operation |
| Collection | Equivalence class | $\text{Aut}(G)$ (group) |

## Historical Context

**Felix Klein** (1849-1925):
- Erlangen program
- Geometry = study of invariants under transformations
- Automorphisms = fundamental transformations

**Évariste Galois** (1811-1832):
- Field automorphisms
- Galois theory foundation
- Polynomial solvability

**Emmy Noether** (1882-1935):
- Abstract algebra
- Automorphism groups in ring theory

## Related Concepts

- [[Isomorphism]]: General concept
- [[Automorphism Group]]: Collection of automorphisms
- [[Homomorphism]]: Structure-preserving maps
- [[Inner Automorphism]]: Conjugation
- [[Galois Theory]]: Field automorphisms
- [[Conjugate]]: Group conjugation
- [[Normal Subgroup]]: Automorphism-related
- [[Center]]: Fixed by inner automorphisms
- [[Characteristic Subgroup]]: Fixed by all automorphisms

