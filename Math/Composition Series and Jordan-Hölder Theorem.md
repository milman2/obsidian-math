# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Normal Subgroup]]
- [[Simple Group]]
- [[Quotient Group, Factor Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups
- Isaacs, Finite Group Theory

---

# <span class="header-definition">Definition</span>

## Composition Series^[합성 열]

**Composition series**^[합성 열] for group $G$:

$$\{e\} = G_0 \triangleleft G_1 \triangleleft \cdots \triangleleft G_n = G$$

where each **factor group**^[인수군] $G_{i+1}/G_i$ is **simple**^[단순]

**의미**: Maximal normal series (cannot refine further)

### 조건

1. **Normal subgroups**: $G_i \triangleleft G_{i+1}$ for all $i$
2. **Simple factors**: $G_{i+1}/G_i$ simple (no nontrivial normal subgroups)
3. **Proper**: $G_i \neq G_{i+1}$ for all $i$

자세한 내용은 [[Normal Subgroup]], [[Simple Group]] 참조

## Composition Factors^[합성 인수]

**Composition factors**^[합성 인수]:

$$G_1/G_0, \; G_2/G_1, \; \ldots, \; G_n/G_{n-1}$$

**의미**: Simple quotients in composition series

**Important**: These are the "building blocks" of $G$

## Subnormal Series^[준정규 열]

**Subnormal series**^[준정규 열]:

$$\{e\} = H_0 \triangleleft H_1 \triangleleft \cdots \triangleleft H_m = G$$

**차이**: Each $H_i$ normal in $H_{i+1}$ (not necessarily in $G$)

**Composition series**: Special case where factors simple

## Normal Series^[정규 열]

**Normal series**^[정규 열]:

$$\{e\} = N_0 \triangleleft N_1 \triangleleft \cdots \triangleleft N_k = G$$

where each $N_i \triangleleft G$ (normal in **entire** $G$)

**더 강한 조건**: Normal series $\Rightarrow$ Subnormal series

## Refinement^[세분화]

Series $(H_i)$ is **refinement**^[세분화] of $(K_j)$ if

$$\{K_j\} \subseteq \{H_i\}$$

**의미**: Insert more subgroups between existing ones

**예**: 

$$(K): \{e\} \triangleleft K \triangleleft G$$

refined to

$$(H): \{e\} \triangleleft H_1 \triangleleft H_2 \triangleleft K \triangleleft G$$

---

# <span class="header-properties">Properties</span>

## Existence

**정리**: Every finite group has composition series

**증명**: By induction on $|G|$
- If $G$ simple: $\{e\} \triangleleft G$ - If not: $\exists$ proper normal $N$ → apply induction to $G/N$ 
자세한 내용은 [[Simple Group]] 참조

## Uniqueness (Jordan-Hölder)

**정리**: Composition factors are **unique** up to order and isomorphism

**의미**: Different composition series have same factors (possibly reordered)

자세한 내용은 [[Jordan-Hölder Theorem]] (아래) 참조

## Simple Factors

**정리**: $G_{i+1}/G_i$ simple $\Leftrightarrow$ no proper normal subgroup of $G_{i+1}$ strictly contains $G_i$

**의미**: Cannot refine further

## Infinite Groups

**주의**: Not all infinite groups have composition series!

**예**: $\mathbb{Z}$ has NO composition series

$$\{0\} \triangleleft \mathbb{Z}$$

$\mathbb{Z}$ not simple, but any proper subgroup $n\mathbb{Z}$ → $\mathbb{Z}/n\mathbb{Z}$ not simple (unless $n$ prime)

**Solvable**: Use derived series instead

자세한 내용은 [[Solvable Group]] 참조

## Length

**Length**^[길이] of composition series: $n$ (number of factors)

**정리**: All composition series of $G$ have same length (Jordan-Hölder)

---

# <span class="header-theorem">Theorem</span>

## Jordan-Hölder Theorem

**정리**: If $G$ has composition series

$$\{e\} = G_0 \triangleleft G_1 \triangleleft \cdots \triangleleft G_n = G$$

$$\{e\} = H_0 \triangleleft H_1 \triangleleft \cdots \triangleleft H_m = G$$

Then:
1. $n = m$ (same length)
2. $\exists$ permutation $\sigma$ : $G_{i+1}/G_i \cong H_{\sigma(i)+1}/H_{\sigma(i)}$

**의미**: Composition factors **uniquely determined** (up to order, isomorphism)

### 비유

**메타포**: Prime factorization

$$n = p_1 \cdots p_k$$

**Fundamental Theorem of Arithmetic**: Primes unique up to order

**Jordan-Hölder**: Simple factors unique up to order

**차이**: Groups don't form unique product (structure matters!)

자세한 내용은 [[Simple Group]] 참조

## Schreier Refinement Theorem

**정리**: Any two subnormal series have **equivalent refinements**

**의미**: Can insert subgroups to make factors isomorphic

**Jordan-Hölder**: Corollary (composition series are refinements of each other)

## Zassenhaus Butterfly Lemma

**정리**: If $A \triangleleft A^*$ and $B \triangleleft B^*$ subgroups of $G$,

$$\frac{A(A^* \cap B)}{A(A^* \cap B^*)} \cong \frac{B(B^* \cap A)}{B(B^* \cap A^*)}$$

**의미**: Technical lemma for Schreier refinement

**Proof**: Construct isomorphism via homomorphisms 
---

# <span class="header-examples">Examples</span>

## Example 1: Cyclic Groups

**$\mathbb{Z}/p^n\mathbb{Z}$ (p prime)**:

$$\{0\} \triangleleft p^{n-1}\mathbb{Z}/p^n\mathbb{Z} \triangleleft \cdots \triangleleft p\mathbb{Z}/p^n\mathbb{Z} \triangleleft \mathbb{Z}/p^n\mathbb{Z}$$

**Factors**: Each $\cong \mathbb{Z}/p\mathbb{Z}$ (simple)

**Length**: $n$

자세한 내용은 [[Cyclic Group]] 참조

## Example 2: $\mathbb{Z}/12\mathbb{Z}$

**Composition series**:

$$\{0\} \triangleleft \langle 6 \rangle \triangleleft \langle 2 \rangle \triangleleft \mathbb{Z}/12\mathbb{Z}$$

**Factors**:
- $\langle 6 \rangle / \{0\} \cong \mathbb{Z}/2\mathbb{Z}$
- $\langle 2 \rangle / \langle 6 \rangle \cong \mathbb{Z}/3\mathbb{Z}$
- $\mathbb{Z}/12\mathbb{Z} / \langle 2 \rangle \cong \mathbb{Z}/2\mathbb{Z}$

**Alternative series**:

$$\{0\} \triangleleft \langle 4 \rangle \triangleleft \langle 2 \rangle \triangleleft \mathbb{Z}/12\mathbb{Z}$$

**Factors**: $\mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/3\mathbb{Z}$ (same up to order!)

## Example 3: $S_4$

$$\{e\} \triangleleft V_4 \triangleleft A_4 \triangleleft S_4$$

**Factors**:
- $V_4 / \{e\} \cong V_4$ (NOT simple!) ✗

Need refinement:

$$\{e\} \triangleleft \langle (12)(34) \rangle \triangleleft V_4 \triangleleft A_4 \triangleleft S_4$$

**Factors**:
- $\mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/3\mathbb{Z}, \mathbb{Z}/2\mathbb{Z}$

자세한 내용은 [[Symmetric Group]], [[Alternating Group]] 참조

## Example 4: Simple Groups

**$G$ simple**: 

$$\{e\} \triangleleft G$$

**Only composition series**: Length 1

**Factors**: $G$ itself

**예**: $A_5, \mathbb{Z}/p\mathbb{Z}$

자세한 내용은 [[Simple Group]] 참조

## Example 5: Direct Product

**$\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z} \cong \mathbb{Z}/6\mathbb{Z}$**:

$$\{(0,0)\} \triangleleft \mathbb{Z}/2\mathbb{Z} \times \{0\} \triangleleft \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$$

**Factors**: $\mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/3\mathbb{Z}$

**Alternative**:

$$\{(0,0)\} \triangleleft \{0\} \times \mathbb{Z}/3\mathbb{Z} \triangleleft \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$$

**Factors**: $\mathbb{Z}/3\mathbb{Z}, \mathbb{Z}/2\mathbb{Z}$ (same up to order!)

자세한 내용은 [[Direct Product]] 참조

## Example 6: Dihedral Group $D_4$

$$D_4 = \langle r, s \mid r^4, s^2, srs^{-1} = r^{-1} \rangle$$

**Composition series**:

$$\{e\} \triangleleft \langle r^2 \rangle \triangleleft \langle r \rangle \triangleleft D_4$$

**Factors**: $\mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/2\mathbb{Z}$

자세한 내용은 [[Dihedral Group]] 참조

---

# <span class="header-proof">Proof</span>

## Jordan-Hölder Theorem (Sketch)

**Proof by induction** on $|G|$ and length

**Base**: $G$ simple → trivial 
**Step**: Suppose $G$ not simple

Two composition series:

$$\{e\} \triangleleft \cdots \triangleleft G_{n-1} \triangleleft G$$

$$\{e\} \triangleleft \cdots \triangleleft H_{m-1} \triangleleft G$$

**Case 1**: $G_{n-1} = H_{m-1}$

Apply induction to $G_{n-1}$ 
**Case 2**: $G_{n-1} \neq H_{m-1}$

**Key**: $G_{n-1} H_{m-1} = G$ (both maximal normal)

Use **Zassenhaus Butterfly Lemma**:

$$G / G_{n-1} \cong H_{m-1} / (G_{n-1} \cap H_{m-1})$$

$$G / H_{m-1} \cong G_{n-1} / (G_{n-1} \cap H_{m-1})$$

Both simple! Now apply induction to $G_{n-1} \cap H_{m-1}$ 
## Schreier Refinement (Idea)

**Given**: Two subnormal series

**Goal**: Insert subgroups to make equivalent

**Method**: Use Zassenhaus lemma iteratively

**Result**: Factors become isomorphic (with duplicates)

**Jordan-Hölder**: Remove duplicates (simple factors)

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Composition Series = "Breaking into simple pieces"**

### 메타포: 소인수분해

**Prime factorization**: $12 = 2^2 \cdot 3$

**Composition factors**: $\mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/3\mathbb{Z}$

**Jordan-Hölder**: "Fundamental Theorem" for groups

**차이**: 
- Numbers: Unique product $2 \times 2 \times 3 = 12$
- Groups: Structure matters! (not just product)

### 메타포: 레고 분해

**Group**: 복잡한 구조물

**Composition series**: 기본 블록들로 분해

**Simple factors**: 더 이상 나눌 수 없는 기본 블록

**Jordan-Hölder**: 어떻게 분해하든 같은 블록들!

## 왜 중요한가?

### 1. Classification

**Simple groups**: Building blocks

**Finite simple groups**: Completely classified!
- Cyclic: $\mathbb{Z}/p\mathbb{Z}$
- Alternating: $A_n$ (n≥5)
- Lie type
- Sporadic: 26 groups

자세한 내용은 [[Simple Group]] 참조

### 2. Structure Theory

**Understand $G$**: Study composition factors

**Properties**: Inherited from simple factors?

### 3. Solvability

**Solvable groups**: All factors abelian

$$G \text{ solvable } \Leftrightarrow \text{ all composition factors cyclic of prime order}$$

자세한 내용은 [[Solvable Group]] 참조

### 4. Algorithmic

**Composition series**: Computable (finite groups)

**GAP, Magma**: Implement algorithms

### 5. Galois Theory

**Galois groups**: Composition series ↔ field tower

**Solvability by radicals**: Galois group solvable

자세한 내용은 [[Galois Theory]] 참조

## Composition vs Derived Series

| | **Composition Series** | **Derived Series** |
|---|---|---|
| **정의** | Simple factors | Commutator subgroups |
| **존재** | Not always (infinite) | Always |
| **Factors** | Simple groups | Abelian groups |
| **Unique** | Yes (Jordan-Hölder) | No (fixed series) |
| **Solvable** | All factors abelian | Terminates at $\{e\}$ |

**관계**: Solvable ↔ derived series terminates ↔ composition factors abelian

자세한 내용은 [[Solvable Group]] 참조

## 계산 방법

### Composition Series 찾기

**Step 1**: Find maximal normal subgroup $N < G$

**Step 2**: Check if $G/N$ simple

**Step 3**: Recursively find series for $N$

**Step 4**: Concatenate

### Verification

**Check 1**: Each $G_i \triangleleft G_{i+1}$

**Check 2**: Each $G_{i+1}/G_i$ simple

**Check 3**: Covers entire group

### Software

**GAP**: `CompositionSeries(G)`

**Magma**: `CompositionSeries(G)`

## 표기법

| 표기 | 의미 |
|------|------|
| $\{e\} = G_0 \triangleleft \cdots \triangleleft G_n = G$ | Composition series |
| $G_{i+1}/G_i$ | Composition factor |
| $n$ | Length of series |
| $G \triangleleft H$ | $G$ normal in $H$ |

## Common Pitfall^[흔한 실수]

### 1. Not all series are composition

Must have **simple** factors!

**예**: $\{e\} \triangleleft V_4 \triangleleft A_4$ not composition ($V_4$ not simple in $A_4$)

### 2. Infinite groups

Not all have composition series!

**예**: $\mathbb{Z}, \mathbb{Q}$ no composition series

### 3. Factors vs Subgroups

**Factors**: Quotients $G_{i+1}/G_i$ (unique)

**Subgroups**: $G_i$ themselves (not unique!)

### 4. Uniqueness is up to ORDER

$$\mathbb{Z}/6\mathbb{Z}: \mathbb{Z}/2\mathbb{Z}, \mathbb{Z}/3\mathbb{Z}$$

or

$$\mathbb{Z}/3\mathbb{Z}, \mathbb{Z}/2\mathbb{Z}$$

Same factors, different order!

### 5. Simple ≠ Cyclic

**Simple**: No proper normal subgroups

**Cyclic**: Generated by one element

**관계**: Simple abelian groups are cyclic of prime order

But $A_5$ simple, not cyclic!

자세한 내용은 [[Simple Group]] 참조

## 응용 분야

**Group Theory**:
- Classification
- Structure theorems

**Galois Theory**:
- Solvability by radicals
- Field towers

**Number Theory**:
- Class field theory

**Topology**:
- Fundamental groups
- Covering spaces

**Physics**:
- Symmetry breaking
- Particle physics

## 역사적 맥락

**Camille Jordan** (1870): First version

**Otto Hölder** (1889): Refined and proved

**Emil Artin** (1942): Modern formulation

**Classification** (1955-2004): All finite simple groups!

## 관련 개념

- [[Simple Group]]: Building blocks
- [[Solvable Group]]: Abelian factors
- [[Normal Subgroup]]: Required for series
- [[Quotient Group, Factor Group]]: Factors
- [[Isomorphism Theorem]]: Used in proof

## 추가 학습 주제

**기초**:
- Definition
- Examples
- Jordan-Hölder statement

**중급**:
- Proof of Jordan-Hölder
- Schreier refinement
- Zassenhaus lemma

**고급**:
- Classification of finite simple groups
- Chief series
- Principal series
- Krull-Schmidt theorem
- Module composition series

