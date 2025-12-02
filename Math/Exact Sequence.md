# <span class="header-prerequisite">Prerequisite</span>
- [[Group Theory]]
- [[Abelian Group]]
- [[Homomorphism]]
- [[Module Theory]]
- [[Kernel and Image]]

# <span class="header-reference">Reference</span>
- Rotman, An Introduction to Homological Algebra
- Weibel, An Introduction to Homological Algebra
- Lang, Algebra
- Hungerford, Algebra

---

# <span class="header-definition">Definition</span>

## Exact Sequence^[완전 수열]

**Exact sequence**^[완전 수열]는 abelian groups (또는 modules)와 homomorphisms의 sequence:

$$\cdots \to A_{n+1} \xrightarrow{f_{n+1}} A_n \xrightarrow{f_n} A_{n-1} \to \cdots$$

where **exactness condition**^[완전성 조건]:

$$\text{im}(f_{n+1}) = \ker(f_n) \quad \text{for all } n$$

**동치 조건**: $f_n \circ f_{n+1} = 0$ and every element in $\ker(f_n)$ comes from $A_{n+1}$

**의미**: "Output of one map = Input of next map"

---

## Short Exact Sequence^[짧은 완전 수열]

**Short exact sequence (SES)**^[짧은 완전 수열]:

$$0 \to A \xrightarrow{f} B \xrightarrow{g} C \to 0$$

**Exactness conditions**:

1. At $A$: $\text{im}(0) = \ker(f) \Rightarrow f$ is injective^[단사]
2. At $B$: $\text{im}(f) = \ker(g)$
3. At $C$: $\text{im}(g) = \ker(0) \Rightarrow g$ is surjective^[전사]

**해석**:
- $f: A \hookrightarrow B$ embeds $A$ as subgroup
- $g: B \twoheadrightarrow C$ quotients out by $A$
- $C \cong B/A$

**직관**: $B$는 $A$를 포함하고, $B$를 $A$로 나누면 $C$

---

## Long Exact Sequence^[긴 완전 수열]

**Long exact sequence (LES)**^[긴 완전 수열]: Infinite (or semi-infinite) exact sequence

**Example** (homology):

$$\cdots \to H_n(A) \to H_n(X) \to H_n(X, A) \xrightarrow{\partial} H_{n-1}(A) \to \cdots$$

**특징**:
- Connects different homology groups
- $\partial$: Connecting homomorphism^[연결 준동형사상]
- Powerful computational tool

---

## Split Exact Sequence^[분해 완전 수열]

Short exact sequence $0 \to A \xrightarrow{f} B \xrightarrow{g} C \to 0$ **splits**^[분해] if:

**Left split**: $\exists$ homomorphism $s: B \to A$ such that $s \circ f = \text{id}_A$

$$A \xrightarrow{f} B \xrightarrow[s]{\text{retraction}} A$$

**Right split**: $\exists$ homomorphism $t: C \to B$ such that $g \circ t = \text{id}_C$

$$C \xrightarrow{t} B \xrightarrow{g} C$$

**정리**: For abelian groups, left split $\Leftrightarrow$ right split

**결과**: If SES splits, then $B \cong A \oplus C$ (direct sum**^[직합])

---

# <span class="header-properties">Properties</span>

## Basic Properties

### Composition Zero

**정리**: In exact sequence, $f_n \circ f_{n+1} = 0$

**증명**: 
- $\text{im}(f_{n+1}) \subseteq \ker(f_n)$ by exactness
- Therefore $f_n(f_{n+1}(x)) = 0$ for all $x$ ✓

**의미**: "Composition of consecutive maps vanishes"

### Exactness at Single Point

Sequence is **exact at $A$**:

$$B \xrightarrow{f} A \xrightarrow{g} C$$

$$\Leftrightarrow \text{im}(f) = \ker(g)$$

## Short Exact Sequence Properties

### First Isomorphism Theorem Connection

**정리**: $0 \to A \xrightarrow{f} B \xrightarrow{g} C \to 0$ exact

$$\Rightarrow C \cong B/\text{im}(f) \cong B/A$$

(identifying $A$ with its image in $B$)

### Splitting Criterion

**정리** (Splitting Lemma):

For SES $0 \to A \xrightarrow{f} B \xrightarrow{g} C \to 0$, TFAE:

1. The sequence splits
2. $\exists$ retraction $s: B \to A$ with $s \circ f = \text{id}_A$
3. $\exists$ section $t: C \to B$ with $g \circ t = \text{id}_C$
4. $B \cong A \oplus C$

**For modules**: Also equivalent to "$C$ is projective" or "$A$ is injective"

### Non-splitting Example

**Example**: $0 \to \mathbb{Z} \xrightarrow{\times 2} \mathbb{Z} \to \mathbb{Z}/2\mathbb{Z} \to 0$

- Exact ✓
- Does NOT split ✗
- $\mathbb{Z} \not\cong \mathbb{Z} \oplus \mathbb{Z}/2\mathbb{Z}$

## Functoriality^[함자성]

### Functors Preserve Exactness

**Left exact functor**^[좌완전 함자]: Preserves exactness of

$$0 \to A \to B \to C$$

**Example**: $\text{Hom}(X, -)$ is left exact

**Right exact functor**^[우완전 함자]: Preserves exactness of

$$A \to B \to C \to 0$$

**Example**: $- \otimes N$ is right exact

**Exact functor**^[완전 함자]: Preserves all exact sequences

**Example**: Free abelian group functor

---

# <span class="header-theorem">Theorems</span>

## Five Lemma^[다섯 보조정리]

**정리** (**Five Lemma**):

Given commutative diagram with exact rows:

$$\begin{array}{ccccccccc}
A_1 & \xrightarrow{f_1} & A_2 & \xrightarrow{f_2} & A_3 & \xrightarrow{f_3} & A_4 & \xrightarrow{f_4} & A_5 \\
\downarrow{\alpha_1} && \downarrow{\alpha_2} && \downarrow{\alpha_3} && \downarrow{\alpha_4} && \downarrow{\alpha_5} \\
B_1 & \xrightarrow{g_1} & B_2 & \xrightarrow{g_2} & B_3 & \xrightarrow{g_3} & B_4 & \xrightarrow{g_4} & B_5
\end{array}$$

If $\alpha_1, \alpha_2, \alpha_4, \alpha_5$ are isomorphisms, then $\alpha_3$ is an isomorphism

**응용**: 많은 동형사상 증명의 핵심 도구

## Snake Lemma^[뱀 보조정리]

**정리** (**Snake Lemma**):

Given commutative diagram with exact rows:

$$\begin{array}{ccccccc}
& & A & \xrightarrow{f} & B & \xrightarrow{g} & C & \to 0 \\
& & \downarrow{\alpha} && \downarrow{\beta} && \downarrow{\gamma} \\
0 \to & A' & \xrightarrow{f'} & B' & \xrightarrow{g'} & C'
\end{array}$$

There exists a long exact sequence:

$$\ker(\alpha) \to \ker(\beta) \to \ker(\gamma) \xrightarrow{\delta} \text{coker}(\alpha) \to \text{coker}(\beta) \to \text{coker}(\gamma)$$

where $\text{coker}(h) = (\text{target of } h) / \text{im}(h)$

**의미**: Connecting homomorphism $\delta$ "snakes" through the diagram

**응용**: Derives long exact sequences from short exact sequences

## Nine Lemma^[아홉 보조정리]

**정리** (**Nine Lemma** / **$3 \times 3$ Lemma**):

Given commutative diagram where rows and columns are exact:

$$\begin{array}{ccccc}
& & 0 & & \\
& & \downarrow & & \\
0 & \to & A_1 & \xrightarrow{f_1} & B_1 & \to 0 \\
& & \downarrow{\alpha_1} & & \downarrow{\beta_1} \\
0 & \to & A_2 & \xrightarrow{f_2} & B_2 & \to 0 \\
& & \downarrow{\alpha_2} & & \downarrow{\beta_2} \\
& & A_3 & \xrightarrow{f_3} & B_3 \\
& & \downarrow & & \downarrow \\
& & 0 & & 0
\end{array}$$

If two rows are exact, the third is exact

**응용**: Diagram chasing arguments

## Four Lemma^[넷 보조정리]

**정리** (**Four Lemma**):

Given commutative diagram with exact rows:

$$\begin{array}{ccccccc}
A_1 & \xrightarrow{f_1} & A_2 & \xrightarrow{f_2} & A_3 & \xrightarrow{f_3} & A_4 \\
\downarrow{\alpha_1} && \downarrow{\alpha_2} && \downarrow{\alpha_3} && \downarrow{\alpha_4} \\
B_1 & \xrightarrow{g_1} & B_2 & \xrightarrow{g_2} & B_3 & \xrightarrow{g_3} & B_4
\end{array}$$

1. If $\alpha_1$ surjective, $\alpha_2, \alpha_4$ isomorphisms, then $\alpha_3$ surjective
2. If $\alpha_4$ injective, $\alpha_2, \alpha_1$ isomorphisms, then $\alpha_3$ injective

**의미**: Weaker version of Five Lemma

---

# <span class="header-examples">Examples</span>

## Example 1: Quotient Groups

**SES of groups**:

$$0 \to N \xrightarrow{i} G \xrightarrow{\pi} G/N \to 0$$

- $i$: Inclusion map (injective)
- $\pi$: Quotient map (surjective)
- $\ker(\pi) = N = \text{im}(i)$ ✓

**Exact at all points** ✓

## Example 2: Submodules

**SES of modules**: $M$ is $R$-module, $N \subseteq M$ submodule

$$0 \to N \xrightarrow{i} M \xrightarrow{\pi} M/N \to 0$$

**Universal construction** for quotients

## Example 3: Integers Modulo $n$

$$0 \to \mathbb{Z} \xrightarrow{\times n} \mathbb{Z} \xrightarrow{\text{mod } n} \mathbb{Z}/n\mathbb{Z} \to 0$$

- $\times n$: Multiplication by $n$
- Exact ✓
- Does NOT split (for $n > 1$)

## Example 4: Direct Sum Decomposition

**Split SES**:

$$0 \to A \xrightarrow{(a \mapsto (a, 0))} A \oplus B \xrightarrow{((a,b) \mapsto b)} B \to 0$$

- Splits ✓
- $A \oplus B \cong A \oplus B$ (trivially)

## Example 5: Long Exact Sequence in Homology

**LES of pair** $(X, A)$:

$$\cdots \to H_n(A) \xrightarrow{i_*} H_n(X) \xrightarrow{j_*} H_n(X, A) \xrightarrow{\partial} H_{n-1}(A) \to \cdots$$

- Fundamental tool in algebraic topology
- Derived from Snake Lemma

## Example 6: Exact Sequence of Vector Spaces

$$0 \to V_1 \xrightarrow{T_1} V_2 \xrightarrow{T_2} V_3 \to 0$$

For vector spaces (over field $k$):

**Dimension formula**:

$$\dim(V_2) = \dim(V_1) + \dim(V_3)$$

**Always splits**: $V_2 \cong V_1 \oplus V_3$

(Vector spaces are projective and injective)

## Example 7: Exponential Sequence

**Complex manifolds**:

$$0 \to \mathbb{Z} \to \mathcal{O} \xrightarrow{\exp(2\pi i -)} \mathcal{O}^* \to 0$$

- $\mathcal{O}$: Holomorphic functions
- $\mathcal{O}^*$: Non-vanishing holomorphic functions
- Exponential map

**Applications**: Line bundles, Picard group

## Example 8: Kummer Sequence

**Algebraic geometry**: For variety $X$ over field with $n$-th roots of unity:

$$0 \to \mu_n \to \mathbb{G}_m \xrightarrow{x \mapsto x^n} \mathbb{G}_m \to 0$$

- $\mu_n$: $n$-th roots of unity
- $\mathbb{G}_m$: Multiplicative group

**Applications**: Étale cohomology

---

# <span class="header-remark">Remark</span>

## Intuitive Understanding

**Exact sequence** = "Perfect fit"

$$A \xrightarrow{f} B \xrightarrow{g} C$$

- Everything $g$ kills comes from $A$
- Nothing extra in $\ker(g)$
- $\text{im}(f) = \ker(g)$ exactly

**SES**: $0 \to A \to B \to C \to 0$

Think: $B$ contains $A$, and $C$ is "what's left"

$$\boxed{B = A + C}$$

## Diagram Chasing^[다이어그램 추적]

**Technique**: Follow elements through commutative diagrams

**Steps**:
1. Start with element in some group
2. Apply homomorphisms
3. Use exactness: $\text{im} = \ker$
4. Use commutativity of diagram
5. Conclude desired property

**Example proof method**: Five Lemma, Snake Lemma

## Exactness vs Composition Zero

**Weaker condition**: $g \circ f = 0 \Leftrightarrow \text{im}(f) \subseteq \ker(g)$

**Exact**: $\text{im}(f) = \ker(g)$ (equality!)

**Chain complex**: Satisfies $\partial \circ \partial = 0$ but not exact

**Acyclic complex**: Chain complex that is exact (no homology)

## Splitting

**When does SES split?**

### Always splits:
- Vector spaces over field
- Free abelian groups (as subgroup of free group)
- Projective/injective modules

### May not split:
- General abelian groups
- Modules over rings
- Non-free groups

**Example not splitting**: $0 \to \mathbb{Z} \xrightarrow{\times 2} \mathbb{Z} \to \mathbb{Z}/2\mathbb{Z} \to 0$

## Exact Functors

**Not all functors preserve exactness!**

### Left exact only:
- $\text{Hom}(X, -)$
- Global sections functor
- Invariants functor

### Right exact only:
- $- \otimes_R M$
- Coinvariants functor

### Exact:
- Forgetful functors (usually)
- Direct sum/product
- Localization (for flat modules)

**Derived functors**: Ext, Tor measure failure of exactness

## Applications in Homological Algebra

### 1. Computing Homology/Cohomology

Long exact sequences:
- LES of pair in topology
- LES in group cohomology
- Mayer-Vietoris sequence

### 2. Extension Theory

**Extension problem**: Given $A, C$, find all $B$ such that

$$0 \to A \to B \to C \to 0$$

**Solution**: $\text{Ext}^1(C, A)$ classifies extensions

### 3. Derived Functors

**Construction**:
1. Take projective/injective resolution
2. Apply functor
3. Take homology

Results in long exact sequences

## Exact Triangles

**Triangulated categories**: Analog of exact sequences

$$A \to B \to C \to \Sigma A$$

where $\Sigma$ is suspension functor

**Example**: Derived categories, stable homotopy theory

## Short Five Lemma

**Corollary of Five Lemma**: Given commutative diagram with exact rows:

$$\begin{array}{ccccc}
0 \to A_1 & \to & A_2 & \to & A_3 \to 0 \\
\downarrow{\alpha} && \downarrow{\beta} && \downarrow{\gamma} \\
0 \to B_1 & \to & B_2 & \to & B_3 \to 0
\end{array}$$

If two of $\{\alpha, \beta, \gamma\}$ are isomorphisms, then the third is too

**Useful for proving isomorphisms**

## Horseshoe Lemma^[말편자 보조정리]

**Statement**: Given SES of complexes and projective resolutions of ends, can construct projective resolution of middle

**Applications**: Computing derived functors

## Historical Development

**Early 20th century**: 
- Algebraic topology (Poincaré, Alexander)
- Exactness implicit in homology theory

**1940s-1950s**:
- Eilenberg-MacLane: Homological algebra
- Cartan-Eilenberg: Systematic theory
- Serre: Spectral sequences

**Modern**:
- Derived categories (Verdier, Grothendieck)
- Triangulated categories
- $\infty$-categories

## Computational Techniques

### Method 1: Direct Verification
Check $\text{im}(f) = \ker(g)$ directly

### Method 2: Use Lemmas
- Five Lemma
- Snake Lemma
- Diagram chase

### Method 3: Spectral Sequences
For double complexes and filtered complexes

### Method 4: Computer Algebra
- Macaulay2
- Sage
- GAP

For concrete computations in specific categories

## Category Theory Perspective

**Definition**: In abelian category $\mathcal{A}$, sequence

$$A \xrightarrow{f} B \xrightarrow{g} C$$

is exact if $\ker(g) = \text{coim}(f)$ (or equivalently $\text{im}(f) = \ker(g)$)

**Generalization**: Can define exactness in any category with kernels and cokernels

## 관련 개념

- [[Chain Complex]]: Satisfies $\partial \circ \partial = 0$
- [[Homology Theory]]: Measures failure of exactness
- [[Derived Functor]]: Ext, Tor
- [[Spectral Sequence]]: Tool for computing homology
- [[Abelian Category]]: Natural setting
- [[Homomorphism]]: Maps in sequences
- [[Kernel and Image]]: Key to exactness
- [[Snake Lemma]]: Derives long exact sequences

