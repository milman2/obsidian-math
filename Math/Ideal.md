# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Subring]]
- [[Quotient Group, Factor Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Eisenbud, Commutative Algebra with a View Toward Algebraic Geometry
- Lang, Algebra

---

# <span class="header-definition">Definition</span>

## Two-sided Ideal

Ring $R$의 부분집합 $I$가 **ideal^[아이디얼]** (or **two-sided ideal^[양측 아이디얼]**)이다 $\Leftrightarrow$

1. $(I, +)$가 $(R, +)$의 **subgroup^[부분군]**
2. **Absorption property^[흡수 성질]**: $\forall r \in R, \forall a \in I$:

$$ra \in I \quad \text{and} \quad ar \in I$$

**표기**: $I \triangleleft R$

**직관**: Ideal은 $R$의 모든 원소와 곱해도 자기 안에 머무름

### Equivalent Definition

$\emptyset \neq I \subseteq R$가 ideal $\Leftrightarrow$

$$\forall a, b \in I, \forall r \in R: \quad a - b \in I, \quad ra \in I, \quad ar \in I$$

## Left Ideal

$I \subseteq R$가 **left ideal^[왼쪽 아이디얼]**이다 $\Leftrightarrow$

1. $(I, +)$가 subgroup
2. $\forall r \in R, \forall a \in I: \quad ra \in I$

**표기**: $I \triangleleft_L R$

**의미**: 왼쪽에서 곱해도 닫혀있음

## Right Ideal

$I \subseteq R$가 **right ideal^[오른쪽 아이디얼]**이다 $\Leftrightarrow$

1. $(I, +)$가 subgroup
2. $\forall r \in R, \forall a \in I: \quad ar \in I$

**표기**: $I \triangleleft_R R$

**의미**: 오른쪽에서 곱해도 닫혀있음

### Commutative Ring에서

**정리**: $R$이 commutative ring이면

$$\text{left ideal} = \text{right ideal} = \text{two-sided ideal}$$

따라서 commutative ring에서는 그냥 "ideal"이라고 부름

## Proper Ideal

Ideal $I$가 **proper ideal^[진 아이디얼]**이다 $\Leftrightarrow$

$$I \neq R$$

**중요한 관찰**:

**정리**: $I \neq R$ $\Leftrightarrow$ $1 \notin I$

**증명**:
- ($\Rightarrow$): $1 \in I$이면 모든 $r \in R$에 대해 $r = r \cdot 1 \in I$, 즉 $I = R$ ✗
- ($\Leftarrow$): $1 \notin I$이면 $I \neq R$ ✓

**따라서**: Proper ideal은 절대 unital subring이 아님!

## Trivial Ideal

**두 가지 trivial ideals**:

1. **Zero ideal**: $\{0\} \triangleleft R$
2. **Whole ring**: $R \triangleleft R$

**Nontrivial ideal**: $\{0\} \neq I \neq R$

## Principal Ideal

**정의**: 하나의 원소로 **generated^[생성]**된 ideal

**Left principal ideal**:

$$Ra = \{ra : r \in R\}$$

**Right principal ideal**:

$$aR = \{ar : r \in R\}$$

**Two-sided principal ideal**:

$$\langle a \rangle = RaR = \left\{ \sum_{i} r_i a s_i : r_i, s_i \in R \right\}$$

**Commutative ring에서**: $\langle a \rangle = Ra = aR$

### Example

**In $\mathbb{Z}$**: 

$$\langle n \rangle = n\mathbb{Z} = \{\ldots, -2n, -n, 0, n, 2n, \ldots\}$$

모든 ideal이 principal! (Principal Ideal Domain)

## Maximal Ideal

Proper ideal $M$이 **maximal ideal^[극대 아이디얼]**이다 $\Leftrightarrow$

$$M \subsetneq I \triangleleft R \quad \Rightarrow \quad I = R$$

**의미**: $M$보다 큰 proper ideal이 존재하지 않음

**동치 조건**: $M \triangleleft R$이 maximal $\Leftrightarrow$ $R/M$이 **field^[체]**

자세한 내용은 [[Maximal Ideal]] 참조

## Prime Ideal

Proper ideal $P$가 **prime ideal^[소 아이디얼]**이다 $\Leftrightarrow$

$$ab \in P \quad \Rightarrow \quad a \in P \text{ or } b \in P$$

**동치 조건**: $P \triangleleft R$이 prime $\Leftrightarrow$ $R/P$가 **integral domain^[정역]**

**관계**: Maximal ideal $\Rightarrow$ Prime ideal (역은 일반적으로 거짓)

자세한 내용은 [[Prime Ideal]] 참조

## Radical Ideal

Ideal $I$가 **radical ideal^[근기 아이디얼]**이다 $\Leftrightarrow$

$$a^n \in I \text{ for some } n \geq 1 \quad \Rightarrow \quad a \in I$$

**의미**: 거듭제곱이 들어있으면 원소 자체도 들어있음

**Radical of $I$**:

$$\sqrt{I} = \{a \in R : a^n \in I \text{ for some } n \geq 1\}$$

**성질**: $\sqrt{I}$는 항상 radical ideal

자세한 내용은 [[Radical Ideal]] 참조

## Nilradical

Ring $R$의 **nilradical^[멱영근기]**:

$$\text{Nil}(R) = \{a \in R : a^n = 0 \text{ for some } n \geq 1\}$$

**정리**: $\text{Nil}(R) = \sqrt{\{0\}}$ = radical of zero ideal

**의미**: 모든 nilpotent elements의 집합

자세한 내용은 [[Nilradical]] 참조

## Jacobson Radical

Ring $R$의 **Jacobson radical^[제이콥슨 근기]**:

$$J(R) = \bigcap_{M \text{ maximal}} M$$

**의미**: 모든 maximal ideals의 교집합

자세한 내용은 [[Jacobson Radical]] 참조

---

# <span class="header-properties">Properties</span>

## Ideal Operations

### 1. Sum of Ideals

$$I + J = \{a + b : a \in I, b \in J\}$$

**정리**: $I + J \triangleleft R$ (ideal)

**성질**: Smallest ideal containing both $I$ and $J$

### 2. Product of Ideals

$$IJ = \left\{ \sum_{i=1}^{n} a_i b_i : a_i \in I, b_i \in J, n \in \mathbb{N} \right\}$$

**정리**: $IJ \triangleleft R$ (ideal)

**주의**: $IJ \subseteq I \cap J$ (generally proper subset!)

### 3. Intersection of Ideals

$$I \cap J$$

**정리**: $I \cap J \triangleleft R$ (ideal)

**일반화**: 임의의 ideals의 교집합도 ideal

$$\bigcap_{\alpha} I_{\alpha} \triangleleft R$$

### 4. Ideal Quotient

$$I : J = \{r \in R : rJ \subseteq I\}$$

**정리**: $I : J \triangleleft R$ (ideal)

**의미**: "$J$를 곱하면 $I$에 들어가는" 원소들

## Lattice Structure

Ring $R$의 모든 ideals는 **lattice^[격자]** 구조 형성:

**Join**: $I \vee J = I + J$ (sum)

**Meet**: $I \wedge J = I \cap J$ (intersection)

**순서**: 포함 관계 $\subseteq$

**특징**:
- 최소원: $\{0\}$
- 최대원: $R$
- Modular lattice (if commutative)

## Quotient Ring

**정리**: $I \triangleleft R$이면 quotient ring $R/I$ 정의 가능

**Cosets^[잉여류]**:

$$R/I = \{r + I : r \in R\}$$

**연산**:
- $(a + I) + (b + I) = (a + b) + I$
- $(a + I) \cdot (b + I) = (ab) + I$

**Well-defined**: Ideal의 absorption property 덕분

자세한 내용은 [[Quotient Ring]] 참조

## Correspondence Theorem

**정리**: $I \triangleleft R$이면 bijection:

$$\{\text{ideals of } R \text{ containing } I\} \leftrightarrow \{\text{ideals of } R/I\}$$

**Correspondence**: $J \mapsto J/I$

**성질 보존**:
- Maximality
- Primeness
- Inclusion relations

자세한 내용은 [[Correspondence Theorem]] 참조

## Ideal in Polynomial Ring

**정리**: $I \triangleleft R$이면 $I[x] \triangleleft R[x]$

**정의**: 

$$I[x] = \left\{ \sum_{i=0}^{n} a_i x^i : a_i \in I \right\}$$

**응용**: Extension and contraction of ideals

자세한 내용은 [[Polynomial Ring]] 참조

## Chinese Remainder Theorem

**정리**: $I_1, \ldots, I_n \triangleleft R$이 pairwise coprime이면

$$I_1 + I_j = R \text{ for } j \neq 1$$

다음이 성립:

$$R / (I_1 \cap \cdots \cap I_n) \cong R/I_1 \times \cdots \times R/I_n$$

**특히**: $\gcd(m, n) = 1$이면

$$\mathbb{Z}/mn\mathbb{Z} \cong \mathbb{Z}/m\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$$

자세한 내용은 [[Chinese Remainder Theorem]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Ideals in $\mathbb{Z}$

**모든 ideal은 principal**:

$$I = n\mathbb{Z} = \{nk : k \in \mathbb{Z}\}$$

**예**:
- $2\mathbb{Z} = \{\ldots, -4, -2, 0, 2, 4, \ldots\}$ (even integers)
- $3\mathbb{Z} = \{\ldots, -6, -3, 0, 3, 6, \ldots\}$ (multiples of 3)

**Maximal ideals**: $p\mathbb{Z}$ where $p$ is prime

**Prime ideals**: $p\mathbb{Z}$ where $p$ is prime (same as maximal!)

## Example 2: $\mathbb{Z}/6\mathbb{Z}$

**모든 ideals**:
- $\langle 0 \rangle = \{0\}$
- $\langle 2 \rangle = \{0, 2, 4\}$
- $\langle 3 \rangle = \{0, 3\}$
- $\langle 1 \rangle = \mathbb{Z}/6\mathbb{Z}$

**Maximal ideals**: $\langle 2 \rangle$, $\langle 3 \rangle$

**Quotients**:
- $\mathbb{Z}/6\mathbb{Z} / \langle 2 \rangle \cong \mathbb{Z}/2\mathbb{Z}$ ✓ (field)
- $\mathbb{Z}/6\mathbb{Z} / \langle 3 \rangle \cong \mathbb{Z}/3\mathbb{Z}$ ✓ (field)

## Example 3: Polynomial Ring $\mathbb{R}[x]$

**Principal ideal**:

$$\langle x^2 + 1 \rangle = \{(x^2 + 1) \cdot p(x) : p(x) \in \mathbb{R}[x]\}$$

**Quotient**:

$$\mathbb{R}[x] / \langle x^2 + 1 \rangle \cong \mathbb{C}$$

**이유**: $x^2 + 1 = 0$ 관계식 부과 $\Rightarrow$ $x$ acts like $i$

**Maximal ideal**: $\langle x^2 + 1 \rangle$ ✓ (quotient is field!)

## Example 4: Matrix Ring $M_2(\mathbb{R})$

**Left ideal**:

$$I = \left\{ \begin{pmatrix} a & b \\ 0 & 0 \end{pmatrix} : a, b \in \mathbb{R} \right\}$$

**Check (left ideal)**:

$$\begin{pmatrix} r & s \\ t & u \end{pmatrix} \begin{pmatrix} a & b \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} ra & rb \\ 0 & 0 \end{pmatrix} \in I$$ ✓

**Not two-sided**: 

$$\begin{pmatrix} a & b \\ 0 & 0 \end{pmatrix} \begin{pmatrix} r & s \\ t & u \end{pmatrix} = \begin{pmatrix} * & * \\ 0 & 0 \end{pmatrix}$$ 

but second row can be nonzero! ✗

## Example 5: $\mathbb{C}[x, y]$

**Ideal generated by two elements**:

$$\langle x, y \rangle = \{xp(x,y) + yq(x,y) : p, q \in \mathbb{C}[x,y]\}$$

**원소**: 모든 상수항이 0인 다항식

**Quotient**:

$$\mathbb{C}[x,y] / \langle x, y \rangle \cong \mathbb{C}$$

**Geometric interpretation**: Functions vanishing at origin

자세한 내용은 [[Algebraic Geometry]] 참조

## Example 6: Continuous Functions

**$C[0,1]$ with pointwise operations**

**Ideal**:

$$I_a = \{f \in C[0,1] : f(a) = 0\}$$

for fixed $a \in [0,1]$

**Check**:
- $f - g$ vanishes at $a$ if $f, g$ do ✓
- $(rf)(a) = r(a) \cdot f(a) = r(a) \cdot 0 = 0$ ✓

**Maximal ideal**: $I_a$ ✓

**Quotient**: $C[0,1] / I_a \cong \mathbb{R}$ (evaluation at $a$)

## Example 7: Nilradical Example

**$R = \mathbb{Z}/12\mathbb{Z}$**

**Nilpotent elements**: $\overline{0}, \overline{6}$

Check: $\overline{6}^2 = \overline{36} = \overline{0}$ ✓

**Nilradical**: $\text{Nil}(R) = \langle 6 \rangle = \{0, 6\}$

## Example 8: Principal Ideal Domain

**$\mathbb{Z}[i]$ (Gaussian integers)**

모든 ideal이 principal:

$$I = \langle a + bi \rangle$$

**예**: $\langle 1 + i \rangle = \{(1+i)(a + bi) : a, b \in \mathbb{Z}\}$

**성질**: PID (Principal Ideal Domain) ✓

자세한 내용은 [[Principal Ideal Domain]] 참조

## Example 9: Non-Principal Ideal

**$\mathbb{Z}[x]$에서**:

$$I = \langle 2, x \rangle = \{2p(x) + xq(x) : p, q \in \mathbb{Z}[x]\}$$

**원소 예**: $2, x, 2x, x^2, 2 + x$, etc.

**Not principal**: $I \neq \langle f(x) \rangle$ for any $f(x)$

**이유**: $2, x \in I$ but $\gcd(2, x) = 1$ in $\mathbb{Q}[x]$

## Example 10: Prime vs Maximal

**In $\mathbb{Z}[x]$**:

**Maximal ideal**: $\langle 2, x \rangle$ ✓

**Quotient**: $\mathbb{Z}[x] / \langle 2, x \rangle \cong \mathbb{Z}/2\mathbb{Z}$ (field!)

**Prime but not maximal**: $\langle x \rangle$

**Quotient**: $\mathbb{Z}[x] / \langle x \rangle \cong \mathbb{Z}$ (integral domain, not field)

---

# <span class="header-theorem">Theorem</span>

## First Isomorphism Theorem

**정리**: $\phi: R \to S$가 ring homomorphism이면

$$R / \ker(\phi) \cong \text{Im}(\phi)$$

**의미**: Kernel (ideal)로 나누면 image 얻음

자세한 내용은 [[Ring Homomorphism]], [[Isomorphism Theorem]] 참조

## Second Isomorphism Theorem

**정리**: $I, J \triangleleft R$이면

$$(I + J) / J \cong I / (I \cap J)$$

**Diamond Isomorphism Theorem**이라고도 함

## Third Isomorphism Theorem

**정리**: $I \subseteq J \triangleleft R$이면

$$(R/I) / (J/I) \cong R/J$$

**의미**: "두 번 나누기 = 한 번에 나누기"

## Fourth Isomorphism Theorem (Correspondence)

**정리**: $I \triangleleft R$이면

$$\{\text{ideals } J \text{ with } I \subseteq J \subseteq R\} \leftrightarrow \{\text{ideals of } R/I\}$$

via $J \mapsto J/I$, inverse $\bar{J} \mapsto \pi^{-1}(\bar{J})$

## Nakayama's Lemma

**정리**: $M$이 finitely generated $R$-module이고 $I \subseteq J(R)$이면

$$IM = M \quad \Rightarrow \quad M = 0$$

**응용**: Module theory, commutative algebra

자세한 내용은 [[Nakayama's Lemma]] 참조

## Krull's Theorem

**정리**: Nontrivial ring $R$은 적어도 하나의 maximal ideal을 가짐

**증명**: Zorn's Lemma 사용 (axiom of choice)

## Structure Theorem for PIDs

**정리**: $R$이 PID이고 $M$이 finitely generated $R$-module이면

$$M \cong R^r \oplus R/(d_1) \oplus \cdots \oplus R/(d_n)$$

where $d_1 | d_2 | \cdots | d_n$

**응용**: Classification of finitely generated abelian groups

자세한 내용은 [[Principal Ideal Domain]] 참조

## Hilbert Basis Theorem

**정리**: $R$이 Noetherian ring이면 $R[x]$도 Noetherian

**의미**: Polynomial ring은 ascending chain condition 보존

자세한 내용은 [[Noetherian Ring]] 참조

## Going-Up and Going-Down Theorems

**정리 (Going-Up)**: $R \subseteq S$ integral extension이고 $P_1 \subseteq P_2$ prime ideals in $R$이면, prime ideal $Q_1 \subseteq S$ with $Q_1 \cap R = P_1$에 대해 $Q_2 \subseteq S$ 존재하여

$$Q_1 \subseteq Q_2, \quad Q_2 \cap R = P_2$$

**응용**: Dimension theory in algebraic geometry

자세한 내용은 [[Integral Extension]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Ideal = "Absorbing Set"**

### 메타포: 블랙홀

**Ring $R$**: 우주

**Ideal $I$**: 블랙홀

**Absorption property**: 
- $r \cdot i \in I$ for all $r \in R$
- 외부 물질($r$)과 블랙홀 물질($i$) 결합 → 블랙홀에 흡수됨

**메타포의 의미**:
- Ideal은 "빠져나올 수 없는" 구조
- 바깥 원소와 곱해도 안에 머무름

### Subring vs Ideal

| 개념 | 특징 | 메타포 |
|------|------|--------|
| **Subring** | Self-contained | 독립된 도시 |
| **Ideal** | Absorbing | 블랙홀 |

**Subring**: $1 \in S$ (자체 완결적)

**Ideal**: $1 \notin I$ (proper), absorption!

### Quotient Ring = "Collapse"

**$R/I$**: Ideal $I$를 하나의 점 (영원소)으로 "축약"

**메타포**: 
- $I$ = "무시할 수 있는" 오차
- $R/I$ = 오차를 제거한 "깨끗한" 세계

## 왜 중요한가?

### 1. Quotient Structures

**군론**: Normal subgroup으로 quotient group

**환론**: Ideal로 quotient ring

**Ideal의 역할**: "나눌 수 있는" 부분집합

### 2. Kernel of Homomorphism

**정리**: $\phi: R \to S$ ring homomorphism

$$\ker(\phi) = \{r \in R : \phi(r) = 0\} \triangleleft R$$

**의미**: Kernel은 항상 ideal!

**역**: 모든 ideal은 어떤 homomorphism의 kernel

$$I \triangleleft R \quad \Rightarrow \quad I = \ker(\pi: R \to R/I)$$

### 3. Geometric Interpretation

**Algebraic Geometry**:

**Ideal $I \subseteq k[x_1, \ldots, x_n]$** $\leftrightarrow$ **Algebraic variety**

$$V(I) = \{(a_1, \ldots, a_n) : f(a_1, \ldots, a_n) = 0 \text{ for all } f \in I\}$$

**의미**: 
- Ideal = "vanishing conditions"
- Variety = solution set

자세한 내용은 [[Algebraic Geometry]] 참조

### 4. Number Theory

**Algebraic number theory**:

**Ideal in $\mathcal{O}_K$** (ring of integers) replaces "numbers"

**Unique factorization**:
- Elements may not factor uniquely
- But ideals always factor uniquely! (Dedekind domains)

자세한 내용은 [[Algebraic Number Theory]] 참조

### 5. Module Theory

**Ideal $I \triangleleft R$** $\leftrightarrow$ **$R$-submodule of $R$**

**의미**: Ideals는 module의 특별한 경우

자세한 내용은 [[Module]] 참조

## 계산 방법

### Ideal에 속하는지 확인

**주어진**: $I = \langle g_1, \ldots, g_n \rangle$, 원소 $f$

**질문**: $f \in I$?

**방법**: $f = r_1 g_1 + \cdots + r_n g_n$으로 표현 가능한가?

**Tool**: Gröbner basis (polynomial rings)

### Ideal Operations

**Sum**: $I + J = \langle \text{generators of } I, \text{generators of } J \rangle$

**Product**: $IJ = \langle g_i h_j : g_i \in \text{gen}(I), h_j \in \text{gen}(J) \rangle$

**Intersection**: Generally difficult! Use elimination theory

### Maximal/Prime Test

**Maximal test**: $R/I$가 field인가?

**Prime test**: $R/I$가 integral domain인가?

**실용적**: Quotient ring의 구조 분석

## 표기법

| 표기 | 의미 |
|------|------|
| $I \triangleleft R$ | $I$ is ideal of $R$ |
| $\langle a \rangle$ | Principal ideal generated by $a$ |
| $I + J$ | Sum of ideals |
| $IJ$ | Product of ideals |
| $I \cap J$ | Intersection |
| $I : J$ | Ideal quotient |
| $\sqrt{I}$ | Radical of $I$ |
| $R/I$ | Quotient ring |

## Common Pitfall^[흔한 실수]

### 1. Ideal $\neq$ Subring

**$2\mathbb{Z} \triangleleft \mathbb{Z}$** (ideal)

but **$2\mathbb{Z} \not\leq \mathbb{Z}$** (not unital subring)

**이유**: $1 \notin 2\mathbb{Z}$

### 2. Product $\neq$ Intersection

Generally: $IJ \subsetneq I \cap J$ (proper!)

**예**: $I = J = 2\mathbb{Z}$
- $IJ = 4\mathbb{Z}$
- $I \cap J = 2\mathbb{Z}$
- $4\mathbb{Z} \subsetneq 2\mathbb{Z}$ ✓

**등호**: Coprime ideals에서만 ($I + J = R$)

### 3. Left $\neq$ Right (Non-commutative)

Non-commutative ring에서:
- Left ideal $\neq$ right ideal
- Two-sided ideal 가장 제한적

**예**: Matrix rings

### 4. Prime $\neq$ Maximal (일반적으로)

**관계**: Maximal $\Rightarrow$ Prime

**역 거짓**: $\langle x \rangle \triangleleft \mathbb{Z}[x]$ is prime but not maximal

**등호**: PID에서는 nonzero prime = maximal

### 5. Generation Confusion

**$\langle a, b \rangle \neq \{a, b\}$**!

$$\langle a, b \rangle = \{ra + sb : r, s \in R\}$$

모든 선형결합 포함!

### 6. Proper Ideal Check

$I \triangleleft R$ proper $\Leftrightarrow$ $1 \notin I$

Not just $I \neq R$ (요 확인!)

## 응용 분야

**Algebra**:
- Ring theory
- Module theory
- Homological algebra

**Algebraic Geometry**:
- Varieties and schemes
- Nullstellensatz
- Dimension theory

**Number Theory**:
- Algebraic integers
- Class groups
- Unique factorization

**Algebraic Topology**:
- Cohomology rings
- Steenrod algebra

**Computer Science**:
- Computer algebra systems
- Cryptography (ideal lattices)
- Coding theory

## 관련 개념

- [[Ring]]: Basic structure
- [[Subring]]: Different closure property
- [[Quotient Ring]]: Construction from ideals
- [[Ring Homomorphism]]: Kernel is ideal
- [[Maximal Ideal]]: Quotient is field
- [[Prime Ideal]]: Quotient is integral domain
- [[Principal Ideal Domain]]: All ideals principal
- [[Noetherian Ring]]: Ascending chain condition

## 역사적 배경

**19세기**:
- **Kummer**: "Ideal numbers" (imaginary divisors)
- **Dedekind**: Modern ideal theory
- 목표: Restore unique factorization

**20세기**:
- **Noether**: Ascending chain condition
- **Hilbert**: Basis theorem
- **Zariski**: Geometric interpretation

**현대**:
- Commutative algebra
- Algebraic geometry (schemes)
- Noncommutative ring theory

## 추가 학습 주제

**기초**:
- Definition and examples
- Ideal operations
- Quotient rings
- Isomorphism theorems

**중급**:
- Maximal and prime ideals
- Principal ideal domains
- Chinese Remainder Theorem
- Radical and nilradical

**고급**:
- Noetherian rings
- Artinian rings
- Dedekind domains
- Krull dimension
- Primary decomposition
- Gröbner bases
- Hilbert's Nullstellensatz
- Scheme theory

