# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Inner Product]]
- [[Hilbert Space]]
- [[Eigen Value, Eigen Vector]]
- [[Unitary Matrix]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Friedberg, Linear Algebra
- Conway, A Course in Functional Analysis
- Rudin, Functional Analysis

---

# <span class="header-definition">Definition</span>

## Adjoint Operator

$V$를 inner product space^[내적 공간]이라고 하고, $T: V \to V$를 linear operator^[선형 연산자]라고 하자.

**Adjoint operator**^[수반 연산자] $T^*: V \to V$는 다음을 만족하는 operator:

$$\langle T(v), w \rangle = \langle v, T^*(w) \rangle \quad \forall v, w \in V$$

### 존재성과 유일성

**존재성**: 
- Finite-dimensional inner product space에서 모든 linear operator $T$는 adjoint를 가짐
- Infinite-dimensional: Hilbert space에서 bounded operator만 adjoint 존재

**유일성**: 
- 위 조건을 만족하는 $T^*$는 **unique** (유일)
- 증명: $\langle v, S_1(w) - S_2(w) \rangle = 0$ for all $v, w$ $\Rightarrow$ $S_1 = S_2$

**Matrix representation**: $[T^*] = [T]^*$ (conjugate transpose^[켤레 전치])

$$[T]^* = \overline{[T]}^T = \overline{[T]^T}$$

**의미**: "내적을 보존하면서 반대쪽으로 작용"

## Normal Operator

**정의**: Linear operator $T: V \to V$가 **normal operator**^[정규 연산자]라는 것은:

$$T^* T = T T^*$$

**즉**: $T$가 adjoint $T^*$와 **commute**^[교환]함

**동치 조건** (finite-dimensional):

$$\|T(v)\| = \|T^*(v)\| \quad \forall v \in V$$

**의미**: $T$와 $T^*$가 "같은 방식으로 작동"

## Special Cases

Normal operator는 다음을 모두 포함하는 일반화:

### 1. Self-Adjoint Operator

**정의**: $T^* = T$

**다른 이름**:
- **Hermitian operator**^[에르미트 연산자] (complex)
- **Symmetric operator**^[대칭 연산자] (real)

**확인**: $T^* T = T \cdot T = T^2 = T \cdot T = T T^*$ 
**예시**: 
- Real symmetric matrix
- Observable in quantum mechanics

### 2. Unitary Operator

**정의**: $T^* T = T T^* = I$ (즉, $T^* = T^{-1}$)

**의미**: "내적을 보존" (isometry^[등거리 사상])

$$\langle T(v), T(w) \rangle = \langle v, w \rangle$$

**확인**: $T^* T = I = T T^*$ 
**예시**:
- Rotation, reflection
- Fourier transform
- Time evolution in quantum mechanics

### 3. Skew-Adjoint Operator

**정의**: $T^* = -T$

**다른 이름**: **Anti-Hermitian operator**^[반에르미트 연산자]

**확인**: $T^* T = (-T) T = -T^2$, $T T^* = T(-T) = -T^2$ 
**예시**:
- Imaginary part of Hermitian
- Infinitesimal generators

### Relationship Diagram

```
        Normal Operator (T*T = TT*)
               /    |    \
              /     |     \
             /      |      \
    Self-Adjoint  Unitary  Skew-Adjoint
      (T*=T)    (T*=T^-1)    (T*=-T)
```

**모든** self-adjoint, unitary, skew-adjoint operators는 normal!

## Matrix Characterization

$T$가 matrix $A$로 표현되면:

**Normal**: $A^* A = A A^*$

where $A^* = \overline{A}^T$ (conjugate transpose)

**예시** ($2 \times 2$):

$$A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}, \quad A^* = \begin{pmatrix} \overline{a} & \overline{c} \\ \overline{b} & \overline{d} \end{pmatrix}$$

$$A^* A = A A^* \quad \Leftrightarrow \quad |a|^2 + |c|^2 = |a|^2 + |b|^2 \text{ and } a\overline{b} + c\overline{d} = a\overline{c} + b\overline{d}$$

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Norm Preservation

**정리**: $T$ normal $\Rightarrow$ $\|T(v)\| = \|T^*(v)\|$ for all $v \in V$

**증명**:

$$\|T(v)\|^2 = \langle T(v), T(v) \rangle = \langle v, T^* T(v) \rangle$$

$T$ normal이므로 $T^* T = T T^*$:

$$= \langle v, T T^*(v) \rangle = \langle T^*(v), T^*(v) \rangle = \|T^*(v)\|^2$$

따라서 $\|T(v)\| = \|T^*(v)\|$ 
**의미**: $T$와 $T^*$가 "같은 크기로" 작용

### 2. Kernel Equality

**정리**: $T$ normal $\Rightarrow$ $\ker(T) = \ker(T^*)$

**증명**:

$v \in \ker(T) \Leftrightarrow T(v) = 0 \Leftrightarrow \|T(v)\| = 0$

Property 1에 의해:

$$\Leftrightarrow \|T^*(v)\| = 0 \Leftrightarrow T^*(v) = 0 \Leftrightarrow v \in \ker(T^*)$$ 
**Corollary**: $\text{Im}(T) = \text{Im}(T^*)^\perp$ (orthogonal complement)

### 3. Eigenspace Orthogonality

**정리**: $T$ normal이고 $\lambda \neq \mu$가 eigenvalues이면, 해당 eigenspaces는 **orthogonal**^[직교]

**증명**:

$T(v) = \lambda v$, $T(w) = \mu w$라고 하자

$$\langle T(v), w \rangle = \langle \lambda v, w \rangle = \lambda \langle v, w \rangle$$

Also:

$$\langle T(v), w \rangle = \langle v, T^*(w) \rangle$$

$T$ normal이므로 $T^*(w)$도 eigenvalue $\overline{\mu}$를 가짐:

**Lemma**: $T$ normal, $T(w) = \mu w \Rightarrow T^*(w) = \overline{\mu} w$

**증명**:

$$\langle T(v), w \rangle = \langle v, T^*(w) \rangle$$

for all $v$. Take $v = w$:

$$\langle T(w), w \rangle = \langle \mu w, w \rangle = \mu \|w\|^2$$

$$\langle w, T^*(w) \rangle = \overline{\langle T^*(w), w \rangle} = \overline{\langle T(w), w \rangle} = \overline{\mu} \|w\|^2$$

따라서 $T^*(w) = \overline{\mu} w$ 
**Back to main proof**:

$$\langle v, T^*(w) \rangle = \langle v, \overline{\mu} w \rangle = \mu \langle v, w \rangle$$

(real case에서는 $\overline{\mu} = \mu$, complex case에서는 조금 다름)

Complex case: $T^*(w) = \overline{\mu} w$이므로

$$\langle v, T^*(w) \rangle = \overline{\mu} \langle v, w \rangle$$

따라서:

$$\lambda \langle v, w \rangle = \overline{\mu} \langle v, w \rangle$$

$$(\lambda - \overline{\mu}) \langle v, w \rangle = 0$$

$\lambda \neq \mu \Rightarrow \lambda \neq \overline{\mu}$ (실수 eigenvalue인 경우나, complex case에서)

따라서 $\langle v, w \rangle = 0$ 
**의미**: Normal operator의 eigenvectors는 **orthogonal basis**를 형성!

### 4. Polynomial Commutativity

**정리**: $T$ normal $\Rightarrow$ $p(T)$ normal for any polynomial $p$

**증명**: $T^* T = T T^*$이면

$$(p(T))^* p(T) = p(T^*) p(T) = p(T) p(T^*) = p(T) (p(T))^*$$ 
**중요한 특수 케이스: Scalar Shift**

**정리**: $T$ normal, $c \in \mathbb{F}$ (scalar), $I$ identity

$$\Rightarrow T - cI \text{ is normal}$$

**증명**:

$$(T - cI)^* = T^* - \overline{c}I$$

$$(T - cI)^*(T - cI) = (T^* - \overline{c}I)(T - cI)$$
$$= T^*T - cT^* - \overline{c}T + |c|^2I$$

$$(T - cI)(T - cI)^* = (T - cI)(T^* - \overline{c}I)$$
$$= TT^* - \overline{c}T - cT^* + |c|^2I$$

$T$ normal이므로 $T^*T = TT^*$, 따라서 두 식이 같음 
**응용**:
- Eigenvalue equation: $(T - \lambda I)v = 0$
- Spectral shift: $T - cI$의 spectrum은 $T$의 spectrum을 $c$만큼 이동
- Normality preservation under translation

### 5. Product and Sum

**정리**:

**(a)** $S$, $T$ normal and commute $\Rightarrow$ $ST$ normal

**(b)** $S$, $T$ normal and commute $\Rightarrow$ $S + T$ normal

**증명**:

**(a)** Assume $ST = TS$:

$$(ST)^* (ST) = T^* S^* S T = T^* T S^* S = T T^* S^* S = T S^* T^* S$$

Need: $= ST T^* S^* = (ST)(ST)^*$

Requires $ST = TS$ and both normal 
**(b)** Similar computation 
**주의**: Commute 조건 없으면 성립 안 함!

### 6. Invertibility

**정리**: $T$ normal and invertible $\Rightarrow$ $T^{-1}$ normal

**증명**:

$$T^* T = T T^* \quad \Rightarrow \quad T^{-1} T^* T (T^{-1})^* = T^{-1} T T^* (T^{-1})^*$$

$$\Rightarrow \quad T^* (T^{-1})^* = (T^{-1})^* T^*$$

$$\Rightarrow \quad (T^{-1})^* (T^{-1}) = (T^{-1}) (T^{-1})^*$$ 
## Spectral Properties

### 7. Eigenvalue Reality (Self-Adjoint)

**정리**: $T$ self-adjoint $\Rightarrow$ all eigenvalues are **real**

**증명**:

$T(v) = \lambda v$, $v \neq 0$이면

$$\langle T(v), v \rangle = \langle \lambda v, v \rangle = \lambda \|v\|^2$$

Also:

$$\langle T(v), v \rangle = \langle v, T^*(v) \rangle = \langle v, T(v) \rangle = \langle v, \lambda v \rangle = \overline{\lambda} \|v\|^2$$

따라서 $\lambda = \overline{\lambda}$ $\Rightarrow$ $\lambda \in \mathbb{R}$ 
### 8. Unit Eigenvalue (Unitary)

**정리**: $T$ unitary $\Rightarrow$ all eigenvalues have $|\lambda| = 1$

**증명**:

$T(v) = \lambda v$, $v \neq 0$이면

$$\|v\|^2 = \|T(v)\|^2 = \|\lambda v\|^2 = |\lambda|^2 \|v\|^2$$

따라서 $|\lambda|^2 = 1$ $\Rightarrow$ $|\lambda| = 1$ 
**의미**: Unitary operator의 eigenvalues는 unit circle^[단위원] 위에!

### 9. Imaginary Eigenvalue (Skew-Adjoint)

**정리**: $T$ skew-adjoint $\Rightarrow$ all eigenvalues are **purely imaginary**

**증명**:

$T^* = -T$이고 $T(v) = \lambda v$이면

$$\langle T(v), v \rangle = \lambda \|v\|^2$$

$$\langle v, T^*(v) \rangle = \langle v, -T(v) \rangle = -\overline{\lambda} \|v\|^2$$

But also:

$$\langle T(v), v \rangle = \overline{\langle v, T^*(v) \rangle} = -\lambda \|v\|^2$$

따라서 $\lambda = -\overline{\lambda}$ $\Rightarrow$ $\lambda = i \cdot (\text{real})$ 
## Diagonalization

### 10. Spectral Theorem (Finite-Dimensional)

**정리**: $V$ finite-dimensional complex inner product space, $T: V \to V$ linear

다음은 동치:

**(a)** $T$ is normal

**(b)** $V$는 $T$의 **orthonormal eigenvectors**^[정규직교 고유벡터]로 이루어진 basis를 가짐

**(c)** $T$는 **unitarily diagonalizable**^[유니타리 대각화 가능]: $T = U D U^*$ where $U$ unitary, $D$ diagonal

**의미**: Normal operator는 **완전히 대각화 가능**!

**증명 sketch**:

**(a) $\Rightarrow$ (b)**: Induction on dimension
- Base: $\dim(V) = 1$ trivial
- Step: $T$는 eigenvalue $\lambda$ 가짐 (fundamental theorem of algebra)
- Eigenspace $E_\lambda$와 orthogonal complement $E_\lambda^\perp$ 고려
- $T$ leaves $E_\lambda^\perp$ invariant (by normality!)
- Induction hypothesis 적용 
**(b) $\Rightarrow$ (c)**: Orthonormal eigenvectors $\{u_1, \ldots, u_n\}$이면
- $U = [u_1 | \cdots | u_n]$ is unitary
- $T u_i = \lambda_i u_i$
- $U^* T U = D$ where $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$ 
**(c) $\Rightarrow$ (a)**: 
$$T^* T = (U D U^*)^* (U D U^*) = U D^* U^* U D U^* = U D^* D U^*$$
$$T T^* = (U D U^*)(U D U^*)^* = U D U^* U D^* U^* = U D D^* U^*$$

Diagonal matrices commute: $D^* D = D D^*$

따라서 $T^* T = T T^*$ 
### Real Spectral Theorem

**정리**: $V$ finite-dimensional **real** inner product space, $T: V \to V$ **self-adjoint**

$\Rightarrow$ $V$는 $T$의 **orthonormal eigenvectors**로 이루어진 basis를 가짐 (with **real** eigenvalues)

**의미**: Real symmetric matrices는 **orthogonally diagonalizable**^[직교 대각화 가능]!

$$T = Q D Q^T$$

where $Q$ orthogonal ($Q^T Q = I$), $D$ diagonal (real entries)

---

# <span class="header-examples">Examples</span>

## Example 1: Diagonal Matrix

$$A = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}$$

**Adjoint**:

$$A^* = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix} = A$$

**Check normality**:

$$A^* A = \begin{pmatrix} 4 & 0 \\ 0 & 9 \end{pmatrix} = A A^*$$ 
**Type**: Self-adjoint (hence normal)

**Eigenvalues**: $\lambda_1 = 2$, $\lambda_2 = 3$ (real)

**Eigenvectors**: $e_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $e_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$ (orthonormal)

## Example 2: Rotation Matrix

$$R_\theta = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$

**Adjoint**:

$$R_\theta^* = \begin{pmatrix} \cos\theta & \sin\theta \\ -\sin\theta & \cos\theta \end{pmatrix} = R_{-\theta} = R_\theta^{-1}$$

**Check normality**:

$$R_\theta^* R_\theta = I = R_\theta R_\theta^*$$ 
**Type**: Unitary (hence normal)

**Eigenvalues**: $\lambda = e^{i\theta}$, $\overline{\lambda} = e^{-i\theta}$ (unit modulus)

**Complex eigenvectors**: 

$$v_1 = \begin{pmatrix} 1 \\ i \end{pmatrix}, \quad v_2 = \begin{pmatrix} 1 \\ -i \end{pmatrix}$$

## Example 3: Symmetric Matrix

$$A = \begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix}$$

**Adjoint**:

$$A^* = \begin{pmatrix} 1 & 2 \\ 2 & 1 \end{pmatrix} = A$$

**Check normality**:

$$A^* A = \begin{pmatrix} 5 & 4 \\ 4 & 5 \end{pmatrix} = A A^*$$ 
**Type**: Self-adjoint (symmetric, hence normal)

**Eigenvalues**:

$$\det(A - \lambda I) = (1-\lambda)^2 - 4 = \lambda^2 - 2\lambda - 3 = 0$$

$$\lambda_1 = 3, \quad \lambda_2 = -1$$ (real)

**Eigenvectors**:

$$v_1 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad v_2 = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix}$$

**Orthonormal**: $\langle v_1, v_2 \rangle = 0$ 
**Diagonalization**:

$$A = Q D Q^T = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & -1 \end{pmatrix} \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix}$$

## Example 4: Skew-Symmetric Matrix

$$A = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}$$

**Adjoint**:

$$A^* = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = -A$$

**Check normality**:

$$A^* A = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = A A^*$$ 
**Type**: Skew-adjoint (hence normal)

**Eigenvalues**: $\lambda = \pm i$ (purely imaginary)

**Physical interpretation**: Infinitesimal rotation

## Example 5: Normal but NOT Self-Adjoint

$$A = \begin{pmatrix} 1 & 1 \\ -1 & 1 \end{pmatrix}$$

**Adjoint**:

$$A^* = \begin{pmatrix} 1 & -1 \\ 1 & 1 \end{pmatrix}$$

**Check normality**:

$$A^* A = \begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix} = A A^*$$ 
**Type**: Normal but neither self-adjoint nor unitary

**Eigenvalues**: $\lambda = 1 \pm i$

**Eigenvectors**: Orthogonal!

## Non-Example: Non-Normal Matrix

$$A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$$

(nilpotent matrix)

**Adjoint**:

$$A^* = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}$$

**Check normality**:

$$A^* A = \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} \neq \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} = A A^*$$

**NOT normal!** ✗

**Eigenvalues**: $\lambda = 0$ (double)

**Eigenvectors**: Only one independent eigenvector!

Cannot be diagonalized (even over $\mathbb{C}$)

**Jordan form**: $J = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$ (already in Jordan form)

## Example 6: Fourier Transform (Infinite-Dimensional)

$$\mathcal{F}: L^2(\mathbb{R}) \to L^2(\mathbb{R})$$

$$(\mathcal{F}f)(\omega) = \frac{1}{\sqrt{2\pi}} \int_{-\infty}^\infty f(t) e^{-i\omega t} \, dt$$

**Adjoint**: Inverse Fourier transform

$$\mathcal{F}^* = \mathcal{F}^{-1}$$

**Unitary**: $\mathcal{F}^* \mathcal{F} = I$

**Normal**: $\mathcal{F}^* \mathcal{F} = \mathcal{F} \mathcal{F}^*$ 
**Eigenvalues**: $\pm 1, \pm i$ (discrete!)

**Eigenfunctions**: Hermite functions

## Example 7: Momentum Operator (Quantum Mechanics)

$$\hat{p} = -i\hbar \frac{d}{dx}$$

on $L^2(\mathbb{R})$

**Adjoint**:

$$\hat{p}^* = -i\hbar \frac{d}{dx} = \hat{p}$$

**Self-adjoint**: $\hat{p}^* = \hat{p}$

**Normal**: 
**Eigenvalues**: All real numbers (continuous spectrum!)

**Eigenfunctions**: $e^{ikx}$ (not in $L^2$ but in distributional sense)

---

# <span class="header-theorem">Theorem</span>

## Spectral Theorem (Detailed Statement)

**정리** (**Spectral Theorem for Normal Operators**^[정규 연산자의 스펙트럼 정리]):

$V$ finite-dimensional complex inner product space, $T: V \to V$ normal operator

$\Rightarrow$ $\exists$ orthonormal basis $\{u_1, \ldots, u_n\}$ consisting of eigenvectors of $T$

**즉**:

$$T u_i = \lambda_i u_i, \quad \langle u_i, u_j \rangle = \delta_{ij}$$

**Diagonalization**:

$$T = U D U^*$$

where:
- $U = [u_1 | \cdots | u_n]$ is unitary
- $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$

**Functional form**:

$$T = \sum_{i=1}^n \lambda_i P_i$$

where $P_i$ is orthogonal projection onto eigenspace of $\lambda_i$:

$$P_i(v) = \langle v, u_i \rangle u_i$$

**의미**: Normal operator는 eigenspaces의 **orthogonal direct sum**^[직교 직합]!

## Real Spectral Theorem (Detailed)

**정리**:

$V$ finite-dimensional **real** inner product space, $T: V \to V$ **self-adjoint**

$\Rightarrow$ $\exists$ orthonormal basis of **real** eigenvectors

**Diagonalization**:

$$T = Q D Q^T$$

where:
- $Q$ orthogonal ($Q^T Q = I$, real entries)
- $D$ diagonal (real entries)

**예시**: Every real symmetric matrix is orthogonally diagonalizable!

## Infinite-Dimensional Spectral Theorem

**정리** (Functional analysis):

$H$ separable Hilbert space, $T: H \to H$ bounded normal operator

$\Rightarrow$ $T$는 **spectral measure**^[스펙트럼 측도] $E$를 통해 표현:

$$T = \int_{\sigma(T)} \lambda \, dE(\lambda)$$

where $\sigma(T)$ is spectrum of $T$

**의미**: "Continuous" version of $T = \sum \lambda_i P_i$

자세한 내용은 [[Spectral Theory]] 참조

## Unitary Diagonalization Characterization

**정리**: $T: V \to V$ (finite-dimensional complex)

다음은 동치:

**(a)** $T$ is normal

**(b)** $T$ is unitarily diagonalizable

**(c)** $T = U D U^*$ for some unitary $U$ and diagonal $D$

**(d)** $V$는 $T$의 orthonormal eigenvectors의 basis를 가짐

**(e)** Different eigenspaces are orthogonal

**의미**: Normality $\Leftrightarrow$ Unitary diagonalizability

## Schur's Theorem

**정리** (**Schur's Lemma**^[슈어 보조정리]):

Every square matrix is unitarily similar to upper triangular matrix

$$A = U T U^*$$

where $U$ unitary, $T$ upper triangular

**Corollary**: $A$ normal $\Leftrightarrow$ $T$ diagonal

**증명**: 

$A$ normal $\Rightarrow$ $U T U^*$ normal $\Rightarrow$ $T$ normal

Upper triangular + normal $\Rightarrow$ diagonal 
## Fuglede's Theorem

**정리** (**Fuglede-Putnam Theorem**^[푸글레드-퍼트남 정리]):

$N$, $M$ normal operators, $X$ linear operator

$$NX = XM \quad \Rightarrow \quad N^* X = X M^*$$

**특수한 경우** ($N = M$):

$$NT = TN \quad \Rightarrow \quad N^* T = T N^*$$

**의미**: $N$과 commute하면 $N^*$와도 commute!

**응용**: Simultaneous diagonalization

## Simultaneous Diagonalization

**정리**: $S$, $T$ normal and **commute** ($ST = TS$)

$\Rightarrow$ $\exists$ orthonormal basis that **simultaneously diagonalizes** both $S$ and $T$

**증명**:

$T$를 diagonalize: $V = \bigoplus E_{\lambda_i}$ (eigenspaces of $T$)

$ST = TS \Rightarrow S$ leaves each $E_{\lambda_i}$ invariant

$S$를 각 $E_{\lambda_i}$에서 diagonalize

Combine bases 
**응용**: Quantum mechanics (commuting observables)

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### What is Normal Operator?

**Intuition**: "$T$와 $T^*$가 '같은 방향으로' 작용"

**Geometric**:
- Self-adjoint: "Reflection" + "Scaling"
- Unitary: "Rotation" (거리 보존)
- Normal: Combination (eigenspaces orthogonal!)

**Algebraic**: $T^* T = T T^*$ (commutativity)

### Why Adjoint?

**Definition**: $\langle T(v), w \rangle = \langle v, T^*(w) \rangle$

**Intuition**: "Transpose with respect to inner product"

**Matrix**: $A^* = \overline{A}^T$ (conjugate transpose)

**Physical**: Time reversal, hermitian conjugate

### Spectral Theorem Intuition

**정리**: Normal $\Rightarrow$ Orthonormal eigenbasis

**Why powerful?**

**(1) Diagonalization**: $T = U D U^*$ (simplest form!)

**(2) Computation**: $T^n = U D^n U^*$ (easy!)

**(3) Functions**: $f(T) = U f(D) U^*$ (define $e^T$, $\sin T$, etc.)

**(4) Geometric**: Eigenspaces orthogonal (coordinate axes!)

**예시**: Symmetric matrix $\Rightarrow$ principal axes!

### Normal vs Non-Normal

**Normal**: "Nice" behavior
- Orthogonal eigenspaces
- Unitary diagonalization
- Stable numerics

**Non-normal**: "Pathological" behavior
- No orthogonal eigenvectors
- Only Jordan form (not diagonal)
- Unstable (e.g., $\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$)

**예시**: Nilpotent matrix ≠ normal

## Connection to Other Concepts

### 1. Spectral Theory

Normal operators are the foundation of spectral theory

**Finite-dimensional**: $T = \sum \lambda_i P_i$ (discrete spectrum)

**Infinite-dimensional**: $T = \int \lambda \, dE(\lambda)$ (continuous spectrum)

**응용**: Quantum mechanics, PDEs

자세한 내용은 [[Spectral Theory]] 참조

### 2. Functional Calculus

**정의**: For normal $T$, define $f(T)$ for functions $f$

$$f(T) = U f(D) U^* = \sum f(\lambda_i) P_i$$

**예시**:
- $e^{iT}$: Time evolution (quantum mechanics)
- $\sqrt{T}$: Square root (positive operators)
- $\sin T$, $\cos T$: Trigonometric

**Only works for normal operators!**

### 3. Quantum Mechanics

**Observables**: Self-adjoint operators
- Measurement outcomes = eigenvalues (real!)
- States = eigenvectors (orthonormal!)

**Unitary operators**: Time evolution
- $U(t) = e^{-iHt/\hbar}$ where $H$ Hamiltonian (self-adjoint)
- Preserves probability: $|\langle \psi | \psi \rangle| = 1$

**Commuting observables**: Simultaneously diagonalizable
- Simultaneous eigenstates
- Compatible measurements

자세한 내용은 [[Quantum Mechanics]] 참조

### 4. Diagonalization Theory

**General matrices**: Jordan normal form (upper triangular blocks)

**Normal matrices**: **Diagonal** (simplest!)

**Hierarchy**:
```
Diagonal ⊂ Normal ⊂ Diagonalizable ⊂ All matrices
```

**Schur form**: Every matrix $\sim$ upper triangular

**Normal**: Upper triangular + normal = diagonal!

### 5. Matrix Functions

**Problem**: Define $f(A)$ for matrix $A$?

**Normal case**: Easy!

$$A = U D U^* \quad \Rightarrow \quad f(A) = U f(D) U^*$$

where $f(D) = \text{diag}(f(\lambda_1), \ldots, f(\lambda_n))$

**예시**: $e^A$, $\log A$, $A^{1/2}$

**Non-normal**: Much harder! (need Jordan form)

### 6. Numerical Stability

**Normal matrices**: Numerically stable
- Condition number $\kappa(U) = 1$ (unitary!)
- Eigenvalue computation stable

**Non-normal matrices**: Can be extremely unstable
- Small perturbations $\Rightarrow$ large eigenvalue changes
- Pseudospectrum (not just eigenvalues!)

**예시**: 

$$A = \begin{pmatrix} 0 & 1000 \\ 0 & 0 \end{pmatrix}$$

Eigenvalue $= 0$ (double), but $\|A^n\| = 1000^n$ (grows exponentially!)

## Special Types Details

### Self-Adjoint Operators

**Properties**:
- Eigenvalues **real**
- Eigenvectors **orthogonal**
- $T = T^*$

**Physical interpretation**: Observables (quantum mechanics)

**예시**:
- Position: $\hat{x}$
- Momentum: $\hat{p} = -i\hbar \frac{d}{dx}$
- Hamiltonian: $\hat{H}$ (energy)

**응용**:
- Variational principles
- Min-max theorems
- Positive operators ($\langle T(v), v \rangle \geq 0$)

### Unitary Operators

**Properties**:
- $T^* T = T T^* = I$
- $T^* = T^{-1}$
- $|\lambda| = 1$ (eigenvalues on unit circle)
- Preserves inner product: $\langle T(v), T(w) \rangle = \langle v, w \rangle$

**Geometric**: Isometries (rotation, reflection)

**Physical interpretation**: Symmetries, time evolution

**예시**:
- Fourier transform: $\mathcal{F}$
- Rotation: $R_\theta$
- Time evolution: $U(t) = e^{-iHt/\hbar}$

**응용**:
- Symmetry groups
- Quantum gates
- Signal processing

### Skew-Adjoint Operators

**Properties**:
- $T^* = -T$
- Eigenvalues **purely imaginary**
- $e^T$ is unitary!

**Connection**: $H$ self-adjoint $\Rightarrow$ $iH$ skew-adjoint

**Physical interpretation**: Generators of symmetries

**예시**:
- Angular momentum: $\hat{L}$ (infinitesimal rotations)
- Hamiltonian: $H$ generates $U(t) = e^{-iHt}$

**Lie theory**: Lie algebra (skew-adjoint) $\to$ Lie group (unitary)

자세한 내용은 [[Lie Algebra]] 참조

## Applications

### 1. Principal Component Analysis (PCA)

**Problem**: Find principal directions of data

**Solution**: Eigenvalue decomposition of covariance matrix $C$

$$C = Q D Q^T$$

where $Q$ orthogonal, $D = \text{diag}(\lambda_1, \ldots, \lambda_n)$

**Why it works**: $C$ symmetric (self-adjoint!) $\Rightarrow$ orthogonal eigenvectors

**Principal components**: Eigenvectors with largest eigenvalues

### 2. Quantum Mechanics

**Observables**: Self-adjoint operators
- Hermitian matrices
- Real eigenvalues (measurement outcomes)
- Orthogonal eigenstates (pure states)

**Time evolution**: Unitary operators
- $|\psi(t)\rangle = U(t) |\psi(0)\rangle$
- $U(t) = e^{-iHt/\hbar}$ (unitary!)
- Preserves normalization

**Commuting observables**: Simultaneously measurable
- $[A, B] = 0 \Rightarrow$ simultaneous eigenbasis

### 3. Vibration Analysis

**Normal modes**: Eigenvectors of oscillating system

**Equation**: $M \ddot{x} + K x = 0$ (mass-spring system)

**Eigenvalue problem**: $K v = \omega^2 M v$

**Why self-adjoint**: $K$, $M$ symmetric positive definite

**Solution**: Orthogonal normal modes!

$$x(t) = \sum c_i e^{i\omega_i t} v_i$$

### 4. Image Compression (SVD)

**Singular Value Decomposition**: $A = U \Sigma V^*$

**Connection**: 
- $A^* A = V \Sigma^2 V^*$ (self-adjoint!)
- $A A^* = U \Sigma^2 U^*$ (self-adjoint!)

**Compression**: Keep largest singular values

**Why it works**: Spectral theorem for $A^* A$, $A A^*$!

### 5. Differential Equations

**ODE**: $\frac{dx}{dt} = A x$

**Solution**: $x(t) = e^{At} x_0$

**$A$ normal**: Easy!

$$A = U D U^* \quad \Rightarrow \quad e^{At} = U e^{Dt} U^*$$

where $e^{Dt} = \text{diag}(e^{\lambda_1 t}, \ldots, e^{\lambda_n t})$

**$A$ self-adjoint**: Real eigenvalues $\Rightarrow$ real solutions

**$A$ skew-adjoint**: Imaginary eigenvalues $\Rightarrow$ oscillations

### 6. Control Theory

**Stability analysis**: Eigenvalues of system matrix

**Normal operators**: Clear stability criterion
- Self-adjoint: $\lambda \in \mathbb{R}$ (no oscillations if $\lambda < 0$)
- Unitary: $|\lambda| = 1$ (marginally stable)
- General normal: Eigenvalues determine behavior

자세한 내용은 [[Control Theory]] 참조

### 7. Signal Processing

**Fourier transform**: Unitary operator
- Parseval's theorem: $\|\mathcal{F}f\| = \|f\|$
- Orthogonal eigenfunctions (complex exponentials)

**Filters**: Multiplication in frequency domain
- $\mathcal{F}(f * g) = \mathcal{F}(f) \cdot \mathcal{F}(g)$

자세한 내용은 [[Signal Processing]] 참조

## Common Misconceptions

### 1. Diagonalizable = Normal?

**실수**: "Diagonalizable $\Rightarrow$ normal"

**반례**:

$$A = \begin{pmatrix} 1 & 1 \\ 0 & 2 \end{pmatrix}$$

Diagonalizable but NOT normal!

**정확**: Normal $\Rightarrow$ **unitarily** diagonalizable (stronger!)

### 2. Real Eigenvalues = Self-Adjoint?

**실수**: "Real eigenvalues $\Rightarrow$ self-adjoint"

**반례**:

$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$

Eigenvalue $= 1$ (real), but NOT self-adjoint!

**정확**: Self-adjoint $\Rightarrow$ real eigenvalues (one direction only!)

### 3. Symmetric = Self-Adjoint?

**Over $\mathbb{R}$**: YES! ($A^T = A \Rightarrow A^* = A$)

**Over $\mathbb{C}$**: NO!

$$A = \begin{pmatrix} 1 & i \\ i & 1 \end{pmatrix}$$

Symmetric ($A^T = A$) but NOT self-adjoint ($A^* \neq A$)!

**정확**: Self-adjoint = **Hermitian** (not just symmetric!)

### 4. All Normal Operators are Self-Adjoint?

**실수**: "Normal = self-adjoint"

**반례**: Unitary operators!

$$R_{90°} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$$

Normal but NOT self-adjoint!

**정확**: Self-adjoint ⊂ Normal (proper subset)

### 5. Matrix + Adjoint = Normal?

**실수**: "$A + A^*$ is normal"

**실제**: $A + A^*$ is **always self-adjoint**!

$$(A + A^*)^* = A^* + (A^*)^* = A^* + A = A + A^*$$ 
**But**: $A$ itself may not be normal!

## Historical Note

**19th century**: 
- Symmetric matrices (real case)
- Spectral theorem for symmetric operators

**Early 20th century**:
- Hilbert: Spectral theory for integral operators
- von Neumann: Spectral theorem for unbounded operators (quantum mechanics)

**1930s-40s**:
- Functional analysis develops
- Normal operators characterized
- Stone-von Neumann theorem

**Modern**:
- Numerical linear algebra (stability of normal matrices)
- Quantum information theory (unitary gates)
- Operator algebras (C*-algebras)

**Key figures**: Hilbert, von Neumann, Stone, Wey l, Riesz

## 관련 개념

- [[Linear mapping]]: General operators
- [[Inner Product]]: Defines adjoint
- [[Hilbert Space]]: Infinite-dimensional setting
- [[Eigen Value, Eigen Vector]]: Diagonalization
- [[Unitary Matrix]]: Unitary operators
- [[Spectral Theory]]: General spectral decomposition
- [[Functional Analysis]]: Unbounded operators
- [[Quantum Mechanics]]: Physical applications
- [[Self-Adjoint Operator]]: Hermitian case
- [[Positive Operator]]: $\langle T(v), v \rangle \geq 0$
- [[Compact Operator]]: Infinite-dimensional analogue
- [[C* Algebra]]: Operator algebras
- [[Singular Value Decomposition]]: Generalization

## 추가 학습 주제

**기초**:
- Adjoint operator definition
- Normal operator definition
- Self-adjoint, unitary, skew-adjoint cases
- Spectral theorem (finite-dimensional)

**중급**:
- Diagonalization procedures
- Functional calculus ($f(T)$)
- Simultaneous diagonalization
- Applications (PCA, quantum mechanics)

**고급**:
- Infinite-dimensional spectral theorem
- Unbounded operators
- Spectral measures
- Operator algebras (C*, von Neumann)
- Non-normal operators (pseudospectrum)
- Numerical analysis of normal matrices

