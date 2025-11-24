# <span class="header-prerequisite">Prerequisite</span>
- 함수의 기본 개념
- Set theory (집합론)

# <span class="header-reference">Reference</span>
- Halmos, Naive Set Theory
- Munkres, Topology

---

# <span class="header-definition">Definition</span>

함수 $f: X \to Y$에 대해:

## Injective^[단사] (One-to-One)

$f$가 **injective^[단사]** (또는 **one-to-one^[일대일]**)이다 $\Leftrightarrow$ 서로 다른 입력은 서로 다른 출력을 가짐:

$$\forall x_1, x_2 \in X, \; x_1 \neq x_2 \Rightarrow f(x_1) \neq f(x_2)$$

**동등한 정의** (contrapositive^[대우]):

$$\forall x_1, x_2 \in X, \; f(x_1) = f(x_2) \Rightarrow x_1 = x_2$$

**직관**: 각 출력값은 최대 하나의 입력값에서만 나옴

## Surjective^[전사] (Onto)

$f$가 **surjective^[전사]** (또는 **onto^[위로]**)이다 $\Leftrightarrow$ 모든 출력값이 실제로 달성됨:

$$\forall y \in Y, \; \exists x \in X \text{ such that } f(x) = y$$

**동등한 정의**:

$$f(X) = Y$$

즉, $f$의 image^[상]가 전체 codomain^[공역]과 같음

**직관**: 공역의 모든 원소가 적어도 하나의 원소로부터 매핑됨

## Bijective^[전단사] (One-to-One Correspondence)

$f$가 **bijective^[전단사]**이다 $\Leftrightarrow$ $f$가 injective이면서 surjective

$$f \text{ is bijective} \Leftrightarrow f \text{ is injective and surjective}$$

**직관**: 완벽한 "짝짓기" - 각 입력이 정확히 하나의 출력과 대응

**동등한 정의**: 역함수 $f^{-1}: Y \to X$가 존재

---

# <span class="header-properties">Properties</span>

### Inverse Function^[역함수]

**정리**: $f: X \to Y$가 bijective $\Leftrightarrow$ 역함수 $f^{-1}: Y \to X$가 존재

역함수는 다음을 만족:
- $f^{-1}(f(x)) = x$ for all $x \in X$
- $f(f^{-1}(y)) = y$ for all $y \in Y$

### Left Inverse^[왼쪽 역원]

$f: X \to Y$가 injective $\Leftrightarrow$ left inverse^[왼쪽 역원] $g: Y \to X$가 존재하여 $g \circ f = \text{id}_X$

(단, Axiom of Choice^[선택 공리] 필요할 수 있음)

### Right Inverse^[오른쪽 역원]

$f: X \to Y$가 surjective $\Leftrightarrow$ right inverse^[오른쪽 역원] $h: Y \to X$가 존재하여 $f \circ h = \text{id}_Y$

(Axiom of Choice 필요)

### Composition^[합성]

**Injective**:
- $f, g$ 모두 injective $\Rightarrow$ $g \circ f$ injective
- $g \circ f$ injective $\Rightarrow$ $f$ injective

**Surjective**:
- $f, g$ 모두 surjective $\Rightarrow$ $g \circ f$ surjective
- $g \circ f$ surjective $\Rightarrow$ $g$ surjective

**Bijective**:
- $f, g$ 모두 bijective $\Rightarrow$ $g \circ f$ bijective
- $(g \circ f)^{-1} = f^{-1} \circ g^{-1}$

### Restriction^[제한]

$f: X \to Y$가 injective이고 $A \subseteq X$이면:
$$f|_A: A \to Y \text{ is injective}$$

$f: X \to Y$가 surjective이고 $f(A) = Y$이면:
$$f|_A: A \to Y \text{ is surjective}$$

---

# <span class="header-examples">Examples</span>

## Injective but Not Surjective

### Example 1: $f: \mathbb{N} \to \mathbb{Z}$

$$f(n) = n$$

- **Injective**: ✓ (서로 다른 자연수는 서로 다른 정수)
- **Surjective**: ✗ (음수는 image에 없음)

### Example 2: $f: \mathbb{R} \to \mathbb{R}$

$$f(x) = e^x$$

- **Injective**: ✓ (지수함수는 strictly increasing)
- **Surjective**: ✗ (음수나 0은 image에 없음, $f(\mathbb{R}) = (0, \infty)$)

### Example 3: $f: \mathbb{R} \to \mathbb{R}$

$$f(x) = x^3 + x$$

- **Injective**: ✓ ($f'(x) = 3x^2 + 1 > 0$이므로 strictly increasing)
- **Surjective**: ✓ ($\lim_{x \to -\infty} f(x) = -\infty$, $\lim_{x \to \infty} f(x) = \infty$)
- **Bijective**: ✓

## Surjective but Not Injective

### Example 1: $f: \mathbb{R} \to \mathbb{R}$

$$f(x) = x^2$$

**주의**: Codomain이 중요!

$f: \mathbb{R} \to \mathbb{R}$:
- **Injective**: ✗ ($f(-1) = f(1) = 1$)
- **Surjective**: ✗ (음수는 image에 없음)

$f: \mathbb{R} \to [0, \infty)$:
- **Injective**: ✗ (여전히 $f(-1) = f(1)$)
- **Surjective**: ✓ (모든 비음수는 제곱근을 가짐)

### Example 2: $f: \mathbb{R} \to \mathbb{R}$

$$f(x) = \sin(x)$$

- **Injective**: ✗ ($\sin(x) = \sin(x + 2\pi)$)
- **Surjective**: ✗ ($f(\mathbb{R}) = [-1, 1]$)

$f: \mathbb{R} \to [-1, 1]$:
- **Injective**: ✗ (주기함수)
- **Surjective**: ✓

### Example 3: Projection Map

$\pi_1: \mathbb{R}^2 \to \mathbb{R}$, $\pi_1(x, y) = x$

- **Injective**: ✗ ($\pi_1(1, 0) = \pi_1(1, 1) = 1$)
- **Surjective**: ✓ (모든 $x \in \mathbb{R}$에 대해 $(x, 0)$이 존재)

## Bijective

### Example 1: Identity Function^[항등함수]

$$\text{id}_X: X \to X, \quad \text{id}_X(x) = x$$

항상 bijective

### Example 2: $f: \mathbb{R} \to \mathbb{R}$

$$f(x) = 2x + 3$$

선형 함수 (기울기 $\neq 0$)는 bijective

역함수: $f^{-1}(y) = \frac{y - 3}{2}$

### Example 3: $f: \mathbb{R} \to \mathbb{R}$

$$f(x) = x^3$$

- **Injective**: ✓ (strictly increasing)
- **Surjective**: ✓ (모든 실수는 세제곱근을 가짐)
- **Bijective**: ✓

역함수: $f^{-1}(y) = \sqrt[3]{y}$

### Example 4: $f: (0, 1) \to \mathbb{R}$

$$f(x) = \tan\left(\pi\left(x - \frac{1}{2}\right)\right)$$

유계 구간을 무한 구간으로 bijection

### Example 5: Exponential (restricted domain)

$f: \mathbb{R} \to (0, \infty)$, $f(x) = e^x$

- **Bijective**: ✓

역함수: $f^{-1}(y) = \ln(y)$

## Neither Injective nor Surjective

### Example: $f: \mathbb{R} \to \mathbb{R}$

$$f(x) = \sin(x)$$

- **Injective**: ✗ (주기함수)
- **Surjective**: ✗ (치역이 $[-1, 1]$)

---

# <span class="header-theorem">Theorem</span>

### Cantor-Bernstein-Schröder Theorem

Injections $f: A \to B$와 $g: B \to A$가 존재하면, bijection $h: A \to B$가 존재

**따름정리**: $|A| \leq |B|$이고 $|B| \leq |A|$이면 $|A| = |B|$ (집합의 cardinality^[기수])

### Cardinality^[기수] 비교

두 집합 $A, B$에 대해:

- $|A| \leq |B|$ $\Leftrightarrow$ injection $f: A \to B$가 존재
- $|A| = |B|$ $\Leftrightarrow$ bijection $f: A \to B$가 존재
- $|A| < |B|$ $\Leftrightarrow$ injection $f: A \to B$가 존재하지만 bijection은 없음

### Pigeonhole Principle^[비둘기집 원리]

유한집합 $X, Y$에서 $|X| > |Y|$이면, 모든 함수 $f: X \to Y$는 injective가 아니다

**따름정리**: $f: X \to Y$가 injective이고 $X, Y$ 유한이면 $|X| \leq |Y|$

---

# <span class="header-remark">Remark</span>

### 직관적 이해

**Injective (One-to-One)**:
- "각자 독립적" - 같은 출력을 내는 서로 다른 입력 없음
- 정보 손실 없음
- $|X| \leq |Y|$ (loosely speaking for finite sets)

**Surjective (Onto)**:
- "모두 덮음" - 공역의 모든 원소가 사용됨
- 출력이 전부 달성됨
- $|X| \geq |Y|$ (loosely speaking for finite sets)

**Bijective**:
- "완벽한 대응" - 일대일 대응
- 역함수 존재
- $|X| = |Y|$

### 용어

| 한국어 | 영어 | 기호적 의미 |
|--------|------|------------|
| 단사 | Injective, One-to-One | $x_1 \neq x_2 \Rightarrow f(x_1) \neq f(x_2)$ |
| 전사 | Surjective, Onto | $f(X) = Y$ |
| 전단사 | Bijective, One-to-One Correspondence | Injective + Surjective |

### 시각화

**Injective**:
```
X → Y
a → 1
b → 2
c → 3
    4  (unused)
```
여러 화살표가 같은 곳을 가리키지 않음

**Surjective**:
```
X → Y
a → 1
b ↘ 2
c ↗
```
$Y$의 모든 원소가 화살표의 끝점

**Bijective**:
```
X → Y
a → 1
b → 2
c → 3
```
완벽한 짝짓기

### Codomain의 중요성

같은 공식이라도 **codomain**에 따라 surjectivity가 달라짐!

$f(x) = x^2$:
- $f: \mathbb{R} \to \mathbb{R}$: Not surjective
- $f: \mathbb{R} \to [0, \infty)$: Surjective
- $f: [0, \infty) \to [0, \infty)$: Bijective

**Image vs Codomain**:
- **Image** $f(X) = \{f(x) : x \in X\}$: 실제로 매핑되는 값들
- **Codomain** $Y$: 함수 정의에서 지정된 출력 집합
- Surjective $\Leftrightarrow$ Image = Codomain

### 선형대수^[Linear Algebra]에서

선형 변환 $T: V \to W$에 대해:

- **Injective** $\Leftrightarrow$ $\ker(T) = \{0\}$ (kernel^[핵]이 자명)
- **Surjective** $\Leftrightarrow$ $\text{im}(T) = W$ (image^[상]이 전체)
- **Bijective** $\Leftrightarrow$ $T$는 isomorphism^[동형사상]

자세한 내용은 [[Linear mapping]] 참조

### 위상수학^[Topology]에서

**Homeomorphism^[위상동형사상]** = continuous bijection with continuous inverse

Bijection만으로는 부족 - 연속성도 필요!

자세한 내용은 [[Topology]] 참조

### 측도론^[Measure Theory]에서

**Measurable function^[가측 함수]**: Bijection일 필요 없음
- Preimage of measurable sets must be measurable
- 함수의 injective/surjective 여부는 measurability와 독립적

### 응용

**암호학^[Cryptography]**:
- Encryption function은 bijective여야 복호화 가능

**컴퓨터 과학**:
- Hash function: 일반적으로 not injective (collision)
- Database keys: Injective mapping to records

**통계학^[Statistics]**:
- Probability transformations
- Change of variables (bijection 필요)

**집합론^[Set Theory]**:
- Cardinality 비교
- Countable vs uncountable sets

