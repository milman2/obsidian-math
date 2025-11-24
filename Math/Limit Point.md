# <span class="header-prerequisite">Prerequisite</span>
- [[Topology]]
- [[Open Set]]
- [[Interior, Closure, Boundary, Exterior in Topoloby]]

# <span class="header-reference">Reference</span>
- Munkres, Topology
- Rudin, Principles of Mathematical Analysis

---

# <span class="header-definition">Definition</span>

Topological space^[위상공간] $(X, \tau)$와 부분집합 $A \subseteq X$에 대해:

## Limit Point^[극한점]

점 $x \in X$가 $A$의 **limit point^[극한점]** (또는 **accumulation point^[축적점]**, **cluster point^[집적점]**)이다 $\Leftrightarrow$ 모든 open set^[열린 집합] $U \ni x$에 대해:

$$(U \setminus \{x\}) \cap A \neq \emptyset$$

즉, $x$의 모든 neighborhood^[근방]에 $x$ 자신을 제외한 $A$의 점이 적어도 하나 존재한다.

**표기**: $A$의 모든 limit point의 집합을 $A'$ (또는 $L(A)$, $\text{der}(A)$)로 표기

## Isolated Point^[고립점]

점 $x \in A$가 $A$의 **isolated point^[고립점]**이다 $\Leftrightarrow$ $x$가 $A$의 limit point가 아니다

즉, $\exists U \in \tau$ s.t. $x \in U$이고 $U \cap A = \{x\}$

## Adherent Point^[접촉점]

점 $x \in X$가 $A$의 **adherent point^[접촉점]**이다 $\Leftrightarrow$ 모든 open set $U \ni x$에 대해:

$$U \cap A \neq \emptyset$$

---

# <span class="header-properties">Properties</span>

### Closure와의 관계

$$\overline{A} = A \cup A'$$

즉, $A$의 closure^[폐포]는 $A$와 그 limit point들의 합집합

**따름정리:**
- $A$가 closed^[닫힌 집합] $\Leftrightarrow$ $A' \subseteq A$ $\Leftrightarrow$ $A = A \cup A'$
- $x \in \overline{A}$ $\Leftrightarrow$ $x \in A$ 또는 $x \in A'$

### Adherent Point와의 관계

Adherent point의 집합은 정확히 $\overline{A}$이다:

$$\text{Adherent points of } A = \overline{A} = A \cup A'$$

차이점:
- **Limit point**: $(U \setminus \{x\}) \cap A \neq \emptyset$ (자기 자신 제외)
- **Adherent point**: $U \cap A \neq \emptyset$ (자기 자신 포함 가능)

### Isolated Point와의 관계

$A$의 모든 점은 다음 중 정확히 하나:
1. Limit point of $A$
2. Isolated point of $A$

$$A = (A \cap A') \cup (A \setminus A')$$

### 기본 성질

1. $A \subseteq B \Rightarrow A' \subseteq B'$
2. $(A \cup B)' = A' \cup B'$
3. $(A')' \subseteq A'$ (일반적으로 등호 성립하지 않음)
4. $(\overline{A})' = A'$
5. $\emptyset' = \emptyset$

### Metric Space^[거리 공간]에서

Metric space $(X, d)$에서 $x \in X$가 $A$의 limit point $\Leftrightarrow$ 모든 $\epsilon > 0$에 대해:

$$(B(x, \epsilon) \setminus \{x\}) \cap A \neq \emptyset$$

동등하게: $\inf_{a \in A \setminus \{x\}} d(x, a) = 0$

---

# <span class="header-examples">Examples</span>

### Example 1: $\mathbb{R}$에서 구간

$A = (0, 1) \subseteq \mathbb{R}$ (standard topology):

- $A' = [0, 1]$
- 모든 $x \in (0, 1)$는 limit point
- $0$과 $1$도 limit point (하지만 $A$에 속하지 않음)
- Isolated point 없음

### Example 2: $\mathbb{R}$에서 정수

$A = \mathbb{Z} \subseteq \mathbb{R}$:

- $A' = \emptyset$ (limit point가 없음)
- 모든 점이 isolated point
- $\overline{A} = A = \mathbb{Z}$

### Example 3: $\mathbb{R}$에서 수열

$A = \{1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \ldots\} = \{\frac{1}{n} : n \in \mathbb{N}\}$:

- $A' = \{0\}$ (유일한 limit point)
- $0 \notin A$이지만 $0 \in A'$
- $A$의 모든 점은 isolated point
- $\overline{A} = A \cup \{0\}$

### Example 4: $\mathbb{R}$에서 유리수

$A = \mathbb{Q} \subseteq \mathbb{R}$:

- $A' = \mathbb{R}$ (모든 실수가 limit point)
- Isolated point 없음
- $\overline{A} = \mathbb{R}$

### Example 5: Discrete Topology^[이산 위상]

$(X, 2^X)$에서 임의의 부분집합 $A$:

- $A' = \emptyset$ (모든 점이 isolated)
- 모든 singleton $\{x\}$가 open이므로 limit point가 없음
- $\overline{A} = A$

### Example 6: Cofinite Topology^[여유한 위상]

무한집합 $X$에 cofinite topology에서 무한부분집합 $A$:

- $A' = X$ (모든 점이 limit point)
- Isolated point 없음

유한부분집합 $A$:
- $A' = \emptyset$ 또는 작은 집합

---

# <span class="header-theorem">Theorem</span>

### Bolzano-Weierstrass Theorem^[볼차노-바이어슈트라스 정리]

$\mathbb{R}^n$에서 모든 bounded^[유계] 무한집합은 적어도 하나의 limit point를 갖는다.

**증명 개요**: Compactness와 관련됨. [[Topology]]의 compact set 이론 참조.

### Characterization of Closed Sets

집합 $A$가 closed $\Leftrightarrow$ $A$가 자신의 모든 limit point를 포함

$$A \text{ is closed} \Leftrightarrow A' \subseteq A$$

### Sequential Characterization (Metric Space)

Metric space에서 $x \in A'$ $\Leftrightarrow$ $A \setminus \{x\}$의 점들로 이루어진 수열 $(x_n)$이 존재하여 $x_n \to x$

**주의**: 일반 topological space에서는 수열로 limit point를 특징지을 수 없음 (net이나 filter 필요)

---

# <span class="header-remark">Remark</span>

### 직관적 이해

- **Limit point**: 아무리 작은 근방을 택해도 $A$의 다른 점들이 "계속 나타나는" 점
- **Isolated point**: 주변에 "혼자" 있는 $A$의 점
- **Adherent point**: $A$에 "닿아 있는" 점 (limit point 또는 $A$의 원소)

### 이름의 유래

**Limit point**라는 이름은 metric space에서 수열의 극한(limit)과 관련:
- $x$가 $A$의 limit point $\Leftrightarrow$ $A$의 점들로 $x$에 수렴하는 수열 존재

**Accumulation point**는 점들이 $x$ 근처에 "축적(accumulate)"된다는 의미

**Cluster point**는 점들이 $x$ 주변에 "집적(cluster)"된다는 의미

### 해석학에서의 중요성

**연속성**: 함수 $f: X \to Y$가 $x$에서 연속 $\Leftrightarrow$ $x$가 $A$의 limit point이면 $f(x)$는 $f(A)$의 limit point 또는 $f(A)$에 속함

**수렴**: Metric space에서 수열 $(x_n)$의 극한 $x$는 $\{x_n : n \in \mathbb{N}\}$의 limit point

**완비성**: Complete metric space는 모든 Cauchy sequence가 수렴 (limit point를 가짐)

### Perfect Set^[완전 집합]

$A$가 **perfect^[완전]** $\Leftrightarrow$ $A = A'$ (closed이면서 isolated point가 없음)

예:
- $[0, 1] \subseteq \mathbb{R}$는 perfect
- Cantor set은 perfect이지만 interior가 비어있음
- $\mathbb{Q}$는 perfect가 아님 (closed가 아니고 $\mathbb{Q}' = \mathbb{R}$)

### Dense-in-itself^[자기조밀]

$A$가 **dense-in-itself^[자기조밀]** $\Leftrightarrow$ $A \subseteq A'$ (isolated point가 없음)

Perfect set는 closed이면서 dense-in-itself인 집합

### 일반화

**$\omega$-accumulation point**: 모든 neighborhood에 $A$의 점이 무한히 많이 존재

**Condensation point^[응축점]**: 모든 neighborhood에 $A$의 점이 uncountably many 존재

이러한 개념들은 descriptive set theory와 관련

