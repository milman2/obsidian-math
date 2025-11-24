# <span class="header-prerequisite">Prerequisite</span>
- [[Open Set]]

# <span class="header-reference">Reference</span>
- Munkres, Topology
- Hatcher, Algebraic Topology

---

# <span class="header-definition">Definition</span>

**Topology^[위상]**은 집합 $X$와 그 부분집합들의 모임 $\tau \subseteq 2^X$로 이루어진 순서쌍 $(X, \tau)$로, 다음 세 가지 공리를 만족한다:

1. $\emptyset, X \in \tau$
2. $\{U_i\}_{i \in I} \subseteq \tau \Rightarrow \bigcup_{i \in I} U_i \in \tau$ (임의의 합집합)
3. $U_1, U_2, \ldots, U_n \in \tau \Rightarrow \bigcap_{i=1}^{n} U_i \in \tau$ (유한 교집합)

이때 $\tau$를 $X$ 위의 **topology^[위상]**이라 하고, $(X, \tau)$를 **topological space^[위상공간]**이라 한다.

$\tau$의 원소를 **open set^[열린 집합]**이라 한다.

---

# <span class="header-examples">Examples</span>

### Standard Topology on $\mathbb{R}$

$\tau = \{U \subseteq \mathbb{R} : \forall x \in U, \exists \epsilon > 0 \text{ s.t. } (x-\epsilon, x+\epsilon) \subseteq U\}$

이는 Euclidean metric^[유클리드 거리] $d(x, y) = |x - y|$로부터 유도된 topology

### Discrete Topology^[이산 위상]

$\tau = 2^X$ (모든 부분집합이 open)

가장 "섬세한" topology (finest topology^[가장 세밀한 위상])

### Indiscrete (Trivial) Topology^[비이산 위상]

$\tau = \{\emptyset, X\}$

가장 "거친" topology (coarsest topology^[가장 거친 위상])

### Cofinite Topology^[여유한 위상]

무한집합 $X$에서:
$$\tau = \{U \subseteq X : U = \emptyset \text{ or } X \setminus U \text{ is finite}\}$$

### Metric Topology^[거리 위상]

Metric space^[거리 공간] $(X, d)$에서 metric으로부터 유도되는 topology:
$$\tau = \{U \subseteq X : \forall x \in U, \exists \epsilon > 0 \text{ s.t. } B(x, \epsilon) \subseteq U\}$$

---

# <span class="header-properties">Properties</span>

### Basis^[기저]

집합족 $\mathcal{B} \subseteq 2^X$가 topology $\tau$의 **basis^[기저]** $\Leftrightarrow$ 모든 $U \in \tau$는 $\mathcal{B}$의 원소들의 합집합으로 표현 가능

**Basis의 조건:**
1. $\bigcup_{B \in \mathcal{B}} B = X$
2. $B_1, B_2 \in \mathcal{B}$이고 $x \in B_1 \cap B_2 \Rightarrow \exists B_3 \in \mathcal{B}$ s.t. $x \in B_3 \subseteq B_1 \cap B_2$

### Subbasis^[부분기저]

집합족 $\mathcal{S} \subseteq 2^X$가 **subbasis^[부분기저]** $\Leftrightarrow$ $\mathcal{S}$의 원소들의 유한 교집합들의 모임이 basis를 생성

### Continuity^[연속성]

함수 $f: (X, \tau_X) \to (Y, \tau_Y)$가 **continuous^[연속]** $\Leftrightarrow$ 모든 $V \in \tau_Y$에 대해 $f^{-1}(V) \in \tau_X$

### Homeomorphism^[위상동형사상]

전단사 함수 $f: X \to Y$가 **homeomorphism^[위상동형사상]** $\Leftrightarrow$ $f$와 $f^{-1}$ 모두 continuous

이때 $X$와 $Y$를 **homeomorphic^[위상동형]**이라 하고 $X \cong Y$로 표기

---

# <span class="header-theorem">Theorem</span>

### Comparison of Topologies^[위상의 비교]

$X$ 위의 두 topology $\tau_1, \tau_2$에 대해:

$\tau_1$이 $\tau_2$보다 **finer^[더 세밀하다]** (또는 $\tau_2$가 $\tau_1$보다 **coarser^[더 거칠다]**) $\Leftrightarrow$ $\tau_2 \subseteq \tau_1$

항등함수 $\text{id}: (X, \tau_1) \to (X, \tau_2)$가 continuous $\Leftrightarrow$ $\tau_1$이 $\tau_2$보다 finer

---

# <span class="header-remark">Remark</span>

### 위상공간론의 중요성

Topology는 현대 수학의 가장 기본적인 구조 중 하나로:
- **Analysis^[해석학]**: 함수의 연속성, 수렴 등을 다룸
- **Geometry^[기하학]**: 공간의 기하학적 성질을 연구
- **Algebra^[대수학]**: [[Algebraic Topology]]에서 대수적 구조와 연결

### 관련 분야

- [[Topology/Algebraic Topology]]: Topological space의 대수적 불변량 연구
- [[Topology/Differential Topology]]: 미분가능 구조를 가진 topology 연구
- [[Measure Space]]: Topology로부터 Borel $\sigma$-algebra 생성

### Separation Axioms^[분리 공리]

Topology의 "좋은" 성질을 나타내는 공리들:
- **$T_0$** (Kolmogorov): 서로 다른 점들을 구별 가능
- **$T_1$**: 점들이 닫힌 집합
- **$T_2$** (Hausdorff^[하우스도르프]): 서로 다른 점들을 분리하는 열린 집합 존재
- **$T_3$** (Regular^[정칙]): $T_0$ + closed set과 그 외부의 점 분리 가능
- **$T_4$** (Normal^[정규]): $T_1$ + disjoint closed sets 분리 가능

Metric space는 항상 Hausdorff이며 Normal이다.

