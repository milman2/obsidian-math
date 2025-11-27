# <span class="header-prerequisite">Prerequisite</span>
- [[Vector Space]]
- [[Field]]
- [[Subspace]]
- [[Linear Independence]]
- [[Basis and Dimension]]

# <span class="header-reference">Reference</span>
- Axler, Linear Algebra Done Right
- Friedberg, Linear Algebra
- Hoffman & Kunze, Linear Algebra
- Roman, Advanced Linear Algebra

---

# <span class="header-definition">Definition</span>

## Linear Mapping

$V$, $W$를 field^[체] $\mathbb{F}$ 위의 vector space^[벡터 공간]이라 하자.

함수 $T: V \to W$가 **linear mapping**^[선형 사상] (또는 **linear transformation**^[선형 변환], **linear operator**^[선형 연산자])이라는 것은 다음을 만족하는 것이다:

$$\forall u, v \in V, \, \forall \alpha, \beta \in \mathbb{F}, \quad T(\alpha u + \beta v) = \alpha T(u) + \beta T(v)$$

**Alternative definition** (두 조건으로 분리):

**(1) Additivity^[가법성]**:

$$T(u + v) = T(u) + T(v) \quad \forall u, v \in V$$

**(2) Homogeneity^[동차성]**:

$$T(\alpha v) = \alpha T(v) \quad \forall \alpha \in \mathbb{F}, v \in V$$

**동치성**: 두 정의는 완전히 동치

## Terminology

**다양한 용어** (모두 같은 개념):

- **Linear mapping**^[선형 사상]
- **Linear transformation**^[선형 변환]
- **Linear operator**^[선형 연산자] (특히 $T: V \to V$일 때)
- **Linear map**^[선형 사상]
- **Linear function**^[선형 함수] (덜 일반적)

**표기법**:
- $\mathcal{L}(V, W)$: $V$에서 $W$로의 모든 linear mappings의 집합
- $\mathcal{L}(V)$: $\mathcal{L}(V, V)$ (linear operators on $V$)
- $\text{Hom}(V, W)$: Homomorphism space (대수학에서)

## Special Cases

### Linear Operator

$T: V \to V$ (같은 공간으로의 linear mapping)

**Endomorphism**^[자기준동형사상]이라고도 함

### Linear Functional

$f: V \to \mathbb{F}$ (scalar-valued^[스칼라값] linear mapping)

**예시**: Inner product $f(v) = \langle v, u \rangle$ for fixed $u$

모든 linear functionals의 집합: **Dual space**^[쌍대 공간] $V^*$

자세한 내용은 [[Dual Spaces]] 참조

### Isomorphism

Bijective^[전단사] linear mapping

**의미**: $V$와 $W$가 "본질적으로 같음" (structurally identical)

자세한 내용은 [[Isomorphism]] 참조

## Vector Space of Linear Mappings

**정리**: $\mathcal{L}(V, W)$는 vector space

**Addition**:

$$(S + T)(v) = S(v) + T(v)$$

**Scalar multiplication**:

$$(cT)(v) = c \cdot T(v)$$

**Zero element**: Zero map $0(v) = 0_W$

**차원** (finite-dimensional case):

$$\dim(\mathcal{L}(V, W)) = \dim(V) \cdot \dim(W)$$

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Zero Vector Preservation

**정리**: $T(0_V) = 0_W$

**증명**:

$$T(0_V) = T(0 \cdot 0_V) = 0 \cdot T(0_V) = 0_W$$ ✓

**의미**: Linear mapping은 항상 원점을 원점으로 보냄

**Contrapositive**: $T(0) \neq 0 \Rightarrow T$ is NOT linear!

### 2. Negative Preservation

**정리**: $T(-v) = -T(v)$

**증명**:

$$T(-v) = T((-1) \cdot v) = (-1) \cdot T(v) = -T(v)$$ ✓

### 3. Linear Combination Preservation

**정리**: 

$$T\left(\sum_{i=1}^n \alpha_i v_i\right) = \sum_{i=1}^n \alpha_i T(v_i)$$

**증명** (Induction):

**Base**: $n = 1$: $T(\alpha_1 v_1) = \alpha_1 T(v_1)$ ✓

**Step**: Assume for $n$, prove for $n+1$:

$$T\left(\sum_{i=1}^{n+1} \alpha_i v_i\right) = T\left(\sum_{i=1}^n \alpha_i v_i + \alpha_{n+1} v_{n+1}\right)$$

$$= T\left(\sum_{i=1}^n \alpha_i v_i\right) + T(\alpha_{n+1} v_{n+1})$$

$$= \sum_{i=1}^n \alpha_i T(v_i) + \alpha_{n+1} T(v_{n+1}) = \sum_{i=1}^{n+1} \alpha_i T(v_i)$$ ✓

**의미**: Linear mapping은 **선형 결합을 보존**

### 4. Subspace Preservation

**정리**: $U \subseteq V$가 subspace이면 $T(U) \subseteq W$도 subspace

**증명**:

**(a)** $0_W = T(0_V) \in T(U)$ ✓

**(b)** $w_1, w_2 \in T(U) \Rightarrow w_1 = T(u_1)$, $w_2 = T(u_2)$

$$w_1 + w_2 = T(u_1) + T(u_2) = T(u_1 + u_2) \in T(U)$$ ✓

**(c)** $\alpha w_1 = \alpha T(u_1) = T(\alpha u_1) \in T(U)$ ✓

따라서 $T(U)$는 subspace ✓

### 5. Composition Preserves Linearity

**정리**: $T: U \to V$, $S: V \to W$ linear이면 $S \circ T: U \to W$ linear

**증명**:

$$(S \circ T)(\alpha u_1 + \beta u_2) = S(T(\alpha u_1 + \beta u_2))$$

$$= S(\alpha T(u_1) + \beta T(u_2)) = \alpha S(T(u_1)) + \beta S(T(u_2))$$

$$= \alpha (S \circ T)(u_1) + \beta (S \circ T)(u_2)$$ ✓

**의미**: Linear mappings의 composition은 linear

## Important Subspaces

### Kernel (Null Space)

**정의**: 

$$\ker(T) = \{v \in V : T(v) = 0_W\}$$

**Alternative names**:
- **Kernel**^[핵]
- **Null space**^[영공간]

**정리**: $\ker(T)$는 $V$의 subspace

**증명**:

**(a)** $T(0_V) = 0_W \Rightarrow 0_V \in \ker(T)$ ✓

**(b)** $v_1, v_2 \in \ker(T)$이면

$$T(v_1 + v_2) = T(v_1) + T(v_2) = 0_W + 0_W = 0_W$$

따라서 $v_1 + v_2 \in \ker(T)$ ✓

**(c)** $v \in \ker(T)$, $\alpha \in \mathbb{F}$이면

$$T(\alpha v) = \alpha T(v) = \alpha \cdot 0_W = 0_W$$

따라서 $\alpha v \in \ker(T)$ ✓

### Image (Range)

**정의**:

$$\text{Im}(T) = \{w \in W : \exists v \in V \text{ such that } T(v) = w\}$$

$$= \{T(v) : v \in V\}$$

**Alternative names**:
- **Image**^[상]
- **Range**^[치역]

**정리**: $\text{Im}(T)$는 $W$의 subspace

**증명**: Property 4 사용 ($\text{Im}(T) = T(V)$, $V$는 subspace) ✓

### Relationship with Basis

**정리**: $\{v_1, \ldots, v_n\}$이 $V$의 basis이면

$$\text{Im}(T) = \text{span}\{T(v_1), \ldots, T(v_n)\}$$

**증명**:

모든 $v \in V$는 $v = \sum_{i=1}^n \alpha_i v_i$로 표현

$$T(v) = T\left(\sum_{i=1}^n \alpha_i v_i\right) = \sum_{i=1}^n \alpha_i T(v_i)$$

따라서 $\text{Im}(T) = \text{span}\{T(v_1), \ldots, T(v_n)\}$ ✓

**의미**: Image를 구하려면 basis의 image만 확인하면 됨!

## Injectivity and Surjectivity

### Injective (One-to-One)

**정의**: $T$가 **injective**^[단사]라는 것은

$$T(v_1) = T(v_2) \quad \Rightarrow \quad v_1 = v_2$$

**정리**: 다음은 동치:

**(a)** $T$ is injective

**(b)** $\ker(T) = \{0_V\}$

**(c)** $T$가 linearly independent^[선형 독립] sets를 linearly independent sets로 보냄

**증명** (a) $\Leftrightarrow$ (b):

**($\Rightarrow$)**: $v \in \ker(T) \Rightarrow T(v) = 0_W = T(0_V)$

Injective이므로 $v = 0_V$ ✓

**($\Leftarrow$)**: $T(v_1) = T(v_2) \Rightarrow T(v_1 - v_2) = 0_W$

따라서 $v_1 - v_2 \in \ker(T) = \{0_V\}$

즉, $v_1 - v_2 = 0_V \Rightarrow v_1 = v_2$ ✓

### Surjective (Onto)

**정의**: $T$가 **surjective**^[전사]라는 것은

$$\text{Im}(T) = W$$

즉, 모든 $w \in W$에 대해 $T(v) = w$인 $v \in V$ 존재

**정리**: 다음은 동치:

**(a)** $T$ is surjective

**(b)** $\text{Im}(T) = W$

**(c)** $\text{rank}(T) = \dim(W)$ (finite-dimensional case)

### Bijective (Isomorphism)

**정의**: $T$가 **bijective**^[전단사]라는 것은 injective이면서 surjective

**정리**: $T$가 bijective $\Leftrightarrow$ $T$는 **isomorphism**^[동형사상]

**의미**: Invertible^[역사상 존재]

$$T^{-1}: W \to V \text{ exists and is also linear}$$

**정리**: Finite-dimensional spaces에서

$$T \text{ is isomorphism} \quad \Leftrightarrow \quad \ker(T) = \{0\} \text{ and } \dim(V) = \dim(W)$$

## Rank and Nullity

### Definitions

**Rank^[계수]**:

$$\text{rank}(T) = \dim(\text{Im}(T))$$

**Nullity^[퇴화차수]**:

$$\text{nullity}(T) = \dim(\ker(T))$$

### Rank-Nullity Theorem

**정리** (**Rank-Nullity Theorem**^[계수-퇴화차수 정리], 또는 **Fundamental Theorem of Linear Mappings**^[선형 사상의 기본 정리]):

$V$가 finite-dimensional^[유한차원] vector space이면

$$\dim(V) = \dim(\ker(T)) + \dim(\text{Im}(T))$$

$$\dim(V) = \text{nullity}(T) + \text{rank}(T)$$

**증명**:

$\{u_1, \ldots, u_k\}$를 $\ker(T)$의 basis라고 하자 ($k = \dim(\ker(T))$)

Extend to basis of $V$: $\{u_1, \ldots, u_k, v_1, \ldots, v_m\}$ where $k + m = \dim(V)$

**Claim**: $\{T(v_1), \ldots, T(v_m)\}$은 $\text{Im}(T)$의 basis

**(a) Spanning**: 임의의 $v \in V$는

$$v = \sum_{i=1}^k \alpha_i u_i + \sum_{j=1}^m \beta_j v_j$$

$$T(v) = \sum_{i=1}^k \alpha_i T(u_i) + \sum_{j=1}^m \beta_j T(v_j) = 0 + \sum_{j=1}^m \beta_j T(v_j)$$

따라서 $\text{Im}(T) = \text{span}\{T(v_1), \ldots, T(v_m)\}$ ✓

**(b) Linear independence**: Suppose

$$\sum_{j=1}^m \beta_j T(v_j) = 0$$

Then

$$T\left(\sum_{j=1}^m \beta_j v_j\right) = 0$$

따라서 $\sum_{j=1}^m \beta_j v_j \in \ker(T)$

$$\sum_{j=1}^m \beta_j v_j = \sum_{i=1}^k \alpha_i u_i$$

$$\sum_{j=1}^m \beta_j v_j - \sum_{i=1}^k \alpha_i u_i = 0$$

$\{u_1, \ldots, u_k, v_1, \ldots, v_m\}$이 linearly independent이므로

$$\beta_1 = \cdots = \beta_m = 0$$ ✓

따라서 $\dim(\text{Im}(T)) = m = \dim(V) - k = \dim(V) - \dim(\ker(T))$ ✓

**의미**:
- $\dim(V)$ = "입력 차원"
- $\dim(\ker(T))$ = "잃어버린 차원" (정보 손실)
- $\dim(\text{Im}(T))$ = "출력 차원" (보존된 차원)

### Applications of Rank-Nullity

**정리**: $T: V \to W$, $\dim(V) = \dim(W) = n$ (finite)

다음은 동치:

**(a)** $T$ is injective

**(b)** $T$ is surjective

**(c)** $T$ is bijective (isomorphism)

**증명**:

Rank-Nullity: $n = \text{nullity}(T) + \text{rank}(T)$

**(a) $\Rightarrow$ (b)**: Injective $\Rightarrow \ker(T) = \{0\} \Rightarrow \text{nullity}(T) = 0$

따라서 $\text{rank}(T) = n = \dim(W)$

즉, $\text{Im}(T) = W$ (surjective) ✓

**(b) $\Rightarrow$ (c)**: Surjective $\Rightarrow \text{rank}(T) = n$

따라서 $\text{nullity}(T) = 0 \Rightarrow \ker(T) = \{0\}$ (injective) ✓

**(c) $\Rightarrow$ (a)**: Obvious ✓

## Matrix Representation

### Coordinate Vectors

$V$의 basis $\mathcal{B} = \{v_1, \ldots, v_n\}$ 선택

$v = \sum_{i=1}^n \alpha_i v_i$의 **coordinate vector**^[좌표 벡터]:

$$[v]_{\mathcal{B}} = \begin{pmatrix} \alpha_1 \\ \vdots \\ \alpha_n \end{pmatrix} \in \mathbb{F}^n$$

### Matrix of Linear Mapping

$T: V \to W$, $\dim(V) = n$, $\dim(W) = m$

Bases: $\mathcal{B} = \{v_1, \ldots, v_n\}$ for $V$, $\mathcal{C} = \{w_1, \ldots, w_m\}$ for $W$

각 $T(v_j)$를 $\mathcal{C}$에 대해 표현:

$$T(v_j) = \sum_{i=1}^m a_{ij} w_i$$

**Matrix of $T$**:

$$[T]_{\mathcal{B}}^{\mathcal{C}} = \begin{pmatrix} a_{11} & \cdots & a_{1n} \\ \vdots & \ddots & \vdots \\ a_{m1} & \cdots & a_{mn} \end{pmatrix}$$

$j$-th column = $[T(v_j)]_{\mathcal{C}}$

**Fundamental relation**:

$$[T(v)]_{\mathcal{C}} = [T]_{\mathcal{B}}^{\mathcal{C}} [v]_{\mathcal{B}}$$

**의미**: Linear mapping $\leftrightarrow$ Matrix multiplication

### Properties of Matrix Representation

**(1)** $[S + T]_{\mathcal{B}}^{\mathcal{C}} = [S]_{\mathcal{B}}^{\mathcal{C}} + [T]_{\mathcal{B}}^{\mathcal{C}}$

**(2)** $[cT]_{\mathcal{B}}^{\mathcal{C}} = c[T]_{\mathcal{B}}^{\mathcal{C}}$

**(3)** $[S \circ T] = [S][T]$ (composition = matrix multiplication)

**(4)** $\text{rank}([T]) = \text{rank}(T)$ (matrix rank = transformation rank)

**(5)** $T$ invertible $\Leftrightarrow$ $[T]$ invertible

### Change of Basis

다른 bases $\mathcal{B}'$, $\mathcal{C}'$ 선택하면

$$[T]_{\mathcal{B}'}^{\mathcal{C}'} = P^{-1} [T]_{\mathcal{B}}^{\mathcal{C}} Q$$

where:
- $P$: change of basis matrix from $\mathcal{C}$ to $\mathcal{C}'$
- $Q$: change of basis matrix from $\mathcal{B}$ to $\mathcal{B}'$

**Linear operator** ($V = W$, $\mathcal{B} = \mathcal{C}$):

$$[T]_{\mathcal{B}'} = P^{-1} [T]_{\mathcal{B}} P$$

**Similar matrices**^[닮은 행렬]: 같은 linear operator의 다른 표현!

---

# <span class="header-examples">Examples</span>

## Example 1: Identity Map

$$I: V \to V, \quad I(v) = v$$

**확인**: $I(\alpha u + \beta v) = \alpha u + \beta v = \alpha I(u) + \beta I(v)$ ✓

**성질**:
- $\ker(I) = \{0\}$ (injective)
- $\text{Im}(I) = V$ (surjective)
- Isomorphism!

**Matrix**: $[I] = I_n$ (identity matrix)

## Example 2: Zero Map

$$0: V \to W, \quad 0(v) = 0_W$$

**확인**: $0(\alpha u + \beta v) = 0_W = \alpha \cdot 0_W + \beta \cdot 0_W$ ✓

**성질**:
- $\ker(0) = V$
- $\text{Im}(0) = \{0_W\}$
- $\text{rank}(0) = 0$

**Matrix**: $[0] = 0_{m \times n}$ (zero matrix)

## Example 3: Differential Operator

$$D: \mathcal{P}_n(\mathbb{R}) \to \mathcal{P}_{n-1}(\mathbb{R})$$

$$D(p) = p'$$

**확인**:

$$D(\alpha p + \beta q) = (\alpha p + \beta q)' = \alpha p' + \beta q' = \alpha D(p) + \beta D(q)$$ ✓

**성질**:
- $\ker(D) = \{c : c \in \mathbb{R}\}$ (constant polynomials)
- $\text{Im}(D) = \mathcal{P}_{n-1}(\mathbb{R})$ (surjective)
- $\text{nullity}(D) = 1$, $\text{rank}(D) = n$
- Rank-Nullity: $1 + n = n + 1 = \dim(\mathcal{P}_n)$ ✓

**Matrix** (basis $\{1, x, x^2, \ldots, x^n\}$):

$$[D] = \begin{pmatrix} 0 & 1 & 0 & 0 & \cdots & 0 \\ 0 & 0 & 2 & 0 & \cdots & 0 \\ 0 & 0 & 0 & 3 & \cdots & 0 \\ \vdots & \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & 0 & \cdots & n \end{pmatrix}$$

## Example 4: Integration Operator

$$I: C([0, 1]) \to \mathbb{R}$$

$$I(f) = \int_0^1 f(x) \, dx$$

**확인**:

$$I(\alpha f + \beta g) = \int_0^1 (\alpha f + \beta g) = \alpha \int_0^1 f + \beta \int_0^1 g = \alpha I(f) + \beta I(g)$$ ✓

**성질**:
- Linear functional! (scalar-valued)
- $\ker(I) = \left\{f : \int_0^1 f = 0\right\}$ (infinite-dimensional)
- Surjective: $I(1) = 1$, $I(0) = 0$

## Example 5: Matrix Multiplication

$$T_A: \mathbb{R}^n \to \mathbb{R}^m, \quad T_A(x) = Ax$$

where $A$ is $m \times n$ matrix

**확인**:

$$T_A(\alpha x + \beta y) = A(\alpha x + \beta y) = \alpha Ax + \beta Ay = \alpha T_A(x) + \beta T_A(y)$$ ✓

**성질**:
- $\ker(T_A) = \{x : Ax = 0\}$ (null space of $A$)
- $\text{Im}(T_A) = \{Ax : x \in \mathbb{R}^n\}$ (column space of $A$)
- $\text{rank}(T_A) = \text{rank}(A)$

**모든** finite-dimensional linear mapping은 이 형태!

## Example 6: Rotation in $\mathbb{R}^2$

$$R_\theta: \mathbb{R}^2 \to \mathbb{R}^2$$

$$R_\theta\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$$

**확인**: Matrix multiplication은 linear ✓

**성질**:
- $\ker(R_\theta) = \{0\}$ (injective)
- $\text{Im}(R_\theta) = \mathbb{R}^2$ (surjective)
- Isomorphism! (rotation preserves structure)
- $R_\theta^{-1} = R_{-\theta}$ (inverse = rotation by $-\theta$)

## Example 7: Projection onto Subspace

$W \subseteq V$ subspace, $V = W \oplus W^\perp$ (orthogonal decomposition)

$$P: V \to V, \quad P(w + w^\perp) = w$$

**확인**: Linearity from uniqueness of decomposition ✓

**성질**:
- $\ker(P) = W^\perp$
- $\text{Im}(P) = W$
- $P^2 = P$ (idempotent^[멱등])
- NOT injective (unless $W^\perp = \{0\}$)
- NOT surjective (unless $W = V$)

**예시**: Projection onto xy-plane in $\mathbb{R}^3$

$$P\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} x \\ y \\ 0 \end{pmatrix}$$

Matrix:

$$[P] = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}$$

## Example 8: Evaluation Functional

$$\text{ev}_a: \mathcal{P}_n(\mathbb{R}) \to \mathbb{R}$$

$$\text{ev}_a(p) = p(a)$$

**확인**:

$$\text{ev}_a(\alpha p + \beta q) = (\alpha p + \beta q)(a) = \alpha p(a) + \beta q(a) = \alpha \text{ev}_a(p) + \beta \text{ev}_a(q)$$ ✓

**성질**:
- Linear functional!
- $\ker(\text{ev}_a) = \{p : p(a) = 0\}$ = polynomials with root at $a$
- By Factor Theorem: $\ker(\text{ev}_a) = \{(x-a)q(x) : q \in \mathcal{P}_{n-1}\}$
- $\text{nullity}(\text{ev}_a) = n$, $\text{rank}(\text{ev}_a) = 1$

## Example 9: Trace

$$\text{tr}: M_n(\mathbb{F}) \to \mathbb{F}$$

$$\text{tr}(A) = \sum_{i=1}^n a_{ii}$$

**확인**:

$$\text{tr}(\alpha A + \beta B) = \sum_i (\alpha a_{ii} + \beta b_{ii}) = \alpha \text{tr}(A) + \beta \text{tr}(B)$$ ✓

**성질**:
- Linear functional on matrix space!
- $\ker(\text{tr}) = \{A : \text{tr}(A) = 0\}$ (traceless matrices)
- $\dim(\ker(\text{tr})) = n^2 - 1$
- $\text{tr}(AB) = \text{tr}(BA)$ (cyclic property)

## Example 10: Transpose

$$T: M_{m \times n}(\mathbb{F}) \to M_{n \times m}(\mathbb{F})$$

$$T(A) = A^T$$

**확인**:

$$(A + B)^T = A^T + B^T, \quad (cA)^T = cA^T$$ ✓

**성질**:
- $\ker(T) = \{0\}$ (injective)
- $\text{Im}(T) = M_{n \times m}$ (surjective)
- Isomorphism!
- $T^{-1} = T$ (self-inverse: $(A^T)^T = A$)

## Non-Examples

### Non-Example 1: Translation

$$T\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} x + 1 \\ y + 1 \end{pmatrix}$$

**Check**:

$$T(0) = \begin{pmatrix} 1 \\ 1 \end{pmatrix} \neq 0$$

**NOT linear!** ✗

**Rule**: 평행이동^[translation]은 linear가 아님!

### Non-Example 2: Norm

$$N: \mathbb{R}^n \to \mathbb{R}, \quad N(x) = \|x\|$$

**Check**:

$$N(2x) = \|2x\| = 2\|x\| = 2N(x)$$ ✓ (homogeneous)

But:

$$N(x + y) = \|x + y\| \leq \|x\| + \|y\| = N(x) + N(y)$$

Strict inequality possible! **NOT linear!** ✗

**Rule**: Norm은 linear가 아님 (subadditive only)

### Non-Example 3: Squaring

$$S: \mathbb{R} \to \mathbb{R}, \quad S(x) = x^2$$

**Check**:

$$S(x + y) = (x + y)^2 = x^2 + 2xy + y^2 \neq x^2 + y^2 = S(x) + S(y)$$

**NOT linear!** ✗

---

# <span class="header-theorem">Theorem</span>

## Existence and Uniqueness Theorem

**정리**: $V$, $W$ vector spaces, $\{v_1, \ldots, v_n\}$ basis of $V$

임의의 $w_1, \ldots, w_n \in W$에 대해, 다음을 만족하는 **유일한** linear mapping $T: V \to W$ 존재:

$$T(v_i) = w_i \quad \text{for } i = 1, \ldots, n$$

**증명**:

**Existence**: 임의의 $v \in V$는 유일하게 표현됨:

$$v = \sum_{i=1}^n \alpha_i v_i$$

Define:

$$T(v) = \sum_{i=1}^n \alpha_i w_i$$

Linearity 확인:

$$T\left(\sum_i \alpha_i v_i + \sum_i \beta_i v_i\right) = T\left(\sum_i (\alpha_i + \beta_i) v_i\right)$$

$$= \sum_i (\alpha_i + \beta_i) w_i = \sum_i \alpha_i w_i + \sum_i \beta_i w_i = T(v) + T(v')$$ ✓

**Uniqueness**: $S(v_i) = w_i = T(v_i)$인 다른 linear mapping $S$ 존재하면

$$S(v) = S\left(\sum_i \alpha_i v_i\right) = \sum_i \alpha_i S(v_i) = \sum_i \alpha_i w_i = T(v)$$

따라서 $S = T$ ✓

**의미**: Linear mapping은 **basis의 image로 완전히 결정!**

## Dimension Theorem for Isomorphism

**정리**: $V$, $W$ finite-dimensional vector spaces

$$V \cong W \quad \Leftrightarrow \quad \dim(V) = \dim(W)$$

**증명**:

**($\Rightarrow$)**: $T: V \to W$ isomorphism이면

Basis $\{v_1, \ldots, v_n\}$ of $V$에 대해

$\{T(v_1), \ldots, T(v_n)\}$은 $W$의 basis

따라서 $\dim(W) = n = \dim(V)$ ✓

**($\Leftarrow$)**: $\dim(V) = \dim(W) = n$

Bases: $\{v_1, \ldots, v_n\}$ for $V$, $\{w_1, \ldots, w_n\}$ for $W$

Existence theorem으로 $T(v_i) = w_i$ 정의

$T$ is bijection (basis to basis)

따라서 isomorphism ✓

**Corollary**: Finite-dimensional spaces는 차원으로 완전히 분류!

$$\mathbb{F}^n \cong V \text{ for any } n\text{-dimensional space } V$$

## First Isomorphism Theorem

**정리**: $T: V \to W$ linear mapping이면

$$V / \ker(T) \cong \text{Im}(T)$$

**증명**:

Define $\bar{T}: V/\ker(T) \to \text{Im}(T)$

$$\bar{T}(v + \ker(T)) = T(v)$$

**Well-defined**: $v + \ker(T) = v' + \ker(T) \Rightarrow v - v' \in \ker(T)$

$$\Rightarrow T(v - v') = 0 \Rightarrow T(v) = T(v')$$ ✓

**Linear**: Quotient structure preserves linearity ✓

**Injective**: $\bar{T}(v + \ker(T)) = 0 \Rightarrow T(v) = 0 \Rightarrow v \in \ker(T)$

$$\Rightarrow v + \ker(T) = \ker(T)$$ (zero of quotient) ✓

**Surjective**: By definition of $\text{Im}(T)$ ✓

따라서 isomorphism ✓

**의미**: $T$는 quotient space $V/\ker(T)$를 image로 "동형"하게 보냄

## Dual Space Dimension

**정리**: $V$ finite-dimensional이면

$$\dim(V^*) = \dim(V)$$

where $V^* = \mathcal{L}(V, \mathbb{F})$ (dual space)

**증명**: $\dim(\mathcal{L}(V, \mathbb{F})) = \dim(V) \cdot \dim(\mathbb{F}) = n \cdot 1 = n$ ✓

**의미**: $V \cong V^*$ (but NOT naturally!)

자세한 내용은 [[Dual Spaces]] 참조

## Composition and Invertibility

**정리**: $T: U \to V$, $S: V \to W$ linear

**(a)** If $S$, $T$ injective, then $S \circ T$ injective

**(b)** If $S$, $T$ surjective, then $S \circ T$ surjective

**(c)** If $S$, $T$ isomorphisms, then $S \circ T$ isomorphism

**(d)** $(S \circ T)^{-1} = T^{-1} \circ S^{-1}$

**증명**: Straightforward verification ✓

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### What is Linearity?

**Geometric intuition**:
- 직선을 직선으로 (no bending)
- 원점을 원점으로 (no translation)
- 평행선을 평행선으로 (preserves parallelism)
- 비율 보존 (preserves ratios)

**Algebraic intuition**:
- 구조 보존 (structure-preserving)
- 연산 교환 (commutes with operations)

$$T(\text{sum}) = \text{sum of } T$$
$$T(\text{scalar multiple}) = \text{scalar multiple of } T$$

### Why Study Linear Mappings?

**이유**:

**(1) Fundamental**: 가장 간단하고 중요한 함수 class

**(2) Approximation**: 많은 nonlinear functions를 locally linear로 근사
- Differential calculus: $f(x + h) \approx f(x) + Df(x) \cdot h$

**(3) Solvability**: Linear equations는 "해결 가능"
- System of linear equations: Gaussian elimination
- Linear ODEs: Closed-form solutions

**(4) Ubiquitous**: 수학, 물리, 공학 전반에 나타남

### Kernel and Image

**직관**:

**Kernel** = "정보 손실"
- $\ker(T)$의 모든 벡터는 0으로 "collapsing"
- $\dim(\ker(T))$ = 얼마나 많은 정보를 잃는가

**Image** = "도달 가능한 곳"
- $\text{Im}(T)$의 벡터들만 $T$의 output
- $\dim(\text{Im}(T))$ = 얼마나 많은 output 생성하는가

**Rank-Nullity**: Trade-off!

$$\text{input dimension} = \text{lost dimension} + \text{preserved dimension}$$

## Connection to Other Concepts

### 1. Group Homomorphisms

Linear mapping은 **group homomorphism**의 특수한 경우

$(V, +)$, $(W, +)$ abelian groups

$T: V \to W$ group homomorphism $\Leftrightarrow$ $T(v_1 + v_2) = T(v_1) + T(v_2)$

Linear mapping = group homomorphism + scalar multiplication 보존

자세한 내용은 [[Group Homomorphism]] 참조

### 2. Ring Homomorphisms

$T: R \to S$ ring homomorphism이면
- $T(a + b) = T(a) + T(b)$ (additive)
- $T(ab) = T(a)T(b)$ (multiplicative)

Linear mapping은 "additive" part만 (multiplication 없음)

### 3. Functors (Category Theory)

Linear mapping은 **functor** $\mathcal{L}: \mathbf{Vect} \to \mathbf{Vect}$

Objects: Vector spaces

Morphisms: Linear mappings

자세한 내용은 [[Category Theory]] 참조

### 4. Differential Calculus

**Derivative** = linear approximation

$$f(x + h) \approx f(x) + Df(x) \cdot h$$

$Df(x): \mathbb{R}^n \to \mathbb{R}^m$ is **linear mapping**!

**Jacobian matrix** = matrix representation of derivative

자세한 내용은 [[Differential Calculus]] 참조

### 5. Functional Analysis

Linear mappings on infinite-dimensional spaces

**Bounded linear operator**: $\|T(v)\| \leq C\|v\|$

**Compact operator**: Maps bounded sets to relatively compact sets

자세한 내용은 [[Functional Analysis]] 참조

## Matrix vs Linear Mapping

### Relationship

**Finite-dimensional**: One-to-one correspondence

$$\text{Linear mapping} \quad \leftrightarrow \quad \text{Matrix}$$

(after choosing bases)

**Infinite-dimensional**: Linear mappings ≠ matrices!
- Differential operator $D$
- Integration operator $I$

### Detailed Explanation: Finite vs Infinite Dimensional

#### Finite-Dimensional Case^[유한차원의 경우]

$V$, $W$가 finite-dimensional이고 $\dim(V) = n$, $\dim(W) = m$이면:

**모든 linear mapping $T: V \to W$는 $m \times n$ matrix로 완전히 표현 가능!**

**How it works**:

**(Step 1)** Basis 선택:
- $\mathcal{B} = \{v_1, \ldots, v_n\}$ for $V$
- $\mathcal{C} = \{w_1, \ldots, w_m\}$ for $W$

**(Step 2)** 각 basis vector $v_j$의 image 계산:

$$T(v_j) = a_{1j} w_1 + a_{2j} w_2 + \cdots + a_{mj} w_m$$

**(Step 3)** Matrix 구성:

$$[T]_{\mathcal{B}}^{\mathcal{C}} = \begin{pmatrix} | & | & & | \\ [T(v_1)]_{\mathcal{C}} & [T(v_2)]_{\mathcal{C}} & \cdots & [T(v_n)]_{\mathcal{C}} \\ | & | & & | \end{pmatrix} = \begin{pmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{pmatrix}$$

**(Step 4)** 계산:

$$[T(v)]_{\mathcal{C}} = [T]_{\mathcal{B}}^{\mathcal{C}} [v]_{\mathcal{B}}$$

**예시**: $T: \mathbb{R}^2 \to \mathbb{R}^2$, rotation by $\theta$

$$T\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} x\cos\theta - y\sin\theta \\ x\sin\theta + y\cos\theta \end{pmatrix}$$

Standard basis에서:

$$T(e_1) = \begin{pmatrix} \cos\theta \\ \sin\theta \end{pmatrix}, \quad T(e_2) = \begin{pmatrix} -\sin\theta \\ \cos\theta \end{pmatrix}$$

Matrix:

$$[T] = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$

**핵심**: 
- Basis의 image만 알면 $T$를 완전히 결정!
- Matrix multiplication으로 모든 계산 가능
- Computer로 numerical computation 가능

#### Infinite-Dimensional Case^[무한차원의 경우]

$V$가 infinite-dimensional이면:

**Linear mapping을 matrix로 표현할 수 없음!**

**Why?**
- Basis가 **무한개**
- Matrix가 "infinite × infinite" 크기 → well-defined 아님
- 대신 **함수 형태**로 표현

**예시 1: Differential Operator^[미분 연산자]**

$$D: C^\infty(\mathbb{R}) \to C^\infty(\mathbb{R})$$

$$D(f) = f'$$

**Linearity 확인**:

$$D(\alpha f + \beta g) = (\alpha f + \beta g)' = \alpha f' + \beta g' = \alpha D(f) + \beta D(g)$$ ✓

**구체적 예**:

$$D(\sin x) = \cos x$$
$$D(e^x) = e^x$$
$$D(x^n) = nx^{n-1}$$

**Matrix 표현?**

Basis $\{1, x, x^2, x^3, \ldots\}$를 사용하면:

$$D(1) = 0 = 0 \cdot 1 + 0 \cdot x + 0 \cdot x^2 + \cdots$$
$$D(x) = 1 = 1 \cdot 1 + 0 \cdot x + 0 \cdot x^2 + \cdots$$
$$D(x^2) = 2x = 0 \cdot 1 + 2 \cdot x + 0 \cdot x^2 + \cdots$$
$$D(x^3) = 3x^2 = 0 \cdot 1 + 0 \cdot x + 3 \cdot x^2 + \cdots$$

**"Infinite matrix"** (formal):

$$[D] = \begin{pmatrix} 0 & 1 & 0 & 0 & 0 & \cdots \\ 0 & 0 & 2 & 0 & 0 & \cdots \\ 0 & 0 & 0 & 3 & 0 & \cdots \\ 0 & 0 & 0 & 0 & 4 & \cdots \\ \vdots & \vdots & \vdots & \vdots & \vdots & \ddots \end{pmatrix}$$

하지만 이것은 **formal notation**일 뿐!
- 실제 matrix multiplication으로 계산 불가
- Infinite sum $\sum_{j=1}^\infty a_{ij} x_j$의 convergence 문제
- Computer에서 직접 다룰 수 없음

**대신 어떻게?** 함수로 직접 계산:

$$D(3x^2 + 5x + 2) = 6x + 5$$

**예시 2: Integration Operator^[적분 연산자]**

$$I: C([0, 1]) \to C([0, 1])$$

$$I(f)(x) = \int_0^x f(t) \, dt$$

**Linearity 확인**:

$$I(\alpha f + \beta g)(x) = \int_0^x (\alpha f(t) + \beta g(t)) \, dt = \alpha \int_0^x f(t) \, dt + \beta \int_0^x g(t) \, dt$$

$$= \alpha I(f)(x) + \beta I(g)(x)$$ ✓

**구체적 예**:

$$I(1)(x) = \int_0^x 1 \, dt = x$$
$$I(t)(x) = \int_0^x t \, dt = \frac{x^2}{2}$$
$$I(t^2)(x) = \int_0^x t^2 \, dt = \frac{x^3}{3}$$

**Matrix 표현?**

$C([0, 1])$는 infinite-dimensional이고, basis가 **uncountable**!
- 각 point $a \in [0, 1]$마다 delta function $\delta_a$
- Uncountable × uncountable "matrix" → 의미 없음!

**대신 어떻게?** Integral로 직접 계산:

$$I(\sin(\pi x))(x) = \int_0^x \sin(\pi t) \, dt = \frac{1 - \cos(\pi x)}{\pi}$$

**예시 3: Multiplication Operator^[곱셈 연산자]**

$$M_x: \mathcal{P}(\mathbb{R}) \to \mathcal{P}(\mathbb{R})$$

$$M_x(p)(t) = t \cdot p(t)$$

**Linearity**: Obvious from distributivity ✓

**구체적 예**:

$$M_x(1) = x$$
$$M_x(x) = x^2$$
$$M_x(x^2 + 3x + 2) = x^3 + 3x^2 + 2x$$

**"Infinite matrix"**:

Basis $\{1, x, x^2, x^3, \ldots\}$에서:

$$M_x(1) = x = 0 \cdot 1 + 1 \cdot x + 0 \cdot x^2 + \cdots$$
$$M_x(x) = x^2 = 0 \cdot 1 + 0 \cdot x + 1 \cdot x^2 + \cdots$$
$$M_x(x^2) = x^3 = 0 \cdot 1 + 0 \cdot x + 0 \cdot x^2 + 1 \cdot x^3 + \cdots$$

$$[M_x] = \begin{pmatrix} 0 & 0 & 0 & 0 & \cdots \\ 1 & 0 & 0 & 0 & \cdots \\ 0 & 1 & 0 & 0 & \cdots \\ 0 & 0 & 1 & 0 & \cdots \\ \vdots & \vdots & \vdots & \vdots & \ddots \end{pmatrix}$$

Again, formal notation only!

**예시 4: Shift Operator^[이동 연산자]**

$$S: \ell^2 \to \ell^2$$

$$(x_1, x_2, x_3, \ldots) \mapsto (0, x_1, x_2, x_3, \ldots)$$

**Linearity**: Component-wise ✓

**"Infinite matrix"**:

$$[S] = \begin{pmatrix} 0 & 0 & 0 & 0 & \cdots \\ 1 & 0 & 0 & 0 & \cdots \\ 0 & 1 & 0 & 0 & \cdots \\ 0 & 0 & 1 & 0 & \cdots \\ \vdots & \vdots & \vdots & \vdots & \ddots \end{pmatrix}$$

이 경우는 실제로 **well-defined**!
- $\ell^2$: square-summable sequences
- Infinite matrix-vector multiplication이 convergence 보장
- $\|S(x)\|_2 = \|x\|_2$ (isometry)

하지만 여전히 "finite matrix"와는 다름!

#### Comparison Table^[비교표]

| Aspect | Finite-Dimensional | Infinite-Dimensional |
|--------|-------------------|---------------------|
| **표현 방법** | Matrix $m \times n$ | 함수, 연산자, (formal infinite matrix) |
| **Basis** | 유한개: $n$개 | 무한개 또는 uncountable |
| **계산** | Matrix multiplication | Function evaluation, integrals, derivatives |
| **Storage** | $m \times n$ numbers | Function definition (rule) |
| **Computer** | Directly computable | Numerical methods (approximation) |
| **예시** | Rotation, projection | $D(f) = f'$, $I(f) = \int f$ |
| **이론** | Linear algebra | Functional analysis^[함수해석학] |
| **Convergence** | N/A (finite!) | Essential concern! |

#### Why This Distinction Matters^[왜 이 구분이 중요한가]

**Finite-dimensional의 장점**:
- **Computational**: Computer로 직접 계산
- **Concrete**: 숫자 $m \times n$개로 완전히 표현
- **Complete theory**: 모든 linear mapping = matrix
- **Algorithms**: Gaussian elimination, eigenvalue algorithms 등

**Finite-dimensional의 한계**:
- 함수 공간, 미분방정식 등 다룰 수 없음
- "Continuous" objects를 "discrete" matrix로 근사해야 함

**Infinite-dimensional의 장점**:
- **Natural**: 미분, 적분 등 자연스럽게 표현
- **Powerful**: Differential equations, Fourier analysis 등
- **Rich structure**: Topology, convergence, compactness 등

**Infinite-dimensional의 어려움**:
- **Abstract**: Matrix 같은 concrete representation 없음
- **Convergence issues**: Infinite sums, integrals
- **Computation**: Numerical approximation 필요
- **Theory complexity**: Functional analysis 필요

#### Practical Implications^[실용적 함의]

**예시: Solving Differential Equations**

**Finite**: System $Ax = b$
- Matrix $A$ 주어짐
- Gaussian elimination, LU decomposition
- Computer로 직접 풀이: `x = A \ b` (MATLAB)

**Infinite**: ODE $y' + p(t)y = q(t)$
- Differential operator $D + p(t)$
- Analytical methods: integrating factor, variation of parameters
- Numerical methods: Euler, Runge-Kutta (finite difference approximation)

**Connection**: Finite difference method
- $y'(t) \approx \frac{y(t+h) - y(t)}{h}$
- Approximate infinite-dimensional $D$ by finite-dimensional matrix!
- 예: $n \times n$ matrix for $n$ grid points

$$[D]_{\text{approx}} = \frac{1}{h} \begin{pmatrix} -1 & 1 & 0 & \cdots & 0 \\ 0 & -1 & 1 & \cdots & 0 \\ \vdots & \ddots & \ddots & \ddots & \vdots \\ 0 & \cdots & 0 & -1 & 1 \end{pmatrix}$$

**핵심**: Infinite-dimensional을 finite-dimensional로 **근사**!

#### Functional Analysis^[함수해석학]

Infinite-dimensional linear mappings를 엄밀하게 연구

**핵심 개념들**:

**(1) Bounded Operator^[유계 연산자]**:

$$\|T(v)\| \leq C \|v\| \quad \text{for some } C > 0, \forall v$$

"출력의 크기가 입력의 크기에 비례"

**예시**:
- $S: \ell^2 \to \ell^2$ shift operator: bounded ($C = 1$)
- $D: L^2 \to L^2$ differentiation: **unbounded**!

**(2) Compact Operator^[콤팩트 연산자]**:

Bounded sets를 relatively compact sets로 보냄

"Infinite-dimensional에서 finite-dimensional처럼 행동"

**예시**: Integral operators (Fredholm, Volterra)

**(3) Continuous vs Bounded**:

**정리** (Finite-dimensional):
- Linear $\Rightarrow$ Continuous $\Leftrightarrow$ Bounded

**정리** (Infinite-dimensional):
- Linear + Bounded $\Rightarrow$ Continuous
- Linear + Continuous $\Rightarrow$ Bounded
- But: Linear ≠ Continuous in general!

**예시**: Differentiation $D$ on $C^\infty$ with pointwise convergence: NOT continuous!

**(4) Spectrum^[스펙트럼]**:

Finite-dimensional: Eigenvalues $\{\lambda_1, \ldots, \lambda_n\}$ (discrete, finite)

Infinite-dimensional: Spectrum $\sigma(T)$ (can be continuous!)

**예시**: 
- Multiplication $M_x$ on $L^2([0, 1])$: $\sigma(M_x) = [0, 1]$ (continuous spectrum!)
- Compact operators: Discrete spectrum like finite-dimensional

자세한 내용은 [[Functional Analysis]], [[Spectral Theory]] 참조

### Coordinate-free vs Coordinate

**Linear mapping**: **Coordinate-free** (geometric object)
- Independent of basis choice
- Intrinsic to spaces $V$, $W$

**Matrix**: **Coordinate-dependent** (numerical representation)
- Depends on basis choice
- Different bases → different matrices (similar matrices)

**Philosophy**: Think geometrically (linear mappings), compute numerically (matrices)

## Common Misconceptions

### 1. "Linear" in Calculus vs Algebra

**Calculus "linear"**: $f(x) = mx + b$ (affine!)

**Algebra "linear"**: $T(x) = mx$ (no constant term!)

**교훈**: Algebra의 "linear"는 더 엄격! ($T(0) = 0$ 필수)

### 2. All Functions are Linear?

**실수**: "간단한" 함수는 linear일 것

**반례**: $f(x) = x^2$, $f(x) = \sin x$, $f(x) = e^x$ 모두 **NOT linear**!

**Test**: $f(2x) = 2f(x)$? $f(x + y) = f(x) + f(y)$?

### 3. Kernel = {0} Always?

**실수**: "좋은" linear mapping은 $\ker(T) = \{0\}$

**반례**: Projection은 유용하지만 kernel 큼!

**교훈**: $\ker(T) \neq \{0\}$도 중요한 mappings!

### 4. Matrix Determines Everything?

**주의**: Matrix는 **basis에 의존**!

Same linear mapping → different matrices (different bases)

**교훈**: Similar matrices = same linear mapping!

### 5. Dimension Preservation?

**실수**: Linear mapping은 차원 보존

**반례**: $T: \mathbb{R}^3 \to \mathbb{R}^2$, projection은 차원 감소!

**정확**: Isomorphism만 차원 보존

## Applications

### 1. Solving Linear Systems

$$Ax = b \quad \Leftrightarrow \quad T_A(x) = b$$

Linear algebra의 핵심 문제!

**Solvability**: $b \in \text{Im}(T_A)$?

**Uniqueness**: $\ker(T_A) = \{0\}$?

### 2. Computer Graphics

**Transformations**:
- Rotation, scaling, shearing: Linear!
- Translation: NOT linear (affine)

**Homogeneous coordinates**: Trick to make translation "linear"

### 3. Quantum Mechanics

**States**: Vectors in Hilbert space $\mathcal{H}$

**Observables**: Linear operators on $\mathcal{H}$

**Time evolution**: $|\psi(t)\rangle = U(t) |\psi(0)\rangle$ (unitary operator)

자세한 내용은 [[Quantum Mechanics]] 참조

### 4. Signal Processing

**Signals**: Vectors in function space

**Filters**: Linear operators
- Convolution: $(h * x)(t) = \int h(t - \tau) x(\tau) d\tau$

**Fourier transform**: Linear operator!

자세한 내용은 [[Signal Processing]] 참조

### 5. Machine Learning

**Neural networks**: Composition of linear + nonlinear

**Linear layers**: $y = Wx + b$ (affine transformation)

**Dimensionality reduction**: PCA (linear projection)

### 6. Differential Equations

**Linear ODEs**: $y' + p(t)y = q(t)$

**Solution space**: Vector space!

**Differential operator**: $L(y) = y' + p(t)y$ linear

### 7. Economics (Linear Models)

**Input-output models**: Leontief model

**Linear programming**: Optimization over linear constraints

## Historical Note

**19th century**: Linear algebra develops from linear equations

**1888**: Peano axiomatizes vector spaces

**Early 20th century**: Abstract linear algebra (Hilbert, Banach)

**1940s-50s**: Modern formulation (Bourbaki)

**Computer age**: Matrix computations, numerical linear algebra

**Modern**: Infinite-dimensional analysis (functional analysis, operator theory)

## 관련 개념

- [[Vector Space]]: Domain and codomain
- [[Subspace]]: Kernel and image are subspaces
- [[Linear Independence]]: Preserved by injective mappings
- [[Basis and Dimension]]: Determines mappings uniquely
- [[Dual Spaces]]: Linear functionals $V \to \mathbb{F}$
- [[Dual of a Linear Map]]: $T^*: W^* \to V^*$
- [[Double dual]]: $(V^*)^*$ and natural embedding
- [[Inner Product]]: Induces linear functionals
- [[Matrix]]: Finite-dimensional representation
- [[Eigenvalue, Eigen Vector]]: $T(v) = \lambda v$
- [[Diagonalization]]: Simplest matrix form
- [[Jordan Normal Form]]: Canonical form
- [[Singular Value Decomposition]]: Geometric decomposition
- [[Isomorphism]]: Bijective linear mapping
- [[Quotient Space]]: $V/\ker(T)$
- [[Direct Sum]]: $V \cong \ker(T) \oplus \text{complement}$

## 추가 학습 주제

**기초**:
- Definition and basic properties
- Kernel and image
- Injectivity, surjectivity, bijectivity
- Matrix representation
- Rank-Nullity Theorem

**중급**:
- Change of basis
- Similar matrices
- Dual spaces and dual mappings
- Quotient spaces
- Isomorphism theorems

**고급**:
- Spectral theory (eigenvalues, eigenvectors)
- Jordan canonical form
- Singular value decomposition
- Tensor products of linear mappings
- Functional analysis (bounded operators)
- Operator algebras
- Representation theory
