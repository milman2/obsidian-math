# <span class="header-prerequisite">Prerequisite</span>
- [[Ring Theory]]
- [[Group Theory]]
- [[Abelian Group]]
- [[Vector Space]]
- [[Homomorphism]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Atiyah & MacDonald, Introduction to Commutative Algebra
- Lang, Algebra
- Rotman, An Introduction to Homological Algebra

---

# <span class="header-definition">Definition</span>

## Module^[가군]

**Left $R$-module**^[왼쪽 $R$-가군]: 

Given a ring^[환] $R$ with identity, a **left $R$-module** is an abelian group $(M, +)$ with scalar multiplication^[스칼라 곱셈]:

$$R \times M \to M, \quad (r, m) \mapsto rm$$

satisfying:

1. **Associativity**^[결합법칙]: $r(sm) = (rs)m$ for all $r, s \in R, m \in M$
2. **Identity**^[항등원]: $1_R \cdot m = m$ for all $m \in M$
3. **Distributivity**^[분배법칙] (over $M$): $r(m_1 + m_2) = rm_1 + rm_2$
4. **Distributivity** (over $R$): $(r + s)m = rm + sm$

**표기**: $M$ is an $R$-module, or $_R M$

---

## Right Module^[오른쪽 가군]

**Right $R$-module**: Abelian group $M$ with scalar multiplication

$$M \times R \to M, \quad (m, r) \mapsto mr$$

satisfying analogous axioms

**표기**: $M_R$

**주의**: For non-commutative rings, left $\neq$ right!

---

## Bimodule^[양가군]

**$(R, S)$-bimodule**: Abelian group $M$ that is both:
- Left $R$-module
- Right $S$-module

with compatibility: $(rm)s = r(ms)$ for all $r \in R, m \in M, s \in S$

**표기**: $_R M_S$

---

## Submodule^[부분가군]

**Submodule**^[부분가군]: Subset $N \subseteq M$ that is:
1. Subgroup of $(M, +)$
2. Closed under scalar multiplication: $r \in R, n \in N \Rightarrow rn \in N$

**표기**: $N \leq M$ or $N \subseteq_R M$

**Example**: Ideals are submodules of $R$ (viewed as $R$-module over itself)

---

## Module Homomorphism^[가군 준동형사상]

**$R$-module homomorphism**^[가군 준동형사상]: Function $f: M \to N$ between $R$-modules such that:

1. **Additive**: $f(m_1 + m_2) = f(m_1) + f(m_2)$
2. **$R$-linear**: $f(rm) = rf(m)$ for all $r \in R, m \in M$

**표기**: $f \in \text{Hom}_R(M, N)$

**Kernel**^[핵]: $\ker(f) = \{m \in M : f(m) = 0\}$ (submodule of $M$)

**Image**^[상]: $\text{im}(f) = \{f(m) : m \in M\}$ (submodule of $N$)

**Isomorphism**^[동형사상]: Bijective homomorphism (invertible)

**표기**: $M \cong N$ (as $R$-modules)

---

## Quotient Module^[몫가군]

For submodule $N \leq M$:

**Quotient module**^[몫가군]: $M/N = \{m + N : m \in M\}$

**Operations**:
- Addition: $(m_1 + N) + (m_2 + N) = (m_1 + m_2) + N$
- Scalar multiplication: $r(m + N) = rm + N$

**정리** (First Isomorphism Theorem):

$$M/\ker(f) \cong \text{im}(f)$$

for any homomorphism $f: M \to N$

---

## Free Module^[자유 가군]

**Free module**^[자유 가군]: $R$-module $F$ with **basis**^[기저] $\{b_i\}_{i \in I}$

Every element uniquely written as:

$$m = \sum_{i \in I} r_i b_i \quad (r_i \in R, \text{ finitely many non-zero})$$

**표기**: $F \cong \bigoplus_{i \in I} R$ or $F \cong R^{(I)}$

**Rank**^[계수]: Cardinality of basis (if well-defined)

**주의**: Unlike vector spaces, not all modules have bases!

---

## Finitely Generated Module^[유한생성 가군]

**Finitely generated**^[유한생성]: $\exists$ finite set $\{m_1, \ldots, m_n\}$ such that

$$M = Rm_1 + Rm_2 + \cdots + Rm_n = \left\{\sum_{i=1}^n r_i m_i : r_i \in R\right\}$$

**Generators**^[생성원]: $\{m_1, \ldots, m_n\}$

**Example**: Every finite-dimensional vector space is finitely generated

**주의**: Finitely generated $\not\Rightarrow$ free!

---

## Torsion^[비틀림]

For $R$ an integral domain:

**Torsion element**^[비틀림 원소]: $m \in M$ such that $\exists r \in R \setminus \{0\}$ with $rm = 0$

**Torsion submodule**^[비틀림 부분가군]:

$$\text{Tor}(M) = \{m \in M : \exists r \neq 0, \, rm = 0\}$$

**Torsion-free**^[비틀림 없는]: $\text{Tor}(M) = \{0\}$

**Torsion module**^[비틀림 가군]: $\text{Tor}(M) = M$

---

# <span class="header-properties">Properties</span>

## Basic Properties

### Trivial Actions

For any $R$-module $M$:

1. $0_R \cdot m = 0_M$ for all $m \in M$
2. $r \cdot 0_M = 0_M$ for all $r \in R$
3. $(-r)m = -(rm) = r(-m)$

**증명**: Using distributivity

$(0_R + 0_R)m = 0_R m \Rightarrow 0_R m + 0_R m = 0_R m \Rightarrow 0_R m = 0_M$ ✓

## Isomorphism Theorems

### First Isomorphism Theorem

**정리**: For $R$-module homomorphism $f: M \to N$:

$$M/\ker(f) \cong \text{im}(f)$$

### Second Isomorphism Theorem

**정리**: For submodules $N, K \leq M$:

$$(N + K)/K \cong N/(N \cap K)$$

### Third Isomorphism Theorem

**정리**: For submodules $K \subseteq N \subseteq M$:

$$(M/K)/(N/K) \cong M/N$$

### Correspondence Theorem

**정리**: Submodules of $M/N$ correspond bijectively to submodules of $M$ containing $N$

## Direct Sum and Product

### Direct Sum^[직합]

For $R$-modules $M_1, \ldots, M_n$:

$$M_1 \oplus M_2 \oplus \cdots \oplus M_n$$

**Elements**: Tuples $(m_1, \ldots, m_n)$ with $m_i \in M_i$

**Operations**: Component-wise

### Infinite Direct Sum vs Product

**Direct sum**: Finite support

$$\bigoplus_{i \in I} M_i = \{(m_i) : \text{finitely many } m_i \neq 0\}$$

**Direct product**: All components

$$\prod_{i \in I} M_i = \{(m_i) : m_i \in M_i\}$$

**관계**: $\bigoplus_{i \in I} M_i \subseteq \prod_{i \in I} M_i$ (equality for finite $I$)

## Tensor Product^[텐서곱]

For $R$-modules $M, N$:

**Tensor product**^[텐서곱]: $M \otimes_R N$

**Universal property**: Bilinear maps $M \times N \to P$ correspond to linear maps $M \otimes_R N \to P$

**Properties**:
1. $R \otimes_R M \cong M$
2. $(M \oplus N) \otimes_R P \cong (M \otimes_R P) \oplus (N \otimes_R P)$
3. Right exact functor: $- \otimes_R N$

## Flatness^[평탄성]

**Flat module**^[평탄 가군]: $R$-module $M$ such that $- \otimes_R M$ is exact functor

**정리**: Following are flat over any ring:
- Free modules
- Projective modules
- Localization $S^{-1}R$ as $R$-module

**Example**: $\mathbb{Q}$ is flat as $\mathbb{Z}$-module

## Projective and Injective Modules

### Projective Module^[사영 가군]

**Projective**^[사영]: $P$ satisfies lifting property

For every surjective $g: M \to N$ and $f: P \to N$, $\exists h: P \to M$ with $g \circ h = f$

**정리**: TFAE:
1. $P$ is projective
2. $P$ is direct summand of free module
3. Every short exact sequence $0 \to A \to B \to P \to 0$ splits

### Injective Module^[단사 가군]

**Injective**^[단사]: $I$ satisfies extension property

For every injective $g: M \to N$ and $f: M \to I$, $\exists h: N \to I$ with $h \circ g = f$

**정리**: Every module embeds in injective module

**Example**: $\mathbb{Q}/\mathbb{Z}$ is injective $\mathbb{Z}$-module

---

# <span class="header-theorem">Theorems</span>

## Structure Theorem for Finitely Generated Modules over PID

**정리**: Let $R$ be a PID, $M$ a finitely generated $R$-module. Then:

$$M \cong R^r \oplus R/(d_1) \oplus R/(d_2) \oplus \cdots \oplus R/(d_k)$$

where $d_1 | d_2 | \cdots | d_k$ (invariant factors^[불변 인수])

**Alternative form** (primary decomposition):

$$M \cong R^r \oplus R/(p_1^{e_1}) \oplus \cdots \oplus R/(p_m^{e_m})$$

where $p_i$ are primes

**Special case**: Fundamental Theorem of Finitely Generated Abelian Groups (when $R = \mathbb{Z}$)

## Nakayama's Lemma^[나카야마 보조정리]

**정리** (**Nakayama**):

Let $R$ be commutative ring, $I$ an ideal contained in Jacobson radical, $M$ finitely generated $R$-module

If $IM = M$, then $M = 0$

**Corollary**: If $IM = M$ and $M$ finitely generated, then $\exists r \in 1 + I$ with $rM = 0$

**Application**: Checking linear independence, minimal generating sets

## Chinese Remainder Theorem for Modules

**정리**: Let $I_1, \ldots, I_n$ be pairwise coprime ideals in commutative ring $R$

$$R/(I_1 \cap \cdots \cap I_n) \cong R/I_1 \oplus \cdots \oplus R/I_n$$

**Generalization**: For any $R$-module $M$:

$$M/(I_1 \cap \cdots \cap I_n)M \cong M/I_1M \oplus \cdots \oplus M/I_nM$$

## Hilbert Basis Theorem^[힐베르트 기저 정리]

**정리**: If $R$ is Noetherian**^[뇌터] ring, then $R[x]$ is Noetherian

**의미**: Polynomial ring over Noetherian ring is Noetherian

**Corollary**: $k[x_1, \ldots, x_n]$ is Noetherian for field $k$

---

# <span class="header-examples">Examples</span>

## Example 1: Vector Spaces as Modules

**Vector space** $V$ over field $k$ = $k$-module

**Why**: Fields are rings, all axioms satisfied

**Special property**: Every $k$-module is **free**!

**Basis**: Every vector space has a basis (requires Axiom of Choice)

## Example 2: Abelian Groups as $\mathbb{Z}$-modules

**Every abelian group** $G$ is a $\mathbb{Z}$-module

**Scalar multiplication**: $n \cdot g = \underbrace{g + g + \cdots + g}_{n \text{ times}}$

**Properties**:
- Subgroups = Submodules
- Group homomorphisms = $\mathbb{Z}$-module homomorphisms
- Quotient groups = Quotient modules

**의미**: Theory of $\mathbb{Z}$-modules = Theory of abelian groups!

## Example 3: Ideals as Modules

**Left ideal** $I \subseteq R$ is left $R$-module

**Scalar multiplication**: Ring multiplication

**Right ideal** = Right $R$-module

**Two-sided ideal** = $(R, R)$-bimodule

## Example 4: $\mathbb{Z}/n\mathbb{Z}$ as $\mathbb{Z}$-module

$$M = \mathbb{Z}/n\mathbb{Z}$$

**Properties**:
- Finitely generated: Generated by $\overline{1}$
- NOT free (has torsion)
- Torsion module: $n \cdot m = 0$ for all $m$
- Cyclic module

**Annihilator**: $\text{Ann}(M) = n\mathbb{Z}$

## Example 5: $\mathbb{Q}$ as $\mathbb{Z}$-module

$$M = \mathbb{Q} \text{ (as abelian group)}$$

**Properties**:
- NOT finitely generated!
  - Reason: Any finite set generates countable subgroup, but $\mathbb{Q}$ contains all rationals
- Torsion-free: No non-zero element killed by non-zero integer
- Divisible: For all $q \in \mathbb{Q}$, $n \neq 0$, $\exists q' \in \mathbb{Q}$ with $nq' = q$
- Injective $\mathbb{Z}$-module

## Example 6: Polynomial Ring $k[x]$ as $k[x]$-module

**$k[x]$ as module over itself**:

$$M = k[x]$$

**Properties**:
- Free module: Basis $\{1\}$
- Principal ideal domain
- Every ideal is free rank-1 submodule

**Submodules**: Ideals of $k[x]$, all principal: $(f(x))$ for $f \in k[x]$

## Example 7: Functions as Modules

**$C^\infty(\mathbb{R})$ = Smooth functions $\mathbb{R} \to \mathbb{R}$**

$$M = C^\infty(\mathbb{R})$$

**Module over**: $R = C^\infty(\mathbb{R})$ (ring under pointwise operations)

**Scalar multiplication**: $(f \cdot g)(x) = f(x) \cdot g(x)$

**Application**: Differential equations, differential geometry

## Example 8: Group Representation as Module

**Representation**: Group homomorphism $\rho: G \to \text{GL}(V)$

**View as module**: $V$ is $k[G]$-module

where $k[G]$ = group algebra

**Scalar multiplication**: $\left(\sum a_g g\right) \cdot v = \sum a_g \rho(g)(v)$

**Connection**: Representation theory = Module theory over $k[G]$

## Example 9: Non-free Module

**$M = \mathbb{Z}/2\mathbb{Z}$ as $\mathbb{Z}$-module**

**Claim**: NOT free

**Proof**: 
- If free with basis $\{b\}$, then $m = nb$ for unique $n \in \mathbb{Z}$
- But $2 \cdot \overline{1} = \overline{0}$
- In free module, $2b = 0 \Rightarrow b = 0$ (contradiction) ✗

## Example 10: Module Without Basis

**$M = \mathbb{Z}/6\mathbb{Z}$ as $\mathbb{Z}$-module**

**Cannot be free**:
- Has torsion: $6m = 0$ for all $m$
- Free modules are torsion-free

**But finitely generated**: Generated by $\overline{1}$

**Structure**: $\mathbb{Z}/6\mathbb{Z} \cong \mathbb{Z}/2\mathbb{Z} \oplus \mathbb{Z}/3\mathbb{Z}$ (by CRT)

---

# <span class="header-remark">Remark</span>

## Modules vs Vector Spaces

**Similarity**: Modules generalize vector spaces

| Vector Spaces | Modules |
|---------------|---------|
| Over field $k$ | Over ring $R$ |
| Always have basis | May not have basis |
| Dimension well-defined | Rank may not exist |
| Always free | May have torsion |
| Structure simple | Can be very complex |

**Key difference**: Fields are "nicer" than rings (division possible)

## Why Study Modules?

### 1. Generalization
Vector spaces are too restrictive - modules allow richer theory

### 2. Natural Examples
- Abelian groups = $\mathbb{Z}$-modules
- Ideals = Modules over ring itself
- Representations = Modules over group algebras

### 3. Homological Algebra
- Ext, Tor functors
- Derived categories
- Cohomology theories

### 4. Algebraic Geometry
- Sheaves of modules
- Vector bundles
- Coherent sheaves

## Categories of Modules

**$R$-Mod**: Category of left $R$-modules

**Properties**:
- Abelian category
- Has kernels, cokernels
- Has direct sums, direct products
- Enough projectives and injectives

**Functors**:
- $\text{Hom}_R(M, -)$: Left exact
- $M \otimes_R -$: Right exact
- Direct sum: Exact

## Noetherian and Artinian Modules

### Noetherian Module

**Noetherian**^[뇌터]: Ascending chain condition (ACC)

Every ascending chain of submodules stabilizes:

$$M_1 \subseteq M_2 \subseteq M_3 \subseteq \cdots \Rightarrow \exists N: M_N = M_{N+1} = \cdots$$

**Equivalent**: Every submodule is finitely generated

### Artinian Module

**Artinian**^[아르틴]: Descending chain condition (DCC)

Every descending chain stabilizes

**Example**: $\mathbb{Z}/n\mathbb{Z}$ is both Noetherian and Artinian

**Non-example**: $\mathbb{Z}$ is Noetherian but not Artinian

## Simple and Semisimple Modules

### Simple Module^[단순 가군]

**Simple**^[단순] (or **irreducible**^[기약]): No proper non-zero submodules

**Only submodules**: $\{0\}$ and $M$ itself

**Example**: $\mathbb{Z}/p\mathbb{Z}$ for prime $p$ (as $\mathbb{Z}$-module)

### Semisimple Module^[반단순 가군]

**Semisimple**^[반단순]: Direct sum of simple modules

$$M = \bigoplus_{i \in I} S_i \quad \text{where each } S_i \text{ is simple}$$

**Equivalent**: Every submodule is direct summand

**Example**: Vector spaces (every $k$-module is semisimple)

## Length of Module^[가군의 길이]

**Composition series**^[합성 열]: Chain of submodules

$$0 = M_0 \subsetneq M_1 \subsetneq \cdots \subsetneq M_n = M$$

where each $M_i/M_{i-1}$ is simple

**Length**^[길이]: $\ell(M) = n$ if composition series exists

**Jordan-Hölder Theorem**: Length is well-defined (independent of series)

**Example**: $\ell(\mathbb{Z}/p^n\mathbb{Z}) = n$ (as $\mathbb{Z}$-module)

## Localization of Modules

For multiplicative set $S \subseteq R$:

**Localized module**: $S^{-1}M$

**Elements**: Equivalence classes $\frac{m}{s}$ where $m \in M, s \in S$

**Module over**: $S^{-1}R$

**Properties**:
- Exact functor
- $(S^{-1}R) \otimes_R M \cong S^{-1}M$

**Example**: $\mathbb{Q}$ is localization of $\mathbb{Z}$ at $S = \mathbb{Z} \setminus \{0\}$

## Applications

### 1. Representation Theory

**Group representations** = Modules over group algebra $k[G]$

**Character theory**: Study modules via traces

**Decomposition**: Into irreducible representations (simple modules)

### 2. Commutative Algebra

**Ideal theory**: Ideals as modules

**Primary decomposition**: Modules over Noetherian rings

**Depth, dimension**: Homological invariants

### 3. Homological Algebra

**Derived functors**: Ext, Tor

**Resolutions**: Projective, injective

**Spectral sequences**: Computing homology

### 4. Algebraic Geometry

**Sheaves**: Sheaves of $\mathcal{O}_X$-modules

**Coherent sheaves**: Correspond to finitely generated modules

**Vector bundles**: Locally free sheaves

### 5. Algebraic Topology

**Homology groups**: Modules over ring (often $\mathbb{Z}$)

**Cohomology rings**: Module structure over cohomology

## Historical Development

**19th century**: 
- Dedekind: Ideals in number theory
- Noether: Abstract approach to module theory

**Early 20th century**:
- Artin: Artinian modules
- Noether: Noetherian modules, Basis theorem

**Mid 20th century**:
- Cartan-Eilenberg: Homological algebra
- Grothendieck: Category theory, schemes

**Modern**:
- Representation theory
- Derived categories
- Noncommutative geometry

## 관련 개념

- [[Ring Theory]]: Base ring structure
- [[Vector Space]]: Special case (module over field)
- [[Abelian Group]]: $\mathbb{Z}$-modules
- [[Homomorphism]]: Module homomorphisms
- [[Tensor Product]]: Combines modules
- [[Exact Sequence]]: Module sequences
- [[Projective Module]]: Lifting property
- [[Injective Module]]: Extension property
- [[Chain Complex]]: Sequences of modules
- [[Derived Functor]]: Ext and Tor

