# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Generator]]
- [[Finitely Generated Groups]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups
- Magnus, Karrass, Solitar, Combinatorial Group Theory

---

# <span class="header-definition">Definition</span>

## Free Group^[자유군]

Set $S$에 대한 **free group**^[자유군] $F(S)$:

Group with **no relations** except those required by group axioms

### Formal Definition

**Universal property**^[보편 성질]:

For any group $G$ and function $f: S \to G$,

$$\exists ! \text{ homomorphism } \phi: F(S) \to G \text{ extending } f$$

```
S ⊂ F(S)
 ↓ f  ↘ φ
   G
```

**의미**: $S$를 어디로든 보내는 함수는 유일하게 homomorphism으로 확장

## Elements of Free Group

**Words**^[단어]: Elements of $F(S)$

$$w = s_1^{\epsilon_1} s_2^{\epsilon_2} \cdots s_n^{\epsilon_n}$$

where $s_i \in S$, $\epsilon_i = \pm 1$

**Reduced word**^[기약 단어]: $s_i^{\epsilon_i}(s_i)^{-\epsilon_i}$ 형태 없음

**예**:
- $aba^{-1}b^{-1}$ reduced ✓
- $aba^{-1}a$ not reduced (= $ab$) ✗

## Free Group on $n$ Generators

$$F_n = F(\{a_1, \ldots, a_n\})$$

**표기**: Often write $F_n = \langle a_1, \ldots, a_n \mid \emptyset \rangle$

**의미**: No relations!

### Special Cases

**$F_0$**: Trivial group $\{e\}$

**$F_1$**: Infinite cyclic $\cong \mathbb{Z}$

**$F_2$**: Most "generic" free group

## Rank of Free Group

**Rank**: Number of free generators

$$\text{rank}(F_n) = n$$

**Nielsen-Schreier**: Every subgroup of free group is free!

But rank can be different

---

# <span class="header-properties">Properties</span>

## Group Operation

**Multiplication**: Concatenation + reduction

$$(abc)(b^{-1}cd) = abcd$$

$$(ab)(b^{-1}c) = ac$$

**Identity**: Empty word $e$

**Inverse**: Reverse + flip exponents

$$(abc)^{-1} = c^{-1}b^{-1}a^{-1}$$

## Universal Property

**Key theorem**: Free groups are "most general"

For any $f: S \to G$ (set map), $\exists ! \phi: F(S) \to G$ (homomorphism)

**응용**: Every group is quotient of free group

$$G \cong F(S) / N$$

for some $S$ and normal subgroup $N$

자세한 내용은 [[Group Presentation]] 참조

## Word Problem

**Word problem**: Is $w = e$ in $F(S)$?

**Answer for Free Groups**: EASY! ✓

$w = e \Leftrightarrow w$ reduces to empty word

**대조**: For general groups, word problem can be undecidable!

## Freeness and Relations

**Free**: No relations except group axioms

$$ab \neq ba \text{ in } F_2$$

$$a^n \neq e \text{ for any } n \neq 0$$

**Contrast with $\mathbb{Z}/n\mathbb{Z}$**: $a^n = e$ (relation!)

## Normal Forms

**Theorem**: Every element has unique reduced word

$$w = s_1^{\epsilon_1} \cdots s_n^{\epsilon_n}$$

**Properties**:
- No $s_i^{\epsilon_i}(s_i)^{-\epsilon_i}$ cancellations
- Unique representation
- $w = e \Leftrightarrow w$ is empty

## Subgroups

**Nielsen-Schreier Theorem**: Every subgroup of $F_n$ is free!

**Rank formula**: If $H \leq F_n$ with $[F_n : H] = m$ finite,

$$\text{rank}(H) = 1 + m(n - 1)$$

**예**: $H \leq F_2$ with index 2 has rank 3

## Abelianization

$$F_n / [F_n, F_n] \cong \mathbb{Z}^n$$

**Commutator subgroup**^[교환자 부분군]: $[F_n, F_n]$ = derived subgroup

**의미**: "Making free group abelian" = free abelian group

자세한 내용은 [[Commutator Subgroup]] 참조

## Center

$$Z(F_n) = \{e\} \quad (n \geq 2)$$

**Center is trivial** for $n \geq 2$

**예외**: $F_1 \cong \mathbb{Z}$ is abelian, so $Z(F_1) = F_1$

자세한 내용은 [[Center]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: $F_1$

$$F_1 = \langle a \rangle \cong \mathbb{Z}$$

**Elements**: $\{\ldots, a^{-2}, a^{-1}, e, a, a^2, \ldots\}$

**Cyclic**: Only free group that's abelian

자세한 내용은 [[Cyclic Group]] 참조

## Example 2: $F_2$

$$F_2 = \langle a, b \rangle$$

**Elements**: $\{e, a, b, ab, ba, aba, \ldots\}$

**Non-abelian**: $ab \neq ba$

**Universal**: $F_2$ contains all countable groups as quotients!

## Example 3: Words in $F_2$

**Example words**:
- $aba^{-1}b^{-1}$ (commutator $[a,b]$) reduced ✓
- $abab$ reduced ✓
- $aba^{-1}a$ not reduced = $ab$ ✗
- $aa^{-1}$ not reduced = $e$ ✗

## Example 4: Homomorphisms

$F_2 = \langle a, b \rangle$, $G = S_3$

Define $f: \{a, b\} \to S_3$:
- $a \mapsto (12)$
- $b \mapsto (123)$

Then $\exists ! \phi: F_2 \to S_3$ with:
- $\phi(a) = (12)$
- $\phi(b) = (123)$
- $\phi(ab) = (12)(123) = (13)$
- etc.

자세한 내용은 [[Symmetric Group]] 참조

## Example 5: Fundamental Group

**Topology**: Fundamental group $\pi_1$ of wedge of circles

$$\pi_1(S^1 \vee S^1) \cong F_2$$

**의미**: Loops on figure-eight = words in $F_2$

## Example 6: Subgroup of $F_2$

$$H = \langle a^2, b^2, ab \rangle \leq F_2$$

**Is $H$ free?** Yes! (Nielsen-Schreier) ✓

**Rank?** Compute using index formula

---

# <span class="header-theorem">Theorem</span>

## Nielsen-Schreier Theorem

**정리**: Every subgroup of free group is free

$$H \leq F_n \Rightarrow H \text{ is free}$$

**Rank formula**: If $[F_n : H] = m < \infty$,

$$\text{rank}(H) = 1 + m(n-1)$$

**증명 idea**: Covering space theory or combinatorial

## Universal Property (Formal)

**정리**: $F(S)$ satisfies universal property

For any group $G$ and $f: S \to G$,

$$\exists ! \phi: F(S) \to G \text{ with } \phi|_S = f$$

**Diagram**:

```
S ⊂ F(S)
↓ f  ↘ φ (unique)
  G
```

## Uniqueness

**정리**: Free group on $S$ is unique up to isomorphism

Any two groups satisfying universal property are isomorphic

## Every Group is Quotient

**정리**: Every group $G$ is quotient of free group

$$G \cong F(S) / N$$

where $S$ = generating set, $N$ = normal subgroup

**Proof**: Take $S$ generating $G$, define $\phi: F(S) \to G$

$N = \ker(\phi)$ $\Rightarrow$ $G \cong F(S)/N$ by First Isomorphism Theorem

자세한 내용은 [[Isomorphism Theorem]] 참조

## Schreier's Formula

**정리**: For subgroup $H$ of $F_n$ with finite index $m$,

$$\text{rank}(H) - 1 = m(n-1)$$

**응용**: Compute rank of subgroups

## Free Groups are Torsion-Free

**정리**: $F_n$ has no elements of finite order (except $e$)

$$g^k = e, \; g \neq e \Rightarrow k = 0$$

**증명**: Reduced word $w$ → $w^k$ has length $k|w|$ if $k \neq 0$ ✓

## Hopfian Property

**정리**: $F_n$ is Hopfian

Every surjective endomorphism is injective

**의미**: Cannot collapse onto proper quotient

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Free = "완전히 자유로운"**

### 메타포: 알파벳과 단어

**Generators**: 알파벳 {a, b, c, ...}

**Group elements**: 단어들 (abc, ba, a⁻¹b, ...)

**No relations**: 아무 단어나 다른 단어와 같지 않음

**예**: "cat" ≠ "dog" ≠ "tac"

### 메타포: 경로

**Figure-eight**: 두 개의 원이 한 점에서 만남

**Generators**: 각 원을 도는 loop

**Free group**: 원들을 임의로 도는 모든 경로

**No relations**: $ab \neq ba$ (순서 중요)

## 왜 중요한가?

### 1. Universal Property

**Every group is quotient** of free group!

$$G = F(S) / N$$

**응용**: Study groups via presentations

### 2. Building Block

**Free groups**: "Most basic" non-abelian groups

**No constraints**: Only group axioms

### 3. Topology

**Fundamental groups**: $\pi_1$ of graphs = free groups

**Covering spaces**: Free groups act on trees

### 4. Combinatorics

**Word problems**: Algorithmically solvable

**Growth**: Exponential

### 5. Representation Theory

**Ping-pong lemma**: Construct free subgroups

**응용**: Show groups are "large"

## Free vs Cyclic

| | **Cyclic** | **Free (n≥2)** |
|---|---|---|
| **Generators** | 1 | $n \geq 2$ |
| **Abelian** | Yes | No |
| **Relations** | $a^k = e$ (finite) or none (infinite) | None |
| **Size** | Finite or countable | Countably infinite |
| **예** | $\mathbb{Z}, \mathbb{Z}/n\mathbb{Z}$ | $F_2, F_3, \ldots$ |

**공통점**: Both are "basic building blocks"

자세한 내용은 [[Cyclic Group]] 참조

## Free vs Free Abelian

| | **Free** | **Free Abelian** |
|---|---|---|
| **Relation** | None | $xy = yx$ |
| **Abelian** | No (n≥2) | Yes |
| **Structure** | $F_n$ | $\mathbb{Z}^n$ |
| **Center** | $\{e\}$ (n≥2) | Whole group |

**Abelianization**: $F_n / [F_n, F_n] \cong \mathbb{Z}^n$

## 계산 방법

### Reduced Form

**Step 1**: Write word $w = s_1^{\epsilon_1} \cdots s_n^{\epsilon_n}$

**Step 2**: Cancel adjacent inverses $s_i^{\epsilon_i}(s_i)^{-\epsilon_i}$

**Step 3**: Repeat until no cancellations possible

**Result**: Unique reduced form

### Equality Check

$w_1 = w_2$ in $F(S)$ $\Leftrightarrow$ same reduced form

**Algorithm**: Reduce both, compare

### Homomorphism

**Given**: $f: \{a_1, \ldots, a_n\} \to G$

**Extend**: $\phi(w) = \phi(a_1)^{\epsilon_1} \cdots \phi(a_n)^{\epsilon_n}$

for $w = a_1^{\epsilon_1} \cdots a_n^{\epsilon_n}$

## 표기법

| 표기 | 의미 |
|------|------|
| $F(S)$ | Free group on set $S$ |
| $F_n$ | Free group on $n$ generators |
| $\langle a_1, \ldots, a_n \mid \emptyset \rangle$ | No relations |
| $[a,b]$ | Commutator $aba^{-1}b^{-1}$ |
| $\text{rank}(F)$ | Number of generators |

## Common Pitfall^[흔한 실수]

### 1. $F_n$ is NOT abelian (n≥2)

$ab \neq ba$ in $F_2$!

**예외**: $F_1 \cong \mathbb{Z}$ abelian

### 2. $F_n$ is infinite (n≥1)

Even one generator gives infinite group!

### 3. No torsion

$a^k \neq e$ unless $k = 0$ in free groups

### 4. Subgroups have different rank

$H \leq F_2$ can have rank 3, 5, ...

Nielsen-Schreier formula!

### 5. Uniqueness of reduced form

Each element has ONE reduced form

Not multiple forms!

## 관련 개념

- [[Group Presentation]]: $\langle S \mid R \rangle$ with relations
- [[Generator]]: Basic concept
- [[Finitely Generated Groups]]: Broader class
- [[Cayley's Theorem]]: Embedding into $S_n$
- [[Isomorphism Theorem]]: Quotients

## 추가 학습 주제

**기초**:
- Definition
- Reduced words
- Universal property

**중급**:
- Nielsen-Schreier
- Subgroups
- Abelianization

**고급**:
- Geometric group theory
- Ping-pong lemma
- Free products
- Bass-Serre theory
- Automorphisms of $F_n$

