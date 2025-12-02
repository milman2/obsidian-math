# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Function]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra

---

# <span class="header-definition">Definition</span>

## Ring^[환]

집합 $R$과 두 이항 연산 $+$ (addition^[덧셈]), $\cdot$ (multiplication^[곱셈])에 대해, $(R, +, \cdot)$가 **ring**^[환]이다 $\Leftrightarrow$ 다음을 만족:

### 1. Abelian Group under Addition^[덧셈에 대한 아벨군]

$(R, +)$는 abelian group^[아벨군]:
- **Associativity**: $(a+b)+c = a+(b+c)$
- **Identity**: $\exists 0 \in R, \; a + 0 = a$
- **Inverse**: $\forall a \in R, \; \exists (-a), \; a + (-a) = 0$
- **Commutativity**: $a + b = b + a$

### 2. Monoid under Multiplication^[곱셈에 대한 모노이드]

- **Closure**: $\forall a, b \in R, \; ab \in R$
- **Associativity**: $(ab)c = a(bc)$

### 3. Distributive Laws^[분배법칙]

- **Left distributivity**^[왼쪽 분배]: $a(b+c) = ab + ac$
- **Right distributivity**^[오른쪽 분배]: $(a+b)c = ac + bc$

**주의**: 곱셈의 항등원(multiplicative identity)은 필수가 아님!

**중요**: 환의 정의를 보면 알 수 있듯이 곱셈에 대한 항등원이나 역원이 존재할 필요가 없다. 항등원이 존재한다고 해도 역원이 존재할 필요 또한 없다.

### 표기법

군에서는 연산에 대한 항등원을 $e$라고 표현한다. 환에서는 연산이 2개이므로 어느 연산에 대한 항등원인지 구별하기 위해 다른 기호를 사용한다:
- **덧셈의 항등원**: $0$ (identity^[항등원])
- **곱셈의 항등원**: $1$ (unity^[단위원])

## Ring with Identity^[단위원을 갖는 환]

Ring $R$이 **ring with identity**^[단위원을 갖는 환] (또는 **unital ring**^[단위환])이다 $\Leftrightarrow$

$$\exists 1 \in R, \; \forall a \in R, \quad 1 \cdot a = a \cdot 1 = a$$

**주의**: $1 \neq 0$ (단, trivial ring $R = \{0\}$ 제외)

**표기**: 명시하지 않으면 보통 ring은 identity를 갖는다고 가정

## Commutative Ring^[가환환]

Ring $R$이 **commutative**^[가환]이다 $\Leftrightarrow$

$$\forall a, b \in R, \quad ab = ba$$

## Division Ring^[나눗셈환]

Ring $R$ (with identity $1 \neq 0$)이 **division ring**^[나눗셈환] (또는 **skew field**^[비가환체])이다 $\Leftrightarrow$

$$\forall a \in R \setminus \{0\}, \; \exists a^{-1} \in R, \quad aa^{-1} = a^{-1}a = 1$$

즉, 0이 아닌 모든 원소가 multiplicative inverse^[곱셈 역원]을 가짐

**주의**: 교환법칙이 성립하지 않을 수 있음

## Unit^[단원]

Ring $R$ (with identity)의 원소 $u \in R$이 **unit**^[단원]이다 $\Leftrightarrow$

$$\exists v \in R, \quad uv = vu = 1$$

**표기**: $R^\times$ = group of units in $R$

## Zero Divisor^[영인자]

Commutative ring $R$의 nonzero 원소 $a \in R \setminus \{0\}$가 **zero divisor**^[영인자]이다 $\Leftrightarrow$

$$\exists b \in R \setminus \{0\}, \quad ab = 0$$

**예**: $\mathbb{Z}/6\mathbb{Z}$에서 $\overline{2} \cdot \overline{3} = \overline{0}$

## Integral Domain^[정역]

Commutative ring $R$ (with identity $1 \neq 0$)이 **integral domain**^[정역]이다 $\Leftrightarrow$ zero divisor가 없음

즉:

$$ab = 0 \Rightarrow a = 0 \text{ or } b = 0$$

**동등 조건**: Cancellation law^[소거법칙] 성립
$$ab = ac \text{ and } a \neq 0 \Rightarrow b = c$$

## Ideal^[아이디얼]

Ring $R$의 부분집합 $I \subseteq R$가 **ideal**^[아이디얼]이다 $\Leftrightarrow$ 다음을 만족:

### Left Ideal^[왼쪽 아이디얼]

1. $(I, +)$는 $R$의 subgroup^[부분군]
2. $\forall r \in R, \forall a \in I, \quad ra \in I$

### Right Ideal^[오른쪽 아이디얼]

1. $(I, +)$는 $R$의 subgroup
2. $\forall r \in R, \forall a \in I, \quad ar \in I$

### Two-sided Ideal^[양측 아이디얼]

Left ideal이면서 right ideal

**주의**: Commutative ring에서는 left/right/two-sided 구별 불필요

**표기**: $I \triangleleft R$ (ideal)

## Ring Homomorphism^[환 준동형사상]

함수 $\phi: R \to S$ (where $R, S$ are rings)가 **ring homomorphism**^[환 준동형사상]이다 $\Leftrightarrow$

1. $\phi(a + b) = \phi(a) + \phi(b)$ (덧셈 보존)
2. $\phi(ab) = \phi(a)\phi(b)$ (곱셈 보존)

**주의**: Identity를 보존하는지 여부는 정의에 따라 다름
- 일부 책에서는 $\phi(1_R) = 1_S$도 요구

### Kernel and Image

- **Kernel**: $\ker(\phi) = \{r \in R : \phi(r) = 0\}$ (ideal of $R$)
- **Image**: $\text{im}(\phi) = \phi(R)$ (subring of $S$)

---

# <span class="header-examples">Examples</span>

## Example 1: 정수환

$$\mathbb{Z}$$

- **Identity**: $1$
- **Commutative**: Yes
- **Integral domain**: Yes
- **Units**: $\mathbb{Z}^\times = \{1, -1\}$

## Example 2: Modular Arithmetic

$$\mathbb{Z}/n\mathbb{Z}$$

- **Commutative**: Yes
- **Integral domain**: $\Leftrightarrow$ $n$ is prime
- **Units**: $(\mathbb{Z}/n\mathbb{Z})^\times = \{[a] : \gcd(a,n) = 1\}$

**예**: $\mathbb{Z}/6\mathbb{Z}$
- Zero divisors: $\overline{2}, \overline{3}, \overline{4}$
- Units: $\overline{1}, \overline{5}$

## Example 3: Polynomial Ring^[다항식환]

$$R[x] = \{a_0 + a_1x + \cdots + a_nx^n : a_i \in R, n \geq 0\}$$

$R$이 commutative ring이면 $R[x]$도 commutative ring

**성질**:
- $R$이 integral domain $\Rightarrow$ $R[x]$도 integral domain
- $\deg(fg) = \deg(f) + \deg(g)$ (if $R$ is integral domain)

## Example 4: Matrix Ring^[행렬환]

$$M_n(R) = \{n \times n \text{ matrices over } R\}$$

- **Identity**: $I_n$
- **Commutative**: No (for $n \geq 2$)
- **Zero divisors**: Many

**예**: $M_2(\mathbb{R})$에서
$$\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$$

## Example 5: Quaternions^[사원수]

$$\mathbb{H} = \{a + bi + cj + dk : a,b,c,d \in \mathbb{R}\}$$

Relations: $i^2 = j^2 = k^2 = ijk = -1$

- **Division ring**: Yes
- **Commutative**: No

**예**: $ij = k$ but $ji = -k$

## Example 6: Function Ring^[함수환]

$$C(X) = \{\text{continuous functions } f: X \to \mathbb{R}\}$$

Pointwise operations: $(f+g)(x) = f(x) + g(x)$, $(fg)(x) = f(x)g(x)$

- **Commutative**: Yes
- **Identity**: constant function $1$

## Example 7: Trivial Ring^[자명환]

$$R = \{0\}$$

$0 = 1$ (유일한 경우)

## Example 8: Ring without Identity

$$2\mathbb{Z} = \{\text{even integers}\}$$

- Subring of $\mathbb{Z}$
- **No identity**: 1이 없음
- **Integral domain**: Yes (zero divisor 없음)

---

# <span class="header-properties">Properties</span>

## Basic Properties^[기본 성질]

### 1. $0 \cdot a = a \cdot 0 = 0$

**증명**: $0 \cdot a = (0+0) \cdot a = 0 \cdot a + 0 \cdot a$

양변에서 $0 \cdot a$ 빼면 $0 = 0 \cdot a$

### 2. $(-a)b = a(-b) = -(ab)$

**증명**: $ab + (-a)b = (a + (-a))b = 0 \cdot b = 0$

따라서 $(-a)b = -(ab)$

### 3. $(-a)(-b) = ab$

**증명**: $(-a)(-b) = -(a(-b)) = -(-(ab)) = ab$

### 4. Distributivity with Subtraction^[뺄셈에 대한 분배법칙]

$$a(b-c) = ab - ac \quad \text{and} \quad (b-c)a = ba - ca$$

**증명**: $a(b-c) = a(b + (-c)) = ab + a(-c) = ab + (-(ac)) = ab - ac$

### 5. Properties with Unity^[단위원이 있을 때]

Ring $R$이 단위원 $1$을 가지면:

**(a)** $(-1)a = -a$

**증명**: $a + (-1)a = 1 \cdot a + (-1)a = (1 + (-1))a = 0 \cdot a = 0$

따라서 $(-1)a = -a$

**(b)** $(-1)(-1) = 1$

**증명**: $(-1)(-1) = -((-1) \cdot 1) = -(-1) = 1$

### 6. Cancellation Law^[소거법칙] (주의!)

**중요**: 환에서는 곱셈에 대한 역원이 존재할 필요가 없으므로, 군에서와 같이 함부로 소거할 수 없다.

**예시**:
- $ab = ac$라고 해서 $b = c$를 결론낼 수 없음 ($a$의 역원이 없을 수 있음)
- $a^2 = a$라고 해서 $a = 0$ 또는 $a = 1$을 결론낼 수 없음

**주의**: Integral domain^[정역]에서는 소거법칙이 성립 (zero divisor가 없으므로)

$$ab = ac \text{ and } a \neq 0 \Rightarrow b = c \quad (\text{in integral domain})$$

## Characteristic^[표수]

Ring $R$ (with identity)의 **characteristic**^[표수] $\text{char}(R)$:

$$\text{char}(R) = \min\{n > 0 : n \cdot 1 = 0\}$$

만약 그런 $n$이 없으면 $\text{char}(R) = 0$

**예**:
- $\text{char}(\mathbb{Z}) = 0$
- $\text{char}(\mathbb{Z}/n\mathbb{Z}) = n$
- $\text{char}(\mathbb{Q}) = \text{char}(\mathbb{R}) = \text{char}(\mathbb{C}) = 0$

### 정리

Integral domain $R$에서 $\text{char}(R)$는 0 또는 prime

**증명**: $\text{char}(R) = mn$이고 $1 < m, n < \text{char}(R)$이면
$$(m \cdot 1)(n \cdot 1) = mn \cdot 1 = 0$$
Zero divisor 발생 (모순)

## Ideals and Quotient Rings^[아이디얼과 몫환]

### Quotient Ring^[몫환]

$I \triangleleft R$에 대해, **quotient ring**^[몫환] $R/I$:

**집합**: $R/I = \{a + I : a \in R\}$ (cosets)

**연산**:
- $(a+I) + (b+I) = (a+b) + I$
- $(a+I)(b+I) = ab + I$

Well-defined (ideal의 정의에 의해)

### Canonical Projection

$$\pi: R \to R/I, \quad \pi(a) = a + I$$

Ring homomorphism with $\ker(\pi) = I$

## Isomorphism Theorems^[동형 정리]

### First Isomorphism Theorem

Ring homomorphism $\phi: R \to S$에 대해:

$$R/\ker(\phi) \cong \text{im}(\phi)$$

### Second Isomorphism Theorem

$I, J \triangleleft R$이면:

$$I/(I \cap J) \cong (I + J)/J$$

### Third Isomorphism Theorem

$I \subseteq J \triangleleft R$이면:

$$(R/I)/(J/I) \cong R/J$$

## Prime and Maximal Ideals^[소 아이디얼과 극대 아이디얼]

Commutative ring $R$ (with identity $1 \neq 0$)에 대해:

### Prime Ideal^[소 아이디얼]

Ideal $P \triangleleft R$ (with $P \neq R$)이 **prime**^[소]이다 $\Leftrightarrow$

$$ab \in P \Rightarrow a \in P \text{ or } b \in P$$

**동등 조건**: $R/P$가 integral domain

### Maximal Ideal^[극대 아이디얼]

Ideal $M \triangleleft R$ (with $M \neq R$)이 **maximal**^[극대]이다 $\Leftrightarrow$

$$M \subsetneq I \triangleleft R \Rightarrow I = R$$

즉, $M$보다 큰 proper ideal이 없음

**동등 조건**: $R/M$이 field^[체]

### 관계

$$\text{Maximal ideal} \Rightarrow \text{Prime ideal}$$

(역은 일반적으로 성립 안 함)

---

# <span class="header-examples">Examples of Ideals</span>

## Example 1: Principal Ideals^[주 아이디얼]

$a \in R$에 대해, **principal ideal**^[주 아이디얼] $(a)$:

$$(a) = Ra = \{ra : r \in R\}$$

**예**: $\mathbb{Z}$에서 $(n) = n\mathbb{Z}$

## Example 2: $\mathbb{Z}$의 Ideals

$\mathbb{Z}$의 모든 ideal은 principal:

$$I \triangleleft \mathbb{Z} \Rightarrow I = (n) \text{ for some } n \geq 0$$

**Prime ideals**: $(p)$ where $p$ is prime (+ $(0)$)

**Maximal ideals**: $(p)$ where $p$ is prime

## Example 3: $\mathbb{Z}/6\mathbb{Z}$의 Ideals

- $(0) = \{\overline{0}\}$
- $(2) = \{\overline{0}, \overline{2}, \overline{4}\}$
- $(3) = \{\overline{0}, \overline{3}\}$
- $(1) = \mathbb{Z}/6\mathbb{Z}$

**Prime ideals**: $(2)$, $(3)$

**Maximal ideals**: $(2)$, $(3)$

## Example 4: Polynomial Ring

$$\mathbb{R}[x]$$

- **Prime ideals**: $(0)$, $(f)$ where $f$ is irreducible
- **Maximal ideals**: $(x-a)$ for $a \in \mathbb{R}$

**예**: $(x^2+1)$는 $\mathbb{R}[x]$에서 maximal ($\mathbb{R}[x]/(x^2+1) \cong \mathbb{C}$)

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Ring**: "덧셈과 곱셈이 있는 구조"

- **덧셈**: 항상 "좋은" 구조 (abelian group)
- **곱셈**: 약한 구조 (결합법칙만, 역원 없어도 됨)
- **분배법칙**: 두 연산을 연결

**핵심**: 다항식과 정수를 일반화한 개념

## Group vs Ring

| | **Group** | **Ring** |
|---|---|---|
| 연산 개수 | 1개 | 2개 |
| 역원 | 모든 원소 | 덧셈만 |
| 교환법칙 | 선택적 | 덧셈은 필수 |
| 예시 | $(\mathbb{Z}, +)$ | $\mathbb{Z}$ |

## Ring vs Field

**Field**^[체]는 ring의 특수한 경우:
- Commutative ring
- With identity $1 \neq 0$
- 모든 nonzero 원소가 unit

자세한 내용은 [[Field]] 참조

## 표기법

| 표기 | 의미 |
|------|------|
| $R^\times$ | Group of units |
| $I \triangleleft R$ | $I$ is an ideal of $R$ |
| $(a)$ | Principal ideal generated by $a$ |
| $R/I$ | Quotient ring |
| $\text{char}(R)$ | Characteristic |

## 역사적 배경

**19세기 발전**:
- **Richard Dedekind**: Ideal 개념 도입
- **David Hilbert**: Commutative algebra 발전
- **Emmy Noether**: 추상적 ring theory 확립

**Noetherian Ring**: Emmy Noether의 이름을 딴 중요한 ring 클래스

## 응용

**수론**:
- $\mathbb{Z}$의 ideal theory
- Algebraic number theory^[대수적 수론]

**대수기하학**:
- Polynomial ring과 variety의 관계
- Ideal과 geometric object의 대응

**암호학**:
- RSA: $\mathbb{Z}/n\mathbb{Z}$의 구조 이용
- Lattice-based cryptography

**물리학**:
- Quantum mechanics: Operator algebra
- Gauge theory

## Common Pitfall^[흔한 실수]

### 1. Ring = Field?

✗ Ring은 나눗셈이 일반적으로 안 됨!
- $\mathbb{Z}$: ring but not field
- $\mathbb{Q}$: field (and ring)

### 2. Unit = Invertible?

 맞음! Unit은 곱셈 역원을 가진 원소

**주의**: Additive inverse는 모든 원소가 가짐

### 3. Ideal = Subring?

✗ Ideal이 더 강한 조건
- Ideal: $rI \subseteq I$ for all $r \in R$
- Subring: 단지 ring 구조만 보존

**반례**: $\mathbb{Z} \subseteq \mathbb{Q}$는 subring이지만 ideal 아님

### 4. Prime ideal = Generated by prime?

✗ 일반적으로 다름

**맞는 경우**: $\mathbb{Z}$에서는 일치 ($(p)$ where $p$ prime)

**안 맞는 경우**: $\mathbb{Z}[x]$에서 $(x)$는 prime이지만 $x$는 정수 의미의 prime 아님

### 5. $\text{char}(R/I) = \text{char}(R)$?

✗ 일반적으로 다름

**반례**: $\text{char}(\mathbb{Z}) = 0$ but $\text{char}(\mathbb{Z}/n\mathbb{Z}) = n$

