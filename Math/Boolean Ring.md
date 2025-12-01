# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Field]]
- [[Commutator in Ring]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Stone, The Theory of Representations for Boolean Algebras

---

# <span class="header-definition">Definition</span>

## Boolean Ring^[불 환]

Ring $R$이 **Boolean ring^[불 환]**이다 $\Leftrightarrow$

$$\forall a \in R, \quad a^2 = a$$

**의미**: 모든 원소가 **idempotent^[멱등원]**

**표기**: Often denoted as $B$ for Boolean ring

자세한 내용은 [[Ring]] 참조

## Idempotent Element^[멱등원]

Ring $R$의 원소 $e \in R$이 **idempotent^[멱등원]**이다 $\Leftrightarrow$

$$e^2 = e$$

**예**: 
- $0^2 = 0$ - $1^2 = 1$ - In $\mathbb{Z}/6\mathbb{Z}$: $\overline{3}^2 = \overline{3}$ 
**Boolean ring**: 모든 원소가 idempotent!

## Boolean Algebra^[불 대수]

**Boolean algebra^[불 대수]**: Set with operations $\land$ (AND), $\lor$ (OR), $\neg$ (NOT)

**관계**: Boolean ring $\leftrightarrow$ Boolean algebra (isomorphic structures)

**변환**:
- $a \land b \leftrightarrow ab$ (multiplication)
- $a \lor b \leftrightarrow a + b + ab$ (symmetric difference + product)
- $\neg a \leftrightarrow 1 + a$ (complement)

---

# <span class="header-properties">Properties</span>

## Every Boolean Ring is Commutative

**정리**: Boolean ring $R$ $\Rightarrow$ $R$ commutative

**증명**:

For any $a, b \in R$:

$$(a + b)^2 = a + b \quad (\text{idempotent})$$

Expand left side:

$$(a + b)^2 = a^2 + ab + ba + b^2 = a + ab + ba + b$$

따라서:

$$a + ab + ba + b = a + b$$

$$ab + ba = 0$$

$$ab = -ba$$

But $2a = a + a = (a + a)^2 = a^2 + 2a^2 + a^2 = 4a^2 = 4a$

$\Rightarrow$ $2a = 0$ for all $a$

Therefore $-ba = ba$, so:

$$ab = ba$$ 
**의미**: Idempotency automatically implies commutativity!

## Characteristic 2

**정리**: Boolean ring has characteristic 2

**증명**: For any $a \in R$:

$$2a = a + a = (a + a)^2 = a^2 + 2a^2 + a^2 = 4a$$

$$2a = 4a \Rightarrow 2a = 0$$ 
**의미**: $a + a = 0$ for all $a$ (every element is its own additive inverse)

## No Nilpotent Elements (except 0)

**정리**: If $a^n = 0$ in Boolean ring, then $a = 0$

**증명**: $a^2 = a$ $\Rightarrow$ $a^3 = a^2 \cdot a = a \cdot a = a^2 = a$

By induction: $a^n = a$ for all $n \geq 1$

If $a^n = 0$, then $a = 0$ 
## Subtraction = Addition

**정리**: $a - b = a + b$ in Boolean ring

**증명**: $-b = b$ (since $2b = 0$)

Therefore $a - b = a + (-b) = a + b$ 
**의미**: Addition and subtraction are same operation!

## Prime Ideals are Maximal

**정리**: In Boolean ring, every prime ideal is maximal

**증명**: For Boolean ring $B$, $B/P$ is Boolean ring and integral domain

$\Rightarrow$ $B/P$ has no zero divisors and idempotent

$\Rightarrow$ $B/P \cong \mathbb{Z}/2\mathbb{Z}$ (field!)

$\Rightarrow$ $P$ maximal 
자세한 내용은 [[Ring]] 참조 (Prime and Maximal Ideals)

## Units

**정리**: In Boolean ring with identity, units are $\{0, 1\}$ only

**증명**: If $u$ unit, then $u^2 = u$ and $\exists v$ : $uv = 1$

From $u^2 = u$: $u(u-1) = 0$

If $u \neq 0$, then $u - 1 = 0$ (no zero divisors in field)

Therefore $u = 1$ 
---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}/2\mathbb{Z}$

$$\mathbb{Z}/2\mathbb{Z} = \{0, 1\}$$

**Operations**: 
- $0 + 0 = 0$, $0 + 1 = 1 + 0 = 1$, $1 + 1 = 0$
- $0 \cdot 0 = 0$, $0 \cdot 1 = 1 \cdot 0 = 0$, $1 \cdot 1 = 1$

**Check**: $0^2 = 0$ , $1^2 = 1$ 
**Simplest non-trivial Boolean ring**

자세한 내용은 [[Field]] 참조

## Example 2: Power Set Ring

**$\mathcal{P}(X)$**: Power set of set $X$

**Operations**:
- Addition: $A + B = A \triangle B$ (symmetric difference)
- Multiplication: $A \cdot B = A \cap B$ (intersection)

**Check**: 
- $(A \cap B) \cap (A \cap B) = A \cap B$  (idempotent)
- Identity: $X$ (for multiplication), $\emptyset$ (for addition)

**Boolean ring**: Yes 
## Example 3: Direct Product

$$R = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z} \times \cdots \times \mathbb{Z}/2\mathbb{Z}$$

**Componentwise operations**:

$$(a_1, \ldots, a_n) \cdot (b_1, \ldots, b_n) = (a_1b_1, \ldots, a_nb_n)$$

**Check**: $(a_i)^2 = a_i$ for each component 
**Boolean ring**: Yes 
## Example 4: Continuous Functions

$$C(X, \mathbb{Z}/2\mathbb{Z}) = \{f: X \to \mathbb{Z}/2\mathbb{Z} \mid f \text{ continuous}\}$$

**Pointwise operations**: $(f \cdot g)(x) = f(x) \cdot g(x)$

**Check**: $(f^2)(x) = f(x)^2 = f(x)$ for all $x$ 
**Boolean ring**: Yes 
## Example 5: Finite Boolean Ring

**Order $2^n$**: Every finite Boolean ring has order $2^n$

**Structure**: 

$$B \cong \mathbb{Z}/2\mathbb{Z} \times \cdots \times \mathbb{Z}/2\mathbb{Z} \quad (n \text{ times})$$

자세한 내용은 [[Direct Product]] (if exists)

## Example 6: Matrix Example (Diagonal)

$$R = \left\{ \begin{pmatrix} a & 0 \\ 0 & b \end{pmatrix} : a, b \in \mathbb{Z}/2\mathbb{Z} \right\}$$

**Check**: 
$$\begin{pmatrix} a & 0 \\ 0 & b \end{pmatrix}^2 = \begin{pmatrix} a^2 & 0 \\ 0 & b^2 \end{pmatrix} = \begin{pmatrix} a & 0 \\ 0 & b \end{pmatrix}$$ 
**Boolean ring**: Yes 
---

# <span class="header-theorem">Theorem</span>

## Stone's Representation Theorem

**정리**: Every Boolean ring $B$ is isomorphic to a ring of subsets of some set

$$B \cong \text{subring of } \mathcal{P}(X)$$

for some set $X$ (with symmetric difference and intersection)

**의미**: Boolean rings = "algebra of sets"

**Proof sketch**: Take $X$ = prime ideals (spectrum), use Zariski topology

## Classification of Finite Boolean Rings

**정리**: Every finite Boolean ring has order $2^n$ and

$$B \cong \underbrace{\mathbb{Z}/2\mathbb{Z} \times \cdots \times \mathbb{Z}/2\mathbb{Z}}_{n \text{ times}}$$

**증명**: Boolean ring $\Rightarrow$ characteristic 2 $\Rightarrow$ vector space over $\mathbb{F}_2$

Idempotency determines unique structure 
## Spectrum of Boolean Ring

**정리**: Spectrum Spec$(B)$ of Boolean ring is totally disconnected

**의미**: No continuous paths (discrete-like topology)

**응용**: Topology, logic

## Boolean Rings are von Neumann Regular

**정리**: Boolean ring $B$ is **von Neumann regular**

$$\forall a \in B, \; \exists x \in B : a = axa$$

**증명**: Take $x = a$:

$$axa = a \cdot a \cdot a = a^3 = a$$ 
(using $a^2 = a$)

## Ideals in Boolean Rings

**정리**: Ideal $I$ in Boolean ring $B$ is generated by idempotents

**Moreover**: Every ideal is semiprime

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Boolean Ring = "Algebra of Sets"**

### 메타포: 스위치

**원소**: 스위치 (ON/OFF = 1/0)

**곱셈**: AND gate (both on)

**덧셈**: XOR gate (exclusive or)

**Idempotency**: $a^2 = a$ (스위치를 두 번 적용 = 한 번)

### 메타포: 집합 연산

**원소**: Sets

**곱셈**: Intersection $\cap$

**덧셈**: Symmetric difference $\triangle$

**Idempotency**: $A \cap A = A$ 
### 메타포: 논리

**원소**: Propositions (true/false)

**곱셈**: AND

**덧셈**: XOR

**Complement**: $\neg a = 1 + a$

## 왜 중요한가?

### 1. Logic and Computer Science

**Boolean algebra**: Foundation of logic circuits

**Applications**: Digital design, computer architecture

### 2. Set Theory

**Stone representation**: Every Boolean ring ≈ algebra of sets

**Topology**: Stone spaces

### 3. Measure Theory

**Measurable sets**: Form Boolean algebra

**$\sigma$-algebras**: Infinite analog

### 4. Topology

**Clopen sets**: Closed and open (Boolean algebra structure)

**Stone-Čech compactification**: Uses Boolean rings

### 5. Logic

**Propositional logic**: Boolean algebra structure

**Model theory**: Stone duality

## Boolean Ring vs Boolean Algebra

| | **Boolean Ring** | **Boolean Algebra** |
|---|---|---|
| **Addition** | XOR ($a + b + ab$) | OR ($a \lor b$) |
| **Multiplication** | AND ($ab$) | AND ($a \land b$) |
| **Complement** | $1 + a$ | $\neg a$ |
| **Structure** | Ring axioms | Lattice axioms |
| **0 element** | Additive identity | Bottom |
| **1 element** | Multiplicative identity | Top |

**관계**: Isomorphic structures (same thing, different language!)

## 계산 방법

### Verify Boolean Ring

**Step 1**: Check $a^2 = a$ for all $a$

**Step 2**: Verify ring axioms (if not already known)

**Step 3**: Note commutativity (automatic!)

### Operations

**Addition**: Symmetric difference (XOR)

$$a + b = a + b - 2ab \quad (\text{in any ring})$$

In Boolean ring: $= a + b$ (since $2ab = 0$)

**Multiplication**: Intersection (AND)

### Complement

If Boolean ring has identity 1:

$$\text{Complement of } a = 1 - a = 1 + a$$

(since $-a = a$ in characteristic 2)

## 표기법

| 표기 | 의미 |
|------|------|
| $a^2 = a$ | Idempotent property |
| $\mathcal{P}(X)$ | Power set of $X$ |
| $A \triangle B$ | Symmetric difference |
| $\mathbb{Z}/2\mathbb{Z}$ | Field with 2 elements |
| Spec$(B)$ | Spectrum (prime ideals) |

## Common Pitfall^[흔한 실수]

### 1. Addition ≠ OR

In Boolean ring: addition = XOR, not OR!

**OR**: $a \lor b = a + b + ab$ (in Boolean ring)

**XOR**: $a \oplus b = a + b$ (in Boolean ring)

### 2. Assuming $a + a = a$

✗ Wrong! $a + a = 0$ in Boolean ring

Idempotency: $a \cdot a = a$ (multiplication!)

### 3. $\mathbb{Z}$ is NOT Boolean

$2^2 = 4 \neq 2$ ✗

Only rings of characteristic 2 can be Boolean

### 4. Not all idempotents form Boolean ring

**예**: $\mathbb{Z}/6\mathbb{Z}$ has idempotents $\{0, 1, 3, 4\}$

But not closed under addition! (e.g., $3 + 3 = 0$)

### 5. Boolean ring $\neq$ Boolean algebra (notation)

Same structure, different operations notation!

## 응용 분야

**Computer Science**:
- Digital logic design
- Boolean circuits
- Binary operations
- Set operations in databases

**Mathematics**:
- Topology (Stone spaces)
- Measure theory
- Logic and model theory
- Algebraic geometry (étale cohomology)

**Physics**:
- Quantum logic
- Event algebras

**Engineering**:
- Digital signal processing
- Error correction codes

## 역사적 맥락

**George Boole** (1815-1864): Boolean algebra for logic

**Marshall Stone** (1936): Stone representation theorem

**연결**: Boolean algebra $\leftrightarrow$ Boolean ring

**현대**: Foundations of computer science

## 특별한 성질들

### 1. Self-dual

Boolean rings have natural duality (Stone duality)

### 2. Reduced

No nilpotent elements (except 0)

### 3. Zero-dimensional

Spectrum is zero-dimensional (Krull dimension 0)

### 4. Totally disconnected

Topologically discrete-like

## 관련 개념

- [[Ring]]: Basic structure
- [[Field]]: $\mathbb{Z}/2\mathbb{Z}$ is field and Boolean ring
- [[Commutator in Ring]]: All commutators = 0 (commutative)

## 추가 학습 주제

**기초**:
- Definition
- Examples
- Basic properties

**중급**:
- Stone representation
- Boolean algebras
- Spectrum

**고급**:
- Stone spaces
- Stone-Čech compactification
- Boolean topoi
- Forcing in set theory
- Stone duality
- Boolean-valued models

