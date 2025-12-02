# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Symmetric Matrix]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Strang, Introduction to Linear Algebra

---

# <span class="header-definition">Definition</span>

## Antisymmetric Matrix^[반대칭 행렬]

(Also known as **Skew-Symmetric Matrix**^[비대칭 행렬])

**Real matrix** $A \in M_n(\mathbb{R})$가 **antisymmetric**^[반대칭]이다 $\Leftrightarrow$

$$A^T = -A$$

즉, $A_{ij} = -A_{ji}$ for all $i, j$

**기하학적 의미**: 주대각선에 대해 부호가 반대

## Complex Extension

**Skew-Hermitian**^[비에르미트] (복소수의 antisymmetric 일반화):

$$A^* = -A$$

여기서 $A^* = \overline{A^T}$ (conjugate transpose)

즉, $A_{ij} = -\overline{A_{ji}}$

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Zero Diagonal

Antisymmetric matrix의 대각 원소는 **0**:

$$A_{ii} = -A_{ii} \Rightarrow 2A_{ii} = 0 \Rightarrow A_{ii} = 0$$

**일반 형태**:

$$A = \begin{pmatrix} 0 & a_{12} & a_{13} & \cdots \\ -a_{12} & 0 & a_{23} & \cdots \\ -a_{13} & -a_{23} & 0 & \cdots \\ \vdots & \vdots & \vdots & \ddots \end{pmatrix}$$

### 2. Sum and Scalar Multiple

$A, B$ antisymmetric, $c \in \mathbb{R}$:

- $A + B$ antisymmetric: $(A + B)^T = A^T + B^T = -A - B = -(A+B)$ - $cA$ antisymmetric: $(cA)^T = cA^T = -cA$ 
**Vector space**: Antisymmetric matrices form a vector space

**Dimension**: $\dim = \frac{n(n-1)}{2}$

### 3. Product with Transpose

$A$ antisymmetric:

$$A^T A = (-A)A = -A^2$$

$$A A^T = A(-A) = -A^2$$

따라서 $A^T A = A A^T$ (symmetric!)

### 4. Odd Dimension Determinant

**정리**: $n$ odd이고 $A$ antisymmetric $\Rightarrow$ $\det(A) = 0$

**증명**:

$$\det(A) = \det(A^T) = \det(-A) = (-1)^n \det(A)$$

$n$ odd $\Rightarrow$ $(-1)^n = -1$:

$$\det(A) = -\det(A) \Rightarrow 2\det(A) = 0 \Rightarrow \det(A) = 0$$ 
따라서 **not invertible**!

## Spectral Properties

### Theorem: Imaginary Eigenvalues

**정리**: Antisymmetric matrix (over $\mathbb{C}$)는 **purely imaginary eigenvalues**를 가짐

**증명**: $A\mathbf{v} = \lambda \mathbf{v}$ (complex)

$$\mathbf{v}^* A \mathbf{v} = \lambda \|\mathbf{v}\|^2$$

Also:

$$\mathbf{v}^* A \mathbf{v} = (A\mathbf{v})^* \mathbf{v} = (\lambda \mathbf{v})^* \mathbf{v} = \overline{\lambda} \|\mathbf{v}\|^2$$

But $A^* = -A$:

$$\mathbf{v}^* A \mathbf{v} = \mathbf{v}^* A^* \mathbf{v} = (A\mathbf{v})^* \mathbf{v} = \overline{\lambda} \|\mathbf{v}\|^2$$

Wait, more carefully:

$$\mathbf{v}^* A \mathbf{v} = -\mathbf{v}^* A^T \mathbf{v} = -(A\mathbf{v})^T \mathbf{v} = -\overline{\lambda} \overline{\mathbf{v}}^T \mathbf{v} = -\overline{\lambda} \|\mathbf{v}\|^2$$

Actually for real $A$:

$$\lambda \|\mathbf{v}\|^2 = \mathbf{v}^* A \mathbf{v} = \mathbf{v}^* A^T \overline{\mathbf{v}} = -\mathbf{v}^* A \overline{\mathbf{v}} = -\overline{\lambda} \|\mathbf{v}\|^2$$

따라서 $\lambda = -\overline{\lambda}$ $\Rightarrow$ $\lambda$ purely imaginary 
### Eigenvalues Come in Pairs

Real antisymmetric matrix: eigenvalues $\pm i\omega$ ($\omega \in \mathbb{R}$)

Even dimension: Pairs of $\pm i\omega$

Odd dimension: One eigenvalue must be $0$ (since $\det(A) = 0$)

---

# <span class="header-examples">Examples</span>

## Example 1: 2×2 Antisymmetric

$$A = \begin{pmatrix} 0 & a \\ -a & 0 \end{pmatrix}$$

**Eigenvalues**:

$$\det(A - \lambda I) = \lambda^2 + a^2 = 0$$

$$\lambda = \pm ia$$ (purely imaginary! )

**Geometric**: Rotation by $90°$ scaled by $a$

## Example 2: 3×3 Example

$$A = \begin{pmatrix} 0 & 1 & 2 \\ -1 & 0 & 3 \\ -2 & -3 & 0 \end{pmatrix}$$

**Check**: $A^T = -A$ 
**Determinant**: $\det(A) = 0$ (odd dimension!) 
**Eigenvalues**: $0, \pm i\sqrt{14}$

## Example 3: Cross Product Matrix

Vector $\mathbf{a} = (a_1, a_2, a_3)^T$에 대해:

$$A = \begin{pmatrix} 0 & -a_3 & a_2 \\ a_3 & 0 & -a_1 \\ -a_2 & a_1 & 0 \end{pmatrix}$$

**Property**: $A\mathbf{x} = \mathbf{a} \times \mathbf{x}$ (cross product!)

**Antisymmetric**: $A^T = -A$ 
## Example 4: Infinitesimal Rotation

$$\Omega = \begin{pmatrix} 0 & -\omega \\ \omega & 0 \end{pmatrix}$$

**Matrix exponential**:

$$e^{\Omega t} = \begin{pmatrix} \cos(\omega t) & -\sin(\omega t) \\ \sin(\omega t) & \cos(\omega t) \end{pmatrix}$$

Rotation matrix! Antisymmetric $\to$ Rotation

---

# <span class="header-theorem">Theorem</span>

## Exponential of Antisymmetric

**정리**: $A$ antisymmetric (real) $\Rightarrow$ $e^A$ orthogonal

**증명**:

$$(e^A)^T e^A = e^{A^T} e^A = e^{-A} e^A = e^{-A+A} = e^0 = I$$ 
**의미**: Antisymmetric matrices generate rotations!

## Normal Operator

Antisymmetric matrix는 **normal**:

$$A^T A = (-A)A = -A^2$$
$$A A^T = A(-A) = -A^2$$

따라서 $A^T A = A A^T$ 
자세한 내용은 [[Normal Operator]] 참조

## Decomposition

**정리**: 모든 matrix $M$은 symmetric과 antisymmetric의 합:

$$M = \frac{M + M^T}{2} + \frac{M - M^T}{2}$$

where:
- $S = \frac{M + M^T}{2}$ symmetric
- $A = \frac{M - M^T}{2}$ antisymmetric

---

# <span class="header-remark">Remark</span>

## 응용

### 1. Rotations and Angular Velocity

3D rotation의 infinitesimal generator:

$$\frac{d R(t)}{dt}\bigg|_{t=0} = \Omega$$

$\Omega$ antisymmetric!

### 2. Lie Algebras^[리 대수]

$\mathfrak{so}(n) = $ antisymmetric $n \times n$ matrices

Lie algebra of $SO(n)$ (rotation group)

**Lie bracket**: $[A, B] = AB - BA$

### 3. Physics: Angular Momentum

Angular momentum operator $\mathbf{L}$:

$$L_i = \epsilon_{ijk} x_j p_k$$

Matrix representation: antisymmetric!

### 4. Electromagnetism

Electromagnetic field tensor $F_{\mu\nu}$:

$$F_{\mu\nu} = -F_{\nu\mu}$$ (antisymmetric!)

### 5. Cross Product

$3 \times 3$ antisymmetric matrices $\leftrightarrow$ vectors in $\mathbb{R}^3$

Cross product as matrix multiplication

## Symmetric vs Antisymmetric

| Property | Symmetric | Antisymmetric |
|----------|-----------|---------------|
| Definition | $A^T = A$ | $A^T = -A$ |
| Diagonal | Any | Zero |
| Eigenvalues (real) | Real | Pure imaginary |
| Dimension | $\frac{n(n+1)}{2}$ | $\frac{n(n-1)}{2}$ |
| $\det(A)$ (odd $n$) | Any | Zero |
| Exponential | Positive definite | Orthogonal |

## Decomposition

$$M_n(\mathbb{R}) = \text{Sym}_n(\mathbb{R}) \oplus \text{Antisym}_n(\mathbb{R})$$

**Direct sum**: Every matrix = symmetric + antisymmetric

$$\dim = \frac{n(n+1)}{2} + \frac{n(n-1)}{2} = n^2$$ 
## 관련 개념

- [[Symmetric Matrix]]: Opposite sign
- [[Orthogonal Matrix]]: $e^A$ for antisymmetric $A$
- [[Normal Operator]]: Both are normal
- [[Unitary Matrix]]: $e^{iA}$ for Hermitian $A$

