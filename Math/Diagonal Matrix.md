# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Eigen Value, Eigen Vector]]

# <span class="header-reference">Reference</span>
- Strang, Introduction to Linear Algebra
- Axler, Linear Algebra Done Right

---

# <span class="header-definition">Definition</span>

## Diagonal Matrix^[대각 행렬]

**Matrix** $D \in M_n(\mathbb{F})$가 **diagonal^[대각]**이다 $\Leftrightarrow$

$$D_{ij} = 0 \quad \text{for all } i \neq j$$

**표기**:

$$D = \text{diag}(d_1, d_2, \ldots, d_n) = \begin{pmatrix} d_1 & 0 & \cdots & 0 \\ 0 & d_2 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & d_n \end{pmatrix}$$

**의미**: 대각선 이외의 모든 원소가 0

---

# <span class="header-properties">Properties</span>

## Basic Operations

### 1. Addition

$$\text{diag}(a_1, \ldots, a_n) + \text{diag}(b_1, \ldots, b_n) = \text{diag}(a_1 + b_1, \ldots, a_n + b_n)$$

Component-wise!

### 2. Multiplication

$$\text{diag}(a_1, \ldots, a_n) \cdot \text{diag}(b_1, \ldots, b_n) = \text{diag}(a_1 b_1, \ldots, a_n b_n)$$

**Commutative**: Diagonal matrices commute!

$$D_1 D_2 = D_2 D_1$$

### 3. Scalar Multiple

$$c \cdot \text{diag}(d_1, \ldots, d_n) = \text{diag}(cd_1, \ldots, cd_n)$$

### 4. Powers

$$D^k = \text{diag}(d_1^k, \ldots, d_n^k)$$

Very easy to compute!

### 5. Inverse

$D$ invertible $\Leftrightarrow$ all $d_i \neq 0$

$$D^{-1} = \text{diag}(d_1^{-1}, \ldots, d_n^{-1})$$

## Matrix Properties

### 1. Transpose

$$D^T = D$$

모든 diagonal matrix는 **symmetric**!

### 2. Determinant

$$\det(D) = d_1 d_2 \cdots d_n = \prod_{i=1}^n d_i$$

Product of diagonal entries

### 3. Trace

$$\text{tr}(D) = d_1 + d_2 + \cdots + d_n = \sum_{i=1}^n d_i$$

Sum of diagonal entries

### 4. Eigenvalues

**정리**: Diagonal matrix의 eigenvalue는 **대각 원소**

$$D = \text{diag}(d_1, \ldots, d_n)$$

**Eigenvalues**: $\lambda_i = d_i$

**Eigenvectors**: Standard basis $\mathbf{e}_i$

$$D\mathbf{e}_i = d_i \mathbf{e}_i$$

**Diagonalization**: Already diagonal! $D = I D I$

## Geometric Interpretation

Diagonal matrix는 **축 방향 scaling^[축 스케일링]**:

$$D\begin{pmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{pmatrix} = \begin{pmatrix} d_1 x_1 \\ d_2 x_2 \\ \vdots \\ d_n x_n \end{pmatrix}$$

각 좌표축을 독립적으로 scale

---

# <span class="header-examples">Examples</span>

## Example 1: Identity Matrix

$$I = \text{diag}(1, 1, \ldots, 1)$$

Special diagonal matrix

## Example 2: Scalar Matrix

$$cI = \text{diag}(c, c, \ldots, c)$$

All diagonal entries같음: **uniform scaling**

## Example 3: Simple Example

$$D = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 3 \end{pmatrix}$$

**Properties**:
- Eigenvalues: $2, -1, 3$
- $\det(D) = 2 \cdot (-1) \cdot 3 = -6$
- $\text{tr}(D) = 2 + (-1) + 3 = 4$

**Geometric**: Scale by 2 in $x$, flip and scale by 1 in $y$, scale by 3 in $z$

## Example 4: Projection

$$P = \text{diag}(1, 1, 0, 0)$$

Projects onto first two coordinates

## Example 5: Zero Matrix

$$0 = \text{diag}(0, 0, \ldots, 0)$$

Special diagonal matrix (all zeros)

---

# <span class="header-theorem">Theorem</span>

## Diagonalization

**정리**: Matrix $A$가 **diagonalizable^[대각화 가능]** $\Leftrightarrow$

$$A = PDP^{-1}$$

for some invertible $P$ and diagonal $D$

**의미**: 
- $D$의 diagonal entries = eigenvalues of $A$
- $P$의 columns = eigenvectors of $A$

**조건**: $A$가 $n$개의 linearly independent eigenvectors를 가짐

자세한 내용은 [[Eigen Value, Eigen Vector]] 참조

## Simultaneous Diagonalization

**정리**: Matrices $A_1, \ldots, A_k$가 **commute** ($A_i A_j = A_j A_i$)

$\Rightarrow$ 같은 $P$로 동시에 대각화 가능 (if diagonalizable)

$$A_i = P D_i P^{-1}$$

**Proof sketch**: Common eigenvectors존재

## Spectral Theorem (Diagonal Form)

**정리**: $A$ symmetric (or normal)

$\Rightarrow$ Orthogonally diagonalizable:

$$A = Q \Lambda Q^T$$

where $Q$ orthogonal, $\Lambda$ diagonal

자세한 내용은 [[Symmetric Matrix]], [[Normal Operator]] 참조

---

# <span class="header-definition">Special Types</span>

## Positive Diagonal

$$D = \text{diag}(d_1, \ldots, d_n), \quad d_i > 0$$

**Properties**:
- Positive definite
- $D^{1/2} = \text{diag}(\sqrt{d_1}, \ldots, \sqrt{d_n})$ exists

## Unitary Diagonal

$$D = \text{diag}(e^{i\theta_1}, \ldots, e^{i\theta_n})$$

where $|e^{i\theta_j}| = 1$

**Unitary**: $D^* D = I$

## Permutation-like Diagonal

Diagonal entries are $0$ or $1$:

$$D = \text{diag}(1, 0, 1, 0, \ldots)$$

**Projection** onto subset of coordinates

---

# <span class="header-remark">Remark</span>

## 왜 대각 행렬이 중요한가?

### 1. Computational Efficiency

**Powers**: $D^k$ 쉽게 계산

**Exponential**: $e^D = \text{diag}(e^{d_1}, \ldots, e^{d_n})$

**Functions**: $f(D) = \text{diag}(f(d_1), \ldots, f(d_n))$

### 2. Simplifies Problems

복잡한 matrix problem → diagonal form으로 변환 → 쉬운 문제

**예**: $A^k$ 계산
- $A = PDP^{-1}$
- $A^k = PD^kP^{-1}$ (easy!)

### 3. Eigenvalue Analysis

Diagonal form = eigenvalue decomposition

Spectral properties 직접 확인 가능

### 4. Decoupling

Differential equations:

$$\frac{d\mathbf{x}}{dt} = D\mathbf{x}$$

Decouples into $n$ independent equations!

$$\frac{dx_i}{dt} = d_i x_i$$

## Limitations

**Not all matrices are diagonalizable!**

**Example**: $\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$ (nilpotent)

→ Jordan canonical form instead

## Diagonal vs Diagonalizable

| 개념 | 의미 |
|------|------|
| **Diagonal matrix** | Already in diagonal form |
| **Diagonalizable matrix** | Can be transformed to diagonal |

$D$ diagonal $\Rightarrow$ $D$ diagonalizable ✓

(Trivially: $D = IDI$)

## Vector Space Structure

**Diagonal matrices**: Vector subspace of $M_n(\mathbb{F})$

**Dimension**: $n$

**Basis**: $\{E_{11}, E_{22}, \ldots, E_{nn}\}$

where $E_{ii}$ has 1 at $(i,i)$, 0 elsewhere

## 응용

### Linear Algebra

- **Eigenvalue problems**
- **Canonical forms**
- **Similarity transformations**

### Differential Equations

- **Decoupling systems**
- **Normal modes**

### Optimization

- **Quadratic forms**: $\mathbf{x}^T D \mathbf{x}$ simple!
- **Principal component analysis**

### Probability

- **Covariance matrices** (diagonal = independent)
- **Markov chains** (steady state)

### Machine Learning

- **Feature scaling**
- **Regularization**: $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$

## 관련 개념

- [[Eigen Value, Eigen Vector]]: Diagonalization의 기초
- [[Symmetric Matrix]]: Orthogonally diagonalizable
- [[Normal Operator]]: Unitarily diagonalizable
- [[Orthogonal Matrix]]: Used in diagonalization

