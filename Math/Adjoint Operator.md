# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Inner Product]]
- [[Dual Spaces]]
- [[Hilbert Space]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Friedberg, Linear Algebra
- Conway, A Course in Functional Analysis
- Rudin, Functional Analysis

---

# <span class="header-definition">Definition</span>

**Adjoint Operator^[수반 연산자]** (또는 **Adjoint^[수반]**)는 내적 공간에서 정의되는 특별한 연산자로, transpose의 일반화이다.

## Inner Product Space Definition

$V, W$ inner product spaces over $\mathbb{F}$ ($\mathbb{R}$ or $\mathbb{C}$)

$T: V \to W$ linear operator

**Definition**: $T$의 **adjoint** $T^*: W \to V$는 다음을 만족하는 유일한 linear operator:

$$\langle T(v), w \rangle_W = \langle v, T^*(w) \rangle_V$$

for all $v \in V$, $w \in W$

**표기**: $T^*$ (읽기: "T star" 또는 "T adjoint")

## Hilbert Space Definition

$H_1, H_2$ Hilbert spaces

$T: H_1 \to H_2$ bounded linear operator

**Definition**: $T^*: H_2 \to H_1$는 다음을 만족:

$$\langle Tx, y \rangle_{H_2} = \langle x, T^*y \rangle_{H_1}$$

for all $x \in H_1$, $y \in H_2$

자세한 내용은 [[Hilbert Space]] 참조

## Matrix Representation

$V = \mathbb{R}^n$, $W = \mathbb{R}^m$ with standard inner product

$T$ represented by matrix $A$

**Adjoint**: $T^*$ represented by $A^T$ (transpose)

---

$V = \mathbb{C}^n$, $W = \mathbb{C}^m$ with standard inner product

$T$ represented by matrix $A$

**Adjoint**: $T^*$ represented by $A^*$ (conjugate transpose^[켤레 전치])

$$A^* = \overline{A^T}$$

**Notation**: 
- $A^*$ (physics, functional analysis)
- $A^\dagger$ (physics, quantum mechanics)
- $A^H$ (engineering, signal processing)

---

# <span class="header-theorem">Existence and Uniqueness</span>

## Finite-Dimensional Case

**정리**: $V, W$ finite-dimensional inner product spaces, $T: V \to W$ linear

$\Rightarrow$ $T^*$ exists and is unique

### Proof of Existence

**Step 1**: Fix $w \in W$

Define functional $\phi_w: V \to \mathbb{F}$:

$$\phi_w(v) = \langle T(v), w \rangle$$

**Step 2**: $\phi_w$ is linear functional

$$\phi_w(\alpha v_1 + \beta v_2) = \langle T(\alpha v_1 + \beta v_2), w \rangle$$

$$= \alpha \langle T(v_1), w \rangle + \beta \langle T(v_2), w \rangle$$

$$= \alpha \phi_w(v_1) + \beta \phi_w(v_2)$$ ✓

**Step 3**: Riesz Representation Theorem

$\exists!$ unique $u \in V$ such that:

$$\phi_w(v) = \langle v, u \rangle$$

자세한 내용은 [[Riesz Representation Theorem]] 참조

**Step 4**: Define $T^*$

$$T^*(w) = u$$

Then:

$$\langle T(v), w \rangle = \phi_w(v) = \langle v, u \rangle = \langle v, T^*(w) \rangle$$ ✓

### Proof of Uniqueness

Suppose $S_1, S_2$ both satisfy adjoint property:

$$\langle T(v), w \rangle = \langle v, S_1(w) \rangle = \langle v, S_2(w) \rangle$$

for all $v, w$

Then:

$$\langle v, S_1(w) - S_2(w) \rangle = 0$$

for all $v$

Choose $v = S_1(w) - S_2(w)$:

$$\|S_1(w) - S_2(w)\|^2 = 0$$

$$S_1(w) = S_2(w)$$ for all $w$

$$S_1 = S_2$$ ✓

## Infinite-Dimensional Case

**정리**: $H_1, H_2$ Hilbert spaces, $T: H_1 \to H_2$ **bounded** linear operator

$\Rightarrow$ $T^*$ exists and is unique

**Proof**: Same as finite-dimensional (Riesz representation holds in Hilbert spaces)

### Important Caveat

**Unbounded operators**: Adjoint may not exist or may have restricted domain!

**Example**: $\frac{d}{dx}$ on $L^2[0,1]$

Domain of $\left(\frac{d}{dx}\right)^*$ is not all of $L^2[0,1]$

**Advanced topic**: Self-adjoint extensions, spectral theory

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Linearity

$$(S + T)^* = S^* + T^*$$

$$(cT)^* = \overline{c} T^*$$

**주의**: Complex case에서 scalar는 conjugate!

**증명**:

$$\langle (cT)(v), w \rangle = \langle cT(v), w \rangle = c \langle T(v), w \rangle$$

$$= c \langle v, T^*(w) \rangle = \langle v, \overline{c} T^*(w) \rangle$$ ✓

### 2. Involution

$$(T^*)^* = T$$

**의미**: Taking adjoint twice returns original operator

**증명**:

$$\langle T^*(w), v \rangle = \overline{\langle v, T^*(w) \rangle}$$

$$= \overline{\langle T(v), w \rangle} = \langle w, T(v) \rangle$$ ✓

### 3. Composition

$$(ST)^* = T^* S^*$$

**주의**: Order reverses! (Like transpose)

**증명**:

$$\langle (ST)(v), w \rangle = \langle S(T(v)), w \rangle$$

$$= \langle T(v), S^*(w) \rangle = \langle v, T^*(S^*(w)) \rangle$$

$$= \langle v, (T^* S^*)(w) \rangle$$ ✓

### 4. Identity

$$I^* = I$$

**증명**:

$$\langle I(v), w \rangle = \langle v, w \rangle = \langle v, I(w) \rangle$$ ✓

### 5. Inverse

If $T$ invertible:

$$(T^{-1})^* = (T^*)^{-1}$$

**표기**: $T^{-*}$ or $(T^*)^{-1}$

**증명**:

$$\langle T^{-1}(v), w \rangle = \langle v, (T^{-1})^*(w) \rangle$$

Apply $T$:

$$\langle v, T^*w \rangle = \langle T(T^{-1}(v)), w \rangle = \langle v, w \rangle$$

$\Rightarrow$ $T^* (T^{-1})^* = I$

$\Rightarrow$ $(T^{-1})^* = (T^*)^{-1}$ ✓

## Norm and Operator Norm

### Operator Norm Equality

$$\|T^*\| = \|T\|$$

**증명**:

$$\|T^*\| = \sup_{\|w\|=1} \|T^*(w)\|$$

$$= \sup_{\|w\|=1} \sup_{\|v\|=1} |\langle T^*(w), v \rangle|$$

$$= \sup_{\|w\|=1} \sup_{\|v\|=1} |\langle w, T(v) \rangle|$$

$$= \sup_{\|v\|=1} \sup_{\|w\|=1} |\langle T(v), w \rangle|$$

$$= \sup_{\|v\|=1} \|T(v)\| = \|T\|$$ ✓

### Norm Identity

$$\|T^* T\| = \|T\|^2$$

**증명**:

$$\|T(v)\|^2 = \langle T(v), T(v) \rangle = \langle v, T^*T(v) \rangle$$

$$\leq \|v\| \cdot \|T^*T(v)\| \leq \|v\|^2 \cdot \|T^*T\|$$

$\Rightarrow$ $\|T\|^2 \leq \|T^*T\|$

Also:

$$\|T^*T\| \leq \|T^*\| \cdot \|T\| = \|T\|^2$$

$\Rightarrow$ $\|T^*T\| = \|T\|^2$ ✓

## Kernel and Range Relationships

### 1. Kernel and Range Orthogonality

$$\ker(T^*) = (\text{range}(T))^\perp$$

$$\ker(T) = (\text{range}(T^*))^\perp$$

**증명**:

$w \in \ker(T^*)$

$\Leftrightarrow$ $T^*(w) = 0$

$\Leftrightarrow$ $\langle v, T^*(w) \rangle = 0$ for all $v$

$\Leftrightarrow$ $\langle T(v), w \rangle = 0$ for all $v$

$\Leftrightarrow$ $w \perp \text{range}(T)$

$\Leftrightarrow$ $w \in (\text{range}(T))^\perp$ ✓

### 2. Range Closure

If $\text{range}(T)$ is closed:

$$\text{range}(T) = (\ker(T^*))^\perp$$

$$\text{range}(T^*) = (\ker(T))^\perp$$

**증명**: Use orthogonal decomposition

$$W = \text{range}(T) \oplus (\text{range}(T))^\perp$$

$$= \text{range}(T) \oplus \ker(T^*)$$ ✓

### 3. Rank Equality

Finite-dimensional case:

$$\text{rank}(T) = \text{rank}(T^*)$$

**증명**:

$$\text{rank}(T) = \dim(\text{range}(T))$$

$$= n - \dim(\ker(T^*))$$ (by orthogonality)

$$= \dim(\text{range}(T^*)) = \text{rank}(T^*)$$ ✓

## Special Operator Classes

### Self-Adjoint Operators

**Definition**: $T^* = T$

$$\langle T(v), w \rangle = \langle v, T(w) \rangle$$

**Real case**: Called **symmetric**

**Complex case**: Called **Hermitian**

**Properties**:
- All eigenvalues are **real**
- Eigenvectors for different eigenvalues are **orthogonal**

자세한 내용은 [[Normal Operator]] 참조

### Unitary Operators

**Definition**: $T^* T = T T^* = I$

$$T^* = T^{-1}$$

**Properties**:
- **Preserves inner product**: $\langle T(v), T(w) \rangle = \langle v, w \rangle$
- **Preserves norm**: $\|T(v)\| = \|v\|$
- All eigenvalues have $|\lambda| = 1$

자세한 내용은 [[Unitary Matrix]], [[Orthogonal Matrix]] 참조

### Normal Operators

**Definition**: $T^* T = T T^*$

**의미**: $T$ commutes with its adjoint

**Properties**:
- **Spectral theorem**: Has orthonormal eigenbasis
- $\|T(v)\| = \|T^*(v)\|$ for all $v$

자세한 내용은 [[Normal Operator]], [[Spectral Theorem]] 참조

### Skew-Adjoint Operators

**Definition**: $T^* = -T$

$$\langle T(v), w \rangle = -\langle v, T(w) \rangle$$

**Properties**:
- Eigenvalues are **purely imaginary** (or zero)
- $e^{tT}$ is unitary for real $t$

**Example**: $i\frac{d}{dx}$ (momentum operator in quantum mechanics)

### Positive Operators

**Definition**: $T$ self-adjoint and $\langle T(v), v \rangle \geq 0$ for all $v$

**Equivalent**: All eigenvalues $\geq 0$

**Notation**: $T \geq 0$ or $T$ positive semidefinite^[양의 준정부호]

**Strict positivity**: $T > 0$ if $\langle T(v), v \rangle > 0$ for all $v \neq 0$

---

# <span class="header-examples">Examples</span>

## Example 1: Matrix Adjoint (Real)

$$A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}$$

**Adjoint**:

$$A^* = A^T = \begin{pmatrix} 1 & 3 \\ 2 & 4 \end{pmatrix}$$

**Verification**:

$$\langle A\mathbf{x}, \mathbf{y} \rangle = (A\mathbf{x})^T \mathbf{y} = \mathbf{x}^T A^T \mathbf{y} = \langle \mathbf{x}, A^T \mathbf{y} \rangle$$ ✓

## Example 2: Matrix Adjoint (Complex)

$$A = \begin{pmatrix} 1+i & 2 \\ 3i & 4-i \end{pmatrix}$$

**Adjoint** (conjugate transpose):

$$A^* = \overline{A^T} = \begin{pmatrix} 1-i & -3i \\ 2 & 4+i \end{pmatrix}$$

**Verification**:

$$\langle A\mathbf{z}, \mathbf{w} \rangle = (A\mathbf{z})^* \mathbf{w} = \mathbf{z}^* A^* \mathbf{w} = \langle \mathbf{z}, A^* \mathbf{w} \rangle$$ ✓

## Example 3: Symmetric Matrix

$$A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}$$

**Adjoint**: $A^* = A^T = A$ (self-adjoint!)

**Properties**:
- Eigenvalues: $\lambda_1 = \frac{5+\sqrt{5}}{2}$, $\lambda_2 = \frac{5-\sqrt{5}}{2}$ (both real)
- Eigenvectors are orthogonal

자세한 내용은 [[Symmetric Matrix]] 참조

## Example 4: Multiplication Operator

$V = L^2[0,1]$, inner product:

$$\langle f, g \rangle = \int_0^1 f(x) \overline{g(x)} dx$$

**Operator**: $(M_\phi f)(x) = \phi(x) f(x)$ (multiplication by $\phi$)

**Adjoint**: $(M_\phi^* f)(x) = \overline{\phi(x)} f(x)$

**증명**:

$$\langle M_\phi f, g \rangle = \int_0^1 \phi(x) f(x) \overline{g(x)} dx$$

$$= \int_0^1 f(x) \overline{\overline{\phi(x)} g(x)} dx = \langle f, M_{\overline{\phi}} g \rangle$$ ✓

**Self-adjoint**: $M_\phi^* = M_\phi$ $\Leftrightarrow$ $\phi$ is real-valued

## Example 5: Differentiation Operator

$V = \{f \in C^1[0,1] : f(0) = f(1) = 0\}$

Inner product: $\langle f, g \rangle = \int_0^1 f(x) \overline{g(x)} dx$

**Operator**: $T(f) = f'$

**Adjoint**: $(T^* g)(x) = -g'(x)$

**증명** (integration by parts):

$$\langle f', g \rangle = \int_0^1 f'(x) \overline{g(x)} dx$$

$$= [f(x)\overline{g(x)}]_0^1 - \int_0^1 f(x) \overline{g'(x)} dx$$

$$= 0 - \int_0^1 f(x) \overline{g'(x)} dx$$ (boundary terms vanish)

$$= \int_0^1 f(x) \overline{(-g'(x))} dx = \langle f, -g' \rangle$$ ✓

**Not self-adjoint**: $T^* = -T$ (skew-adjoint)

## Example 6: Shift Operator

$V = \ell^2(\mathbb{N})$ (square-summable sequences)

**Right shift**: $S(x_1, x_2, x_3, \ldots) = (0, x_1, x_2, \ldots)$

**Adjoint** (left shift): $S^*(x_1, x_2, x_3, \ldots) = (x_2, x_3, x_4, \ldots)$

**Verification**:

$$\langle S\mathbf{x}, \mathbf{y} \rangle = \sum_{n=1}^{\infty} (S\mathbf{x})_n \overline{y_n}$$

$$= 0 \cdot \overline{y_1} + x_1 \overline{y_2} + x_2 \overline{y_3} + \cdots$$

$$= \sum_{n=1}^{\infty} x_n \overline{y_{n+1}} = \langle \mathbf{x}, S^*\mathbf{y} \rangle$$ ✓

**Properties**:
- $S^* S = I$ (but $S S^* \neq I$!)
- $S$ is **isometry** but not unitary

## Example 7: Projection Operator

$V = \mathbb{R}^3$, $W = \text{span}\{(1,0,0), (0,1,0)\}$ (xy-plane)

**Orthogonal projection**: $P(x,y,z) = (x,y,0)$

**Adjoint**: $P^* = P$ (self-adjoint!)

**General**: Orthogonal projections are always self-adjoint

**Matrix form**:

$$P = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix} = P^T$$ ✓

---

# <span class="header-examples">Applications</span>

## 1. Least Squares

**Problem**: Solve $A\mathbf{x} = \mathbf{b}$ when no exact solution exists

**Normal equations**:

$$A^* A \mathbf{x} = A^* \mathbf{b}$$

**Solution**: $\mathbf{x} = (A^* A)^{-1} A^* \mathbf{b}$ (if $A^* A$ invertible)

**Derivation**: Minimize $\|A\mathbf{x} - \mathbf{b}\|^2$

$$\frac{\partial}{\partial \mathbf{x}} \langle A\mathbf{x} - \mathbf{b}, A\mathbf{x} - \mathbf{b} \rangle = 0$$

$$\Rightarrow A^* A \mathbf{x} = A^* \mathbf{b}$$ ✓

## 2. Quantum Mechanics

**Observables**: Self-adjoint operators

**Hermitian operators**: $H^* = H$

**Physical meaning**: Real-valued measurements

**Examples**:
- Position: $\hat{x}$
- Momentum: $\hat{p} = -i\hbar \frac{d}{dx}$
- Hamiltonian: $\hat{H} = -\frac{\hbar^2}{2m}\nabla^2 + V(\mathbf{x})$

**Unitary evolution**: $U(t) = e^{-iHt/\hbar}$

## 3. Signal Processing

**Convolution operator**: $T(f) = f * h$

**Adjoint**: $T^*(g) = g * \tilde{h}$

where $\tilde{h}(t) = \overline{h(-t)}$ (time-reversed conjugate)

**Matched filter**: Use $T^*$ for optimal detection

## 4. Differential Equations

**Boundary value problem**: $L u = f$

$L$ differential operator

**Adjoint problem**: $L^* v = g$

**Green's function**: Uses adjoint operator

**Self-adjoint case**: Symmetric boundary conditions

## 5. Optimization

**Gradient**: $\nabla f = A^* A \mathbf{x} - A^* \mathbf{b}$

**Adjoint method**: Efficient gradient computation in high dimensions

**Backpropagation**: Composition of adjoint operators

## 6. Functional Analysis

**Dual space**: $V^* = \{\phi: V \to \mathbb{F} \text{ linear}\}$

**Riesz map**: $V \to V^*$ via inner product

**Adjoint**: Connects $\mathcal{L}(V,W)$ and $\mathcal{L}(W,V)$

자세한 내용은 [[Dual Spaces]] 참조

---

# <span class="header-remark">Remark</span>

## Adjoint vs Transpose

### Similarities

- Both satisfy $(AB)^* = B^* A^*$
- Both satisfy $(A^*)^* = A$
- Matrix representation connection

### Differences

| Property | Transpose | Adjoint |
|----------|-----------|---------|
| **Definition** | $(A^T)_{ij} = A_{ji}$ | $\langle T(v), w \rangle = \langle v, T^*(w) \rangle$ |
| **Context** | Matrices | Inner product spaces |
| **Conjugation** | No conjugation | Conjugation (complex case) |
| **Dependency** | Independent of inner product | Depends on inner product |

### Key Insight

**Real inner product space**: Adjoint = Transpose

**Complex inner product space**: Adjoint = Conjugate Transpose

**General inner product**: Adjoint depends on chosen inner product!

## Different Inner Products Give Different Adjoints

**Example**: $\mathbb{R}^2$ with two inner products

**Standard inner product**: $\langle \mathbf{x}, \mathbf{y} \rangle_1 = x_1 y_1 + x_2 y_2$

**Weighted inner product**: $\langle \mathbf{x}, \mathbf{y} \rangle_2 = 2x_1 y_1 + x_2 y_2$

**Operator**: $T(x_1, x_2) = (x_2, x_1)$ (swap)

**Adjoint w.r.t. $\langle \cdot, \cdot \rangle_1$**: $T^* = T$ (self-adjoint)

**Adjoint w.r.t. $\langle \cdot, \cdot \rangle_2$**: 

$$T^*(x_1, x_2) = \left(\frac{1}{2}x_2, 2x_1\right)$$

**Different adjoints for different inner products!**

## Bounded vs Unbounded Operators

### Bounded Operators

**Definition**: $\exists C$ such that $\|T(v)\| \leq C \|v\|$ for all $v$

**Adjoint**: Always exists and is bounded

**Domain**: $\text{dom}(T^*) = W$ (entire space)

### Unbounded Operators

**Definition**: No such $C$ exists

**Adjoint**: May exist but domain $\text{dom}(T^*) \subsetneq W$

**Example**: $\frac{d}{dx}$ on $L^2[0,1]$

- $\text{dom}(T) = H^1[0,1]$ (Sobolev space)
- $\text{dom}(T^*) = H^1[0,1]$ with boundary conditions

**Self-adjoint extension**: Advanced topic in spectral theory

## Notation Conventions

Different fields use different notation:

| Notation | Field | Meaning |
|----------|-------|---------|
| $A^*$ | Functional analysis, physics | Adjoint |
| $A^\dagger$ | Quantum mechanics | Hermitian conjugate |
| $A^H$ | Engineering, signal processing | Hermitian transpose |
| $A^T$ | Linear algebra | Transpose |
| $\bar{A}$ | Complex analysis | Complex conjugate |

**This document**: Use $T^*$ for adjoint

## Relationship to Dual Map

**Dual space**: $V^* = \{f: V \to \mathbb{F} \text{ linear}\}$

**Dual map**: $T': W^* \to V^*$

$$T'(\phi) = \phi \circ T$$

**Riesz isomorphism**: $V \cong V^*$ (inner product spaces)

$$v \mapsto \langle \cdot, v \rangle$$

**Adjoint = Dual map under Riesz isomorphism**:

```
     T
V -------> W
|          |
| Riesz    | Riesz
|          |
V* <------ W*
     T'
```

Adjoint $T^*$ makes diagram commute

자세한 내용은 [[Dual of a Linear Map]] 참조

## Historical Context

**Hermann Grassmann** (1809-1877): Early work on duality

**Hermann Weyl** (1885-1955): Adjoint operators in differential equations

**John von Neumann** (1903-1957): Unbounded self-adjoint operators

**Frigyes Riesz** (1880-1956): Riesz representation theorem

**Fundamental importance**: Foundation of spectral theory and quantum mechanics

## Computational Considerations

### Matrix Case

**Computing $A^*$**:
- Real: Simple transpose (no extra cost)
- Complex: Transpose + conjugate ($O(n^2)$)

**Storage**: Same as original matrix

### Operator Case

**Implicit representation**: Store $T$, compute $T^*$ action on-demand

**Adjoint-vector product**: Often as cheap as forward multiplication

**Automatic differentiation**: Computes adjoints automatically

## Common Patterns

### Pattern 1: Self-Adjoint Analysis

**Problem**: Analyze operator properties

**Check**: Is $T^* = T$?

**Benefit**: Real eigenvalues, orthogonal eigenvectors

### Pattern 2: Normal Equations

**Problem**: Solve $T\mathbf{x} = \mathbf{b}$ (overconstrained)

**Transform**: $T^* T \mathbf{x} = T^* \mathbf{b}$

**Result**: Square system (often better conditioned)

### Pattern 3: Adjoint Method

**Problem**: Compute gradient of $f(T(\mathbf{x}))$

**Method**: Use chain rule with $T^*$

**Efficiency**: Backpropagation, adjoint sensitivity

## Limitations and Caveats

### 1. Requires Inner Product

Adjoint only defined in inner product spaces

**Alternative**: Dual map (more general, but less structure)

### 2. Depends on Inner Product

Different inner products → different adjoints

**Warning**: Must specify which inner product!

### 3. Unbounded Operators

Domain issues, self-adjoint extensions

**Advanced topic**: Operator theory, spectral theory

### 4. Numerical Computation

Explicitly forming $T^*$ may be expensive or ill-conditioned

**Solution**: Use adjoint-vector products instead

## 관련 개념

- [[Normal Operator]]: Operators commuting with adjoint
- [[Spectral Theorem]]: Uses adjoint crucially
- [[Singular Value Decomposition]]: $A^* A$ and $A A^*$
- [[Symmetric Matrix]]: Real self-adjoint matrices
- [[Unitary Matrix]]: $U^* = U^{-1}$
- [[Orthogonal Matrix]]: Real unitary matrices
- [[Inner Product]]: Foundation for adjoint
- [[Dual Spaces]]: Relationship to dual map
- [[Hilbert Space]]: Setting for unbounded adjoints
- [[Riesz Representation Theorem]]: Existence proof

