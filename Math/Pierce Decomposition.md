# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Boolean Ring]]
- [[Direct Product]]

# <span class="header-reference">Reference</span>
- Lam, A First Course in Noncommutative Rings
- Pierce, Modules over Commutative Regular Rings
- Goodearl, Von Neumann Regular Rings

---

# <span class="header-definition">Definition</span>

## Idempotent Element^[멱등원]

Ring $R$의 원소 $e \in R$이 **idempotent^[멱등원]**이다 $\Leftrightarrow$

$$e^2 = e$$

**예**:
- $0^2 = 0$  (trivial idempotent)
- $1^2 = 1$  (trivial idempotent)
- In $\mathbb{Z}/6\mathbb{Z}$: $\overline{3}^2 = \overline{3}$  (nontrivial)

자세한 내용은 [[Boolean Ring]] 참조

## Orthogonal Idempotents^[직교 멱등원]

Idempotents $e, f \in R$가 **orthogonal^[직교]**이다 $\Leftrightarrow$

$$ef = fe = 0$$

**의미**: 서로 "겹치지 않는" 멱등원

## Complete Set of Orthogonal Idempotents^[완전 직교 멱등원 집합]

Idempotents $\{e_1, \ldots, e_n\}$가 **complete set of orthogonal idempotents**^[완전 직교 멱등원 집합]이다 $\Leftrightarrow$

1. $e_i^2 = e_i$ for all $i$
2. $e_i e_j = 0$ for $i \neq j$ (orthogonal)
3. $e_1 + \cdots + e_n = 1$ (complete)

**의미**: 환을 완전히 "분할"하는 멱등원들

## Pierce Decomposition^[피어스 분해]

Complete set of orthogonal idempotents $\{e_1, \ldots, e_n\}$에 대한 **Pierce decomposition**^[피어스 분해]:

$$R = e_1 R \oplus e_2 R \oplus \cdots \oplus e_n R$$

**의미**: 환을 직합으로 분해

---

# <span class="header-theorem">Theorem</span>

## Decomposition by Single Idempotent

**정리**: 단위원 $1$을 가지는 환 $R$에서, $a \in R$이 멱등원 ($a^2 = a$)이면,

$$R = aR \times (1-a)R$$

로 유일하게 분해된다.

### 증명

**Step 1**: $(1-a)$도 멱등원

$$(1-a)^2 = 1 - 2a + a^2 = 1 - 2a + a = 1 - a$$ 
**Step 2**: 직교성 (Orthogonality)

$$a(1-a) = a - a^2 = a - a = 0$$

$$(1-a)a = a - a^2 = 0$$ 
**Step 3**: 완전성 (Completeness)

$$a + (1-a) = 1$$ 
**Step 4**: 직합 분해

임의의 $r \in R$에 대해:

$$r = r \cdot 1 = r(a + (1-a)) = ra + r(1-a)$$

where $ra \in aR$ and $r(1-a) \in (1-a)R$

**유일성**: $ra + r(1-a) = 0$이면,

양변에 $a$를 곱하면: $ra \cdot a = ra^2 = ra = 0$ (since $a^2 = a$)

양변에 $(1-a)$를 곱하면: $r(1-a)^2 = r(1-a) = 0$

따라서 $R = aR \oplus (1-a)R$ 
**Step 5**: Ring 구조

- $aR$의 항등원: $a$ (since $a \cdot a = a^2 = a$)
- $(1-a)R$의 항등원: $(1-a)$
- 직교성: $(aR) \cdot ((1-a)R) = 0$

따라서 $R \cong aR \times (1-a)R$ (ring direct product) 
## General Pierce Decomposition

**정리**: Complete set of orthogonal idempotents $\{e_1, \ldots, e_n\}$에 대해:

$$R = e_1 R \times e_2 R \times \cdots \times e_n R$$

**증명**: Induction on $n$ using single idempotent case 
### As Rings

Each $e_i R$ is a ring with identity $e_i$:
- Multiplication: $(e_i r)(e_i s) = e_i rs$ (since $e_i^2 = e_i$)
- Identity: $e_i$

### Isomorphism

$$R \cong \prod_{i=1}^{n} e_i R$$

via $r \mapsto (e_1 r, \ldots, e_n r)$

## Central Idempotents

**정리**: If $e$ is **central idempotent**^[중심 멱등원] ($e \in Z(R)$, $e^2 = e$),

$$R \cong eR \times (1-e)R$$

as rings (not just as additive groups)

**의미**: Central idempotents give "true" ring decomposition

자세한 내용은 [[Center]] 참조

## Boolean Rings

**정리**: Boolean ring $B$에서 모든 원소가 idempotent

$$\forall a \in B: \quad B = aB \times (1-a)B$$

**의미**: Boolean rings는 "완전히 분해 가능"

자세한 내용은 [[Boolean Ring]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}/6\mathbb{Z}$

**Idempotent**: $a = \overline{3}$

Check: $\overline{3}^2 = \overline{9} = \overline{3}$ 
**Complement**: $1 - a = \overline{1} - \overline{3} = \overline{-2} = \overline{4}$

Check: $\overline{4}^2 = \overline{16} = \overline{4}$ 
**Orthogonality**: $\overline{3} \cdot \overline{4} = \overline{12} = \overline{0}$ 
**Decomposition**:

$$\mathbb{Z}/6\mathbb{Z} = \overline{3}\mathbb{Z}/6\mathbb{Z} \times \overline{4}\mathbb{Z}/6\mathbb{Z}$$

$$= \{0, 3\} \times \{0, 4\}$$

$$\cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$$

(Chinese Remainder Theorem!)

## Example 2: Matrix Ring

**Ring**: $R = M_2(\mathbb{R})$

**Idempotent**: 

$$e = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}$$

Check: $e^2 = e$ 
**Complement**:

$$1 - e = \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix}$$

**Decomposition**:

$$eR = \left\{ \begin{pmatrix} a & b \\ 0 & 0 \end{pmatrix} : a, b \in \mathbb{R} \right\}$$

$$(1-e)R = \left\{ \begin{pmatrix} 0 & 0 \\ c & d \end{pmatrix} : c, d \in \mathbb{R} \right\}$$

$$M_2(\mathbb{R}) = eR \times (1-e)R$$

## Example 3: Boolean Ring

**$B = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$**

**Idempotent**: $a = (1, 0)$

$$a^2 = (1,0) \cdot (1,0) = (1,0) = a$$ 
**Decomposition**:

$$B = aB \times (1-a)B$$

$$= \{(0,0), (1,0)\} \times \{(0,0), (0,1)\}$$

$$\cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$$

## Example 4: Product of Rings

**$R = R_1 \times R_2$** (direct product)

**Idempotents**: 
- $e_1 = (1, 0)$
- $e_2 = (0, 1)$

**Properties**:
- $e_1^2 = e_1$, $e_2^2 = e_2$ - $e_1 e_2 = 0$ - $e_1 + e_2 = (1, 1) = 1$ 
**Decomposition**:

$$R = e_1 R \times e_2 R = R_1 \times R_2$$

## Example 5: $\mathbb{Z}/30\mathbb{Z}$

**Chinese Remainder Theorem**: $30 = 2 \times 3 \times 5$

**Idempotents**: 
- $e_1 = \overline{15}$ (corresponds to $\mathbb{Z}/2\mathbb{Z}$)
- $e_2 = \overline{10}$ (corresponds to $\mathbb{Z}/3\mathbb{Z}$)
- $e_3 = \overline{6}$ (corresponds to $\mathbb{Z}/5\mathbb{Z}$)

Check: $e_1 + e_2 + e_3 = \overline{15 + 10 + 6} = \overline{31} = \overline{1}$ 
**Decomposition**:

$$\mathbb{Z}/30\mathbb{Z} \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z} \times \mathbb{Z}/5\mathbb{Z}$$

## Example 6: Continuous Functions

**$R = C([0,1] \cup [2,3])$**: Continuous functions on disjoint union

**Idempotent**: $e(x) = \begin{cases} 1 & x \in [0,1] \\ 0 & x \in [2,3] \end{cases}$

**Decomposition**:

$$R = eR \times (1-e)R \cong C([0,1]) \times C([2,3])$$

---

# <span class="header-properties">Properties</span>

## Idempotents and Projections

**정리**: In ring $R$, idempotent $e$ acts as projection

$$r \mapsto er$$

**Properties**:
- $(er)e = er$ (image in $eR$)
- $e(er) = er$ (idempotent on image)

## Lifting Idempotents

**정리**: If $R/I$ has idempotent $\bar{e}$, when can we lift to idempotent in $R$?

**Answer**: If $I$ is nil ideal, lifting is possible

## Uniqueness of Decomposition

**정리**: Decomposition $R = e_1 R \times \cdots \times e_n R$ is unique up to permutation

**의미**: The "factors" are uniquely determined

## Central Idempotents and Ideals

**정리**: Central idempotent $e$ $\Leftrightarrow$ $eR$ is two-sided ideal

**Proof**: 
- $e$ central $\Rightarrow$ $re = er$ for all $r$
- $\Rightarrow$ $r(eR) = (re)R = (er)R \subseteq eR$ 
## Direct Product Characterization

**정리**: $R \cong R_1 \times R_2$ $\Leftrightarrow$ $\exists$ central idempotent $e$ with

$$R_1 \cong eR, \quad R_2 \cong (1-e)R$$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Pierce Decomposition = "공간 분할"**

### 메타포: 방 나누기

**환 $R$**: 큰 방

**멱등원 $e$**: 칸막이

**$eR$**: 칸막이 한쪽

**$(1-e)R$**: 칸막이 다른쪽

**직교성**: 두 공간 사이 상호작용 없음

**완전성**: 두 공간이 전체를 덮음

### 메타포: 스위치

**멱등원 $e$**: ON/OFF 스위치

**$e^2 = e$**: 스위치를 두 번 켜도 한 번 켠 것과 같음

**$eR$**: 스위치가 ON일 때의 상태

**$(1-e)R$**: 스위치가 OFF일 때의 상태

**직교성**: ON과 OFF는 동시에 불가

### 메타포: 필터

**멱등원**: 특정 부분만 "통과"시키는 필터

**$e \cdot r$**: $r$의 "$e$-부분"

**$(1-e) \cdot r$**: $r$의 "나머지 부분"

## 왜 중요한가?

### 1. Structure Theory

**환의 구조 이해**: 복잡한 환을 단순한 부분들로 분해

**Direct product decomposition**: 환을 완전히 이해

### 2. Module Theory

**Module decomposition**: Modules를 direct summands로 분해

**Projective modules**: Idempotents와 밀접한 관련

### 3. Representation Theory

**Decomposition of representations**: Irreducible components

**Schur's lemma**: Idempotents 역할

### 4. Chinese Remainder Theorem

**$\mathbb{Z}/n\mathbb{Z}$ 분해**: Idempotents로 설명

$$\mathbb{Z}/n\mathbb{Z} \cong \prod_{p^k \| n} \mathbb{Z}/p^k\mathbb{Z}$$

### 5. Algebraic Geometry

**Spectrum decomposition**: Idempotents $\leftrightarrow$ clopen sets

**Sheaf theory**: Local decomposition

## 계산 방법

### Find Idempotents

**Step 1**: Solve $e^2 = e$

**Step 2**: In $\mathbb{Z}/n\mathbb{Z}$: Use Chinese Remainder Theorem

**Step 3**: Check orthogonality and completeness

### Decompose Ring

**Step 1**: Find complete set $\{e_1, \ldots, e_n\}$

**Step 2**: Compute $e_i R$ for each $i$

**Step 3**: Verify $R = e_1 R \times \cdots \times e_n R$

### Verify Decomposition

**Check 1**: $e_i^2 = e_i$ for all $i$

**Check 2**: $e_i e_j = 0$ for $i \neq j$

**Check 3**: $\sum e_i = 1$

## 표기법

| 표기 | 의미 |
|------|------|
| $e^2 = e$ | Idempotent |
| $ef = 0$ | Orthogonal idempotents |
| $eR$ | Principal left ideal generated by $e$ |
| $R = e_1 R \oplus \cdots \oplus e_n R$ | Pierce decomposition |
| $Z(R)$ | Center of ring |

## Common Pitfall^[흔한 실수]

### 1. Not all idempotents are central

$e^2 = e$ doesn't imply $er = re$!

**Central**: Additional condition needed

### 2. $eR \neq Re$ generally

Left ideal $\neq$ right ideal

For two-sided ideal: need $e$ central

### 3. Complement $(1-e)$ also idempotent

Don't forget to verify $(1-e)^2 = 1-e$!

Automatic in any ring 
### 4. Orthogonality is symmetric

$ef = 0$ $\Rightarrow$ $fe = 0$ (in commutative ring)

Not automatic in non-commutative!

### 5. Trivial idempotents

$0$ and $1$ always idempotent

Nontrivial: $e \neq 0, 1$

## 응용 분야

**Algebra**:
- Ring theory
- Module theory
- Representation theory

**Algebraic Geometry**:
- Spectrum decomposition
- Sheaf theory

**Functional Analysis**:
- Projections in $C^*$-algebras
- Spectral theory

**Computer Science**:
- Boolean circuits (Boolean rings)
- Database theory (set operations)

## 관련 개념

- [[Ring]]: Basic structure
- [[Boolean Ring]]: All elements idempotent
- [[Direct Product]]: Decomposition target
- [[Center]]: Central idempotents

## 추가 학습 주제

**기초**:
- Idempotent elements
- Single idempotent decomposition
- Examples

**중급**:
- Pierce decomposition
- Central idempotents
- Chinese Remainder Theorem

**고급**:
- Lifting idempotents
- von Neumann regular rings
- Peirce decomposition in Jordan algebras
- K-theory of rings
- Morita equivalence

