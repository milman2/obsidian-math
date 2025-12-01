# <span class="header-prerequisite">Prerequisite</span>
- [[Field]]
- [[Polynomial Ring]]
- [[Vector Space]]
- [[Homomorphism]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Lang, Algebra
- Stewart, Galois Theory

---

# <span class="header-definition">Definition</span>

## Field Extension^[체 확대]

Field $K$와 $F$에 대해, $K \subseteq F$일 때 $F$를 $K$의 **extension field^[확대체]** (또는 **field extension^[체 확대]**)라 한다.

**표기**: 
- $F/K$ 
- $K \subseteq F$

**주의**: $F/K$는 quotient가 **아님**! Extension을 나타내는 표기법

**용어**:
- $F$: **Extension field^[확대체]** (또는 **overfield^[상위체]**)
- $K$: **Base field^[기저체]** (또는 **ground field^[바탕체]**)

## Vector Space Structure^[벡터 공간 구조]

Field extension $F/K$는 자연스럽게 $K$-vector space^[벡터 공간] 구조를 가진다:

**스칼라곱**: $a \in K$, $\alpha \in F$에 대해 $a \cdot \alpha \in F$

**벡터 덧셈**: $F$의 덧셈

## Degree of Extension^[확대 차수]

$$[F : K] = \dim_K F$$

$F$를 $K$-vector space로 볼 때의 차원^[dimension]

**분류**:
- **Finite extension^[유한 확대]**: $[F : K] < \infty$
- **Infinite extension^[무한 확대]**: $[F : K] = \infty$

## Simple Extension^[단순 확대]

### Single Element Adjunction^[단일 원소 첨가]

$K \subseteq F$이고 $\alpha \in F$일 때:

$$K(\alpha) = \text{smallest subfield of } F \text{ containing } K \text{ and } \alpha$$

**표기**: "$K$ adjoining $\alpha$" 또는 "$K$에 $\alpha$를 첨가"

### Simple Extension

Extension $F/K$가 **simple extension^[단순 확대]**이다 $\Leftrightarrow$ 어떤 $\alpha \in F$에 대해:

$$F = K(\alpha)$$

$\alpha$를 **primitive element^[원시 원소]**라 함

## Finitely Generated Extension^[유한 생성 확대]

$$F = K(\alpha_1, \alpha_2, \ldots, \alpha_n)$$

유한 개의 원소를 첨가하여 생성된 extension

**Tower**:
$$K \subseteq K(\alpha_1) \subseteq K(\alpha_1, \alpha_2) \subseteq \cdots \subseteq K(\alpha_1, \ldots, \alpha_n)$$

## Algebraic Element^[대수적 원소]

$F/K$ (field extension)와 $\alpha \in F$에 대해:

### Algebraic

$\alpha$가 **algebraic over $K$^[K 위에서 대수적]**이다 $\Leftrightarrow$

$$\exists p(x) \in K[x] \setminus \{0\}, \quad p(\alpha) = 0$$

즉, $\alpha$가 $K$ 계수 다항식의 근

### Transcendental

$\alpha$가 **transcendental over $K$^[K 위에서 초월적]**이다 $\Leftrightarrow$ $\alpha$가 algebraic이 아님

**예**:
- $\sqrt{2}$ is algebraic over $\mathbb{Q}$ (satisfies $x^2 - 2 = 0$)
- $\pi$ is transcendental over $\mathbb{Q}$
- $e$ is transcendental over $\mathbb{Q}$

## Minimal Polynomial^[최소 다항식]

$\alpha$가 algebraic over $K$일 때, **minimal polynomial^[최소 다항식]** $m_{\alpha, K}(x) \in K[x]$:

**유일한** monic^[최고계수가 1] irreducible polynomial^[기약 다항식] such that $m_{\alpha, K}(\alpha) = 0$

**성질**:
1. Monic: leading coefficient = 1
2. Irreducible over $K$
3. $p(\alpha) = 0$ $\Rightarrow$ $m_{\alpha, K}(x) \mid p(x)$
4. Degree = $[K(\alpha) : K]$

**표기**: $m_{\alpha, K}(x)$ 또는 간단히 $m_\alpha(x)$

## Algebraic Extension^[대수 확대]

Extension $F/K$가 **algebraic^[대수적]**이다 $\Leftrightarrow$

$$\forall \alpha \in F, \; \alpha \text{ is algebraic over } K$$

**반대**: **Transcendental extension^[초월 확대]**

## Splitting Field^[분해체]

Polynomial $p(x) \in K[x]$의 **splitting field^[분해체]** $F$:

1. $p(x)$가 $F[x]$에서 완전히 linear factor^[일차 인수]로 분해:
   $$p(x) = c(x - \alpha_1)(x - \alpha_2) \cdots (x - \alpha_n)$$

2. $F = K(\alpha_1, \alpha_2, \ldots, \alpha_n)$ (최소성)

**유일성**: Splitting field는 $K$-isomorphism을 제외하고 유일

**예**: 
- $x^2 + 1 \in \mathbb{R}[x]$의 splitting field: $\mathbb{C} = \mathbb{R}(i)$
- $x^3 - 2 \in \mathbb{Q}[x]$의 splitting field: $\mathbb{Q}(\sqrt[3]{2}, \omega)$ where $\omega = e^{2\pi i/3}$

## Normal Extension^[정규 확대]

Extension $F/K$가 **normal^[정규]**이다 $\Leftrightarrow$ 다음 동등 조건 중 하나:

1. 모든 irreducible $p(x) \in K[x]$가 $F$에서 한 근을 가지면, 완전히 분해됨

2. $F$는 어떤 polynomial 집합의 splitting field

3. 모든 $K$-embedding $\sigma: F \to \overline{K}$에 대해 $\sigma(F) = F$

**직관**: "다항식의 모든 근을 포함"

## Separable Extension^[분리가능 확대]

### Separable Polynomial^[분리가능 다항식]

Polynomial $p(x) \in K[x]$가 **separable^[분리가능]**이다 $\Leftrightarrow$ 모든 irreducible factor가 중근^[repeated root]을 갖지 않음

**동등 조건**: $\gcd(p(x), p'(x)) = 1$ (where $p'$ is formal derivative^[형식적 도함수])

### Separable Element^[분리가능 원소]

$\alpha \in F$가 **separable over $K$**^[K 위에서 분리가능]이다 $\Leftrightarrow$ minimal polynomial $m_{\alpha, K}(x)$가 separable

### Separable Extension^[분리가능 확대]

Extension $F/K$가 **separable^[분리가능]**이다 $\Leftrightarrow$ 모든 $\alpha \in F$가 separable over $K$

**중요**: 
- Characteristic 0 field (e.g., $\mathbb{Q}, \mathbb{R}, \mathbb{C}$): **모든 extension이 separable**
- Characteristic $p > 0$: Inseparable extension 존재 가능

---

# <span class="header-theorem">Theorems</span>

## Tower Law^[탑 법칙]

**정리** (**Tower Law** 또는 **Multiplicativity of Degree**):

$$K \subseteq E \subseteq F \Rightarrow [F : K] = [F : E][E : K]$$

**증명 개요**:
- $\{e_1, \ldots, e_m\}$: $E$의 $K$-basis
- $\{f_1, \ldots, f_n\}$: $F$의 $E$-basis
- $\{e_i f_j : 1 \leq i \leq m, 1 \leq j \leq n\}$: $F$의 $K$-basis (크기 $mn$)

**따름정리**: Finite extension의 tower는 finite

$$[E : K] < \infty, \, [F : E] < \infty \Rightarrow [F : K] < \infty$$

## Structure of Simple Extensions^[단순 확대의 구조]

### Case 1: Algebraic

$\alpha$ algebraic over $K$, $\deg(m_\alpha) = n$

$$K(\alpha) \cong K[x]/(m_\alpha(x))$$

**Basis**: $\{1, \alpha, \alpha^2, \ldots, \alpha^{n-1}\}$

**Degree**: $[K(\alpha) : K] = n = \deg(m_\alpha)$

**원소 표현**: $a_0 + a_1\alpha + \cdots + a_{n-1}\alpha^{n-1}$ where $a_i \in K$

### Case 2: Transcendental

$\alpha$ transcendental over $K$

$$K(\alpha) \cong K(x) = \text{field of rational functions}$$

**Degree**: $[K(\alpha) : K] = \infty$

**원소 표현**: $\frac{p(\alpha)}{q(\alpha)}$ where $p, q \in K[x]$, $q \neq 0$

## Finite Extensions are Algebraic^[유한 확대는 대수적]

**정리**: $[F : K] < \infty$ $\Rightarrow$ $F/K$ is algebraic

**증명**: $\alpha \in F$에 대해, $\{1, \alpha, \alpha^2, \ldots, \alpha^n\}$는 linearly dependent (for large enough $n$)

따라서 $\exists a_0, \ldots, a_n \in K$ (not all zero) such that:

$$a_0 + a_1\alpha + \cdots + a_n\alpha^n = 0$$

즉, $\alpha$는 algebraic 
**주의**: 역은 성립하지 않음! Algebraic이어도 infinite extension 가능

**반례**: $\overline{\mathbb{Q}}/\mathbb{Q}$ (algebraic closure는 algebraic이지만 infinite)

## Primitive Element Theorem^[원시 원소 정리]

**정리** (**Primitive Element Theorem**):

Finite separable extension^[유한 분리가능 확대] $F/K$에 대해:

$$\exists \alpha \in F, \quad F = K(\alpha)$$

즉, **단일 원소**로 전체 extension 생성 가능

**조건**:
- Characteristic 0: **항상 성립** (모든 extension이 separable)
- Finite field: **항상 성립** (multiplicative group이 cyclic)
- Infinite field of characteristic $p$: Separability 필요

**구성적 증명**: $F = K(\alpha, \beta)$일 때, $\gamma = \alpha + c\beta$ for appropriate $c \in K$

## Algebraic Closure Existence^[대수적 폐포의 존재성]

**정리**: 모든 field $K$는 **algebraic closure^[대수적 폐포]** $\overline{K}$를 가진다:

1. $K \subseteq \overline{K}$
2. $\overline{K}$는 algebraically closed^[대수적으로 닫힘]: 모든 polynomial $p(x) \in \overline{K}[x]$가 $\overline{K}$에서 근을 가짐
3. $\overline{K}/K$는 algebraic extension
4. $K$-isomorphism을 제외하고 유일

**예**:
- $\overline{\mathbb{Q}} \subseteq \mathbb{C}$ (algebraic numbers)
- $\overline{\mathbb{R}} = \mathbb{C}$
- $\overline{\mathbb{F}_p}$ (infinite field)

## Theorem on Algebraic Extensions^[대수 확대에 관한 정리]

**정리**: $E/K$ algebraic, $F/E$ algebraic $\Rightarrow$ $F/K$ algebraic

**증명**: $\alpha \in F$에 대해, $\alpha$는 algebraic over $E$

Minimal polynomial의 계수들은 $E$에 속하고, 각각 algebraic over $K$

따라서 $K$에 이 계수들을 첨가하면 finite extension

Tower law 적용하여 $[K(\alpha) : K] < \infty$

따라서 $\alpha$는 algebraic over $K$ 
## Existence of Splitting Fields^[분해체의 존재성]

**정리**: 모든 non-constant polynomial $p(x) \in K[x]$는 splitting field를 가진다

**구성**:
1. $p(x)$의 irreducible factor $f(x)$ 선택
2. $K_1 = K[x]/(f(x))$ 구성 ($f$의 근 $\alpha_1$ 포함)
3. $p(x) = (x - \alpha_1)q(x)$ in $K_1[x]$
4. $q(x)$에 대해 반복
5. 모든 근을 포함할 때까지 계속

**Degree**: $[(\text{splitting field}) : K] \leq n!$ where $\deg(p) = n$

---

# <span class="header-examples">Examples</span>

## Example 1: Quadratic Extensions^[2차 확대]

$$\mathbb{Q}(\sqrt{d}) / \mathbb{Q}$$ where $d \in \mathbb{Z}$, $d$ not a perfect square

**Degree**: $[\mathbb{Q}(\sqrt{d}) : \mathbb{Q}] = 2$

**Basis**: $\{1, \sqrt{d}\}$

**Minimal polynomial**: $m_{\sqrt{d}}(x) = x^2 - d$

**원소**: $a + b\sqrt{d}$ where $a, b \in \mathbb{Q}$

**연산**:
- $(a + b\sqrt{d}) + (c + e\sqrt{d}) = (a+c) + (b+e)\sqrt{d}$
- $(a + b\sqrt{d})(c + e\sqrt{d}) = (ac + bde) + (ae + bc)\sqrt{d}$

**예시**:
- $\mathbb{Q}(\sqrt{2})$
- $\mathbb{Q}(\sqrt{-1}) = \mathbb{Q}(i)$ (Gaussian rationals^[가우스 유리수])
- $\mathbb{Q}(\sqrt{3})$

## Example 2: Cyclotomic Extensions^[원분 확대]

$$\mathbb{Q}(\zeta_n) / \mathbb{Q}$$ where $\zeta_n = e^{2\pi i/n}$ (primitive $n$-th root of unity^[원시 n차 단위근])

**Degree**: $[\mathbb{Q}(\zeta_n) : \mathbb{Q}] = \phi(n)$ (Euler totient function^[오일러 파이 함수])

**Minimal polynomial**: Cyclotomic polynomial^[원분 다항식] $\Phi_n(x)$

$$\Phi_n(x) = \prod_{\substack{1 \leq k \leq n \\ \gcd(k,n)=1}} (x - \zeta_n^k)$$

**예시**:
- $n = 2$: $\Phi_2(x) = x + 1$, $[\mathbb{Q}(\zeta_2) : \mathbb{Q}] = 1$
- $n = 3$: $\Phi_3(x) = x^2 + x + 1$, $[\mathbb{Q}(\zeta_3) : \mathbb{Q}] = 2$
- $n = 4$: $\Phi_4(x) = x^2 + 1$, $[\mathbb{Q}(\zeta_4) : \mathbb{Q}] = 2$
- $n = 5$: $\Phi_5(x) = x^4 + x^3 + x^2 + x + 1$, $[\mathbb{Q}(\zeta_5) : \mathbb{Q}] = 4$

## Example 3: Finite Field Extensions^[유한체 확대]

$$\mathbb{F}_{p^n} / \mathbb{F}_p$$

**Degree**: $[\mathbb{F}_{p^n} : \mathbb{F}_p] = n$

**Order**: $|\mathbb{F}_{p^n}| = p^n$

**Structure**: $\mathbb{F}_{p^n} \cong \mathbb{F}_p[x]/(f(x))$ where $f$ is irreducible of degree $n$

**예시**: $\mathbb{F}_4 = \mathbb{F}_2(\alpha)$ where $\alpha^2 + \alpha + 1 = 0$
- Elements: $\{0, 1, \alpha, \alpha+1\}$
- $[\mathbb{F}_4 : \mathbb{F}_2] = 2$

**Subfield lattice**: $\mathbb{F}_{p^m} \subseteq \mathbb{F}_{p^n} \Leftrightarrow m \mid n$

## Example 4: Cubic Extension^[3차 확대]

$$\mathbb{Q}(\sqrt[3]{2}) / \mathbb{Q}$$

**Degree**: $[\mathbb{Q}(\sqrt[3]{2}) : \mathbb{Q}] = 3$

**Basis**: $\{1, \sqrt[3]{2}, \sqrt[3]{4}\}$

**Minimal polynomial**: $m_{\sqrt[3]{2}}(x) = x^3 - 2$

**Not normal**: $x^3 - 2$의 다른 근 $\omega\sqrt[3]{2}$, $\omega^2\sqrt[3]{2}$ (where $\omega = e^{2\pi i/3}$) 불포함

**Splitting field**: $\mathbb{Q}(\sqrt[3]{2}, \omega)$
- $[\mathbb{Q}(\sqrt[3]{2}, \omega) : \mathbb{Q}] = 6$

## Example 5: Transcendental Extension^[초월 확대]

$$\mathbb{Q}(x) / \mathbb{Q}$$ (rational functions^[유리 함수])

**Degree**: $[\mathbb{Q}(x) : \mathbb{Q}] = \infty$

**원소**: $\frac{p(x)}{q(x)}$ where $p, q \in \mathbb{Q}[x]$, $q \neq 0$

**Structure**: $\mathbb{Q}(x)$ is the field of fractions of $\mathbb{Q}[x]$

**Multiple variables**: $\mathbb{Q}(x, y) / \mathbb{Q}$
- $[\mathbb{Q}(x, y) : \mathbb{Q}] = \infty$
- Transcendence degree^[초월 차수] = 2

## Example 6: Real Numbers over Rationals^[실수의 유리수 확대]

$$\mathbb{R} / \mathbb{Q}$$

**Degree**: $[\mathbb{R} : \mathbb{Q}] = 2^{\aleph_0}$ (uncountable!)

**Not finitely generated**: 유한 개의 원소로 생성 불가

**Transcendental**: 대부분의 실수는 $\mathbb{Q}$ 위에서 초월적
- $\overline{\mathbb{Q}}$ (algebraic numbers)는 countable
- $\mathbb{R}$는 uncountable
- 따라서 "거의 모든" 실수는 transcendental

## Example 7: Complex over Real^[복소수의 실수 확대]

$$\mathbb{C} / \mathbb{R}$$

**Degree**: $[\mathbb{C} : \mathbb{R}] = 2$

**Basis**: $\{1, i\}$

**Minimal polynomial**: $m_i(x) = x^2 + 1$

**Algebraically closed**: $\overline{\mathbb{C}} = \mathbb{C}$

**Fundamental Theorem of Algebra**: 모든 non-constant polynomial $p(x) \in \mathbb{C}[x]$가 $\mathbb{C}$에서 근을 가짐

## Example 8: Multiple Quadratic Extensions^[다중 2차 확대]

$$\mathbb{Q}(\sqrt{2}, \sqrt{3}) / \mathbb{Q}$$

**Tower**:
$$\mathbb{Q} \subseteq \mathbb{Q}(\sqrt{2}) \subseteq \mathbb{Q}(\sqrt{2}, \sqrt{3})$$

**Degrees**:
- $[\mathbb{Q}(\sqrt{2}) : \mathbb{Q}] = 2$
- $[\mathbb{Q}(\sqrt{2}, \sqrt{3}) : \mathbb{Q}(\sqrt{2})] = 2$ (since $\sqrt{3} \notin \mathbb{Q}(\sqrt{2})$)
- Tower law: $[\mathbb{Q}(\sqrt{2}, \sqrt{3}) : \mathbb{Q}] = 2 \times 2 = 4$

**Basis**: $\{1, \sqrt{2}, \sqrt{3}, \sqrt{6}\}$

**Primitive element**: $\sqrt{2} + \sqrt{3}$
$$\mathbb{Q}(\sqrt{2}, \sqrt{3}) = \mathbb{Q}(\sqrt{2} + \sqrt{3})$$

---

# <span class="header-properties">Properties</span>

## Compositum^[합성체]

Extensions $F_1/K$, $F_2/K$ (in some larger field)에 대해:

**Compositum^[합성체]** $F_1F_2$:

$$F_1F_2 = K(F_1 \cup F_2)$$

$K$를 포함하는 가장 작은 field containing both $F_1$ and $F_2$

### Degree Formula

$$[F_1F_2 : K] = \frac{[F_1 : K][F_2 : K]}{[F_1 \cap F_2 : K]}$$

(when well-defined)

### Algebraic Compositum

$F_1/K$, $F_2/K$ 모두 algebraic $\Rightarrow$ $F_1F_2/K$ algebraic

## Algebraically Independent Elements^[대수적 독립 원소]

Elements $\{\alpha_1, \ldots, \alpha_n\} \subseteq F$가 **algebraically independent over $K$^[K 위에서 대수적 독립]**이다 $\Leftrightarrow$

$$p(\alpha_1, \ldots, \alpha_n) = 0 \text{ for } p \in K[x_1, \ldots, x_n] \Rightarrow p = 0$$

**예**:
- $\pi, e$ are algebraically independent over $\mathbb{Q}$ (conjectured, not proven!)
- $x, y$ are algebraically independent in $\mathbb{Q}(x, y)$

## Transcendence Degree^[초월 차수]

Extension $F/K$의 **transcendence degree^[초월 차수]** $\text{tr.deg}(F/K)$:

$$\text{tr.deg}(F/K) = \text{maximal size of algebraically independent subset}$$

**성질**:
- $\text{tr.deg}(F/K) = 0 \Leftrightarrow F/K$ is algebraic
- $\text{tr.deg}(K(x_1, \ldots, x_n)/K) = n$
- Well-defined (모든 maximal set이 같은 크기)

## Intermediate Fields^[중간체]

$$K \subseteq E \subseteq F$$

$E$를 **intermediate field^[중간체]**라 함

### Lattice Structure^[격자 구조]

Intermediate fields는 lattice^[격자] 구조:
- Meet: $E_1 \cap E_2$
- Join: $E_1 E_2$ (compositum)

### Correspondence (Galois Theory)

Galois extension에서 intermediate fields $\leftrightarrow$ subgroups of Galois group

자세한 내용은 [[Galois Theory]] 참조

## Norm and Trace^[노름과 대각합]

Finite extension $F/K$, $\alpha \in F$에 대해:

### Norm^[노름]

$$N_{F/K}(\alpha) = \det(m_\alpha) \in K$$

where $m_\alpha: F \to F$, $m_\alpha(x) = \alpha x$ (multiplication map)

**Multiplicative**: $N(\alpha\beta) = N(\alpha)N(\beta)$

### Trace^[대각합]

$$\text{Tr}_{F/K}(\alpha) = \text{trace}(m_\alpha) \in K$$

**Additive**: $\text{Tr}(\alpha + \beta) = \text{Tr}(\alpha) + \text{Tr}(\beta)$

**예**: $\mathbb{Q}(\sqrt{d})/\mathbb{Q}$에서 $\alpha = a + b\sqrt{d}$
- $N(\alpha) = a^2 - db^2$
- $\text{Tr}(\alpha) = 2a$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Field Extension**: "더 큰 수 체계로 확장"

**동기**:
- 방정식의 해를 포함하도록 확장
- 예: $x^2 + 1 = 0$은 $\mathbb{R}$에서 해가 없음 → $\mathbb{C}$로 확장

**Vector Space 관점**: Extension field는 base field 위의 벡터 공간

**Geometric interpretation**: Degree = "차원"

## 표기법 주의

### $F/K$ vs $F \div K$

**$F/K$**: Field extension (NOT quotient!)

**혼동 주의**: Ring의 quotient $R/I$와 다른 의미

### $K(\alpha)$ vs $K[\alpha]$

**$K(\alpha)$**: Field generated by $\alpha$

**$K[\alpha]$**: Ring generated by $\alpha$

**관계**:
- $\alpha$ algebraic: $K[\alpha] = K(\alpha)$ (field!)
- $\alpha$ transcendental: $K[\alpha] \subsetneq K(\alpha)$
  - $K[\alpha] \cong K[x]$ (polynomial ring)
  - $K(\alpha) \cong K(x)$ (field of rational functions)

## Algebraic vs Finite

**항상 성립**: Finite $\Rightarrow$ Algebraic

**역은 거짓**: Algebraic $\not\Rightarrow$ Finite

**반례**: $\overline{\mathbb{Q}}/\mathbb{Q}$
- Algebraic: Yes (모든 원소가 algebraic by definition)
- Finite: No ($[\overline{\mathbb{Q}} : \mathbb{Q}] = \infty$)

**이유**: $\overline{\mathbb{Q}}$는 모든 차수의 algebraic numbers 포함

## Separability Issues^[분리가능성 문제]

**Characteristic 0**: 모든 extension이 separable → 걱정 없음

**Characteristic $p > 0**: Inseparable extension 가능

**예** (inseparable): $\mathbb{F}_p(t)[x]/(x^p - t)$
- $x^p - t = (x - \alpha)^p$ in characteristic $p$
- 중근을 가짐

**실용적**: 대부분의 경우 characteristic 0이므로 separability 자동

## 역사적 배경

**고대**: 작도 문제 (자와 컴퍼스)
- 각의 3등분
- 정육면체 배적
- 원적 문제

**16세기**: 3차, 4차 방정식의 근의 공식 (Cardano, Ferrari)

**19세기**: 
- **Galois**: 5차 이상 방정식의 일반 근의 공식 불가능 증명
- Field extension theory의 탄생

**현대**: 
- Algebraic geometry
- Number theory
- Cryptography

## 응용 분야

### 1. Galois Theory^[갈루아 이론]

Field extension + Group theory = Galois theory

방정식의 풀이 가능성 판정

자세한 내용은 [[Galois Theory]] 참조

### 2. Algebraic Number Theory^[대수적 정수론]

Number fields: finite extensions of $\mathbb{Q}$

**예**: $\mathbb{Q}(\sqrt{-5})$, cyclotomic fields

**응용**: Fermat's Last Theorem, class field theory

### 3. Algebraic Geometry^[대수기하학]

Function fields: transcendental extensions

**예**: $K(X)$ where $X$ is algebraic variety

**Connection**: Geometry $\leftrightarrow$ Algebra

### 4. Coding Theory^[부호 이론]

Finite field extensions for error-correcting codes

**예**: Reed-Solomon codes, BCH codes

### 5. Cryptography^[암호학]

**Elliptic curves**: over finite field extensions

**Pairing-based crypto**: uses extension fields

**AES**: operations in $\mathbb{F}_{2^8}$

### 6. Constructibility^[작도 가능성]

Constructible with ruler and compass $\Leftrightarrow$ degree is power of 2

**해결된 고대 문제**:
- ✗ 각의 3등분: $[\mathbb{Q}(\cos 20°) : \mathbb{Q}] = 3$
- ✗ 정육면체 배적: $[\mathbb{Q}(\sqrt[3]{2}) : \mathbb{Q}] = 3$
- ✗ 원적: $\pi$ is transcendental

## Common Pitfalls^[흔한 실수]

### 1. $F/K$ is NOT quotient!

✗ $F/K \neq F \div K$

Field extension 표기법일 뿐

### 2. $K[\alpha] \neq K(\alpha)$ (일반적으로)

 $\alpha$ algebraic: $K[\alpha] = K(\alpha)$

✗ $\alpha$ transcendental: $K[\alpha] \subsetneq K(\alpha)$

### 3. Algebraic = Finite?

✗ Algebraic $\not\Rightarrow$ Finite

 Finite $\Rightarrow$ Algebraic

### 4. $[F : K] = |F|/|K|$?

✗ Degree $\neq$ Cardinality ratio

Degree = Vector space dimension

**예외**: Finite fields
$$|\mathbb{F}_{p^n}| = p^n = |\mathbb{F}_p|^{[\mathbb{F}_{p^n} : \mathbb{F}_p]}$$

### 5. Tower Law 순서

✗ $[F : K] = [E : K][F : E]$ (wrong order!)

 $[F : K] = [F : E][E : K]$ (correct order!)

"위에서 중간" × "중간에서 아래"

## 추가 학습 주제

**기본 개념**:
- [[Field]]: Field의 기본 정의와 성질
- [[Polynomial Ring]]: 다항식환과 기약 다항식
- [[Vector Space]]: 벡터 공간 이론

**고급 주제**:
- [[Galois Theory]]: Galois extension과 fundamental theorem
- [[Finite Fields]]: 유한체 이론
- [[Algebraic Closure]]: 대수적 폐포

**응용**:
- [[Constructibility]]: 작도 가능성 이론
- [[Algebraic Number Theory]]: 대수적 정수론
- [[Algebraic Geometry]]: 대수기하학

## 관련 개념

- [[Field]]: Base concept
- [[Galois Theory]]: Galois extensions and symmetry
- [[Polynomial Ring]]: Construction via quotients
- [[Vector Space]]: Extension as vector space
- [[Homomorphism]]: Field homomorphisms and embeddings
- [[Splitting Field]]: Detailed study
- [[Finite Fields]]: Finite field extensions

