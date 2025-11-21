# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Dual Spaces]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Dual map^[쌍대 사상]

$V$, $W$를 field^[체] $\mathbb{F}$ 위의 vector space^[벡터 공간]라 하고, $T: V \rightarrow W$를 linear map^[선형 사상]이라 하자.

**Dual map**^[쌍대 사상] (또는 **transpose**^[전치], **adjoint**^[수반]) $T^* : W^* \rightarrow V^*$는 다음과 같이 정의된다:

$$T^*(g) = g \circ T$$

임의의 $g \in W^*$에 대해.

즉, 임의의 $v \in V$에 대해:
$$(T^*(g))(v) = g(T(v))$$

### Diagram^[도표]

```
    T
V -----> W
|        |
Φ_V      Φ_W
↓        ↓
V** <--- W**
    T**
```

여기서 horizontal arrows는 원래 방향과 **반대 방향**으로 간다는 것이 핵심!

### Alternative notation^[대체 표기법]

- $T^*$: 주로 사용됨
- $T^t$ 또는 $T^\top$: transpose로 볼 때
- $T'$: 일부 문헌에서

---

# <span class="header-properties">Properties</span>

## Basic properties^[기본 성질]

### 1. Linearity^[선형성]

$T^*$는 linear map^[선형 사상]이다:
$$T^*(\alpha g_1 + \beta g_2) = \alpha T^*(g_1) + \beta T^*(g_2)$$

### 2. Composition^[합성]

$S: U \rightarrow V$, $T: V \rightarrow W$에 대해:

$$(T \circ S)^* = S^* \circ T^*$$

**주의**: 순서가 **반대**로 뒤집힌다!

**Proof sketch**:
임의의 $g \in W^*$에 대해,
$$(T \circ S)^*(g) = g \circ (T \circ S) = (g \circ T) \circ S = S^*(g \circ T) = S^*(T^*(g))$$

### 3. Identity^[항등 사상]

$$(\text{id}_V)^* = \text{id}_{V^*}$$

### 4. Inverse^[역]

$T$가 isomorphism^[동형사상]이면, $T^*$도 isomorphism이고:

$$(T^{-1})^* = (T^*)^{-1}$$

## Functoriality^[함자성]

Dual space construction은 **contravariant functor**^[반변 함자]이다:
- Objects: Vector spaces $V \mapsto V^*$
- Morphisms: Linear maps $T \mapsto T^*$ (방향 반대!)

## Kernel and image^[핵과 상]

### Annihilator^[소멸자]

$S \subseteq V$의 **annihilator**^[소멸자]:
$$S^\perp = \{f \in V^* : f(s) = 0 \text{ for all } s \in S\}$$

### Key relationships

1. **Kernel of dual**:
   $$\ker(T^*) = (\text{Im}(T))^\perp$$
   
   $T^*$의 kernel은 $T$의 image를 annihilate하는 functionals.

2. **Image of dual**:
   $$\text{Im}(T^*) = (\ker(T))^\perp$$
   
   (유한차원에서, 또는 적절한 closure^[폐포] 조건 하에서)

3. **Dimension formula**:
   유한차원에서,
   $$\dim(\text{Im}(T^*)) = \dim(\text{Im}(T))$$
   
   즉, $\text{rank}(T^*) = \text{rank}(T)$.

**상세한 내용**: [[Linear mapping]] (Rank-Nullity Theorem)

---

# <span class="header-definition">Matrix Representation</span>

## Transpose matrix^[전치 행렬]

$V$, $W$가 finite-dimensional^[유한차원]이고 각각 basis^[기저] $\{e_1, \ldots, e_n\}$, $\{f_1, \ldots, f_m\}$를 가진다고 하자.

$T: V \rightarrow W$의 matrix representation^[행렬 표현]이 $A = [a_{ij}]_{m \times n}$이면:

$$T^*: W^* \rightarrow V^*$$

의 matrix representation (dual bases^[쌍대 기저]에 대해)은 **transpose**^[전치] $A^t = [a_{ji}]_{n \times m}$이다.

### Verification^[검증]

Dual basis^[쌍대 기저] $\{e^1, \ldots, e^n\}$, $\{f^1, \ldots, f^m\}$에 대해:

$$T^*(f^j) = \displaystyle\sum_{i=1}^n a_{ji} e^i$$

이는 정확히 $A^t$의 $j$-th column이다.

### Coordinate-free interpretation^[좌표 없는 해석]

$$\langle T^*(g), v \rangle = \langle g, T(v) \rangle$$

여기서 $\langle f, v \rangle = f(v)$는 pairing^[짝지음].

---

# <span class="header-examples">Examples</span>

## 1. Linear functional on $\mathbb{R}^n$

$T: \mathbb{R}^3 \rightarrow \mathbb{R}^2$, $T(x, y, z) = (x + y, y + z)$

**Matrix**:
$$A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \end{pmatrix}$$

**Dual map** $T^*: (\mathbb{R}^2)^* \rightarrow (\mathbb{R}^3)^*$:

$$A^t = \begin{pmatrix} 1 & 0 \\ 1 & 1 \\ 0 & 1 \end{pmatrix}$$

Linear functional $(a, b) \in (\mathbb{R}^2)^*$를 $(a, a+b, b) \in (\mathbb{R}^3)^*$로 매핑.

**Verification**:
$$T^*((a, b))(x, y, z) = (a, b) \cdot T(x, y, z) = a(x+y) + b(y+z) = ax + (a+b)y + bz$$

## 2. Differentiation operator^[미분 연산자]

$V = W = C^\infty(\mathbb{R})$ (smooth functions)

$D: V \rightarrow W$, $D(f) = f'$

**Dual map** $D^*: W^* \rightarrow V^*$?

일반적으로 $C^\infty(\mathbb{R})^*$는 distributions^[분포]를 포함하므로 복잡.

Finite-dimensional subspace에서 (예: polynomials of degree $\leq n$):
$D^*$는 **integration by parts**^[부분 적분]와 관련.

For inner product $\langle f, g \rangle = \int f(x)g(x) dx$:
$$D^* = -D \quad \text{(formal adjoint)}$$

## 3. Restriction map^[제한 사상]

$U \subseteq V$ subspace^[부분공간], $i: U \hookrightarrow V$ inclusion^[포함 사상].

**Dual map** $i^*: V^* \rightarrow U^*$는 **restriction**^[제한]:
$$i^*(f) = f|_U$$

$V^*$의 functional을 $U$로 제한.

**Image**: $\text{Im}(i^*) = U^\perp$ (in the sense of annihilator).

## 4. Projection^[사영]

$V = U \oplus W$ (direct sum^[직합])

$\pi_U: V \rightarrow U$ projection^[사영]

**Dual**: $\pi_U^*: U^* \rightarrow V^*$는 **extension by zero**^[0으로 확장]:

$$\pi_U^*(f)(u + w) = f(u) \quad \forall u \in U, w \in W$$

---

# <span class="header-properties">Advanced Properties</span>

## Double dual and natural transformation^[이중 쌍대와 자연 변환]

Natural embedding^[자연 매장] $\Phi_V: V \rightarrow V^{**}$에 대해:

$$\Phi_W \circ T = T^{**} \circ \Phi_V$$

다음 diagram이 commute^[가환]:

```
    T
V -----> W
|        |
Φ_V      Φ_W
↓        ↓
V** ---> W**
    T**
```

이는 $\Phi$가 **natural transformation**^[자연 변환]임을 의미.

**상세한 내용**: [[Dual Spaces]] (Double dual 섹션)

## Adjoint in inner product spaces^[내적 공간에서의 수반]

Inner product space^[내적 공간] $(V, \langle \cdot, \cdot \rangle)$에서:

**Hermitian adjoint**^[에르미트 수반] $T^*: V \rightarrow V$ (같은 공간!)는:

$$\langle T(v), w \rangle = \langle v, T^*(w) \rangle$$

이는 Riesz representation^[리스 표현]을 사용하여 $V^* \cong V$를 식별한 것.

**주의**: 이는 dual map과 다른 개념이지만 관련 있음!

**상세한 내용**: [[Riesz Representation Theorem]]

## Self-adjoint operators^[자기 수반 연산자]

$T^* = T$인 operator: Hermitian^[에르미트] or self-adjoint^[자기 수반].

**Properties**:
- Real eigenvalues^[실수 고유값]
- Orthogonal eigenvectors^[직교 고유벡터]
- Spectral theorem^[스펙트럼 정리]

---

# <span class="header-remark">Applications</span>

## Differential geometry^[미분 기하학]

### Pullback of differential forms^[미분 형식의 당김]

Smooth map $\phi: M \rightarrow N$ induces:

$$\phi^*: \Omega^k(N) \rightarrow \Omega^k(M)$$

Differential forms^[미분 형식]의 pullback^[당김].

**Connection**: Cotangent bundle의 map의 dual!

**상세한 내용**: [[Differential Forms]]

### Push-forward of vector fields^[벡터장의 밀기]

반대 방향: Vector fields는 "push forward", forms는 "pull back".

## Functional analysis^[함수해석학]

### Dual operators on Banach spaces

Bounded linear operator $T: X \rightarrow Y$ (Banach spaces):

$$T^*: Y^* \rightarrow X^*$$

**Properties**:
- $\|T^*\| = \|T\|$
- Weak* topology^[약한* 위상]
- Reflexive spaces^[반사 공간]: $X^{**} \cong X$

### Annihilators and closed subspaces

$$S^{\perp\perp} = \overline{S} \quad \text{(closure)}$$

Duality와 topology의 관계.

## Optimization^[최적화]

### Lagrange multipliers^[라그랑주 승수]

Constraint optimization:
$$\min f(x) \text{ subject to } g(x) = 0$$

Lagrange multiplier $\lambda$는 dual space^[쌍대 공간]의 원소!

$$\nabla f = \lambda \nabla g$$

### Duality in linear programming^[선형 계획법에서의 쌍대성]

Primal problem:
$$\min c^t x \text{ subject to } Ax \geq b, x \geq 0$$

Dual problem:
$$\max b^t y \text{ subject to } A^t y \leq c, y \geq 0$$

$A^t$는 dual map의 matrix representation!

## Quantum mechanics^[양자 역학]

### Bra-ket notation^[브라-켓 표기법]

- $|v\rangle$ (ket): vector in Hilbert space^[힐베르트 공간]
- $\langle w|$ (bra): element of dual space

$$\langle w | T | v \rangle = \langle T^*(w), v \rangle$$

Dual operator와 자연스럽게 연결.

---

# <span class="header-remark">Theoretical Significance</span>

## Category theory perspective^[범주론 관점]

Dual space construction은 **contravariant functor**^[반변 함자]:

$$\text{Vect}_{\mathbb{F}} \rightarrow \text{Vect}_{\mathbb{F}}^{\text{op}}$$

**Properties**:
- $(-)^*: \text{Vect} \rightarrow \text{Vect}^{\text{op}}$ is contravariant
- $(-)^{**}: \text{Vect} \rightarrow \text{Vect}$ is covariant (원래 방향 복구)
- Natural transformation $\Phi: \text{id} \Rightarrow (-)^{**}$

**상세한 내용**: [[Category Theory]]

## Universal property^[보편 성질]

Dual space $V^*$는 다음의 universal property를 만족:

For any linear map $T: V \rightarrow W$ and bilinear pairing, there exists unique $T^*: W^* \rightarrow V^*$ making certain diagram commute.

## Reflexivity^[반사성]

Space $V$가 **reflexive**^[반사]이다 $\Leftrightarrow$ $\Phi_V: V \rightarrow V^{**}$가 isomorphism.

**Examples**:
- Finite-dimensional spaces: Always reflexive
- Hilbert spaces: Reflexive
- $L^p$ spaces ($1 < p < \infty$): Reflexive
- $L^1$, $L^\infty$, $C[0, 1]$: Not reflexive

---

# <span class="header-examples">핵심 공식 요약</span>

| Concept | Formula |
|---------|---------|
| Definition | $(T^*(g))(v) = g(T(v))$ |
| Composition | $(T \circ S)^* = S^* \circ T^*$ |
| Matrix | $[T^*] = [T]^t$ |
| Kernel | $\ker(T^*) = (\text{Im}(T))^\perp$ |
| Image | $\text{Im}(T^*) = (\ker(T))^\perp$ |
| Rank | $\text{rank}(T^*) = \text{rank}(T)$ |
| Inner product | $\langle T(v), w \rangle = \langle v, T^*(w) \rangle$ |

## 핵심 성질

1. **Contravariance**^[반변성]: 방향이 반대로 뒤집힘
2. **Transpose**^[전치]: Matrix representation은 전치 행렬
3. **Functoriality**^[함자성]: 구조를 보존하는 변환
4. **Natural**^[자연스러움]: Double dual과의 compatibility

---

**기초 개념**: [[Linear mapping]], [[Dual Spaces]]
**관련 주제**: [[Category Theory]], [[Tensor]], [[Differential Forms]]
**응용**: [[Riesz Representation Theorem]], [[Hilbert Space]]

