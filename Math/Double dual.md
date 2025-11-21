# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Dual Spaces]]
- [[Dual of a Linear Map]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Double dual space^[이중 쌍대 공간]

$V$를 field^[체] $\mathbb{F}$ 위의 vector space^[벡터 공간]라 하자.

**Double dual space**^[이중 쌍대 공간] (또는 **bidual**^[쌍대의 쌍대])는:

$$V^{**} = (V^*)^*$$

즉, $V^{**}$는 $V^*$에서 $\mathbb{F}$로 가는 모든 linear functionals^[선형 범함수]의 공간이다.

**원소**: $\Psi \in V^{**}$는 linear map $\Psi: V^* \rightarrow \mathbb{F}$

---

# <span class="header-definition">Canonical Embedding</span>

## Evaluation map^[평가 사상]

**Canonical embedding**^[표준 매장] (또는 **natural embedding**, **evaluation map**) $\Phi: V \rightarrow V^{**}$는:

$$\Phi(v)(f) = f(v)$$

임의의 $v \in V$, $f \in V^*$에 대해.

### 직관적 의미

- $v \in V$: 원래 벡터
- $\Phi(v) \in V^{**}$: "벡터 $v$로 평가하는" functional
- $\Phi(v)$는 $f \in V^*$를 받아서 $f(v) \in \mathbb{F}$를 반환

**관점의 전환**: 벡터를 "평가되는 대상"에서 "평가하는 주체"로 바꿈.

### Linearity^[선형성]

$\Phi$는 linear map^[선형 사상]:

$$\Phi(\alpha v + \beta w)(f) = f(\alpha v + \beta w) = \alpha f(v) + \beta f(w) = \alpha \Phi(v)(f) + \beta \Phi(w)(f)$$

따라서 $\Phi(\alpha v + \beta w) = \alpha \Phi(v) + \beta \Phi(w)$.

---

# <span class="header-properties">Properties</span>

## Injectivity^[단사성]

$\Phi$는 **항상 injective**^[단사]이다.

**Proof**:
$\Phi(v) = 0$이라 하자. 즉, 모든 $f \in V^*$에 대해 $\Phi(v)(f) = 0$.

따라서 모든 $f \in V^*$에 대해 $f(v) = 0$.

$v \neq 0$이라 가정하면, basis를 확장하여 $v$를 포함시킬 수 있고, 이에 대한 dual basis element $f_v$는 $f_v(v) = 1$을 만족. 모순!

따라서 $v = 0$. $\square$

**결론**: $\Phi$는 $V$를 $V^{**}$의 subspace로 embedding.

## Finite-dimensional case^[유한차원 경우]

$V$가 finite-dimensional^[유한차원]이면:

$$\dim(V) = \dim(V^*) = \dim(V^{**})$$

$\Phi$가 injective이고 domain과 codomain의 차원이 같으므로:

$$\Phi \text{ is an isomorphism: } V \cong V^{**}$$

**결론**: 유한차원에서는 $V$와 $V^{**}$를 (자연스럽게) 동일시할 수 있다.

## Infinite-dimensional case^[무한차원 경우]

$V$가 infinite-dimensional^[무한차원]이면:

일반적으로 $\Phi$는 injective이지만 **not surjective**^[전사 아님]:

$$V \subsetneq V^{**} \quad \text{(proper subspace)}$$

**Intuition**: $V^{**}$가 $V$보다 "훨씬 크다".

**예외**: Reflexive spaces^[반사 공간] (아래 참조)

---

# <span class="header-definition">Reflexive Spaces</span>

## Definition^[정의]

Vector space $V$가 **reflexive**^[반사]이다 $\Leftrightarrow$ canonical embedding $\Phi: V \rightarrow V^{**}$가 **surjective**^[전사] (따라서 isomorphism).

즉, $V \cong V^{**}$ via the natural map.

## Examples of reflexive spaces^[반사 공간의 예]

### 1. Finite-dimensional spaces

**모든** finite-dimensional vector spaces는 reflexive.

### 2. Hilbert spaces^[힐베르트 공간]

**모든** Hilbert spaces $H$는 reflexive.

**Reason**: Riesz representation theorem에 의해 $H^* \cong H$, 따라서 $H^{**} \cong H^* \cong H$.

**상세한 내용**: [[Hilbert Space]], [[Riesz Representation Theorem]]

### 3. $L^p$ spaces ($1 < p < \infty$)

For $1 < p < \infty$:

$$L^p(\mu)^* \cong L^q(\mu) \quad \text{where } \frac{1}{p} + \frac{1}{q} = 1$$

따라서 $L^p$ ($1 < p < \infty$)는 reflexive.

### 4. Sobolev spaces $W^{k,p}$ ($1 < p < \infty$)

Sobolev spaces^[소볼레프 공간]도 reflexive (for $p$ in the range).

## Non-reflexive spaces^[비반사 공간]

### 1. $L^1$ and $L^\infty$

- $(L^1)^* \cong L^\infty$
- $(L^\infty)^* \supsetneq L^1$ (strictly larger!)

따라서 $L^1$과 $L^\infty$는 **not reflexive**.

### 2. $C[0, 1]$ (continuous functions)

$C[0, 1]^*$는 signed measures (Riesz representation)

$(C[0, 1])^{**}$는 $C[0, 1]$보다 훨씬 크다.

### 3. $c_0$ (sequences vanishing at infinity)

$c_0 = \{(x_n): x_n \to 0\}$

$c_0^* \cong \ell^1$, 하지만 $(\ell^1)^* \cong \ell^\infty \supsetneq c_0$.

---

# <span class="header-examples">Examples and Computations</span>

## 1. Euclidean space $\mathbb{R}^n$

$V = \mathbb{R}^n$, standard basis $\{e_1, \ldots, e_n\}$.

**Dual basis**: $\{e^1, \ldots, e^n\}$ where $e^i(e_j) = \delta_{ij}$.

**Double dual basis**: $\{(e^*)^1, \ldots, (e^*)^n\}$.

**Canonical embedding**:
$$\Phi(e_i)(e^j) = e^j(e_i) = \delta_{ij} = (e^*)^i(e^j)$$

따라서 $\Phi(e_i) = (e^*)^i$, 즉 $\Phi$는 bases를 일치시킴.

## 2. Polynomials

$V = \mathbb{F}[x]$ (모든 다항식)

**Dual**: $V^* = \mathbb{F}[[x]]$ (형식 급수, evaluation functionals)

**Double dual**: $V^{**}$는 $V$보다 훨씬 크다.

$\Phi$는 injective이지만 not surjective.

## 3. Sequence spaces

### $\ell^2$ (square-summable sequences)

$\ell^2 = \{(x_n): \sum |x_n|^2 < \infty\}$

Hilbert space이므로 reflexive:
$$\ell^2 \cong (\ell^2)^* \cong (\ell^2)^{**}$$

### $\ell^1$ (absolutely summable)

$\ell^1 = \{(x_n): \sum |x_n| < \infty\}$

$(\ell^1)^* \cong \ell^\infty$ (bounded sequences)

$(\ell^\infty)^*$는 $\ell^1$보다 훨씬 크다 → not reflexive.

## 4. Function spaces

### $L^2[0, 1]$

Hilbert space, reflexive.

$$L^2 \cong (L^2)^{**}$$

### $C[0, 1]$

$(C[0, 1])^* = M[0, 1]$ (signed Borel measures)

$(M[0, 1])^*$는 bounded measurable functions보다 크다.

Not reflexive.

---

# <span class="header-properties">Compatibility with Linear Maps</span>

## Natural transformation^[자연 변환]

$T: V \rightarrow W$ linear map에 대해:

```
    T
V -----> W
|        |
Φ_V      Φ_W
↓        ↓
V** ---> W**
    T**
```

다음이 성립:

$$\Phi_W \circ T = T^{**} \circ \Phi_V$$

**Proof**:
임의의 $v \in V$, $g \in W^*$에 대해,

$$(\Phi_W \circ T)(v)(g) = \Phi_W(T(v))(g) = g(T(v))$$

$$(T^{**} \circ \Phi_V)(v)(g) = T^{**}(\Phi_V(v))(g) = \Phi_V(v)(T^*(g)) = T^*(g)(v) = g(T(v))$$

$\square$

**의미**: $\Phi$는 **natural transformation**^[자연 변환]이다. 선택한 basis와 무관하게 자연스럽게 정의됨.

**상세한 내용**: [[Dual of a Linear Map]]

---

# <span class="header-remark">Functional Analysis Perspective</span>

## Weak and weak* topologies^[약한 위상과 약한* 위상]

### Weak topology on $V$

$V$의 **weak topology**^[약한 위상] $\sigma(V, V^*)$:

Functionals $f \in V^*$로 정의되는 가장 약한 topology.

### Weak* topology on $V^*$

$V^*$의 **weak* topology**^[약한* 위상] $\sigma(V^*, V)$:

Evaluation functionals $\text{ev}_v$ (for $v \in V$)로 정의되는 가장 약한 topology.

**Connection to double dual**:
- $\text{ev}_v = \Phi(v) \in V^{**}$
- Weak* topology는 $\Phi(V) \subseteq V^{**}$에 의해 유도됨

### Goldstine's theorem^[골드스타인 정리]

$\Phi(V)$는 $V^{**}$에서 weak* dense^[약한* 조밀]:

$$\overline{\Phi(V)}^{\text{weak*}} = V^{**}$$

**의미**: $V$가 reflexive가 아니어도, $\Phi(V)$는 weak* sense에서는 $V^{**}$를 "채운다".

## Banach space theory^[바나흐 공간 이론]

### Norm preservation^[노름 보존]

$V$가 normed space^[노름 공간]이면:

$$\|\Phi(v)\|_{V^{**}} = \|v\|_V$$

즉, $\Phi$는 **isometry**^[등거리 사상].

**Proof**: Hahn-Banach theorem 사용.

### James' theorem^[제임스 정리]

Banach space $V$가 reflexive $\Leftrightarrow$ 모든 continuous linear functional이 최대값을 달성.

### Reflexivity and compactness

$V$ reflexive $\Rightarrow$ closed bounded sets are weakly compact^[약하게 콤팩트].

이는 optimization theory에서 중요!

---

# <span class="header-remark">Applications</span>

## Optimization theory^[최적화 이론]

### Dual problems^[쌍대 문제]

Primal problem: $\min_{x \in V} f(x)$

Dual problem involves $V^*$ and sometimes $V^{**}$.

**Biduality**: 쌍대의 쌍대는 원래 문제 (under convexity^[볼록성]).

### Convex analysis^[볼록 해석학]

Convex function $f: V \rightarrow \mathbb{R}$의 **conjugate**^[켤레]:

$$f^*(y) = \sup_{x \in V} \{\langle y, x \rangle - f(x)\}, \quad y \in V^*$$

**Double conjugate**:
$$f^{**}: V^{**} \rightarrow \mathbb{R}$$

$f$ convex이면: $f^{**}|_V = f$ (via $\Phi$).

## Differential geometry^[미분 기하학]

### Tangent and cotangent bundles

Manifold $M$의 점 $p$에서:

- $T_p M$: Tangent space^[접공간]
- $T_p^* M = (T_p M)^*$: Cotangent space^[여접공간]
- $(T_p M)^{**}$: Double dual

**Natural identification**: $(T_p M)^{**} \cong T_p M$ (finite-dimensional!)

### Tensors

$(r, s)$-tensor: $T_p M$ 복사 $r$개와 $T_p^* M$ 복사 $s$개의 multilinear map.

Double dual을 통해 vectors와 covectors 사이 관계 이해.

**상세한 내용**: [[Tensor]], [[Differential Forms]]

## Quantum mechanics^[양자 역학]

### Dirac notation^[디랙 표기법]

- Ket $|v\rangle \in \mathcal{H}$ (Hilbert space)
- Bra $\langle w| \in \mathcal{H}^*$ (dual)
- $\langle w | v \rangle$: Inner product

Hilbert space는 reflexive이므로:
$$\mathcal{H}^{**} \cong \mathcal{H}$$

Bra와 ket을 자연스럽게 식별.

### Dual representations^[쌍대 표현]

Lie algebra representation $\rho: \mathfrak{g} \rightarrow \text{End}(V)$

Dual representation: $\rho^*: \mathfrak{g} \rightarrow \text{End}(V^*)$

Double dual: $\rho^{**}: \mathfrak{g} \rightarrow \text{End}(V^{**})$

$V$ reflexive이면 $\rho^{**} \cong \rho$.

---

# <span class="header-remark">Categorical Perspective</span>

## Natural transformation^[자연 변환]

Category theory^[범주론]에서 $\Phi$의 의의:

- **Functor**: $(-)^{**}: \textbf{Vect} \rightarrow \textbf{Vect}$ (identity functor의 변형)
- **Natural transformation**: $\Phi: \text{id}_{\textbf{Vect}} \Rightarrow (-)^{**}$

**Naturality**: 어떤 linear map $T: V \rightarrow W$에 대해서도:
$$T^{**} \circ \Phi_V = \Phi_W \circ T$$

**의미**: Basis 선택과 무관하게 정의됨 (canonical!).

**상세한 내용**: [[Category Theory]]

## Universal property^[보편 성질]

$V^{**}$와 $\Phi$는 특정 universal property를 만족하지만, 이는 고급 주제.

---

# <span class="header-examples">핵심 개념 요약</span>

## 핵심 정리

| Concept | Statement |
|---------|-----------|
| Definition | $V^{**} = (V^*)^*$ |
| Canonical map | $\Phi(v)(f) = f(v)$ |
| Injectivity | $\Phi$ always injective |
| Finite-dim | $V \cong V^{**}$ (isomorphism) |
| Reflexive | $\Phi$ surjective $\Leftrightarrow$ reflexive |
| Natural | $\Phi_W \circ T = T^{**} \circ \Phi_V$ |

## 차원별 특징

| Dimension | Property |
|-----------|----------|
| Finite | Always $V \cong V^{**}$ |
| Infinite | $V \subsetneq V^{**}$ (일반적으로) |
| Hilbert | Reflexive ($V \cong V^{**}$) |
| $L^p$ ($1<p<\infty$) | Reflexive |
| $L^1$, $L^\infty$, $C[0,1]$ | Not reflexive |

## Visualization

```
V ⊆ V** (via Φ, injection)

Finite-dimensional:
V = V** (isomorphism)

Infinite-dimensional:
V ⊊ V** (proper subspace, usually)

Reflexive spaces:
V = V** (special cases!)
```

---

**기초 개념**: [[Linear mapping]], [[Dual Spaces]]
**관련 주제**: [[Dual of a Linear Map]], [[Hilbert Space]], [[Riesz Representation Theorem]]
**응용**: [[Tensor]], [[Differential Forms]], [[Category Theory]]

