# <span class="header-prerequisite">Prerequisite</span>
- Set theory (집합론 기초)
- [[Function]]

# <span class="header-reference">Reference</span>
- Halmos, Naive Set Theory
- Enderton, Elements of Set Theory

---

# <span class="header-definition">Definition</span>

## Relation^[관계]

집합 $A$, $B$에 대해, **relation^[관계]** $R$은 $A \times B$의 부분집합:

$$R \subseteq A \times B$$

$(a, b) \in R$일 때 "$a$는 $b$와 관계가 있다"고 하며, 다음과 같이 표기:

$$aRb \quad \text{or} \quad a \sim b \quad \text{or} \quad a \mathrel{R} b$$

### Domain and Range

**Domain^[정의역]**:
$$\text{dom}(R) = \{a \in A : \exists b \in B, (a,b) \in R\}$$

**Range^[치역]** (또는 Image^[상]):
$$\text{ran}(R) = \text{im}(R) = \{b \in B : \exists a \in A, (a,b) \in R\}$$

## Binary Relation^[이항 관계]

가장 흔한 경우: **binary relation^[이항 관계]** on $A$

$$R \subseteq A \times A$$

집합 $A$의 원소들 사이의 관계

## $n$-ary Relation

일반화: **$n$-ary relation^[$n$항 관계]**

$$R \subseteq A_1 \times A_2 \times \cdots \times A_n$$

예: Database의 relation (table)

---

# <span class="header-definition">Properties of Relations</span>

집합 $A$ 위의 binary relation $R$에 대해:

## Reflexivity^[반사성]

$R$이 **reflexive^[반사]**이다 $\Leftrightarrow$

$$\forall a \in A, \; aRa$$

모든 원소가 자기 자신과 관계됨

**예**: 
- $\leq$ on $\mathbb{R}$: reflexive ✓ ($x \leq x$)
- $<$ on $\mathbb{R}$: not reflexive ✗ ($x \not< x$)

## Irreflexivity^[비반사성]

$R$이 **irreflexive^[비반사]**이다 $\Leftrightarrow$

$$\forall a \in A, \; \neg(aRa)$$

어떤 원소도 자기 자신과 관계되지 않음

**예**: $<$ on $\mathbb{R}$

## Symmetry^[대칭성]

$R$이 **symmetric^[대칭]**이다 $\Leftrightarrow$

$$\forall a, b \in A, \; aRb \Rightarrow bRa$$

관계의 방향을 바꿀 수 있음

**예**:
- $=$ on $\mathbb{R}$: symmetric ✓
- $\leq$ on $\mathbb{R}$: not symmetric ✗

## Antisymmetry^[반대칭성]

$R$이 **antisymmetric^[반대칭]**이다 $\Leftrightarrow$

$$\forall a, b \in A, \; aRb \land bRa \Rightarrow a = b$$

양방향 관계는 같은 원소만 가능

**예**: $\leq$ on $\mathbb{R}$ (antisymmetric ✓)

**주의**: Antisymmetric $\neq$ Not symmetric!

## Asymmetry^[비대칭성]

$R$이 **asymmetric^[비대칭]**이다 $\Leftrightarrow$

$$\forall a, b \in A, \; aRb \Rightarrow \neg(bRa)$$

한 방향만 가능

**예**: $<$ on $\mathbb{R}$

**관계**: Asymmetric $\Rightarrow$ Antisymmetric + Irreflexive

## Transitivity^[추이성]

$R$이 **transitive^[추이]**이다 $\Leftrightarrow$

$$\forall a, b, c \in A, \; aRb \land bRc \Rightarrow aRc$$

관계가 "전달"됨

**예**:
- $\leq$ on $\mathbb{R}$: transitive ✓
- "부모-자식" relation: not transitive ✗

## Totality^[전체성]

$R$이 **total^[전체]** (또는 **complete^[완전]**)이다 $\Leftrightarrow$

$$\forall a, b \in A, \; aRb \lor bRa$$

모든 원소 쌍이 비교 가능

**예**:
- $\leq$ on $\mathbb{R}$: total ✓
- $\subseteq$ on $2^X$: not total ✗ (incomparable sets exist)

---

# <span class="header-definition">Special Types of Relations</span>

## Equivalence Relation^[동치 관계]

$R$이 **equivalence relation^[동치 관계]** $\Leftrightarrow$ Reflexive + Symmetric + Transitive

**예**: 
- Equality $=$
- Congruence modulo $n$: $a \equiv b \pmod{n}$
- "Same birthday"

자세한 내용은 [[Equivalence Relation and Partitions]] 참조

## Partial Order^[부분 순서]

$R$이 **partial order^[부분 순서]** $\Leftrightarrow$ Reflexive + Antisymmetric + Transitive

**표기**: 주로 $\leq$ 또는 $\preceq$

**예**:
- $\leq$ on $\mathbb{R}$
- $\subseteq$ on $2^X$ (집합의 포함)
- Divisibility $\mid$ on $\mathbb{N}$

**(Partially) Ordered Set (Poset)^[부분 순서 집합]**: $(A, \leq)$

## Total Order^[전순서]

$R$이 **total order^[전순서]** (또는 **linear order^[선형 순서]**)
$\Leftrightarrow$ Partial order + Total

즉: Reflexive + Antisymmetric + Transitive + Total

**예**:
- $\leq$ on $\mathbb{R}$ ✓
- $\subseteq$ on $2^X$ ✗ (partial but not total)

## Strict Order^[엄격 순서]

### Strict Partial Order

**Strict partial order^[엄격 부분 순서]** $\Leftrightarrow$ Irreflexive + Transitive

**표기**: 주로 $<$ 또는 $\prec$

**예**: $<$ on $\mathbb{R}$

### Strict Total Order

**Strict total order^[엄격 전순서]** $\Leftrightarrow$ Strict partial order + Trichotomy

**Trichotomy^[삼분법]**: $\forall a, b$, exactly one of $a < b$, $a = b$, $b < a$

## Preorder^[전순서]

$R$이 **preorder^[전순서]** (또는 **quasi-order^[준순서]**)
$\Leftrightarrow$ Reflexive + Transitive

Partial order에서 antisymmetry 제거

**예**: 
- "선호도": $a \preceq b$ = "$a$를 $b$만큼 선호" (같은 선호도 가능)
- Specialization order in topology

---

# <span class="header-definition">Operations on Relations</span>

## Inverse Relation^[역관계]

Relation $R \subseteq A \times B$의 **inverse^[역관계]** $R^{-1} \subseteq B \times A$:

$$R^{-1} = \{(b, a) : (a, b) \in R\}$$

**성질**:
- $(R^{-1})^{-1} = R$
- $R$ symmetric $\Leftrightarrow$ $R = R^{-1}$

## Composition^[합성]

Relations $R \subseteq A \times B$, $S \subseteq B \times C$의 **composition^[합성]** $S \circ R \subseteq A \times C$:

$$(S \circ R) = \{(a, c) : \exists b \in B, (a,b) \in R \land (b,c) \in S\}$$

**순서 주의**: $S \circ R$ = "$R$ 먼저, 그 다음 $S$"

**성질**:
1. **Associativity^[결합법칙]**: $(T \circ S) \circ R = T \circ (S \circ R)$
2. **Identity**: $I_A \circ R = R = R \circ I_B$ (where $I_A = \{(a,a) : a \in A\}$)

## Reflexive/Symmetric/Transitive Closure

### Reflexive Closure^[반사 폐포]

$R$을 포함하는 가장 작은 reflexive relation:

$$R^= = R \cup \{(a, a) : a \in A\}$$

### Symmetric Closure^[대칭 폐포]

$R$을 포함하는 가장 작은 symmetric relation:

$$R^s = R \cup R^{-1}$$

### Transitive Closure^[추이 폐포]

$R$을 포함하는 가장 작은 transitive relation:

$$R^+ = \bigcup_{n=1}^{\infty} R^n$$

여기서 $R^n = \underbrace{R \circ R \circ \cdots \circ R}_{n \text{ times}}$

**Reflexive-transitive closure**: $R^* = R^+ \cup I_A$

---

# <span class="header-examples">Examples</span>

## Example 1: Arithmetic Relations

**$\mathbb{R}$ 위에서**:

| Relation | Reflexive | Symmetric | Transitive | Type |
|----------|-----------|-----------|------------|------|
| $=$ | ✓ | ✓ | ✓ | Equivalence |
| $\leq$ | ✓ | ✗ | ✓ | Total order |
| $<$ | ✗ | ✗ | ✓ | Strict total order |
| $\neq$ | ✗ | ✓ | ✗ | Symmetric only |

## Example 2: Divisibility

$\mathbb{N}$ 위에서 $a \mid b$ (divides):

- Reflexive: ✓ ($a \mid a$)
- Antisymmetric: ✓ ($a \mid b \land b \mid a \Rightarrow a = b$ for $\mathbb{N}$)
- Transitive: ✓ ($a \mid b \land b \mid c \Rightarrow a \mid c$)
- Total: ✗ (예: $2 \nmid 3$, $3 \nmid 2$)

**Type**: Partial order

## Example 3: Subset Relation

$2^X$ (power set) 위에서 $\subseteq$:

- Reflexive: ✓
- Antisymmetric: ✓
- Transitive: ✓
- Total: ✗ (incomparable sets)

**Type**: Partial order (not total)

**Hasse diagram^[하세 도표]**로 시각화 가능

## Example 4: Family Relations

"Parent-child" relation:

- Reflexive: ✗ (자기 자신의 부모 아님)
- Symmetric: ✗ (부모 $\not\Rightarrow$ 자식)
- Transitive: ✗ (부모의 부모 $\neq$ 부모)

"Ancestor-descendant" relation = transitive closure of parent-child

## Example 5: Graph Theory

Directed graph $G = (V, E)$: $E \subseteq V \times V$ (relation!)

- **Path**: Transitive closure of $E$
- **Strong connectivity**: $E^+ \cup (E^+)^{-1}$ is total

## Example 6: Congruence Modulo $n$

$\mathbb{Z}$ 위에서 $a \equiv b \pmod{n}$:

- Reflexive: ✓
- Symmetric: ✓
- Transitive: ✓

**Type**: Equivalence relation

자세한 내용은 [[Equivalence Relation and Partitions]] 참조

---

# <span class="header-properties">Properties</span>

## Relation vs Function

**Function^[함수]** = special relation with additional property:

$$\forall a \in A, \exists! b \in B : (a, b) \in R$$

즉, function은 "single-valued" relation

**일반 relation**: 하나의 $a$가 여러 $b$와 관계될 수 있음

자세한 내용은 [[Function]] 참조

## Representation of Relations

### 1. Set of Ordered Pairs

$$R = \{(1, 2), (2, 3), (1, 3)\}$$

### 2. Matrix (유한 집합)

$A = \{a_1, \ldots, a_n\}$에 대해 $n \times n$ matrix $M$:

$$M_{ij} = \begin{cases} 1 & (a_i, a_j) \in R \\ 0 & \text{otherwise} \end{cases}$$

**Composition**: $M_{S \circ R} = M_S \cdot M_R$ (Boolean matrix multiplication)

### 3. Directed Graph (Digraph)

- Vertices = elements of $A$
- Edges = pairs in $R$

**Properties와 graph**:
- Reflexive: Self-loops at all vertices
- Symmetric: Bidirectional edges
- Transitive: Triangle closure

## Properties of Property Combinations

| Reflexive | Symmetric | Transitive | Type |
|-----------|-----------|------------|------|
| ✓ | ✓ | ✓ | Equivalence relation |
| ✓ | ✗ (antisym) | ✓ | Partial order |
| ✗ | ✗ | ✓ | Strict partial order |
| ✓ | ✗ | ✓ | Preorder |

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Relation = "연결"의 일반화**

- **Equivalence relation**: "같음"의 일반화
- **Order relation**: "크기 비교"의 일반화
- **Function**: "유일한 출력"을 가진 특수 relation

## Relations in Different Fields

### Set Theory^[집합론]

**기본 개념**: Relation은 집합론의 fundamental building block

**Axiom of Extensionality**: Sets defined by relations

### Databases^[데이터베이스]

**Relational model**:
- Table = $n$-ary relation
- Query = relation operation (join, union, etc.)

### Graph Theory^[그래프 이론]

**Graph = Relation**:
- Adjacency = binary relation
- Path = transitive closure

### Logic^[논리학]

**Predicate logic**: Binary predicate = relation

$$P(x, y) \Leftrightarrow (x, y) \in R$$

### Computer Science^[컴퓨터 과학]

**State transitions**: $(s, s') \in R$ = "state $s$ transitions to $s'$"

**Reachability**: Transitive closure

## Cardinality of Relations

유한 집합 $|A| = n$, $|B| = m$:

**가능한 relations**: $2^{nm}$ (모든 부분집합)

**Binary relations on $A$**: $2^{n^2}$

**Equivalence relations**: Bell number $B_n$

**Partial orders**: Hard to count (complex combinatorics)

## Historical Note

**René Descartes** (1596-1650): Cartesian product의 기초

**Gottfried Leibniz** (1646-1716): Relations in logic

**Ernst Schröder** (1841-1902): Algebra of relations

**Alfred North Whitehead & Bertrand Russell** (1910-1913): 
*Principia Mathematica* - Relations in formal logic

## Practical Applications

**Recommendation systems**: "User likes item" relation

**Social networks**: "Friendship" (symmetric), "Following" (asymmetric)

**Scheduling**: "Task $A$ must precede task $B$" (partial order)

**Type systems**: Subtype relation (preorder or partial order)

## Common Mistakes^[흔한 실수]

### 1. Symmetric vs Antisymmetric

**Not opposites!**
- $=$ is both symmetric AND antisymmetric
- "Not symmetric" $\neq$ Antisymmetric

### 2. Reflexive vs Irreflexive

**Not opposites!**
- Relation can be neither (예: $(a, b)$ where $a \neq b$)

### 3. Composition order

$S \circ R$ means "$R$ first, then $S$"

(Opposite to function composition in some notations!)

## Related Concepts

- [[Function]]: Special type of relation
- [[Equivalence Relation and Partitions]]: Reflexive + Symmetric + Transitive
- [[One-to-On, Onto]]: Properties of functions (special relations)
- [[Conjugate]]: Conjugacy as equivalence relation

## Further Topics

**Advanced**:
- Well-founded relations
- Noetherian relations
- Dependency relations
- Rewriting systems

**Category Theory**:
- Relations as morphisms in $\mathbf{Rel}$
- Allegories

