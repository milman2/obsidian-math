# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Dual Spaces]]
- [[Inner Product]]
- Metric spaces (거리 공간)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Hilbert space

**Hilbert space**^[힐베르트 공간] $H$는 **complete^[완비] inner product space^[내적 공간]**이다.

즉, 다음 조건을 만족:
1. Inner product^[내적] $\langle \cdot, \cdot \rangle : H \times H \rightarrow \mathbb{F}$ (여기서 $\mathbb{F} = \mathbb{R}$ 또는 $\mathbb{C}$)
2. Induced norm^[유도 노름]: $\|x\| = \sqrt{\langle x, x \rangle}$
3. **Completeness^[완비성]**: 모든 Cauchy sequence^[코시 수열]가 $H$에서 수렴

### Inner product의 성질

$x, y, z \in H$, $\alpha, \beta \in \mathbb{F}$에 대해:

1. **Conjugate symmetry^[켤레 대칭]**: $\langle x, y \rangle = \overline{\langle y, x \rangle}$
2. **Linearity in first argument^[첫 번째 인수에 대한 선형성]**: 
   $$\langle \alpha x + \beta y, z \rangle = \alpha \langle x, z \rangle + \beta \langle y, z \rangle$$
3. **Positive definiteness^[양의 정부호성]**: $\langle x, x \rangle \geq 0$, 등호는 $x = 0$일 때만

---

# <span class="header-properties">Properties</span>

## Cauchy-Schwarz inequality^[코시-슈바르츠 부등식]

모든 $x, y \in H$에 대해:
$$|\langle x, y \rangle| \leq \|x\| \cdot \|y\|$$

등호는 $x$와 $y$가 linearly dependent^[선형 종속]일 때만.

## Parallelogram law^[평행사변형 법칙]

$$\|x + y\|^2 + \|x - y\|^2 = 2(\|x\|^2 + \|y\|^2)$$

이는 norm이 inner product에서 유도됨을 특징짓는다.

## Polarization identity^[극화 항등식]

Inner product를 norm으로부터 복원:

**Real case** ($\mathbb{R}$):
$$\langle x, y \rangle = \frac{1}{4}(\|x + y\|^2 - \|x - y\|^2)$$

**Complex case** ($\mathbb{C}$):
$$\langle x, y \rangle = \frac{1}{4}\displaystyle\sum_{k=0}^{3} i^k \|x + i^k y\|^2$$

## Orthogonality^[직교성]

$x \perp y$ (직교) $\Leftrightarrow$ $\langle x, y \rangle = 0$

**Pythagorean theorem^[피타고라스 정리]**: $x \perp y$이면
$$\|x + y\|^2 = \|x\|^2 + \|y\|^2$$

---

# <span class="header-examples">Examples</span>

### 1. Euclidean space^[유클리드 공간] $\mathbb{R}^n$
Inner product: $\langle x, y \rangle = \displaystyle\sum_{i=1}^n x_i y_i$

유한차원이므로 자동으로 complete.

### 2. $\ell^2$ space
$$\ell^2 = \left\{(x_n)_{n=1}^\infty : \displaystyle\sum_{n=1}^\infty |x_n|^2 < \infty\right\}$$

Inner product: $\langle x, y \rangle = \displaystyle\sum_{n=1}^\infty x_n \overline{y_n}$

무한차원 Hilbert space의 대표적 예시.

### 3. $L^2$ space
$$L^2([a,b]) = \left\{f: [a,b] \rightarrow \mathbb{C} : \int_a^b |f(x)|^2 \, dx < \infty\right\}$$

Inner product: $\langle f, g \rangle = \displaystyle\int_a^b f(x) \overline{g(x)} \, dx$

Functional analysis^[함수해석학]의 핵심 공간.

### 4. Sobolev spaces^[소볼레프 공간] $H^k$

Weak derivatives^[약한 미분]까지 포함한 함수 공간.

PDE 이론에서 중요.

---

# <span class="header-theorem">Theorem</span>

## [[Riesz Representation Theorem]]

$H$가 Hilbert space이고 $L: H \rightarrow \mathbb{F}$가 bounded linear functional^[유계 선형 범함수]이면,

$$\exists! \, h_0 \in H \text{ s.t. } \forall h \in H, \quad L(h) = \langle h, h_0 \rangle$$

이는 $H^* \cong H$ (반선형 동형사상)을 의미한다.

## Projection theorem^[사영 정리]

$H$의 closed subspace^[닫힌 부분공간] $M$에 대해:

$$H = M \oplus M^\perp$$

여기서 $M^\perp = \{x \in H : x \perp M\}$ (orthogonal complement^[직교 여공간])

임의의 $x \in H$는 유일하게:
$$x = P_M(x) + P_{M^\perp}(x)$$

여기서 $P_M: H \rightarrow M$은 orthogonal projection^[직교 사영].

## Orthonormal basis^[정규직교 기저]

$H$의 orthonormal basis^[정규직교 기저] $\{e_i\}_{i \in I}$에 대해:

$$x = \displaystyle\sum_{i \in I} \langle x, e_i \rangle e_i$$

**Parseval's identity^[파르스발 항등식]**:
$$\|x\|^2 = \displaystyle\sum_{i \in I} |\langle x, e_i \rangle|^2$$

---

# <span class="header-remark">Remark</span>

## 유한차원 vs 무한차원

| 성질 | 유한차원 | 무한차원 |
|------|----------|----------|
| Basis | 유한 개 | 가산 무한 또는 비가산 |
| Completeness | 자동 | 조건 필요 |
| Closed = Compact | ✓ | ✗ |
| $H \cong H^*$ | Natural^[자연스러운] | Via inner product^[내적으로] |

## Separability^[분리가능성]

Hilbert space $H$가 **separable^[분리가능]** $\Leftrightarrow$ countable^[가산] dense subset 존재

예시:
- $\ell^2$: separable (rational 좌표 수열들)
- $L^2([a,b])$: separable (다항식들)

## Banach space와의 관계

모든 Hilbert space는 Banach space^[바나흐 공간]이다 (complete normed space).

역은 성립하지 않음: $L^p$ ($p \neq 2$)는 Banach이지만 Hilbert가 아님.

Hilbert space의 특별한 점:
- Inner product structure^[내적 구조]
- Orthogonal projection^[직교 사영] 존재
- Self-dual^[자기 쌍대]: $H^* \cong H$ (반선형)

## Applications^[응용]

### Quantum mechanics^[양자역학]
- State space^[상태 공간]는 Hilbert space
- Observables^[관측 가능량]는 self-adjoint operators^[자기 수반 연산자]
- Inner product = probability amplitude^[확률 진폭]

### Signal processing^[신호 처리]
- $L^2$ space로 신호 모델링
- Fourier transform^[푸리에 변환]
- Orthonormal basis = wavelets, etc.

### PDE theory
- Weak solutions^[약한 해] in Sobolev spaces
- Variational methods^[변분법]
- Spectral theory^[스펙트럼 이론]

## 관련 개념

- **Bounded operators^[유계 연산자]**: $T: H \rightarrow H$
- **Compact operators^[컴팩트 연산자]**: Generalization of finite-rank
- **Spectral theorem^[스펙트럼 정리]**: Self-adjoint operators의 대각화
- **Reproducing kernel Hilbert space (RKHS)**: Machine learning에서 중요

---

# <span class="header-examples">Hilbert space의 구조</span>

```
Inner product space (내적 공간)
    ↓ completion (완비화)
Hilbert space (힐베르트 공간)
    ↓ dual (쌍대)
H* ≅ H (Riesz Representation Theorem)
    ↓ operators
Bounded operators: B(H)
```

## 핵심 아이디어

**"무한차원의 Euclidean space"**
- Geometry (기하): Inner product, Orthogonality
- Analysis (해석): Completeness, Convergence
- Algebra (대수): Linear structure, Operators

모든 separable infinite-dimensional Hilbert spaces는 $\ell^2$와 isomorphic^[동형]이다!

---

**기초 개념**: [[Linear mapping]], [[Dual Spaces]], [[Inner Product]], [[Measure Space]]
**관련 정리**: [[Riesz Representation Theorem]], [[Monotone Convergence Theorem]], [[Dominated Convergence Theorem]], [[Fatou's Lemma]]
**응용**: [[Expected Value]], Quantum mechanics, Functional analysis

