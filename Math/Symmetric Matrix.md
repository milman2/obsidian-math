# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Inner Product]]
- [[Eigen Value, Eigen Vector]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Strang, Introduction to Linear Algebra

---

# <span class="header-definition">Definition</span>

## Symmetric Matrix^[대칭 행렬]

**Real matrix** $A \in M_n(\mathbb{R})$가 **symmetric^[대칭]**이다 $\Leftrightarrow$

$$A^T = A$$

즉, $A_{ij} = A_{ji}$ for all $i, j$

**기하학적 의미**: 주대각선^[main diagonal]에 대해 대칭

## Complex Extension

**Complex matrix** $A \in M_n(\mathbb{C})$:

**Hermitian^[에르미트]** (복소수의 symmetric 일반화):

$$A^* = A$$

여기서 $A^* = \overline{A^T}$ (conjugate transpose^[켤레 전치])

즉, $A_{ij} = \overline{A_{ji}}$

**주의**: Real symmetric matrix는 자동으로 Hermitian

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Real Entries on Diagonal

Symmetric matrix의 대각 원소는 실수:

$$A_{ii} = A_{ii}^T \Rightarrow A_{ii} \in \mathbb{R}$$

Hermitian의 경우도:

$$A_{ii} = \overline{A_{ii}} \Rightarrow A_{ii} \in \mathbb{R}$$

### 2. Sum and Scalar Multiple

$A, B$ symmetric, $c \in \mathbb{R}$:

- $A + B$ symmetric: $(A + B)^T = A^T + B^T = A + B$ ✓
- $cA$ symmetric: $(cA)^T = cA^T = cA$ ✓

**Vector space**: Symmetric matrices form a vector space

**Dimension**: $\dim = \frac{n(n+1)}{2}$

### 3. Product (주의!)

$A, B$ symmetric이어도 $AB$는 일반적으로 symmetric 아님!

$$(AB)^T = B^T A^T = BA \neq AB$$ (일반적으로)

**Symmetric $\Leftrightarrow$ $AB = BA$** (commute)

### 4. Inverse

$A$ symmetric and invertible $\Rightarrow$ $A^{-1}$ symmetric

$$(A^{-1})^T = (A^T)^{-1} = A^{-1}$$ ✓

## Spectral Properties

### Theorem: Real Eigenvalues

**정리**: Symmetric matrix는 **모든 eigenvalue가 실수**

**증명**: $A$ symmetric, $A\mathbf{v} = \lambda \mathbf{v}$ (complex case)

$$\mathbf{v}^* A \mathbf{v} = \mathbf{v}^* (\lambda \mathbf{v}) = \lambda \|\mathbf{v}\|^2$$

Also:

$$\mathbf{v}^* A \mathbf{v} = (A\mathbf{v})^* \mathbf{v} = (\lambda \mathbf{v})^* \mathbf{v} = \overline{\lambda} \|\mathbf{v}\|^2$$

따라서 $\lambda = \overline{\lambda}$ $\Rightarrow$ $\lambda \in \mathbb{R}$ ✓

### Theorem: Orthogonal Eigenvectors

**정리**: 서로 다른 eigenvalue의 eigenvector는 **orthogonal^[직교]**

**증명**: $A\mathbf{v}_1 = \lambda_1 \mathbf{v}_1$, $A\mathbf{v}_2 = \lambda_2 \mathbf{v}_2$, $\lambda_1 \neq \lambda_2$

$$\lambda_1 \langle \mathbf{v}_1, \mathbf{v}_2 \rangle = \langle A\mathbf{v}_1, \mathbf{v}_2 \rangle = \langle \mathbf{v}_1, A\mathbf{v}_2 \rangle = \lambda_2 \langle \mathbf{v}_1, \mathbf{v}_2 \rangle$$

$$(\lambda_1 - \lambda_2)\langle \mathbf{v}_1, \mathbf{v}_2 \rangle = 0$$

$\lambda_1 \neq \lambda_2$ $\Rightarrow$ $\langle \mathbf{v}_1, \mathbf{v}_2 \rangle = 0$ ✓

### Spectral Theorem

**정리** (**Spectral Theorem for Symmetric Matrices**):

$A$ symmetric $\Rightarrow$ $A$는 **orthogonally diagonalizable^[직교 대각화 가능]**

$$A = Q \Lambda Q^T$$

여기서:
- $Q$ orthogonal ($Q^T Q = I$)
- $\Lambda = \text{diag}(\lambda_1, \ldots, \lambda_n)$ (real eigenvalues)
- $Q$의 columns는 orthonormal eigenvectors

**의미**: Symmetric matrix는 **orthonormal basis of eigenvectors**를 가짐!

---

# <span class="header-examples">Examples</span>

## Example 1: Simple Symmetric

$$A = \begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix}$$

**Check**: $A^T = \begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix} = A$ ✓

**Eigenvalues**: 

$$\det(A - \lambda I) = (1-\lambda)^2 - 4 = \lambda^2 - 2\lambda - 3 = 0$$

$$\lambda_1 = 3, \quad \lambda_2 = -1$$ (real! ✓)

**Eigenvectors**:

$$\mathbf{v}_1 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad \mathbf{v}_2 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix}$$

**Orthogonal**: $\mathbf{v}_1 \cdot \mathbf{v}_2 = 0$ ✓

**Diagonalization**:

$$A = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & -1 \end{pmatrix} \frac{1}{\sqrt{2}}\begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$

## Example 2: Diagonal Matrix

$$D = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 3 \end{pmatrix}$$

모든 diagonal matrix는 symmetric ✓

**Eigenvalues**: $2, -1, 3$ (대각 원소)

## Example 3: Identity Matrix

$$I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$$

Symmetric ✓, eigenvalues all $= 1$

## Example 4: Projection Matrix

$$P = \begin{pmatrix} 1/2 & 1/2 \\ 1/2 & 1/2 \end{pmatrix}$$

**Check**: $P^T = P$ ✓

**Property**: $P^2 = P$ (idempotent)

**Eigenvalues**: $1, 0$

---

# <span class="header-definition">Special Types</span>

## Positive Definite^[양정부호]

**정의**: $A$ symmetric이고 

$$\mathbf{x}^T A \mathbf{x} > 0 \quad \forall \mathbf{x} \neq \mathbf{0}$$

**동치 조건**:
- 모든 eigenvalue $> 0$
- 모든 leading principal minors $> 0$
- $A = B^T B$ for some invertible $B$

**예**: $A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$ (eigenvalues: $3, 1 > 0$)

## Positive Semidefinite^[양반정부호]

$$\mathbf{x}^T A \mathbf{x} \geq 0 \quad \forall \mathbf{x}$$

**동치**: 모든 eigenvalue $\geq 0$

## Negative Definite/Semidefinite

Similar with $< 0$ or $\leq 0$

## Indefinite^[부정부호]

양수와 음수 eigenvalue 모두 존재

---

# <span class="header-theorem">Theorem</span>

## Rayleigh Quotient

$$R(A, \mathbf{x}) = \frac{\mathbf{x}^T A \mathbf{x}}{\mathbf{x}^T \mathbf{x}}$$

**정리**: $A$ symmetric with eigenvalues $\lambda_1 \geq \cdots \geq \lambda_n$

$$\lambda_{\min} \leq R(A, \mathbf{x}) \leq \lambda_{\max}$$

**최대/최소**: Eigenvectors에서 달성

## Courant-Fischer Theorem

$$\lambda_k = \min_{\dim(S)=k} \max_{\mathbf{x} \in S, \|\mathbf{x}\|=1} \mathbf{x}^T A \mathbf{x}$$

Eigenvalue의 variational characterization^[변분 특징화]

## Sylvester's Criterion

$A$ symmetric이 positive definite $\Leftrightarrow$ 모든 leading principal minors $> 0$

---

# <span class="header-remark">Remark</span>

## 응용

### 1. Quadratic Forms^[이차 형식]

$$Q(\mathbf{x}) = \mathbf{x}^T A \mathbf{x}$$

Symmetric matrix와 일대일 대응

**Diagonalization**: Principal axes transformation

### 2. Optimization

**Hessian matrix**: $\nabla^2 f$ (이차 도함수)

Symmetric! Critical point 분석에 사용

### 3. Principal Component Analysis (PCA)

Covariance matrix는 symmetric

Eigenvectors = principal components

### 4. Differential Equations

$$\frac{d\mathbf{x}}{dt} = A\mathbf{x}$$

$A$ symmetric $\Rightarrow$ 해가 orthogonal mode로 분해

### 5. Quantum Mechanics

Observable operators = Hermitian matrices

Eigenvalues = measurement outcomes (real!)

## Normal Operator와의 관계

Symmetric matrix는 **normal operator**:

$$A^T A = A \cdot A = A^2 = A \cdot A = A A^T$$ ✓

자세한 내용은 [[Normal Operator]] 참조

## 관련 개념

- [[Diagonal Matrix]]: 특수한 symmetric
- [[Orthogonal Matrix]]: Diagonalization에 사용
- [[Unitary Matrix]]: Complex 일반화
- [[Normal Operator]]: 일반적 framework

