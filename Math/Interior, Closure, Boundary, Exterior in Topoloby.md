# <span class="header-prerequisite">Prerequisite</span>
- [[Topology]]
- [[Open Set]]

# <span class="header-reference">Reference</span>
- Munkres, Topology
- Rudin, Principles of Mathematical Analysis

---

# <span class="header-definition">Definition</span>

Topological space^[위상공간] $(X, \tau)$와 부분집합 $A \subseteq X$에 대해:

## Interior^[내부]

$A$의 **interior^[내부]** $\text{int}(A)$ (또는 $A^\circ$)는 $A$에 포함되는 모든 open set^[열린 집합]의 합집합:

$$\text{int}(A) = \bigcup \{U \in \tau : U \subseteq A\}$$

즉, $A$에 포함되는 **가장 큰 open set**

$\text{int}(A) = \{x \in A : \exists U \in \tau \text{ s.t. } x \in U \subseteq A\}$

## Closure^[폐포]

$A$의 **closure^[폐포]** $\overline{A}$ (또는 $\text{cl}(A)$)는 $A$를 포함하는 모든 closed set^[닫힌 집합]의 교집합:

$$\overline{A} = \bigcap \{F \subseteq X : F \text{ is closed and } A \subseteq F\}$$

즉, $A$를 포함하는 **가장 작은 closed set**

동등한 정의: $\overline{A} = \{x \in X : \forall U \in \tau, x \in U \Rightarrow U \cap A \neq \emptyset\}$

## Boundary^[경계]

$A$의 **boundary^[경계]** $\partial A$ (또는 $\text{bd}(A)$, $\text{Fr}(A)$)는:

$$\partial A = \overline{A} \setminus \text{int}(A)$$

또는 동등하게: $\partial A = \overline{A} \cap \overline{X \setminus A}$

## Exterior^[외부]

$A$의 **exterior^[외부]** $\text{ext}(A)$는:

$$\text{ext}(A) = \text{int}(X \setminus A)$$

즉, $A$의 complement^[여집합]의 interior

---

# <span class="header-properties">Properties</span>

### 기본 성질

**Interior:**
1. $\text{int}(A) \subseteq A$
2. $\text{int}(A)$는 open set
3. $A$가 open $\Leftrightarrow$ $A = \text{int}(A)$
4. $\text{int}(\text{int}(A)) = \text{int}(A)$ (idempotent^[멱등])
5. $\text{int}(\emptyset) = \emptyset$, $\text{int}(X) = X$

**Closure:**
1. $A \subseteq \overline{A}$
2. $\overline{A}$는 closed set
3. $A$가 closed $\Leftrightarrow$ $A = \overline{A}$
4. $\overline{\overline{A}} = \overline{A}$ (idempotent^[멱등])
5. $\overline{\emptyset} = \emptyset$, $\overline{X} = X$

**Boundary:**
1. $\partial A$는 closed set
2. $\partial A = \partial(X \setminus A)$
3. $A$가 open이면서 closed $\Leftrightarrow$ $\partial A = \emptyset$ (clopen^[열린닫힌])
4. $\partial(\partial A) \subseteq \partial A$

**Exterior:**
1. $\text{ext}(A)$는 open set
2. $\text{ext}(A) = \text{ext}(\overline{A})$
3. $\text{ext}(A) \cap A = \emptyset$

### 상호 관계

**공간의 분할:**
$$X = \text{int}(A) \cup \partial A \cup \text{ext}(A)$$
이들은 서로소(disjoint)

**Duality:**
- $\text{int}(X \setminus A) = X \setminus \overline{A}$
- $\overline{X \setminus A} = X \setminus \text{int}(A)$
- $\partial A = X \setminus (\text{int}(A) \cup \text{ext}(A))$

### 합집합과 교집합

**Interior:**
- $\text{int}(A \cap B) = \text{int}(A) \cap \text{int}(B)$
- $\text{int}(A) \cup \text{int}(B) \subseteq \text{int}(A \cup B)$ (등호 일반적으로 성립하지 않음)

**Closure:**
- $\overline{A \cup B} = \overline{A} \cup \overline{B}$
- $\overline{A \cap B} \subseteq \overline{A} \cap \overline{B}$ (등호 일반적으로 성립하지 않음)

### Limit Points^[극한점]

점 $x \in X$가 $A$의 **limit point^[극한점]** (또는 accumulation point^[축적점]) $\Leftrightarrow$ 모든 open set $U \ni x$에 대해 $(U \setminus \{x\}) \cap A \neq \emptyset$

$A' = \{x : x \text{ is a limit point of } A\}$로 표기하면:

$$\overline{A} = A \cup A'$$

---

# <span class="header-examples">Examples</span>

### Example 1: $\mathbb{R}$에서 반열린 구간

$A = [0, 1) \subseteq \mathbb{R}$ (standard topology):

- $\text{int}(A) = (0, 1)$
- $\overline{A} = [0, 1]$
- $\partial A = \{0, 1\}$
- $\text{ext}(A) = (-\infty, 0) \cup (1, \infty)$

### Example 2: $\mathbb{R}$에서 유리수

$A = \mathbb{Q} \subseteq \mathbb{R}$:

- $\text{int}(\mathbb{Q}) = \emptyset$ (유리수는 interior point를 갖지 않음)
- $\overline{\mathbb{Q}} = \mathbb{R}$ (유리수는 dense^[조밀])
- $\partial \mathbb{Q} = \mathbb{R}$
- $\text{ext}(\mathbb{Q}) = \emptyset$

### Example 3: $\mathbb{R}^2$에서 열린 원판

$A = \{(x, y) \in \mathbb{R}^2 : x^2 + y^2 < 1\}$:

- $\text{int}(A) = A$ (이미 open)
- $\overline{A} = \{(x, y) : x^2 + y^2 \leq 1\}$
- $\partial A = \{(x, y) : x^2 + y^2 = 1\}$ (단위원)
- $\text{ext}(A) = \{(x, y) : x^2 + y^2 > 1\}$

### Example 4: Discrete Topology^[이산 위상]

$(X, 2^X)$에서 공집합이 아닌 모든 부분집합 $A$:

- $\text{int}(A) = A$ (모든 집합이 open)
- $\overline{A} = A$ (모든 집합이 closed)
- $\partial A = \emptyset$
- $\text{ext}(A) = X \setminus A$

### Example 5: Indiscrete Topology^[비이산 위상]

$(X, \{\emptyset, X\})$에서 $\emptyset \neq A \neq X$:

- $\text{int}(A) = \emptyset$
- $\overline{A} = X$
- $\partial A = X$
- $\text{ext}(A) = \emptyset$

---

# <span class="header-theorem">Theorem</span>

### Kuratowski Closure Axioms^[쿠라토프스키 폐포 공리]

위상공간은 closure operator로 정의할 수도 있다. 함수 $\text{cl}: 2^X \to 2^X$가 다음을 만족하면:

1. $\text{cl}(\emptyset) = \emptyset$
2. $A \subseteq \text{cl}(A)$
3. $\text{cl}(\text{cl}(A)) = \text{cl}(A)$
4. $\text{cl}(A \cup B) = \text{cl}(A) \cup \text{cl}(B)$

이는 유일한 topology를 유도하며, 이 topology에서 $\overline{A} = \text{cl}(A)$

---

# <span class="header-remark">Remark</span>

### 직관적 이해

- **Interior**: $A$ 안에서 "확실히" 있는 점들 (boundary에서 멀리 떨어진 점들)
- **Closure**: $A$에 "가까운" 모든 점들 ($A$를 벗어날 수 없는 점들)
- **Boundary**: $A$의 안과 밖의 "경계선"에 있는 점들
- **Exterior**: $A$에서 "확실히" 떨어진 점들

### 응용

**해석학:**
- 연속함수의 정의
- 수열의 수렴
- Compact set 이론

**미분기하:**
- Manifold의 boundary
- Submanifold의 정의

**측도론:**
- Regular measure
- Borel set의 근사

### Dense Set^[조밀 집합]

$A$가 **dense^[조밀]** in $X$ $\Leftrightarrow$ $\overline{A} = X$

동등 조건:
- $\text{int}(X \setminus A) = \emptyset$
- 모든 nonempty open set $U$에 대해 $U \cap A \neq \emptyset$

예: $\mathbb{Q}$는 $\mathbb{R}$에서 dense, $\mathbb{R} \setminus \mathbb{Q}$도 dense

### Nowhere Dense^[처처 조밀하지 않음]

$A$가 **nowhere dense^[처처 조밀하지 않음]** $\Leftrightarrow$ $\text{int}(\overline{A}) = \emptyset$

즉, $A$의 closure가 interior point를 갖지 않음

예: $\mathbb{Z} \subseteq \mathbb{R}$, Cantor set

