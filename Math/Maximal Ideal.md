# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Ideal]]
- [[Field]]
- [[Quotient Ring]]
- [[Prime Ideal]]

# <span class="header-reference">Reference</span>
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Dummit & Foote, Abstract Algebra
- Eisenbud, Commutative Algebra with a View Toward Algebraic Geometry

---

# <span class="header-definition">Definition</span>

## Maximal Ideal^[극대 아이디얼]

Commutative ring $R$의 proper ideal^[진 아이디얼] $M$이 **maximal ideal^[극대 아이디얼]**이다 $\Leftrightarrow$

$$M \subsetneq I \triangleleft R \quad \Rightarrow \quad I = R$$

**의미**: $M$보다 큰 proper ideal이 존재하지 않음

**표기**: $M \in \text{MaxSpec}(R)$

**직관**: "가장 큰" proper ideal

## Equivalent Characterizations

다음은 모두 동치:

**1. Definition**: $M \subsetneq I \triangleleft R \Rightarrow I = R$

**2. Quotient ring**: $R/M$이 **field^[체]**

**3. Maximality**: $M$이 proper ideals의 부분순서에서 maximal element

**증명**:

**(1 $\Leftrightarrow$ 2)**:

($\Rightarrow$) $M$ maximal이면, $r \notin M$에 대해
- Ideal $\langle M, r \rangle = M + \langle r \rangle \supsetneq M$
- Maximality: $\langle M, r \rangle = R$
- $\Rightarrow$ $1 = m + sr$ for some $m \in M$, $s \in R$
- In $R/M$: $\overline{1} = \overline{s} \cdot \overline{r}$
- 따라서 $\overline{r}$는 unit in $R/M$
- 모든 nonzero element가 unit $\Rightarrow$ $R/M$ is field ✓

($\Leftarrow$) $R/M$ field이고 $M \subseteq I \triangleleft R$이면
- $I/M \triangleleft R/M$ (correspondence theorem)
- Field는 $\{0\}$과 자기자신만을 ideal로 가짐
- $\Rightarrow$ $I/M = \{0\}$ or $I/M = R/M$
- $\Rightarrow$ $I = M$ or $I = R$ ✓

## Maximal Spectrum

Ring $R$의 **maximal spectrum^[극대 스펙트럼]**:

$$\text{MaxSpec}(R) = \{\text{all maximal ideals of } R\}$$

**관계**: $\text{MaxSpec}(R) \subseteq \text{Spec}(R)$ (모든 maximal ideal은 prime)

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Proper Ideal

**정리**: Maximal ideal은 항상 proper ideal

**증명**: 정의에서 $M \neq R$ ✓

### 2. Maximal $\Rightarrow$ Prime

**정리**: Every maximal ideal is prime

**증명**: 
- $M$ maximal $\Rightarrow$ $R/M$ is field
- Field는 integral domain
- $\Rightarrow$ $M$ is prime ✓

**역 거짓**: Prime ideal이 maximal은 아님!

예: $\langle 0 \rangle \triangleleft \mathbb{Z}$ is prime but not maximal

자세한 내용은 [[Prime Ideal]] 참조

### 3. Existence (Krull's Theorem)

**정리**: Nontrivial commutative ring $R$은 적어도 하나의 maximal ideal을 가짐

**증명**: Zorn's Lemma
- Proper ideals의 collection은 비어있지 않음 ($\{0\} \neq R$)
- Chain에 대해 상한 존재 (합집합)
- $\Rightarrow$ Maximal element 존재 ✓

**중요**: Axiom of Choice 필요!

### 4. Units and Maximal Ideals

**정리**: $r \in R$가 unit $\Leftrightarrow$ $r$이 어떤 maximal ideal에도 속하지 않음

**증명**:

($\Rightarrow$) $r$ unit이면 $rs = 1$
- $r \in M$ (maximal)이면 $1 = rs \in M$ (ideal)
- $\Rightarrow$ $M = R$ ✗ (contradiction)

($\Leftarrow$) $r$이 어떤 maximal ideal에도 속하지 않으면
- Ideal $\langle r \rangle$는 어떤 maximal ideal에도 포함되지 않음
- $\Rightarrow$ $\langle r \rangle = R$ (not proper)
- $\Rightarrow$ $1 \in \langle r \rangle$
- $\Rightarrow$ $1 = sr$ for some $s$
- $\Rightarrow$ $r$ is unit ✓

**계**: $U(R) = R \setminus \bigcup_{M \text{ maximal}} M$

### 5. Jacobson Radical

**정의**: Ring $R$의 **Jacobson radical^[제이콥슨 근기]**

$$J(R) = \bigcap_{M \text{ maximal}} M$$

**의미**: 모든 maximal ideals의 교집합

**성질**: $J(R)$의 원소들은 "거의 0"처럼 작동

자세한 내용은 [[Jacobson Radical]] 참조

## Maximal Ideals in Special Rings

### In Fields

**정리**: Field $F$의 ideals는 $\{0\}$과 $F$뿐

**따라서**: Field는 maximal ideal이 없음 (proper ideal이 없으므로)

### In PIDs

**정리**: PID $R$에서 nonzero prime ideal은 maximal

**증명**: $P = \langle p \rangle$ prime이고 $P \subseteq I = \langle a \rangle$이면
- $p = ab$ for some $b$
- $p$ prime $\Rightarrow$ $p | a$ or $p | b$
- If $p | a$: $I = R$
- If $p | b$: $I = P$
- 따라서 $P$ maximal ✓

**예**: $\mathbb{Z}$에서 $\langle p \rangle$ (prime $p$)

자세한 내용은 [[Principal Ideal Domain]] 참조

### In Polynomial Rings

**$k[x]$ (field $k$)**:

**Maximal ideals**: $\langle f(x) \rangle$ where $f$ is irreducible

**이유**: $k[x]$ is PID

**$k[x_1, \ldots, x_n]$** (multiple variables):

**Maximal ideals**: $\langle x_1 - a_1, \ldots, x_n - a_n \rangle$ (points!)

**이유**: Quotient $\cong k$ (field) ✓

**Nullstellensatz**: Over algebraically closed field, these are ALL maximal ideals

자세한 내용은 [[Polynomial Ring]], [[Nullstellensatz]] 참조

### In $\mathbb{Z}$

**Maximal ideals**: $\langle p \rangle$ where $p$ is prime

**Quotient**: $\mathbb{Z}/p\mathbb{Z}$ is field ✓

**NOT maximal**: $\langle 0 \rangle$ (prime but not maximal)

### In $\mathbb{Z}/n\mathbb{Z}$

**Maximal ideals**: $\langle p \rangle$ where $p | n$ and $p$ is prime

**예 ($n = 12$)**:
- $\langle 2 \rangle = \{0, 2, 4, 6, 8, 10\}$ ✓
- $\langle 3 \rangle = \{0, 3, 6, 9\}$ ✓

**Check**: 
- $\mathbb{Z}/12\mathbb{Z} / \langle 2 \rangle \cong \mathbb{Z}/2\mathbb{Z}$ (field) ✓
- $\mathbb{Z}/12\mathbb{Z} / \langle 3 \rangle \cong \mathbb{Z}/3\mathbb{Z}$ (field) ✓

### In Localization

**정리**: $S^{-1}R$의 maximal ideals $\leftrightarrow$ maximal ideals of $R$ disjoint from $S$

**Local ring at prime**: $R_P$의 unique maximal ideal은 $PR_P$

자세한 내용은 [[Localization]], [[Local Ring]] 참조

## Correspondence with Points

**Algebraic Geometry**:

**Maximal ideal** $\leftrightarrow$ **Point**

**$k[x_1, \ldots, x_n]$ over algebraically closed $k$**:

$$M_{(a_1, \ldots, a_n)} = \langle x_1 - a_1, \ldots, x_n - a_n \rangle$$

**Evaluation**: $f \mapsto f(a_1, \ldots, a_n)$

**Nullstellensatz**: 
- Every maximal ideal has this form
- Bijection between $\text{MaxSpec}(k[x_1, \ldots, x_n])$ and $k^n$

자세한 내용은 [[Algebraic Geometry]], [[Nullstellensatz]] 참조

## Operations

### Sum with Ideal

**정리**: $M$ maximal이고 $I$ ideal이면

$$M + I = M \quad \text{or} \quad M + I = R$$

**증명**: Maximality ✓

### Product

**정리**: $M$ maximal이고 $M \supseteq IJ$이면 $M \supseteq I$ or $M \supseteq J$

**증명**: $M$ is prime (maximal $\Rightarrow$ prime) ✓

### Coprime Ideals

**정의**: Ideals $I, J$가 **coprime^[서로소]**이다 $\Leftrightarrow$ $I + J = R$

**정리**: $I, J$ coprime to $M$ (maximal) $\Rightarrow$ $IJ$ coprime to $M$

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$

**Maximal ideals**: $\langle p \rangle$ where $p$ is prime

- $\langle 2 \rangle$: $\mathbb{Z}/2\mathbb{Z} \cong \mathbb{F}_2$ ✓
- $\langle 3 \rangle$: $\mathbb{Z}/3\mathbb{Z} \cong \mathbb{F}_3$ ✓
- $\langle 5 \rangle$, $\langle 7 \rangle$, $\langle 11 \rangle$, ...

**NOT maximal**: 
- $\langle 0 \rangle$ (prime but not maximal)
- $\langle 4 \rangle$ (not even prime)

**모든 nonzero prime ideals = maximal ideals** (PID!)

## Example 2: $\mathbb{Q}$, $\mathbb{R}$, $\mathbb{C}$

**Fields have NO maximal ideals**

**이유**: Only ideals are $\{0\}$ and $F$
- $\{0\}$ is not proper ($0 \neq F$ assumed)
- Wait, $\{0\}$ IS proper, but not maximal? No...

Actually: Field $F$의 proper ideals는 $\{0\}$뿐

Maximality check: $\{0\} \subseteq I \triangleleft F$
- If $I \neq \{0\}$: $\exists a \neq 0$ in $I$
- $a$ has inverse $a^{-1}$
- $1 = a \cdot a^{-1} \in I$
- $\Rightarrow$ $I = F$ ✓

따라서 **no maximal ideals** (no proper ideals except $\{0\}$, and $\{0\}$ is not maximal since... wait)

Actually $\{0\}$ IS maximal! (only proper ideal)

**Correct**: Fields have exactly one maximal ideal: $\{0\}$

## Example 3: $\mathbb{R}[x]$

**Maximal ideals**: $\langle f(x) \rangle$ where $f$ is irreducible

**Irreducibles**:
- Linear: $\langle x - a \rangle$ for $a \in \mathbb{R}$
- Quadratic: $\langle x^2 + bx + c \rangle$ where $b^2 - 4c < 0$

**Examples**:
- $\langle x \rangle$: $\mathbb{R}[x]/\langle x \rangle \cong \mathbb{R}$ ✓
- $\langle x - 2 \rangle$: Evaluation at $2$, quotient $\cong \mathbb{R}$ ✓
- $\langle x^2 + 1 \rangle$: $\mathbb{R}[x]/\langle x^2 + 1 \rangle \cong \mathbb{C}$ ✓

**NOT maximal**:
- $\langle 0 \rangle$ (prime but not maximal)
- $\langle x^2 - 1 \rangle = \langle (x-1)(x+1) \rangle$ (reducible, not even prime)

## Example 4: $\mathbb{C}[x]$

**Maximal ideals**: $\langle x - a \rangle$ for $a \in \mathbb{C}$

**이유**: 
- $\mathbb{C}$ is algebraically closed
- Every irreducible polynomial is linear
- $\mathbb{C}[x]/\langle x - a \rangle \cong \mathbb{C}$ (evaluation at $a$)

**Bijection**: $\text{MaxSpec}(\mathbb{C}[x]) \leftrightarrow \mathbb{C}$

## Example 5: $\mathbb{C}[x, y]$

**Maximal ideals**: $\langle x - a, y - b \rangle$ for $(a, b) \in \mathbb{C}^2$

**Quotient**: 

$$\mathbb{C}[x, y] / \langle x - a, y - b \rangle \cong \mathbb{C}$$

(evaluation at $(a, b)$)

**Bijection**: $\text{MaxSpec}(\mathbb{C}[x, y]) \leftrightarrow \mathbb{C}^2$

**Geometric interpretation**: Maximal ideals = Points!

**NOT maximal**:
- $\langle x \rangle$ (codimension 1, prime but not maximal)
- $\langle x^2 + y^2 - 1 \rangle$ (circle, not maximal)

## Example 6: $\mathbb{Z}[x]$

**Maximal ideals**: $\langle p, f(x) \rangle$ where:
- $p$ is prime
- $f(x)$ is irreducible mod $p$

**Examples**:
- $\langle 2, x \rangle$: $\mathbb{Z}[x]/\langle 2, x \rangle \cong \mathbb{Z}/2\mathbb{Z}$ ✓
- $\langle 3, x^2 + 1 \rangle$: Quotient $\cong \mathbb{F}_3[x]/\langle x^2 + 1 \rangle \cong \mathbb{F}_9$ ✓
- $\langle 5, x - 2 \rangle$: Evaluation at $2$ mod $5$, quotient $\cong \mathbb{F}_5$ ✓

**NOT maximal**:
- $\langle x \rangle$: $\mathbb{Z}[x]/\langle x \rangle \cong \mathbb{Z}$ (not field)
- $\langle 2 \rangle$: $\mathbb{Z}[x]/\langle 2 \rangle \cong \mathbb{F}_2[x]$ (not field)

## Example 7: $\mathbb{Z}_{(2)}$ (Localization)

$$\mathbb{Z}_{(2)} = \left\{ \frac{a}{b} : 2 \nmid b \right\}$$

**Unique maximal ideal**: $M = 2\mathbb{Z}_{(2)} = \left\{ \frac{2k}{b} : 2 \nmid b \right\}$

**Local ring**: Exactly one maximal ideal!

**Non-units**: Precisely $M$

자세한 내용은 [[Local Ring]] 참조

## Example 8: $k[[x]]$ (Formal Power Series)

$$k[[x]] = \left\{ \sum_{i=0}^{\infty} a_i x^i : a_i \in k \right\}$$

**Unique maximal ideal**: $\langle x \rangle$ (constant term 0)

**Units**: $f$ with $a_0 \neq 0$

**Non-units**: $f$ with $a_0 = 0$ (precisely $\langle x \rangle$)

**Local ring**: ✓

## Example 9: $C([0,1])$ (Continuous Functions)

**Maximal ideals**: $M_x = \{f : f(x) = 0\}$ for each $x \in [0,1]$

**Quotient**: $C([0,1]) / M_x \cong \mathbb{R}$ (evaluation at $x$)

**Bijection**: $\text{MaxSpec}(C([0,1])) \leftrightarrow [0,1]$

**Gelfand-Naimark Theorem**: Correspondence between compact Hausdorff spaces and commutative $C^*$-algebras

## Example 10: $\mathbb{Z}/12\mathbb{Z}$

**Maximal ideals**:
- $\langle 2 \rangle = \{0, 2, 4, 6, 8, 10\}$
- $\langle 3 \rangle = \{0, 3, 6, 9\}$

**Quotients**:
- $\mathbb{Z}/12\mathbb{Z} / \langle 2 \rangle \cong \mathbb{Z}/2\mathbb{Z}$ ✓
- $\mathbb{Z}/12\mathbb{Z} / \langle 3 \rangle \cong \mathbb{Z}/3\mathbb{Z}$ ✓

**Jacobson radical**: $J(\mathbb{Z}/12\mathbb{Z}) = \langle 2 \rangle \cap \langle 3 \rangle = \langle 6 \rangle$

---

# <span class="header-theorem">Theorem</span>

## Krull's Theorem

**정리**: Nontrivial commutative ring $R$ (with unity)은 적어도 하나의 maximal ideal을 가짐

**증명**: Zorn's Lemma on proper ideals ✓

## Maximal $\Rightarrow$ Prime

**정리**: Every maximal ideal is prime

**증명**: $R/M$ is field $\Rightarrow$ $R/M$ is integral domain ✓

## Chinese Remainder Theorem

**정리**: $M_1, \ldots, M_n$ pairwise coprime maximal ideals이면

$$R / (M_1 \cap \cdots \cap M_n) \cong R/M_1 \times \cdots \times R/M_n$$

**Corollary**: 

$$R / (M_1 \cdots M_n) \cong R/M_1 \times \cdots \times R/M_n$$

(since coprime: $M_i M_j = M_i \cap M_j$)

자세한 내용은 [[Chinese Remainder Theorem]] 참조

## Hilbert's Nullstellensatz

**정리 (Weak form)**: $k$ algebraically closed field이고 $I \triangleleft k[x_1, \ldots, x_n]$ proper ideal이면

$$V(I) \neq \emptyset$$

**정리 (Strong form)**: 

$$I(V(I)) = \sqrt{I}$$

**계**: Maximal ideals in $k[x_1, \ldots, x_n]$ (algebraically closed $k$):

$$\text{MaxSpec}(k[x_1, \ldots, x_n]) = \{\langle x_1 - a_1, \ldots, x_n - a_n \rangle : (a_1, \ldots, a_n) \in k^n\}$$

자세한 내용은 [[Nullstellensatz]] 참조

## Nakayama's Lemma

**정리**: $(R, \mathfrak{m})$ local ring with maximal ideal $\mathfrak{m}$, $M$ finitely generated $R$-module이면

$$\mathfrak{m} M = M \quad \Rightarrow \quad M = 0$$

**응용**: Module theory, local algebra

자세한 내용은 [[Nakayama's Lemma]] 참조

## Correspondence Theorem

**정리**: $M \triangleleft R$ ideal이면

$$\{\text{ideals } I \text{ with } M \subseteq I \subseteq R\} \leftrightarrow \{\text{ideals of } R/M\}$$

**성질 보존**: Maximality preserved!

$I$ maximal in $R$ and $I \supseteq M$ $\Leftrightarrow$ $I/M$ maximal in $R/M$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Maximal Ideal = "가장 큰" Proper Ideal**

### 메타포: 최고 수준

**Ring $R$**: 전체 시스템

**Maximal ideal $M$**: "거의" 전체 ($R$에 최대한 가까움)

**Quotient $R/M$**: "가장 단순한" 구조 (field!)

**의미**:
- $M$보다 크면 $R$
- $M$에서 조금만 벗어나면 전체
- "경계선"에 위치

### Quotient = Field

**$R/M$ is field**

**의미**:
- Maximal ideal로 나누면 "완벽한" 구조
- 모든 nonzero element가 역원
- 더 이상 단순화 불가

### Points in Geometry

**Algebraic Geometry**:

**Maximal ideal** $\leftrightarrow$ **Point**

**예**: $\mathbb{C}[x, y]$
- $M = \langle x - a, y - b \rangle$
- Corresponds to point $(a, b)$
- Functions vanishing at that point

## Maximal vs Prime

| | Maximal Ideal | Prime Ideal |
|---|---------------|-------------|
| **정의** | 더 큰 proper ideal 없음 | $ab \in P \Rightarrow a \in P$ or $b \in P$ |
| **Quotient** | Field | Integral domain |
| **관계** | Maximal $\Rightarrow$ Prime | Prime $\not\Rightarrow$ Maximal |
| **기하** | Point | Irreducible subvariety |
| **예 ($\mathbb{Z}$)** | $\langle p \rangle$ (prime $p$) | $\langle 0 \rangle$, $\langle p \rangle$ |
| **예 ($k[x,y]$)** | $\langle x-a, y-b \rangle$ | $\langle 0 \rangle$, $\langle f \rangle$ |

**핵심**:
- Maximal: "Strongest" proper ideal
- Prime: "Prime-like" property
- Maximal $\subset$ Prime (strict inclusion)

자세한 내용은 [[Prime Ideal]] 참조

## 응용 분야

### 1. Algebraic Geometry

**Maximal ideals = Points**

**Correspondence**:
- $\text{MaxSpec}(k[x_1, \ldots, x_n]) \leftrightarrow k^n$ (alg. closed)
- Evaluation homomorphisms
- Structure sheaf

### 2. Functional Analysis

**Gelfand Theory**: $C^*$-algebras

**Maximal ideals** in $C(X)$ $\leftrightarrow$ **Points** in $X$

**Gelfand-Naimark Theorem**: Duality

### 3. Number Theory

**Maximal ideals in $\mathcal{O}_K$**:
- Lie over prime ideals in $\mathbb{Z}$
- Decomposition of primes
- Local-global principles

### 4. Local Algebra

**Localization at maximal ideal**:
- Local ring $(R_M, MR_M)$
- Study "near" a point
- Local properties

### 5. Module Theory

**Simple modules**: $R/M$ as $R$-module

**Composition series**: Built from simples

## 계산 방법

### Maximal Test

**방법 1**: Check quotient is field
- Compute $R/M$
- Verify all nonzero elements have inverses

**방법 2**: Check maximality directly
- For all ideals $I \supsetneq M$: $I = R$

**방법 3**: Use known characterizations
- In $\mathbb{Z}$: $\langle p \rangle$ (prime $p$)
- In $k[x]$: $\langle f \rangle$ (irreducible $f$)
- In $k[x_1, \ldots, x_n]$: $\langle x_i - a_i \rangle$ (alg. closed)

### Finding All Maximals

**$\mathbb{Z}$**: $\{\langle p \rangle : p \text{ prime}\}$

**$k[x]$**: $\{\langle f \rangle : f \text{ irreducible}\}$

**$\mathbb{C}[x_1, \ldots, x_n]$**: $\{\langle x_i - a_i \rangle : (a_i) \in \mathbb{C}^n\}$

**General**: Use Krull's Theorem (existence) + Zorn's Lemma

## Common Pitfall^[흔한 실수]

### 1. Maximal $\neq$ "Largest"

"Maximal"은 "더 큰 proper ideal 없음"

NOT "가장 큰 ideal" (그건 $R$)

### 2. Zero Ideal

$\langle 0 \rangle$이 maximal? 

**답**: Field에서만! (다른 proper ideal 없을 때)

일반적으로: $\langle 0 \rangle$ is NOT maximal

### 3. Prime $\not\Rightarrow$ Maximal

$\langle 0 \rangle \triangleleft \mathbb{Z}$ is prime but NOT maximal

$\langle x \rangle \triangleleft \mathbb{Z}[x]$ is prime but NOT maximal

**예외**: PID에서 nonzero prime = maximal

### 4. Field에서

Field $F$의 maximal ideal?

**답**: $\{0\}$ (유일한 proper ideal)

Field는 "trivially" maximal ideal 하나만

### 5. Direct Product

$R_1 \times R_2$의 maximal ideals?

**NOT** $M_1 \times M_2$ (generally)!

**Correct**: $M \times R_2$ or $R_1 \times N$ where $M, N$ maximal

### 6. Localization

$S^{-1}R$의 maximal ideals ≠ $S^{-1}M$ (generally)

Correct correspondence 필요!

## 역사적 배경

**19세기**:
- **Dedekind**: Ideal theory
- 목표: Unique factorization 복원

**20세기 초**:
- **Hilbert**: Nullstellensatz
- **Krull**: Existence theorem (Zorn's Lemma)
- **Noether**: Abstract ideal theory

**현대**:
- **Grothendieck**: Scheme theory (points = primes, not just maximals!)
- **Gelfand**: Functional analysis connection
- **Atiyah-Macdonald**: Standard modern treatment

## 관련 개념

- [[Ideal]]: General concept
- [[Prime Ideal]]: Weaker condition
- [[Principal Ideal]]: Generated by one element
- [[Field]]: Quotient by maximal
- [[Quotient Ring]]: $R/M$ construction
- [[Local Ring]]: Unique maximal ideal
- [[Spectrum]]: All primes (not just maximals)
- [[Jacobson Radical]]: Intersection of all maximals
- [[Algebraic Geometry]]: Maximal = points

## 추가 학습 주제

**기초**:
- Definition and characterization
- Quotient is field
- Examples in $\mathbb{Z}$, $k[x]$
- Maximal vs prime

**중급**:
- Krull's Theorem
- Nullstellensatz
- Correspondence with points
- Chinese Remainder Theorem

**고급**:
- Jacobson radical
- Local rings
- Maximal spectrum topology
- Gelfand theory
- Local-global principles
- Henselian rings

