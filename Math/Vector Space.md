# <span class="header-prerequisite">Prerequisite</span>

- [[Field]]
- [[Abelian Group]]
- [[Linear Algebra]]
- [[Module]]

# <span class="header-reference">Reference</span>

- Axler, *Linear Algebra Done Right*
- Hoffman & Kunze, *Linear Algebra*
- Lang, *Algebra*
- Friedberg, Insel & Spence, *Linear Algebra*

---

# <span class="header-definition">Definition</span>

## Vector Space^[벡터 공간]

**Vector space**^[벡터 공간] over a field^[체] $F$는 abelian group^[아벨 군] $(V, +)$와 **scalar multiplication**^[스칼라 곱셈] 연산:

$$\cdot: F \times V \to V, \quad (c, v) \mapsto c \cdot v$$

다음 8개의 공리를 만족:

### Vector Addition Axioms (4개)

모든 $u, v, w \in V$에 대해:

**VA1. Commutativity**^[교환법칙]:

$$u + v = v + u$$

**VA2. Associativity**^[결합법칙]:

$$(u + v) + w = u + (v + w)$$

**VA3. Identity**^[항등원]:

$$\exists 0 \in V: \quad v + 0 = v$$

**VA4. Inverse**^[역원]:

$$\exists (-v) \in V: \quad v + (-v) = 0$$

### Scalar Multiplication Axioms (4개)

모든 $c, d \in F$와 $v, w \in V$에 대해:

**SM1. Compatibility**^[양립성]:

$$c \cdot (d \cdot v) = (cd) \cdot v$$

**SM2. Identity**^[항등원]:

$$1 \cdot v = v$$

**SM3. Distributivity (scalars)**^[분배법칙 (스칼라)]:

$$(c + d) \cdot v = c \cdot v + d \cdot v$$

**SM4. Distributivity (vectors)**^[분배법칙 (벡터)]:

$$c \cdot (v + w) = c \cdot v + c \cdot w$$

## Key Terminology

**Vector**^[벡터]: Elements of $V$

**Scalar**^[스칼라]: Elements of $F$

**Base field**^[기저체]: The field $F$

**Notation**: Often write $cv$ instead of $c \cdot v$

## Vector Space vs Module

**Vector space** = **Module over a field**^[체 위의 가군]

$$\text{Vector space over } F = F\text{-module}$$

**차이점**: Module은 ring 위에서 정의, vector space는 field 위에서 정의

Field의 성질 (모든 nonzero element가 역원 존재) → Vector space가 module보다 다루기 쉬움

자세한 내용은 [[Module]] 참조

---

# <span class="header-definition">Fundamental Concepts</span>

## Linear Combination^[일차 결합]

Vectors $v_1, \ldots, v_n \in V$와 scalars $c_1, \ldots, c_n \in F$에 대해:

$$c_1 v_1 + c_2 v_2 + \cdots + c_n v_n$$

를 **linear combination**^[일차 결합]이라 함

## Span^[생성]

$$\text{span}(S) = \text{span}\{v_1, \ldots, v_n\} = \{c_1 v_1 + \cdots + c_n v_n : c_i \in F\}$$

**의미**: $S$의 원소들의 모든 linear combinations

**성질**: $\text{span}(S)$는 subspace^[부분공간]

## Linear Independence^[일차 독립]

Vectors $v_1, \ldots, v_n \in V$가 **linearly independent**^[일차 독립]이다 $\Leftrightarrow$

$$c_1 v_1 + \cdots + c_n v_n = 0 \quad \Rightarrow \quad c_1 = \cdots = c_n = 0$$

**의미**: 어떤 벡터도 다른 벡터들의 linear combination으로 표현 불가

### Linear Dependence^[일차 종속]

**Linearly dependent**^[일차 종속]: Not linearly independent

$$\exists c_1, \ldots, c_n \text{ (not all zero)}: \quad c_1 v_1 + \cdots + c_n v_n = 0$$

## Basis^[기저]

$V$의 **basis**^[기저]는 다음을 만족하는 집합 $\mathcal{B} = \{v_1, \ldots, v_n\}$:

**B1. Spanning**^[생성]: $\text{span}(\mathcal{B}) = V$

**B2. Linear independence**^[일차 독립]: $\mathcal{B}$는 linearly independent

**동등 조건**: 모든 $v \in V$는 $\mathcal{B}$의 원소들의 **유일한** linear combination으로 표현

$$v = c_1 v_1 + \cdots + c_n v_n$$

**Coordinates**^[좌표]: $(c_1, \ldots, c_n) \in F^n$

## Dimension^[차원]

**정리**: Finite-dimensional vector space의 모든 basis는 같은 개수의 원소를 가짐

**Dimension**^[차원]: $\dim(V)$ = basis의 원소 개수

**Finite-dimensional**^[유한 차원]: Finite basis가 존재

**Infinite-dimensional**^[무한 차원]: Finite basis가 존재하지 않음

---

# <span class="header-properties">Subspaces</span>

## Subspace^[부분공간]

$W \subseteq V$가 **subspace**^[부분공간]이다 $\Leftrightarrow$ 다음 세 조건:

**S1. Zero vector**: $0 \in W$

**S2. Addition**: $u, v \in W \Rightarrow u + v \in W$

**S3. Scalar multiplication**: $c \in F, v \in W \Rightarrow cv \in W$

**동등 조건**: $W$가 vector space structure를 그대로 상속

## Subspace Test

$W \subseteq V$가 subspace $\Leftrightarrow$ $W \neq \emptyset$이고:

$$c, d \in F, \quad u, v \in W \quad \Rightarrow \quad cu + dv \in W$$

**One-step subspace test**

## Sum of Subspaces^[부분공간의 합]

$$U + W = \{u + w : u \in U, w \in W\}$$

**성질**: $U + W$는 subspace

## Direct Sum^[직합]

$V = U \oplus W$ (direct sum^[직합]) $\Leftrightarrow$:

**DS1. Sum**: $V = U + W$

**DS2. Trivial intersection**: $U \cap W = \{0\}$

**동등 조건**: 모든 $v \in V$는 **유일하게** $v = u + w$ (where $u \in U, w \in W$)로 표현

**차원 공식**:

$$\dim(V) = \dim(U) + \dim(W)$$

## Dimension Formula for Subspaces

일반적으로 (direct sum이 아니어도):

$$\dim(U + W) = \dim(U) + \dim(W) - \dim(U \cap W)$$

---

# <span class="header-examples">Examples</span>

## Example 1: $F^n$ (Standard Example)

$$F^n = \{(x_1, \ldots, x_n) : x_i \in F\}$$

**Addition**: Component-wise

**Scalar multiplication**: Component-wise

**Standard basis**^[표준 기저]:

$$e_1 = (1, 0, \ldots, 0), \quad e_2 = (0, 1, 0, \ldots, 0), \quad \ldots, \quad e_n = (0, \ldots, 0, 1)$$

**Dimension**: $\dim(F^n) = n$

## Example 2: $\mathbb{R}^2$ and $\mathbb{R}^3$ (Geometric)

**$\mathbb{R}^2$**: Plane (2D)

**$\mathbb{R}^3$**: 3D space

**Geometric operations**: Addition = parallelogram rule

**응용**: Physics, computer graphics

## Example 3: Polynomial Space $F[x]_n$

$$F[x]_n = \{a_0 + a_1 x + \cdots + a_n x^n : a_i \in F\}$$

**Polynomials of degree at most $n$**

**Basis**: $\{1, x, x^2, \ldots, x^n\}$

**Dimension**: $\dim(F[x]_n) = n + 1$

## Example 4: All Polynomials $F[x]$

$$F[x] = \{\text{all polynomials with coefficients in } F\}$$

**Basis**: $\{1, x, x^2, x^3, \ldots\}$ (infinite)

**Dimension**: $\dim(F[x]) = \infty$ (infinite-dimensional)

## Example 5: Function Space $\mathcal{F}(\mathbb{R}, \mathbb{R})$

$$\mathcal{F}(\mathbb{R}, \mathbb{R}) = \{f: \mathbb{R} \to \mathbb{R}\}$$

**Addition**: $(f + g)(x) = f(x) + g(x)$

**Scalar multiplication**: $(cf)(x) = c \cdot f(x)$

**Dimension**: Infinite

## Example 6: Solution Space of Linear System

$$Ax = 0$$

where $A$ is $m \times n$ matrix over $F$

**Solution space**: $\text{Null}(A) = \{x \in F^n : Ax = 0\}$

**Subspace** of $F^n$

**Dimension**: $\dim(\text{Null}(A)) = n - \text{rank}(A)$ (Rank-Nullity Theorem)

## Example 7: Matrix Space $M_{m \times n}(F)$

$$M_{m \times n}(F) = \{m \times n \text{ matrices with entries in } F\}$$

**Addition**: Matrix addition

**Scalar multiplication**: Scalar multiplication of matrices

**Standard basis**: Matrices $E_{ij}$ (1 in $(i,j)$-entry, 0 elsewhere)

**Dimension**: $\dim(M_{m \times n}(F)) = mn$

## Example 8: Continuous Functions $C(\mathbb{R})$

$$C(\mathbb{R}) = \{f: \mathbb{R} \to \mathbb{R} : f \text{ is continuous}\}$$

**Subspace** of $\mathcal{F}(\mathbb{R}, \mathbb{R})$

**Dimension**: Infinite

**응용**: Analysis, differential equations

## Example 9: Sequence Space $\ell^2$

$$\ell^2 = \left\{(x_1, x_2, \ldots) : x_i \in \mathbb{R}, \sum_{i=1}^{\infty} x_i^2 < \infty\right\}$$

**Infinite-dimensional** vector space

**Inner product space** (Hilbert space)

**응용**: Functional analysis, quantum mechanics

## Example 10: Zero Vector Space

$$V = \{0\}$$

**Trivial vector space**^[자명한 벡터 공간]

**Dimension**: $\dim(\{0\}) = 0$

**Basis**: Empty set $\emptyset$

---

# <span class="header-theorem">Important Theorems</span>

## Theorem 1: Basis Existence

**Statement**: Every vector space has a basis

**증명**: Zorn's Lemma (requires Axiom of Choice)

**유한 차원**: Constructive proof 가능

## Theorem 2: Dimension Theorem

**Statement**: Finite-dimensional vector space의 모든 basis는 같은 크기

**증명**: Exchange lemma, Steinitz exchange lemma

**결과**: Dimension이 well-defined

## Theorem 3: Extending to a Basis

**Statement**: Linearly independent set은 basis로 확장 가능

$$S \subseteq V \text{ linearly independent} \quad \Rightarrow \quad \exists \text{ basis } \mathcal{B}: S \subseteq \mathcal{B}$$

## Theorem 4: Reducing to a Basis

**Statement**: Spanning set은 basis로 축소 가능

$$\text{span}(S) = V \quad \Rightarrow \quad \exists \text{ basis } \mathcal{B} \subseteq S$$

## Theorem 5: Dimension of Subspace

$$W \subseteq V \text{ subspace} \quad \Rightarrow \quad \dim(W) \leq \dim(V)$$

**Equality** $\Leftrightarrow$ $W = V$

## Theorem 6: Rank-Nullity Theorem

Linear transformation $T: V \to W$에 대해:

$$\dim(V) = \dim(\ker(T)) + \dim(\text{im}(T))$$

$$\dim(V) = \text{nullity}(T) + \text{rank}(T)$$

자세한 내용은 [[Linear Transformation]], [[Rank-Nullity Theorem]] 참조

## Theorem 7: Dimension Formula (Subspaces)

$$\dim(U + W) = \dim(U) + \dim(W) - \dim(U \cap W)$$

**응용**: Inclusion-exclusion principle for dimensions

## Theorem 8: Linear Independence Test in $F^n$

$n$ vectors in $F^n$가 linearly independent $\Leftrightarrow$ matrix의 determinant $\neq 0$

---

# <span class="header-properties">Key Properties</span>

## 1. Uniqueness of Zero Vector

$$0 \in V \text{ is unique}$$

**증명**: $0, 0'$ both identity이면 $0 = 0 + 0' = 0'$

## 2. Uniqueness of Additive Inverse

$$\text{For each } v \in V, \quad -v \text{ is unique}$$

## 3. Scalar Multiplication Properties

$$0 \cdot v = 0$$

$$c \cdot 0 = 0$$

$$(-1) \cdot v = -v$$

$$cv = 0 \quad \Rightarrow \quad c = 0 \text{ or } v = 0$$

## 4. Cancellation

$$v + u = v + w \quad \Rightarrow \quad u = w$$

## 5. Linear Independence Properties

**LI1**: Empty set $\emptyset$는 linearly independent

**LI2**: Set containing $0$는 linearly dependent

**LI3**: Subset of linearly independent set은 linearly independent

**LI4**: Superset of linearly dependent set은 linearly dependent

## 6. Basis Properties

**$n$ vectors in $\dim(V) = n$**:

다음은 모두 동치:
- Basis
- Linearly independent
- Spanning set

## 7. Coordinate Representation

Basis $\mathcal{B} = \{v_1, \ldots, v_n\}$가 주어지면:

$$v = c_1 v_1 + \cdots + c_n v_n$$

**Coordinate vector**^[좌표 벡터]: $[v]_\mathcal{B} = (c_1, \ldots, c_n)^T$

**Isomorphism**: $V \cong F^n$

---

# <span class="header-examples">Applications</span>

## 1. Linear Systems

$$Ax = b$$

**Solution space**: Affine subspace

**Homogeneous system**: $Ax = 0$ (subspace)

자세한 내용은 [[Linear System]] 참조

## 2. Differential Equations

**Linear ODE**: Solution space는 vector space

**예**: $y'' + py' + qy = 0$

Solution space는 2-dimensional vector space

## 3. Quantum Mechanics

**State space**: Hilbert space (infinite-dimensional vector space with inner product)

**Superposition principle**: Linear combination of states

## 4. Computer Graphics

**3D transformations**: Linear algebra in $\mathbb{R}^3$

**Coordinate systems**: Change of basis

## 5. Data Science

**Feature space**: Each data point = vector

**Dimension reduction**: PCA, finding subspaces

## 6. Signal Processing

**Fourier series**: Functions as infinite linear combinations

**Basis**: Sine and cosine functions

## 7. Coding Theory

**Error-correcting codes**: Subspaces of $\mathbb{F}_2^n$

**Linear codes**: Use vector space structure

자세한 내용은 [[Linear Code]] 참조

## 8. Functional Analysis

**Normed spaces**, **Banach spaces**, **Hilbert spaces**

Generalizations of finite-dimensional vector spaces

---

# <span class="header-remark">Common Pitfalls</span>

## 1. Field vs Ring

✗ "Vector space over a ring"?

✓ **Module** over a ring

Vector space는 **field** 위에서만 정의

## 2. Basis Uniqueness

✗ "Basis is unique"?

✓ Basis는 **유일하지 않음**

✓ Basis의 **크기**(cardinality)는 유일 = dimension

## 3. Span Contains Original Set

✗ "$\text{span}(S) = S$"?

✓ $S \subseteq \text{span}(S)$

Equality는 $S$가 subspace일 때만

## 4. Dimension Zero

✗ "Dimension 0 vector space doesn't exist"?

✓ $V = \{0\}$ has $\dim(V) = 0$

Basis = empty set

## 5. Linear Independence of Single Vector

✗ "Single vector는 항상 linearly independent"?

✓ $\{v\}$ is linearly independent $\Leftrightarrow$ $v \neq 0$

## 6. Subspace vs Subset

✗ "모든 subset은 subspace"?

✓ Subspace는 **특별한** subset

Must satisfy closure properties

## 7. Direct Sum Notation

✗ "$V = U + W$ means direct sum"?

✓ Use $V = U \oplus W$ for direct sum

$V = U + W$ is just sum (may have nontrivial intersection)

## 8. Coordinates Depend on Basis

✗ "Coordinate vector는 절대적"?

✓ $[v]_\mathcal{B}$ depends on choice of basis $\mathcal{B}$

Different basis → different coordinates

## 9. Infinite-Dimensional Spaces

✗ "모든 vector space는 유한 차원"?

✓ Many important spaces are **infinite-dimensional**

Examples: $F[x]$, $C(\mathbb{R})$, $\ell^2$

---

# <span class="header-examples">Comparison Table</span>

## Finite vs Infinite Dimensional

| Property | Finite-Dimensional | Infinite-Dimensional |
|----------|-------------------|----------------------|
| Basis | Finite set | Infinite set |
| Coordinates | Finite tuple | Infinite sequence |
| Subspace = closed span | Always | Not always |
| Every LI set extends to basis | ✓ | ✓ (with AC) |
| Every spanning set reduces to basis | ✓ | ✓ (with AC) |
| Algebraic dual = continuous dual | ✓ (if normed) | ✗ |

## Vector Space vs Module

| Aspect | Vector Space | Module |
|--------|--------------|---------|
| Base structure | Field $F$ | Ring $R$ |
| Scalars | Always invertible (≠0) | May not be invertible |
| Basis existence | ✓ | Not always |
| Dimension well-defined | ✓ | Not always |
| Examples | $\mathbb{R}^n$, $F[x]$ | $\mathbb{Z}$-modules = abelian groups |

---

# <span class="header-remark">Historical Context</span>

**Giuseppe Peano** (1858-1932):
- First axiomatic definition (1888)
- Vector space axioms
- Foundation of linear algebra

**Hermann Grassmann** (1809-1877):
- *Ausdehnungslehre* (1844)
- Exterior algebra
- Geometric approach to vectors

**William Rowan Hamilton** (1805-1865):
- Quaternions (1843)
- Early vector-like structures
- 4-dimensional "vectors"

**Augustin-Louis Cauchy** (1789-1857):
- Matrix theory
- Linear systems

**Arthur Cayley** (1821-1895):
- Matrix algebra (1858)
- Abstract matrix operations

**20th Century Development**:
- Functional analysis
- Infinite-dimensional spaces
- Banach spaces, Hilbert spaces
- Applications to quantum mechanics

---

# <span class="header-remark">Related Concepts</span>

## Linear Algebra

- [[Linear Transformation]]: Structure-preserving maps
- [[Matrix]]: Representation of linear maps
- [[Determinant]]: Scalar associated with matrices
- [[Eigenvalue and Eigenvector]]: Special vectors
- [[Inner Product Space]]: Vector space with inner product
- [[Norm]]: Notion of length
- [[Orthogonality]]: Perpendicularity

## Algebra

- [[Module]]: Generalization to rings
- [[Field]]: Scalars
- [[Abelian Group]]: Additive structure
- [[Ring]]: More general scalar structure

## Analysis

- [[Normed Vector Space]]: Vector space with norm
- [[Banach Space]]: Complete normed vector space
- [[Hilbert Space]]: Complete inner product space
- [[Topological Vector Space]]: Vector space with topology

## Geometry

- [[Affine Space]]: "Vector space without origin"
- [[Projective Space]]: Quotient by scalar multiplication
- [[Tensor Space]]: Multilinear algebra

## Applications

- [[Linear System]]: Solving $Ax = b$
- [[Least Squares]]: Approximation problems
- [[Principal Component Analysis]]: Dimension reduction
- [[Fourier Analysis]]: Function spaces
- [[Quantum Mechanics]]: State spaces

