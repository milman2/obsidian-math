# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Field]]
- [[Group of Units]]
- [[Commutative Ring]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Herstein, Noncommutative Rings
- Lam, A First Course in Noncommutative Rings

---

# <span class="header-definition">Definition</span>

## Division Ring^[나눗셈환]

**정의**: Ring $D$가 **division ring**^[나눗셈환] (또는 **skew field**^[비가환체])이다 $\Leftrightarrow$

1. $D \neq \{0\}$ (nontrivial)
2. $D$는 unity^[단위원] $1$을 가짐
3. 모든 nonzero 원소가 **multiplicative inverse**^[곱셈 역원]를 가짐

$$\forall a \in D \setminus \{0\}, \quad \exists a^{-1} \in D: \quad aa^{-1} = a^{-1}a = 1$$

**주의**: Commutativity는 요구하지 않음!

## Alternative Definition

**정의**: Division ring $D$ = ring where $(D \setminus \{0\}, \cdot)$가 **group**^[군]

즉:
- $(D, +)$: Abelian group
- $(D \setminus \{0\}, \cdot)$: Group (not necessarily abelian!)
- Distributivity

## Division Ring vs Field

| | Division Ring | Field |
|---|---------------|-------|
| **Additive structure** | Abelian group | Abelian group |
| **Multiplicative structure** | Group (nonzero elements) | **Abelian** group |
| **Commutativity** | NOT required | Required |
| **예시** | $\mathbb{H}$ (quaternions) | $\mathbb{Q}$, $\mathbb{R}$, $\mathbb{C}$ |

**핵심 차이**: Field = Commutative division ring

$$\text{Field} = \text{Commutative Division Ring}$$

## Skew Field

**용어**: **Skew field**^[비가환체] = Division ring

**의미**:
- "Skew" = non-commutative
- "Field" = division possible

**동의어**: Division ring = Skew field

## Related Concepts

**Unit**: $a$가 multiplicative inverse를 가짐

**Group of units**: $U(R) = R^* = $ invertible elements

**Division ring**: $U(D) = D \setminus \{0\}$ (모든 nonzero 원소가 unit!)

자세한 내용은 [[Group of Units]] 참조

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. No Zero Divisors

**정리**: Division ring은 zero divisors를 가지지 않음

**증명**: $ab = 0$이고 $a \neq 0$이면
- $a$는 invertible
- $b = a^{-1}(ab) = a^{-1} \cdot 0 = 0$ 
따라서 $ab = 0 \Rightarrow a = 0$ or $b = 0$

**계**: Division ring은 **integral domain**^[정역] (if commutative)

### 2. Cancellation Law

**정리**: Division ring에서 cancellation law 성립

**Left cancellation**:

$$ab = ac \text{ and } a \neq 0 \quad \Rightarrow \quad b = c$$

**Right cancellation**:

$$ba = ca \text{ and } a \neq 0 \quad \Rightarrow \quad b = c$$

**증명**: 
- $ab = ac$
- $a^{-1}(ab) = a^{-1}(ac)$
- $b = c$ 
### 3. No Proper Ideals

**정리**: Division ring의 ideals는 $\{0\}$과 $D$뿐

**증명**: $I \triangleleft D$이고 $I \neq \{0\}$이면
- $\exists a \in I$, $a \neq 0$
- $a$ is invertible
- $1 = a^{-1} a \in I$ (ideal property)
- $\Rightarrow$ $I = D$ 
**의미**: Division rings are "simple" (no nontrivial ideals)

### 4. Field of Fractions

**정리**: Division ring은 자기 자신의 "field of fractions"

**의미**: 이미 모든 nonzero 원소가 invertible하므로 확장 불필요

### 5. Characteristic

**정의**: Division ring $D$의 **characteristic**^[표수]

$$\text{char}(D) = \min\{n > 0 : n \cdot 1 = 0\}$$

(또는 $\infty$ if no such $n$ exists)

**정리**: Division ring의 characteristic은 0 또는 prime

**증명**: Field와 동일 (no zero divisors) 
## Units and Invertibility

**정리**: Division ring에서:

$$D^* = D \setminus \{0\}$$

**의미**: "거의 모든" 원소가 unit (0만 제외)

**Group structure**: $(D^*, \cdot)$는 group

- Commutative division ring: Abelian group
- Non-commutative division ring: Non-abelian group (generally)

## Subrings and Subfields

**정의**: Division ring $D$의 **subdivision ring**^[부분 나눗셈환]

$$E \subseteq D$$

where $E$ is itself a division ring

**예**: $\mathbb{C} \subseteq \mathbb{H}$ (복소수를 quaternions의 subdivision ring으로)

**Center**:

$$Z(D) = \{z \in D : zd = dz \text{ for all } d \in D\}$$

**정리**: $Z(D)$는 **field** (commutative division ring!)

자세한 내용은 [[Center]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Fields (Commutative Division Rings)

모든 **field**는 division ring입니다!

**예시**:
- $\mathbb{Q}$ (rationals) - $\mathbb{R}$ (reals) - $\mathbb{C}$ (complex numbers) - $\mathbb{F}_p$ (finite fields) - $\mathbb{Q}(\sqrt{2})$ (algebraic extensions) 
**특징**: Commutative!

## Example 2: Quaternions $\mathbb{H}$ ⭐

**가장 유명한 non-commutative division ring!**

**정의**:

$$\mathbb{H} = \{a + bi + cj + dk : a, b, c, d \in \mathbb{R}\}$$

**Multiplication rules**:

$$i^2 = j^2 = k^2 = ijk = -1$$

$$ij = k, \quad jk = i, \quad ki = j$$
$$ji = -k, \quad kj = -i, \quad ik = -j$$

**Inverse**: $q = a + bi + cj + dk \neq 0$이면

$$q^{-1} = \frac{\bar{q}}{|q|^2} = \frac{a - bi - cj - dk}{a^2 + b^2 + c^2 + d^2}$$

**Non-commutativity**:

$$ij = k \neq -k = ji$$

**응용**:
- 3D rotations
- Computer graphics
- Robotics
- Physics (quantum mechanics)

자세한 내용은 [[Quaternions]] 참조

## Example 3: $\mathbb{C}$ (as Subdivision Ring of $\mathbb{H}$)

**Complex numbers**: $\mathbb{C} = \{a + bi : a, b \in \mathbb{R}\} \subseteq \mathbb{H}$

**Properties**:
- Commutative - Division ring (field) - Subdivision ring of $\mathbb{H}$

**Center**: $Z(\mathbb{H}) = \mathbb{R}$ (real numbers only!)

## Example 4: Matrix Rings (NON-example)

**$M_n(F)$ for $n \geq 2$**: NOT a division ring!

**이유**: Singular matrices (zero divisors exist)

$$\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$$

**예외**: $M_1(F) \cong F$ (trivial case)

## Example 5: Finite Fields (Commutative!)

**$\mathbb{F}_p$, $\mathbb{F}_{p^n}$**: All finite fields

**Wedderburn's Theorem**: **모든 finite division ring은 commutative (field)!**

따라서 finite non-commutative division ring은 **존재하지 않음**!

## Example 6: Rational Functions (Field)

**$F(x)$**: Field of rational functions over field $F$

$$F(x) = \left\{ \frac{f(x)}{g(x)} : f, g \in F[x], g \neq 0 \right\}$$

**Division ring**:  (actually a field, commutative)

## Example 7: $p$-adic Numbers $\mathbb{Q}_p$

**$\mathbb{Q}_p$**: $p$-adic rationals

**Properties**:
- Commutative - Division ring (field) - Complete metric space
- Characteristic 0

자세한 내용은 [[p-adic Numbers]] 참조

## Example 8: Function Fields

**$F(X)$**: Function field over variety $X$

**Properties**:
- Commutative - Division ring (field) - Applications in algebraic geometry

## Example 9: Non-Commutative Formal Series (NOT Division Ring)

**$k\langle\langle x, y \rangle\rangle$**: Non-commutative power series in $x, y$

**NOT division ring**: Not all nonzero elements invertible

예: $x$ has no inverse

## Example 10: Endomorphism Ring (Usually NOT)

**$\text{End}_k(V)$ for vector space $V$**:

- If $\dim(V) = 1$: $\cong k$ (field) - If $\dim(V) > 1$: NOT division ring (zero divisors) ✗

---

# <span class="header-theorem">Theorem</span>

## Wedderburn's Little Theorem ⭐

**정리**: 모든 **finite division ring**은 **field**이다

$$|D| < \infty \quad \Rightarrow \quad D \text{ is commutative}$$

**의미**: Finite non-commutative division rings는 존재하지 않음!

**증명 개요** (어려움):
1. $Z(D) = $ center는 finite field $\mathbb{F}_q$
2. $D$는 $Z(D)$-vector space, $|D| = q^n$
3. Class equation 사용
4. Cyclotomic polynomials로 모순 유도
5. $\Rightarrow$ $n = 1$, 즉 $D = Z(D)$ 
**역사**: Wedderburn (1905)

## Frobenius Theorem

**정리**: $\mathbb{R}$ 위의 finite-dimensional associative division algebra는:

1. $\mathbb{R}$ (dimension 1)
2. $\mathbb{C}$ (dimension 2)
3. $\mathbb{H}$ (dimension 4)

**의미**: Quaternions는 "$\mathbb{R}$ 위의 유일한 4차원 division algebra"

**주의**: Octonions $\mathbb{O}$ (dimension 8)는 **associative하지 않음**!

## Structure Theorems

### No Proper Ideals

**정리**: Division ring $D$의 ideals는 $\{0\}$과 $D$뿐

**의미**: Division rings are **simple rings**

### Center is a Field

**정리**: Division ring $D$의 center $Z(D)$는 field

**증명**: 
- $Z(D)$는 commutative ring - $z \in Z(D) \setminus \{0\}$이면 $z^{-1} \in D$
- $z^{-1}$도 commutes with all: $z^{-1} \in Z(D)$ - 따라서 $Z(D)$는 field 
### Every Element Algebraic over Center

**정리**: $D$ finite-dimensional division algebra over its center $k$이면

모든 $d \in D$는 $k$ over algebraic

**의미**: Satisfies polynomial equation with coefficients in $k$

## Division Ring of Fractions

**정리**: Integral domain $R$이 division ring $D$에 embed되면

$$D = \text{Frac}(R) = \left\{ ab^{-1} : a, b \in R, b \neq 0 \right\}$$

(if minimal)

**주의**: Non-commutative에서는 조건 필요 (Ore condition)

자세한 내용은 [[Ore Condition]], [[Skew Field of Fractions]] 참조

## Brauer Group

**정의**: Central simple algebras over field $k$ modulo Morita equivalence

**원소**: Division algebras play key role

자세한 내용은 [[Brauer Group]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Division Ring = "나눗셈 가능한 Ring"**

### 메타포: 완벽한 산술

**Field**: 덧셈, 뺄셈, 곱셈, 나눗셈 모두 가능 + 교환법칙

**Division Ring**: 덧셈, 뺄셈, 곱셈, 나눗셈 모두 가능 (교환법칙은 선택사항)

**의미**:
- "거의" field처럼 작동
- 곱셈이 commutative하지 않을 수 있음
- 모든 nonzero 원소가 invertible

### Why "Division"?

**Division**^[나눗셈]: $a / b = a \cdot b^{-1}$

**Division ring**: 모든 nonzero $b$에 대해 $b^{-1}$ 존재!

$$a / b \text{ always defined (if } b \neq 0 \text{)}$$

### Quaternions: 핵심 예시

**$\mathbb{H}$**: 가장 유명한 non-commutative division ring

**역사적 중요성**:
- Hamilton (1843) 발견
- 최초의 non-commutative algebra
- 3D rotations의 자연스러운 언어

**응용**:
- Computer graphics (rotation interpolation)
- Aerospace engineering
- Quantum mechanics

## Division Ring vs Related Concepts

### Comparison Table

| Concept | Additive Group | Multiplicative | Commutative | Zero Divisors |
|---------|----------------|----------------|-------------|---------------|
| **Field** | Abelian | Group (nonzero) | Yes | No |
| **Division Ring** | Abelian | Group (nonzero) | Maybe | No |
| **Integral Domain** | Abelian | Monoid | Yes | No |
| **Ring with Unity** | Abelian | Monoid | Maybe | Maybe |

### Hierarchy

$$\text{Field} \subsetneq \text{Division Ring} \subsetneq \text{Ring with Unity}$$

$$\text{Field} \subsetneq \text{Integral Domain} \subsetneq \text{Commutative Ring}$$

**Division Ring과 Integral Domain**:
- Division ring: All nonzero invertible (may be non-commutative)
- Integral domain: No zero divisors (must be commutative)
- Intersection: **Field**!

## Non-Commutativity의 의미

**Quaternions에서**:

$$ij = k \neq -k = ji$$

**결과**:
- $(a + bi)(c + di) \neq (c + di)(a + bi)$ (generally)
- 순서가 중요!
- Matrix multiplication과 유사

**응용**:
- 3D rotations: 순서가 중요 (rotation은 non-commutative!)
- Quantum mechanics: Operators don't commute

## Wedderburn's Theorem의 중요성

**Statement**: Finite division rings are commutative

**의미**:
1. Non-commutative division rings는 **infinite**해야 함
2. Quaternions $\mathbb{H}$: Infinite over $\mathbb{R}$
3. Finite algebra에서는 commutativity가 "자동"

**증명**: 매우 어려움 (group theory, cyclotomic polynomials 사용)

## 응용 분야

### 1. Geometry and Physics

**Quaternions**:
- 3D/4D rotations
- Unit quaternions = $SU(2) = $ spinors
- Special relativity (spacetime)

**Clifford Algebras**:
- Generalization of quaternions
- Geometric algebra
- Physics (Dirac equation)

### 2. Computer Graphics

**Rotation interpolation**:
- Quaternions > Euler angles
- SLERP (Spherical Linear Interpolation)
- Animation, robotics

### 3. Algebra

**Central simple algebras**:
- Brauer group
- Galois cohomology
- Class field theory

### 4. Coding Theory

**Cyclic codes**: Use division ring properties

### 5. Operator Theory

**Von Neumann algebras**: Division ring structure

## 계산 방법

### Quaternion Multiplication

**$q_1 = a_1 + b_1 i + c_1 j + d_1 k$**
**$q_2 = a_2 + b_2 i + c_2 j + d_2 k$**

**Product**: Use $i^2 = j^2 = k^2 = -1$, $ij = k$, etc.

**Shortcut**: 
$$q_1 q_2 = (a_1 a_2 - b_1 b_2 - c_1 c_2 - d_1 d_2) + \cdots$$

**Software**: Most programming languages have quaternion libraries

### Inverse

**Quaternion $q = a + bi + cj + dk$**:

$$q^{-1} = \frac{a - bi - cj - dk}{a^2 + b^2 + c^2 + d^2}$$

**Conjugate**: $\bar{q} = a - bi - cj - dk$

**Norm**: $|q|^2 = q\bar{q} = a^2 + b^2 + c^2 + d^2$

## Common Pitfall^[흔한 실수]

### 1. Division Ring = Field?

**NO!** Division ring may be non-commutative

**예**: $\mathbb{H}$ is division ring but NOT field

### 2. Finite Division Ring?

**Wedderburn's Theorem**: All finite division rings are fields!

따라서 "finite non-commutative division ring"은 존재하지 않음

### 3. Quaternion Multiplication Order

$$ij \neq ji$$

**주의**: 순서가 중요! Non-commutative!

### 4. $(ab)^{-1} = a^{-1} b^{-1}$?

**NO!** In non-commutative ring:

$$(ab)^{-1} = b^{-1} a^{-1}$$

(순서 반대!)

### 5. Division $a/b$?

**주의**: $a/b = ab^{-1}$ or $a/b = b^{-1}a$?

Left vs right division 구별 필요!

### 6. Center of $\mathbb{H}$

$Z(\mathbb{H}) = \mathbb{R}$ (NOT $\mathbb{C}$!)

**이유**: $i$ doesn't commute with $j$!

### 7. Octonions

**$\mathbb{O}$**: NOT a division ring!

**이유**: Not associative! (multiplication)

Dimension 8, but loses associativity

## 역사적 배경

**1843**: **William Rowan Hamilton** discovers quaternions
- Walking along Royal Canal, Dublin
- Carved formula on bridge: $i^2 = j^2 = k^2 = ijk = -1$
- First non-commutative algebra

**1877**: **Frobenius** theorem (only $\mathbb{R}$, $\mathbb{C}$, $\mathbb{H}$ over $\mathbb{R}$)

**1905**: **Joseph Wedderburn** proves finite division rings are commutative

**Modern**: 
- Central simple algebras
- Brauer groups
- Non-commutative geometry
- Quantum groups

## 관련 개념

- [[Ring]]: General concept
- [[Field]]: Commutative division ring
- [[Quaternions]]: Main non-commutative example
- [[Group of Units]]: $D^* = D \setminus \{0\}$
- [[Integral Domain]]: Commutative, no zero divisors
- [[Center]]: $Z(D)$ is a field
- [[Simple Ring]]: No proper ideals
- [[Brauer Group]]: Classification of division algebras
- [[Clifford Algebra]]: Generalizations

## 추가 학습 주제

**기초**:
- Definition and basic properties
- Field vs division ring
- Quaternions $\mathbb{H}$
- No zero divisors

**중급**:
- Wedderburn's Little Theorem
- Frobenius Theorem
- Center is a field
- Quaternion applications (rotations)

**고급**:
- Central simple algebras
- Brauer group
- Skew field of fractions (Ore localization)
- Division rings in representation theory
- Non-commutative algebraic geometry
- Clifford algebras

