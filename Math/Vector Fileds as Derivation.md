# <span class="header-prerequisite">Prerequisite</span>
- [[Vector Field]]
- [[Linear mapping]]
- Manifolds^[다양체] (기초)
- Calculus^[미적분학]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Derivation^[미분 연산자]

Manifold $M$의 점 $p$에서 **derivation**^[미분 연산자]은 linear map $D_p: C^\infty(M) \rightarrow \mathbb{R}$로 다음을 만족:

### 1. Linearity^[선형성]

$$D_p(\alpha f + \beta g) = \alpha D_p(f) + \beta D_p(g)$$

for all $\alpha, \beta \in \mathbb{R}$, $f, g \in C^\infty(M)$.

### 2. Leibniz rule^[라이프니츠 법칙]

$$D_p(fg) = D_p(f) \cdot g(p) + f(p) \cdot D_p(g)$$

여기서 $D_p(f)$, $D_p(g)$는 실수이고, $f(p)$, $g(p)$는 점 $p$에서의 함수값(실수)이다.

**핵심**: Leibniz rule이 "미분"의 본질을 포착한다!

### Notation abuse^[표기법 남용]

흔히 $g(p)$를 그냥 $g$로 쓰기도 한다:
$$D_p(fg) = D_p(f) \cdot g + f \cdot D_p(g)$$

이 경우 $f$, $g$는 "점 p에서의 값"을 의미한다. Context에서 명확하면 이 표기를 사용.

## Vector field as derivation^[미분 연산자로서의 벡터장]

Vector field $X$는 두 가지 관점에서 볼 수 있다:

### Local (pointwise)^[국소적]

각 점 $p$에서 derivation:

$$X_p: C^\infty(M) \rightarrow \mathbb{R}$$
$$X_p(f) = \displaystyle\sum_{i=1}^n X^i(p) \frac{\partial f}{\partial x^i}(p)$$

여기서 $X_p(f)$는 **실수**이다 (점 $p$에서의 방향 도함수).

**Leibniz rule** (점 p에서):
$$X_p(fg) = X_p(f) \cdot g(p) + f(p) \cdot X_p(g)$$

### Global^[전역적]

함수를 함수로 보내는 연산자:

$$X: C^\infty(M) \rightarrow C^\infty(M)$$
$$(Xf)(p) = X_p(f)$$

이는 새로운 함수를 만든다: $Xf \in C^\infty(M)$.

**Leibniz rule** (전역):
$$X(fg) = X(f) \cdot g + f \cdot X(g)$$

여기서 곱셈은 pointwise (함수의 곱).

---

# <span class="header-properties">Fundamental Theorem</span>

## 대수-기하 대응^[Algebra-Geometry Correspondence]

점 $p \in M$에서:

$$T_p M \cong \{\text{Derivations at } p\}$$

**의미**: Tangent vectors와 derivations는 **같은 것**이다!

### 증명 스케치

**방향 1**: Tangent vector → Derivation

Curve $\gamma: (-\epsilon, \epsilon) \rightarrow M$, $\gamma(0) = p$, $\gamma'(0) = v$:

$$D_v(f) = \frac{d}{dt}\bigg|_{t=0} f(\gamma(t))$$

이는 derivation의 성질을 만족.

**방향 2**: Derivation → Tangent vector

좌표 $(x^1, \ldots, x^n)$에서, derivation $D$에 대해:

$$D = \displaystyle\sum_{i=1}^n D(x^i) \frac{\partial}{\partial x^i}\bigg|_p$$

따라서 $D$는 tangent vector이다.

**결론**: 두 공간은 자연스럽게 동형.

---

# <span class="header-remark">Why This Viewpoint?</span>

## 1. 좌표 독립성^[Coordinate Independence]

### 문제: 전통적 정의

$\mathbb{R}^n$에서 vector = $(v_1, \ldots, v_n)$ (화살표)

**한계**:
- 좌표계에 의존
- 다른 좌표계에서는 다른 성분
- Curved space에서는 의미 불명확

### 해결: Derivation 정의

함수 $f$에 작용하는 연산자:
- ✅ 함수는 좌표 무관
- ✅ 내재적 정의
- ✅ 모든 manifold에서 작동

## 2. 내재적 정의^[Intrinsic Definition]

### Embedding 없이 정의 가능

**전통적**: Manifold를 $\mathbb{R}^N$에 embedding
- "화살표"는 외부 공간 필요
- Manifold 구조만으로 불충분

**Derivation**: Manifold 자체만으로 정의
- Functions $C^\infty(M)$는 내재적
- 외부 공간 불필요

### 예: 구면 $S^2$

**나쁜 정의**: $S^2 \subset \mathbb{R}^3$의 tangent vectors
- $\mathbb{R}^3$ 필요

**좋은 정의**: Derivations on $C^\infty(S^2)$
- $S^2$만으로 정의됨

## 3. 자동 좌표 변환^[Automatic Coordinate Transformation]

좌표 변환 $(x^i) \to (y^j)$일 때:

**전통적 방법**: Chain rule을 수동으로 적용
$$\frac{\partial}{\partial x^i} = \displaystyle\sum_j \frac{\partial y^j}{\partial x^i} \frac{\partial}{\partial y^j}$$

**Derivation 방법**: 자동으로 올바르게 변환
$$\frac{\partial f}{\partial x^i} = \frac{\partial}{\partial x^i}(f)$$

함수 $f$는 좌표 무관하므로, derivation도 올바르게 변환됨.

---

# <span class="header-examples">Examples</span>

## 1. Directional derivative^[방향 도함수] in $\mathbb{R}^3$

점 $p = (x_0, y_0, z_0)$, 방향 $\mathbf{v} = (a, b, c)$:

### 전통적 정의

$$D_{\mathbf{v}}f = \lim_{h \to 0} \frac{f(p + h\mathbf{v}) - f(p)}{h}$$

### Derivation 정의

$$D_{\mathbf{v}}(f) = a \frac{\partial f}{\partial x}\bigg|_p + b \frac{\partial f}{\partial y}\bigg|_p + c \frac{\partial f}{\partial z}\bigg|_p$$

**같은 것**이다!

### Leibniz rule 확인

$f(x,y,z) = x^2y$, $g(x,y,z) = z$, $\mathbf{v} = (1, 0, 0)$:

$$D_{\mathbf{v}}(fg) = D_{\mathbf{v}}(x^2yz) = 2xyz$$

**Product rule**:
$$D_{\mathbf{v}}(f) \cdot g + f \cdot D_{\mathbf{v}}(g) = 2xy \cdot z + x^2y \cdot 0 = 2xyz$$

✓ 일치!

## 2. Coordinate vector fields^[좌표 벡터장]

좌표 $(x^1, \ldots, x^n)$에서:

$$\frac{\partial}{\partial x^i}: f \mapsto \frac{\partial f}{\partial x^i}$$

**명백히 derivation**:
- Linear: ✓
- Leibniz: $\frac{\partial(fg)}{\partial x^i} = \frac{\partial f}{\partial x^i} g + f \frac{\partial g}{\partial x^i}$ ✓

**Basis of tangent space**:
$$T_p M = \text{span}\left\{\frac{\partial}{\partial x^1}\bigg|_p, \ldots, \frac{\partial}{\partial x^n}\bigg|_p\right\}$$

## 3. Polar coordinates^[극좌표]

$\mathbb{R}^2 \setminus \{0\}$에서 $(r, \theta)$:

### Radial direction^[방사 방향]

$$\frac{\partial}{\partial r}(f) = \text{"$f$를 $r$ 방향으로 미분"}$$

Cartesian coordinates로 변환:
$$\frac{\partial}{\partial r} = \cos\theta \frac{\partial}{\partial x} + \sin\theta \frac{\partial}{\partial y}$$

**자동으로 나옴**!

### Angular direction^[각도 방향]

$$\frac{\partial}{\partial \theta}(f) = r\left(-\sin\theta \frac{\partial f}{\partial x} + \cos\theta \frac{\partial f}{\partial y}\right)$$

## 4. Sphere $S^2$

Spherical coordinates $(\theta, \phi)$:

$$\frac{\partial}{\partial \theta}, \quad \frac{\partial}{\partial \phi}$$

이들은 $S^2$에서 **내재적으로** 정의된 derivations.

$\mathbb{R}^3$에 embedding할 필요 없음!

---

# <span class="header-properties">Properties and Operations</span>

## Lie bracket as commutator^[교환자로서의 리 브래킷]

두 derivations $X, Y$의 **commutator**^[교환자]:

$$[X, Y](f) = X(Yf) - Y(Xf)$$

### $[X, Y]$도 derivation임을 확인

**Linearity**: 명백.

**Leibniz rule**:
$$[X, Y](fg) = X(Y(fg)) - Y(X(fg))$$

$Y(fg) = (Yf)g + f(Yg)$를 사용:

$$= X((Yf)g + f(Yg)) - Y((Xf)g + f(Xg))$$

전개하고 정리하면:

$$= [X, Y](f) \cdot g + f \cdot [X, Y](g)$$

✓ Leibniz rule 만족!

### Lie algebra 구조

Derivations의 공간은 Lie bracket으로 **Lie algebra**^[리 대수]를 이룬다:
1. Bilinearity
2. Antisymmetry: $[X, Y] = -[Y, X]$
3. Jacobi identity: $[X, [Y, Z]] + [Y, [Z, X]] + [Z, [X, Y]] = 0$

## Module structure^[가군 구조]

Vector fields $\mathfrak{X}(M)$는 $C^\infty(M)$-module:

$$(fX)(g) = f \cdot X(g)$$

**주의**: Leibniz rule의 변형:
$$(fX)(gh) = f \cdot X(gh) = f \cdot (X(g) \cdot h + g \cdot X(h))$$

## Lie derivative^[리 도함수]

Vector field $X$를 따라 함수를 미분:

$$\mathcal{L}_X f = Xf$$

**Interpretation**: Flow $\phi_t$ along $X$:

$$\mathcal{L}_X f = \frac{d}{dt}\bigg|_{t=0} (f \circ \phi_t)$$

---

# <span class="header-properties">Historical Context</span>

## 1950년대 이전: 화살표 관점

**기하학적 직관**:
- Vector = 화살표
- Tangent space = 점에서 접하는 평면
- 주로 $\mathbb{R}^n$ 또는 embedded manifolds

**한계**:
- 좌표 의존적
- Embedding 필요
- 일반화 어려움

## 1950년대 이후: 대수적 관점

**주요 인물**:
- **Claude Chevalley** (1946): Theory of Lie Groups
- **Jean-Louis Koszul** (1950): Connections
- **Élie Cartan**: Differential forms

**혁신**:
- Manifold를 독립적으로 정의
- Derivation으로 tangent vectors 정의
- **좌표 무관** 미분기하학 수립

## 현대적 정의

**Standard**: Tangent vector = Derivation

**교과서**:
- Lee, *Introduction to Smooth Manifolds*
- Spivak, *Calculus on Manifolds*
- Warner, *Foundations of Differentiable Manifolds*

---

# <span class="header-examples">Applications</span>

## 1. Physics^[물리학]

### Observables와 symmetries

**Quantum mechanics**:
- Functions $f \in C^\infty(M)$ = Observables (측정 가능량)
- Vector fields $X$ = Symmetry generators
- $Xf$ = "대칭성 $X$에 따라 $f$가 변하는 양"

### Hamiltonian mechanics^[해밀턴 역학]

Phase space $(q, p)$에서:
- Hamiltonian $H$ = 에너지 함수
- Hamiltonian vector field $X_H$
- $X_H(f)$ = Poisson bracket $\{H, f\}$

$$X_H(f) = \frac{\partial H}{\partial p} \frac{\partial f}{\partial q} - \frac{\partial H}{\partial q} \frac{\partial f}{\partial p}$$

## 2. Differential geometry^[미분기하학]

### Killing vector fields^[킬링 벡터장]

Riemannian metric $g$를 보존하는 vector field:

$$\mathcal{L}_X g = 0$$

**Interpretation**: Infinitesimal isometries (대칭성).

### Connections^[접속]

Covariant derivative $\nabla$ on vector fields:

$$\nabla: \mathfrak{X}(M) \times \mathfrak{X}(M) \rightarrow \mathfrak{X}(M)$$

Derivation 개념의 확장.

## 3. Lie theory^[리 이론]

### Lie groups와 Lie algebras

**Lie group** $G$의 **Lie algebra** $\mathfrak{g}$:

$$\mathfrak{g} = T_e G = \{\text{Left-invariant vector fields}\}$$

Derivations의 Lie bracket = Lie algebra 구조.

### Exponential map^[지수 사상]

Vector field $X$ → Flow $\phi_t$ → One-parameter subgroup

$$\exp(tX) = \phi_t(e)$$

---

# <span class="header-remark">Conceptual Advantages</span>

## 1. Duality with differential forms^[미분 형식과의 쌍대성]

**상세한 내용**: [[Differential Forms]]

- Vector fields = Derivations on functions
- 1-forms = Linear functionals on tangent vectors

**Natural pairing**^[자연스러운 쌍]:
$$\langle \omega, X \rangle = \omega(X) = X(\cdot) \in C^\infty(M)$$

이는 **dual spaces**^[쌍대 공간]의 관계:
$$T^*_p M = (T_p M)^*$$

## 2. Functoriality^[함자성]

Smooth map $F: M \rightarrow N$:

**Pullback of functions**^[함수의 당겨오기]:
$$F^*: C^\infty(N) \rightarrow C^\infty(M)$$
$$F^*g = g \circ F$$

**Pushforward of derivations**^[미분 연산자의 밀어내기]:

$F$ diffeomorphism일 때, derivation $D$ on $M$:
$$F_* D = D \circ F^*$$

**자연스럽게 정의됨**!

## 3. Algebraic clarity^[대수적 명확성]

Vector fields = Derivations → **Lie algebra**

명확한 대수 구조:
- Module over $C^\infty(M)$
- Lie algebra under bracket
- Can define cohomology, etc.

---

# <span class="header-examples">Common Misconceptions</span>

## Misconception 1: "Vector fields are just arrows"

**문제**: 이것은 $\mathbb{R}^n$에서만 명확.

**진실**: Vector fields는 **derivations** (coordinate-free).

## Misconception 2: "Tangent space is a subspace of $\mathbb{R}^n$"

**문제**: Embedding 필요.

**진실**: Tangent space = **space of derivations** (intrinsic).

## Misconception 3: "$\frac{\partial}{\partial x}$는 단지 표기법"

**문제**: 이것은 진짜 **연산자**이다!

**진실**: 
$$\frac{\partial}{\partial x}: C^\infty(M) \rightarrow C^\infty(M)$$

함수를 미분하는 derivation.

---

# <span class="header-examples">핵심 개념 요약</span>

## Vector Fields의 세 가지 관점

```
1. 기하학적 관점
   Vector field = 각 점에 화살표
   ↕
2. 대수적 관점 (Derivation)
   Vector field = 함수를 미분하는 연산자
   ↕
3. 미분방정식 관점
   Vector field = ODE를 정의하는 시스템
```

**Derivation 관점이 가장 근본적**!

## Derivation의 정의

| Property | Formula |
|----------|---------|
| **Linearity** | $D(\alpha f + \beta g) = \alpha D(f) + \beta D(g)$ |
| **Leibniz rule** | $D(fg) = D(f) \cdot g + f \cdot D(g)$ |

**핵심**: 이 두 조건이 "미분"을 특징짓는다!

## 주요 정리

$$T_p M \cong \{\text{Derivations at } p\}$$

**의미**: 기하학과 대수가 동일!

## 왜 이 관점인가?

| Advantage | Description |
|-----------|-------------|
| **좌표 독립성** | 함수는 좌표 무관 |
| **내재적** | 외부 공간 불필요 |
| **자동 변환** | 좌표 변환이 자연스럽게 처리됨 |
| **일반성** | 모든 manifold에 적용 |
| **대수 구조** | Lie algebra 등 명확한 구조 |

## 역사적 발전

**1950년대 이전**: Vector = 화살표 (기하학적)
**1950년대 이후**: Vector = Derivation (대수적)
**현대**: 두 관점의 통합

---

**기초 개념**: [[Vector Field]], [[Linear mapping]], [[Dual Spaces]]
**핵심 개념**: [[Derivation]]
**관련 개념**: [[Differential Forms]], [[Tensor]]
**응용**: Differential geometry, Lie theory, Physics (Hamiltonian mechanics)
**역사**: Chevalley, Koszul, Cartan

