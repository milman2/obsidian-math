# <span class="header-prerequisite">Prerequisite</span>
- [[Directional Derivative]]
- [[Vector Field]]
- [[Inner Product]]
- Calculus^[미적분학]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Gradient^[기울기]

함수 $f: \mathbb{R}^n \rightarrow \mathbb{R}$에 대해, **gradient**^[기울기]는 vector field^[벡터장]:

$$\nabla f = \left(\frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, \ldots, \frac{\partial f}{\partial x_n}\right)$$

또는 column vector로:

$$\nabla f = \begin{pmatrix} \frac{\partial f}{\partial x_1} \\ \vdots \\ \frac{\partial f}{\partial x_n} \end{pmatrix}$$

## Notation^[표기법]

- $\nabla f$ ("nabla f" 또는 "del f")
- $\text{grad } f$
- $Df$ (total derivative)
- $\frac{\partial f}{\partial \mathbf{x}}$ (vector calculus)

---

# <span class="header-properties">Geometric Interpretation</span>

## Direction of steepest ascent^[가장 가파른 상승 방향]

점 $\mathbf{a}$에서:

$$\nabla f(\mathbf{a}) = \text{direction of maximum increase of } f$$

**크기**: $\|\nabla f(\mathbf{a})\|$ = maximum rate of increase.

### Proof^[증명]

Directional derivative in direction $\mathbf{v}$ (unit vector):

$$D_{\mathbf{v}} f = \nabla f \cdot \mathbf{v} = \|\nabla f\| \|\mathbf{v}\| \cos\theta = \|\nabla f\| \cos\theta$$

**최대**: $\theta = 0$일 때, 즉 $\mathbf{v} \parallel \nabla f$. ∎

## Normal to level surfaces^[등위면에 수직]

Level surface^[등위면] (또는 level set^[등위 집합]):

$$S_c = \{\mathbf{x} : f(\mathbf{x}) = c\}$$

**정리**: $\nabla f(\mathbf{a})$는 점 $\mathbf{a} \in S_c$에서 level surface에 **수직**^[perpendicular].

### Proof

$S_c$ 위의 임의의 curve $\mathbf{r}(t)$, $\mathbf{r}(0) = \mathbf{a}$:

$$f(\mathbf{r}(t)) = c \quad \forall t$$

미분:
$$\frac{d}{dt} f(\mathbf{r}(t)) = \nabla f(\mathbf{r}(t)) \cdot \mathbf{r}'(t) = 0$$

따라서 $\nabla f \perp \mathbf{r}'(t)$ (tangent vector).

모든 tangent vectors에 수직이므로, $\nabla f \perp S_c$. ∎

## Gradient as 1-form^[1-형식으로서의 기울기]

**미분기하학적 관점**:

Differential $df$ (1-form):
$$df = \displaystyle\sum_{i=1}^n \frac{\partial f}{\partial x_i} dx^i$$

Metric이 주어지면 **musical isomorphism**^[음악적 동형사상]:
$$df \xrightarrow{\sharp} \nabla f$$

**상세한 내용**: [[Differential Forms]], [[Dual Spaces]]

---

# <span class="header-properties">Properties</span>

## Linearity^[선형성]

$$\nabla(\alpha f + \beta g) = \alpha \nabla f + \beta \nabla g$$

## Product rule^[곱셈 규칙]

$$\nabla(fg) = f \nabla g + g \nabla f$$

**Leibniz rule**!

## Chain rule^[연쇄 법칙]

Composition $h = g \circ f$, $f: \mathbb{R}^n \rightarrow \mathbb{R}^m$, $g: \mathbb{R}^m \rightarrow \mathbb{R}$:

$$\nabla h(\mathbf{x}) = (Df(\mathbf{x}))^T \nabla g(f(\mathbf{x}))$$

여기서 $Df$는 Jacobian matrix^[야코비 행렬].

**특수 경우**: $h(\mathbf{x}) = g(f(\mathbf{x}))$, $f: \mathbb{R}^n \rightarrow \mathbb{R}$:

$$\nabla h = g'(f) \nabla f$$

## Quotient rule^[몫 규칙]

$$\nabla\left(\frac{f}{g}\right) = \frac{g \nabla f - f \nabla g}{g^2}$$

---

# <span class="header-examples">Examples</span>

## 1. Linear function^[선형 함수]

$$f(\mathbf{x}) = \mathbf{a} \cdot \mathbf{x} = \displaystyle\sum_{i=1}^n a_i x_i$$

$$\nabla f = \mathbf{a}$$

**Constant gradient** everywhere!

## 2. Quadratic form^[이차 형식]

$$f(\mathbf{x}) = \mathbf{x}^T A \mathbf{x} = \displaystyle\sum_{i,j} A_{ij} x_i x_j$$

$A$ symmetric:

$$\nabla f(\mathbf{x}) = 2A\mathbf{x}$$

**특수 경우**: $f(\mathbf{x}) = \|\mathbf{x}\|^2 = \mathbf{x}^T \mathbf{x}$:

$$\nabla f = 2\mathbf{x}$$

## 3. Distance function^[거리 함수]

$$f(\mathbf{x}) = \|\mathbf{x} - \mathbf{a}\|$$

$$\nabla f(\mathbf{x}) = \frac{\mathbf{x} - \mathbf{a}}{\|\mathbf{x} - \mathbf{a}\|}$$

**Unit vector** pointing away from $\mathbf{a}$.

## 4. Exponential

$$f(\mathbf{x}) = e^{\mathbf{a} \cdot \mathbf{x}}$$

$$\nabla f(\mathbf{x}) = \mathbf{a} e^{\mathbf{a} \cdot \mathbf{x}} = \mathbf{a} f(\mathbf{x})$$

## 5. Log of norm

$$f(\mathbf{x}) = \log \|\mathbf{x}\|$$

$$\nabla f(\mathbf{x}) = \frac{1}{\|\mathbf{x}\|^2} \mathbf{x} = \frac{\mathbf{x}}{\|\mathbf{x}\|^2}$$

## 6. Specific examples in $\mathbb{R}^3$

### $f(x, y, z) = x^2 + y^2 + z^2$

$$\nabla f = (2x, 2y, 2z) = 2\mathbf{r}$$

Level surfaces: Spheres centered at origin.

Gradient points radially outward.

### $f(x, y, z) = xy + yz + zx$

$$\nabla f = (y+z, x+z, x+y)$$

---

# <span class="header-properties">Operations with Gradients</span>

## Gradient of gradient (not standard)

Gradient는 vector를 만들므로, "gradient of gradient"는 의미 없음.

대신 → **Hessian matrix**^[헤세 행렬].

## Divergence of gradient^[기울기의 발산]

$$\nabla \cdot (\nabla f) = \Delta f$$

**Laplacian**^[라플라시안]:

$$\Delta f = \displaystyle\sum_{i=1}^n \frac{\partial^2 f}{\partial x_i^2}$$

## Curl of gradient^[기울기의 회전]

($\mathbb{R}^3$에서)

$$\nabla \times (\nabla f) = \mathbf{0}$$

**항상 영**!

**의미**: Gradient fields are **curl-free**^[회전 없음] (irrotational^[비회전], conservative^[보존적]).

---

# <span class="header-properties">Relationship with Other Concepts</span>

## Directional derivative^[방향 도함수]

$$D_{\mathbf{v}} f = \nabla f \cdot \mathbf{v} = \langle \nabla f, \mathbf{v} \rangle$$

**상세한 내용**: [[Directional Derivative]]

## Total differential^[전미분]

$$df = \nabla f \cdot d\mathbf{x} = \displaystyle\sum_{i=1}^n \frac{\partial f}{\partial x_i} dx_i$$

## Conservative vector field^[보존 벡터장]

Vector field $\mathbf{F}$가 **conservative**^[보존적] ⟺ $\exists f$ s.t. $\mathbf{F} = \nabla f$.

$f$를 **potential function**^[포텐셜 함수]라 한다.

**Test**: $\nabla \times \mathbf{F} = \mathbf{0}$ (simply connected domain에서).

**상세한 내용**: [[Vector Field]]

---

# <span class="header-examples">Applications</span>

## 1. Optimization^[최적화]

### Critical points^[임계점]

$$\nabla f(\mathbf{x}^*) = \mathbf{0} \Leftrightarrow \mathbf{x}^* \text{ is critical point}$$

**Types**^[유형]:
- Local minimum^[극소]: Hessian positive definite
- Local maximum^[극대]: Hessian negative definite
- Saddle point^[안장점]: Hessian indefinite

### Gradient descent^[경사 하강법]

$$\mathbf{x}_{k+1} = \mathbf{x}_k - \alpha_k \nabla f(\mathbf{x}_k)$$

**Convergence**: Under convexity, converges to minimum.

### Newton's method^[뉴턴 방법]

$$\mathbf{x}_{k+1} = \mathbf{x}_k - H_f(\mathbf{x}_k)^{-1} \nabla f(\mathbf{x}_k)$$

Uses Hessian for faster convergence.

## 2. Physics^[물리학]

### Potential energy^[위치 에너지]

Force $\mathbf{F}$ from potential $V$:

$$\mathbf{F} = -\nabla V$$

**예**:
- Gravity: $V = mgh$, $\mathbf{F} = -mg\mathbf{k}$
- Electric: $\mathbf{E} = -\nabla \phi$ (electric field from potential)

### Heat equation^[열방정식]

Temperature $T(\mathbf{x}, t)$:

$$\frac{\partial T}{\partial t} = k \Delta T = k \nabla \cdot (\nabla T)$$

Heat flows down the temperature gradient: $\mathbf{q} = -k\nabla T$.

### Fluid mechanics^[유체역학]

Pressure $p$, velocity $\mathbf{v}$:

$$\rho \frac{\partial \mathbf{v}}{\partial t} = -\nabla p + \text{other forces}$$

Pressure gradient drives fluid motion.

## 3. Machine learning^[기계 학습]

### Loss function minimization

$$\mathbf{w}^* = \arg\min_{\mathbf{w}} L(\mathbf{w})$$

Use gradient: $\nabla_{\mathbf{w}} L$.

### Backpropagation^[역전파]

Chain rule for gradients through neural network layers.

$$\frac{\partial L}{\partial w_{ij}^{(l)}} = \text{(computed via } \nabla L \text{ and chain rule)}$$

### Natural gradient^[자연 기울기]

Use Fisher information matrix $F$:

$$\mathbf{w}_{k+1} = \mathbf{w}_k - \alpha F^{-1} \nabla L(\mathbf{w}_k)$$

Accounts for parameter space geometry.

## 4. Image processing^[영상 처리]

### Edge detection^[윤곽 검출]

Image intensity $I(x, y)$.

**Gradient magnitude**: $\|\nabla I\|$ large at edges.

**Gradient direction**: Perpendicular to edge.

**Sobel operator**: Discrete approximation of gradient.

### Image segmentation^[영상 분할]

**Active contours**: Evolve curve $\mathbf{r}(s, t)$ using:

$$\frac{\partial \mathbf{r}}{\partial t} = -\nabla E(\mathbf{r})$$

where $E$ is energy functional.

## 5. Computer graphics^[컴퓨터 그래픽스]

### Normal vectors^[법선 벡터]

Surface defined by $f(\mathbf{x}) = c$.

**Normal**: $\mathbf{n} = \frac{\nabla f}{\|\nabla f\|}$

Used for lighting calculations (Phong shading).

### Bump mapping^[범프 매핑]

Perturb normals using gradient of height field:

$$\mathbf{n}_{\text{perturbed}} = \mathbf{n} + k \nabla h$$

Creates illusion of surface detail.

## 6. Economics^[경제학]

### Marginal analysis^[한계 분석]

Utility function $U(x_1, \ldots, x_n)$.

**Gradient** $\nabla U$: Marginal utilities.

**Indifference curves**: Level sets of $U$ (gradient perpendicular).

### Price optimization

Profit $\Pi(p_1, \ldots, p_n)$ as function of prices.

Optimize: $\nabla \Pi = \mathbf{0}$.

---

# <span class="header-remark">Remark</span>

## Gradient depends on metric^[기울기는 계량에 의존]

Euclidean space: Standard gradient $\nabla f = \left(\frac{\partial f}{\partial x_i}\right)$.

**일반 Riemannian manifold**: Gradient depends on metric $g$:

$$(\nabla f)^i = \displaystyle\sum_j g^{ij} \frac{\partial f}{\partial x_j}$$

여기서 $g^{ij}$는 metric의 inverse.

**Flat space**: $g^{ij} = \delta^{ij}$ → standard gradient.

## Gradient vs differential^[기울기 vs 미분]

**Differential** $df$: 1-form (covector)
$$df = \displaystyle\sum_i \frac{\partial f}{\partial x_i} dx^i$$

**Gradient** $\nabla f$: Vector
$$\nabla f = \displaystyle\sum_i \frac{\partial f}{\partial x_i} \frac{\partial}{\partial x_i}$$

**Connection**: Musical isomorphism $df \xrightarrow{\sharp} \nabla f$ (requires metric).

## Row vs column convention

**Mathematics**: Often column vector
$$\nabla f = \begin{pmatrix} \partial_1 f \\ \vdots \\ \partial_n f \end{pmatrix}$$

**Machine learning**: Often row vector (easier for matrix multiplication).

Context dependent!

---

# <span class="header-examples">핵심 개념 요약</span>

## Definition^[정의]

$$\nabla f = \left(\frac{\partial f}{\partial x_1}, \ldots, \frac{\partial f}{\partial x_n}\right)$$

Vector of partial derivatives.

## Geometric meaning^[기하학적 의미]

| Property | Description |
|----------|-------------|
| **Direction** | Steepest ascent |
| **Magnitude** | $\|\nabla f\|$ = maximum rate of increase |
| **Perpendicular** | To level surfaces $f = c$ |

## Key formula^[핵심 공식]

$$\boxed{D_{\mathbf{v}} f = \nabla f \cdot \mathbf{v}}$$

Directional derivative = inner product with gradient.

## Properties^[성질]

| Property | Formula |
|----------|---------|
| **Linearity** | $\nabla(\alpha f + \beta g) = \alpha \nabla f + \beta \nabla g$ |
| **Product rule** | $\nabla(fg) = f\nabla g + g\nabla f$ |
| **Chain rule** | $\nabla(g \circ f) = g'(f) \nabla f$ |

## Vector calculus identities^[벡터 미적분 항등식]

$$\nabla \cdot (\nabla f) = \Delta f \quad \text{(Laplacian)}$$
$$\nabla \times (\nabla f) = \mathbf{0} \quad \text{(Curl-free)}$$

## Applications^[응용]

| Field | Use |
|-------|-----|
| **Optimization** | $\nabla f = 0$ finds critical points |
| **Physics** | $\mathbf{F} = -\nabla V$ (conservative force) |
| **Machine learning** | Gradient descent |
| **Image processing** | Edge detection |
| **Economics** | Marginal analysis |

## Connection diagram^[연결 다이어그램]

```
Function f
    ↓ gradient
Vector field ∇f
    ↓ inner product with v
Directional derivative D_v f
```

---

**기초 개념**: [[Directional Derivative]], [[Vector Field]], [[Inner Product]]
**관련 개념**: [[Differential Forms]], [[Dual Spaces]], [[Derivation]]
**응용**: Optimization, Physics, Machine learning, Computer graphics
**핵심 성질**: Direction of steepest ascent, Normal to level surfaces

