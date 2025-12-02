# <span class="header-prerequisite">Prerequisite</span>

- [[Vector Space]]
- [[Ring]]
- [[Field]]
- [[Bilinear Map]]
- [[Module]]

# <span class="header-reference">Reference</span>

- Dummit & Foote, *Abstract Algebra*
- Lang, *Algebra*
- Jacobson, *Lie Algebras*
- Humphreys, *Introduction to Lie Algebras and Representation Theory*

---

# <span class="header-definition">Definition</span>

## Algebra^[대수]

Field^[체] $F$ 위의 **algebra**^[대수] $A$는 다음을 만족하는 구조:

### 1. Vector Space Structure

$(A, +, \cdot)$는 $F$ 위의 vector space^[벡터 공간]

### 2. Multiplication Operation

**Algebra multiplication**^[대수 곱셈]: Bilinear map^[쌍선형 사상]

$$\mu: A \times A \to A, \quad (a, b) \mapsto ab$$

다음 조건을 만족:

**Bilinearity**^[쌍선형성]:
- **Left distributivity**: $(a + b)c = ac + bc$
- **Right distributivity**: $a(b + c) = ab + ac$
- **Compatibility with scalars**: $(\lambda a)b = \lambda(ab) = a(\lambda b)$ for $\lambda \in F$

**표기**: Often write $A$ instead of $(A, +, \cdot, \mu)$

---

## Unital Algebra^[단위원을 갖는 대수]

Algebra $A$가 **unital**^[단위원을 가진] (또는 **algebra with identity**^[항등원을 가진 대수])이다 $\Leftrightarrow$

$$\exists 1 \in A: \quad 1 \cdot a = a \cdot 1 = a \quad \forall a \in A$$

**주의**: $1 \neq 0$ (단, trivial algebra $A = \{0\}$ 제외)

**표준 가정**: 특별한 언급이 없으면 algebra는 unital이라고 가정

---

## Associative Algebra^[결합 대수]

Algebra $A$가 **associative**^[결합적]이다 $\Leftrightarrow$

$$\forall a, b, c \in A: \quad (ab)c = a(bc)$$

**의미**: 곱셈의 괄호 위치가 중요하지 않음

**예**: Matrix algebras, polynomial algebras

**반대**: Lie algebras, Jordan algebras는 비결합적

---

## Commutative Algebra^[가환 대수]

Algebra $A$가 **commutative**^[가환]이다 $\Leftrightarrow$

$$\forall a, b \in A: \quad ab = ba$$

**예**: $F[x]$ (polynomial algebra), $\mathbb{C}$ (as $\mathbb{R}$-algebra)

**비가환 예**: Matrix algebras ($n \geq 2$), quaternions

---

## Division Algebra^[나눗셈 대수]

Unital algebra $A$ (with $1 \neq 0$)가 **division algebra**^[나눗셈 대수]이다 $\Leftrightarrow$

$$\forall a \in A \setminus \{0\}, \; \exists a^{-1} \in A: \quad aa^{-1} = a^{-1}a = 1$$

**의미**: 0이 아닌 모든 원소가 곱셈 역원을 가짐

**예**: 
- $\mathbb{R}$, $\mathbb{C}$, $\mathbb{H}$ (quaternions)
- Frobenius Theorem: 실수 위의 finite-dimensional division algebra는 $\mathbb{R}$, $\mathbb{C}$, $\mathbb{H}$ 뿐

---

## Subalgebra^[부분대수]

Algebra $A$의 부분집합 $B \subseteq A$가 **subalgebra**^[부분대수]이다 $\Leftrightarrow$:

1. $B$는 $A$의 vector subspace^[부분 벡터 공간]
2. $B$는 곱셈에 대해 닫혀있음: $b_1, b_2 \in B \Rightarrow b_1 b_2 \in B$
3. (Unital인 경우) $1 \in B$

**예**: $\mathbb{R} \subseteq \mathbb{C}$ ($\mathbb{R}$-algebra로)

---

## Algebra Homomorphism^[대수 준동형사상]

$F$-algebras $A, B$ 사이의 **algebra homomorphism**^[대수 준동형사상]: 함수 $\phi: A \to B$로 다음을 만족:

1. **Additive**: $\phi(a_1 + a_2) = \phi(a_1) + \phi(a_2)$
2. **$F$-linear**: $\phi(\lambda a) = \lambda \phi(a)$ for $\lambda \in F$
3. **Multiplicative**: $\phi(ab) = \phi(a)\phi(b)$
4. (Unital인 경우) **Preserves identity**: $\phi(1_A) = 1_B$

**표기**: $\phi \in \text{Hom}_{\text{Alg}_F}(A, B)$

**Isomorphism**^[동형사상]: Bijective homomorphism

**표기**: $A \cong B$ (as $F$-algebras)

---

## Ideal in Algebra^[대수의 아이디얼]

Algebra $A$의 부분집합 $I \subseteq A$가 **(two-sided) ideal**^[양측 아이디얼]이다 $\Leftrightarrow$:

1. $I$는 vector subspace
2. $\forall a \in A, \forall x \in I: \quad ax \in I \text{ and } xa \in I$

**성질**: Ideal은 subalgebra가 아닐 수 있음 (항등원을 포함하지 않을 수 있음)

**Quotient algebra**^[몫 대수]: $A/I$ (자연스러운 algebra 구조)

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Algebra as Ring and Vector Space

Algebra $A$는 두 구조를 동시에 가짐:

**As ring**^[환으로서]: $(A, +, \cdot)$는 ring (단, 반드시 commutative ring은 아님)

**As vector space**^[벡터 공간으로서]: $(A, +, \cdot)$는 $F$-vector space

**Compatibility**: 이 두 구조가 bilinearity로 연결됨

### 2. Algebra as Module

**정리**: $F$-algebra $A$는 $F$-module

**의미**: Algebra = "module with multiplication"

### 3. Dimension

**Finite-dimensional algebra**^[유한 차원 대수]: $\dim_F(A) < \infty$

**Infinite-dimensional algebra**^[무한 차원 대수]: $\dim_F(A) = \infty$

**예**:
- $M_n(F)$: Finite-dimensional, $\dim = n^2$
- $F[x]$: Infinite-dimensional

### 4. Center of Algebra^[대수의 중심]

$$Z(A) = \{z \in A : za = az \text{ for all } a \in A\}$$

**성질**: $Z(A)$는 commutative subalgebra

**예**: $Z(M_n(F)) = F \cdot I_n$ (scalar matrices)

### 5. Unit Group^[단원군]

Unital algebra $A$에서:

$$A^\times = \{a \in A : \exists a^{-1}, \; aa^{-1} = a^{-1}a = 1\}$$

**Group of units**^[단원군]

**예**: $\text{GL}_n(F) = M_n(F)^\times$ (invertible matrices)

---

# <span class="header-examples">Examples</span>

## Example 1: Matrix Algebra $M_n(F)$

$$M_n(F) = \{n \times n \text{ matrices with entries in } F\}$$

**Vector space**: $\dim(M_n(F)) = n^2$

**Multiplication**: Matrix multiplication

**Properties**:
- Associative
- Unital: Identity = $I_n$
- **Non-commutative** for $n \geq 2$

**Center**: $Z(M_n(F)) = \{cI_n : c \in F\} \cong F$

---

## Example 2: Polynomial Algebra $F[x]$

$$F[x] = \{a_0 + a_1 x + \cdots + a_n x^n : a_i \in F, n \in \mathbb{N}\}$$

**Vector space**: Infinite-dimensional, basis $\{1, x, x^2, x^3, \ldots\}$

**Multiplication**: Polynomial multiplication

**Properties**:
- Associative
- Commutative
- Unital: Identity = $1$

**응용**: Polynomial rings, algebraic geometry

---

## Example 3: Complex Numbers $\mathbb{C}$ as $\mathbb{R}$-algebra

$$\mathbb{C} = \{a + bi : a, b \in \mathbb{R}\}$$

**Vector space**: $\dim_\mathbb{R}(\mathbb{C}) = 2$, basis $\{1, i\}$

**Multiplication**: $(a + bi)(c + di) = (ac - bd) + (ad + bc)i$

**Properties**:
- Associative
- Commutative
- Division algebra
- Field

---

## Example 4: Quaternions $\mathbb{H}$ as $\mathbb{R}$-algebra

$$\mathbb{H} = \{a + bi + cj + dk : a, b, c, d \in \mathbb{R}\}$$

**Basis**: $\{1, i, j, k\}$, $\dim_\mathbb{R}(\mathbb{H}) = 4$

**Multiplication rules**:

$$i^2 = j^2 = k^2 = ijk = -1$$

$$ij = k, \quad jk = i, \quad ki = j$$

$$ji = -k, \quad kj = -i, \quad ik = -j$$

**Properties**:
- Associative
- **Non-commutative**: $ij \neq ji$
- Division algebra
- NOT a field (not commutative)

**역사**: Hamilton (1843), first non-commutative division algebra

---

## Example 5: Exterior Algebra $\Lambda(V)$

For vector space $V$ over $F$:

**Exterior algebra**^[외대수]: $\Lambda(V) = \bigoplus_{k=0}^\infty \Lambda^k(V)$

**Multiplication**: Wedge product $\wedge$

**Properties**:
- Associative
- Graded algebra
- Anticommutativity: $v \wedge w = -w \wedge v$

**응용**: Differential geometry, differential forms

자세한 내용은 [[Exterior Algebra]] 참조

---

## Example 6: Group Algebra $F[G]$

For finite group $G$:

**Group algebra**^[군 대수]: $F[G] = \left\{\sum_{g \in G} a_g g : a_g \in F\right\}$

**Vector space**: Basis = elements of $G$, $\dim(F[G]) = |G|$

**Multiplication**: Extend group multiplication bilinearly

$$\left(\sum a_g g\right) \left(\sum b_h h\right) = \sum_{g,h} a_g b_h (gh)$$

**Properties**:
- Associative
- Unital: Identity = $e$ (group identity)
- Generally non-commutative

**응용**: Representation theory, group representations $\leftrightarrow$ $F[G]$-modules

---

## Example 7: Endomorphism Algebra $\text{End}(V)$

For vector space $V$:

$$\text{End}(V) = \{T: V \to V : T \text{ is linear}\}$$

**Vector space**: Pointwise operations

**Multiplication**: Composition of linear transformations

$$T \circ S: v \mapsto T(S(v))$$

**Properties**:
- Associative
- Unital: Identity = $\text{Id}_V$
- Non-commutative (generally)

**Isomorphism**: If $\dim(V) = n$, then $\text{End}(V) \cong M_n(F)$

---

## Example 8: Lie Algebra $\mathfrak{gl}_n(F)$

**General linear Lie algebra**^[일반 선형 리 대수]:

$$\mathfrak{gl}_n(F) = M_n(F)$$

**Vector space**: Same as $M_n(F)$

**Multiplication**: Lie bracket $[A, B] = AB - BA$

**Properties**:
- **Non-associative**: $[A, [B, C]] \neq [[A, B], C]$ generally
- Anticommutative: $[A, B] = -[B, A]$
- Jacobi identity: $[A, [B, C]] + [B, [C, A]] + [C, [A, B]] = 0$

자세한 내용은 [[Lie Algebra]] 참조

---

## Example 9: Clifford Algebra

For vector space $V$ with quadratic form $Q$:

**Clifford algebra**^[클리포드 대수]: $\text{Cl}(V, Q)$

**Construction**: Quotient of tensor algebra by ideal generated by $v \otimes v - Q(v) \cdot 1$

**Properties**:
- Associative
- Unital
- Generalizes exterior algebra, quaternions

**Special cases**:
- $\text{Cl}(\mathbb{R}^0, 0) \cong \mathbb{R}$
- $\text{Cl}(\mathbb{R}^1, -x^2) \cong \mathbb{C}$
- $\text{Cl}(\mathbb{R}^2, -x^2 - y^2) \cong \mathbb{H}$

**응용**: Spin geometry, physics

---

## Example 10: Tensor Algebra $T(V)$

For vector space $V$:

**Tensor algebra**^[텐서 대수]: $T(V) = \bigoplus_{k=0}^\infty V^{\otimes k}$

where $V^{\otimes k} = V \otimes V \otimes \cdots \otimes V$ ($k$ times)

**Multiplication**: Tensor product

**Properties**:
- Associative
- Unital: Identity = $1 \in V^{\otimes 0} = F$
- Universal property for algebras

**의미**: "Free algebra" generated by $V$

---

# <span class="header-theorem">Important Theorems</span>

## Theorem 1: Frobenius Theorem

**정리** (**Frobenius**, 1877):

Finite-dimensional associative division algebras over $\mathbb{R}$는 다음 셋 뿐:

1. $\mathbb{R}$ (dimension 1)
2. $\mathbb{C}$ (dimension 2)
3. $\mathbb{H}$ (quaternions, dimension 4)

**의미**: No other real division algebras exist!

**응용**: Topology, physics

---

## Theorem 2: Wedderburn's Theorem

**정리** (**Wedderburn**):

Every finite-dimensional simple associative algebra over algebraically closed field $F$ is isomorphic to $M_n(F)$ for some $n$

**의미**: Matrix algebras are the "building blocks"

---

## Theorem 3: Artin-Wedderburn Theorem

**정리**:

Every finite-dimensional semisimple algebra over field $F$ is isomorphic to direct product:

$$A \cong M_{n_1}(D_1) \times M_{n_2}(D_2) \times \cdots \times M_{n_k}(D_k)$$

where $D_i$ are division algebras over $F$

**응용**: Representation theory, decomposition of algebras

---

## Theorem 4: Poincaré-Birkhoff-Witt Theorem

**정리** (PBW):

For Lie algebra $\mathfrak{g}$, universal enveloping algebra $U(\mathfrak{g})$ has natural filtration whose associated graded algebra is isomorphic to symmetric algebra $S(\mathfrak{g})$

**의미**: Structure of universal enveloping algebras

**응용**: Representation theory of Lie algebras

---

## Theorem 5: Hopf's Theorem

**정리**:

Finite-dimensional division algebra over $\mathbb{C}$는 $\mathbb{C}$ 뿐

**증명**: Uses algebraic closure

---

# <span class="header-properties">Structure Theory</span>

## Simple and Semisimple Algebras

### Simple Algebra^[단순 대수]

**Simple algebra**^[단순 대수]: No proper two-sided ideals (except $\{0\}$)

**예**: $M_n(F)$ is simple

### Semisimple Algebra^[반단순 대수]

**Semisimple algebra**^[반단순 대수]: Direct sum of simple algebras

**Jacobson radical**: $J(A) = $ intersection of all maximal left ideals

**정리**: $A$ is semisimple $\Leftrightarrow$ $J(A) = \{0\}$

---

## Graded Algebras^[등급 대수]

**Graded algebra**^[등급 대수]: $A = \bigoplus_{n=0}^\infty A_n$ with $A_m \cdot A_n \subseteq A_{m+n}$

**예**:
- Polynomial algebra: $F[x]$ graded by degree
- Exterior algebra: $\Lambda(V)$
- Tensor algebra: $T(V)$

**Homogeneous elements**^[동차 원소]: Elements in $A_n$

---

## Universal Enveloping Algebra^[보편 포락 대수]

For Lie algebra $\mathfrak{g}$:

**Universal enveloping algebra**^[보편 포락 대수]: $U(\mathfrak{g})$

**Construction**: Quotient of tensor algebra $T(\mathfrak{g})$ by ideal generated by

$$x \otimes y - y \otimes x - [x, y]$$

**Universal property**: Lie algebra homomorphisms $\mathfrak{g} \to A$ (associative) correspond to algebra homomorphisms $U(\mathfrak{g}) \to A$

**응용**: Represent Lie algebras as associative algebras

---

# <span class="header-remark">Common Pitfalls</span>

## 1. Algebra $\neq$ Ring

✗ "모든 ring은 algebra"?

✓ Algebra는 **field 위에서 정의**

Algebra = ring + vector space + compatibility

**차이**: Ring은 base field 불필요

---

## 2. Associativity Not Always True

✗ "모든 algebra는 associative"?

✓ **Lie algebras**, **Jordan algebras**는 non-associative

**정의 주의**: "Algebra"만 쓸 때는 보통 associative를 가정

---

## 3. Commutative Algebra (두 가지 의미)

**의미 1**: Commutative algebra (structure)
- $ab = ba$인 algebra

**의미 2**: Commutative algebra (field)
- Branch of mathematics studying commutative rings

**주의**: 문맥에 따라 의미 다름!

---

## 4. Subalgebra Must Contain Identity

✗ "Vector subspace + closed under multiplication = subalgebra"?

✓ Unital algebra의 subalgebra는 **same identity** 포함해야 함

---

## 5. Division Algebra $\neq$ Field

✗ "Division algebra = field"?

✓ Field = **commutative** division algebra

Division algebra는 non-commutative일 수 있음 (예: $\mathbb{H}$)

---

## 6. Dimension as Algebra vs Vector Space

**Algebra dimension**: As vector space over base field

**Matrix algebra**: $\dim(M_n(F)) = n^2$ (not $n$!)

---

# <span class="header-remark">Comparison Tables</span>

## Algebra vs Ring vs Module

| Aspect | Ring | Algebra | Module |
|--------|------|---------|--------|
| Structure | Addition + Multiplication | Ring + Vector space | Abelian group + Scalar multiplication |
| Base | None | Field $F$ | Ring $R$ |
| Examples | $\mathbb{Z}$, $\mathbb{Z}/n\mathbb{Z}$ | $M_n(F)$, $F[x]$ | $\mathbb{Z}$-modules = abelian groups |
| Scalars | None | Field elements | Ring elements |

---

## Types of Algebras

| Type | Associative? | Commutative? | Has Identity? | Example |
|------|--------------|--------------|---------------|---------|
| Associative algebra | ✓ | May vary | Usually | $M_n(F)$ |
| Commutative algebra | ✓ | ✓ | Usually | $F[x]$ |
| Division algebra | ✓ | May vary | ✓ | $\mathbb{H}$ |
| Lie algebra | ✗ | ✗ | ✗ | $\mathfrak{gl}_n$ |
| Jordan algebra | ✗ | "Commutative" | May vary | Special cases |

---

## Famous Examples Comparison

| Algebra | Dimension | Associative? | Commutative? | Division? |
|---------|-----------|--------------|--------------|-----------|
| $\mathbb{R}$ | 1 | ✓ | ✓ | ✓ |
| $\mathbb{C}$ | 2 (over $\mathbb{R}$) | ✓ | ✓ | ✓ |
| $\mathbb{H}$ | 4 (over $\mathbb{R}$) | ✓ | ✗ | ✓ |
| $M_n(F)$ | $n^2$ | ✓ | ✗ ($n \geq 2$) | ✗ |
| $F[x]$ | $\infty$ | ✓ | ✓ | ✗ |

---

# <span class="header-remark">Historical Context</span>

**William Rowan Hamilton** (1805-1865):
- Discovered quaternions (1843)
- First non-commutative algebra
- "I walked with Lady Hamilton to Dublin, and there I scratched the formulae on a stone of Brougham Bridge"

**Ferdinand Georg Frobenius** (1849-1917):
- Frobenius theorem (1877)
- Classification of real division algebras
- Representation theory

**Joseph Wedderburn** (1882-1948):
- Wedderburn's theorem
- Structure theory of algebras
- Semisimple algebras

**Emmy Noether** (1882-1935):
- Abstract algebra approach
- Module theory
- Noncommutative algebra

**Élie Cartan** (1869-1951):
- Lie algebras
- Classification of simple Lie algebras
- Exterior algebras

**Hermann Grassmann** (1809-1877):
- Exterior algebra (1844)
- Grassmann algebra
- Geometric applications

---

# <span class="header-remark">Related Concepts</span>

## Core Algebra

- [[Ring]]: Underlying multiplicative structure
- [[Vector Space]]: Underlying additive structure
- [[Module]]: Generalization over rings
- [[Field]]: Base field for scalras
- [[Bilinear Map]]: Multiplication structure

## Special Types

- [[Lie Algebra]]: Non-associative algebra with Jacobi identity
- [[Associative Algebra]]: Standard algebras
- [[Commutative Algebra]]: Abelian multiplication
- [[Division Algebra]]: All nonzero elements invertible
- [[Graded Algebra]]: Decomposition by degree

## Constructions

- [[Tensor Algebra]]: Free algebra construction
- [[Exterior Algebra]]: Alternating tensors
- [[Clifford Algebra]]: Generalizes quaternions
- [[Universal Enveloping Algebra]]: From Lie to associative
- [[Group Algebra]]: From groups to algebras

## Structure Theory

- [[Simple Algebra]]: No proper ideals
- [[Semisimple Algebra]]: Direct sums of simple
- [[Central Simple Algebra]]: Center is field
- [[Azumaya Algebra]]: Generalization to schemes

## Homomorphisms

- [[Algebra Homomorphism]]: Structure-preserving maps
- [[Ideal]]: Kernels of homomorphisms
- [[Quotient Algebra]]: Factoring by ideal

## Representation Theory

- [[Representation]]: Algebras acting on vector spaces
- [[Module over Algebra]]: Representations as modules
- [[Character Theory]]: Traces of representations

## Applications

- [[Linear Transformation]]: Endomorphism algebras
- [[Matrix Theory]]: Matrix algebras
- [[Polynomial Ring]]: Commutative algebras
- [[Differential Geometry]]: Exterior algebras
- [[Quantum Mechanics]]: Operator algebras

---

# <span class="header-remark">Applications</span>

## 1. Representation Theory

**Group representations** via group algebras $F[G]$

**Lie algebra representations** via universal enveloping algebras

**응용**: Physics, chemistry (symmetry)

---

## 2. Quantum Mechanics

**Observable operators**: Form algebra (generally non-commutative)

**Commutation relations**: $[x, p] = i\hbar$

**Heisenberg algebra**: Fundamental in quantum theory

---

## 3. Differential Geometry

**Differential forms**: Exterior algebra $\Lambda(T^*M)$

**Tensor fields**: Tensor algebra

**응용**: Stokes' theorem, de Rham cohomology

---

## 4. Algebraic Geometry

**Coordinate rings**: Commutative algebras

**Sheaves of algebras**: Local-to-global principle

---

## 5. Computer Science

**Algebraic structures**: Algorithm design

**Coding theory**: Finite field algebras

**Cryptography**: Division algebras, quaternion cryptography

---

## 6. Physics

**Spin**: Clifford algebras, spinors

**Gauge theory**: Lie algebras

**String theory**: Vertex operator algebras

