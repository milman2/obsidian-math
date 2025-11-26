# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Lang, Algebra

---

# <span class="header-definition">Definition</span>

## Subring^[부분환]

Ring $R$의 부분집합 $S$가 **subring^[부분환]**이다 $\Leftrightarrow$

1. $S$가 $R$의 덧셈에 대해 **subgroup^[부분군]**
2. $S$가 $R$의 곱셈에 대해 **닫혀있음** (closed)
3. (선택적) $S$가 $R$의 곱셈 항등원 $1_R$을 포함 (unital subring)

**수식 표현**:

$$\forall a, b \in S: \quad a - b \in S, \quad ab \in S$$

**표기**: $S \leq R$ 또는 $S \subseteq R$

### Unital vs Non-unital Subring

**두 가지 관점**:

#### 1. Non-unital subring (관대한 정의)

$S$가 자체적으로 ring이면 충분:
- $S$는 자신의 항등원을 가질 수 있음 ($1_S$)
- $1_S \neq 1_R$ 가능
- 예: $2\mathbb{Z} \leq \mathbb{Z}$ (but $1 \notin 2\mathbb{Z}$)

#### 2. Unital subring (엄격한 정의)

$S$가 $R$의 항등원을 포함해야 함:
- $1_R \in S$ 필수
- $1_S = 1_R$
- 많은 현대 교재가 이 정의 사용

**본 문서**: **Unital subring** 관점 채택

> **중요**: 문맥에 따라 어느 정의를 사용하는지 확인 필요!

## Subring Test

**정리 (Subring Test)**: 비어있지 않은 부분집합 $S \subseteq R$가 subring $\Leftrightarrow$

$$\forall a, b \in S: \quad a - b \in S \text{ and } ab \in S$$

$$1_R \in S \quad \text{(unital subring인 경우)}$$

**증명**:

**($\Rightarrow$)**: Subring이면 당연히 닫혀있음 ✓

**($\Leftarrow$)**:
1. **Additive subgroup**: 
   - $0 = a - a \in S$ (identity)
   - $-a = 0 - a \in S$ (inverse)
   - $a + b = a - (-b) \in S$ (closure)
   
2. **Multiplicative closure**: $ab \in S$ by assumption ✓

3. **Unity**: $1_R \in S$ by assumption (unital) ✓

따라서 $S \leq R$ ✓

### Simplified Test

만약 $S$가 finite이면:

$$\forall a, b \in S: \quad a + b \in S, \quad ab \in S, \quad 1 \in S$$

만 확인하면 충분 (역원 자동)

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Intersection of Subrings

Subrings의 교집합도 subring:

$$S_1, S_2 \leq R \quad \Rightarrow \quad S_1 \cap S_2 \leq R$$

**증명**: $a, b \in S_1 \cap S_2$이면
- $a - b \in S_1$ and $a - b \in S_2$ $\Rightarrow$ $a - b \in S_1 \cap S_2$ ✓
- $ab \in S_1$ and $ab \in S_2$ $\Rightarrow$ $ab \in S_1 \cap S_2$ ✓
- $1 \in S_1$ and $1 \in S_2$ $\Rightarrow$ $1 \in S_1 \cap S_2$ ✓

### 2. Generated Subring

집합 $X \subseteq R$이 주어졌을 때, $X$를 포함하는 **smallest subring**^[최소 부분환]:

$$\langle X \rangle = \bigcap_{X \subseteq S \leq R} S$$

**의미**: $X$로 **generated^[생성]**된 subring

**원소**: 모든 $a_1, \ldots, a_n \in X$와 정수 $k_1, \ldots, k_n$에 대한

$$k_1 a_1 + \cdots + k_n a_n + \sum_{i,j} a_i a_j + \cdots$$

(덧셈, 뺄셈, 곱셈의 유한 조합)

### 3. Characteristic Inheritance

**정리**: $S \leq R$이면 $\text{char}(S) = \text{char}(R)$

**증명**: $1_S = 1_R$이므로 (unital subring)

$$n \cdot 1_S = n \cdot 1_R$$

따라서 characteristic 동일 ✓

자세한 내용은 [[Characteristic]] 참조

### 4. Subring Lattice

Ring $R$의 모든 subrings는 **lattice^[격자]** 구조:

**Join**: $S_1 \vee S_2 = \langle S_1 \cup S_2 \rangle$ (smallest subring containing both)

**Meet**: $S_1 \wedge S_2 = S_1 \cap S_2$ (intersection)

**특징**:
- 부분 순서: 포함 관계
- 최소원: $\mathbb{Z} \cdot 1$ (or $\mathbb{Z}/n\mathbb{Z} \cdot 1$)
- 최대원: $R$ 자체

## Subring vs Ideal

**중요한 차이점**:

| | Subring | Ideal |
|---|---------|-------|
| 덧셈 | Subgroup ✓ | Subgroup ✓ |
| 곱셈 | Closed: $ab \in S$ | Absorption: $ra \in I$ for all $r \in R$ |
| 항등원 | $1 \in S$ (unital) | $1 \notin I$ (proper ideal) |
| 예 | $\mathbb{Z} \leq \mathbb{Q}$ | $2\mathbb{Z} \triangleleft \mathbb{Z}$ |

**관계**:
- Every ideal is a subring (non-unital 정의에서)
- Proper ideal은 unital subring이 아님
- Unital subring은 ideal이 아님 (일반적으로)

자세한 내용은 [[Ideal]] 참조

## Prime Subring

**정의**: Ring $R$의 **prime subring^[소 부분환]** = 모든 subrings의 교집합

$$\text{Prime}(R) = \bigcap_{S \leq R} S$$

**의미**: $R$의 "가장 작은" subring

### Structure of Prime Subring

Ring $R$의 prime subring:

**Case 1**: $\text{char}(R) = 0$

$$\text{Prime}(R) \cong \mathbb{Z}$$

**Case 2**: $\text{char}(R) = n > 0$

$$\text{Prime}(R) \cong \mathbb{Z}/n\mathbb{Z}$$

**증명**: Prime subring은 $1$로 생성됨

$$\text{Prime}(R) = \{n \cdot 1 : n \in \mathbb{Z}\} = \langle 1 \rangle$$

- If $n \cdot 1 \neq 0$ for all $n \neq 0$: isomorphic to $\mathbb{Z}$
- If $n \cdot 1 = 0$ for smallest $n > 0$: isomorphic to $\mathbb{Z}/n\mathbb{Z}$

## Center as Subring

Ring $R$의 **center^[중심]**:

$$Z(R) = \{z \in R : zr = rz \text{ for all } r \in R\}$$

**정리**: $Z(R) \leq R$ (subring)

**증명**:
- $1 \in Z(R)$ ✓
- $z_1, z_2 \in Z(R)$이면 $z_1 - z_2 \in Z(R)$ ✓
- $z_1, z_2 \in Z(R)$이면 $z_1 z_2 \in Z(R)$ ✓

자세한 내용은 [[Center]] 참조

## Subring of Field

**정리**: Field $F$의 unital subring $S$는:

1. Integral domain^[정역]
2. $S$의 quotient field^[분수체] $\subseteq F$

**예**:
- $\mathbb{Z} \leq \mathbb{Q}$ (quotient field = $\mathbb{Q}$)
- $\mathbb{Q} \leq \mathbb{R}$ (quotient field = $\mathbb{Q}$)
- $\mathbb{Z}[i] \leq \mathbb{Q}[i]$ (quotient field = $\mathbb{Q}[i]$)

자세한 내용은 [[Field]], [[Integral Domain]], [[Quotient Field]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z} \leq \mathbb{Q}$

**Check**:
- $a - b \in \mathbb{Z}$ if $a, b \in \mathbb{Z}$ ✓
- $ab \in \mathbb{Z}$ if $a, b \in \mathbb{Z}$ ✓
- $1 \in \mathbb{Z}$ ✓

Therefore $\mathbb{Z} \leq \mathbb{Q}$ ✓

**Chain**: $\mathbb{Z} \leq \mathbb{Q} \leq \mathbb{R} \leq \mathbb{C}$

## Example 2: Gaussian Integers

**$\mathbb{Z}[i] = \{a + bi : a, b \in \mathbb{Z}\}$** in $\mathbb{C}$

**Check**:
- $(a + bi) - (c + di) = (a-c) + (b-d)i \in \mathbb{Z}[i]$ ✓
- $(a + bi)(c + di) = (ac - bd) + (ad + bc)i \in \mathbb{Z}[i]$ ✓
- $1 = 1 + 0i \in \mathbb{Z}[i]$ ✓

Therefore $\mathbb{Z}[i] \leq \mathbb{C}$ ✓

**Properties**:
- Integral domain
- Euclidean domain
- Unique factorization domain

자세한 내용은 [[Gaussian Integers]] 참조

## Example 3: Polynomial Ring

**$\mathbb{Z}[x] \leq \mathbb{Q}[x]$**

Polynomials with integer coefficients form subring of polynomials with rational coefficients

**Check**:
- Subtraction preserves integer coefficients ✓
- Multiplication preserves integer coefficients ✓
- $1 \in \mathbb{Z}[x]$ ✓

**Chain**: $\mathbb{Z}[x] \leq \mathbb{Q}[x] \leq \mathbb{R}[x] \leq \mathbb{C}[x]$

자세한 내용은 [[Polynomial Ring]] 참조

## Example 4: Matrix Ring

**Upper triangular matrices** in $M_n(\mathbb{R})$:

$$U_n(\mathbb{R}) = \left\{ \begin{pmatrix} a & b \\ 0 & d \end{pmatrix} : a, b, d \in \mathbb{R} \right\}$$

**Check**:
- Closed under subtraction ✓
- Closed under multiplication ✓
- Contains $I$ ✓

Therefore $U_n(\mathbb{R}) \leq M_n(\mathbb{R}$ ✓

## Example 5: Even Integers (NON-example)

**$2\mathbb{Z}$ is NOT a unital subring of $\mathbb{Z}$**

**Why?**: $1 \notin 2\mathbb{Z}$

However:
- $2\mathbb{Z}$ is a ring (with unity $2$)
- $2\mathbb{Z}$ is an ideal of $\mathbb{Z}$
- $2\mathbb{Z}$ is a non-unital subring (관대한 정의)

**교훈**: Ideal $\neq$ Unital subring!

## Example 6: $\mathbb{Z}[\sqrt{2}]$

**$\mathbb{Z}[\sqrt{2}] = \{a + b\sqrt{2} : a, b \in \mathbb{Z}\}$** in $\mathbb{R}$

**Check**:
- $(a + b\sqrt{2}) - (c + d\sqrt{2}) = (a-c) + (b-d)\sqrt{2} \in \mathbb{Z}[\sqrt{2}]$ ✓
- $(a + b\sqrt{2})(c + d\sqrt{2}) = (ac + 2bd) + (ad + bc)\sqrt{2} \in \mathbb{Z}[\sqrt{2}]$ ✓
- $1 \in \mathbb{Z}[\sqrt{2}]$ ✓

**Properties**:
- Integral domain
- Unique factorization domain
- Quotient field: $\mathbb{Q}[\sqrt{2}]$

## Example 7: Center of Matrix Ring

**$Z(M_n(\mathbb{R}))$ = scalar matrices**

$$Z(M_n(\mathbb{R})) = \{cI : c \in \mathbb{R}\} \cong \mathbb{R}$$

**Check**:
- $cI - dI = (c-d)I \in Z$ ✓
- $(cI)(dI) = (cd)I \in Z$ ✓
- $I \in Z$ ✓

Therefore $Z(M_n(\mathbb{R})) \leq M_n(\mathbb{R})$ ✓

## Example 8: Continuous Functions

**$C^{\infty}[0,1] \leq C[0,1]$**

Infinitely differentiable functions form subring of continuous functions

**Check**:
- $f - g$ is $C^{\infty}$ if $f, g$ are ✓
- $fg$ is $C^{\infty}$ if $f, g$ are ✓
- Constant function $1$ is $C^{\infty}$ ✓

**Chain**: $C^{\infty}[0,1] \leq C^k[0,1] \leq C[0,1]$

## Example 9: Quaternions

**$\mathbb{H} = \{a + bi + cj + dk : a,b,c,d \in \mathbb{R}\}$**

**Subring**: $\mathbb{C} = \{a + bi : a, b \in \mathbb{R}\} \leq \mathbb{H}$

Identifying $\mathbb{C}$ with $\{a + bi + 0j + 0k\}$

**Note**: $\mathbb{H}$ is non-commutative, but $\mathbb{C}$ is commutative

자세한 내용은 [[Quaternions]] 참조

## Example 10: Direct Product

**$R_1 \times \{0\} \leq R_1 \times R_2$**

**Check**:
- $(a, 0) - (b, 0) = (a-b, 0) \in R_1 \times \{0\}$ ✓
- $(a, 0)(b, 0) = (ab, 0) \in R_1 \times \{0\}$ ✓
- $(1, 0) \in R_1 \times \{0\}$?

**문제**: $(1, 0) \neq (1, 1) = 1_{R_1 \times R_2}$

따라서 **NOT a unital subring**! (but is an ideal)

자세한 내용은 [[Direct Product]] 참조

---

# <span class="header-theorem">Theorem</span>

## Subring Correspondence (for Ring Homomorphism)

**정리**: $\phi: R \to S$가 ring homomorphism이고 $T \leq S$이면

$$\phi^{-1}(T) \leq R$$

**증명**:
- $a, b \in \phi^{-1}(T)$이면 $\phi(a), \phi(b) \in T$
- $\phi(a - b) = \phi(a) - \phi(b) \in T$ $\Rightarrow$ $a - b \in \phi^{-1}(T)$ ✓
- $\phi(ab) = \phi(a)\phi(b) \in T$ $\Rightarrow$ $ab \in \phi^{-1}(T)$ ✓
- $\phi(1_R) = 1_S \in T$ $\Rightarrow$ $1_R \in \phi^{-1}(T)$ ✓

자세한 내용은 [[Ring Homomorphism]] 참조

## Image of Subring

**정리**: $\phi: R \to S$가 ring homomorphism이고 $T \leq R$이면

$$\phi(T) \leq \phi(R)$$

(but not necessarily $\phi(T) \leq S$ if $\phi$ not surjective!)

**주의**: Image가 unital subring이 되려면 $\phi(1_R) = 1_S$ 필요

## Extension of Subrings

**정리**: $F$가 field이고 $\alpha \in \bar{F}$ (algebraic closure)이면

$$F \leq F[\alpha] \leq F(\alpha) \leq \bar{F}$$

**의미**: Field는 algebraic elements를 추가하여 확장 가능

자세한 내용은 [[Field Extension]] 참조

## Subring Generated by Element

**정리**: $R$이 ring이고 $a \in R$이면

$$\mathbb{Z}[a] = \{p(a) : p \in \mathbb{Z}[x]\}$$

is the smallest subring containing $a$

**원소**: $a$의 모든 polynomial expressions with integer coefficients

**예**:
- $\mathbb{Z}[i] = \mathbb{Z}[i]$ where $i^2 = -1$
- $\mathbb{Z}[\sqrt{2}] = \{a + b\sqrt{2} : a, b \in \mathbb{Z}\}$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Subring = "작은 환"**

### 메타포: 도시와 마을

**Ring $R$**: 큰 도시

**Subring $S$**: 도시 안의 작은 마을

**요구사항**:
1. 마을 내에서 덧셈/뺄셈 가능 (closed)
2. 마을 내에서 곱셈 가능 (closed)
3. 마을에 "기준점" 1 존재 (unital)

**중요**: 마을 밖으로 나가지 않고도 연산 가능!

### Subring vs Ideal

| 개념 | 메타포 | 특징 |
|------|--------|------|
| Subring | 독립된 마을 | 자체적으로 완전한 환 |
| Ideal | 공장 지역 | 외부 재료 흡수, but 1 없음 |

**Subring**: "Self-contained" (독립성)

**Ideal**: "Absorbing" (흡수성)

## 왜 Unital 정의가 중요한가?

### 1. Homomorphism Compatibility

Ring homomorphism $\phi: R \to S$는 $\phi(1_R) = 1_S$ 요구

만약 subring이 다른 항등원을 가지면:
- Restriction $\phi|_T: T \to S$가 ring homomorphism 아닐 수 있음
- 이론 전개가 복잡해짐

### 2. Field Theory

Field extension $F \leq E$에서:
- $1_F = 1_E$ 필수
- 그렇지 않으면 vector space 구조 깨짐

### 3. Ideal vs Subring 구분

Unital 정의:
- Proper ideal은 절대 unital subring이 아님
- 개념적 명확성

## 표기법 주의

| 표기 | 의미 |
|------|------|
| $S \leq R$ | $S$ is a subring of $R$ |
| $I \triangleleft R$ | $I$ is an ideal of $R$ |
| $S \subset R$ | Proper subring |
| $S \subseteq R$ | Subring (possibly $S = R$) |

## Common Pitfall^[흔한 실수]

### 1. Ideal $\neq$ Subring

$2\mathbb{Z} \triangleleft \mathbb{Z}$ (ideal)

but $2\mathbb{Z} \not\leq \mathbb{Z}$ (not unital subring)

**이유**: $1 \notin 2\mathbb{Z}$

### 2. Closure under Division?

Subring는 나눗셈에 닫혀있을 필요 없음!

예: $\mathbb{Z} \leq \mathbb{Q}$

$2, 3 \in \mathbb{Z}$ but $2/3 \notin \mathbb{Z}$ ✓ (OK)

### 3. Intersection vs Union

**Intersection**: Always subring ✓

**Union**: Generally NOT subring!

예: $\mathbb{Q} \cup (\mathbb{Q} + \sqrt{2}\mathbb{Q})$ is not a subring

### 4. Generated Subring Size

$\langle a \rangle$ can be infinite even if $R$ is finite!

Wait, no: if $R$ finite, then $\langle a \rangle$ finite too.

하지만: $\langle a \rangle$ can be much larger than expected

예: $\langle x \rangle = \mathbb{Z}[x]$ in $\mathbb{Q}[x]$ (infinite!)

### 5. Prime Subring ≠ Prime Ideal

**Prime subring**: Smallest subring

**Prime ideal**: Ideal with $ab \in P \Rightarrow a \in P$ or $b \in P$

완전히 다른 개념!

자세한 내용은 [[Prime Ideal]] 참조

## 응용 분야

**Algebra**:
- Ring theory foundations
- Field extensions
- Algebraic number theory

**Number Theory**:
- Algebraic integers
- Cyclotomic fields
- Class field theory

**Geometry**:
- Coordinate rings
- Function fields
- Algebraic varieties

**Analysis**:
- Function spaces
- Operator algebras

## 관련 개념

- [[Ring]]: Basic structure
- [[Ideal]]: Different closure property
- [[Subgroup]]: Analogous concept for groups
- [[Ring Homomorphism]]: Preserves subring structure
- [[Field Extension]]: Subrings in field context

## 역사적 배경

**19세기**: Ring 개념 발전
- Dedekind: Algebraic integers
- Kronecker: Polynomial rings

**20세기**: Unital vs non-unital 논쟁
- Bourbaki: Unital 정의 채택
- Modern algebra: 대부분 unital 사용

**현재**: Context-dependent
- Commutative algebra: Unital
- Functional analysis: 때때로 non-unital 허용

## 추가 학습 주제

**기초**:
- Subring test
- Basic examples ($\mathbb{Z} \leq \mathbb{Q}$)
- Subring vs ideal

**중급**:
- Prime subring
- Generated subring
- Subring lattice
- Center as subring

**고급**:
- Subring in field extensions
- Integral closure
- Algebraic integers
- Transcendence degree
- Hilbert basis theorem (polynomial subrings)

