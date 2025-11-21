# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- Calculus^[미적분학]
- Abstract algebra (기초)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Derivation^[미분 연산자]

Vector space $V$와 algebra $A$ (over field $\mathbb{F}$)에 대해, **derivation**^[미분 연산자]은 linear map $D: A \rightarrow V$로 다음을 만족:

### 1. Linearity^[선형성]

$$D(\alpha f + \beta g) = \alpha D(f) + \beta D(g)$$

for all $\alpha, \beta \in \mathbb{F}$, $f, g \in A$.

### 2. Leibniz rule^[라이프니츠 법칙] (Product rule)

$$D(fg) = D(f) \cdot g + f \cdot D(g)$$

**핵심**: 이 **두 조건만**으로 "미분"의 본질이 완전히 특징지어진다!

## Special case: Derivation at a point^[점에서의 미분 연산자]

Manifold $M$의 점 $p$에서:

$$D_p: C^\infty(M) \rightarrow \mathbb{R}$$

$$D_p(fg) = D_p(f) \cdot g(p) + f(p) \cdot D_p(g)$$

여기서 $D_p(f)$, $D_p(g)$, $f(p)$, $g(p)$는 모두 실수.

---

# <span class="header-theorem">Fundamental Theorem</span>

## Characterization of derivations^[미분 연산자의 특징화]

점 $p \in M$에서:

$$\boxed{\{\text{Derivations at } p\} \cong T_p M}$$

**의미**: Linearity + Leibniz rule을 만족하는 **모든** 연산자는 정확히 tangent vector이다!

### Proof sketch^[증명 스케치]

**방향 1**: Tangent vector → Derivation

$v \in T_p M$에 대해, directional derivative^[방향 도함수]:

$$D_v(f) = \frac{d}{dt}\bigg|_{t=0} f(\gamma(t))$$

여기서 $\gamma(0) = p$, $\gamma'(0) = v$.

**Leibniz rule 확인**:
$$D_v(fg) = \frac{d}{dt}\bigg|_{t=0} (f(\gamma(t)) \cdot g(\gamma(t)))$$
$$= f'(0) \cdot g(0) + f(0) \cdot g'(0) = D_v(f) \cdot g(p) + f(p) \cdot D_v(g)$$

**방향 2**: Derivation → Tangent vector

좌표 $(x^1, \ldots, x^n)$에서, derivation $D$는:

$$D = \sum_{i=1}^n D(x^i) \frac{\partial}{\partial x^i}\bigg|_p$$

따라서 $D$는 계수 $D(x^i)$를 가진 tangent vector.

**결론**: 일대일 대응. ∎

---

# <span class="header-properties">Automatic Properties</span>

Linearity + Leibniz rule로부터 **자동으로** 다음이 따라온다:

## 1. Constants vanish^[상수는 사라짐]

$$D(c) = 0 \quad \forall c \in \mathbb{F}$$

**Proof**:

$$D(1) = D(1 \cdot 1) = D(1) \cdot 1 + 1 \cdot D(1) = 2D(1)$$

따라서 $D(1) = 0$.

임의의 상수 $c$:
$$D(c) = D(c \cdot 1) = D(c) \cdot 1 + c \cdot D(1) = D(c) + 0 = D(c)$$

아니, 다시:
$$D(c) = D(c \cdot 1) = c \cdot D(1) = 0$$

(여기서 $c$를 scalar로 빼냄). ∎

## 2. Locality^[국소성]

$f = g$ in a neighborhood of $p$ ⟹ $D_p(f) = D_p(g)$

**Proof**:

$h = f - g = 0$ near $p$이면, $h(p) = 0$이고 $h^2 = 0$ near $p$.

$$0 = D_p(h^2) = D_p(h) \cdot h(p) + h(p) \cdot D_p(h) = 0 + 0 = 0$$

실제로, $h^2(p) = 0$이므로:
$$D_p(h^2) = D_p(h) \cdot h(p) + h(p) \cdot D_p(h) = 0$$

$h^2 = 0$ near $p$이므로 $D_p(h^2) = 0$ (by locality, but this is circular).

**Better proof**: Use bump functions and Taylor expansion. 핵심은 $D_p$는 $p$ 근처의 정보만 사용한다는 것.

## 3. Product of vanishing functions^[사라지는 함수들의 곱]

$f(p) = 0$이고 $g(p) = 0$이면:

$$D_p(fg) = 0$$

**Proof**:

$$D_p(fg) = D_p(f) \cdot g(p) + f(p) \cdot D_p(g) = D_p(f) \cdot 0 + 0 \cdot D_p(g) = 0$$

∎

## 4. Ideal property^[아이디얼 성질]

$I_p = \{f \in C^\infty(M) : f(p) = 0\}$ (maximal ideal at $p$).

$$D_p(I_p^2) = 0$$

여기서 $I_p^2 = \{fg : f, g \in I_p\}$.

**의미**: Derivation은 1차 정보만 본다.

---

# <span class="header-properties">Coordinate Representation</span>

## General form in coordinates^[좌표계에서의 일반 형태]

좌표 $(x^1, \ldots, x^n)$이 주어지면, 임의의 derivation $D_p$는:

$$D_p = \sum_{i=1}^n a_i \frac{\partial}{\partial x^i}\bigg|_p$$

여기서 $a_i = D_p(x^i) \in \mathbb{R}$.

### Proof^[증명]

함수 $f$를 Taylor 전개 (1차 근사):

$$f(x) = f(p) + \sum_{i=1}^n \frac{\partial f}{\partial x^i}(p) \cdot (x^i - x^i(p)) + O(|x-p|^2)$$

$D_p$ 적용:

$$D_p(f) = D_p(f(p)) + \sum_{i=1}^n D_p\left(\frac{\partial f}{\partial x^i}(p) \cdot (x^i - x^i(p))\right) + 0$$

$f(p)$는 상수이므로 $D_p(f(p)) = 0$.

$\frac{\partial f}{\partial x^i}(p)$도 상수 (점 p에서의 값):

$$D_p(f) = \sum_{i=1}^n \frac{\partial f}{\partial x^i}(p) \cdot D_p(x^i - x^i(p))$$

$$= \sum_{i=1}^n \frac{\partial f}{\partial x^i}(p) \cdot D_p(x^i)$$

$a_i = D_p(x^i)$로 놓으면:

$$D_p(f) = \sum_{i=1}^n a_i \frac{\partial f}{\partial x^i}(p) = \left(\sum_{i=1}^n a_i \frac{\partial}{\partial x^i}\right)(f)$$

∎

**결론**: 모든 derivation은 coordinate vector fields의 선형결합!

## Basis of derivations^[미분 연산자의 기저]

$$\left\{\frac{\partial}{\partial x^1}\bigg|_p, \ldots, \frac{\partial}{\partial x^n}\bigg|_p\right\}$$

이들은 derivations의 공간 $T_p M$의 basis를 이룬다.

**Dimension**: $\dim(T_p M) = n = \dim(M)$

---

# <span class="header-examples">Non-Examples</span>

Linearity + Leibniz rule을 **모두** 만족하지 않으면 derivation이 아니다.

## 1. Integration^[적분] ✗

$$I(f) = \int_0^1 f(x) \, dx$$

**Linearity**: ✓
$$I(\alpha f + \beta g) = \alpha I(f) + \beta I(g)$$

**Leibniz rule**: ✗
$$I(fg) = \int_0^1 f(x)g(x) \, dx$$

하지만:
$$I(f) \cdot g(0) + f(0) \cdot I(g) = \left(\int_0^1 f\right) \cdot g(0) + f(0) \cdot \left(\int_0^1 g\right)$$

일반적으로 다름!

**예**: $f(x) = g(x) = x$:
$$I(x \cdot x) = \int_0^1 x^2 \, dx = \frac{1}{3}$$
$$I(x) \cdot 0 + 0 \cdot I(x) = 0$$

$\frac{1}{3} \neq 0$ ✗

## 2. Second derivative^[2차 도함수] ✗

$$D(f) = \frac{d^2f}{dx^2}$$

**Linearity**: ✓
$$\frac{d^2(\alpha f + \beta g)}{dx^2} = \alpha \frac{d^2f}{dx^2} + \beta \frac{d^2g}{dx^2}$$

**Leibniz rule**: ✗

Product rule for second derivative:
$$\frac{d^2(fg)}{dx^2} = f'' g + 2f' g' + f g''$$

**Extra term** $2f'g'$ 때문에 실패!

Standard Leibniz:
$$f''(0) \cdot g(0) + f(0) \cdot g''(0)$$

일반적으로 $f''g + 2f'g' + fg'' \neq f''g + fg''$ ✗

## 3. Evaluation at different point^[다른 점에서의 평가] ✗

$p \neq q$일 때:
$$E_q(f) = f(q)$$

**Linearity**: ✓
**Leibniz rule**: ✗

$$E_q(fg) = f(q)g(q)$$

하지만:
$$E_q(f) \cdot g(p) + f(p) \cdot E_q(g) = f(q)g(p) + f(p)g(q)$$

일반적으로 $f(q)g(q) \neq f(q)g(p) + f(p)g(q)$ ✗

**주의**: $p = q$이면 이것은 derivation이 **아니라** evaluation (constant).

## 4. Average^[평균] ✗

$$A(f) = \frac{1}{2\epsilon} \int_{p-\epsilon}^{p+\epsilon} f(x) \, dx$$

**Linearity**: ✓
**Leibniz rule**: ✗ (global information 사용)

Derivation은 **local**이어야 함.

## 5. Square^[제곱] ✗

$$S(f) = (f')^2$$

**Linearity**: ✗
$$S(\alpha f + \beta g) = (\alpha f' + \beta g')^2 \neq \alpha S(f) + \beta S(g)$$

**Leibniz rule**: ✗

Non-linear이므로 derivation이 될 수 없음.

---

# <span class="header-examples">Examples of Derivations</span>

## 1. Directional derivative^[방향 도함수]

$\mathbb{R}^n$에서 방향 $\mathbf{v} = (v_1, \ldots, v_n)$:

$$D_{\mathbf{v}}(f) = \sum_{i=1}^n v_i \frac{\partial f}{\partial x_i}$$

**Verification**:
- Linearity: ✓ (partial derivatives are linear)
- Leibniz: ✓ (product rule)

## 2. Time derivative along a curve^[곡선을 따른 시간 도함수]

Curve $\gamma: (-\epsilon, \epsilon) \rightarrow M$, $\gamma(0) = p$:

$$D(f) = \frac{d}{dt}\bigg|_{t=0} f(\gamma(t))$$

**Verification**:
- Linearity: ✓
- Leibniz: ✓ (chain rule + product rule)

## 3. Coordinate partials^[좌표 편미분]

$$\frac{\partial}{\partial x^i}\bigg|_p: f \mapsto \frac{\partial f}{\partial x^i}(p)$$

**Verification**:
- Linearity: ✓
- Leibniz: ✓ (standard product rule)

## 4. Lie derivative^[리 도함수]

Vector field $X$를 따라:

$$\mathcal{L}_X(f) = X(f)$$

**Verification**:
- Linearity: ✓
- Leibniz: ✓ (by definition of vector field)

---

# <span class="header-properties">Algebraic Structure</span>

## Derivations form a vector space^[벡터 공간]

점 $p$에서 derivations의 집합 $\text{Der}_p(C^\infty(M))$:

### Vector space operations

$D_1, D_2$ derivations, $\alpha, \beta \in \mathbb{R}$:

$$(\alpha D_1 + \beta D_2)(f) = \alpha D_1(f) + \beta D_2(f)$$

**Verification**: $\alpha D_1 + \beta D_2$도 derivation.
- Linearity: ✓
- Leibniz: ✓ (각각 만족하므로)

## Derivations form a Lie algebra^[리 대수]

두 derivations $D_1, D_2$의 commutator^[교환자]:

$$[D_1, D_2] = D_1 \circ D_2 - D_2 \circ D_1$$

### $[D_1, D_2]$도 derivation!

**Leibniz rule 확인**:

$$[D_1, D_2](fg) = D_1(D_2(fg)) - D_2(D_1(fg))$$

$D_2(fg) = D_2(f) \cdot g + f \cdot D_2(g)$를 사용:

$$= D_1(D_2(f) \cdot g + f \cdot D_2(g)) - D_2(D_1(f) \cdot g + f \cdot D_1(g))$$

전개하면:
$$= [D_1, D_2](f) \cdot g + f \cdot [D_1, D_2](g)$$

✓ Leibniz rule 만족!

### Lie algebra properties

1. **Bilinearity**: ✓
2. **Antisymmetry**: $[D_1, D_2] = -[D_2, D_1]$ ✓
3. **Jacobi identity**: $[D_1, [D_2, D_3]] + [D_2, [D_3, D_1]] + [D_3, [D_1, D_2]] = 0$ ✓

따라서 $\text{Der}(A)$는 Lie algebra를 이룬다.

---

# <span class="header-properties">Universality Property</span>

## Derivation determines tangent vector^[미분 연산자가 접벡터를 결정]

점 $p$에서 derivation $D_p$가 주어지면, tangent vector가 **유일하게** 결정된다:

$$v = \sum_{i=1}^n D_p(x^i) \frac{\partial}{\partial x^i}\bigg|_p$$

**역으로**, tangent vector $v$가 주어지면:

$$D_v(f) = \sum_{i=1}^n v^i \frac{\partial f}{\partial x^i}(p)$$

로 derivation이 **유일하게** 결정된다.

## Functoriality^[함자성]

Smooth map $F: M \rightarrow N$에 대해:

**Pullback of functions**:
$$F^*: C^\infty(N) \rightarrow C^\infty(M)$$
$$F^*g = g \circ F$$

**Pushforward of derivations** ($F$ diffeomorphism):
$$(F_* D)(g) = D(F^* g) = D(g \circ F)$$

**관계**:
$$F_* [D_1, D_2] = [F_* D_1, F_* D_2]$$

Lie algebra homomorphism!

---

# <span class="header-remark">Philosophical Interpretation</span>

## What does Leibniz rule mean?^[라이프니츠 법칙의 의미]

$$D(fg) = D(f) \cdot g + f \cdot D(g)$$

**해석들**:

### 1. "Differentiation respects product structure"

Product의 미분 = 각 인수를 미분한 것들의 합

### 2. "First-order approximation"

$D$는 **1차 정보**만 본다:
- $D(c) = 0$ (0차: 사라짐)
- $D(f)$ (1차: 잡아냄)
- Higher order terms (무시됨)

### 3. "Leibniz rule = Product rule = Chain rule"

모든 미적분의 product/chain rules는 Leibniz rule의 변형.

### 4. "Infinitesimal change"

$$D(fg) \approx \frac{f(p+\epsilon v) g(p+\epsilon v) - f(p)g(p)}{\epsilon}$$

$$\approx \frac{(f(p) + \epsilon D(f))(g(p) + \epsilon D(g)) - f(p)g(p)}{\epsilon}$$

$$\approx D(f) \cdot g(p) + f(p) \cdot D(g)$$

## Why only two axioms?^[왜 두 공리만?]

**놀라운 사실**: Linearity + Leibniz만으로 "미분"의 모든 본질적 성질이 따라온다!

- Locality
- Constants vanish
- Coordinate representation
- Lie algebra structure

**철학**: "올바른" 공리는 자동으로 많은 것을 내포한다.

---

# <span class="header-examples">핵심 개념 요약</span>

## Derivation의 정의

| Axiom | Formula |
|-------|---------|
| **Linearity** | $D(\alpha f + \beta g) = \alpha D(f) + \beta D(g)$ |
| **Leibniz rule** | $D(fg) = D(f) \cdot g + f \cdot D(g)$ |

**이것만으로 충분!**

## Main Theorem^[주요 정리]

$$\boxed{\text{Derivations at } p \cong T_p M \cong \mathbb{R}^n}$$

**의미**: 
- Linearity + Leibniz ⟺ Tangent vector
- 일대일 대응
- 차원 = $\dim(M)$

## Automatic properties^[자동적 성질]

| Property | Statement |
|----------|-----------|
| Constants vanish | $D(c) = 0$ |
| Locality | $f = g$ near $p$ ⟹ $D(f) = D(g)$ |
| Product of zeros | $f(p) = g(p) = 0$ ⟹ $D(fg) = 0$ |
| Coordinate form | $D = \sum a_i \frac{\partial}{\partial x^i}$ |

## What is NOT a derivation^[미분 연산자가 아닌 것들]

| Operator | Why not? |
|----------|----------|
| Integration | Fails Leibniz ✗ |
| 2nd derivative | Fails Leibniz ✗ (extra term) |
| Evaluation at $q \neq p$ | Fails Leibniz ✗ |
| Square $(f')^2$ | Fails Linearity ✗ |

## Algebraic structure^[대수 구조]

$$\text{Der}(A) = \{\text{Derivations on } A\}$$

- **Vector space**: ✓
- **Lie algebra**: ✓ (with bracket $[D_1, D_2]$)
- **Module**: ✓ (over $C^\infty(M)$)

---

**기초 개념**: [[Linear mapping]]
**관련 개념**: [[Directional Derivative]], [[Gradient]], [[Vector Field]], [[Vector Fileds as Derivation]], [[Differential Forms]]
**응용**: Differential geometry, Lie theory, Algebraic geometry
**핵심 정리**: Derivation ⟺ Tangent vector

