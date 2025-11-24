# <span class="header-prerequisite">Prerequisite</span>
- [[Topology]]
- [[Open Set]]

# <span class="header-reference">Reference</span>
- Munkres, Topology
- Kelley, General Topology

---

# <span class="header-definition">Definition</span>

Topological space^[위상공간] $(X, \tau)$와 점 $x \in X$에 대해:

## Neighborhood^[근방]

집합 $N \subseteq X$가 $x$의 **neighborhood^[근방]**이다 $\Leftrightarrow$ $x \in U \subseteq N$인 open set^[열린 집합] $U \in \tau$가 존재한다.

즉, $N$은 $x$를 포함하는 어떤 open set을 포함한다.

**중요**: Neighborhood는 open일 필요가 없다!

## Open Neighborhood^[열린 근방]

$x$의 neighborhood $N$이 **open neighborhood^[열린 근방]**이다 $\Leftrightarrow$ $N \in \tau$ (즉, $N$이 open set)

## Neighborhood System^[근방계]

점 $x \in X$의 모든 neighborhood의 모임을 $x$의 **neighborhood system^[근방계]** (또는 **neighborhood filter^[근방 필터]**)라 하고 $\mathcal{N}(x)$ (또는 $\mathcal{N}_x$)로 표기:

$$\mathcal{N}(x) = \{N \subseteq X : N \text{ is a neighborhood of } x\}$$

## Neighborhood Base^[근방 기저]

집합족 $\mathcal{B}(x) \subseteq \mathcal{N}(x)$가 $x$의 **neighborhood base^[근방 기저]** (또는 **local base^[국소 기저]**)이다 $\Leftrightarrow$ 모든 $N \in \mathcal{N}(x)$에 대해 $B \in \mathcal{B}(x)$가 존재하여 $B \subseteq N$

즉, 모든 neighborhood가 neighborhood base의 원소로 "근사"될 수 있다.

---

# <span class="header-properties">Properties</span>

### Neighborhood System의 성질

$\mathcal{N}(x)$는 다음을 만족:

1. $N \in \mathcal{N}(x) \Rightarrow x \in N$
2. $N \in \mathcal{N}(x)$이고 $N \subseteq M \Rightarrow M \in \mathcal{N}(x)$
3. $N_1, N_2 \in \mathcal{N}(x) \Rightarrow N_1 \cap N_2 \in \mathcal{N}(x)$
4. $N \in \mathcal{N}(x) \Rightarrow \exists M \in \mathcal{N}(x)$ s.t. $M \subseteq N$이고 $M \in \mathcal{N}(y)$ for all $y \in M$

**역으로**: 이러한 조건을 만족하는 filter $\mathcal{N}(x)$들이 주어지면 유일한 topology가 정의됨

### Open Set의 Neighborhood 특징화

$U \subseteq X$가 open $\Leftrightarrow$ 모든 $x \in U$에 대해 $U \in \mathcal{N}(x)$

즉, open set는 자신의 모든 점의 neighborhood

### Interior의 Neighborhood 특징화

$$x \in \text{int}(A) \Leftrightarrow A \in \mathcal{N}(x)$$

즉, $\text{int}(A) = \{x \in X : A \in \mathcal{N}(x)\}$

### Closure의 Neighborhood 특징화

$$x \in \overline{A} \Leftrightarrow \forall N \in \mathcal{N}(x), N \cap A \neq \emptyset$$

즉, $x$의 모든 neighborhood가 $A$와 만난다

### Limit Point의 Neighborhood 특징화

$$x \in A' \Leftrightarrow \forall N \in \mathcal{N}(x), (N \setminus \{x\}) \cap A \neq \emptyset$$

자세한 내용은 [[Limit Point]] 참조

---

# <span class="header-examples">Examples</span>

### Example 1: $\mathbb{R}$의 Standard Topology

점 $x \in \mathbb{R}$에 대해:

**Open neighborhoods**: $(x - \epsilon, x + \epsilon)$ for any $\epsilon > 0$

**General neighborhoods**: 
- $[x - \epsilon, x + \epsilon]$
- $(x - \epsilon, x + \epsilon]$
- $(x - 1, x + 2)$
- $\mathbb{R}$ 자체

**Neighborhood base**: $\{(x - \frac{1}{n}, x + \frac{1}{n}) : n \in \mathbb{N}\}$

### Example 2: $\mathbb{R}^n$의 Euclidean Topology

점 $\mathbf{x} \in \mathbb{R}^n$에 대해:

**Open neighborhoods**: Open balls $B(\mathbf{x}, \epsilon) = \{\mathbf{y} : \|\mathbf{y} - \mathbf{x}\| < \epsilon\}$

**Neighborhood base**: $\{B(\mathbf{x}, \frac{1}{n}) : n \in \mathbb{N}\}$ (countable base)

### Example 3: Discrete Topology^[이산 위상]

$(X, 2^X)$에서 모든 점 $x$:

모든 부분집합이 open이므로:
- $x$의 가장 작은 neighborhood: $\{x\}$ (singleton)
- 모든 $x$를 포함하는 집합이 neighborhood
- Neighborhood base: $\{\{x\}\}$

### Example 4: Indiscrete Topology^[비이산 위상]

$(X, \{\emptyset, X\})$에서 모든 점 $x$:

- 유일한 open neighborhood: $X$
- 모든 neighborhood는 $X$와 같음 (다른 선택지 없음)
- $\mathcal{N}(x) = \{X\}$

### Example 5: Metric Space^[거리 공간]

Metric space $(X, d)$에서 점 $x$:

**$\epsilon$-neighborhood**: $B(x, \epsilon) = \{y \in X : d(x, y) < \epsilon\}$

**Neighborhood base**: $\{B(x, \epsilon) : \epsilon > 0\}$ 또는 $\{B(x, \frac{1}{n}) : n \in \mathbb{N}\}$

모든 metric space는 countable local base를 가짐 (first-countable)

---

# <span class="header-theorem">Theorem</span>

### Continuity의 Neighborhood 특징화

함수 $f: X \to Y$가 $x \in X$에서 **continuous^[연속]** $\Leftrightarrow$ $f(x)$의 모든 neighborhood $V$에 대해, $f^{-1}(V)$는 $x$의 neighborhood

$$\forall V \in \mathcal{N}(f(x)), f^{-1}(V) \in \mathcal{N}(x)$$

**동등한 정의** (neighborhood base 사용):
$f$가 $x$에서 continuous $\Leftrightarrow$ $f(x)$의 neighborhood base $\mathcal{B}(f(x))$에 대해, 모든 $V \in \mathcal{B}(f(x))$에 대해 $f^{-1}(V) \in \mathcal{N}(x)$

### Convergence의 Neighborhood 특징화

Topological space에서 net^[망] $(x_\alpha)$가 $x$로 **converge^[수렴]** $\Leftrightarrow$ 모든 $N \in \mathcal{N}(x)$에 대해, $\alpha_0$가 존재하여 $\alpha \geq \alpha_0 \Rightarrow x_\alpha \in N$

Metric space에서 수열 $(x_n)$이 $x$로 수렴 $\Leftrightarrow$ 모든 $\epsilon > 0$에 대해 $N$이 존재하여 $n \geq N \Rightarrow x_n \in B(x, \epsilon)$

---

# <span class="header-remark">Remark</span>

### 직관적 이해

Neighborhood는 점 $x$ "주변"의 집합이다. $x$의 neighborhood는:
- $x$를 "포함"하면서
- $x$ "가까이"에 있는 점들을 포함
- $x$에서 "약간 벗어나도" 여전히 포함됨

Neighborhood는 topological space에서 "근처", "가까움"의 개념을 형식화

### 정의의 변형

**문헌마다 다른 정의**:

1. **일반적 정의** (이 노트 사용): Neighborhood는 open set을 포함하는 집합 (open일 필요 없음)
2. **대안 정의** (일부 교재): Neighborhood는 항상 open (= open neighborhood)

두 정의는 대부분의 결과에서 동일하나, 명시적으로 확인 필요

이 노트에서는 **일반적 정의**를 사용하며, open일 때 "open neighborhood"로 명시

### First-Countability^[제1 가산성]

Topological space $X$가 **first-countable^[제1 가산]** $\Leftrightarrow$ 모든 점 $x \in X$가 countable neighborhood base를 가짐

**예시**:
- 모든 metric space는 first-countable
- $\mathbb{R}^n$는 first-countable
- Uncountable product $\prod_{i \in I} X_i$ (with product topology)는 일반적으로 first-countable이 아님

**중요성**: First-countable space에서는 수열(sequence)만으로 topological 성질을 특징지을 수 있음

### Second-Countability^[제2 가산성]

Topological space $X$가 **second-countable^[제2 가산]** $\Leftrightarrow$ $X$가 countable basis (for topology)를 가짐

Second-countable $\Rightarrow$ First-countable (역은 거짓)

**예시**:
- $\mathbb{R}^n$는 second-countable (basis: open balls with rational centers and radii)
- Separable metric space는 second-countable

### Hausdorff Space와 Neighborhood

Topological space $X$가 **Hausdorff^[하우스도르프]** $\Leftrightarrow$ 서로 다른 점 $x, y$에 대해 disjoint neighborhoods $N_x, N_y$가 존재:

$$\forall x, y \in X, x \neq y \Rightarrow \exists N_x \in \mathcal{N}(x), N_y \in \mathcal{N}(y) \text{ s.t. } N_x \cap N_y = \emptyset$$

Hausdorff 조건은 topology가 "점들을 충분히 구분"하는 조건

### Filter Theory와의 관계

Neighborhood system $\mathcal{N}(x)$는 **filter^[필터]**의 예시:
- $\emptyset \notin \mathcal{N}(x)$
- $N_1, N_2 \in \mathcal{N}(x) \Rightarrow N_1 \cap N_2 \in \mathcal{N}(x)$
- $N \in \mathcal{N}(x)$이고 $N \subseteq M \Rightarrow M \in \mathcal{N}(x)$

Filter theory는 general topology와 convergence를 연구하는 강력한 도구

### 응용

**해석학**: 함수의 극한, 연속성, 미분 정의

**위상수학**: Compactness, connectedness 등의 성질 연구

**함수해석학**: Weak topology, weak* topology에서 convergence

**확률론**: Convergence in probability, convergence in distribution

