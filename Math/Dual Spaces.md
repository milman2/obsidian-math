# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

$V$를 field^[체] $\mathbb{F}$ 위의 vector space^[벡터 공간]라 하자.

**Dual space**^[쌍대 공간] $V^*$는 $V$에서 $\mathbb{F}$로 가는 모든 linear functional^[선형 범함수]들의 집합이다:

$$V^* = \{f : V \rightarrow \mathbb{F} \mid f \text{ is linear}\}$$

### Dual space의 구조
$V^*$는 자연스럽게 vector space^[벡터 공간] 구조를 가진다:
- **덧셈**: $(f + g)(v) = f(v) + g(v)$
- **스칼라곱**: $(\alpha f)(v) = \alpha f(v)$

---

# <span class="header-properties">Properties</span>

### Dimension^[차원]
$V$가 finite-dimensional^[유한차원]이면,
$$\dim(V^*) = \dim(V)$$

따라서 $V \cong V^*$ (isomorphic^[동형])이지만, 자연스러운 동형사상은 없다.

### Dual basis^[쌍대 기저]
$V$의 basis^[기저] $\{e_1, \ldots, e_n\}$에 대해, **dual basis**^[쌍대 기저] $\{e^1, \ldots, e^n\} \subset V^*$는 다음을 만족한다:

$$e^i(e_j) = \delta_{ij} = \begin{cases} 1 & \text{if } i = j \\ 0 & \text{if } i \neq j \end{cases}$$

여기서 $\delta_{ij}$는 Kronecker delta^[크로네커 델타]이다.

### Evaluation map^[평가 사상]
각 $v \in V$에 대해, evaluation functional^[평가 범함수] $\text{ev}_v : V^* \rightarrow \mathbb{F}$를 다음과 같이 정의할 수 있다:

$$\text{ev}_v(f) = f(v)$$

---

# <span class="header-examples">Examples</span>

### 1. Euclidean space^[유클리드 공간]
$V = \mathbb{R}^n$인 경우, $f \in V^*$는 다음 형태:
$$f(x) = a_1 x_1 + \cdots + a_n x_n$$
여기서 $(a_1, \ldots, a_n) \in \mathbb{R}^n$.

### 2. Function space^[함수 공간]
$V = C[0,1]$ (연속함수 공간)인 경우:
- **Point evaluation**: $\delta_a(f) = f(a)$ for $a \in [0,1]$
- **Integration**: $I(f) = \displaystyle\int_0^1 f(x) \, dx$

### 3. Matrix representation^[행렬 표현]
유한차원에서 $f \in V^*$는 row vector^[행 벡터]로, $v \in V$는 column vector^[열 벡터]로 표현되며:
$$f(v) = [a_1 \cdots a_n] \begin{bmatrix} v_1 \\ \vdots \\ v_n \end{bmatrix}$$

---

# <span class="header-remark">Remark</span>

### Double dual^[이중 쌍대]
$V^{**} = (V^*)^*$를 **double dual**^[이중 쌍대 공간]이라 한다. 

**Canonical embedding**^[표준 매장, Natural embedding, Evaluation map] $\Phi : V \rightarrow V^{**}$가 존재:

임의의 $v \in V$와 $f \in V^*$에 대해,
$$\Phi(v)(f) = f(v)$$

$\Phi$는 항상 injective^[단사]이다. 유한차원에서 $\Phi$는 isomorphism^[동형사상]이다: $V \cong V^{**}$.

**상세한 내용**: [[Double dual]]

### Hilbert space와의 관계
Hilbert space $H$에서는 [[Riesz Representation Theorem]]에 의해 $H^* \cong H$ (반선형 동형사상).

이는 내적 구조가 있으면 dual space^[쌍대 공간]를 자연스럽게 식별할 수 있음을 의미한다.

### Differential geometry와의 관계

Manifold^[다양체] $M$의 한 점 $p$에서:
- **Tangent space**^[접공간] $T_p M$ = 그 점에서의 벡터들
- **Cotangent space**^[여접공간] $T_p^* M = (T_p M)^*$ = differential 1-forms^[미분 1-형식]

관련 개념: [[Tensor]], [[Differential Forms]]

함수 $f: M \rightarrow \mathbb{R}$에 대해:
- **Differential**^[미분] $df \in T_p^* M$는 cotangent vector^[여접벡터] (1-form)
- $df(v) = D_v f$ (방향도함수)

**Riemannian metric**^[리만 계량] $g$가 있을 때:
- **Musical isomorphism**^[음악적 동형사상]: flat (♭)과 sharp (♯) 연산자
- $(df)^\sharp = \nabla f \in T_p M$ (gradient vector^[기울기 벡터])

즉, gradient는 원래 1-form인 differential을 metric으로 변환한 tangent vector^[접벡터]이다.

**Double dual의 역할:**
- Canonical embedding: $T_p M \rightarrow (T_p M)^{**} = (T_p^* M)^*$
- 유한차원에서: vector → covector → double dual ≅ 원래 vector
- Euclidean space $\mathbb{R}^n$에서는 표준 metric으로 인해 이 구별이 자동으로 처리됨

### 무한차원의 경우
Infinite-dimensional^[무한차원] space에서는:
- 일반적으로 $V \not\cong V^*$
- $\Phi$는 injective^[단사]이지만 surjective^[전사]가 아님: $V \subsetneq V^{**}$ (진부분공간)
- Functional analysis^[함수해석학]에서 중요한 역할

---

**관련 개념**: [[Linear mapping]], [[Dual of a Linear Map]], [[Double dual]], [[Tensor]], [[Differential Forms]]
