# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Dual Spaces]]
- Manifolds^[다양체] (기초)
- Calculus^[미적분학]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Vector field^[벡터장]

Manifold^[다양체] $M$에서의 **vector field**^[벡터장] $X$는 각 점 $p \in M$에 tangent vector^[접벡터] $X_p \in T_p M$을 대응시키는 함수이다:

$$X: M \rightarrow TM$$
$$X: p \mapsto X_p \in T_p M$$

여기서 $TM = \bigcup_{p \in M} T_p M$은 **tangent bundle**^[접다발]이다.

### Smooth vector field^[매끄러운 벡터장]

Vector field $X$가 **smooth**^[매끄러운]이다 $\Leftrightarrow$ 좌표계에서 모든 성분 함수가 smooth function^[매끄러운 함수]이다.

### Space of vector fields^[벡터장의 공간]

$\mathfrak{X}(M)$ 또는 $\Gamma(TM)$는 $M$ 위의 모든 smooth vector fields의 집합을 나타낸다.

이는:
- Vector space^[벡터 공간] (pointwise addition and scalar multiplication)
- Module^[가군] over $C^\infty(M)$ (smooth functions)

## Coordinate representation^[좌표 표현]

좌표계 $(x^1, \ldots, x^n)$에서, vector field $X$는:

$$X = \displaystyle\sum_{i=1}^n X^i \frac{\partial}{\partial x^i}$$

여기서:
- $X^i: M \rightarrow \mathbb{R}$는 **component functions**^[성분 함수]
- $\frac{\partial}{\partial x^i}$는 **coordinate vector fields**^[좌표 벡터장] (basis)

점 $p$에서:

$$X_p = \displaystyle\sum_{i=1}^n X^i(p) \left.\frac{\partial}{\partial x^i}\right|_p$$

---

# <span class="header-properties">Properties</span>

## Vector fields as derivations^[미분으로서의 벡터장]

Vector field $X$는 functions에 작용하는 **derivation**^[미분 연산자]으로 볼 수 있다:

$$X: C^\infty(M) \rightarrow C^\infty(M)$$

함수 $f: M \rightarrow \mathbb{R}$에 대해:

$$(Xf)(p) = X_p(f) = \sum_{i=1}^n X^i(p) \frac{\partial f}{\partial x^i}(p)$$

### Derivation properties^[미분 성질]

1. **Linearity**^[선형성]: $X(\alpha f + \beta g) = \alpha Xf + \beta Xg$
2. **Leibniz rule**^[라이프니츠 법칙]: $X(fg) = (Xf)g + f(Xg)$

**역으로**: 이 두 성질을 만족하는 모든 연산자는 vector field로부터 온다!

## Lie bracket^[리 브래킷]

두 vector fields $X, Y$의 **Lie bracket**^[리 브래킷] $[X, Y]$는 새로운 vector field:

$$[X, Y]f = X(Yf) - Y(Xf)$$

### Properties^[성질]

1. **Bilinearity**^[쌍선형성]: $[aX + bY, Z] = a[X, Z] + b[Y, Z]$
2. **Antisymmetry**^[반대칭성]: $[X, Y] = -[Y, X]$
3. **Jacobi identity**^[야코비 항등식]: $[X, [Y, Z]] + [Y, [Z, X]] + [Z, [X, Y]] = 0$

이 세 성질로 $\mathfrak{X}(M)$는 **Lie algebra**^[리 대수]를 이룬다.

### Coordinate formula^[좌표 공식]

$$[X, Y]^k = \displaystyle\sum_{i=1}^n \left(X^i \frac{\partial Y^k}{\partial x^i} - Y^i \frac{\partial X^k}{\partial x^i}\right)$$

## Flow and integral curves^[흐름과 적분 곡선]

Vector field $X$는 **ordinary differential equation**^[상미분방정식]을 정의한다:

$$\frac{d\gamma}{dt}(t) = X_{\gamma(t)}$$

### Integral curve^[적분 곡선]

초기 조건 $\gamma(0) = p$를 만족하는 curve $\gamma: I \rightarrow M$를 $X$의 **integral curve**^[적분 곡선]이라 한다.

### Flow^[흐름]

Vector field $X$의 **flow**^[흐름] $\phi_t: M \rightarrow M$는:

$$\phi_t(p) = \gamma_p(t)$$

여기서 $\gamma_p$는 $p$를 지나는 integral curve.

**Properties**:
- $\phi_0 = \text{id}_M$ (identity)
- $\phi_{t+s} = \phi_t \circ \phi_s$ (group property)
- $\frac{d}{dt}\bigg|_{t=0} \phi_t(p) = X_p$

---

# <span class="header-examples">Examples</span>

## 1. $\mathbb{R}^n$에서의 vector fields

### Standard basis vector fields

$$\frac{\partial}{\partial x^i} = (0, \ldots, 0, 1, 0, \ldots, 0)$$

$i$-th component만 1.

### General vector field

$$X = (X^1(x_1, \ldots, x_n), \ldots, X^n(x_1, \ldots, x_n))$$

## 2. $\mathbb{R}^3$에서의 vector fields

### Constant vector field^[상수 벡터장]

$$X = (a, b, c)$$

모든 점에서 같은 벡터.

**Integral curves**: Straight lines in direction $(a, b, c)$.

### Radial field^[방사형 장]

$$X = (x, y, z)$$

원점으로부터 방사.

**Integral curves**: Rays from origin, $\gamma(t) = e^t (x_0, y_0, z_0)$.

### Rotation field^[회전장]

$$X = (-y, x, 0)$$

$z$-axis 주위로 회전.

**Integral curves**: Circles around $z$-axis.

### Gradient field^[기울기장]

함수 $f: \mathbb{R}^3 \rightarrow \mathbb{R}$에 대해:

$$\nabla f = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z}\right)$$

**Property**: Conservative^[보존적] (curl-free^[회전 없음]).

## 3. Sphere $S^2$에서의 vector fields

### Tangent to latitude circles

$$X = \frac{\partial}{\partial \phi}$$

(spherical coordinates에서)

### Hairy ball theorem^[털 달린 공 정리]

$S^2$ 위에 **nowhere vanishing**^[어디서도 사라지지 않는] continuous vector field는 존재하지 않는다.

**Intuition**: "You can't comb a hairy ball smooth."

## 4. Phase space^[위상 공간] in dynamics

Hamiltonian system에서 **Hamiltonian vector field**^[해밀턴 벡터장]:

$$X_H = \left(\frac{\partial H}{\partial p}, -\frac{\partial H}{\partial q}\right)$$

**Integral curves**: Trajectories of system.

---

# <span class="header-properties">Vector Calculus Operations</span>

$\mathbb{R}^3$에서의 중요한 연산들.

## Gradient^[기울기]

Scalar field $f: \mathbb{R}^3 \rightarrow \mathbb{R}$에 대해:

$$\nabla f = \left(\frac{\partial f}{\partial x}, \frac{\partial f}{\partial y}, \frac{\partial f}{\partial z}\right)$$

**Interpretation**: Direction of steepest ascent^[최대 상승 방향].

**Magnitude**: Rate of change in that direction.

## Divergence^[발산]

Vector field $\mathbf{F} = (F_1, F_2, F_3)$에 대해:

$$\nabla \cdot \mathbf{F} = \frac{\partial F_1}{\partial x} + \frac{\partial F_2}{\partial y} + \frac{\partial F_3}{\partial z}$$

**Interpretation**: "Source density"^[원천 밀도] - 얼마나 많은 "stuff"가 나오는가.

**Positive**: Source (expanding)
**Negative**: Sink (contracting)
**Zero**: Divergence-free^[발산 없음] (incompressible flow^[비압축성 흐름])

## Curl^[회전]

Vector field $\mathbf{F} = (F_1, F_2, F_3)$에 대해:

$$\nabla \times \mathbf{F} = \left(\frac{\partial F_3}{\partial y} - \frac{\partial F_2}{\partial z}, \frac{\partial F_1}{\partial z} - \frac{\partial F_3}{\partial x}, \frac{\partial F_2}{\partial x} - \frac{\partial F_1}{\partial y}\right)$$

**Interpretation**: "Rotation density"^[회전 밀도] - 얼마나 회전하는가.

**Magnitude**: Strength of rotation
**Direction**: Axis of rotation (right-hand rule)
**Zero**: Curl-free^[회전 없음] (irrotational^[비회전], conservative^[보존적])

## Laplacian^[라플라시안]

Scalar field $f$에 대해:

$$\Delta f = \nabla \cdot (\nabla f) = \frac{\partial^2 f}{\partial x^2} + \frac{\partial^2 f}{\partial y^2} + \frac{\partial^2 f}{\partial z^2}$$

Vector field $\mathbf{F}$에 대해:

$$\Delta \mathbf{F} = \nabla(\nabla \cdot \mathbf{F}) - \nabla \times (\nabla \times \mathbf{F})$$

(in $\mathbb{R}^3$ with Euclidean metric)

---

# <span class="header-properties">Important Identities</span>

## Curl of gradient is zero^[기울기의 회전은 0]

$$\nabla \times (\nabla f) = 0$$

**Consequence**: Gradient fields are curl-free^[회전 없음] (conservative^[보존적]).

**Converse** (Poincaré lemma): Simply connected domain에서, curl-free → gradient.

## Divergence of curl is zero^[회전의 발산은 0]

$$\nabla \cdot (\nabla \times \mathbf{F}) = 0$$

**Consequence**: Curl fields are divergence-free^[발산 없음] (solenoidal^[솔레노이드]).

**Converse**: Contractible domain에서, divergence-free → curl.

## Product rules^[곱셈 규칙]

### Gradient

$$\nabla(fg) = f \nabla g + g \nabla f$$

### Divergence

$$\nabla \cdot (f \mathbf{F}) = (\nabla f) \cdot \mathbf{F} + f (\nabla \cdot \mathbf{F})$$

### Curl

$$\nabla \times (f \mathbf{F}) = (\nabla f) \times \mathbf{F} + f (\nabla \times \mathbf{F})$$

## Second-order identities

$$\nabla \times (\nabla \times \mathbf{F}) = \nabla(\nabla \cdot \mathbf{F}) - \Delta \mathbf{F}$$

---

# <span class="header-properties">Relationship with Differential Forms</span>

**상세한 내용**: [[Differential Forms]]

$\mathbb{R}^3$에서 Riemannian metric이 있을 때, vector fields와 differential forms 사이의 대응:

## Musical isomorphism^[음악적 동형사상]

### Flat (♭): Vector field → 1-form

Vector field $\mathbf{F} = (F_1, F_2, F_3)$ → 1-form:

$$\mathbf{F}^\flat = F_1 \, dx + F_2 \, dy + F_3 \, dz$$

### Sharp (♯): 1-form → Vector field

1-form $\omega = P \, dx + Q \, dy + R \, dz$ → vector field:

$$\omega^\sharp = (P, Q, R)$$

## Hodge star^[호지 스타]

Vector field $\mathbf{F}$ → 2-form (via Hodge star):

$$\star \mathbf{F}^\flat = F_1 \, dy \wedge dz + F_2 \, dz \wedge dx + F_3 \, dx \wedge dy$$

## Correspondence table^[대응표]

| Vector calculus | Differential forms |
|-----------------|-------------------|
| Scalar field $f$ | 0-form $f$ |
| Vector field $\mathbf{F}$ | 1-form $\mathbf{F}^\flat$ |
| Vector field $\mathbf{F}$ | 2-form $\star \mathbf{F}^\flat$ |
| Scalar field $f$ | 3-form $f \, dx \wedge dy \wedge dz$ |
| $\nabla f$ | $df$ |
| $\nabla \times \mathbf{F}$ | $d(\mathbf{F}^\flat)$ (as 2-form) |
| $\nabla \cdot \mathbf{F}$ | $d(\star \mathbf{F}^\flat)$ (as 3-form) |

**Key insight**: Exterior derivative $d$ unifies gradient, curl, and divergence!

---

# <span class="header-properties">Lie Derivative</span>

## Lie derivative of functions^[함수의 리 도함수]

Vector field $X$와 function $f$:

$$\mathcal{L}_X f = Xf = \displaystyle\sum_i X^i \frac{\partial f}{\partial x^i}$$

**Interpretation**: Rate of change of $f$ along flow of $X$.

## Lie derivative of vector fields^[벡터장의 리 도함수]

Vector fields $X, Y$:

$$\mathcal{L}_X Y = [X, Y]$$

**Interpretation**: How $Y$ changes along flow of $X$.

## Properties^[성질]

1. **Linearity**: $\mathcal{L}_X(\alpha Y + \beta Z) = \alpha \mathcal{L}_X Y + \beta \mathcal{L}_X Z$
2. **Leibniz**: $\mathcal{L}_X(fY) = (\mathcal{L}_X f) Y + f \mathcal{L}_X Y$
3. **Commutation**: $\mathcal{L}_{[X,Y]} = [\mathcal{L}_X, \mathcal{L}_Y]$

## Cartan's formula^[카르탕 공식]

For differential forms:

$$\mathcal{L}_X = d \circ i_X + i_X \circ d$$

여기서 $i_X$는 interior product^[내부곱] (contraction^[축약]).

---

# <span class="header-examples">Applications</span>

## 1. Physics^[물리학]

### Velocity field^[속도장]

Fluid flow: $\mathbf{v}(\mathbf{x}, t)$ gives velocity at each point.

**Continuity equation**^[연속 방정식]:

$$\frac{\partial \rho}{\partial t} + \nabla \cdot (\rho \mathbf{v}) = 0$$

### Electric field^[전기장]

$$\mathbf{E} = -\nabla \phi - \frac{\partial \mathbf{A}}{\partial t}$$

**Gauss's law**^[가우스 법칙]:

$$\nabla \cdot \mathbf{E} = \frac{\rho}{\epsilon_0}$$

### Magnetic field^[자기장]

$$\nabla \cdot \mathbf{B} = 0 \quad \text{(no magnetic monopoles)}$$

$$\nabla \times \mathbf{E} = -\frac{\partial \mathbf{B}}{\partial t} \quad \text{(Faraday's law)}$$

## 2. Dynamical systems^[역학계]

### Autonomous ODE^[자율 상미분방정식]

$$\frac{dx}{dt} = X(x)$$

$X$는 phase space^[위상 공간]의 vector field.

**Fixed points**^[고정점]: $X(x_0) = 0$

**Stability**^[안정성]: Linearization at fixed points.

### Hamiltonian mechanics^[해밀턴 역학]

Phase space $(q, p)$에서:

$$\frac{dq}{dt} = \frac{\partial H}{\partial p}, \quad \frac{dp}{dt} = -\frac{\partial H}{\partial q}$$

Hamiltonian vector field preserves symplectic structure^[심플렉틱 구조].

## 3. Differential geometry^[미분기하학]

### Killing vector fields^[킬링 벡터장]

Riemannian metric을 preserve:

$$\mathcal{L}_X g = 0$$

**Interpretation**: Infinitesimal isometries^[무한소 등거리 변환] (symmetries).

### Geodesic flow^[측지선 흐름]

Geodesic equation을 정의하는 vector field on tangent bundle.

## 4. Control theory^[제어 이론]

### Control system

$$\frac{dx}{dt} = f(x) + \displaystyle\sum_i u_i(t) g_i(x)$$

$f, g_i$는 vector fields, $u_i$는 controls.

**Controllability**: Lie bracket 조건.

## 5. Topology^[위상수학]

### Poincaré-Hopf theorem^[푸앵카레-호프 정리]

Compact oriented manifold $M$과 vector field $X$ (finitely many zeros):

$$\displaystyle\sum_{\text{zeros } p} \text{index}(X, p) = \chi(M)$$

(Euler characteristic^[오일러 지표])

---

# <span class="header-remark">Remark</span>

## Vector fields vs tangent vectors^[벡터장 vs 접벡터]

- **Tangent vector**^[접벡터]: 한 점에서의 벡터 $v \in T_p M$
- **Vector field**^[벡터장]: 모든 점에 벡터를 대응 $X: M \rightarrow TM$

**Analogy**: Function value vs function.

## Coordinate independence^[좌표 무관성]

Vector fields are **intrinsic**^[내재적] objects:
- Definition doesn't depend on coordinates
- Transformation law under coordinate change

좌표 변환 $(x^i) \to (y^j)$:

$$\frac{\partial}{\partial x^i} = \displaystyle\sum_j \frac{\partial y^j}{\partial x^i} \frac{\partial}{\partial y^j}$$

## Commuting vector fields^[가환 벡터장]

$[X, Y] = 0 \Leftrightarrow$ flows commute: $\phi^X_t \circ \phi^Y_s = \phi^Y_s \circ \phi^X_t$

**Frobenius theorem**^[프로베니우스 정리]: Commuting vector fields → integrable distribution^[적분 가능 분포] → foliation^[엽층 구조].

## Pushforward and pullback^[밀어내기와 당겨오기]

Smooth map $F: M \rightarrow N$:

### Pushforward^[밀어내기]

$$F_* X: N \rightarrow TN$$

(when $F$ is diffeomorphism)

### Pullback^[당겨오기]

Vector fields **cannot** be pulled back in general!

(But 1-forms **can**: $F^* \omega$)

## Time-dependent vector fields^[시간 의존 벡터장]

$$X(p, t)$$

**Non-autonomous ODE**^[비자율 상미분방정식]:

$$\frac{d\gamma}{dt} = X(\gamma(t), t)$$

Flow는 더 이상 group property를 만족하지 않음.

---

# <span class="header-examples">핵심 개념 요약</span>

## Definition^[정의]

```
Vector field X on manifold M
    ↓
X: M → TM
    ↓
p ↦ X_p ∈ T_p M
```

## In coordinates^[좌표계에서]

$$X = \displaystyle\sum_{i=1}^n X^i \frac{\partial}{\partial x^i}$$

## Three roles of vector fields^[벡터장의 세 역할]

| Role | Description |
|------|-------------|
| **Geometric** | Tangent vectors at each point |
| **Differential operator** | Derivation on functions: $X: C^\infty(M) \to C^\infty(M)$ |
| **ODE** | Defines flow: $\frac{d\gamma}{dt} = X_{\gamma(t)}$ |

## Key operations^[핵심 연산]

| Operation | Formula | Meaning |
|-----------|---------|---------|
| **Lie bracket** | $[X, Y]f = X(Yf) - Y(Xf)$ | Commutator |
| **Lie derivative** | $\mathcal{L}_X Y = [X, Y]$ | Change along flow |
| **Flow** | $\phi_t: M \to M$ | Integral curves |

## In $\mathbb{R}^3$: Vector calculus^[벡터 미적분학]

| Operator | Formula | Output |
|----------|---------|--------|
| **Gradient** | $\nabla f$ | Vector field |
| **Divergence** | $\nabla \cdot \mathbf{F}$ | Scalar |
| **Curl** | $\nabla \times \mathbf{F}$ | Vector field |
| **Laplacian** | $\Delta f = \nabla^2 f$ | Scalar |

## Important identities^[중요한 항등식]

$$\nabla \times (\nabla f) = 0$$
$$\nabla \cdot (\nabla \times \mathbf{F}) = 0$$

---

**기초 개념**: [[Linear mapping]], [[Dual Spaces]]
**관련 개념**: [[Differential Forms]], [[Tensor]]
**응용**: Physics (electromagnetism, fluid dynamics), Dynamical systems, Control theory
**고급 주제**: Lie groups, Symplectic geometry, Riemannian geometry

