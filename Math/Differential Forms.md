# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Dual Spaces]]
- [[Tensor]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Differential form^[미분 형식]

Manifold^[다양체] $M$의 한 점 $p$에서, **$k$-form**은 alternating^[교대] (antisymmetric^[반대칭]) multilinear map^[다중선형 사상]이다:

$$\omega: \underbrace{T_p M \times \cdots \times T_p M}_{k \text{ times}} \rightarrow \mathbb{R}$$

다음을 만족:
$$\omega(v_1, \ldots, v_i, \ldots, v_j, \ldots, v_k) = -\omega(v_1, \ldots, v_j, \ldots, v_i, \ldots, v_k)$$

### Space of $k$-forms

$\Lambda^k(T_p^* M)$는 점 $p$에서의 모든 $k$-forms의 vector space^[벡터 공간]이다.

특별한 경우:
- $\Lambda^0(T_p^* M) = \mathbb{R}$ (functions^[함수])
- $\Lambda^1(T_p^* M) = T_p^* M$ (cotangent vectors^[여접벡터])
- $\Lambda^n(T_p^* M)$ where $n = \dim(M)$ (volume forms^[부피 형식])

## Wedge product^[쐐기곱]

$k$-form $\omega$와 $\ell$-form $\eta$에 대해, **wedge product**^[쐐기곱] $\omega \wedge \eta$는 $(k+\ell)$-form이다:

$$(\omega \wedge \eta)(v_1, \ldots, v_{k+\ell}) = \displaystyle\frac{1}{k!\ell!} \sum_{\sigma \in S_{k+\ell}} \text{sgn}(\sigma) \cdot \omega(v_{\sigma(1)}, \ldots, v_{\sigma(k)}) \cdot \eta(v_{\sigma(k+1)}, \ldots, v_{\sigma(k+\ell)})$$

### 성질
- **Associative**^[결합법칙]: $(\omega \wedge \eta) \wedge \zeta = \omega \wedge (\eta \wedge \zeta)$
- **Anticommutative**^[반교환법칙]: $\omega \wedge \eta = (-1)^{k\ell} \eta \wedge \omega$
  - 특히, $k$가 홀수면: $\omega \wedge \omega = 0$

## Exterior derivative^[외미분]

$k$-form $\omega$에 대해, **exterior derivative**^[외미분] $d\omega$는 $(k+1)$-form이다.

### 성질
1. **Linearity**^[선형성]: $d(\alpha \omega + \beta \eta) = \alpha d\omega + \beta d\eta$
2. **Leibniz rule**^[라이프니츠 법칙]: $d(\omega \wedge \eta) = d\omega \wedge \eta + (-1)^k \omega \wedge d\eta$
3. **$d^2 = 0$**: $d(d\omega) = 0$ (모든 $\omega$에 대해)

---

# <span class="header-properties">Properties</span>

### Dimension of $\Lambda^k(V^*)$

$\dim(V) = n$이면,
$$\dim(\Lambda^k(V^*)) = \binom{n}{k}$$

특히, $k > n$이면 $\Lambda^k(V^*) = \{0\}$.

### Basis of $k$-forms

좌표 함수 $\{x^1, \ldots, x^n\}$ (0-forms)에 exterior derivative를 적용하면 $\{dx^1, \ldots, dx^n\}$ (1-forms).

$k$-forms의 basis는:
$$dx^{i_1} \wedge dx^{i_2} \wedge \cdots \wedge dx^{i_k}, \quad 1 \leq i_1 < i_2 < \cdots < i_k \leq n$$

여기서 $dx^i = d(x^i)$는 좌표 함수 $x^i$의 exterior derivative이다.

임의의 $k$-form은:
$$\omega = \displaystyle\sum_{i_1 < \cdots < i_k} f_{i_1 \cdots i_k} \, dx^{i_1} \wedge \cdots \wedge dx^{i_k}$$

### Exterior algebra^[외대수]

$$\Lambda^*(V^*) = \bigoplus_{k=0}^n \Lambda^k(V^*)$$

이는 wedge product를 곱셈으로 하는 graded algebra^[등급 대수]를 이룬다.

---

# <span class="header-examples">Examples</span>

### 0-form
Functions: $f: M \rightarrow \mathbb{R}$

 **중요**: 좌표 함수 $x^1, \ldots, x^n: M \rightarrow \mathbb{R}$도 0-forms이다.

Exterior derivative: $df = \displaystyle\sum_{i=1}^n \frac{\partial f}{\partial x^i} dx^i$ (gradient를 1-form으로)

여기서 $dx^i = d(x^i)$는 좌표 함수 $x^i$에 exterior derivative를 적용한 1-form이다.

### 1-form in $\mathbb{R}^3$
$$\omega = P \, dx + Q \, dy + R \, dz$$

여기서 $P, Q, R$은 함수들.

Exterior derivative:
$$d\omega = \left(\frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}\right) dy \wedge dz + \left(\frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}\right) dz \wedge dx + \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dx \wedge dy$$

이것은 **curl (회전)**과 같다!

### 2-form in $\mathbb{R}^3$
$$\eta = A \, dy \wedge dz + B \, dz \wedge dx + C \, dx \wedge dy$$

Exterior derivative:
$$d\eta = \left(\frac{\partial A}{\partial x} + \frac{\partial B}{\partial y} + \frac{\partial C}{\partial z}\right) dx \wedge dy \wedge dz$$

이것은 **divergence (발산)**와 같다!

### 3-form (volume form)
$$\omega = f \, dx \wedge dy \wedge dz$$

Integration^[적분]: $\displaystyle\int_M \omega = \int_M f \, dV$ (volume integral)

---

# <span class="header-theorem">Theorem</span>

## Stokes' Theorem^[스토크스 정리]

Oriented manifold^[방향을 가진 다양체] $M$과 그 boundary^[경계] $\partial M$에 대해:

$$\int_M d\omega = \int_{\partial M} \omega$$

### 특수한 경우들

이 정리는 다음을 일반화한다:

1. **Fundamental Theorem of Calculus**^[미적분학의 기본정리]:
   $$\int_a^b f'(x) \, dx = f(b) - f(a)$$

2. **Green's Theorem**^[그린 정리] ($\mathbb{R}^2$):
   $$\int_D \left(\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y}\right) dA = \oint_{\partial D} (P \, dx + Q \, dy)$$

3. **Classical Stokes' Theorem** (surface in $\mathbb{R}^3$):
   $$\int_S (\nabla \times \mathbf{F}) \cdot d\mathbf{S} = \oint_{\partial S} \mathbf{F} \cdot d\mathbf{r}$$

4. **Divergence Theorem**^[발산 정리] (Gauss' theorem):
   $$\int_V (\nabla \cdot \mathbf{F}) \, dV = \oint_{\partial V} \mathbf{F} \cdot d\mathbf{S}$$

---

# <span class="header-remark">Remark</span>

### De Rham cohomology^[드람 코호몰로지]

$d^2 = 0$ 성질로 인해:
- **Closed forms**^[닫힌 형식]: $\omega$ s.t. $d\omega = 0$
- **Exact forms**^[완전 형식]: $\omega = d\eta$ for some $\eta$

모든 exact form은 closed이다. 그 역은 일반적으로 성립하지 않으며, 이 차이가 manifold의 topology^[위상]를 반영한다.

**De Rham cohomology group**:
$$H^k_{dR}(M) = \frac{\{\text{closed } k\text{-forms}\}}{\{\text{exact } k\text{-forms}\}}$$

### Vector calculus와의 대응

$\mathbb{R}^3$에서:

| Differential forms | Vector calculus |
|-------------------|-----------------|
| 0-form: $f$ | Scalar field |
| 1-form: $\omega$ | Vector field (via metric) |
| 2-form: $\eta$ | Vector field (via Hodge star) |
| 3-form: $\zeta$ | Scalar field |
| $d$ (on 0-forms) | gradient ($\nabla f$) |
| $d$ (on 1-forms) | curl ($\nabla \times \mathbf{F}$) |
| $d$ (on 2-forms) | divergence ($\nabla \cdot \mathbf{F}$) |

Differential forms는 이러한 연산들을 좌표계에 무관하게 일반화한다.

**상세한 내용**: [[Vector Field]]

### Hodge star operator^[호지 스타 연산자]

Riemannian manifold에서 $k$-form을 $(n-k)$-form으로 변환:
$$\star: \Lambda^k(M) \rightarrow \Lambda^{n-k}(M)$$

이를 통해 inner product on forms를 정의할 수 있다.

### Applications

- **Physics**: Maxwell equations은 differential forms로 간결하게 표현됨
- **Topology**: De Rham cohomology는 manifold의 topological invariants^[위상 불변량]
- **Complex geometry**: Kähler forms, Dolbeault cohomology

---

**기초 개념**: [[Linear mapping]], [[Dual Spaces]], [[Tensor]]
**관련 개념**: [[Vector Field]]
**응용**: Physics (electromagnetism), Topology (De Rham cohomology), Complex geometry

