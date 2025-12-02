# <span class="header-prerequisite">Prerequisite</span>

- [[Vector Space]]
- [[Bilinear Map]]
- [[Commutator in Ring]]
- [[Derivation]]

# <span class="header-reference">Reference</span>

- Jacobson, *Lie Algebras*
- Humphreys, *Introduction to Lie Algebras and Representation Theory*
- Hall, *Lie Groups, Lie Algebras, and Representations*
- Warner, *Foundations of Differentiable Manifolds and Lie Groups*

---

# <span class="header-definition">Definition</span>

## Lie Bracket^[리 브라켓]

**Lie bracket**^[리 브라켓]은 Lie algebra^[리 대수]의 핵심 연산:

$$[\cdot, \cdot]: \mathfrak{g} \times \mathfrak{g} \to \mathfrak{g}$$

다음 세 가지 공리를 만족하는 bilinear map^[쌍선형 사상]:

### 1. Bilinearity^[쌍선형성]

$$[a\alpha + b\beta, \gamma] = a[\alpha, \gamma] + b[\beta, \gamma]$$

$$[\alpha, a\beta + b\gamma] = a[\alpha, \beta] + b[\alpha, \gamma]$$

모든 $\alpha, \beta, \gamma \in \mathfrak{g}$와 $a, b$ (scalars)에 대해

### 2. Anticommutativity^[반교환성]

$$[\alpha, \beta] = -[\beta, \alpha]$$

**결과**: $[\alpha, \alpha] = 0$ (자기 자신과의 bracket은 0)

### 3. Jacobi Identity^[야코비 항등식]

$$[[\alpha, \beta], \gamma] + [[\beta, \gamma], \alpha] + [[\gamma, \alpha], \beta] = 0$$

**의미**: Lie bracket의 "일관성 조건"

자세한 내용은 [[Jacobi Idenity]] 참조

---

## Lie Algebra^[리 대수]

Vector space $\mathfrak{g}$ with Lie bracket $[\cdot, \cdot]$가 **Lie algebra**^[리 대수]:

$$(\mathfrak{g}, [\cdot, \cdot])$$

**구조**: Vector space + bracket operation (위 세 공리 만족)

**표기**: $\mathfrak{g}$ (Fraktur font), 또는 $L$

---

## Contexts for Lie Brackets

Lie bracket은 다양한 맥락에서 나타남:

### Context 1: Associative Algebras

Associative algebra $A$에서:

$$[a, b] = ab - ba$$

**Commutator**^[교환자]라고도 함

**정리**: $(A, [\cdot, \cdot])$는 Lie algebra

자세한 내용은 [[Commutator in Ring]] 참조

### Context 2: Vector Fields

Manifold $M$ 위의 vector fields^[벡터장] $X, Y$:

$$[X, Y](f) = X(Y(f)) - Y(X(f))$$

**의미**: Commutator of derivations

**결과**: $[X, Y]$도 vector field (derivation)

자세한 내용은 [[Vector Field]] 참조

### Context 3: Differential Operators

Differential operators $D_1, D_2$:

$$[D_1, D_2] = D_1 \circ D_2 - D_2 \circ D_1$$

**예**: $\left[\frac{d}{dx}, x\right] = 1$ (multiplication by $x$)

자세한 내용은 [[Derivation]] 참조

---

## Alternative Forms

### Derivation Form^[미분 형태]

Jacobi identity를 다르게 쓰면:

$$[\alpha, [\beta, \gamma]] = [[\alpha, \beta], \gamma] + [\beta, [\alpha, \gamma]]$$

**의미**: $\text{ad}_\alpha = [\alpha, \cdot]$는 derivation

### Adjoint Representation^[수반 표현]

Fixed $\alpha \in \mathfrak{g}$에 대해:

$$\text{ad}_\alpha: \mathfrak{g} \to \mathfrak{g}, \quad \text{ad}_\alpha(\beta) = [\alpha, \beta]$$

**정리**: $\text{ad}_\alpha$는 Lie algebra homomorphism^[리 대수 준동형사상]

$$\text{ad}_{[\alpha, \beta]} = [\text{ad}_\alpha, \text{ad}_\beta]$$

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Self-bracket is Zero

$$[\alpha, \alpha] = 0$$

**증명**: Anticommutativity에서 $[\alpha, \alpha] = -[\alpha, \alpha]$ $\Rightarrow$ $2[\alpha, \alpha] = 0$

### 2. Linearity in Each Argument

$$[\lambda \alpha, \beta] = \lambda [\alpha, \beta] = [\alpha, \lambda \beta]$$

for scalar $\lambda$

### 3. Zero Bracket $\Leftrightarrow$ Commute

**In associative algebra**: $[a, b] = 0$ $\Leftrightarrow$ $ab = ba$

**In Lie algebra**: $[\alpha, \beta] = 0$ $\Leftrightarrow$ $\alpha, \beta$ commute

### 4. Leibniz Rule (for ad)

$$\text{ad}_\alpha([\beta, \gamma]) = [\text{ad}_\alpha(\beta), \gamma] + [\beta, \text{ad}_\alpha(\gamma)]$$

즉:

$$[\alpha, [\beta, \gamma]] = [[\alpha, \beta], \gamma] + [\beta, [\alpha, \gamma]]$$

**의미**: $\text{ad}_\alpha$는 derivation

### 5. ad is Lie Algebra Homomorphism

$$\text{ad}: \mathfrak{g} \to \text{End}(\mathfrak{g})$$

$$\text{ad}_{[\alpha, \beta]} = [\text{ad}_\alpha, \text{ad}_\beta]$$

**의미**: Adjoint representation

---

## Subalgebras and Ideals

### Subalgebra^[부분대수]

$\mathfrak{h} \subseteq \mathfrak{g}$가 **subalgebra**^[부분대수] $\Leftrightarrow$:
- Vector subspace
- Closed under bracket: $[\mathfrak{h}, \mathfrak{h}] \subseteq \mathfrak{h}$

### Ideal^[아이디얼]

$\mathfrak{i} \subseteq \mathfrak{g}$가 **ideal**^[아이디얼] $\Leftrightarrow$:
- Subalgebra
- $[\mathfrak{g}, \mathfrak{i}] \subseteq \mathfrak{i}$ (absorbs from outside)

**의미**: Kernel of Lie algebra homomorphism

---

## Center and Centralizer

### Center^[중심]

$$Z(\mathfrak{g}) = \{\alpha \in \mathfrak{g} : [\alpha, \beta] = 0 \text{ for all } \beta \in \mathfrak{g}\}$$

**성질**: $Z(\mathfrak{g})$는 abelian ideal

### Centralizer^[중심화 부분대수]

For subset $S \subseteq \mathfrak{g}$:

$$C_{\mathfrak{g}}(S) = \{\alpha \in \mathfrak{g} : [\alpha, s] = 0 \text{ for all } s \in S\}$$

**성질**: Subalgebra

---

## Derived Series

**Derived subalgebra**^[도출 부분대수]:

$$\mathfrak{g}^{(1)} = [\mathfrak{g}, \mathfrak{g}] = \text{span}\{[\alpha, \beta] : \alpha, \beta \in \mathfrak{g}\}$$

**Derived series**^[도출 열]:

$$\mathfrak{g} \supseteq \mathfrak{g}^{(1)} \supseteq \mathfrak{g}^{(2)} \supseteq \cdots$$

where $\mathfrak{g}^{(n+1)} = [\mathfrak{g}^{(n)}, \mathfrak{g}^{(n)}]$

**Solvable**^[가해]: If $\mathfrak{g}^{(n)} = 0$ for some $n$

---

## Lower Central Series

**Lower central series**^[하부 중심 열]:

$$\mathfrak{g} \supseteq \mathfrak{g}^1 \supseteq \mathfrak{g}^2 \supseteq \cdots$$

where $\mathfrak{g}^{n+1} = [\mathfrak{g}, \mathfrak{g}^n]$

**Nilpotent**^[멱영]: If $\mathfrak{g}^n = 0$ for some $n$

---

# <span class="header-examples">Examples</span>

## Example 1: Matrix Lie Algebras

**General linear Lie algebra**: $\mathfrak{gl}_n(\mathbb{R})$

$$\mathfrak{gl}_n(\mathbb{R}) = M_n(\mathbb{R})$$

**Bracket**: Commutator

$$[A, B] = AB - BA$$

**Subalgebras**:
- $\mathfrak{sl}_n$: Traceless matrices ($\text{tr}(A) = 0$)
- $\mathfrak{so}_n$: Skew-symmetric matrices ($A^T = -A$)
- $\mathfrak{u}_n$: Skew-Hermitian matrices

---

## Example 2: Vector Fields on $\mathbb{R}^n$

**Coordinate vector fields**:

$$\frac{\partial}{\partial x_i}, \quad i = 1, \ldots, n$$

**Bracket**:

$$\left[\frac{\partial}{\partial x_i}, \frac{\partial}{\partial x_j}\right] = 0$$

**일반 vector field**:

$$X = \sum_i f_i(x) \frac{\partial}{\partial x_i}, \quad Y = \sum_j g_j(x) \frac{\partial}{\partial x_j}$$

$$[X, Y] = \sum_{i,j} \left(f_i \frac{\partial g_j}{\partial x_i} - g_i \frac{\partial f_j}{\partial x_i}\right) \frac{\partial}{\partial x_j}$$

---

## Example 3: Heisenberg Algebra

**3-dimensional Heisenberg algebra**: $\mathfrak{h}_3$

**Basis**: $\{X, Y, Z\}$

**Bracket relations**:

$$[X, Y] = Z, \quad [X, Z] = 0, \quad [Y, Z] = 0$$

**Center**: $Z(\mathfrak{h}_3) = \text{span}\{Z\}$

**응용**: Quantum mechanics (canonical commutation relations)

---

## Example 4: Abelian Lie Algebra

**Vector space** $V$ with **zero bracket**:

$$[\alpha, \beta] = 0 \quad \text{for all } \alpha, \beta \in V$$

**예**: $\mathbb{R}^n$ with trivial bracket

**성질**: Every element is in center

---

## Example 5: Lie Algebra of Lie Group

For Lie group $G$, **Lie algebra** $\mathfrak{g} = T_e G$ (tangent space at identity)

**Bracket**: Via left-invariant vector fields

**예**:
- $G = \text{GL}_n(\mathbb{R})$ $\Rightarrow$ $\mathfrak{g} = \mathfrak{gl}_n(\mathbb{R})$
- $G = \text{SO}(n)$ $\Rightarrow$ $\mathfrak{g} = \mathfrak{so}_n$
- $G = \text{SU}(n)$ $\Rightarrow$ $\mathfrak{g} = \mathfrak{su}_n$

---

## Example 6: $\mathfrak{sl}_2(\mathbb{C})$

**Special linear Lie algebra**: $\mathfrak{sl}_2(\mathbb{C})$

**Basis** (Cartan-Weyl basis):

$$H = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \quad E = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}, \quad F = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}$$

**Bracket relations**:

$$[H, E] = 2E, \quad [H, F] = -2F, \quad [E, F] = H$$

**응용**: Fundamental example in representation theory

---

## Example 7: Cross Product as Lie Bracket

**$\mathbb{R}^3$ with cross product**:

$$[v, w] = v \times w$$

**성질**: Satisfies Jacobi identity!

$$u \times (v \times w) + v \times (w \times u) + w \times (u \times v) = 0$$

**Lie algebra**: $\mathfrak{so}_3 \cong \mathbb{R}^3$ (with cross product)

---

## Example 8: Poisson Bracket

For smooth functions $f, g$ on symplectic manifold:

$$\{f, g\} = \sum_i \left(\frac{\partial f}{\partial q_i} \frac{\partial g}{\partial p_i} - \frac{\partial f}{\partial p_i} \frac{\partial g}{\partial q_i}\right)$$

**성질**: Satisfies Jacobi identity

**Classical mechanics**: Observables form Lie algebra

**Quantization**: $\{f, g\} \to \frac{1}{i\hbar}[F, G]$

---

## Example 9: Commutators in Quantum Mechanics

**Position and momentum operators**: $\hat{x}$, $\hat{p}$

**Canonical commutation relation**:

$$[\hat{x}, \hat{p}] = i\hbar$$

**Angular momentum**: $\hat{L}_x, \hat{L}_y, \hat{L}_z$

$$[\hat{L}_x, \hat{L}_y] = i\hbar \hat{L}_z$$

(cyclic permutations)

**Lie algebra**: $\mathfrak{so}_3$

---

## Example 10: Differential Operators

**$D = \frac{d}{dx}$**, **$M_x = $ multiplication by $x$**:

$$[D, M_x](f) = D(xf) - x D(f) = f + xf' - xf' = f$$

따라서:

$$[D, M_x] = I$$

**Generalization**: Weyl algebra, deformation quantization

---

# <span class="header-theorem">Important Theorems</span>

## Theorem 1: Jacobi Identity

**정리**: Lie bracket은 Jacobi identity를 만족

$$[[\alpha, \beta], \gamma] + [[\beta, \gamma], \alpha] + [[\gamma, \alpha], \beta] = 0$$

**증명**: Associative algebra에서 commutator로 정의하면 직접 계산으로 확인

자세한 내용은 [[Jacobi Idenity]] 참조

---

## Theorem 2: From Associative to Lie

**정리**: Every associative algebra $A$ gives Lie algebra

Define $[a, b] = ab - ba$

**증명**: Bilinearity, anticommutativity, Jacobi 모두 확인 가능

**의미**: Associative algebra는 자연스럽게 Lie algebra 구조 가짐

---

## Theorem 3: Poincaré-Birkhoff-Witt (PBW)

**정리**: For Lie algebra $\mathfrak{g}$, universal enveloping algebra $U(\mathfrak{g})$는 특별한 basis 가짐

**의미**: Lie algebra를 associative algebra에 embed 가능

**응용**: Representation theory

---

## Theorem 4: Ado's Theorem

**정리**: Every finite-dimensional Lie algebra over field of characteristic 0 has faithful finite-dimensional representation

**의미**: Lie algebra를 matrix algebra의 subalgebra로 realize 가능

---

## Theorem 5: Lie's Third Theorem

**정리**: Every finite-dimensional real Lie algebra is Lie algebra of some Lie group

**의미**: Lie algebras $\leftrightarrow$ Lie groups (locally)

---

# <span class="header-properties">Structure Theory</span>

## Simple and Semisimple Lie Algebras

### Simple Lie Algebra^[단순 리 대수]

**Simple**: No proper non-trivial ideals

**예**: $\mathfrak{sl}_n$ (for $n \geq 2$), $\mathfrak{so}_n$ (for $n \geq 3$), $\mathfrak{sp}_{2n}$

### Semisimple Lie Algebra^[반단순 리 대수]

**Semisimple**: $[\mathfrak{g}, \mathfrak{g}] = \mathfrak{g}$ and Killing form non-degenerate

**동등 조건**: Direct sum of simple Lie algebras

**Classification**: Cartan (1894), Killing (1888)
- Classical: $A_n, B_n, C_n, D_n$
- Exceptional: $E_6, E_7, E_8, F_4, G_2$

---

## Killing Form^[킬링 형식]

For Lie algebra $\mathfrak{g}$:

$$\kappa(\alpha, \beta) = \text{tr}(\text{ad}_\alpha \circ \text{ad}_\beta)$$

**성질**:
- Bilinear
- Symmetric: $\kappa(\alpha, \beta) = \kappa(\beta, \alpha)$
- **Invariant**: $\kappa([\alpha, \beta], \gamma) = \kappa(\alpha, [\beta, \gamma])$

**정리**: $\mathfrak{g}$ is semisimple $\Leftrightarrow$ $\kappa$ is non-degenerate

---

## Cartan Subalgebra^[카르탕 부분대수]

**Cartan subalgebra**: Maximal abelian subalgebra $\mathfrak{h} \subseteq \mathfrak{g}$ consisting of semisimple elements

**예**: $\mathfrak{gl}_n$에서 diagonal matrices

**Root system**: Eigenvalues of $\text{ad}_H$ for $H \in \mathfrak{h}$

**Classification**: Via root systems and Dynkin diagrams

---

# <span class="header-remark">Common Pitfalls</span>

## 1. Lie Algebra ≠ Associative Algebra

✗ "Lie bracket is associative"?

✓ Lie bracket is **NOT** associative

$[[\alpha, \beta], \gamma] \neq [\alpha, [\beta, \gamma]]$ in general

**대신**: Jacobi identity (weaker condition)

---

## 2. Commutator vs Lie Bracket

✗ "Commutator와 Lie bracket은 다름"?

✓ **같은 것**: Associative algebra에서 Lie bracket = commutator

**차이**: Context가 다름
- Commutator: Associative algebra 맥락
- Lie bracket: Lie algebra 맥락

---

## 3. Zero Bracket ≠ Zero Element

✗ "$[\alpha, \beta] = 0$ means $\alpha = 0$ or $\beta = 0$"?

✓ No! Just means $\alpha, \beta$ **commute**

**예**: Abelian Lie algebra에서 모든 bracket = 0

---

## 4. Bracket Has No Identity

✗ "Lie algebra has identity element for bracket"?

✓ **No identity element** for Lie bracket

$[\alpha, e] = \alpha$ doesn't make sense

**대신**: Vector space has zero element

---

## 5. Bilinearity ≠ Jacobi

✗ "Bilinear + anticommutative = Lie algebra"?

✓ Need **Jacobi identity** too!

**반례**: Can construct non-Lie bracket satisfying first two only

---

## 6. Vector Fields Bracket

✗ "Vector fields bracket = pointwise bracket"?

✓ **Not pointwise**!

$$[X, Y](f) = X(Yf) - Y(Xf)$$

involves derivatives, not just multiplication

---

# <span class="header-remark">Comparison Tables</span>

## Lie Algebra vs Associative Algebra

| Property | Associative Algebra | Lie Algebra |
|----------|---------------------|-------------|
| Multiplication | Associative $(ab)c = a(bc)$ | Non-associative |
| Identity | May have 1 | **No** identity for bracket |
| Commutativity | Optional | **Anti**-commutative |
| Key axiom | Associativity | Jacobi identity |
| Example | $M_n(F)$ | $\mathfrak{gl}_n$ |

---

## Types of Lie Brackets

| Context | Definition | Example |
|---------|------------|---------|
| Associative algebra | $[a,b] = ab - ba$ | $M_n(\mathbb{R})$ |
| Vector fields | $[X,Y](f) = X(Yf) - Y(Xf)$ | $\mathfrak{X}(M)$ |
| Differential operators | $[D_1, D_2] = D_1 \circ D_2 - D_2 \circ D_1$ | $D = \frac{d}{dx}$ |
| Cross product | $[v, w] = v \times w$ | $\mathbb{R}^3$ |
| Poisson bracket | $\{f, g\}$ | Classical mechanics |

---

## Classical Lie Algebras

| Name | Notation | Matrices | Dimension |
|------|----------|----------|-----------|
| General linear | $\mathfrak{gl}_n$ | All $n \times n$ | $n^2$ |
| Special linear | $\mathfrak{sl}_n$ | Traceless | $n^2 - 1$ |
| Orthogonal | $\mathfrak{so}_n$ | Skew-symmetric | $\frac{n(n-1)}{2}$ |
| Symplectic | $\mathfrak{sp}_{2n}$ | Special form | $n(2n+1)$ |
| Unitary | $\mathfrak{u}_n$ | Skew-Hermitian | $n^2$ |

---

# <span class="header-remark">Applications</span>

## 1. Quantum Mechanics

**Observables**: Hermitian operators form Lie algebra

**Commutation relations**: $[x, p] = i\hbar$

**Symmetries**: Angular momentum, spin

**Heisenberg equation**: $\frac{d}{dt}A = \frac{1}{i\hbar}[H, A]$

---

## 2. Differential Geometry

**Vector fields**: Tangent spaces with Lie bracket

**Curvature**: Measured by brackets

**Connection**: Covariant derivative

**Foliations**: Involutive distributions (Frobenius theorem)

---

## 3. Lie Groups

**Lie algebra $\leftrightarrow$ Lie group**

**Exponential map**: $\exp: \mathfrak{g} \to G$

**Baker-Campbell-Hausdorff formula**:

$$\exp(X) \exp(Y) = \exp\left(X + Y + \frac{1}{2}[X, Y] + \cdots\right)$$

---

## 4. Physics

**Gauge theories**: Yang-Mills, Standard Model

**Symmetries**: Conservation laws (Noether)

**Particle physics**: $\mathfrak{su}_3$ (QCD), $\mathfrak{su}_2 \oplus \mathfrak{u}_1$ (electroweak)

**String theory**: Virasoro algebra, Kac-Moody algebras

---

## 5. Control Theory

**Controllability**: Lie bracket of vector fields

**Optimal control**: Pontryagin maximum principle

**Robotics**: Configuration spaces

---

## 6. Representation Theory

**Modules over Lie algebras**: Representations

**Weight spaces**: Cartan subalgebra action

**Highest weight representations**: Classification

---

# <span class="header-remark">Historical Context</span>

**Sophus Lie** (1842-1899):
- Invented Lie theory (1870s)
- Continuous transformation groups
- Lie algebras as "infinitesimal generators"

**Wilhelm Killing** (1847-1923):
- Classification of simple Lie algebras (1888)
- Killing form
- Root systems

**Élie Cartan** (1869-1951):
- Completed classification (1894)
- Cartan subalgebras
- Exceptional Lie algebras

**Hermann Weyl** (1885-1955):
- Representation theory (1920s)
- Character formulas
- Compact Lie groups

**Armand Borel, Jacques Tits** (20th century):
- Algebraic groups
- Buildings
- Modern structure theory

---

# <span class="header-remark">Related Concepts</span>

## Core Theory

- [[Vector Space]]: Underlying structure
- [[Bilinear Map]]: Bracket is bilinear
- [[Commutator in Ring]]: Special case in associative algebras
- [[Jacobi Idenity]]: Fundamental axiom
- [[Derivation]]: ad-map is derivation

## Lie Algebra Theory

- [[Lie Algebra]]: General theory
- [[Simple Lie Algebra]]: No proper ideals
- [[Semisimple Lie Algebra]]: Direct sum of simple
- [[Killing Form]]: Invariant bilinear form
- [[Cartan Subalgebra]]: Maximal abelian

## Connections

- [[Lie Group]]: Integration of Lie algebras
- [[Exponential Map]]: Lie algebra to Lie group
- [[Baker-Campbell-Hausdorff Formula]]: Product formula
- [[Universal Enveloping Algebra]]: Associative hull
- [[Representation]]: Modules over Lie algebras

## Geometric

- [[Vector Field]]: Lie bracket of vector fields
- [[Differential Forms]]: Exterior derivative
- [[Connection]]: Covariant derivative
- [[Curvature]]: From brackets

## Physics

- [[Quantum Mechanics]]: Canonical commutation relations
- [[Gauge Theory]]: Symmetries
- [[Angular Momentum]]: $\mathfrak{so}_3$
- [[Poisson Bracket]]: Classical mechanics

## Applications

- [[Representation Theory]]: Modules and characters
- [[Root System]]: Classification
- [[Dynkin Diagram]]: Graphical representation
- [[Weyl Character Formula]]: Dimensions

