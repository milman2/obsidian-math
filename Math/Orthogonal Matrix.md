# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Inner Product]]
- [[Eigen Value, Eigen Vector]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Strang, Introduction to Linear Algebra

---

# <span class="header-definition">Definition</span>

## Orthogonal Matrix^[직교 행렬]

**Real matrix** $Q \in M_n(\mathbb{R})$가 **orthogonal**^[직교]이다 $\Leftrightarrow$

$$Q^T Q = I$$

**동등한 조건**:
- $Q Q^T = I$ (also holds)
- $Q^{-1} = Q^T$ (inverse = transpose)
- $Q$의 columns는 **orthonormal basis**
- $Q$의 rows는 **orthonormal basis**

**의미**: "Inner product를 보존하는 linear transformation"

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Inverse

$$Q^{-1} = Q^T$$

Very easy to compute inverse!

### 2. Determinant

$$\det(Q) = \pm 1$$

**증명**:

$$1 = \det(I) = \det(Q^T Q) = \det(Q^T) \det(Q) = \det(Q)^2$$

따라서 $\det(Q) = \pm 1$ 
### 3. Eigenvalues

Complex eigenvalues have $|\lambda| = 1$ (unit modulus)

Real eigenvalues: $\lambda = \pm 1$

### 4. Product

$Q_1, Q_2$ orthogonal $\Rightarrow$ $Q_1 Q_2$ orthogonal

$$(Q_1 Q_2)^T (Q_1 Q_2) = Q_2^T Q_1^T Q_1 Q_2 = Q_2^T Q_2 = I$$ 
**Group**: Orthogonal matrices form a **group** $O(n)$

## Geometric Properties

### Inner Product Preservation

$$\langle Q\mathbf{x}, Q\mathbf{y} \rangle = \langle \mathbf{x}, \mathbf{y} \rangle$$

**증명**:

$$\langle Q\mathbf{x}, Q\mathbf{y} \rangle = (Q\mathbf{x})^T (Q\mathbf{y}) = \mathbf{x}^T Q^T Q \mathbf{y} = \mathbf{x}^T \mathbf{y} = \langle \mathbf{x}, \mathbf{y} \rangle$$ 
### Length Preservation (Isometry)

$$\|Q\mathbf{x}\| = \|\mathbf{x}\|$$

**증명**: $\|Q\mathbf{x}\|^2 = \langle Q\mathbf{x}, Q\mathbf{x} \rangle = \langle \mathbf{x}, \mathbf{x} \rangle = \|\mathbf{x}\|^2$ 
**의미**: Orthogonal transformation은 **거리를 보존**

### Angle Preservation

$$\cos\theta = \frac{\langle \mathbf{x}, \mathbf{y} \rangle}{\|\mathbf{x}\| \|\mathbf{y}\|}$$

$Q$ preserves inner products and lengths $\Rightarrow$ preserves angles

**의미**: **Rigid motion**^[강체 운동] (rotation + reflection)

## Column/Row Properties

### Orthonormal Columns

$Q = [\mathbf{q}_1 | \mathbf{q}_2 | \cdots | \mathbf{q}_n]$

$$Q^T Q = I \Leftrightarrow \mathbf{q}_i^T \mathbf{q}_j = \delta_{ij}$$

즉:
- $\|\mathbf{q}_i\| = 1$ (unit length)
- $\mathbf{q}_i \perp \mathbf{q}_j$ for $i \neq j$ (orthogonal)

### Orthonormal Rows

$Q Q^T = I$ also holds

Rows도 orthonormal basis!

---

# <span class="header-examples">Examples</span>

## Example 1: Identity

$$I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$$

Trivially orthogonal

## Example 2: Reflection

$$R = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}$$

**Check**: $R^T R = I$ 
**Geometric**: Reflection about $x$-axis

**Determinant**: $\det(R) = -1$

## Example 3: Rotation

$$R_\theta = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$

**Check**: 

$$R_\theta^T R_\theta = \begin{pmatrix} \cos\theta & \sin\theta \\ -\sin\theta & \cos\theta \end{pmatrix} \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix} = I$$ 
**Geometric**: Rotation by angle $\theta$

**Determinant**: $\det(R_\theta) = 1$

## Example 4: Permutation

$$P = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0 \end{pmatrix}$$

**Permutation matrices**: Orthogonal!

**Columns**: Standard basis vectors (permuted)

## Example 5: Householder Reflection

$$H = I - 2\mathbf{v}\mathbf{v}^T$$

where $\|\mathbf{v}\| = 1$

**Check**:

$$H^T H = (I - 2\mathbf{v}\mathbf{v}^T)^2 = I - 4\mathbf{v}\mathbf{v}^T + 4\mathbf{v}\mathbf{v}^T\mathbf{v}\mathbf{v}^T = I$$ 
**Geometric**: Reflection about hyperplane $\perp \mathbf{v}$

---

# <span class="header-definition">Orthogonal Group</span>

## $O(n)$: Orthogonal Group

$$O(n) = \{Q \in M_n(\mathbb{R}) : Q^T Q = I\}$$

**Group structure**:
- **Identity**: $I \in O(n)$
- **Closure**: $Q_1, Q_2 \in O(n) \Rightarrow Q_1 Q_2 \in O(n)$
- **Inverse**: $Q \in O(n) \Rightarrow Q^{-1} = Q^T \in O(n)$
- **Associativity**: Matrix multiplication

**Dimension**: $\frac{n(n-1)}{2}$ (as Lie group)

## $SO(n)$: Special Orthogonal Group

$$SO(n) = \{Q \in O(n) : \det(Q) = 1\}$$

**Subgroup** of $O(n)$

**의미**: **Rotations only** (no reflections)

**Properties**:
- $SO(2)$: 2D rotations (circle)
- $SO(3)$: 3D rotations
- Connected component of identity in $O(n)$

---

# <span class="header-theorem">Theorem</span>

## Spectral Theorem for Symmetric

**정리**: $A$ real symmetric

$$A = Q \Lambda Q^T$$

where $Q$ orthogonal, $\Lambda$ diagonal (real)

**의미**: Symmetric matrices are **orthogonally diagonalizable**

자세한 내용은 [[Symmetric Matrix]] 참조

## QR Decomposition

**정리**: 모든 invertible matrix $A$는 분해 가능:

$$A = QR$$

where $Q$ orthogonal, $R$ upper triangular

**응용**: Numerical linear algebra (eigenvalue algorithms)

## Polar Decomposition

**정리**: 모든 invertible matrix $A$는:

$$A = QS$$

where $Q$ orthogonal, $S$ symmetric positive definite

**의미**: Rotation × Scaling

## Normal Operator

Orthogonal matrix는 **normal**:

$$Q^T Q = I = Q Q^T$$ 
자세한 내용은 [[Normal Operator]] 참조

---

# <span class="header-remark">Remark</span>

## 기하학적 해석

Orthogonal transformations = **Rigid motions**^[강체 운동]

**$\det(Q) = 1$**: Rotation (orientation-preserving)

**$\det(Q) = -1$**: Rotation + Reflection (orientation-reversing)

### 2D Case

$$O(2) = \text{Rotations} \cup \text{Reflections}$$

$$SO(2) = \{\text{Rotations}\} \cong S^1$$ (circle)

### 3D Case

$$SO(3) = \{\text{3D Rotations}\}$$

Euler angles, axis-angle representation

## 응용

### 1. Computer Graphics

Rotations, reflections, camera transformations

Orthogonal matrices preserve shape!

### 2. Numerical Linear Algebra

**QR algorithm**: Eigenvalue computation

**Orthogonal iteration**: Stable numerics

### 3. Principal Component Analysis (PCA)

Covariance matrix: $A = Q \Lambda Q^T$

$Q$ columns = principal components (orthogonal!)

### 4. Least Squares

QR decomposition for solving $A\mathbf{x} = \mathbf{b}$

### 5. Quantum Mechanics

Evolution operators (real case): Orthogonal

**Time evolution**: $U(t) = e^{iHt}$ (unitary, not orthogonal)

### 6. Signal Processing

**Discrete Cosine Transform (DCT)**: Orthogonal matrix

**Wavelet transforms**: Orthogonal bases

### 7. Optimization on Manifolds

$O(n)$, $SO(n)$ as Riemannian manifolds

**Procrustes problem**: Find optimal rotation

## Computational Advantages

### Easy Inverse

$Q^{-1} = Q^T$ (just transpose!)

### Numerical Stability

Orthogonal transformations don't amplify errors

**Condition number**: $\kappa(Q) = 1$ (perfect!)

### Preserves Structure

Inner products, norms, angles all preserved

## Orthogonal vs Unitary

| Property | Orthogonal ($\mathbb{R}$) | Unitary ($\mathbb{C}$) |
|----------|-----------------|---------------|
| Condition | $Q^T Q = I$ | $U^* U = I$ |
| Entries | Real | Complex |
| Determinant | $\pm 1$ | $\|det\| = 1$ |
| Eigenvalues | $\pm 1$ (real) | $\|\lambda\| = 1$ |
| Group | $O(n)$ | $U(n)$ |

자세한 내용은 [[Unitary Matrix]] 참조

## 관련 개념

- [[Unitary Matrix]]: Complex generalization
- [[Symmetric Matrix]]: Orthogonally diagonalizable
- [[Normal Operator]]: General framework
- [[Diagonal Matrix]]: Target of diagonalization
- [[Eigen Value, Eigen Vector]]: Spectral theory

