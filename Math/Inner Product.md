# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- Vector spaces^[벡터 공간]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Inner product^[내적]

Vector space $V$ over field $\mathbb{F}$ ($\mathbb{R}$ 또는 $\mathbb{C}$)에서 **inner product**^[내적]은 함수:

$$\langle \cdot, \cdot \rangle: V \times V \rightarrow \mathbb{F}$$

다음을 만족:

### 1. Conjugate symmetry^[켤레 대칭]

$$\langle x, y \rangle = \overline{\langle y, x \rangle}$$

**실수 벡터 공간**에서는:
$$\langle x, y \rangle = \langle y, x \rangle \quad \text{(symmetry)}$$

### 2. Linearity in first argument^[첫 번째 인수에 대한 선형성]

$$\langle \alpha x + \beta y, z \rangle = \alpha \langle x, z \rangle + \beta \langle y, z \rangle$$

for all $\alpha, \beta \in \mathbb{F}$, $x, y, z \in V$.

### 3. Positive definiteness^[양의 정부호성]

$$\langle x, x \rangle \geq 0$$

등호는 $x = 0$일 때만 성립.

## Inner product space^[내적 공간]

Inner product가 주어진 vector space $(V, \langle \cdot, \cdot \rangle)$를 **inner product space**^[내적 공간]라 한다.

**주의**: 
- **Conjugate linear**^[켤레 선형] in second argument (복소수 공간):
$$\langle x, \alpha y + \beta z \rangle = \overline{\alpha} \langle x, y \rangle + \overline{\beta} \langle x, z \rangle$$

---

# <span class="header-properties">Properties</span>

## Induced norm^[유도 노름]

Inner product로부터 **norm**^[노름]을 정의:

$$\|x\| = \sqrt{\langle x, x \rangle}$$

### Norm properties^[노름 성질]

1. **Non-negativity**^[비음성]: $\|x\| \geq 0$
2. **Positive definiteness**^[양의 정부호성]: $\|x\| = 0 \Leftrightarrow x = 0$
3. **Homogeneity**^[동차성]: $\|\alpha x\| = |\alpha| \|x\|$
4. **Triangle inequality**^[삼각 부등식]: $\|x + y\| \leq \|x\| + \|y\|$

## Cauchy-Schwarz inequality^[코시-슈바르츠 부등식]

$$|\langle x, y \rangle| \leq \|x\| \cdot \|y\|$$

등호는 $x$, $y$가 linearly dependent^[선형 종속]일 때만 성립.

### Proof^[증명]

$y = 0$이면 명백. $y \neq 0$이라 가정.

임의의 $t \in \mathbb{R}$에 대해:

$$0 \leq \langle x - ty, x - ty \rangle = \|x\|^2 - 2t \text{Re}\langle x, y \rangle + t^2 \|y\|^2$$

$t = \frac{\text{Re}\langle x, y \rangle}{\|y\|^2}$를 선택:

$$0 \leq \|x\|^2 - \frac{(\text{Re}\langle x, y \rangle)^2}{\|y\|^2}$$

$$(\text{Re}\langle x, y \rangle)^2 \leq \|x\|^2 \|y\|^2$$

일반적으로 $|\langle x, y \rangle| \geq \text{Re}\langle x, y \rangle$이므로:

$$|\langle x, y \rangle|^2 \leq \|x\|^2 \|y\|^2$$

∎

## Parallelogram law^[평행사변형 법칙]

$$\|x + y\|^2 + \|x - y\|^2 = 2(\|x\|^2 + \|y\|^2)$$

**기하학적 의미**: 평행사변형의 대각선 길이 제곱의 합 = 변 길이 제곱의 합의 2배.

### Proof

$$\|x + y\|^2 = \langle x+y, x+y \rangle = \|x\|^2 + 2\text{Re}\langle x, y \rangle + \|y\|^2$$
$$\|x - y\|^2 = \langle x-y, x-y \rangle = \|x\|^2 - 2\text{Re}\langle x, y \rangle + \|y\|^2$$

더하면:
$$\|x + y\|^2 + \|x - y\|^2 = 2\|x\|^2 + 2\|y\|^2$$

∎

## Polarization identity^[극화 항등식]

Inner product를 norm으로부터 복원:

### 실수 공간

$$\langle x, y \rangle = \frac{1}{4}(\|x+y\|^2 - \|x-y\|^2)$$

### 복소수 공간

$$\langle x, y \rangle = \frac{1}{4}\sum_{k=0}^3 i^k \|x + i^k y\|^2$$

**의미**: Norm이 inner product로부터 오는지 확인 가능!

**역**: Norm이 parallelogram law를 만족 ⟺ inner product로부터 유도됨.

---

# <span class="header-examples">Examples</span>

## 1. Euclidean space^[유클리드 공간] $\mathbb{R}^n$

**Standard inner product**^[표준 내적]:

$$\langle x, y \rangle = \displaystyle\sum_{i=1}^n x_i y_i = x^T y$$

for $x = (x_1, \ldots, x_n)$, $y = (y_1, \ldots, y_n)$.

**Induced norm**:
$$\|x\| = \sqrt{x_1^2 + \cdots + x_n^2}$$

## 2. Complex Euclidean space $\mathbb{C}^n$

**Standard inner product**:

$$\langle x, y \rangle = \displaystyle\sum_{i=1}^n x_i \overline{y_i} = x^* y$$

여기서 $x^*$는 conjugate transpose^[켤레 전치].

**예**: $x = (1, i)$, $y = (2, 1)$:
$$\langle x, y \rangle = 1 \cdot 2 + i \cdot 1 = 2 + i$$

## 3. Function space $L^2([a, b])$

**Inner product**:

$$\langle f, g \rangle = \int_a^b f(x) \overline{g(x)} \, dx$$

**Induced norm**:
$$\|f\|_2 = \sqrt{\int_a^b |f(x)|^2 \, dx}$$

이는 **Hilbert space** $L^2$를 만든다.

**상세한 내용**: [[Hilbert Space]]

## 4. Sequence space $\ell^2$

$$\ell^2 = \left\{(a_n)_{n=1}^\infty : \displaystyle\sum_{n=1}^\infty |a_n|^2 < \infty\right\}$$

**Inner product**:

$$\langle (a_n), (b_n) \rangle = \displaystyle\sum_{n=1}^\infty a_n \overline{b_n}$$

**Induced norm**:
$$\|(a_n)\| = \sqrt{\displaystyle\sum_{n=1}^\infty |a_n|^2}$$

## 5. Matrix space

$M_{m \times n}(\mathbb{C})$에서:

### Frobenius inner product^[프로베니우스 내적]

$$\langle A, B \rangle = \text{tr}(A^* B) = \displaystyle\sum_{i,j} A_{ij} \overline{B_{ij}}$$

**Induced norm** (Frobenius norm):
$$\|A\|_F = \sqrt{\text{tr}(A^* A)} = \sqrt{\displaystyle\sum_{i,j} |A_{ij}|^2}$$

## 6. Weighted inner product^[가중 내적]

$\mathbb{R}^n$에서 positive definite matrix^[양의 정부호 행렬] $W$:

$$\langle x, y \rangle_W = x^T W y = \displaystyle\sum_{i,j} W_{ij} x_i y_j$$

**예**: Mahalanobis distance^[마할라노비스 거리]에 사용.

## 7. Polynomial space

$P_n[a, b]$ (차수 $\leq n$인 다항식):

$$\langle p, q \rangle = \int_a^b p(x) q(x) w(x) \, dx$$

여기서 $w(x) > 0$는 weight function^[가중 함수].

**예**: Legendre polynomials ($w(x) = 1$ on $[-1, 1]$).

---

# <span class="header-properties">Orthogonality</span>

## Orthogonal vectors^[직교 벡터]

$$x \perp y \Leftrightarrow \langle x, y \rangle = 0$$

### Pythagorean theorem^[피타고라스 정리]

$x \perp y$이면:

$$\|x + y\|^2 = \|x\|^2 + \|y\|^2$$

**Proof**:
$$\|x + y\|^2 = \langle x+y, x+y \rangle = \|x\|^2 + 2\text{Re}\langle x, y \rangle + \|y\|^2 = \|x\|^2 + \|y\|^2$$

(since $\langle x, y \rangle = 0$). ∎

## Orthonormal set^[정규직교 집합]

집합 $\{e_1, \ldots, e_n\}$이 **orthonormal**^[정규직교]이다 ⟺:

$$\langle e_i, e_j \rangle = \delta_{ij} = \begin{cases} 1 & i = j \\ 0 & i \neq j \end{cases}$$

### Orthonormal basis^[정규직교 기저]

Orthonormal set이 basis이면, 임의의 $x \in V$:

$$x = \displaystyle\sum_{i=1}^n \langle x, e_i \rangle e_i$$

**Fourier coefficients**^[푸리에 계수]: $c_i = \langle x, e_i \rangle$

### Parseval's identity^[파르스발 항등식]

Orthonormal basis $\{e_i\}$에 대해:

$$\|x\|^2 = \displaystyle\sum_i |\langle x, e_i \rangle|^2$$

## Gram-Schmidt process^[그람-슈미트 과정]

Linearly independent^[선형 독립] vectors $\{v_1, \ldots, v_n\}$을 orthonormal vectors $\{e_1, \ldots, e_n\}$로 변환:

### Algorithm^[알고리즘]

$$u_1 = v_1, \quad e_1 = \frac{u_1}{\|u_1\|}$$

$$u_k = v_k - \displaystyle\sum_{j=1}^{k-1} \langle v_k, e_j \rangle e_j, \quad e_k = \frac{u_k}{\|u_k\|}$$

**결과**: $\text{span}\{e_1, \ldots, e_k\} = \text{span}\{v_1, \ldots, v_k\}$

## Orthogonal complement^[직교 여공간]

Subspace $W \subseteq V$에 대해:

$$W^\perp = \{v \in V : \langle v, w \rangle = 0, \forall w \in W\}$$

### Properties^[성질]

1. $W^\perp$는 subspace
2. $W \cap W^\perp = \{0\}$
3. Finite dimension: $V = W \oplus W^\perp$ (직합)
4. $(W^\perp)^\perp = W$ (finite dimension)

---

# <span class="header-properties">Projections</span>

## Orthogonal projection^[직교 사영]

Closed subspace $W$와 $v \in V$에 대해, **orthogonal projection**^[직교 사영] $P_W(v) \in W$:

$$\|v - P_W(v)\| = \min_{w \in W} \|v - w\|$$

### Characterization^[특징]

$$P_W(v) = w \Leftrightarrow v - w \perp W$$

### Formula with orthonormal basis

$W$의 orthonormal basis $\{e_1, \ldots, e_k\}$:

$$P_W(v) = \displaystyle\sum_{i=1}^k \langle v, e_i \rangle e_i$$

## Best approximation^[최적 근사]

**정리**: $w^* = P_W(v)$는 $v$의 $W$에서의 unique best approximation:

$$\|v - w^*\| < \|v - w\| \quad \forall w \in W, w \neq w^*$$

**응용**: Least squares^[최소제곱법], regression^[회귀분석].

---

# <span class="header-properties">Angle and Distance</span>

## Angle^[각도]

Non-zero vectors $x, y$에 대해:

$$\cos \theta = \frac{\text{Re}\langle x, y \rangle}{\|x\| \|y\|}$$

또는 (실수 공간):

$$\cos \theta = \frac{\langle x, y \rangle}{\|x\| \|y\|}$$

**Cauchy-Schwarz**에 의해 $|\cos \theta| \leq 1$.

## Metric^[거리]

Inner product로부터 **metric**^[거리]을 유도:

$$d(x, y) = \|x - y\| = \sqrt{\langle x-y, x-y \rangle}$$

### Metric properties^[거리 성질]

1. $d(x, y) \geq 0$, 등호는 $x = y$일 때만
2. $d(x, y) = d(y, x)$ (symmetry)
3. $d(x, z) \leq d(x, y) + d(y, z)$ (triangle inequality)

따라서 inner product space는 **metric space**^[거리 공간]이다.

---

# <span class="header-properties">Relationship with Hilbert Spaces</span>

## Complete inner product space^[완비 내적 공간]

Inner product space $V$가 **complete**^[완비]이다 ⟺ 모든 Cauchy sequence가 수렴.

**정의**: Complete inner product space = **Hilbert space**^[힐베르트 공간].

**상세한 내용**: [[Hilbert Space]]

### Examples^[예시]

**Hilbert spaces** (complete):
- $\mathbb{R}^n$, $\mathbb{C}^n$ (finite dimensional)
- $L^2([a, b])$
- $\ell^2$

**Not Hilbert** (incomplete):
- $C([0, 1])$ with $L^2$ inner product (not complete)
- Polynomials with $L^2$ inner product

## Riesz representation theorem^[리스 표현 정리]

Hilbert space $H$에서, 모든 bounded linear functional^[유계 선형 범함수] $\phi: H \to \mathbb{F}$에 대해:

$$\exists! y \in H : \phi(x) = \langle x, y \rangle \quad \forall x \in H$$

**의미**: $(H^*)^* \cong H$ (antilinear isomorphism).

**상세한 내용**: [[Riesz Representation Theorem]]

---

# <span class="header-examples">Applications</span>

## 1. Least squares^[최소제곱법]

Overdetermined system $Ax = b$ (no exact solution):

**Minimize**: $\|Ax - b\|^2$

**Solution**: Normal equation^[정규 방정식]
$$A^T A x = A^T b$$

이는 $x$를 $\text{range}(A)$로의 orthogonal projection.

## 2. Fourier series^[푸리에 급수]

$L^2([-\pi, \pi])$에서 orthonormal basis:

$$\left\{\frac{1}{\sqrt{2\pi}}, \frac{\cos(nx)}{\sqrt{\pi}}, \frac{\sin(nx)}{\sqrt{\pi}} : n \geq 1\right\}$$

함수 $f$:
$$f(x) = \frac{a_0}{2} + \displaystyle\sum_{n=1}^\infty (a_n \cos(nx) + b_n \sin(nx))$$

Coefficients:
$$a_n = \langle f, \cos(nx) \rangle, \quad b_n = \langle f, \sin(nx) \rangle$$

## 3. Quantum mechanics^[양자역학]

**State space**: Hilbert space $\mathcal{H}$
**States**: Vectors $|\psi\rangle \in \mathcal{H}$
**Observables**: Self-adjoint operators
**Probability**: $|\langle \phi, \psi \rangle|^2$

**Dirac notation**^[디랙 표기법]:
- Ket: $|\psi\rangle$ (vector)
- Bra: $\langle \phi|$ (dual vector)
- Inner product: $\langle \phi | \psi \rangle$

## 4. Signal processing^[신호 처리]

**Correlation**^[상관]:
$$\text{corr}(f, g) = \frac{\langle f, g \rangle}{\|f\| \|g\|}$$

**Energy**: $E = \|f\|^2$

**Orthogonal decomposition**: Filters, wavelets

## 5. Machine learning^[기계 학습]

### Kernel methods^[커널 방법]

Kernel $K(x, y) = \langle \phi(x), \phi(y) \rangle$

Feature map $\phi: X \to H$ (Hilbert space).

**Support Vector Machines (SVM)**: Use inner products in feature space.

### Principal Component Analysis (PCA)

Orthogonal projection onto principal directions.

## 6. Optimization^[최적화]

### Gradient descent^[경사 하강법]

Update direction = negative gradient (steepest descent in $L^2$).

Inner product determines "steepest" direction.

---

# <span class="header-remark">Remark</span>

## Why inner products?^[왜 내적인가?]

Inner product는 다음을 제공:
1. **Norm** (크기): $\|x\|$
2. **Angle** (방향): $\cos \theta$
3. **Orthogonality** (직교성): $\langle x, y \rangle = 0$
4. **Projection** (사영): Best approximation

**기하학**과 **대수**의 연결!

## Not all norms come from inner products

**예**: $\ell^p$ norms ($p \neq 2$)
$$\|x\|_p = \left(\displaystyle\sum_i |x_i|^p\right)^{1/p}$$

**Test**: Parallelogram law 확인
- $p = 2$: ✓ (comes from inner product)
- $p \neq 2$: ✗ (no inner product)

## Finite vs infinite dimensional

### Finite dimensional

- All norms equivalent
- Orthonormal basis always exists
- Closed subspaces have orthogonal complement
- Complete (no need for Cauchy sequences)

### Infinite dimensional

- Different norms not equivalent
- Completeness matters → Hilbert space
- Orthonormal basis may be infinite (countable)
- Functional analysis needed

## Sesquilinear form^[반쌍선형 형식]

More general: **sesquilinear form**^[반쌍선형 형식]
- Linear in first argument
- Conjugate linear in second
- May not be positive definite

**Inner product** = positive definite sesquilinear form.

---

# <span class="header-examples">핵심 개념 요약</span>

## Inner product의 정의

| Property | Formula |
|----------|---------|
| **Conjugate symmetry** | $\langle x, y \rangle = \overline{\langle y, x \rangle}$ |
| **Linearity** | $\langle \alpha x + \beta y, z \rangle = \alpha \langle x, z \rangle + \beta \langle y, z \rangle$ |
| **Positive definiteness** | $\langle x, x \rangle > 0$ if $x \neq 0$ |

## Induced structures^[유도 구조]

$$\text{Inner product } \langle \cdot, \cdot \rangle$$
$$\Downarrow$$
$$\text{Norm } \|x\| = \sqrt{\langle x, x \rangle}$$
$$\Downarrow$$
$$\text{Metric } d(x,y) = \|x - y\|$$

## Key inequalities^[핵심 부등식]

| Inequality | Formula |
|------------|---------|
| **Cauchy-Schwarz** | $\|\langle x, y \rangle\| \leq \|x\| \cdot \|y\|$ |
| **Triangle inequality** | $\|x + y\| \leq \|x\| + \|y\|$ |
| **Parallelogram law** | $\|x+y\|^2 + \|x-y\|^2 = 2(\|x\|^2 + \|y\|^2)$ |

## Orthogonality^[직교성]

$$x \perp y \Leftrightarrow \langle x, y \rangle = 0$$

**Consequences**:
- Pythagorean theorem
- Orthogonal projection
- Best approximation

## Examples^[예시]

| Space | Inner product |
|-------|---------------|
| $\mathbb{R}^n$ | $\langle x, y \rangle = \sum x_i y_i$ |
| $\mathbb{C}^n$ | $\langle x, y \rangle = \sum x_i \overline{y_i}$ |
| $L^2$ | $\langle f, g \rangle = \int f(x) \overline{g(x)} \, dx$ |
| $\ell^2$ | $\langle (a_n), (b_n) \rangle = \sum a_n \overline{b_n}$ |

## Connection to Hilbert spaces

$$\boxed{\text{Inner product space} + \text{Complete} = \text{Hilbert space}}$$

**상세한 내용**: [[Hilbert Space]], [[Riesz Representation Theorem]]

---

**기초 개념**: [[Linear mapping]], Vector spaces
**관련 개념**: [[Hilbert Space]], [[Riesz Representation Theorem]], [[Dual Spaces]]
**응용**: Fourier analysis, Quantum mechanics, Signal processing, Machine learning
**핵심 부등식**: Cauchy-Schwarz inequality

