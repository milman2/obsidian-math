# <span class="header-prerequisite">Prerequisite</span>
- [[Binary Operation]]
- [[Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Hungerford, Algebra
- Aluffi, Algebra: Chapter 0

---

# <span class="header-definition">Definition</span>

## Semigroup^[반군]

집합 $S$와 binary operation^[이항 연산] $\cdot: S \times S \to S$에 대해, $(S, \cdot)$가 **semigroup**^[반군]이다 $\Leftrightarrow$ 다음을 만족:

**1. Closure**^[닫혀있음]:

$$\forall a, b \in S, \quad a \cdot b \in S$$

**2. Associativity**^[결합법칙]:

$$\forall a, b, c \in S, \quad (a \cdot b) \cdot c = a \cdot (b \cdot c)$$

**핵심**: Group의 공리 중 **항등원**과 **역원**이 없는 구조

---

## Monoid^[모노이드]

Semigroup $(S, \cdot)$가 **monoid**^[모노이드]이다 $\Leftrightarrow$ **identity element**^[항등원] $e \in S$가 존재:

$$\forall a \in S, \quad e \cdot a = a \cdot e = a$$

**관계**: 
- Semigroup ⊂ Monoid ⊂ Group
- Monoid = Semigroup + Identity
- Group = Monoid + Inverse

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. No Cancellation Law (일반적으로)

Semigroup에서:

$$a \cdot b = a \cdot c \not\Rightarrow b = c$$

**반례**: Semigroup of functions under composition

### 2. Powers

원소 $a \in S$에 대해 $a^n$ (for $n \geq 1$) 정의 가능:

$$a^1 = a, \quad a^{n+1} = a^n \cdot a$$

**성질**: $a^m \cdot a^n = a^{m+n}$, $(a^m)^n = a^{mn}$

### 3. Subsemigroup^[부분반군]

$T \subseteq S$가 **subsemigroup**^[부분반군]이다 $\Leftrightarrow$ $T$가 $S$의 연산으로 semigroup

**조건**: $\forall a, b \in T, \; a \cdot b \in T$ (closure만 확인!)

### 4. Idempotent^[멱등원]

원소 $e \in S$가 **idempotent**^[멱등원]이다 $\Leftrightarrow$

$$e \cdot e = e$$

**예**: 
- $0, 1$ in $(\mathbb{N}, \max)$
- Projection maps in function composition

---

# <span class="header-examples">Examples</span>

## Example 1: Natural Numbers under Addition

$$(\mathbb{N}, +)$$

**Verification**:
- Closure: $m + n \in \mathbb{N}$
- Associativity: $(m + n) + p = m + (n + p)$
- Identity: $0 \in \mathbb{N}$ (monoid)
- No inverse: $n > 0$에 대해 $-n \notin \mathbb{N}$

**결론**: Monoid이지만 group이 아님

## Example 2: Natural Numbers under Multiplication

$$(\mathbb{N}, \times)$$

**Verification**:
- Closure: $m \times n \in \mathbb{N}$
- Associativity: $(m \times n) \times p = m \times (n \times p)$
- Identity: $1$
- No inverse: $n > 1$에 대해 $1/n \notin \mathbb{N}$

**결론**: Monoid (not group)

## Example 3: Non-empty Strings

$$S = \{a, b, c, \ldots\}^* \setminus \{\epsilon\}$$

**Operation**: Concatenation

**Properties**:
- Semigroup
- Not monoid (empty string excluded)

**With empty string** $\{a, b, c, \ldots\}^*$: **Free monoid**^[자유 모노이드]

## Example 4: Functions under Composition

$$S = \{f: X \to X\}$$

**Operation**: Composition $\circ$

**Properties**:
- Associativity: $(f \circ g) \circ h = f \circ (g \circ h)$
- Identity: $\text{id}_X$ (monoid)
- Not group: Not all functions invertible

**Subset**: Bijective functions = symmetric group $S_X$

## Example 5: Matrices under Multiplication

$$M_n(\mathbb{R})$$

**Operation**: Matrix multiplication

**Properties**:
- Associativity
- Identity: $I_n$ (monoid)
- Not group: Singular matrices have no inverse

**Subset**: $GL_n(\mathbb{R})$ (invertible matrices) = group

## Example 6: Max/Min Semigroups

$$(\mathbb{R}, \max)$$ 또는 $$(\mathbb{R}, \min)$$

**Verification**:
- Closure: $\max(a, b) \in \mathbb{R}$
- Associativity: $\max(a, \max(b, c)) = \max(\max(a, b), c)$
- Identity for $\max$: $-\infty$ (extended reals)
- No inverse

## Example 7: Non-negative Reals under Addition

$$(\mathbb{R}_{\geq 0}, +)$$

**Properties**:
- Semigroup
- Monoid (identity = $0$)
- Not group (no inverse for $a > 0$)

## Example 8: Power Set with Intersection

$$(2^X, \cap)$$

**Properties**:
- Associativity: $(A \cap B) \cap C = A \cap (B \cap C)$
- Identity: $X$ (monoid)
- Idempotent: $A \cap A = A$ for all $A$

---

# <span class="header-theorem">Important Theorems</span>

## Cayley's Theorem for Semigroups

**정리**: Every semigroup $S$ embeds into the **full transformation semigroup**^[전변환 반군] on some set.

$$S \hookrightarrow T_X$$

where $T_X$ = all functions $X \to X$ under composition

**의미**: Semigroups can be represented by transformations

## Green's Relations

Semigroup $S$에서 다음 equivalence relations^[동치 관계] 정의:

**1. $\mathcal{L}$-relation** (left):

$$a \mathcal{L} b \Leftrightarrow S^1 a = S^1 b$$

**2. $\mathcal{R}$-relation** (right):

$$a \mathcal{R} b \Leftrightarrow a S^1 = b S^1$$

**3. $\mathcal{J}$-relation** (two-sided):

$$a \mathcal{J} b \Leftrightarrow S^1 a S^1 = S^1 b S^1$$

**4. $\mathcal{H}$-relation**:

$$\mathcal{H} = \mathcal{L} \cap \mathcal{R}$$

**5. $\mathcal{D}$-relation**:

$$\mathcal{D} = \mathcal{L} \circ \mathcal{R} = \mathcal{R} \circ \mathcal{L}$$

여기서 $S^1 = S \cup \{e\}$ (identity 추가)

**의미**: Semigroup의 구조를 분석하는 도구

---

# <span class="header-remark">Remark</span>

## Algebraic Hierarchy

$$\text{Semigroup} \subseteq \text{Monoid} \subseteq \text{Group}$$

**비교표**:

| Structure | Closure | Associativity | Identity | Inverse |
|-----------|---------|---------------|----------|---------|
| **Semigroup** | ✓ | ✓ | ✗ | ✗ |
| **Monoid** | ✓ | ✓ | ✓ | ✗ |
| **Group** | ✓ | ✓ | ✓ | ✓ |

## Commutative Semigroups

Semigroup $(S, \cdot)$가 **commutative**^[가환]이다 $\Leftrightarrow$

$$\forall a, b \in S, \quad a \cdot b = b \cdot a$$

**예**: $(\mathbb{N}, +)$, $(\mathbb{N}, \times)$

## Free Semigroups

Set $X$에 대한 **free semigroup**^[자유 반군] $X^+$:

$$X^+ = \{\text{non-empty finite sequences from } X\}$$

**Operation**: Concatenation

**Universal property**^[보편 성질]: 모든 function $f: X \to S$ (where $S$ is semigroup)는 unique homomorphism $\bar{f}: X^+ \to S$로 확장

## Applications

### 1. Computer Science

- **Regular languages**: Recognized by finite semigroups
- **Automata theory**: State transitions form semigroup
- **Formal languages**: Strings under concatenation

### 2. Theoretical Computer Science

- **Complexity theory**: Transformation monoids
- **Formal verification**: Semigroup actions
- **Concurrency**: Process algebras

### 3. Abstract Algebra

- **Building blocks**: Understanding group structure
- **Category theory**: Monoids as one-object categories
- **Universal algebra**: Varieties of semigroups

### 4. Functional Analysis

- **Operator semigroups**: Evolution equations
- **C₀-semigroups**: Continuous parameter semigroups
- **Semigroup of operators**: $T(t): X \to X$ for $t \geq 0$

## Commutative Monoid vs Abelian Group

**Commutative monoid**: $(\mathbb{N}, +)$
- 모든 원소에 inverse 없음
- Grothendieck construction으로 $\mathbb{Z}$ 얻음

**Abelian group**: $(\mathbb{Z}, +)$
- 모든 원소에 inverse 있음

**일반화**: Commutative monoid에서 group 구성 가능 (group completion)

## 관련 개념

- [[Group]]: Semigroup + Identity + Inverse
- [[Monoid]]: Semigroup + Identity
- [[Binary Operation]]: 기본 연산 구조
- [[Homomorphism]]: Structure-preserving maps
- [[Category Theory]]: Monoids as categories
- [[Free Group]]: Free constructions

