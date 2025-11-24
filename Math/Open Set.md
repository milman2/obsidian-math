# <span class="header-prerequisite">Prerequisite</span>
- [[Topology]]
- [[Measure Space]]

# <span class="header-reference">Reference</span>
- Munkres, Topology

---

# <span class="header-definition">Definition</span>

**Topological space^[위상공간]** $(X, \tau)$에서 **open set^[열린 집합]**은 topology^[위상] $\tau$의 원소를 말한다.

즉, $U \subseteq X$가 open set $\Leftrightarrow$ $U \in \tau$

### Topology의 공리로부터 유도되는 성질

1. $\emptyset$와 $X$는 open set
2. Open set들의 임의의 합집합(arbitrary union)은 open set
3. Open set들의 유한 교집합(finite intersection)은 open set

---

# <span class="header-examples">Examples</span>

### Metric Space^[거리 공간]에서의 Open Set

Metric space^[거리 공간] $(X, d)$에서 $U \subseteq X$가 open $\Leftrightarrow$ 모든 $x \in U$에 대해 $\epsilon > 0$가 존재하여 $B(x, \epsilon) \subseteq U$

여기서 $B(x, \epsilon) = \{y \in X : d(x, y) < \epsilon\}$는 **open ball^[열린 공]**

### Euclidean Space^[유클리드 공간] $\mathbb{R}^n$

- Open interval^[열린 구간] $(a, b) \subset \mathbb{R}$
- Open ball $B(x, r) = \{y \in \mathbb{R}^n : \|y - x\| < r\}$
- $\mathbb{R}^n$ 자체

### Discrete Topology^[이산 위상]

모든 부분집합이 open set (즉, $\tau = 2^X$)

### Indiscrete Topology^[비이산 위상]

$\emptyset$와 $X$만이 open set (즉, $\tau = \{\emptyset, X\}$)

---

# <span class="header-properties">Properties</span>

### Open Set과 Closed Set의 관계

$U \subseteq X$가 open $\Leftrightarrow$ $X \setminus U$가 closed^[닫힌 집합]

### Interior^[내부]

집합 $A \subseteq X$에 대해:
$$\text{int}(A) = \bigcup \{U : U \text{ is open and } U \subseteq A\}$$

$\text{int}(A)$는 $A$에 포함되는 가장 큰 open set이며, $A$의 **interior^[내부]**라 한다.

$A$가 open $\Leftrightarrow$ $A = \text{int}(A)$

### Neighborhood^[근방]

점 $x \in X$에 대해, 집합 $N \subseteq X$가 $x$의 **neighborhood^[근방]** $\Leftrightarrow$ $x \in U \subseteq N$인 open set $U$가 존재

---

# <span class="header-remark">Remark</span>

### 측도론^[Measure Theory]과의 관계

- Measure theory^[측도론]에서는 **measurable set^[가측 집합]**을 다룸
- Topology에서는 **open set^[열린 집합]**을 다룸
- [[Borel Sigma Algebra]]는 open set들로부터 생성되는 $\sigma$-algebra

### 해석학^[Analysis]에서의 중요성

Open set은 **continuity^[연속성]**, **convergence^[수렴]**, **differentiation^[미분]** 등 해석학의 핵심 개념을 정의하는 데 필수적이다.

함수 $f: X \to Y$가 continuous^[연속] $\Leftrightarrow$ 모든 open set $V \subseteq Y$에 대해 $f^{-1}(V)$가 open in $X$

