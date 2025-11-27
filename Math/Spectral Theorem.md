# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Inner Product]]
- [[Eigen Value, Eigen Vector]]
- [[Normal Operator]]
- [[Symmetric Matrix]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Friedberg, Linear Algebra
- Conway, A Course in Functional Analysis
- Rudin, Functional Analysis

---

# <span class="header-definition">Overview</span>

**Spectral Theorem^[스펙트럼 정리]**는 선형대수학과 함수해석학에서 가장 중요한 정리 중 하나로, 특정 종류의 operator를 **eigenvalue와 eigenvector로 완전히 분해**할 수 있음을 보장한다.

**핵심 아이디어**:

> "좋은 성질을 가진 operator는 orthonormal eigenbasis를 가진다"

**여러 버전**:
1. Symmetric matrices (real)
2. Hermitian operators (complex)
3. Normal operators (general)
4. Compact self-adjoint operators (infinite-dim)
5. Unbounded self-adjoint operators (functional analysis)

---

# <span class="header-theorem">Finite-Dimensional Versions</span>

## Version 1: Real Symmetric Matrices

**정리** (**Spectral Theorem for Symmetric Matrices**):

$A \in M_n(\mathbb{R})$ symmetric (즉, $A^T = A$)

$\Rightarrow$ $\exists$ orthogonal matrix $Q$ and diagonal matrix $\Lambda$ (real entries) such that:

$$A = Q \Lambda Q^T$$

**동등한 명제**:
- $A$는 **orthonormal basis of eigenvectors**를 가짐
- All eigenvalues are **real**
- Different eigenspaces are **orthogonal**

**표기**: $\Lambda = \text{diag}(\lambda_1, \ldots, \lambda_n)$

자세한 내용은 [[Symmetric Matrix]] 참조

## Version 2: Hermitian Matrices

**정리** (**Spectral Theorem for Hermitian Matrices**):

$A \in M_n(\mathbb{C})$ Hermitian (즉, $A^* = A$)

$\Rightarrow$ $\exists$ unitary matrix $U$ and diagonal matrix $\Lambda$ (real entries) such that:

$$A = U \Lambda U^*$$

**핵심**:
- Eigenvalues are **real** (even though $A$ is complex!)
- Eigenvectors form **orthonormal basis**

자세한 내용은 [[Unitary Matrix]] 참조

## Version 3: Normal Operators

**정리** (**Spectral Theorem for Normal Operators**):

$T: V \to V$ normal operator on finite-dimensional complex inner product space (즉, $T^* T = T T^*$)

$\Rightarrow$ $\exists$ orthonormal basis $\{u_1, \ldots, u_n\}$ consisting of eigenvectors of $T$

**Decomposition**:

$$T = U \Lambda U^*$$

where $U$ unitary, $\Lambda$ diagonal (complex eigenvalues)

**동등한 명제**:
- **(a)** $T$ is normal
- **(b)** $V$ has orthonormal basis of eigenvectors of $T$
- **(c)** $T$ is unitarily diagonalizable
- **(d)** Different eigenspaces are orthogonal

자세한 내용은 [[Normal Operator]] 참조

## Spectral Decomposition Form

$$T = \sum_{i=1}^{n} \lambda_i P_i$$

여기서:
- $\lambda_i$ = distinct eigenvalues
- $P_i$ = orthogonal projection onto eigenspace $E_{\lambda_i}$

**성질**:
- $P_i P_j = 0$ for $i \neq j$ (orthogonal)
- $\sum P_i = I$ (complete)
- $P_i^2 = P_i$ (projection)
- $P_i^* = P_i$ (self-adjoint)

**의미**: Operator를 orthogonal projections의 가중합으로 분해

---

# <span class="header-theorem">Infinite-Dimensional Versions</span>

## Compact Self-Adjoint Operators

**정리** (**Spectral Theorem for Compact Self-Adjoint Operators**):

$H$ Hilbert space, $T: H \to H$ compact^[콤팩트] self-adjoint operator

$\Rightarrow$ $\exists$ orthonormal basis $\{e_n\}$ of eigenvectors and real eigenvalues $\{\lambda_n\}$ such that:

$$T(x) = \sum_{n=1}^{\infty} \lambda_n \langle x, e_n \rangle e_n$$

**추가 성질**:
- $\lambda_n \to 0$ as $n \to \infty$ (only accumulation point is 0)
- Only finitely many eigenvalues $> \epsilon$ for any $\epsilon > 0$

**예**: Integral operators with continuous kernel

## Bounded Self-Adjoint Operators

**정리** (**Spectral Theorem for Bounded Self-Adjoint Operators**):

$H$ Hilbert space, $T: H \to H$ bounded self-adjoint

$\Rightarrow$ $\exists$ unique spectral measure^[스펙트럼 측도] $E$ such that:

$$T = \int_{\sigma(T)} \lambda \, dE(\lambda)$$

여기서 $\sigma(T) \subseteq \mathbb{R}$ is the spectrum^[스펙트럼]

**의미**: Continuous generalization of $T = \sum \lambda_i P_i$

## Unbounded Self-Adjoint Operators

**정리** (**Spectral Theorem for Unbounded Self-Adjoint**):

$A$ unbounded self-adjoint operator on Hilbert space $H$

$\Rightarrow$ $\exists$ spectral measure $E$ such that:

$$A = \int_{\mathbb{R}} \lambda \, dE(\lambda)$$

**주의**: Domain issues! $\text{dom}(A) \neq H$ in general

**예**: 
- Momentum operator: $\hat{p} = -i\hbar \frac{d}{dx}$
- Position operator: $\hat{x}$

**응용**: Quantum mechanics (observables)

---

# <span class="header-proof">Proof Outline (Finite-Dimensional)</span>

## Proof of Spectral Theorem for Normal Operators

**Statement**: $T$ normal on finite-dimensional complex inner product space $V$

$\Rightarrow$ $V$ has orthonormal basis of eigenvectors

### Step 1: Existence of Eigenvalue

**Fundamental Theorem of Algebra**: Every linear operator on complex vector space has eigenvalue

$\exists \lambda \in \mathbb{C}, v \in V$ such that $T(v) = \lambda v$

### Step 2: Key Lemma

**Lemma**: $T$ normal, $T(v) = \lambda v$

$\Rightarrow$ $T^*(v) = \overline{\lambda} v$

**증명**:

$$(T - \lambda I)^* = T^* - \overline{\lambda} I$$

$T$ normal $\Rightarrow$ $T - \lambda I$ normal (scalar shift preserves normality)

$$\|(T - \lambda I)(v)\| = \|(T - \lambda I)^*(v)\|$$

$$0 = \|T^*(v) - \overline{\lambda} v\|$$

따라서 $T^*(v) = \overline{\lambda} v$ ✓

### Step 3: Invariant Subspace

Eigenspace $E_\lambda = \ker(T - \lambda I)$

Orthogonal complement $E_\lambda^\perp$

**핵심**: $T$ leaves $E_\lambda^\perp$ invariant!

**증명**: $w \in E_\lambda^\perp$, $v \in E_\lambda$

$$\langle T(w), v \rangle = \langle w, T^*(v) \rangle = \langle w, \overline{\lambda} v \rangle = \overline{\lambda} \langle w, v \rangle = 0$$

따라서 $T(w) \in E_\lambda^\perp$ ✓

### Step 4: Induction

- **Base**: $\dim(V) = 1$ → trivial
- **Induction**: $T|_{E_\lambda^\perp}$ is also normal on $E_\lambda^\perp$
- By induction hypothesis, $E_\lambda^\perp$ has orthonormal eigenbasis
- Combine with orthonormal basis of $E_\lambda$

$$V = E_\lambda \oplus E_\lambda^\perp$$ ✓

### Step 5: Conclusion

By induction, orthonormal eigenbasis exists for all of $V$ ✓

---

# <span class="header-examples">Examples</span>

## Example 1: $2 \times 2$ Symmetric

$$A = \begin{pmatrix} 3 & 1 \\ 1 & 3 \end{pmatrix}$$

**Eigenvalues**: 

$$\det(A - \lambda I) = (3-\lambda)^2 - 1 = 0$$

$$\lambda_1 = 4, \quad \lambda_2 = 2$$

**Eigenvectors**:

$$\mathbf{v}_1 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad \mathbf{v}_2 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -1 \end{pmatrix}$$

**Spectral decomposition**:

$$A = 4 P_1 + 2 P_2$$

where:

$$P_1 = \frac{1}{2}\begin{pmatrix} 1 & 1 \\ 1 & 1 \end{pmatrix}, \quad P_2 = \frac{1}{2}\begin{pmatrix} 1 & -1 \\ -1 & 1 \end{pmatrix}$$

**Verification**: $P_1 + P_2 = I$, $P_1 P_2 = 0$ ✓

## Example 2: Rotation Matrix

$$R_\theta = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$

**Complex eigenvalues**: $\lambda = e^{\pm i\theta}$

**Complex eigenvectors**:

$$\mathbf{v}_1 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ i \end{pmatrix}, \quad \mathbf{v}_2 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ -i \end{pmatrix}$$

**Normal**: $R^T R = I = R R^T$ (orthogonal, hence normal) ✓

## Example 3: Diagonal Matrix

$$D = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 3 \end{pmatrix}$$

Already in spectral form!

$$D = 2 P_1 + (-1) P_2 + 3 P_3$$

where $P_i = \mathbf{e}_i \mathbf{e}_i^T$ (projections onto coordinate axes)

자세한 내용은 [[Diagonal Matrix]] 참조

## Example 4: Infinite-Dimensional

**Fourier Transform** on $L^2(\mathbb{R})$:

$$(\mathcal{F}f)(\omega) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^{\infty} f(x) e^{-i\omega x} dx$$

**Unitary**: $\mathcal{F}^* \mathcal{F} = I$

**Eigenvalues**: $\pm 1, \pm i$

**Spectral decomposition**: Projection onto eigenspaces

---

# <span class="header-properties">Properties and Consequences</span>

## Functional Calculus

Spectral theorem을 이용하면 **operator의 함수**를 정의할 수 있음:

$$f(T) = U f(\Lambda) U^*$$

where $f(\Lambda) = \text{diag}(f(\lambda_1), \ldots, f(\lambda_n))$

**예시**:
- **Square root**: $\sqrt{T} = U \sqrt{\Lambda} U^*$ (for positive definite $T$)
- **Exponential**: $e^T = U e^\Lambda U^*$
- **Logarithm**: $\log T = U \log \Lambda U^*$
- **Trigonometric**: $\sin T$, $\cos T$

**조건**: $T$ must be **normal** (or self-adjoint)!

## Spectral Radius

$$\rho(T) = \max_{i} |\lambda_i|$$

**정리**: $T$ normal

$$\|T\| = \rho(T)$$

Operator norm = spectral radius

## Positive Operators

$T$ self-adjoint이고 모든 eigenvalue $\geq 0$

$$T = U \Lambda U^* \text{ where } \Lambda = \text{diag}(\lambda_1, \ldots, \lambda_n), \; \lambda_i \geq 0$$

**Square root exists**:

$$T^{1/2} = U \Lambda^{1/2} U^*$$

## Spectral Projections

Eigenvalue $\lambda_i$의 multiplicity가 $m_i$일 때:

$$P_i = \text{orthogonal projection onto } E_{\lambda_i}$$

**Properties**:
1. $P_i^2 = P_i$ (idempotent^[멱등])
2. $P_i^* = P_i$ (self-adjoint)
3. $P_i P_j = 0$ for $i \neq j$ (orthogonal)
4. $\sum_{i} P_i = I$ (complete)

**Spectral decomposition**:

$$T = \sum_{i=1}^{k} \lambda_i P_i$$

---

# <span class="header-examples">Applications</span>

## 1. Principal Component Analysis (PCA)

**Setup**: Data matrix $X$, covariance matrix $C = X^T X$

$C$ symmetric $\Rightarrow$ Spectral theorem:

$$C = Q \Lambda Q^T$$

**Principal components**: Columns of $Q$ (eigenvectors)

**Variance explained**: Eigenvalues $\lambda_i$

**Dimensionality reduction**: Keep top $k$ eigenvalues

## 2. Solving Differential Equations

$$\frac{d\mathbf{x}}{dt} = A\mathbf{x}$$

$A$ symmetric $\Rightarrow$ $A = Q \Lambda Q^T$

**Solution**:

$$\mathbf{x}(t) = Q e^{\Lambda t} Q^T \mathbf{x}(0)$$

where $e^{\Lambda t} = \text{diag}(e^{\lambda_1 t}, \ldots, e^{\lambda_n t})$

**Normal modes**: Eigenvectors decouple the system

## 3. Quadratic Forms

$$Q(\mathbf{x}) = \mathbf{x}^T A \mathbf{x}$$

$A$ symmetric $\Rightarrow$ $A = Q \Lambda Q^T$

Change of variables $\mathbf{y} = Q^T \mathbf{x}$:

$$Q(\mathbf{x}) = \mathbf{y}^T \Lambda \mathbf{y} = \sum_{i=1}^{n} \lambda_i y_i^2$$

**Principal axes**: Eigenvectors of $A$

## 4. Optimization

**Rayleigh quotient**:

$$R(\mathbf{x}) = \frac{\mathbf{x}^T A \mathbf{x}}{\mathbf{x}^T \mathbf{x}}$$

$A$ symmetric:

$$\lambda_{\min} \leq R(\mathbf{x}) \leq \lambda_{\max}$$

**Achieved at eigenvectors**!

## 5. Quantum Mechanics

**Observable** $A$ (Hermitian)

$$A = \sum_{i} \lambda_i P_i$$

**Measurement**:
- Eigenvalues $\lambda_i$ = possible outcomes
- $P_i$ = probability projection
- Eigenvectors = measurement basis

**Born rule**: $P(\lambda_i) = \|P_i \psi\|^2$

## 6. Matrix Functions

**Matrix exponential**:

$$e^{At} = Q e^{\Lambda t} Q^T$$

**Matrix square root** (positive definite):

$$\sqrt{A} = Q \sqrt{\Lambda} Q^T$$

**Only possible via spectral theorem**!

## 7. Singular Value Decomposition (SVD)

**Connection**: SVD uses spectral theorem

$$A = U \Sigma V^*$$

where $U, V$ unitary

**Derivation**:
- $A^* A$ is Hermitian → Spectral theorem
- $A A^*$ is Hermitian → Spectral theorem
- Singular values = $\sqrt{\text{eigenvalues of } A^* A}$

---

# <span class="header-remark">Remark</span>

## 왜 Normal이어야 하나?

**핵심**: Normality $\Leftrightarrow$ Unitary diagonalizability

**반례** (Not normal):

$$A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$$

**Not diagonalizable**! Jordan form:

$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$$

**Eigenvectors not orthogonal**

## 직관적 이해

**Spectral Theorem**: "좋은" operator는 "좋은" basis를 가짐

**"좋은" operator**:
- Normal (commutes with adjoint)
- Structure is "well-behaved"

**"좋은" basis**:
- Orthonormal
- Eigenvectors
- Diagonalizes the operator

**기하학적**: Operator = rotation/scaling along orthogonal axes

## Real vs Complex

### Real Spectral Theorem

**조건**: Self-adjoint (stronger than normal)

**결과**: Real eigenvalues, real eigenvectors

### Complex Spectral Theorem

**조건**: Normal (weaker)

**결과**: Complex eigenvalues possible, complex eigenvectors

**예**: Rotation in $\mathbb{R}^2$ 
- Not diagonalizable over $\mathbb{R}$
- But diagonalizable over $\mathbb{C}$ ✓

## 역사적 배경

**David Hilbert** (1862-1943):
- Spectral theory in integral equations
- Hilbert space theory

**John von Neumann** (1903-1957):
- Unbounded operators
- Quantum mechanics foundations

**Hermann Weyl** (1885-1955):
- Spectral theory for differential operators

**Marshall Stone** (1903-1989):
- Stone-Weierstrass theorem
- Spectral theorem generalization

## Versions Summary

| Version | Operator Type | Space | Eigenvalues | Diagonalization |
|---------|--------------|-------|-------------|----------------|
| Real | Symmetric | $\mathbb{R}^n$ | Real | Orthogonal |
| Complex | Hermitian | $\mathbb{C}^n$ | Real | Unitary |
| General | Normal | $\mathbb{C}^n$ | Complex | Unitary |
| Compact | Compact self-adjoint | Hilbert | Real | Series |
| Bounded | Bounded self-adjoint | Hilbert | Real | Integral |
| Unbounded | Self-adjoint | Hilbert | Real | Integral |

## Proof Techniques

다른 접근들:

1. **Schur triangularization** → Normal → Diagonal
2. **Induction on dimension** (위 증명)
3. **Functional analysis**: Gelfand representation
4. **Variational principle**: Rayleigh quotient
5. **Category theory**: Universal property

## Common Patterns

### Pattern 1: Diagonalization

Problem: Compute $A^k$, $e^{At}$, etc.

Solution: $A = Q \Lambda Q^T$ → $A^k = Q \Lambda^k Q^T$

### Pattern 2: Change of Basis

Problem: Simplify quadratic form

Solution: Spectral theorem → principal axes

### Pattern 3: Functional Calculus

Problem: Define $f(A)$ for matrix $A$

Solution: $f(A) = Q f(\Lambda) Q^T$

## Limitations

**Spectral theorem does NOT apply to**:

1. **Non-normal matrices**
   - Jordan canonical form instead
   - Generalized eigenvectors

2. **Non-self-adjoint operators** (over $\mathbb{R}$)
   - Need complexification

3. **General unbounded operators**
   - Domain issues
   - Spectral measure may not exist

## Extensions and Generalizations

**Advanced topics**:
- **Spectral theorem for normal operators on Banach spaces** (Gelfand)
- **Spectral theorem for commutative $C^*$-algebras**
- **Borel functional calculus**
- **Spectral theorem for unitary representations**

## 관련 개념

- [[Normal Operator]]: General framework
- [[Symmetric Matrix]]: Real version
- [[Unitary Matrix]]: Diagonalization matrix
- [[Orthogonal Matrix]]: Real diagonalization
- [[Diagonal Matrix]]: Target form
- [[Eigen Value, Eigen Vector]]: Building blocks
- [[Hilbert Space]]: Infinite-dimensional setting

