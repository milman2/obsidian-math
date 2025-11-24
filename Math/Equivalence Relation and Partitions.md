# <span class="header-prerequisite">Prerequisite</span>
- Set theory (집합론 기초)
- [[One-to-On, Onto]]

# <span class="header-reference">Reference</span>
- Halmos, Naive Set Theory
- Munkres, Topology

---

# <span class="header-definition">Definition</span>

## Relation^[관계]

집합 $X$에 대한 **relation^[관계]** $R$은 $X \times X$의 부분집합

$(x, y) \in R$일 때 $x \sim y$ 또는 $xRy$로 표기

## Equivalence Relation^[동치 관계]

집합 $X$에 대한 relation $\sim$이 **equivalence relation^[동치 관계]**이다 $\Leftrightarrow$ 다음 세 가지 성질을 만족:

### 1. Reflexivity^[반사성]

$$\forall x \in X, \quad x \sim x$$

모든 원소는 자기 자신과 관계됨

### 2. Symmetry^[대칭성]

$$\forall x, y \in X, \quad x \sim y \Rightarrow y \sim x$$

관계의 방향을 바꿀 수 있음

### 3. Transitivity^[추이성]

$$\forall x, y, z \in X, \quad x \sim y \text{ and } y \sim z \Rightarrow x \sim z$$

관계가 "전달"됨

## Equivalence Class^[동치류]

$x \in X$의 **equivalence class^[동치류]** $[x]$ (또는 $\bar{x}$, $\text{cl}(x)$)는:

$$[x] = \{y \in X : y \sim x\}$$

즉, $x$와 equivalence relation으로 관계된 모든 원소의 집합

## Quotient Set^[몫집합]

$X$의 모든 equivalence class의 모임을 **quotient set^[몫집합]** (또는 **quotient space^[몫공간]**)이라 하고 $X/\sim$로 표기:

$$X/\sim = \{[x] : x \in X\}$$

## Partition^[분할]

집합 $X$의 **partition^[분할]** $\mathcal{P}$는 $X$의 부분집합들의 모임으로, 다음을 만족:

1. $\emptyset \notin \mathcal{P}$ (공집합이 아닌 집합들)
2. $\bigcup_{A \in \mathcal{P}} A = X$ (전체를 덮음)
3. $A, B \in \mathcal{P}$이고 $A \neq B \Rightarrow A \cap B = \emptyset$ (서로소)

**직관**: $X$를 겹치지 않는 조각들로 나눔

---

# <span class="header-theorem">Theorem</span>

## Fundamental Theorem of Equivalence Relations

**정리**: Equivalence relation과 partition 사이에는 일대일 대응이 존재

### Part 1: Equivalence Relation $\Rightarrow$ Partition

$\sim$이 $X$의 equivalence relation이면, equivalence class들의 모임 $\{[x] : x \in X\}$는 $X$의 partition

**증명**:
1. $x \in [x]$ (reflexivity)이므로 $[x] \neq \emptyset$
2. $x \in [x]$이므로 $\bigcup [x] = X$
3. $[x] \neq [y]$이면 $[x] \cap [y] = \emptyset$ (아래 보조정리)

**보조정리**: $x \sim y \Leftrightarrow [x] = [y]$

**증명**:
- ($\Rightarrow$) $z \in [x] \Rightarrow z \sim x$. $x \sim y$이므로 (symmetry + transitivity) $z \sim y$, 즉 $z \in [y]$
- ($\Leftarrow$) $x \in [x] = [y]$이므로 $x \sim y$

### Part 2: Partition $\Rightarrow$ Equivalence Relation

$\mathcal{P}$가 $X$의 partition이면, 다음과 같이 정의된 relation은 equivalence relation:

$$x \sim y \Leftrightarrow \exists P \in \mathcal{P} \text{ such that } x, y \in P$$

즉, "같은 조각에 속함"

**증명**:
- **Reflexivity**: 각 $x$는 어떤 $P \in \mathcal{P}$에 속하므로 $x \sim x$
- **Symmetry**: $x, y \in P \Rightarrow y, x \in P$
- **Transitivity**: $x, y \in P$이고 $y, z \in Q$이면, $y \in P \cap Q$이므로 $P = Q$ (partition의 disjointness), 따라서 $x, z \in P$

### 일대일 대응

이 두 구성은 서로 역:
- Equivalence relation → Partition → 같은 equivalence relation
- Partition → Equivalence relation → 같은 partition

따라서:
$$\{\text{Equivalence relations on } X\} \leftrightarrow \{\text{Partitions of } X\}$$

---

# <span class="header-examples">Examples</span>

## Example 1: 정수의 합동^[Congruence]

$\mathbb{Z}$에서 $n \in \mathbb{N}$에 대해:

$$a \equiv b \pmod{n} \Leftrightarrow n \mid (a - b)$$

**Equivalence relation 확인**:
- **Reflexivity**: $n \mid 0$이므로 $a \equiv a$
- **Symmetry**: $n \mid (a-b) \Rightarrow n \mid (b-a)$
- **Transitivity**: $n \mid (a-b)$이고 $n \mid (b-c) \Rightarrow n \mid (a-c)$

**Equivalence classes**: $[0], [1], \ldots, [n-1]$

예: $n = 3$일 때
- $[0] = \{\ldots, -6, -3, 0, 3, 6, \ldots\}$
- $[1] = \{\ldots, -5, -2, 1, 4, 7, \ldots\}$
- $[2] = \{\ldots, -4, -1, 2, 5, 8, \ldots\}$

**Quotient set**: $\mathbb{Z}/n\mathbb{Z} = \{[0], [1], \ldots, [n-1]\}$

## Example 2: 유리수의 구성

$\mathbb{Z} \times (\mathbb{Z} \setminus \{0\})$에서:

$$(a, b) \sim (c, d) \Leftrightarrow ad = bc$$

**직관**: "같은 분수"

**Equivalence classes**: $[(a, b)] = \{\text{all representations of } \frac{a}{b}\}$

예: $[(1, 2)] = \{(1, 2), (2, 4), (3, 6), (-1, -2), \ldots\}$

**유리수**: $\mathbb{Q} = (\mathbb{Z} \times (\mathbb{Z} \setminus \{0\}))/\sim$

## Example 3: 집합의 Cardinality^[기수]

집합들의 모임에서:

$$A \sim B \Leftrightarrow \exists \text{ bijection } f: A \to B$$

**Equivalence classes**: 같은 크기를 가진 집합들

예:
- $[\{1, 2, 3\}] = \{\text{all 3-element sets}\}$
- $[\mathbb{N}] = \{\text{all countable infinite sets}\}$

**Cardinality**: $|A|$는 $A$의 equivalence class

## Example 4: 행렬의 Similar^[닮음]

$n \times n$ 행렬들의 집합에서:

$$A \sim B \Leftrightarrow \exists \text{ invertible } P \text{ s.t. } B = P^{-1}AP$$

**Equivalence classes**: 같은 Jordan canonical form^[조르단 표준형]을 가진 행렬들

## Example 5: 기하학적 도형의 합동

평면 도형들의 모임에서:

$$F \sim G \Leftrightarrow F \text{ is congruent to } G$$

즉, $F$가 $G$로 rigid motion^[강체 운동] (평행이동, 회전, 대칭 등)으로 변환 가능

**Equivalence classes**: "같은 모양"을 가진 도형들

## Example 6: 함수의 같은 극한값

$\mathbb{R} \to \mathbb{R}$ 함수들의 모임에서:

$$f \sim g \Leftrightarrow \lim_{x \to a} f(x) = \lim_{x \to a} g(x)$$

(고정된 $a \in \mathbb{R}$)

**Equivalence classes**: 같은 점에서 같은 극한값을 가진 함수들

## Example 7: Topological Space의 Homotopy^[호모토피]

연속함수 $f, g: X \to Y$에 대해:

$$f \sim g \Leftrightarrow f \text{ is homotopic to } g$$

**Equivalence classes**: Homotopy classes

자세한 내용은 [[Topology/Algebraic Topology]] 참조

---

# <span class="header-properties">Properties</span>

### Representative^[대표원]

각 equivalence class $[x]$에서 하나씩 선택한 원소를 **representative^[대표원]**이라 함

모든 equivalence class의 representative들의 집합을 **complete set of representatives^[완전 대표계]**라 함

**예**: $\mathbb{Z}/3\mathbb{Z}$의 complete set of representatives: $\{0, 1, 2\}$ (또는 $\{3, 4, 5\}$ 등)

### Canonical Projection^[표준 사영]

$$\pi: X \to X/\sim, \quad \pi(x) = [x]$$

$\pi$는 항상 surjective^[전사]

**Universal property^[보편 성질]**: 함수 $f: X \to Y$가 $x \sim y \Rightarrow f(x) = f(y)$를 만족하면, 유일한 함수 $\bar{f}: X/\sim \to Y$가 존재하여 $f = \bar{f} \circ \pi$

```
X --π--> X/∼
 \      /
  f   f̄
   \ /
    Y
```

### Refinement^[세분화]

Partition $\mathcal{P}_1$이 $\mathcal{P}_2$의 **refinement^[세분화]**이다 $\Leftrightarrow$ 모든 $P_1 \in \mathcal{P}_1$에 대해 $P_2 \in \mathcal{P}_2$가 존재하여 $P_1 \subseteq P_2$

**동등한 조건**: $\mathcal{P}_1$에 대응하는 equivalence relation이 $\mathcal{P}_2$에 대응하는 것보다 "더 세밀"

### Well-definedness^[잘 정의됨]

Quotient set에 연산을 정의할 때, **representative의 선택과 무관**해야 함

**예**: $\mathbb{Z}/n\mathbb{Z}$에서 덧셈:
$$[a] + [b] = [a + b]$$

**Well-defined 확인**: $a \equiv a'$이고 $b \equiv b'$이면 $a + b \equiv a' + b'$인가?
- $n \mid (a - a')$이고 $n \mid (b - b')$
- $\Rightarrow n \mid ((a+b) - (a'+b'))$ ✓

---

# <span class="header-remark">Remark</span>

### 직관적 이해

**Equivalence relation**: "같다고 볼 수 있는" 관계
- 예: "같은 생일", "같은 학년", "같은 크기"

**Equivalence class**: 서로 "같다고 여겨지는" 원소들의 그룹

**Partition**: 전체 집합을 겹치지 않는 그룹들로 나눔
- 예: 사람들을 생일로 분류, 학생들을 학년으로 분류

**핵심 통찰**: 
> "어떤 것들을 같다고 볼 것인가?"를 정하는 것 = "어떻게 분류할 것인가?"를 정하는 것

### 용어

| 개념 | 영어 | 기호 |
|------|------|------|
| 동치 관계 | Equivalence relation | $\sim$ |
| 동치류 | Equivalence class | $[x]$ |
| 몫집합 | Quotient set | $X/\sim$ |
| 분할 | Partition | $\mathcal{P}$ |
| 대표원 | Representative | - |

### 선형대수에서의 응용

**Vector space quotient**: $V/W$ where $W \subseteq V$ is a subspace

$$v_1 \sim v_2 \Leftrightarrow v_1 - v_2 \in W$$

**Equivalence classes**: Cosets^[코셋] $v + W = \{v + w : w \in W\}$

**차원**: $\dim(V/W) = \dim(V) - \dim(W)$

자세한 내용은 [[Linear mapping]] 참조

### 군론^[Group Theory]에서

**Normal subgroup^[정규 부분군]** $H \triangleleft G$에 대해:

$$g_1 \sim g_2 \Leftrightarrow g_1 g_2^{-1} \in H$$

**Quotient group^[몫군]**: $G/H$ with operation $[g_1][g_2] = [g_1 g_2]$

### 위상수학에서

**Quotient topology^[몫 위상]**: $X/\sim$에 canonical projection $\pi: X \to X/\sim$이 continuous가 되도록 하는 finest topology

**응용**: 
- Torus = Square with opposite edges identified
- Projective space = Sphere with antipodal points identified

자세한 내용은 [[Topology]] 참조

### 범주론^[Category Theory]에서

**Quotient = Coequalizer**

Equivalence relation은 category theory에서 coequalizer로 일반화됨

자세한 내용은 [[Category Theory]] 참조

### 실용적 응용

**컴퓨터 과학**:
- Union-Find 자료구조
- Disjoint-set data structure
- Graph connectivity

**데이터베이스**:
- Grouping과 aggregation
- Partitioning strategies

**물리학**:
- Gauge equivalence
- Symmetry groups

**프로그래밍**:
- Hash table (collision = equivalence)
- Object equality

### 역사적 배경

Equivalence relation과 partition의 개념은 현대 수학의 가장 기본적인 도구 중 하나

**발전 과정**:
- 19세기: 합동 관계 (Gauss)
- 20세기 초: 추상화 및 일반화
- 현대: 범주론적 관점

**중요성**: 
- "같음"의 개념을 일반화
- 분류와 구조화의 수학적 기초
- 거의 모든 수학 분야에서 사용

### Common Pitfall^[흔한 실수]

**잘못된 예**:

$\mathbb{R}$에서 $x \sim y \Leftrightarrow x < y$

- Reflexivity: ✗ ($x \not< x$)
- Symmetry: ✗ ($x < y \not\Rightarrow y < x$)
- Transitivity: ✓

$\Rightarrow$ Equivalence relation이 **아님** (이것은 order relation^[순서 관계])

**Tip**: 세 가지 조건을 **모두** 확인해야 함!

