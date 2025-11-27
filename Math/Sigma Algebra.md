# <span class="header-prerequisite">Prerequisite</span>
- [[Set Theory]]
- [[Function]]
- [[Equivalence Relation and Partitions]]

# <span class="header-reference">Reference</span>
- Folland, Real Analysis
- Royden & Fitzpatrick, Real Analysis
- Rudin, Real and Complex Analysis
- Billingsley, Probability and Measure

---

# <span class="header-definition">Definition</span>

## Sigma Algebra

$X$를 nonempty set이라고 하자.

**Sigma algebra**^[시그마 대수] (또는 **sigma field**^[시그마 체]):

$X$의 부분집합들의 모임 $\mathcal{F} \subseteq \mathcal{P}(X)$가 다음 세 조건을 만족하면 **sigma algebra**라고 함:

**(1) $X \in \mathcal{F}$** (전체 집합 포함)

**(2)** $A \in \mathcal{F} \Rightarrow A^c \in \mathcal{F}$ (여집합에 닫혀있음^[closed under complement])

**(3)** $A_1, A_2, A_3, \ldots \in \mathcal{F} \Rightarrow \displaystyle\bigcup_{i=1}^{\infty} A_i \in \mathcal{F}$ (가산 합집합에 닫혀있음^[closed under countable union])

**표기**:
- $\mathcal{F}$, $\mathcal{A}$, $\Sigma$ 등으로 표기
- $(X, \mathcal{F})$: **measurable space**^[가측 공간]

**핵심**:
- "측정 가능한" 집합들의 모임
- 가산^[countable] 연산에 닫혀있음
- 측도론의 기초

## Alternative Definition

위 정의는 다음과 동치:

**(1')** $\emptyset \in \mathcal{F}$ (공집합 포함)

**(2')** $A \in \mathcal{F} \Rightarrow A^c \in \mathcal{F}$ (여집합)

**(3')** $A_1, A_2, A_3, \ldots \in \mathcal{F} \Rightarrow \displaystyle\bigcup_{i=1}^{\infty} A_i \in \mathcal{F}$ (가산 합집합)

**증명**:
- $(1) \Rightarrow (1')$: $\emptyset = X^c \in \mathcal{F}$ (by (2))
- $(1') \Rightarrow (1)$: $X = \emptyset^c \in \mathcal{F}$ (by (2))

## Algebra of Sets

**정의**: **Algebra of sets**^[집합 대수] (또는 **field of sets**^[집합 체]):

$\mathcal{A} \subseteq \mathcal{P}(X)$가 다음을 만족:

**(1)** $X \in \mathcal{A}$

**(2)** $A \in \mathcal{A} \Rightarrow A^c \in \mathcal{A}$

**(3)** $A, B \in \mathcal{A} \Rightarrow A \cup B \in \mathcal{A}$ (**finite** union)

**차이점**:
- **Algebra**: **유한^[finite]** 합집합에 닫혀있음
- **Sigma algebra**: **가산^[countable]** 합집합에 닫혀있음

**관계**: 

$$\text{Sigma algebra} \subseteq \text{Algebra}$$

모든 sigma algebra는 algebra이지만, 역은 성립하지 않음

## Measurable Space

**정의**: Pair $(X, \mathcal{F})$를 **measurable space**^[가측 공간]이라고 함

where:
- $X$: nonempty set
- $\mathcal{F}$: sigma algebra on $X$

**의미**:
- $X$: "전체 공간"
- $\mathcal{F}$: "측정 가능한 집합들"

**Example**:
- $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$: Real line with Borel sigma algebra
- $(\Omega, \mathcal{F})$: Probability space (before adding measure)

## Measurable Set

**정의**: $(X, \mathcal{F})$가 measurable space일 때

$$A \in \mathcal{F} \quad \Leftrightarrow \quad A \text{ is } \mathcal{F}\text{-measurable}$$

$A$를 **measurable set**^[가측 집합]이라고 함

**의미**:
- $A \in \mathcal{F}$: "측정할 수 있는" 집합
- $A \notin \mathcal{F}$: "측정할 수 없는" 집합 (pathological)

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Empty Set

**정리**: $\emptyset \in \mathcal{F}$

**증명**:
- $X \in \mathcal{F}$ (by axiom 1)
- $\emptyset = X^c \in \mathcal{F}$ (by axiom 2) ✓

### 2. Finite Union

**정리**: $A_1, \ldots, A_n \in \mathcal{F} \Rightarrow \displaystyle\bigcup_{i=1}^{n} A_i \in \mathcal{F}$

**증명**:

Define $A_{n+1} = A_{n+2} = \cdots = \emptyset$

$$\bigcup_{i=1}^{n} A_i = \bigcup_{i=1}^{\infty} A_i \in \mathcal{F}$$ 

(by axiom 3) ✓

### 3. Countable Intersection

**정리**: $A_1, A_2, A_3, \ldots \in \mathcal{F} \Rightarrow \displaystyle\bigcap_{i=1}^{\infty} A_i \in \mathcal{F}$

**증명** (De Morgan's Law):

$$\bigcap_{i=1}^{\infty} A_i = \left( \bigcup_{i=1}^{\infty} A_i^c \right)^c$$

- $A_i \in \mathcal{F} \Rightarrow A_i^c \in \mathcal{F}$ (axiom 2)
- $\bigcup_{i=1}^{\infty} A_i^c \in \mathcal{F}$ (axiom 3)
- $\left( \bigcup_{i=1}^{\infty} A_i^c \right)^c \in \mathcal{F}$ (axiom 2) ✓

### 4. Finite Intersection

**정리**: $A_1, \ldots, A_n \in \mathcal{F} \Rightarrow \displaystyle\bigcap_{i=1}^{n} A_i \in \mathcal{F}$

**증명**: Property 3과 동일한 방법 ✓

### 5. Set Difference

**정리**: $A, B \in \mathcal{F} \Rightarrow A \setminus B \in \mathcal{F}$

**증명**:

$$A \setminus B = A \cap B^c$$

- $B^c \in \mathcal{F}$ (axiom 2)
- $A \cap B^c \in \mathcal{F}$ (property 4) ✓

### 6. Symmetric Difference

**정리**: $A, B \in \mathcal{F} \Rightarrow A \triangle B \in \mathcal{F}$

**증명**:

$$A \triangle B = (A \setminus B) \cup (B \setminus A)$$

- $A \setminus B, B \setminus A \in \mathcal{F}$ (property 5)
- $(A \setminus B) \cup (B \setminus A) \in \mathcal{F}$ (property 2) ✓

## Closure Properties

**정리**: Sigma algebra $\mathcal{F}$는 다음 연산에 닫혀있음:

**(a)** Complement: $A \in \mathcal{F} \Rightarrow A^c \in \mathcal{F}$

**(b)** Countable union: $\{A_i\}_{i=1}^{\infty} \subseteq \mathcal{F} \Rightarrow \bigcup_{i=1}^{\infty} A_i \in \mathcal{F}$

**(c)** Countable intersection: $\{A_i\}_{i=1}^{\infty} \subseteq \mathcal{F} \Rightarrow \bigcap_{i=1}^{\infty} A_i \in \mathcal{F}$

**(d)** Set difference: $A, B \in \mathcal{F} \Rightarrow A \setminus B \in \mathcal{F}$

**(e)** Symmetric difference: $A, B \in \mathcal{F} \Rightarrow A \triangle B \in \mathcal{F}$

**의미**: Sigma algebra는 "rich structure" (많은 연산에 안정적)

## Limit Sets

### Limit Superior

**정의**: $\{A_n\}_{n=1}^{\infty} \subseteq \mathcal{F}$일 때

$$\limsup_{n \to \infty} A_n = \bigcap_{n=1}^{\infty} \bigcup_{k=n}^{\infty} A_k$$

**의미**: "무한히 많은 $A_n$에 속하는" 원소들

**표기**: $A_n$ **i.o.**^[infinitely often]

**정리**: $\limsup_{n \to \infty} A_n \in \mathcal{F}$

### Limit Inferior

**정의**: 

$$\liminf_{n \to \infty} A_n = \bigcup_{n=1}^{\infty} \bigcap_{k=n}^{\infty} A_k$$

**의미**: "충분히 큰 모든 $n$에 대해 $A_n$에 속하는" 원소들

**표기**: $A_n$ **eventually**^[궁극적으로]

**정리**: $\liminf_{n \to \infty} A_n \in \mathcal{F}$

### Relationship

**정리**:

$$\liminf_{n \to \infty} A_n \subseteq \limsup_{n \to \infty} A_n$$

**Limit exists**:

$$\lim_{n \to \infty} A_n = A \quad \Leftrightarrow \quad \liminf_{n \to \infty} A_n = \limsup_{n \to \infty} A_n = A$$

자세한 내용은 [[Limit of Sets]] 참조

## Minimal Property

**정리**: Sigma algebras의 교집합은 sigma algebra

**증명**: $\{\mathcal{F}_\alpha\}_{\alpha \in I}$를 sigma algebras라고 하자

Let $\mathcal{F} = \bigcap_{\alpha \in I} \mathcal{F}_\alpha$

**(1)** $X \in \mathcal{F}_\alpha$ for all $\alpha$ $\Rightarrow$ $X \in \mathcal{F}$ ✓

**(2)** $A \in \mathcal{F}$ $\Rightarrow$ $A \in \mathcal{F}_\alpha$ for all $\alpha$ $\Rightarrow$ $A^c \in \mathcal{F}_\alpha$ for all $\alpha$ $\Rightarrow$ $A^c \in \mathcal{F}$ ✓

**(3)** Similarly for countable unions ✓

**중요성**: Generated sigma algebra의 existence 보장

---

# <span class="header-examples">Examples</span>

## Example 1: Power Set

$$\mathcal{F} = \mathcal{P}(X) = \{A : A \subseteq X\}$$

**모든** 부분집합의 모임

**확인**:
- $X \in \mathcal{P}(X)$ ✓
- $A \subseteq X \Rightarrow A^c \subseteq X$ ✓
- $A_i \subseteq X \Rightarrow \bigcup A_i \subseteq X$ ✓

**특징**: 가장 큰^[largest] sigma algebra

**사용**: 이산^[discrete] 측도론, 유한 집합

## Example 2: Trivial Sigma Algebra

$$\mathcal{F} = \{\emptyset, X\}$$

**확인**:
- $X \in \mathcal{F}$ ✓
- $X^c = \emptyset \in \mathcal{F}$, $\emptyset^c = X \in \mathcal{F}$ ✓
- $X \cup X = X$, $X \cup \emptyset = X$, $\emptyset \cup \emptyset = \emptyset$ ✓

**특징**: 가장 작은^[smallest] sigma algebra

**의미**: "아무것도 측정 못함" (trivial information)

## Example 3: Singleton Extension

$x \in X$에 대해

$$\mathcal{F} = \{\emptyset, \{x\}, \{x\}^c, X\}$$

**확인**: Closure properties 확인 가능 ✓

**특징**: $\{x\}$를 "구별"하는 가장 작은 sigma algebra

## Example 4: Borel Sigma Algebra

**정의**: $\mathbb{R}$의 **Borel sigma algebra**^[보렐 시그마 대수]:

$$\mathcal{B}(\mathbb{R}) = \sigma(\{\text{open sets}\})$$

모든 open sets를 포함하는 가장 작은 sigma algebra

**원소**:
- All open sets
- All closed sets
- All intervals: $(a, b)$, $[a, b]$, $(a, b]$, $[a, \infty)$, etc.
- Countable unions/intersections of above
- More...

**크기**: $|\mathcal{B}(\mathbb{R})| = 2^{\aleph_0}$ (continuum)

**주의**: $\mathcal{B}(\mathbb{R}) \subsetneq \mathcal{P}(\mathbb{R})$ (strict!)

Non-Borel sets 존재 (하지만 constructing이 어려움)

자세한 내용은 [[Borel Sigma Algebra]] 참조

## Example 5: Generated by Intervals

$$\mathcal{F} = \sigma(\{(a, b) : a < b\})$$

모든 open intervals로부터 생성된 sigma algebra

**정리**: $\mathcal{F} = \mathcal{B}(\mathbb{R})$

**증명**:
- $(\subseteq)$: Every open interval is open set $\Rightarrow$ $\mathcal{F} \subseteq \mathcal{B}(\mathbb{R})$
- $(\supseteq)$: Every open set is countable union of open intervals $\Rightarrow$ $\mathcal{B}(\mathbb{R}) \subseteq \mathcal{F}$ ✓

## Example 6: Finite Set

$X = \{a, b, c\}$

**Some sigma algebras on $X$**:

**(a)** $\{\emptyset, X\}$ (trivial)

**(b)** $\{\emptyset, \{a\}, \{b, c\}, X\}$

**(c)** $\{\emptyset, \{a\}, \{b\}, \{c\}, \{a, b\}, \{a, c\}, \{b, c\}, X\}$ (power set)

**개수**: Not every subset family is sigma algebra!

For $|X| = n$: number of sigma algebras는 복잡한 공식

## Example 7: Cofinite Sigma Algebra (NOT!)

**시도**: $\mathcal{F} = \{A : A \text{ finite or } A^c \text{ finite}\}$

**확인**:
- $X \in \mathcal{F}$ (if $X$ finite) or $X^c = \emptyset$ finite ✓
- $A \in \mathcal{F} \Rightarrow A^c \in \mathcal{F}$ ✓
- Countable union? ✗

**반례** ($X = \mathbb{N}$):

$$A_n = \{n\} \in \mathcal{F}$$ (each finite)

But:

$$\bigcup_{n=1}^{\infty} \{n\} = \mathbb{N}$$

$\mathbb{N}$도 $\mathbb{N}^c = \emptyset$도... 실제로 $\mathbb{N}^c = \emptyset$는 finite! ✓

다시 생각... 이 경우는 OK!

**실제 반례** ($X = \mathbb{R}$):

Even integers: $2\mathbb{Z} = \bigcup_{n \in \mathbb{Z}} \{2n\}$

Countable union of finite sets, but neither $2\mathbb{Z}$ nor $(2\mathbb{Z})^c$ is finite ✗

**결론**: NOT always sigma algebra (depends on $X$)

## Example 8: Countable-Cocountable

$X$ uncountable이면

$$\mathcal{F} = \{A : A \text{ countable or } A^c \text{ countable}\}$$

**확인**:
- $X$ uncountable $\Rightarrow$ $X^c = \emptyset$ countable $\Rightarrow$ $X \in \mathcal{F}$ ✓
- $A$ countable $\Rightarrow$ $A^c$ cocountable ✓, vice versa ✓
- $A_i$ countable $\Rightarrow$ $\bigcup A_i$ countable ✓
- $A_i$ cocountable (at least one) $\Rightarrow$ $\bigcup A_i$ cocountable ✓

**결론**: Sigma algebra! ✓

## Example 9: From Partition

$\{B_1, B_2, \ldots, B_n\}$이 $X$의 partition이면

$$\mathcal{F} = \left\{ \bigcup_{i \in I} B_i : I \subseteq \{1, 2, \ldots, n\} \right\}$$

**확인**: Sigma algebra ✓

**크기**: $|\mathcal{F}| = 2^n$

**의미**: Partition에 의해 정의된 "가장 fine한" information

자세한 내용은 [[Equivalence Relation and Partitions]] 참조

## Example 10: Lebesgue Measurable Sets

$$\mathcal{L} = \{A \subseteq \mathbb{R} : A \text{ is Lebesgue measurable}\}$$

**정의**: $A$가 Lebesgue measurable $\Leftrightarrow$

$$\lambda^*(E) = \lambda^*(E \cap A) + \lambda^*(E \cap A^c)$$

for all $E \subseteq \mathbb{R}$ (Carathéodory condition)

**관계**:

$$\mathcal{B}(\mathbb{R}) \subsetneq \mathcal{L} \subsetneq \mathcal{P}(\mathbb{R})$$

**크기**: $|\mathcal{L}| = 2^{2^{\aleph_0}}$ (larger than continuum!)

자세한 내용은 [[Lebesgue Measure]] 참조

---

# <span class="header-definition">Definition (Continued)</span>

## Generated Sigma Algebra

**정의**: $\mathcal{E} \subseteq \mathcal{P}(X)$에 대해

$$\sigma(\mathcal{E}) = \bigcap \{\mathcal{F} : \mathcal{F} \text{ is sigma algebra}, \mathcal{E} \subseteq \mathcal{F}\}$$

$\mathcal{E}$를 포함하는 **가장 작은^[smallest]** sigma algebra

**표기**: 
- $\sigma(\mathcal{E})$: sigma algebra generated by $\mathcal{E}$
- $\mathcal{E}$: **generating set**^[생성 집합]

**존재성**: 
- $\mathcal{P}(X)$는 sigma algebra이고 $\mathcal{E} \subseteq \mathcal{P}(X)$
- Sigma algebras의 교집합은 sigma algebra (Property 참조)
- Therefore $\sigma(\mathcal{E})$ 존재 ✓

**유일성**: Definition에 의해 유일 ✓

## Properties of Generated Sigma Algebra

### 1. Minimality

$$\mathcal{E} \subseteq \sigma(\mathcal{E})$$

**의미**: $\mathcal{E}$의 모든 원소를 포함

### 2. Universal Property

$$\mathcal{E} \subseteq \mathcal{F} \text{ (sigma algebra)} \quad \Rightarrow \quad \sigma(\mathcal{E}) \subseteq \mathcal{F}$$

**의미**: $\mathcal{E}$를 포함하는 모든 sigma algebra는 $\sigma(\mathcal{E})$를 포함

### 3. Monotonicity

$$\mathcal{E}_1 \subseteq \mathcal{E}_2 \quad \Rightarrow \quad \sigma(\mathcal{E}_1) \subseteq \sigma(\mathcal{E}_2)$$

### 4. Idempotence

$$\sigma(\sigma(\mathcal{E})) = \sigma(\mathcal{E})$$

**증명**: $\sigma(\mathcal{E})$는 이미 sigma algebra ✓

### 5. Extension

$\mathcal{E}$가 algebra이면 $\sigma(\mathcal{E})$는 가장 작은 sigma algebra extending $\mathcal{E}$

## Product Sigma Algebra

**정의**: $(X_1, \mathcal{F}_1)$, $(X_2, \mathcal{F}_2)$가 measurable spaces이면

$$\mathcal{F}_1 \otimes \mathcal{F}_2 = \sigma(\{A_1 \times A_2 : A_1 \in \mathcal{F}_1, A_2 \in \mathcal{F}_2\})$$

**Product sigma algebra**^[곱 시그마 대수] on $X_1 \times X_2$

**원소**:
- Measurable rectangles $A_1 \times A_2$
- Countable unions/intersections of above
- More...

**Example**:

$$\mathcal{B}(\mathbb{R}) \otimes \mathcal{B}(\mathbb{R}) = \mathcal{B}(\mathbb{R}^2)$$

(for Euclidean space)

자세한 내용은 [[Product Sigma Algebra]] 참조

## Sub-sigma Algebra

**정의**: $(X, \mathcal{F})$가 measurable space이고 $\mathcal{G} \subseteq \mathcal{F}$가 sigma algebra이면

$\mathcal{G}$를 **sub-sigma algebra**^[부분 시그마 대수]라고 함

**의미**: "Coarser information" (less refined)

**Example** (Filtration):

$$\mathcal{F}_1 \subseteq \mathcal{F}_2 \subseteq \cdots \subseteq \mathcal{F}$$

**응용**: Stochastic processes, conditional expectation

자세한 내용은 [[Filtration]] 참조

---

# <span class="header-theorem">Theorem</span>

## Dynkin's π-λ Theorem

**정의**: 
- **π-system**^[파이 시스템]: $\mathcal{P} \subseteq \mathcal{P}(X)$가 finite intersections에 닫혀있음
- **λ-system**^[람다 시스템] (Dynkin system): $\mathcal{D} \subseteq \mathcal{P}(X)$가:
  - $X \in \mathcal{D}$
  - $A \in \mathcal{D} \Rightarrow A^c \in \mathcal{D}$
  - $A_i \in \mathcal{D}$ (disjoint) $\Rightarrow \bigcup A_i \in \mathcal{D}$

**정리**: $\mathcal{P}$가 π-system이고 $\mathcal{D}$가 λ-system with $\mathcal{P} \subseteq \mathcal{D}$이면

$$\sigma(\mathcal{P}) \subseteq \mathcal{D}$$

**의미**: Sigma algebra equality를 보이는 강력한 도구!

**응용**: Uniqueness of measures

자세한 내용은 [[Dynkin System]] 참조

## Monotone Class Theorem

**정의**: **Monotone class**^[단조 클래스] $\mathcal{M}$:
- $A_n \uparrow A$ (increasing) $\Rightarrow$ $A \in \mathcal{M}$
- $A_n \downarrow A$ (decreasing) $\Rightarrow$ $A \in \mathcal{M}$

**정리**: $\mathcal{A}$가 algebra이면

$$\sigma(\mathcal{A}) = m(\mathcal{A})$$

where $m(\mathcal{A})$ is the smallest monotone class containing $\mathcal{A}$

**응용**: Proving properties of integrals

자세한 내용은 [[Monotone Class Theorem]] 참조

## Carathéodory Extension Theorem

**정리**: $(X, \mathcal{A}, \mu)$가 measure space이고 $\mathcal{A}$가 algebra이면

$\mu$는 $\sigma(\mathcal{A})$로 unique하게 extend됨 (if $\mu$ is σ-finite)

**의미**: Measure를 algebra에서 sigma algebra로 확장 가능!

**응용**: Lebesgue measure의 construction

자세한 내용은 [[Caratheodory Extension Theorem]] 참조

## Borel Hierarchy

**정리**: Borel sets는 계층 구조를 가짐:

- $\mathbf{\Sigma}^0_1$: Open sets
- $\mathbf{\Pi}^0_1$: Closed sets  
- $\mathbf{\Sigma}^0_2$: $F_\sigma$ sets (countable union of closed)
- $\mathbf{\Pi}^0_2$: $G_\delta$ sets (countable intersection of open)
- $\vdots$

**Complexity**: Measures "how complicated" a Borel set is

자세한 내용은 [[Borel Hierarchy]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### What is Sigma Algebra?

**Intuition**: "측정 가능한 집합들의 모임"

**Why these axioms?**

**(1) $X \in \mathcal{F}$**: 전체 공간은 측정 가능해야 함

**(2) $A^c \in \mathcal{F}$**: $A$를 측정할 수 있으면 $A^c$도 측정 가능

**(3) Countable unions**: "분해하여 측정 가능"하면 합친 것도 측정 가능

### Why NOT Finite Unions Only?

**Reason**: Measure theory needs **limits**!

**Example**: 

$$[0, 1] = \bigcup_{n=1}^{\infty} \left[0, 1 - \frac{1}{n}\right]$$

Limit process requires countable operations

**Algebra vs Sigma Algebra**:
- Algebra: Finite operations only (too weak!)
- Sigma algebra: Countable operations (just right!)

### Geometric Picture

**Think of $\mathcal{F}$ as**:
- "Zoom levels" in $X$
- Finer sigma algebra = more detail
- Coarser sigma algebra = less detail

**Extremes**:
- $\{\emptyset, X\}$: No detail (trivial)
- $\mathcal{P}(X)$: All detail (power set)

## Why Countable, Not Uncountable?

**Question**: Why not allow uncountable unions?

**Answer**: Pathological behavior!

**Example** (Vitali set):

Uncountable unions can lead to non-measurable sets

**Countable**: "Large enough" for analysis, "small enough" to avoid pathology

**Compromise**: Balance between power and consistency

## Borel vs Lebesgue

### Borel Sigma Algebra

$$\mathcal{B}(\mathbb{R}) = \sigma(\{\text{open sets}\})$$

**크기**: Continuum ($2^{\aleph_0}$)

**특징**: Topologically defined

### Lebesgue Sigma Algebra

$$\mathcal{L} = \{\text{Lebesgue measurable sets}\}$$

**크기**: Much larger ($2^{2^{\aleph_0}}$)

**특징**: Measure-theoretically complete

### Relationship

$$\mathcal{B}(\mathbb{R}) \subsetneq \mathcal{L} \subsetneq \mathcal{P}(\mathbb{R})$$

**모든** Borel sets는 Lebesgue measurable

But:
- Non-Borel Lebesgue measurable sets exist
- Non-measurable sets exist (Axiom of Choice!)

자세한 내용은 [[Lebesgue Measure]] 참조

## Generating Sets

### Different Generators for Borel

**정리**: 다음은 모두 $\mathcal{B}(\mathbb{R})$를 생성:

**(a)** $\sigma(\{\text{open sets}\})$

**(b)** $\sigma(\{\text{closed sets}\})$

**(c)** $\sigma(\{(a, b) : a < b\})$ (open intervals)

**(d)** $\sigma(\{[a, b] : a \leq b\})$ (closed intervals)

**(e)** $\sigma(\{(-\infty, a) : a \in \mathbb{R}\})$ (half-lines)

**(f)** $\sigma(\{(-\infty, a] : a \in \mathbb{R}\})$

**(g)** $\sigma(\{(a, \infty) : a \in \mathbb{R}\})$

**(h)** $\sigma(\{[a, \infty) : a \in \mathbb{R}\})$

**증명 아이디어**: Show mutual containment

**의미**: Many "bases" for same sigma algebra!

**응용**: Choose convenient generator for proof

## Non-Measurable Sets

**Question**: Do non-measurable sets exist?

**Answer**: YES! (assuming Axiom of Choice)

### Vitali Set

**Construction**:
- Define $x \sim y \Leftrightarrow x - y \in \mathbb{Q}$
- Choose one representative from each equivalence class in $[0, 1]$
- Call this set $V$ (Vitali set)

**정리**: $V \notin \mathcal{L}$ (not Lebesgue measurable)

**증명**: 
- If $V$ measurable, then shifts $V + r$ measurable
- But $[0, 1] \subseteq \bigcup_{r \in \mathbb{Q} \cap [0,1]} (V + r) \subseteq [0, 2]$
- Leads to contradiction with countable additivity ✗

**주의**: Construction uses Axiom of Choice (essential!)

자세한 내용은 [[Vitali Set]] 참조

## Sigma Algebra in Probability

**Probability space**: $(\Omega, \mathcal{F}, P)$

where:
- $\Omega$: Sample space
- $\mathcal{F}$: Sigma algebra of **events**^[사건]
- $P$: Probability measure

**Interpretation**:
- $\mathcal{F}$: "Observable events"
- $A \in \mathcal{F}$: Event we can assign probability
- $A \notin \mathcal{F}$: "Undefined" event (pathological)

**Example**:
- Coin flip: $\Omega = \{H, T\}$, $\mathcal{F} = \mathcal{P}(\Omega)$
- Continuous random variable: $\Omega = \mathbb{R}$, $\mathcal{F} = \mathcal{B}(\mathbb{R})$

자세한 내용은 [[Probability]] 참조

## Information Interpretation

**Sub-sigma algebra** $\mathcal{G} \subseteq \mathcal{F}$: "Partial information"

**Finer**: $\mathcal{G}_1 \subseteq \mathcal{G}_2$: More information in $\mathcal{G}_2$

**Example** (Coin flips):

After 1 flip: $\mathcal{F}_1 = \sigma(\{H\}, \{T\})$

After 2 flips: $\mathcal{F}_2 = \sigma(\{HH\}, \{HT\}, \{TH\}, \{TT\})$

$\mathcal{F}_1 \subseteq \mathcal{F}_2$ (filtration!)

**응용**: 
- Conditional expectation: $E[X \mid \mathcal{G}]$
- Martingales: Adapted to filtration

자세한 내용은 [[Filtration]], [[Conditional Expectation]] 참조

## Computational Aspects

### Explicit Description

**Hard**: Describe $\sigma(\mathcal{E})$ explicitly!

**Usually**: Transfinite recursion needed

**Strategy**: Use π-λ theorem or monotone class theorem instead

### Checking Sigma Algebra

**직접**: Verify 3 axioms

**간접**: 
- Show it's generated by some set
- Use theorems (Dynkin, Monotone class)

### Cardinality

**Question**: How many sigma algebras on $X$?

**Answer**: Depends on $|X|$!

- $|X| = n$ finite: Complicated (related to partitions)
- $|X| = \aleph_0$: Continuum many
- $|X| = 2^{\aleph_0}$: Even more!

**관찰**: Usually continuum many sigma algebras

## Common Pitfall

### 1. Uncountable Unions

Sigma algebra는 **countable** unions에만 닫혀있음!

**실수**: Uncountable unions 시도

**예**: $\bigcup_{x \in \mathbb{R}} \{x\} = \mathbb{R}$ (uncountable union of singletons)

Each $\{x\}$ Borel, but reasoning requires **countable** union property

### 2. Algebra ≠ Sigma Algebra

**차이**: Finite vs countable unions

**예**: Finite unions만 사용하는 증명은 불충분!

### 3. Generation is Hard

$\sigma(\mathcal{E})$는 $\mathcal{E}$보다 **훨씬** 크고 복잡!

**실수**: $\sigma(\mathcal{E}) = \mathcal{E}$ (unless $\mathcal{E}$ already sigma algebra)

**실제**: $\sigma(\mathcal{E})$는 transfinite process로 구성

### 4. Non-Measurable Sets

"거의 모든" 집합이 measurable이지만, non-measurable sets 존재!

**주의**: Axiom of Choice 필요

**실용**: "Natural" sets는 대부분 measurable

### 5. Product Sigma Algebra

$$\mathcal{F}_1 \otimes \mathcal{F}_2 \neq \mathcal{F}_1 \times \mathcal{F}_2$$

**차이**: Generated vs Cartesian product

**실제**: $\mathcal{F}_1 \otimes \mathcal{F}_2 = \sigma(\mathcal{F}_1 \times \mathcal{F}_2)$

### 6. Borel Sets

"모든" 실수 집합이 Borel set? **NO!**

$$\mathcal{B}(\mathbb{R}) \subsetneq \mathcal{P}(\mathbb{R})$$

Non-Borel sets 존재 (but hard to construct!)

## Applications

### 1. Measure Theory

**Foundation**: $(X, \mathcal{F}, \mu)$ measure space

Sigma algebra defines "measurable sets"

자세한 내용은 [[Measure Space]] 참조

### 2. Probability Theory

**Probability space**: $(\Omega, \mathcal{F}, P)$

$\mathcal{F}$ = events we can assign probability

자세한 내용은 [[Probability]] 참조

### 3. Integration Theory

**Measurable functions**: $f: (X, \mathcal{F}) \to (\mathbb{R}, \mathcal{B})$

$$f^{-1}(B) \in \mathcal{F} \text{ for all } B \in \mathcal{B}$$

자세한 내용은 [[Measurable Function]] 참조

### 4. Ergodic Theory

**Invariant sigma algebra**: 

$$\mathcal{I} = \{A \in \mathcal{F} : T^{-1}(A) = A\}$$

자세한 내용은 [[Ergodic Theory]] 참조

### 5. Stochastic Processes

**Filtration**: $\{\mathcal{F}_t\}_{t \geq 0}$

Information available at time $t$

자세한 내용은 [[Filtration]] 참조

## 관련 개념

- [[Measure Space]]: $(X, \mathcal{F}, \mu)$ with measure
- [[Borel Sigma Algebra]]: $\sigma(\{\text{open sets}\})$
- [[Measure]]: $\mu: \mathcal{F} \to [0, \infty]$
- [[Measurable Function]]: $f^{-1}(\text{Borel}) \in \mathcal{F}$
- [[Probability]]: Probability measure on sigma algebra
- [[Lebesgue Measure]]: Completion of Borel measure
- [[Product Sigma Algebra]]: $\mathcal{F}_1 \otimes \mathcal{F}_2$
- [[Filtration]]: Increasing family of sigma algebras
- [[Dynkin System]]: π-λ theorem
- [[Monotone Class Theorem]]: Alternative to sigma algebra

## 추가 학습 주제

**기초**:
- Definition and axioms
- Basic properties (intersection, difference)
- Simple examples (power set, trivial)
- Generated sigma algebra

**중급**:
- Borel sigma algebra
- Product sigma algebra
- π-λ theorem
- Monotone class theorem
- Measurable functions

**고급**:
- Non-measurable sets (Vitali)
- Borel hierarchy
- Descriptive set theory
- Universal completion
- Cardinality issues
- Abstract measure theory

