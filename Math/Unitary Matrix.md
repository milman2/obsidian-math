# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Inner Product]]
- [[Orthogonal Matrix]]
- [[Eigen Value, Eigen Vector]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Friedberg, Linear Algebra
- Conway, A Course in Functional Analysis

---

# <span class="header-definition">Definition</span>

## Unitary Matrix^[유니타리 행렬]

**Complex matrix** $U \in M_n(\mathbb{C})$가 **unitary**^[유니타리]이다 $\Leftrightarrow$

$$U^* U = I$$

여기서 $U^* = \overline{U^T}$ (conjugate transpose^[켤레 전치])

**동등한 조건**:
- $U U^* = I$ (also holds)
- $U^{-1} = U^*$ (inverse = conjugate transpose)
- $U$의 columns는 **orthonormal basis** (complex inner product)
- $U$의 rows는 **orthonormal basis**

**의미**: "Complex inner product를 보존하는 linear transformation"

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Inverse

$$U^{-1} = U^*$$

Easy to compute!

### 2. Determinant

$$|\det(U)| = 1$$

**증명**:

$$1 = \det(I) = \det(U^* U) = \det(U^*) \det(U) = \overline{\det(U)} \det(U) = |\det(U)|^2$$

따라서 $|\det(U)| = 1$ 
$\det(U) = e^{i\theta}$ for some $\theta \in \mathbb{R}$

### 3. Eigenvalues

모든 eigenvalue는 **unit modulus**: $|\lambda| = 1$

**증명**: $U\mathbf{v} = \lambda \mathbf{v}$, $\mathbf{v} \neq 0$

$$\|\mathbf{v}\|^2 = \|U\mathbf{v}\|^2 = \|\lambda \mathbf{v}\|^2 = |\lambda|^2 \|\mathbf{v}\|^2$$

따라서 $|\lambda| = 1$ 
### 4. Product

$U_1, U_2$ unitary $\Rightarrow$ $U_1 U_2$ unitary

$$(U_1 U_2)^* (U_1 U_2) = U_2^* U_1^* U_1 U_2 = U_2^* U_2 = I$$ 
**Group**: Unitary matrices form a **group** $U(n)$

## Geometric Properties

### Complex Inner Product Preservation

$$\langle U\mathbf{x}, U\mathbf{y} \rangle = \langle \mathbf{x}, \mathbf{y} \rangle$$

여기서 $\langle \mathbf{x}, \mathbf{y} \rangle = \mathbf{y}^* \mathbf{x}$

**증명**:

$$\langle U\mathbf{x}, U\mathbf{y} \rangle = (U\mathbf{y})^* (U\mathbf{x}) = \mathbf{y}^* U^* U \mathbf{x} = \mathbf{y}^* \mathbf{x} = \langle \mathbf{x}, \mathbf{y} \rangle$$ 
### Length Preservation

$$\|U\mathbf{x}\| = \|\mathbf{x}\|$$

**증명**: $\|U\mathbf{x}\|^2 = \langle U\mathbf{x}, U\mathbf{x} \rangle = \langle \mathbf{x}, \mathbf{x} \rangle = \|\mathbf{x}\|^2$ 
**의미**: Isometry^[등거리 변환]

## Column/Row Properties

### Orthonormal Columns

$U = [\mathbf{u}_1 | \mathbf{u}_2 | \cdots | \mathbf{u}_n]$

$$U^* U = I \Leftrightarrow \mathbf{u}_i^* \mathbf{u}_j = \delta_{ij}$$

즉:
- $\|\mathbf{u}_i\| = 1$ (unit length)
- $\mathbf{u}_i^* \mathbf{u}_j = 0$ for $i \neq j$ (orthogonal)

### Orthonormal Rows

$U U^* = I$ also holds

Rows도 orthonormal!

---

# <span class="header-examples">Examples</span>

## Example 1: Identity

$$I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$$

Trivially unitary

## Example 2: Phase Shift

$$U = \begin{pmatrix} e^{i\theta} & 0 \\ 0 & e^{i\phi} \end{pmatrix}$$

**Check**: $U^* U = I$ 
**Geometric**: Independent phase shifts

**Determinant**: $\det(U) = e^{i(\theta + \phi)}$

## Example 3: Hadamard Matrix

$$H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$

**Check**:

$$H^* H = \frac{1}{2} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} = I$$ 
**응용**: Quantum computing (Hadamard gate)

## Example 4: Pauli Matrices (Normalized)

$$X = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad Y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \quad Z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$$

모두 unitary! (사실 Hermitian이면서 unitary)

## Example 5: DFT Matrix

**Discrete Fourier Transform**:

$$F_n = \frac{1}{\sqrt{n}} \begin{pmatrix} 1 & 1 & 1 & \cdots \\ 1 & \omega & \omega^2 & \cdots \\ 1 & \omega^2 & \omega^4 & \cdots \\ \vdots & \vdots & \vdots & \ddots \end{pmatrix}$$

where $\omega = e^{2\pi i / n}$

**Unitary**: $F_n^* F_n = I$ 
## Example 6: Complex Rotation

$$U = \begin{pmatrix} \cos\theta & -\sin\theta e^{i\phi} \\ \sin\theta e^{-i\phi} & \cos\theta \end{pmatrix}$$

Generalization of real rotation to complex

---

# <span class="header-definition">Unitary Group</span>

## $U(n)$: Unitary Group

$$U(n) = \{U \in M_n(\mathbb{C}) : U^* U = I\}$$

**Group structure**:
- **Identity**: $I \in U(n)$
- **Closure**: $U_1, U_2 \in U(n) \Rightarrow U_1 U_2 \in U(n)$
- **Inverse**: $U \in U(n) \Rightarrow U^{-1} = U^* \in U(n)$
- **Associativity**: Matrix multiplication

**Dimension**: $n^2$ (as real Lie group)

## $SU(n)$: Special Unitary Group

$$SU(n) = \{U \in U(n) : \det(U) = 1\}$$

**Subgroup** of $U(n)$

**Properties**:
- $SU(2)$: Covers rotations in 3D (double cover of $SO(3)$)
- Important in quantum mechanics and particle physics
- Dimension: $n^2 - 1$

## Relationship with Orthogonal

$$O(n) = U(n) \cap M_n(\mathbb{R})$$

**의미**: Orthogonal = Real unitary

$$\text{Orthogonal} \subset \text{Unitary}$$

자세한 내용은 [[Orthogonal Matrix]] 참조

---

# <span class="header-theorem">Theorem</span>

## Spectral Theorem for Normal

**정리**: $A$ normal (즉, $A^* A = A A^*$)

$$A = U \Lambda U^*$$

where $U$ unitary, $\Lambda$ diagonal (complex)

**의미**: Normal matrices are **unitarily diagonalizable**

**Special cases**:
- $A$ Hermitian: $\Lambda$ real
- $A$ unitary: $|\Lambda_{ii}| = 1$

자세한 내용은 [[Normal Operator]] 참조

## Unitary Diagonalization

**정리**: Matrix $A$가 **unitarily diagonalizable** $\Leftrightarrow$ $A$ is normal

**증명**:
- ($\Leftarrow$) Normal $\Rightarrow$ Spectral theorem
- ($\Rightarrow$) $A = U \Lambda U^*$ $\Rightarrow$ $A^* A = U \Lambda^* \Lambda U^* = U \Lambda \Lambda^* U^* = A A^*$ 
## Exponential Map

**정리**: $A$ Hermitian $\Rightarrow$ $e^{iA}$ unitary

**증명**:

$$(e^{iA})^* e^{iA} = e^{-iA^*} e^{iA} = e^{-iA} e^{iA} = e^0 = I$$ 
**의미**: Hermitian matrices generate unitary transformations

**Stone's theorem**: 연결 (quantum mechanics)

---

# <span class="header-remark">Remark</span>

## 기하학적 해석

Unitary transformations = Complex version of rotations

**Real case** ($U$ real): Rotations and reflections

**Complex case**: Generalized rotations with phase shifts

## 응용

### 1. Quantum Mechanics

**Quantum gates**: Unitary matrices

**Time evolution**: $U(t) = e^{-iHt/\hbar}$ (unitary!)

**Observables**: Hermitian $\Leftrightarrow$ Real eigenvalues

### 2. Signal Processing

**Fourier Transform**: Unitary operator

$$\mathcal{F}: L^2(\mathbb{R}) \to L^2(\mathbb{R})$$

Preserves energy: $\|\mathcal{F}f\| = \|f\|$

### 3. Quantum Computing

**Quantum gates**:
- Hadamard gate: $H$
- Pauli gates: $X, Y, Z$
- CNOT gate
- All unitary!

### 4. Numerical Linear Algebra

**Unitary iteration**: Stable algorithms

**QR algorithm**: Uses unitary transformations

### 5. Control Theory

**System stability**: Unitary evolution preserves state norm

### 6. Information Theory

**Quantum information**: Unitary channels (reversible)

## Computational Advantages

### Easy Inverse

$U^{-1} = U^*$ (conjugate transpose!)

### Numerical Stability

Condition number: $\kappa(U) = 1$ (perfect!)

No amplification of errors

### Preserves Structure

Complex inner products, norms preserved

## Unitary vs Orthogonal vs Hermitian

| Property | Unitary | Orthogonal | Hermitian |
|----------|---------|------------|-----------|
| Condition | $U^* U = I$ | $Q^T Q = I$ | $A^* = A$ |
| Field | $\mathbb{C}$ | $\mathbb{R}$ | $\mathbb{C}$ |
| Inverse | $U^{-1} = U^*$ | $Q^{-1} = Q^T$ | N/A |
| Eigenvalues | $\|\lambda\| = 1$ | $\lambda = \pm 1$ | $\lambda \in \mathbb{R}$ |
| Preserves | Inner product | Inner product | N/A |

**관계**:
- Orthogonal ⊂ Unitary (real subset)
- Unitary ∩ Hermitian = Special case

## Lie Group Structure

$U(n)$ is a **Lie group**:
- Smooth manifold
- Group operations smooth
- Tangent space at $I$ = $\mathfrak{u}(n)$ (Lie algebra)

**Lie algebra**: $\mathfrak{u}(n) = $ Skew-Hermitian matrices

$$A^* = -A$$

**Exponential map**: $\exp: \mathfrak{u}(n) \to U(n)$

## Physical Interpretation

### Quantum State Evolution

$$|\psi(t)\rangle = U(t) |\psi(0)\rangle$$

$U(t)$ unitary $\Rightarrow$ $\langle \psi(t) | \psi(t) \rangle = 1$ (normalization preserved)

### Symmetry Transformations

**Wigner's theorem**: Symmetries in quantum mechanics = Unitary or antiunitary

### Measurement

**Observable** $A$ Hermitian:

$$A = U \Lambda U^*$$

$U$ columns = measurement basis (orthonormal!)

## 관련 개념

- [[Orthogonal Matrix]]: Real case
- [[Normal Operator]]: General framework
- [[Inner Product]]: Preserved by unitary
- [[Eigen Value, Eigen Vector]]: Spectral theory
- [[Symmetric Matrix]]: Hermitian (real case)

