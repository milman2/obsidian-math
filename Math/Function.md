# <span class="header-prerequisite">Prerequisite</span>
- Set theory (집합론 기초)
- [[Equivalence Relation and Partitions]]

# <span class="header-reference">Reference</span>
- Halmos, Naive Set Theory
- Rudin, Principles of Mathematical Analysis

---

# <span class="header-definition">Definition</span>

## Function^[함수]

집합 $X$, $Y$에 대해, **function^[함수]** (또는 **mapping^[사상]**, **map^[맵]**)은 $f: X \to Y$로 표기하며, 다음을 만족하는 규칙:

$$\forall x \in X, \; \exists! y \in Y \text{ such that } f(x) = y$$

즉, $X$의 각 원소에 대해 $Y$의 **유일한** 원소를 대응시킴

### 집합론적 정의

함수 $f: X \to Y$는 다음을 만족하는 $X \times Y$의 부분집합:

1. $\forall x \in X, \; \exists y \in Y$ such that $(x, y) \in f$
2. $(x, y_1) \in f$이고 $(x, y_2) \in f$이면 $y_1 = y_2$ (well-defined^[잘 정의됨])

**표기**: $(x, y) \in f$를 $f(x) = y$로 쓴다

## 기본 용어

### Domain^[정의역]

함수 $f: X \to Y$의 **domain^[정의역]**은 $X$

$$\text{dom}(f) = X$$

입력값들의 집합

### Codomain^[공역]

함수 $f: X \to Y$의 **codomain^[공역]**은 $Y$

$$\text{codom}(f) = Y$$

가능한 출력값들의 집합 (함수 정의에 포함)

### Range/Image^[치역/상]

함수 $f: X \to Y$의 **range^[치역]** (또는 **image^[상]**)는:

$$\text{im}(f) = f(X) = \{f(x) : x \in X\} = \{y \in Y : \exists x \in X, f(x) = y\}$$

실제로 사용되는 출력값들의 집합

**주의**: $\text{im}(f) \subseteq \text{codom}(f)$이지만 일반적으로 $\neq$

### Graph^[그래프]

함수 $f: X \to Y$의 **graph^[그래프]**는:

$$\text{graph}(f) = \{(x, f(x)) : x \in X\} \subseteq X \times Y$$

## Preimage^[역상]

$f: X \to Y$와 $B \subseteq Y$에 대해, $B$의 **preimage^[역상]** (또는 **inverse image^[역상]**)는:

$$f^{-1}(B) = \{x \in X : f(x) \in B\}$$

**주의**: 
- $f^{-1}$은 여기서 집합의 연산 (역함수와 다름!)
- 역함수가 없어도 preimage는 항상 정의됨

---

# <span class="header-properties">Properties</span>

## Image와 Preimage의 성질

$f: X \to Y$에 대해:

### Image

$A, A_1, A_2 \subseteq X$일 때:

1. $f(A_1 \cup A_2) = f(A_1) \cup f(A_2)$
2. $f(A_1 \cap A_2) \subseteq f(A_1) \cap f(A_2)$ (일반적으로 등호 성립 안 함)
3. $A_1 \subseteq A_2 \Rightarrow f(A_1) \subseteq f(A_2)$ (monotone^[단조])
4. $f(\emptyset) = \emptyset$

### Preimage

$B, B_1, B_2 \subseteq Y$일 때:

1. $f^{-1}(B_1 \cup B_2) = f^{-1}(B_1) \cup f^{-1}(B_2)$
2. $f^{-1}(B_1 \cap B_2) = f^{-1}(B_1) \cap f^{-1}(B_2)$ (등호 성립!)
3. $f^{-1}(Y \setminus B) = X \setminus f^{-1}(B)$ (complement 보존)
4. $f^{-1}(\emptyset) = \emptyset$
5. $f^{-1}(Y) = X$

**핵심**: Preimage는 합집합, 교집합, 여집합을 모두 보존 (더 좋은 성질)

### Image와 Preimage의 관계

1. $A \subseteq f^{-1}(f(A))$ (등호는 $f$가 injective일 때)
2. $f(f^{-1}(B)) \subseteq B$ (등호는 $f$가 surjective일 때)

## Equality of Functions^[함수의 같음]

두 함수 $f, g$가 **같다** $\Leftrightarrow$ 다음을 모두 만족:

1. $\text{dom}(f) = \text{dom}(g)$
2. $\text{codom}(f) = \text{codom}(g)$
3. $\forall x \in \text{dom}(f), \; f(x) = g(x)$

**주의**: Codomain도 중요! $f: \mathbb{R} \to \mathbb{R}$와 $g: \mathbb{R} \to (0, \infty)$ (with $f(x) = g(x) = e^x$)는 엄밀히 다른 함수

---

# <span class="header-definition">Composition</span>

## Definition^[정의]

함수 $f: X \to Y$와 $g: Y \to Z$에 대해, **composition^[합성]** $g \circ f: X \to Z$는:

$$(g \circ f)(x) = g(f(x))$$

**순서 주의**: $g \circ f$는 "$f$를 먼저 적용, 그 다음 $g$"

```
X --f--> Y --g--> Z
  \            /
   \--g∘f----/
```

## Properties

1. **Associativity^[결합법칙]**: $(h \circ g) \circ f = h \circ (g \circ f)$
2. **Identity^[항등원]**: $f \circ \text{id}_X = f = \text{id}_Y \circ f$
3. **일반적으로 교환법칙 성립 안 함**: $g \circ f \neq f \circ g$

## Composition과 Injectivity/Surjectivity

- $f, g$ 모두 injective $\Rightarrow$ $g \circ f$ injective
- $f, g$ 모두 surjective $\Rightarrow$ $g \circ f$ surjective
- $g \circ f$ injective $\Rightarrow$ $f$ injective
- $g \circ f$ surjective $\Rightarrow$ $g$ surjective

자세한 내용은 [[One-to-On, Onto]] 참조

---

# <span class="header-definition">Restriction and Extension</span>

## Restriction^[제한]

$f: X \to Y$와 $A \subseteq X$에 대해, **restriction^[제한]** $f|_A: A \to Y$는:

$$f|_A(x) = f(x) \quad \forall x \in A$$

$f$를 부분집합 $A$로 "제한"

## Extension^[확장]

$g: A \to Y$와 $A \subseteq X$에 대해, $f: X \to Y$가 $g$의 **extension^[확장]** $\Leftrightarrow$ $f|_A = g$

즉, $f(x) = g(x)$ for all $x \in A$

---

# <span class="header-examples">Examples</span>

## Example 1: 다항식 함수

$$f: \mathbb{R} \to \mathbb{R}, \quad f(x) = x^2 - 3x + 2$$

- Domain: $\mathbb{R}$
- Codomain: $\mathbb{R}$
- Range: $[-\frac{1}{4}, \infty)$ (완전제곱식으로 계산)

## Example 2: 절댓값 함수

$$f: \mathbb{R} \to \mathbb{R}, \quad f(x) = |x|$$

- Domain: $\mathbb{R}$
- Codomain: $\mathbb{R}$
- Range: $[0, \infty)$
- Not injective: $f(-1) = f(1) = 1$

## Example 3: 지수 함수

$$f: \mathbb{R} \to (0, \infty), \quad f(x) = e^x$$

- Injective: ✓
- Surjective: ✓
- Bijective: ✓
- Inverse: $f^{-1}(y) = \ln(y)$

## Example 4: 상수 함수

$$f: X \to Y, \quad f(x) = c \text{ (constant)}$$

- Range: $\{c\}$
- Injective: ✗ (unless $|X| = 1$)
- Surjective: ✗ (unless $Y = \{c\}$)

## Example 5: 항등 함수

$$\text{id}_X: X \to X, \quad \text{id}_X(x) = x$$

- 항상 bijective
- $f \circ \text{id}_X = f = \text{id}_Y \circ f$ for $f: X \to Y$

## Example 6: Projection^[사영]

$$\pi_1: X \times Y \to X, \quad \pi_1(x, y) = x$$
$$\pi_2: X \times Y \to Y, \quad \pi_2(x, y) = y$$

- Surjective (if $X, Y \neq \emptyset$)
- Not injective (unless $Y$ or $X$ is singleton)

## Example 7: Inclusion^[포함 사상]

$A \subseteq X$에 대해:

$$\iota: A \to X, \quad \iota(a) = a$$

- 항상 injective
- Surjective $\Leftrightarrow$ $A = X$

## Example 8: Characteristic Function^[특성 함수]

$A \subseteq X$에 대해:

$$\chi_A: X \to \{0, 1\}, \quad \chi_A(x) = \begin{cases} 1 & x \in A \\ 0 & x \notin A \end{cases}$$

측도론에서는 $\mathbb{1}_A$ (indicator function^[지시 함수])로도 표기

---

# <span class="header-definition">Special Functions</span>

## Inverse Function^[역함수]

함수 $f: X \to Y$가 bijective이면, **inverse function^[역함수]** $f^{-1}: Y \to X$가 존재:

$$f^{-1}(y) = x \Leftrightarrow f(x) = y$$

**성질**:
- $f^{-1}(f(x)) = x$ for all $x \in X$
- $f(f^{-1}(y)) = y$ for all $y \in Y$
- $f^{-1} \circ f = \text{id}_X$
- $f \circ f^{-1} = \text{id}_Y$
- $(f^{-1})^{-1} = f$
- $(g \circ f)^{-1} = f^{-1} \circ g^{-1}$

자세한 내용은 [[One-to-On, Onto]] 참조

## Partial Function^[부분 함수]

**Partial function^[부분 함수]**은 domain의 일부에서만 정의될 수 있음

예: $f(x) = \frac{1}{x}$는 $x = 0$에서 정의되지 않음

엄밀한 정의에서 함수는 전체 domain에서 정의되어야 하므로:
- $f: \mathbb{R} \setminus \{0\} \to \mathbb{R}$ ✓
- $f: \mathbb{R} \to \mathbb{R}$ ✗ (not well-defined at $x=0$)

## Multivalued Function^[다가 함수]

수학의 일부 맥락에서 하나의 입력이 여러 출력을 가질 수 있음

예: $\sqrt{x}$는 복소수에서 두 값을 가짐

엄밀한 정의에서는 함수가 아님 (relation^[관계]로 취급)

## Implicit Function^[음함수]

방정식 $F(x, y) = 0$으로 정의된 함수

예: $x^2 + y^2 = 1$

**Implicit Function Theorem^[음함수 정리]**가 조건을 제시

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**함수**: "기계" 또는 "규칙"
- 입력 $x$를 넣으면 출력 $f(x)$가 나옴
- 같은 입력은 항상 같은 출력 (deterministic^[결정론적])
- 각 입력에 대해 정확히 하나의 출력

## 표기법

| 표기 | 의미 |
|------|------|
| $f: X \to Y$ | $X$에서 $Y$로의 함수 |
| $x \mapsto f(x)$ | $x$가 $f(x)$로 매핑됨 |
| $f(x)$ | $x$에서의 함수값 |
| $f^{-1}(B)$ | 집합 $B$의 preimage |
| $f^{-1}$ | 역함수 (bijective일 때만) |

## Domain vs Codomain vs Range

**혼동하기 쉬운 개념**:

```
f: ℝ → ℝ, f(x) = x²

Domain (정의역): ℝ (모든 입력 가능)
Codomain (공역): ℝ (함수 정의에 명시)
Range (치역): [0, ∞) (실제 출력값들)
```

- **Domain**: 입력으로 허용되는 모든 값
- **Codomain**: 출력이 "속해야 하는" 집합 (함수 정의의 일부)
- **Range**: 실제로 나오는 출력값들 (계산으로 결정)

## 함수의 동등성

$f = g$ $\Leftrightarrow$ domain, codomain, 모든 점에서의 값이 같음

**예시**:
- $f: \mathbb{R} \to \mathbb{R}$, $f(x) = x^2$
- $g: \mathbb{R} \to [0, \infty)$, $g(x) = x^2$

$f \neq g$ (codomain이 다름!)

## 선형대수에서

**Linear map^[선형 사상]** $T: V \to W$:

$$T(av + bw) = aT(v) + bT(w)$$

선형성을 가진 함수

자세한 내용은 [[Linear mapping]] 참조

## 해석학에서

**Continuous function^[연속 함수]** $f: X \to Y$:

Topological 또는 metric 구조 하에서 "가까운 점을 가까운 점으로"

자세한 내용은 [[Topology]], [[Open Set]] 참조

## 측도론에서

**Measurable function^[가측 함수]** $f: X \to Y$:

$$f^{-1}(B) \text{ is measurable for all measurable } B$$

Preimage가 measurable sets을 보존

자세한 내용은 [[Measure Space]], [[Measure]] 참조

## 범주론에서

**Morphism^[사상]**: 범주론에서 함수의 일반화

- Objects 사이의 "화살표"
- Composition과 identity를 가짐

자세한 내용은 [[Category Theory]] 참조

## 역사적 배경

**함수의 발전**:
- 17세기: Leibniz, Newton - 곡선과 해석적 표현
- 18세기: Euler - 변수 사이의 관계
- 19세기: Dirichlet - 현대적 정의 (임의의 대응)
- 20세기: Bourbaki - 집합론적 정의

현대 정의는 매우 일반적:
- 명시적 공식 불필요
- 어떤 종류의 대응도 가능
- 추상적이고 공리적

## 컴퓨터 과학에서

**Function (programming)**:
- 입력 → 처리 → 출력
- Pure function: 같은 입력 → 같은 출력 (side effect 없음)
- Mathematical function과 직접 대응

**함수형 프로그래밍**:
- 함수를 일급 객체로 취급
- Composition, higher-order functions
- 수학적 함수 개념에 기반

