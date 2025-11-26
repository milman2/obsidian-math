# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Vector Space]]
- [[Matrix]]
- [[Determinant]]
- [[Polynomial]]
- [[Inner Product]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Hoffman & Kunze, Linear Algebra
- Strang, Linear Algebra and Its Applications
- Horn & Johnson, Matrix Analysis

---

# <span class="header-definition">Definition</span>

## Eigenvalue and Eigenvector

### Linear Operator Perspective

$V$를 field $\mathbb{F}$ 위의 vector space^[벡터 공간], $T: V \to V$를 linear operator^[선형 작용소]라고 하자.

**Eigenvector**^[고유벡터]:

벡터 $v \in V$, $v \neq 0$이 다음을 만족하면 $v$를 $T$의 **eigenvector**라고 함:

$$T(v) = \lambda v$$

for some scalar $\lambda \in \mathbb{F}$

**Eigenvalue**^[고유값]:

위 식을 만족하는 scalar $\lambda$를 $v$에 대응하는 **eigenvalue**라고 함

**핵심**:
- $T(v)$가 $v$와 **같은 방향**
- $\lambda$는 **스케일 인수**^[배율]
- $v \neq 0$ 조건 필수!

### Matrix Perspective

$A$를 $n \times n$ matrix라고 하자.

**Eigenvector**: 

$$Av = \lambda v, \quad v \neq 0$$

**Eigenvalue**: 

위 식을 만족하는 $\lambda$

**Equivalent Form**:

$$(A - \lambda I)v = 0$$

$v \neq 0$이 존재 $\Leftrightarrow$ $A - \lambda I$ is singular $\Leftrightarrow$ $\det(A - \lambda I) = 0$

## Characteristic Polynomial

**정의**: $A$의 **characteristic polynomial**^[특성 다항식]:

$$p_A(\lambda) = \det(A - \lambda I)$$

**Characteristic equation**^[특성 방정식]:

$$\det(A - \lambda I) = 0$$

**Properties**:
- Degree $n$ polynomial in $\lambda$
- $\lambda$는 eigenvalue $\Leftrightarrow$ $p_A(\lambda) = 0$
- Eigenvalues = roots of characteristic polynomial

**Alternative form**:

$$p_A(\lambda) = \det(\lambda I - A) = (-1)^n \det(A - \lambda I)$$

(부호 차이만 있음, roots는 동일)

## Eigenspace

**정의**: Eigenvalue $\lambda$에 대한 **eigenspace**^[고유 공간]:

$$E_\lambda = \ker(T - \lambda I) = \{v \in V : T(v) = \lambda v\}$$

또는 matrix의 경우:

$$E_\lambda = \{v \in \mathbb{F}^n : Av = \lambda v\} = \text{null}(A - \lambda I)$$

**Properties**:
- $E_\lambda$는 $V$의 subspace
- $0 \in E_\lambda$ (항상)
- Eigenvectors for $\lambda$ = nonzero vectors in $E_\lambda$
- $\dim(E_\lambda) \geq 1$ (if $\lambda$ is eigenvalue)

## Multiplicity

### Algebraic Multiplicity

**정의**: Eigenvalue $\lambda$의 **algebraic multiplicity**^[대수적 중복도]:

Characteristic polynomial에서 $(\lambda - \lambda_0)$의 지수

$$p_A(\lambda) = (\lambda - \lambda_1)^{m_1} \cdots (\lambda - \lambda_k)^{m_k} \cdot q(\lambda)$$

where $q(\lambda_i) \neq 0$

$\lambda_i$의 algebraic multiplicity = $m_i$

**표기**: $\text{alg-mult}(\lambda)$ 또는 $m_a(\lambda)$

### Geometric Multiplicity

**정의**: Eigenvalue $\lambda$의 **geometric multiplicity**^[기하적 중복도]:

$$\dim(E_\lambda) = \dim(\ker(A - \lambda I))$$

**표기**: $\text{geom-mult}(\lambda)$ 또는 $m_g(\lambda)$

**Interpretation**:
- Maximum number of linearly independent eigenvectors for $\lambda$

### Relationship

**정리**: 모든 eigenvalue $\lambda$에 대해

$$1 \leq m_g(\lambda) \leq m_a(\lambda)$$

**증명 아이디어**:
- $m_g(\lambda) \geq 1$: $\lambda$가 eigenvalue이므로 eigenvector 존재
- $m_g(\lambda) \leq m_a(\lambda)$: Linear algebra theorem

## Spectrum

**정의**: Operator $T$ (또는 matrix $A$)의 **spectrum**^[스펙트럼]:

$$\sigma(T) = \{\lambda \in \mathbb{F} : \lambda \text{ is eigenvalue of } T\}$$

**표기**: $\text{spec}(T)$ 또는 $\sigma(T)$

**Properties**:
- $|\sigma(A)| \leq n$ (for $n \times n$ matrix)
- Over $\mathbb{C}$: $|\sigma(A)| \geq 1$ (Fundamental Theorem of Algebra)
- Over $\mathbb{R}$: $|\sigma(A)|$ can be 0 (예: rotation)

## Spectral Radius

**정의**: **Spectral radius**^[스펙트럼 반지름]:

$$\rho(A) = \max\{|\lambda| : \lambda \in \sigma(A)\}$$

**Interpretation**: "크기가 가장 큰" eigenvalue의 절댓값

**중요성**: Convergence, stability analysis

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Zero is NOT Eigenvector

**정의**: $v = 0$은 eigenvector가 **아님**

**이유**: $T(0) = 0 = \lambda \cdot 0$ for **all** $\lambda$

Eigenvalue가 well-defined되지 않음!

### 2. Eigenvalue Can Be Zero

$\lambda = 0$은 eigenvalue가 될 수 있음!

$$T(v) = 0 \cdot v = 0$$

**의미**: $v \in \ker(T)$

**정리**: $\lambda = 0$이 eigenvalue $\Leftrightarrow$ $T$ is singular $\Leftrightarrow$ $\det(A) = 0$

### 3. Linearity of Eigenspace

$E_\lambda = \ker(T - \lambda I)$는 subspace

**증명**:
- $T(v_1) = \lambda v_1$, $T(v_2) = \lambda v_2$이면
- $T(av_1 + bv_2) = aT(v_1) + bT(v_2) = a\lambda v_1 + b\lambda v_2 = \lambda(av_1 + bv_2)$ ✓

### 4. Linear Independence

**정리**: 서로 다른 eigenvalues에 대응하는 eigenvectors는 **linearly independent**

**증명** (Induction):
- $v_1, \ldots, v_k$가 eigenvalues $\lambda_1, \ldots, \lambda_k$에 대응 ($\lambda_i \neq \lambda_j$)
- Suppose $c_1 v_1 + \cdots + c_k v_k = 0$
- Apply $T$ and manipulate to get $c_i = 0$ ✓

**계**: 서로 다른 $n$개의 eigenvalues $\Rightarrow$ $n$개의 linearly independent eigenvectors

### 5. Dimension Bound

**정리**: $n \times n$ matrix는 최대 $n$개의 distinct eigenvalues

**이유**: Characteristic polynomial has degree $n$

### 6. Sum and Product

**정리**: $A$가 $n \times n$ matrix, eigenvalues $\lambda_1, \ldots, \lambda_n$ (with multiplicity)이면

**(a)** $\displaystyle\sum_{i=1}^{n} \lambda_i = \text{tr}(A)$ (trace)

**(b)** $\displaystyle\prod_{i=1}^{n} \lambda_i = \det(A)$

**증명**:

Characteristic polynomial:

$$p_A(\lambda) = \det(\lambda I - A) = \lambda^n - (\text{tr}(A))\lambda^{n-1} + \cdots + (-1)^n \det(A)$$

Vieta's formulas ✓

### 7. Invariant Under Similarity

**정리**: $A \sim B$ (similar matrices) $\Rightarrow$ same eigenvalues

**증명**: $B = P^{-1}AP$이면

$$\det(B - \lambda I) = \det(P^{-1}(A - \lambda I)P) = \det(A - \lambda I)$$ ✓

**주의**: Eigenvectors는 다름! ($v_B = P^{-1}v_A$)

## Diagonalization

### Diagonalizable

**정의**: Matrix $A$가 **diagonalizable**^[대각화 가능]하다:

$$\exists \text{ invertible } P: \quad P^{-1}AP = D$$

where $D$ is diagonal

**Equivalent conditions**:

**(a)** $A$ has $n$ linearly independent eigenvectors

**(b)** $\displaystyle\sum_{\lambda \in \sigma(A)} m_g(\lambda) = n$

**(c)** For all $\lambda$: $m_g(\lambda) = m_a(\lambda)$

### Diagonalization Theorem

**정리**: $A$가 diagonalizable $\Leftrightarrow$ $V$가 eigenvectors의 basis를 가짐

**구성**:
- $P = [v_1 \mid v_2 \mid \cdots \mid v_n]$ (eigenvectors)
- $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$ (eigenvalues)

$$AP = PD \quad \Leftrightarrow \quad A = PDP^{-1}$$

**계산**:

$$A^k = PD^kP^{-1}$$

where $D^k = \text{diag}(\lambda_1^k, \ldots, \lambda_n^k)$ (easy!)

### Sufficient Condition

**정리**: $A$가 $n$개의 **distinct** eigenvalues를 가지면 diagonalizable

**증명**: Distinct eigenvalues $\Rightarrow$ $n$ linearly independent eigenvectors ✓

**주의**: Converse는 false! 
- 예: $I$ has eigenvalue 1 with multiplicity $n$, but diagonalizable

### Non-Diagonalizable Example

**Example**: 

$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$

- Eigenvalue: $\lambda = 1$ (multiplicity 2)
- Eigenvector: Only $(1, 0)^T$ (up to scalar)
- $m_a(1) = 2$, $m_g(1) = 1$
- $m_g \neq m_a$ $\Rightarrow$ NOT diagonalizable ✗

## Powers and Functions of Matrices

### Powers

If $A = PDP^{-1}$:

$$A^k = PD^kP^{-1} = P \begin{pmatrix} \lambda_1^k & & \\ & \ddots & \\ & & \lambda_n^k \end{pmatrix} P^{-1}$$

**Application**: Solving $x_{k+1} = Ax_k$

$$x_k = A^k x_0 = PD^k P^{-1} x_0$$

### Matrix Functions

**정의**: If $f(\lambda) = \sum a_k \lambda^k$:

$$f(A) = \sum a_k A^k = P f(D) P^{-1} = P \begin{pmatrix} f(\lambda_1) & & \\ & \ddots & \\ & & f(\lambda_n) \end{pmatrix} P^{-1}$$

**Examples**:
- $e^{At} = Pe^{Dt}P^{-1} = P \text{diag}(e^{\lambda_1 t}, \ldots, e^{\lambda_n t})P^{-1}$
- $\sin(A)$, $\cos(A)$, $\sqrt{A}$, etc.

## Cayley-Hamilton Theorem

**정리**: 모든 square matrix $A$는 자신의 characteristic polynomial을 만족

$$p_A(A) = 0$$

**예**: 

$$A = \begin{pmatrix} 1 & 2 \\ 3 & 4 \end{pmatrix}, \quad p_A(\lambda) = \lambda^2 - 5\lambda - 2$$

Then:

$$A^2 - 5A - 2I = 0$$

**Applications**:
- Computing $A^{-1}$: If $p_A(\lambda) = \lambda^n + \cdots + a_0$, then $A^{-1} = -\frac{1}{a_0}(A^{n-1} + \cdots)$
- Minimal polynomial
- Jordan normal form

자세한 내용은 [[Cayley-Hamilton Theorem]] 참조

## Trace and Determinant

**Trace**^[대각합]:

$$\text{tr}(A) = \sum_{i=1}^{n} a_{ii} = \sum_{i=1}^{n} \lambda_i$$

**Determinant**^[행렬식]:

$$\det(A) = \prod_{i=1}^{n} \lambda_i$$

**Applications**:
- Quick eigenvalue check
- $\det(A) = 0 \Leftrightarrow$ $\lambda = 0$ is eigenvalue
- $\text{tr}(A) = 0 \Leftrightarrow$ $\sum \lambda_i = 0$

---

# <span class="header-examples">Examples</span>

## Example 1: 2×2 Matrix

**Problem**: Find eigenvalues and eigenvectors of

$$A = \begin{pmatrix} 3 & 1 \\ 0 & 2 \end{pmatrix}$$

**Solution**:

**Characteristic polynomial**:

$$\det(A - \lambda I) = \det\begin{pmatrix} 3-\lambda & 1 \\ 0 & 2-\lambda \end{pmatrix} = (3-\lambda)(2-\lambda) = 0$$

**Eigenvalues**: $\lambda_1 = 3$, $\lambda_2 = 2$

**Eigenvector for $\lambda_1 = 3$**:

$$(A - 3I)v = \begin{pmatrix} 0 & 1 \\ 0 & -1 \end{pmatrix} \begin{pmatrix} v_1 \\ v_2 \end{pmatrix} = 0$$

$\Rightarrow v_2 = 0$, $v_1$ free

$$v_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$

**Eigenvector for $\lambda_2 = 2$**:

$$(A - 2I)v = \begin{pmatrix} 1 & 1 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} v_1 \\ v_2 \end{pmatrix} = 0$$

$\Rightarrow v_1 + v_2 = 0$

$$v_2 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}$$

**검증**:

$$A\begin{pmatrix} 1 \\ 0 \end{pmatrix} = \begin{pmatrix} 3 \\ 0 \end{pmatrix} = 3\begin{pmatrix} 1 \\ 0 \end{pmatrix}$$ ✓

$$A\begin{pmatrix} 1 \\ -1 \end{pmatrix} = \begin{pmatrix} 2 \\ -2 \end{pmatrix} = 2\begin{pmatrix} 1 \\ -1 \end{pmatrix}$$ ✓

## Example 2: Diagonal Matrix

$$D = \begin{pmatrix} 2 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & 5 \end{pmatrix}$$

**Eigenvalues**: $\lambda_1 = 2$, $\lambda_2 = -1$, $\lambda_3 = 5$ (diagonal entries!)

**Eigenvectors**: Standard basis vectors

$$v_1 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}, \quad v_2 = \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}, \quad v_3 = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$$

**Rule**: Diagonal matrix의 eigenvalues = diagonal entries ✓

## Example 3: Identity Matrix

$$I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$$

**Eigenvalue**: $\lambda = 1$ (multiplicity 2)

**Eigenvectors**: **모든** nonzero vector!

$$I v = v = 1 \cdot v$$ for all $v$

**Eigenspace**: $E_1 = \mathbb{R}^2$

## Example 4: Rotation Matrix

$$R = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$

**Characteristic polynomial**:

$$\det(R - \lambda I) = \lambda^2 - 2\cos\theta \cdot \lambda + 1$$

**Discriminant**: $\Delta = 4\cos^2\theta - 4 = -4\sin^2\theta$

**Case 1** ($\theta \neq 0, \pi$): $\Delta < 0$

No real eigenvalues! (rotation has no invariant directions)

**Case 2** ($\theta = 0$): $R = I$, $\lambda = 1$ (multiplicity 2)

**Case 3** ($\theta = \pi$): $R = -I$, $\lambda = -1$ (multiplicity 2)

**Over $\mathbb{C}$**: 

$$\lambda = \cos\theta \pm i\sin\theta = e^{\pm i\theta}$$

Complex eigenvalues!

## Example 5: Symmetric Matrix

$$A = \begin{pmatrix} 2 & 1 \\ 1 & 2 \end{pmatrix}$$

**Characteristic polynomial**:

$$\det(A - \lambda I) = (2-\lambda)^2 - 1 = \lambda^2 - 4\lambda + 3 = (\lambda - 3)(\lambda - 1)$$

**Eigenvalues**: $\lambda_1 = 3$, $\lambda_2 = 1$ (real!)

**Eigenvectors**:

For $\lambda_1 = 3$:

$$v_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$

For $\lambda_2 = 1$:

$$v_2 = \begin{pmatrix} 1 \\ -1 \end{pmatrix}$$

**관찰**: $v_1 \perp v_2$ (orthogonal!)

**일반**: Symmetric matrices have real eigenvalues and orthogonal eigenvectors ✓

## Example 6: Projection Matrix

$$P = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$$

Projection onto $x$-axis

**Eigenvalues**: $\lambda_1 = 1$, $\lambda_2 = 0$

**Eigenvectors**:

For $\lambda_1 = 1$:

$$v_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$ (on projection)

For $\lambda_2 = 0$:

$$v_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$$ (orthogonal to projection)

**일반**: Projection has eigenvalues 0 and 1 only

## Example 7: Nilpotent Matrix

$$N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$$

$N^2 = 0$ (nilpotent!)

**Eigenvalue**: $\lambda = 0$ (only, multiplicity 2)

**Eigenvector**: 

$$v = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$

Only one eigenvector! $m_a(0) = 2$, $m_g(0) = 1$

**결론**: NOT diagonalizable ✗

## Example 8: 3×3 with Repeated Eigenvalue

$$A = \begin{pmatrix} 2 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 3 \end{pmatrix}$$

**Eigenvalues**: $\lambda_1 = 2$ (multiplicity 2), $\lambda_2 = 3$

**Eigenspace for $\lambda = 2$**:

$$(A - 2I)v = \begin{pmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}v = 0$$

$$E_2 = \text{span}\left\{\begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 1 \\ 0 \end{pmatrix}\right\}$$

$\dim(E_2) = 2 = m_a(2)$ ✓

**결론**: Diagonalizable! (이미 diagonal이지만)

## Example 9: Shear Matrix

$$S = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$

**Eigenvalue**: $\lambda = 1$ (multiplicity 2)

**Eigenvector**: Only $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$

$m_a(1) = 2$, $m_g(1) = 1$

**결론**: NOT diagonalizable ✗

**Jordan form**:

$$S = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$ (already in Jordan form!)

## Example 10: Markov Matrix

$$M = \begin{pmatrix} 0.7 & 0.3 \\ 0.3 & 0.7 \end{pmatrix}$$

Stochastic matrix (columns sum to 1)

**Eigenvalues**: $\lambda_1 = 1$, $\lambda_2 = 0.4$

**Eigenvector for $\lambda = 1$**:

$$v_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$ (steady state!)

**Long-term behavior**:

$$M^k \to \begin{pmatrix} 0.5 & 0.5 \\ 0.5 & 0.5 \end{pmatrix}$$ as $k \to \infty$

**Application**: PageRank algorithm

## Example 11: Over $\mathbb{F}_2$

$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \text{ over } \mathbb{F}_2$$

**Characteristic polynomial**:

$$\det(A - \lambda I) = (1 + \lambda)^2 = \lambda^2 + 1$$ (in $\mathbb{F}_2$: $1 + 1 = 0$)

**Eigenvalue**: $\lambda = 1$ (since $1 + 1 = 0$ in $\mathbb{F}_2$)

**Note**: Different from real case!

## Example 12: Geometric Transformation

**Scaling**: 

$$S = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}$$

Eigenvalues: 2, 3 (scale factors in each direction)

**Reflection** (across $y = x$):

$$R = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$

Eigenvalues: 1, -1

Eigenvectors: $\begin{pmatrix} 1 \\ 1 \end{pmatrix}$ (on line), $\begin{pmatrix} 1 \\ -1 \end{pmatrix}$ (perpendicular)

---

# <span class="header-theorem">Theorem</span>

## Spectral Theorem (Real Symmetric)

**정리**: $A$가 real **symmetric** matrix이면

**(a)** 모든 eigenvalues는 **real**

**(b)** 서로 다른 eigenvalues에 대응하는 eigenvectors는 **orthogonal**

**(c)** $A$는 **orthogonally diagonalizable**:

$$A = Q\Lambda Q^T$$

where $Q$ is orthogonal ($Q^TQ = I$), $\Lambda$ is diagonal

자세한 내용은 [[Spectral Theorem]] 참조

## Spectral Theorem (Normal Operators)

**정리**: $T$가 normal operator^[정규 작용소] (over $\mathbb{C}$)이면

$$T^*T = TT^*$$

Then:

**(a)** $T$는 **unitarily diagonalizable**

**(b)** Orthonormal basis of eigenvectors 존재

**Examples of normal operators**:
- Hermitian: $T^* = T$
- Unitary: $T^*T = I$
- Skew-Hermitian: $T^* = -T$

자세한 내용은 [[Normal Operator]] 참조

## Perron-Frobenius Theorem

**정리**: $A$가 positive matrix (모든 entries $> 0$)이면

**(a)** Largest eigenvalue $\lambda_{\max}$는 **real and positive**

**(b)** $\lambda_{\max}$는 **simple** ($m_a = m_g = 1$)

**(c)** Eigenvector는 **positive entries**

**(d)** $\lambda_{\max} > |\lambda|$ for all other eigenvalues $\lambda$

**Applications**: Markov chains, PageRank, population dynamics

자세한 내용은 [[Perron-Frobenius Theorem]] 참조

## Gershgorin Circle Theorem

**정리**: $A$의 모든 eigenvalues는 Gershgorin discs의 합집합에 속함:

$$\bigcup_{i=1}^{n} D_i$$

where

$$D_i = \left\{\lambda \in \mathbb{C} : |\lambda - a_{ii}| \leq \sum_{j \neq i} |a_{ij}|\right\}$$

**응용**: Eigenvalue location, stability analysis

자세한 내용은 [[Gershgorin Circle Theorem]] 참조

## Power Method

**정리**: $A$가 dominant eigenvalue $\lambda_1$ (i.e., $|\lambda_1| > |\lambda_i|$ for $i \geq 2$)를 가지면

$$\lim_{k \to \infty} \frac{A^k v}{||A^k v||} = v_1$$

(eigenvector for $\lambda_1$)

**Algorithm**: Iterative method to find largest eigenvalue

자세한 내용은 [[Power Method]] 참조

## Jordan Normal Form

**정리**: 모든 matrix $A$ (over $\mathbb{C}$)는 similar to Jordan matrix:

$$A = PJP^{-1}$$

where $J$ is block diagonal:

$$J = \begin{pmatrix} J_1 & & \\ & \ddots & \\ & & J_k \end{pmatrix}$$

**Jordan block**:

$$J_i = \begin{pmatrix} \lambda & 1 & & \\ & \lambda & \ddots & \\ & & \ddots & 1 \\ & & & \lambda \end{pmatrix}$$

**의미**: "Almost diagonal" form (diagonalization의 일반화)

자세한 내용은 [[Jordan Normal Form]] 참조

## Rayleigh Quotient

**정의**: 

$$R(A, x) = \frac{x^* A x}{x^* x}$$

**정리**: For Hermitian $A$:

$$\lambda_{\min} \leq R(A, x) \leq \lambda_{\max}$$

with equality when $x$ is eigenvector

**Application**: Eigenvalue estimation, variational principle

자세한 내용은 [[Rayleigh Quotient]] 참조

## Min-Max Theorem (Courant-Fischer)

**정리**: For Hermitian $A$ with eigenvalues $\lambda_1 \geq \cdots \geq \lambda_n$:

$$\lambda_k = \max_{\dim(S) = k} \min_{x \in S, ||x||=1} x^* A x$$

$$= \min_{\dim(S) = n-k+1} \max_{x \in S, ||x||=1} x^* A x$$

**응용**: Variational characterization of eigenvalues

자세한 내용은 [[Min-Max Theorem]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### Geometric Interpretation

**Eigenvector = "Special Direction"**

$T(v) = \lambda v$ means:
- $T$ acts on $v$ by **stretching/shrinking** only
- **No rotation** (direction preserved)
- $\lambda$: scale factor

**시각화** (2D):

일반적인 벡터 $w$:

$$T(w) = \text{rotated and scaled}$$

Eigenvector $v$:

$$T(v) = \lambda v = \text{only scaled!}$$

### Physical Interpretation

**Principal Axes**:
- Eigenvectors = natural axes of the system
- Eigenvalues = behavior along those axes

**Examples**:
- **Vibrating string**: Eigenvectors = modes, Eigenvalues = frequencies
- **Moment of inertia**: Eigenvectors = principal axes
- **Stress tensor**: Eigenvectors = principal stress directions

### Dynamical Systems

$$\frac{dx}{dt} = Ax$$

**Solution**:

$$x(t) = e^{At} x_0 = P e^{\Lambda t} P^{-1} x_0$$

**Behavior**:
- $\lambda > 0$: Exponential growth
- $\lambda < 0$: Exponential decay
- $\lambda = 0$: Constant
- $\lambda$ complex: Oscillation

**Stability**: System stable $\Leftrightarrow$ $\text{Re}(\lambda) < 0$ for all $\lambda$

## Computational Aspects

### Finding Eigenvalues

**Small matrices** ($n \leq 4$):
- Solve $\det(A - \lambda I) = 0$ explicitly

**Large matrices**:
- **Power method**: Largest eigenvalue
- **QR algorithm**: All eigenvalues
- **Arnoldi/Lanczos**: For sparse matrices

**Complexity**: $O(n^3)$ in general

### Numerical Stability

**주의**:
- Eigenvalue problem can be **ill-conditioned**
- Small perturbations in $A$ $\Rightarrow$ large changes in eigenvalues

**Example** (Wilkinson):

$$A = \begin{pmatrix} 1 & 100 \\ 0 & 1 \end{pmatrix}$$

Small perturbation in (2,1) entry $\Rightarrow$ eigenvalues change dramatically!

**Condition number**:

$$\kappa(A) = \frac{|\lambda_{\max}|}{|\lambda_{\min}|}$$

## Why Zero is NOT Eigenvector

**Definition requires** $v \neq 0$

**Reason 1**: Trivial solution

$T(0) = 0 = \lambda \cdot 0$ for **all** $\lambda$

Eigenvalue would not be well-defined!

**Reason 2**: Linear independence

Eigenvectors for distinct eigenvalues should be linearly independent

$0$ is never linearly independent

**Reason 3**: Geometric meaning

Eigenvector = "special direction"

$0$ has no direction!

## Why Eigenvalue CAN Be Zero

$\lambda = 0$ is perfectly valid!

$$T(v) = 0 \cdot v = 0$$

**Meaning**: $v \in \ker(T)$

**Example**:

$$A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$$

$\lambda = 0$ (multiplicity 2)

**정리**: $\lambda = 0$ is eigenvalue $\Leftrightarrow$ $\det(A) = 0$ $\Leftrightarrow$ $A$ is singular

## Real vs Complex Eigenvalues

### Real Matrices

**Over $\mathbb{R}$**: Eigenvalues can be complex!

**Example** (Rotation):

$$R = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$$

Eigenvalues: $\pm i$ (complex!)

**Rule**: Complex eigenvalues come in conjugate pairs

If $\lambda = a + bi$ is eigenvalue, then $\overline{\lambda} = a - bi$ also

### Over $\mathbb{C}$

**Fundamental Theorem of Algebra**: Every polynomial has roots in $\mathbb{C}$

**결론**: Every $n \times n$ matrix (over $\mathbb{C}$) has $n$ eigenvalues (counting multiplicity) ✓

### Symmetric/Hermitian

**Real symmetric**: All eigenvalues **real**

**Hermitian** ($A^* = A$): All eigenvalues **real**

**Proof**: $\lambda = \frac{x^* A x}{x^* x}$ is real when $A^* = A$ ✓

## Algebraic vs Geometric Multiplicity

### Relationship

$$1 \leq m_g(\lambda) \leq m_a(\lambda)$$

### Diagonalizability

$A$ diagonalizable $\Leftrightarrow$ $m_g(\lambda) = m_a(\lambda)$ for all $\lambda$

### Examples

**Diagonalizable**:

$$A = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix}$$

$\lambda = 2$: $m_a = 2$, $m_g = 2$ ✓

**Non-diagonalizable**:

$$B = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}$$

$\lambda = 2$: $m_a = 2$, $m_g = 1$ ✗

### Gap

$m_a - m_g$ = "deficiency"

Measures "how far" from diagonalizable

If gap $> 0$: Need Jordan form

## Applications

### 1. Principal Component Analysis (PCA)

**Idea**: Find principal directions of data

**Method**:
- Compute covariance matrix $C$
- Find eigenvectors (principal components)
- Eigenvalues = variance along each component

**Use**: Dimensionality reduction, data visualization

자세한 내용은 [[Principal Component Analysis]] 참조

### 2. Google PageRank

**Idea**: Importance of web pages

**Model**: Markov chain on web graph

**Method**:
- Construct transition matrix $M$
- Find eigenvector for $\lambda = 1$ (steady state)
- Eigenvector entries = page ranks

자세한 내용은 [[PageRank]] 참조

### 3. Quantum Mechanics

**Observable**: Hermitian operator $\hat{O}$

**Measurement outcomes**: Eigenvalues of $\hat{O}$

**States**: Eigenvectors

**Example** (Hamiltonian):
- Eigenvalues = energy levels
- Eigenvectors = stationary states

### 4. Vibration Analysis

**System**: $M\ddot{x} + Kx = 0$

**Normal modes**: Eigenvectors of $M^{-1}K$

**Natural frequencies**: $\omega_i = \sqrt{\lambda_i}$

**Example**: Vibrating string, bridge oscillation

### 5. Image Compression

**SVD** (Singular Value Decomposition):

$$A = U\Sigma V^T$$

Related to eigenvalues of $AA^T$ and $A^TA$

**Use**: JPEG, low-rank approximation

### 6. Stability Analysis

**Linear system**: $\dot{x} = Ax$

**Stability**: 
- Stable $\Leftrightarrow$ $\text{Re}(\lambda) < 0$ for all $\lambda$
- Unstable $\Leftrightarrow$ $\exists \lambda$ with $\text{Re}(\lambda) > 0$

**Application**: Control theory, population dynamics

### 7. Graph Theory

**Adjacency matrix** $A$: Eigenvalues give graph properties

- Largest eigenvalue: Connectivity
- Second eigenvalue: Expansion, clustering
- Eigenspace: Graph partitioning

자세한 내용은 [[Spectral Graph Theory]] 참조

### 8. Differential Equations

**PDE**: Heat equation, wave equation

**Separation of variables**: Leads to eigenvalue problem

$$\nabla^2 u = \lambda u$$

**Solution**: Fourier series in eigenfunctions

## Common Pitfall

### 1. Zero Vector

$v = 0$ is **NOT** eigenvector!

**이유**: Definition requires $v \neq 0$

### 2. Different Eigenspaces

Eigenvectors for **different** $\lambda$ are linearly independent

But eigenvectors for **same** $\lambda$ can be dependent!

### 3. Similarity

Similar matrices have **same eigenvalues** but **different eigenvectors**

$B = P^{-1}AP$: $\lambda_B = \lambda_A$, but $v_B = P^{-1}v_A$

### 4. Characteristic Polynomial

$\det(A - \lambda I)$ vs $\det(\lambda I - A)$

Differ by $(-1)^n$, but **same roots**!

### 5. Multiplicity

Eigenvalue can have $m_a > 1$ but still be diagonalizable!

**Check**: Need $m_g = m_a$

### 6. Real vs Complex

Real matrix can have complex eigenvalues!

**Over $\mathbb{R}$**: Rotation has no real eigenvalues

**Over $\mathbb{C}$**: Always has eigenvalues

### 7. Singular Matrix

$A$ singular $\Leftrightarrow$ $\lambda = 0$ is eigenvalue $\Leftrightarrow$ $\det(A) = 0$

**Not** $\Leftrightarrow$ "no eigenvalues"!

### 8. Normalization

Eigenvector는 scalar multiple 자유!

$$v \text{ is eigenvector} \Rightarrow cv \text{ is eigenvector (for } c \neq 0\text{)}$$

Convention: Normalize to $||v|| = 1$

## 관련 개념

- [[Linear mapping]]: Eigenvector = invariant direction
- [[Determinant]]: $\det(A) = \prod \lambda_i$
- [[Trace]]: $\text{tr}(A) = \sum \lambda_i$
- [[Diagonalization]]: $A = PDP^{-1}$
- [[Jordan Normal Form]]: Generalization when non-diagonalizable
- [[Spectral Theorem]]: For symmetric/Hermitian
- [[Singular Value Decomposition]]: Related to eigenvalues of $A^TA$
- [[Cayley-Hamilton Theorem]]: $p_A(A) = 0$
- [[Characteristic Polynomial]]: $\det(A - \lambda I)$
- [[Minimal Polynomial]]: Smallest degree with $m(A) = 0$
- [[Matrix Exponential]]: $e^{At}$ using eigenvalues
- [[Perron-Frobenius Theorem]]: For positive matrices
- [[Spectral Graph Theory]]: Eigenvalues of graph matrices

## 추가 학습 주제

**기초**:
- Eigenvalue computation (2×2, 3×3)
- Eigenvector finding
- Diagonalization
- Geometric interpretation
- Real vs complex eigenvalues

**중급**:
- Characteristic polynomial
- Algebraic vs geometric multiplicity
- Cayley-Hamilton theorem
- Spectral theorem (symmetric)
- Power method
- Applications (PCA, Markov)

**고급**:
- Jordan normal form
- Spectral theorem (normal operators)
- Numerical methods (QR, Arnoldi)
- Perturbation theory
- Rayleigh quotient
- Min-max theorem
- Spectral graph theory
- Quantum mechanics applications

