# <span class="header-prerequisite">Prerequisite</span>
- [[Function]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Mac Lane, Categories for the Working Mathematician
- Hungerford, Algebra

---

# <span class="header-definition">Definition</span>

## Monoid^[모노이드]

**Monoid**^[모노이드]: Set $M$ with binary operation $\cdot$ satisfying

1. **Associativity**^[결합법칙]: $(a \cdot b) \cdot c = a \cdot (b \cdot c)$ for all $a, b, c \in M$
2. **Identity element**^[항등원]: $\exists e \in M$ : $e \cdot a = a \cdot e = a$ for all $a \in M$

**표기**: $(M, \cdot, e)$ or simply $M$

**의미**: "Group without inverses"

### 비교: Group

**Group**^[군] = Monoid + inverses^[역원]

$$\text{Group} = \text{Monoid} + \text{(inverse elements)}$$

자세한 내용은 [[Group]] 참조

## Identity Element

**Identity**^[항등원] $e \in M$:

$$e \cdot a = a \cdot e = a \quad \text{for all } a \in M$$

**정리**: Identity is unique

**증명**: If $e, e'$ both identity,

$$e = e \cdot e' = e'$$ ✓

## Monoid Homomorphism^[모노이드 준동형]

**Homomorphism**^[준동형] $f: M \to N$ between monoids:

$$f(a \cdot b) = f(a) \cdot f(b) \quad \text{and} \quad f(e_M) = e_N$$

**의미**: Preserves operation and identity

자세한 내용은 [[Homomorphism]] 참조

---

# <span class="header-properties">Properties</span>

## Associativity

**No parentheses needed**:

$$a_1 \cdot a_2 \cdot \cdots \cdot a_n$$

well-defined regardless of bracketing

## Identity Uniqueness

**정리**: Identity element is unique

**증명**: 위 참조 ✓

## Powers

**Positive powers**: $a^n = \underbrace{a \cdot a \cdots a}_{n \text{ times}}$

**Zero power**: $a^0 = e$

**Laws**:
- $a^m \cdot a^n = a^{m+n}$
- $(a^m)^n = a^{mn}$

**주의**: Negative powers NOT defined (no inverses in general)

## Submonoids

**Submonoid**^[부분 모노이드]: Subset $N \subseteq M$ that is monoid with:
- Same operation
- Same identity $e$

**조건**:
1. $e \in N$
2. Closed under operation: $a, b \in N$ $\Rightarrow$ $a \cdot b \in N$

자세한 내용은 [[Subgroup]] 참조 (similar concept)

## Invertible Elements

**Unit**^[단원]: Element $a \in M$ with inverse

$$\exists b \in M : a \cdot b = b \cdot a = e$$

**Group of units**: $M^{\times} = \{a \in M : a \text{ invertible}\}$

$$M^{\times} \leq M \quad (\text{forms a group!})$$

---

# <span class="header-examples">Examples</span>

## Example 1: Natural Numbers

$$(\mathbb{N}, +, 0)$$

**Operation**: Addition

**Identity**: $0$

**Monoid**: Yes ✓

**Group**: No ✗ (no negatives)

## Example 2: Positive Integers (Multiplication)

$$(\mathbb{N}^+, \times, 1)$$

**Operation**: Multiplication

**Identity**: $1$

**Monoid**: Yes ✓

**Group**: No ✗ (no reciprocals except for $1$)

**Units**: $M^{\times} = \{1\}$

## Example 3: Strings

**$\Sigma^*$**: Set of all strings over alphabet $\Sigma$

**Operation**: Concatenation

**Identity**: Empty string $\varepsilon$

**Monoid**: Yes ✓ (free monoid)

**예**:
- $\Sigma = \{a, b\}$
- $ab \cdot ba = abba$
- $\varepsilon \cdot ab = ab$

## Example 4: Functions

**$M = \{f: X \to X\}$**: Endomorphisms of set $X$

**Operation**: Composition $\circ$

**Identity**: $\text{id}_X$

**Monoid**: Yes ✓

**Units**: $M^{\times} = \text{Bij}(X)$ (bijections = group)

## Example 5: Matrices

**$M_n(\mathbb{R})$**: $n \times n$ real matrices

**Operation**: Matrix multiplication

**Identity**: Identity matrix $I_n$

**Monoid**: Yes ✓

**Units**: $M^{\times} = \text{GL}_n(\mathbb{R})$ (invertible matrices)

## Example 6: Lists

**Lists over type $A$**:

**Operation**: Concatenation $++$

**Identity**: Empty list $[]$

**Monoid**: Yes ✓

**응용**: Functional programming

## Example 7: Boolean AND/OR

**$(\{0, 1\}, \land, 1)$**: Boolean AND

**$(\{0, 1\}, \lor, 0)$**: Boolean OR

Both are monoids!

**Units**: 
- AND: $M^{\times} = \{1\}$
- OR: $M^{\times} = \{1\}$

## Example 8: Trivial Monoid

**$M = \{e\}$**: Single element

**Operation**: $e \cdot e = e$

**Identity**: $e$

**Monoid**: Yes ✓ (also a group!)

---

# <span class="header-theorem">Theorem</span>

## Free Monoid

**정리**: For any set $S$, $\exists$ **free monoid**^[자유 모노이드] $M(S)$

$$M(S) = S^* = \{\text{finite sequences from } S\}$$

**Operation**: Concatenation

**Identity**: Empty sequence

**Universal property**: For any $f: S \to N$ (set map to monoid $N$),

$$\exists ! \text{ homomorphism } \phi: M(S) \to N \text{ extending } f$$

**의미**: "Most general" monoid on $S$

자세한 내용은 [[Free Group]] 참조 (similar concept)

## Cayley's Theorem for Monoids

**정리**: Every monoid embeds into transformation monoid

$$M \hookrightarrow \text{End}(M)$$

via left multiplication: $a \mapsto (x \mapsto a \cdot x)$

자세한 내용은 [[Cayley's Theorem]] 참조

## Group of Units

**정리**: $M^{\times}$ forms a group

**증명**: 
- Identity: $e \in M^{\times}$ ✓
- Closure: $a, b$ invertible $\Rightarrow$ $ab$ invertible (inverse $b^{-1}a^{-1}$) ✓
- Inverses: By definition ✓
- Associativity: Inherited ✓

## Monoid Isomorphism

**정리**: Monoids $M, N$ isomorphic $\Leftrightarrow$

$$\exists \text{ bijection } f: M \to N \text{ preserving operation and identity}$$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Monoid = "Sequential composition"**

### 메타포: 레고 조립

**Monoid elements**: 레고 블록들

**Operation**: 블록 연결 (한 방향으로만)

**Identity**: 빈 블록 (아무것도 안함)

**No inverses**: 연결한 것 분리 불가

### 메타포: 문자열 연결

**Elements**: 문자열 `"hello"`, `"world"`

**Operation**: 연결 `"hello" + "world" = "helloworld"`

**Identity**: Empty string `""`

**No inverses**: `"hello" + ? ≠ ""` (no inverse)

### 메타포: 요리 과정

**Elements**: 요리 단계들

**Operation**: 순차 실행

**Identity**: "아무것도 안함"

**No inverses**: 요리는 되돌릴 수 없음!

## 왜 중요한가?

### 1. Generalization

**More general than groups**: 역원 필요 없음

**More structures**: 많은 예시들

### 2. Computer Science

**Programming**: Lists, strings, operations

**Functional programming**: Monoid pattern

**Parallel computation**: Associativity enables parallelism

### 3. Category Theory

**Monoid**: Object in category with one object

**Monoidal categories**: Generalization

자세한 내용은 [[Category Theory]] 참조

### 4. Formal Languages

**Regular languages**: Monoids of strings

**Automata theory**: State transitions

### 5. Combinatorics

**Counting**: Compositions, sequences

**Generating functions**: Monoid operations

## Monoid vs Group

| | **Monoid** | **Group** |
|---|---|---|
| **Associativity** | Yes ✓ | Yes ✓ |
| **Identity** | Yes ✓ | Yes ✓ |
| **Inverses** | No ✗ | Yes ✓ |
| **예** | $(\mathbb{N}, +)$ | $(\mathbb{Z}, +)$ |
| **예** | Strings | Permutations |
| **Cancellation** | Not always | Always |

**관계**: Group = Monoid with inverses

자세한 내용은 [[Group]] 참조

## Monoid vs Semigroup

| | **Semigroup** | **Monoid** |
|---|---|---|
| **Associativity** | Yes ✓ | Yes ✓ |
| **Identity** | No ✗ | Yes ✓ |
| **Inverses** | No ✗ | No ✗ |

**관계**: Monoid = Semigroup with identity

$$\text{Semigroup} \subseteq \text{Monoid} \subseteq \text{Group}$$

## 계산 방법

### Verify Monoid

**Step 1**: Check associativity $(ab)c = a(bc)$

**Step 2**: Find identity $e$

**Step 3**: Verify $ea = ae = a$ for all $a$

### Find Units

**Step 1**: For each $a \in M$, check if $\exists b$ : $ab = ba = e$

**Step 2**: Collect all such $a$ into $M^{\times}$

### Monoid Table

For finite monoid, write multiplication table

**예**: $M = \{e, a, b\}$

| $\cdot$ | $e$ | $a$ | $b$ |
|---|---|---|---|
| $e$ | $e$ | $a$ | $b$ |
| $a$ | $a$ | $a$ | ? |
| $b$ | $b$ | ? | ? |

Fill in to satisfy associativity

## 표기법

| 표기 | 의미 |
|------|------|
| $(M, \cdot, e)$ | Monoid with operation $\cdot$, identity $e$ |
| $M^{\times}$ | Group of units |
| $S^*$ or $M(S)$ | Free monoid on $S$ |
| $\varepsilon$ | Empty string (identity) |
| $\text{End}(X)$ | Endomorphism monoid |

## Common Pitfall^[흔한 실수]

### 1. Not all elements have inverses

Monoid ≠ Group!

**예**: $\mathbb{N}$ under $+$, only $0$ has inverse (itself)

### 2. Identity must exist

Without identity, just semigroup

**예**: Positive integers under addition (no 0) = semigroup

### 3. Commutativity NOT required

**Abelian**: $ab = ba$ (special case)

**General**: $ab \neq ba$ possible

**예**: Matrix multiplication, string concatenation

### 4. $a^0 = e$ always

Even if $a$ not invertible!

**Convention**: $a^0 = e$ by definition

### 5. Submonoid must contain identity

**Subset**: Not enough

**Must have**: Same identity element

## 응용 분야

**Computer Science**:
- Data structures (lists, trees)
- Functional programming (monoid pattern)
- Parallel algorithms (associativity)
- Regular expressions

**Mathematics**:
- Category theory
- Formal languages
- Combinatorics
- Topology (homotopy)

**Physics**:
- Quantum mechanics (operators without inverse)
- Statistical mechanics

**Cryptography**:
- Hash functions (monoid structure)

## Programming Example

### Haskell Monoid Type Class

```haskell
class Monoid m where
  mempty :: m           -- identity
  mappend :: m -> m -> m  -- operation
  
instance Monoid [a] where
  mempty = []
  mappend = (++)
```

**예시**:
- Lists: `mempty = []`, `mappend = ++`
- Numbers: `mempty = 0`, `mappend = +`
- Numbers: `mempty = 1`, `mappend = *`

## 특별한 Monoids

### Commutative Monoid

**Abelian monoid**^[아벨 모노이드]: $ab = ba$ for all $a, b$

**예**: $(\mathbb{N}, +)$, $(\mathbb{N}, \times)$

자세한 내용은 [[Abelian Group]] 참조

### Cancellative Monoid

**Cancellative**^[소거 가능]: $ac = bc$ $\Rightarrow$ $a = b$

**예**: $(\mathbb{N}, +)$ cancellative

**Non-example**: $(\mathbb{N}, \times)$ not cancellative ($0 \cdot a = 0 \cdot b$ doesn't imply $a = b$)

### Free Monoid

**Free on set $S$**: $S^*$ = finite sequences

**No relations**: Completely free

자세한 내용은 [[Free Group]] 참조

## 관련 개념

- [[Group]]: Monoid with inverses
- [[Ring]]: Two monoid structures (addition + multiplication)
- [[Category Theory]]: Monoid as one-object category
- [[Homomorphism]]: Structure-preserving maps
- [[Free Group]]: Similar to free monoid

## 추가 학습 주제

**기초**:
- Definition
- Examples
- Group of units

**중급**:
- Free monoids
- Monoid homomorphisms
- Submonoids

**고급**:
- Monoid actions
- Monoidal categories
- Green's relations
- Rees theorem
- Automata and monoids
- Syntactic monoids

