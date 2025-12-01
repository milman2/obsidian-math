# <span class="header-prerequisite">Prerequisite</span>
- [[Topology]]
- [[Open Set]]
- [[Metric Space]]
- [[Sequence]]
- [[Interior, Closure, Boundary, Exterior in Topoloby]]

# <span class="header-reference">Reference</span>
- Munkres, Topology
- Rudin, Principles of Mathematical Analysis
- Folland, Real Analysis

---

# <span class="header-definition">Definition</span>

## Compact Set^[컴팩트 집합]

Topological space^[위상공간] $(X, \tau)$와 부분집합 $K \subseteq X$에 대해:

### Open Cover^[열린 덮개]

집합족 $\{U_\alpha\}_{\alpha \in I}$ (where $U_\alpha \in \tau$)가 $K$의 **open cover^[열린 덮개]**이다 $\Leftrightarrow$

$$K \subseteq \bigcup_{\alpha \in I} U_\alpha$$

### Compact

$K$가 **compact^[컴팩트]**이다 $\Leftrightarrow$ 모든 open cover가 **finite subcover^[유한 부분덮개]**를 가짐

즉, $K$의 임의의 open cover $\{U_\alpha\}_{\alpha \in I}$에 대해 유한 개의 index $\alpha_1, \ldots, \alpha_n$이 존재하여:

$$K \subseteq U_{\alpha_1} \cup U_{\alpha_2} \cup \cdots \cup U_{\alpha_n}$$

**직관**: "무한한 덮개를 유한하게 줄일 수 있다"

## Sequentially Compact^[수열 컴팩트]

Metric space^[거리공간] $(X, d)$에서 $K \subseteq X$가 **sequentially compact^[수열 컴팩트]**이다 $\Leftrightarrow$

$K$의 모든 수열 $(x_n) \subseteq K$가 $K$에서 수렴하는 subsequence^[부분수열]를 가짐

**동등 조건**: 모든 infinite sequence in $K$ has a convergent subsequence with limit in $K$

## Limit Point Compact^[극한점 컴팩트]

$K \subseteq X$가 **limit point compact^[극한점 컴팩트]**이다 $\Leftrightarrow$

$K$의 모든 infinite subset^[무한 부분집합]이 $K$에서 limit point^[극한점]를 가짐

---

# <span class="header-theorem">Theorems</span>

## Equivalence in Metric Spaces^[거리공간에서의 동치]

**정리**: Metric space $(X, d)$에서 $K \subseteq X$에 대해 다음은 동등:

1. $K$ is compact
2. $K$ is sequentially compact
3. $K$ is limit point compact

**증명 개요**:
- (1) $\Rightarrow$ (3): Open cover로부터 모순 유도
- (3) $\Rightarrow$ (2): Limit point를 subsequence의 극한으로 사용
- (2) $\Rightarrow$ (1): Lebesgue number lemma 사용

**주의**: 일반 topological space에서는 이들이 동등하지 않을 수 있음!

## Heine-Borel Theorem^[하이네-보렐 정리]

**정리** (**Heine-Borel Theorem**):

$\mathbb{R}^n$에서 $K \subseteq \mathbb{R}^n$에 대해:

$$K \text{ is compact} \Leftrightarrow K \text{ is closed and bounded}$$

**증명 개요**:

$(\Rightarrow)$ Compact $\Rightarrow$ Closed and Bounded:
- Closed: Complement의 점들을 분리하는 open sets 사용
- Bounded: Open balls로 덮개 구성

$(\Leftarrow)$ Closed and Bounded $\Rightarrow$ Compact:
- Bounded이므로 큰 box에 포함
- Box는 compact (Tychonoff's theorem 또는 직접 증명)
- Closed subset of compact is compact

**중요성**: $\mathbb{R}^n$에서 compactness를 쉽게 판정 가능!

## Properties of Compact Sets^[컴팩트 집합의 성질]

### 1. Closed Subsets

**정리**: Compact space $X$에서 모든 closed^[닫힌] subset은 compact

**증명**: Closed subset의 open cover를 전체 공간의 open cover로 확장

### 2. Closed in Hausdorff

**정리**: Hausdorff space^[하우스도르프 공간] $X$에서 모든 compact subset은 closed

**증명**: Compact set의 complement가 open임을 보임 (separation 이용)

### 3. Intersection

**정리**: Nested decreasing compact sets의 교집합은 비어있지 않음

$$K_1 \supseteq K_2 \supseteq K_3 \supseteq \cdots, \quad K_i \text{ compact} \Rightarrow \bigcap_{i=1}^{\infty} K_i \neq \emptyset$$

(Hausdorff space에서)

## Continuous Images^[연속상]

**정리**: Continuous function의 compact set의 image는 compact

$$f: X \to Y \text{ continuous}, \quad K \subseteq X \text{ compact} \Rightarrow f(K) \text{ compact}$$

**증명**: $f(K)$의 open cover를 $K$의 open cover로 끌어올림 (continuous의 정의)

**따름정리**:

1. **Extreme Value Theorem^[최대최소 정리]**: 
   $$f: K \to \mathbb{R} \text{ continuous}, \quad K \text{ compact} \Rightarrow f \text{ attains max and min}$$

2. **Uniform Continuity^[균등 연속성]**:
   $$f: K \to \mathbb{R} \text{ continuous}, \quad K \text{ compact} \Rightarrow f \text{ uniformly continuous}$$

## Finite Intersection Property^[유한 교집합 성질]

**정리**: $K$ is compact $\Leftrightarrow$ 다음을 만족:

Closed sets $\{F_\alpha\}_{\alpha \in I}$가 finite intersection property^[유한 교집합 성질]를 가지면 (즉, 모든 유한 부분집합의 교집합이 비어있지 않으면):

$$\bigcap_{\alpha \in I} F_\alpha \neq \emptyset$$

**증명**: Open cover characterization의 dual

## Bolzano-Weierstrass Theorem^[볼차노-바이어슈트라스 정리]

**정리**: $\mathbb{R}^n$에서 모든 bounded^[유계] infinite subset은 limit point를 가짐

**연결**: Heine-Borel + Sequential compactness

자세한 내용은 [[Limit Point]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Closed Intervals^[닫힌 구간]

$$K = [a, b] \subseteq \mathbb{R}$$

**Compact**: Yes ✓
- Closed: Yes (complement is union of open intervals)
- Bounded: Yes ($|x| \leq \max\{|a|, |b|\}$)
- Heine-Borel: Closed + Bounded $\Rightarrow$ Compact

## Example 2: Open Intervals^[열린 구간]

$$K = (a, b) \subseteq \mathbb{R}$$

**Compact**: No ✗
- Not closed
- Cover $\{(a + \frac{1}{n}, b - \frac{1}{n})\}_{n=3}^{\infty}$는 finite subcover가 없음

## Example 3: Closed Unbounded^[닫히고 비유계]

$$K = [0, \infty) \subseteq \mathbb{R}$$

**Compact**: No ✗
- Closed: Yes
- Bounded: No
- Cover $\{(-n, n)\}_{n=1}^{\infty}$는 finite subcover가 없음

## Example 4: Finite Sets^[유한 집합]

$$K = \{x_1, x_2, \ldots, x_n\}$$

**Compact**: Always Yes ✓
- 모든 topology에서 finite set은 compact
- Open cover의 각 점마다 하나씩 선택하면 유한 subcover

## Example 5: Unit Ball^[단위 공]

### Closed Unit Ball

$$K = \{x \in \mathbb{R}^n : \|x\| \leq 1\}$$

**Compact**: Yes ✓ (closed and bounded)

### Open Unit Ball

$$K = \{x \in \mathbb{R}^n : \|x\| < 1\}$$

**Compact**: No ✗ (not closed)

## Example 6: $\mathbb{N}$ in Discrete Topology

$$K = \mathbb{N}$$ with discrete topology^[이산 위상]

**Compact**: No ✗
- Cover $\{\{n\}\}_{n=1}^{\infty}$는 finite subcover가 없음
- Discrete topology에서 infinite set은 non-compact

## Example 7: Cantor Set^[칸토어 집합]

$$K = \text{Cantor set} \subseteq [0, 1]$$

**Compact**: Yes ✓
- Closed subset of compact set $[0, 1]$
- 따라서 compact

**성질**:
- Perfect set (no isolated points)
- Uncountable
- Measure zero

## Example 8: $\mathbb{Q} \cap [0, 1]$

$$K = \mathbb{Q} \cap [0, 1]$$

**Compact**: No ✗
- Not closed in $\mathbb{R}$ ($\overline{K} = [0, 1]$)
- Countable dense subset

## Example 9: Hilbert Cube^[힐베르트 입방체]

$$K = \left\{(x_n) \in \ell^2 : |x_n| \leq \frac{1}{n}\right\}$$

**Compact**: Yes ✓ (Tychonoff's theorem)

## Example 10: Sphere^[구]

$$S^{n-1} = \{x \in \mathbb{R}^n : \|x\| = 1\}$$

**Compact**: Yes ✓
- Closed: Preimage of $\{1\}$ under continuous map $x \mapsto \|x\|$
- Bounded: $\|x\| = 1$

---

# <span class="header-properties">Properties</span>

## Total Boundedness^[전체 유계성]

**정의**: Metric space $(X, d)$에서 $K$가 **totally bounded^[전체 유계]**이다 $\Leftrightarrow$

모든 $\epsilon > 0$에 대해 유한 개의 $\epsilon$-balls로 $K$를 덮을 수 있음

**정리**: Compact $\Rightarrow$ Totally bounded + Complete

Metric space에서: Compact $\Leftrightarrow$ Complete + Totally bounded

## Local Compactness^[국소 컴팩트성]

**정의**: Topological space $X$가 **locally compact^[국소 컴팩트]**이다 $\Leftrightarrow$

모든 점 $x \in X$가 compact neighborhood^[컴팩트 근방]를 가짐

**예**:
- $\mathbb{R}^n$: Locally compact ✓
- Hilbert space $\ell^2$: Not locally compact ✗
- Discrete space: Locally compact ✓

## Compactification^[컴팩트화]

비컴팩트 공간을 컴팩트 공간에 매장하는 방법:

### One-Point Compactification^[일점 컴팩트화]

Locally compact Hausdorff space $X$에 점 $\infty$ 추가:

$$X^* = X \cup \{\infty\}$$

**예**: $\mathbb{R}^n$의 일점 컴팩트화는 $S^n$ (구)

### Stone-Čech Compactification

가장 큰 컴팩트화 (universal property)

## Tychonoff's Theorem^[티호노프 정리]

**정리** (**Tychonoff's Theorem**):

Compact spaces의 임의의 곱^[product]은 compact (product topology^[곱 위상]에서)

$$\prod_{\alpha \in I} K_\alpha \text{ compact} \Leftrightarrow \text{each } K_\alpha \text{ compact}$$

**중요성**: 
- Choice axiom과 동치
- Functional analysis에서 중요 (Banach-Alaoglu theorem)

## Compactness and Separation Axioms^[분리 공리]

### Hausdorff Space

Compact Hausdorff space $X$:
- Normal space^[정규 공간]
- Compact subsets는 closed
- 좋은 성질 많음

### Non-Hausdorff

Compact이지만 non-Hausdorff:
- Limit points가 유일하지 않을 수 있음
- 덜 유용

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Compactness**: "유한성의 일반화"

**세 가지 관점**:

1. **Open cover**: 무한한 덮개 → 유한하게 축소
2. **Sequential**: 모든 수열 → 수렴하는 부분수열 존재
3. **Limit point**: 무한 집합 → 축적점 존재

**기하학적**: "작고 닫힌" 공간

**해석학적**: "좋은 성질"을 많이 가짐

## Compactness vs Closedness vs Boundedness

| | Compact | Closed | Bounded |
|---|---------|--------|---------|
| **$\mathbb{R}^n$** | Closed + Bounded | ✓ | ✓ |
| **General metric** | Complete + Totally bounded | ✓ | ? |
| **General topology** | Finite subcover | ? | N/A |

**주의**: 
- 일반 metric space: Closed + Bounded $\not\Rightarrow$ Compact
- 예: $\ell^2$의 unit ball (closed + bounded but not compact)

## 응용 분야

### 1. Optimization^[최적화]

**Extreme Value Theorem**: Continuous function on compact set attains max/min

$$f: K \to \mathbb{R}, \quad K \text{ compact} \Rightarrow \exists x_0 \in K: f(x_0) = \max f(K)$$

**응용**: 최적화 문제의 해 존재성 보장

### 2. Functional Analysis^[함수해석학]

**Banach-Alaoglu Theorem**: Unit ball in dual space is weak* compact

**Arzela-Ascoli Theorem**: 함수 공간에서의 compactness 특징

### 3. Topology^[위상수학]

**Fundamental group**: Compact spaces의 covering space theory

**Homology**: Compact spaces는 좋은 homological 성질

### 4. Differential Geometry^[미분기하]

**Compact manifolds**: 좋은 global 성질
- Finite volume
- Complete geodesics

### 5. Partial Differential Equations

**Compact embedding**: Sobolev spaces

**Existence of solutions**: Compactness arguments

### 6. Probability Theory^[확률론]

**Prohorov's Theorem**: Tight families of measures

**Convergence**: Compactness in distribution spaces

## 역사적 배경

**19세기**:
- **Bolzano, Weierstrass**: 유계 수열의 수렴하는 부분수열
- **Heine, Borel**: 유한 덮개 성질

**20세기**:
- **Fréchet**: Metric spaces로 일반화
- **Hausdorff**: General topology
- **Tychonoff**: Product theorem

**현대**: 
- Category theory
- Pointless topology
- Applications in analysis

## Compactness in Different Contexts^[다양한 맥락에서의 컴팩트성]

### Metric Spaces

**특징**: Sequential compactness = Compactness

**판정**: Complete + Totally bounded

### $\mathbb{R}^n$

**특징**: Closed + Bounded (Heine-Borel)

**쉬운 판정**: 매우 유용!

### Function Spaces

**Arzela-Ascoli**: Equicontinuity + pointwise boundedness

**응용**: ODE theory, approximation

### Measure Spaces

**Weak compactness**: Probability measures

**Tightness**: Control at infinity

## Common Patterns^[일반적 패턴]

### Pattern 1: Existence

Compact $\Rightarrow$ 최댓값/최솟값 존재

**응용**: Optimization, variational problems

### Pattern 2: Finiteness

Infinite → Finite (subcover, subsequence)

**응용**: Combinatorial arguments

### Pattern 3: Continuity

Continuous → Uniform continuous (on compact)

**응용**: Analysis, approximation

## Common Pitfalls^[흔한 실수]

### 1. Closed + Bounded ≠ Compact (일반적으로)

✗ 모든 metric space에서 closed + bounded = compact?

✓ $\mathbb{R}^n$에서만! (Heine-Borel)

**반례**: $\ell^2$ (infinite-dimensional Hilbert space)
- Unit ball: closed + bounded but NOT compact

### 2. Compact ≠ Bounded (일반 topology)

"Bounded"는 metric 개념

일반 topology에서는 정의 불가

### 3. Sequential Compactness ≠ Compactness (일반적으로)

✗ 모든 topological space에서 동등?

✓ Metric space에서만 동등

**반례**: Certain non-metrizable spaces

### 4. Countable Compactness

**Countably compact**: 모든 countable open cover가 finite subcover

Compact $\Rightarrow$ Countably compact

역은 일반적으로 거짓 (first-countable space에서는 참)

### 5. Compactness of Subsets

✗ $A \subseteq B$, $B$ compact $\Rightarrow$ $A$ compact?

✓ $A$ **closed** in $B$, $B$ compact $\Rightarrow$ $A$ compact

**핵심**: Closed subset 필요!

## Why Compactness Matters^[컴팩트성이 중요한 이유]

**1. Existence Theorems**: 최적화 문제의 해 존재

**2. Uniform Properties**: Continuity → Uniform continuity

**3. Finiteness**: 무한 → 유한으로 축소

**4. Completeness**: "구멍 없는" 공간

**5. Good Approximation**: 유한 차원 근사 가능

## Equivalent Definitions (Summary)^[동치 정의 요약]

Metric space $(X, d)$에서 $K \subseteq X$:

| 정의 | 조건 |
|------|------|
| **Compact** | 모든 open cover → finite subcover |
| **Sequentially compact** | 모든 sequence → convergent subsequence |
| **Limit point compact** | 모든 infinite subset → limit point |
| **Complete + Totally bounded** | Cauchy complete + $\epsilon$-net |

**$\mathbb{R}^n$에서**: **Closed + Bounded** (Heine-Borel)

## 관련 개념

- [[Topology]]: Compactness의 일반적 framework
- [[Metric Space]]: Sequential compactness
- [[Sequence]]: 부분수열과 수렴
- [[Limit Point]]: Bolzano-Weierstrass theorem
- [[Open Set]]: Open cover의 정의
- [[Convergence and Divergence in Sequences]]: 수렴 개념
- [[Interior, Closure, Boundary, Exterior in Topoloby]]: Closed sets

