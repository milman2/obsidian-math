# <span class="header-prerequisite">Prerequisite</span>
- [[Derivation]]
- [[Vector Field]]
- Calculus^[미적분학]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Directional derivative^[방향 도함수]

함수 $f: \mathbb{R}^n \rightarrow \mathbb{R}$와 점 $\mathbf{a} \in \mathbb{R}^n$, 방향 $\mathbf{v} \in \mathbb{R}^n$에 대해, **directional derivative**^[방향 도함수]는:

$$D_{\mathbf{v}} f(\mathbf{a}) = \lim_{h \to 0} \frac{f(\mathbf{a} + h\mathbf{v}) - f(\mathbf{a})}{h}$$

**의미**: 점 $\mathbf{a}$에서 방향 $\mathbf{v}$로 움직일 때 $f$의 순간 변화율.

## Unit directional derivative^[단위 방향 도함수]

$\mathbf{v}$가 **unit vector**^[단위 벡터] ($\|\mathbf{v}\| = 1$)일 때:

$$D_{\mathbf{v}} f(\mathbf{a})$$

이것이 표준적인 정의. 일반 벡터의 경우:

$$D_{\mathbf{v}} f = \|\mathbf{v}\| \cdot D_{\mathbf{v}/\|\mathbf{v}\|} f$$

---

# <span class="header-properties">Properties</span>

## Formula with partial derivatives^[편미분으로의 공식]

$f$가 differentiable^[미분가능]하면:

$$D_{\mathbf{v}} f(\mathbf{a}) = \nabla f(\mathbf{a}) \cdot \mathbf{v} = \displaystyle\sum_{i=1}^n \frac{\partial f}{\partial x_i}(\mathbf{a}) v_i$$

여기서 $\nabla f$는 **gradient**^[기울기].

**상세한 내용**: [[Gradient]]

### Proof^[증명]

Chain rule을 사용. Curve $\gamma(t) = \mathbf{a} + t\mathbf{v}$를 정의하면:

$$D_{\mathbf{v}} f(\mathbf{a}) = \frac{d}{dt}\bigg|_{t=0} f(\gamma(t))$$

Chain rule:

$$= \displaystyle\sum_{i=1}^n \frac{\partial f}{\partial x_i}(\mathbf{a}) \frac{d\gamma_i}{dt}(0) = \displaystyle\sum_{i=1}^n \frac{\partial f}{\partial x_i}(\mathbf{a}) v_i$$

∎

## Linearity in direction^[방향에 대한 선형성]

$$D_{\alpha \mathbf{v} + \beta \mathbf{w}} f = \alpha D_{\mathbf{v}} f + \beta D_{\mathbf{w}} f$$

**의미**: Directional derivative는 방향 벡터에 대해 선형.

## As a derivation^[미분 연산자로서]

고정된 방향 $\mathbf{v}$에 대해, $D_{\mathbf{v}}: C^\infty(\mathbb{R}^n) \rightarrow \mathbb{R}$는 **derivation**^[미분 연산자]:

1. **Linearity**: $D_{\mathbf{v}}(\alpha f + \beta g) = \alpha D_{\mathbf{v}}(f) + \beta D_{\mathbf{v}}(g)$
2. **Leibniz rule**: $D_{\mathbf{v}}(fg) = D_{\mathbf{v}}(f) \cdot g + f \cdot D_{\mathbf{v}}(g)$

**상세한 내용**: [[Derivation]], [[Vector Fileds as Derivation]]

## Coordinate vector fields^[좌표 벡터장]

표준 basis vectors $\mathbf{e}_i = (0, \ldots, 1, \ldots, 0)$에 대해:

$$D_{\mathbf{e}_i} f = \frac{\partial f}{\partial x_i}$$

**의미**: Partial derivatives는 coordinate directions의 directional derivatives!

---

# <span class="header-properties">Relationship with Gradient</span>

## Gradient formula^[기울기 공식]

$$D_{\mathbf{v}} f(\mathbf{a}) = \nabla f(\mathbf{a}) \cdot \mathbf{v} = \langle \nabla f(\mathbf{a}), \mathbf{v} \rangle$$

**내적**^[Inner product] 형태!

**상세한 내용**: [[Inner Product]]

## Maximum rate of change^[최대 변화율]

$\mathbf{v}$가 unit vector일 때:

$$D_{\mathbf{v}} f(\mathbf{a}) = \|\nabla f(\mathbf{a})\| \cos \theta$$

여기서 $\theta$는 $\nabla f(\mathbf{a})$와 $\mathbf{v}$ 사이의 각도.

### Maximum occurs when $\theta = 0$

$$\max_{\|\mathbf{v}\|=1} D_{\mathbf{v}} f(\mathbf{a}) = \|\nabla f(\mathbf{a})\|$$

**방향**: $\mathbf{v} = \frac{\nabla f(\mathbf{a})}{\|\nabla f(\mathbf{a})\|}$

**결론**: **Gradient는 가장 가파른 상승 방향**을 가리킨다!

## Zero directional derivative^[영 방향 도함수]

$$D_{\mathbf{v}} f(\mathbf{a}) = 0 \Leftrightarrow \mathbf{v} \perp \nabla f(\mathbf{a})$$

**의미**: Gradient에 수직인 방향으로는 함수가 변하지 않음.

이러한 방향들은 **level surface**^[등위면] $f = \text{const}$에 접함.

---

# <span class="header-examples">Examples</span>

## 1. Linear function^[선형 함수]

$$f(x, y) = ax + by$$

방향 $\mathbf{v} = (v_1, v_2)$:

$$D_{\mathbf{v}} f(x_0, y_0) = av_1 + bv_2$$

**Gradient**: $\nabla f = (a, b)$ (constant everywhere).

## 2. Quadratic function^[이차 함수]

$$f(x, y) = x^2 + y^2$$

점 $(1, 0)$에서 방향 $\mathbf{v} = (\cos\theta, \sin\theta)$:

$$D_{\mathbf{v}} f(1, 0) = \nabla f(1, 0) \cdot \mathbf{v} = (2, 0) \cdot (\cos\theta, \sin\theta) = 2\cos\theta$$

**Maximum**: $\theta = 0$일 때 (positive $x$-direction), $D_{\mathbf{v}} f = 2$.

## 3. $\mathbb{R}^3$에서

$$f(x, y, z) = xyz$$

점 $(1, 1, 1)$에서 방향 $\mathbf{v} = \frac{1}{\sqrt{3}}(1, 1, 1)$:

$$\nabla f(1, 1, 1) = (yz, xz, xy)\bigg|_{(1,1,1)} = (1, 1, 1)$$

$$D_{\mathbf{v}} f(1, 1, 1) = (1, 1, 1) \cdot \frac{1}{\sqrt{3}}(1, 1, 1) = \frac{3}{\sqrt{3}} = \sqrt{3}$$

## 4. Distance function^[거리 함수]

$$f(x, y) = \sqrt{x^2 + y^2}$$

방향 $\mathbf{v}$ at point $(x_0, y_0) \neq (0, 0)$:

$$\nabla f(x_0, y_0) = \frac{1}{\sqrt{x_0^2 + y_0^2}}(x_0, y_0) = \frac{\mathbf{r}}{\|\mathbf{r}\|}$$

**Radial direction**: $D_{\mathbf{r}/\|\mathbf{r}\|} f = 1$ (moving away from origin).

**Tangential direction**: $D_{\mathbf{v}} f = 0$ if $\mathbf{v} \perp \mathbf{r}$.

## 5. Temperature distribution^[온도 분포]

$T(x, y, z)$ = temperature at point $(x, y, z)$.

**물리적 의미**:
- $\nabla T$: Direction of maximum temperature increase
- $\|\nabla T\|$: Rate of maximum temperature change
- Heat flows in direction $-\nabla T$ (down the gradient)

---

# <span class="header-properties">Higher Derivatives</span>

## Second directional derivative^[2차 방향 도함수]

$$D_{\mathbf{v}}^2 f = D_{\mathbf{v}}(D_{\mathbf{v}} f)$$

좌표로:

$$D_{\mathbf{v}}^2 f = \displaystyle\sum_{i,j} v_i v_j \frac{\partial^2 f}{\partial x_i \partial x_j}$$

Matrix form:
$$D_{\mathbf{v}}^2 f = \mathbf{v}^T H_f \mathbf{v}$$

여기서 $H_f$는 **Hessian matrix**^[헤세 행렬].

## Taylor expansion along a direction

$$f(\mathbf{a} + h\mathbf{v}) = f(\mathbf{a}) + h D_{\mathbf{v}} f(\mathbf{a}) + \frac{h^2}{2} D_{\mathbf{v}}^2 f(\mathbf{a}) + O(h^3)$$

---

# <span class="header-properties">Manifold Generalization</span>

## Directional derivative on manifolds^[다양체에서의 방향 도함수]

Manifold $M$, 점 $p \in M$, tangent vector $v \in T_p M$:

$$D_v f = v(f)$$

여기서 $v$는 **derivation**으로 작용.

**상세한 내용**: [[Vector Fileds as Derivation]]

좌표 $(x^1, \ldots, x^n)$에서:

$$v = \displaystyle\sum_{i=1}^n v^i \frac{\partial}{\partial x^i}\bigg|_p$$

$$D_v f = \displaystyle\sum_{i=1}^n v^i \frac{\partial f}{\partial x^i}(p)$$

## Covariant derivative^[공변 도함수]

Riemannian manifold에서는 **covariant derivative**^[공변 도함수] $\nabla_{\mathbf{v}} \mathbf{w}$:
- Vector field의 방향 도함수
- Connection^[접속]을 사용
- Parallel transport^[평행 이동]와 관련

---

# <span class="header-examples">Applications</span>

## 1. Optimization^[최적화]

### Gradient descent^[경사 하강법]

$$\mathbf{x}_{n+1} = \mathbf{x}_n - \alpha \nabla f(\mathbf{x}_n)$$

**방향**: $-\nabla f$ (steepest descent).

### Line search^[선 탐색]

고정된 방향 $\mathbf{d}$에서 minimize:

$$\min_{\alpha > 0} f(\mathbf{x} + \alpha \mathbf{d})$$

$\frac{d}{d\alpha} f(\mathbf{x} + \alpha \mathbf{d}) = D_{\mathbf{d}} f(\mathbf{x} + \alpha \mathbf{d})$

## 2. Physics^[물리학]

### Work done by force^[힘이 한 일]

Force field $\mathbf{F}$, potential $V$:

$$\mathbf{F} = -\nabla V$$

Work along direction $\mathbf{v}$:

$$dW = \mathbf{F} \cdot \mathbf{v} \, ds = -D_{\mathbf{v}} V \, ds$$

### Directional heat flux^[방향 열유속]

Temperature $T$, heat flux $\mathbf{q} = -k \nabla T$ (Fourier's law).

Heat flow in direction $\mathbf{v}$:

$$q_{\mathbf{v}} = \mathbf{q} \cdot \mathbf{v} = -k D_{\mathbf{v}} T$$

## 3. Computer graphics^[컴퓨터 그래픽스]

### Normal mapping^[법선 매핑]

Surface defined by $f(x, y, z) = c$.

**Normal vector**^[법선 벡터]: $\nabla f$ (perpendicular to level surface).

Directional derivative determines shading.

### Edge detection^[윤곽 검출]

Image intensity $I(x, y)$.

**Gradient magnitude** $\|\nabla I\|$: Large at edges.

**Gradient direction**: Perpendicular to edge.

## 4. Machine learning^[기계 학습]

### Gradient-based optimization

Loss function $L(\mathbf{w})$.

Update: $\mathbf{w} \leftarrow \mathbf{w} - \eta \nabla L(\mathbf{w})$

**Stochastic gradient descent**: Use noisy estimates.

### Adversarial examples^[적대적 예제]

Perturb input in direction of $\nabla_{\mathbf{x}} L$:

$$\mathbf{x}_{\text{adv}} = \mathbf{x} + \epsilon \cdot \text{sign}(\nabla_{\mathbf{x}} L)$$

## 5. Numerical methods^[수치 방법]

### Finite differences^[유한 차분]

Approximate directional derivative:

$$D_{\mathbf{v}} f(\mathbf{a}) \approx \frac{f(\mathbf{a} + h\mathbf{v}) - f(\mathbf{a})}{h}$$

**Forward difference**: 1st order accuracy.

**Central difference**:
$$D_{\mathbf{v}} f(\mathbf{a}) \approx \frac{f(\mathbf{a} + h\mathbf{v}) - f(\mathbf{a} - h\mathbf{v})}{2h}$$

2nd order accuracy.

---

# <span class="header-remark">Remark</span>

## Directional derivative vs partial derivative

**Partial derivative**: Special case along coordinate directions
$$\frac{\partial f}{\partial x_i} = D_{\mathbf{e}_i} f$$

**Directional derivative**: Generalization to arbitrary directions.

## Existence and differentiability

**주의**: 
- Directional derivatives may exist in all directions
- But $f$ may not be differentiable!

**Example**: $f(x, y) = \begin{cases} \frac{xy^2}{x^2+y^4} & (x,y) \neq (0,0) \\ 0 & (x,y) = (0,0) \end{cases}$

At $(0, 0)$:
- All directional derivatives exist
- But $f$ is not differentiable (not continuous!)

**Differentiability requires**: $D_{\mathbf{v}} f = \nabla f \cdot \mathbf{v}$ with continuous $\nabla f$.

## Convention: Unit vectors

Many texts require $\|\mathbf{v}\| = 1$ for directional derivative.

**General convention**: Allow any $\mathbf{v}$, then:
$$D_{c\mathbf{v}} f = c \cdot D_{\mathbf{v}} f$$

Scaling property.

---

# <span class="header-examples">핵심 개념 요약</span>

## Definition^[정의]

$$D_{\mathbf{v}} f(\mathbf{a}) = \lim_{h \to 0} \frac{f(\mathbf{a} + h\mathbf{v}) - f(\mathbf{a})}{h}$$

**의미**: 방향 $\mathbf{v}$로의 순간 변화율.

## Formula^[공식]

$$D_{\mathbf{v}} f = \nabla f \cdot \mathbf{v} = \displaystyle\sum_{i=1}^n \frac{\partial f}{\partial x_i} v_i$$

## Key properties^[핵심 성질]

| Property | Statement |
|----------|-----------|
| **Linearity** | $D_{\alpha \mathbf{v} + \beta \mathbf{w}} f = \alpha D_{\mathbf{v}} f + \beta D_{\mathbf{w}} f$ |
| **Leibniz rule** | $D_{\mathbf{v}}(fg) = D_{\mathbf{v}}(f) \cdot g + f \cdot D_{\mathbf{v}}(g)$ |
| **Maximum** | $\max_{\|\mathbf{v}\|=1} D_{\mathbf{v}} f = \|\nabla f\|$ |
| **Direction** | Max occurs when $\mathbf{v} \parallel \nabla f$ |

## Relationship with gradient^[기울기와의 관계]

$$\boxed{D_{\mathbf{v}} f = \langle \nabla f, \mathbf{v} \rangle}$$

- $\nabla f$: Direction of steepest ascent
- $\|\nabla f\|$: Maximum rate of change
- $\mathbf{v} \perp \nabla f$: No change (level surface)

## Special cases^[특수한 경우]

| Case | Formula |
|------|---------|
| **Coordinate direction** | $D_{\mathbf{e}_i} f = \frac{\partial f}{\partial x_i}$ |
| **Gradient direction** | $D_{\nabla f / \|\nabla f\|} f = \|\nabla f\|$ |
| **Perpendicular to gradient** | $D_{\mathbf{v}} f = 0$ |

---

**기초 개념**: [[Derivation]], [[Vector Field]]
**관련 개념**: [[Gradient]], [[Vector Fileds as Derivation]]
**응용**: Optimization, Physics, Machine learning, Computer graphics
**핵심 관계**: $D_{\mathbf{v}} f = \nabla f \cdot \mathbf{v}$

