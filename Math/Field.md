# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Lang, Algebra

---

# <span class="header-definition">Definition</span>

## Field^[체]

집합 $\mathbb{F}$와 두 이항 연산 $+$, $\cdot$에 대해, $(\mathbb{F}, +, \cdot)$가 **field**^[체]이다 $\Leftrightarrow$ 다음을 만족:

### 1. Commutative Ring^[가환환]

$\mathbb{F}$는 commutative ring with identity $1 \neq 0$

### 2. Multiplicative Inverses^[곱셈 역원]

$$\forall a \in \mathbb{F} \setminus \{0\}, \; \exists a^{-1} \in \mathbb{F}, \quad a \cdot a^{-1} = 1$$

즉, (Ring의 특수한 경우) 0이 아닌 모든 원소가 곱셈 역원을 가짐

### 동등한 정의

Field $\mathbb{F}$ $\Leftrightarrow$ 다음을 만족:

1. $(\mathbb{F}, +)$는 abelian group^[아벨군] (identity: $0$)
2. $(\mathbb{F}^\times, \cdot)$는 abelian group^[아벨군] (identity: $1$), where $\mathbb{F}^\times = \mathbb{F} \setminus \{0\}$
3. Distributive law^[분배법칙]: $a(b+c) = ab + ac$

**직관**: "사칙연산이 모두 가능한 구조"

## Subfield^[부분체]

$K \subseteq \mathbb{F}$가 **subfield**^[부분체]이다 $\Leftrightarrow$ $K$가 $\mathbb{F}$의 연산으로 field

**표기**: $K \subseteq \mathbb{F}$ 또는 $\mathbb{F}/K$ (field extension^[체 확대])

### Subfield Test

$K \subseteq \mathbb{F}$ $\Leftrightarrow$ 다음을 만족:
1. $0, 1 \in K$
2. $a, b \in K \Rightarrow a - b \in K$
3. $a, b \in K, b \neq 0 \Rightarrow ab^{-1} \in K$

## Prime Field^[소체]

Field $\mathbb{F}$의 **prime field**^[소체]: $\mathbb{F}$의 가장 작은 subfield

**정리**: 모든 field는 유일한 prime field를 포함

Prime field는 다음 중 하나:
- $\mathbb{Q}$ (characteristic 0)
- $\mathbb{F}_p = \mathbb{Z}/p\mathbb{Z}$ (characteristic $p$, prime)

## Field Extension^[체 확대]

$K \subseteq \mathbb{F}$일 때, $\mathbb{F}$를 $K$의 **extension field**^[확대체]라 함

**표기**: $\mathbb{F}/K$ (field extension)

**주의**: Quotient가 아님! ($\mathbb{F}/K$는 $\mathbb{F}$ divided by $K$가 아님)

### Degree of Extension^[확대 차수]

$$[\mathbb{F} : K] = \dim_K \mathbb{F}$$

$\mathbb{F}$를 $K$-vector space로 볼 때의 차원

**분류**:
- **Finite extension**^[유한 확대]: $[\mathbb{F} : K] < \infty$
- **Infinite extension**^[무한 확대]: $[\mathbb{F} : K] = \infty$

### Tower Law^[탑 법칙]

$$K \subseteq E \subseteq \mathbb{F} \Rightarrow [\mathbb{F} : K] = [\mathbb{F} : E][E : K]$$

## Algebraic and Transcendental Elements^[대수적 원소와 초월 원소]

$\mathbb{F}/K$ (field extension)와 $\alpha \in \mathbb{F}$에 대해:

### Algebraic Element^[대수적 원소]

$\alpha$가 **algebraic over $K$**^[K 위에서 대수적]이다 $\Leftrightarrow$

$$\exists p(x) \in K[x] \setminus \{0\}, \quad p(\alpha) = 0$$

즉, $\alpha$가 $K$ 계수 다항식의 근

### Transcendental Element^[초월 원소]

$\alpha$가 **transcendental over $K$**^[K 위에서 초월적]이다 $\Leftrightarrow$ $\alpha$가 algebraic이 아님

**예**:
- $\sqrt{2}$ is algebraic over $\mathbb{Q}$ (근: $x^2 - 2 = 0$)
- $\pi$ is transcendental over $\mathbb{Q}$
- $e$ is transcendental over $\mathbb{Q}$

### Minimal Polynomial^[최소 다항식]

$\alpha$가 algebraic over $K$일 때, **minimal polynomial**^[최소 다항식] $m_{\alpha, K}(x)$:

- Monic^[최고 계수가 1]
- $m_{\alpha, K}(\alpha) = 0$
- Irreducible over $K$^[K 위에서 기약]
- 최소 차수

**유일성**: 이 조건을 만족하는 다항식은 유일

## Algebraic Extension^[대수 확대]

Field extension $\mathbb{F}/K$가 **algebraic**^[대수적]이다 $\Leftrightarrow$

$$\forall \alpha \in \mathbb{F}, \; \alpha \text{ is algebraic over } K$$

**정리**: Finite extension은 algebraic
$$[\mathbb{F} : K] < \infty \Rightarrow \mathbb{F}/K \text{ is algebraic}$$

(역은 일반적으로 성립 안 함)

## Field Homomorphism^[체 준동형사상]

함수 $\phi: \mathbb{F} \to \mathbb{E}$ (where $\mathbb{F}, \mathbb{E}$ are fields)가 **field homomorphism**^[체 준동형사상]이다 $\Leftrightarrow$ ring homomorphism

**중요 성질**: 모든 field homomorphism은 injective^[단사]!

**증명**: $\ker(\phi)$는 ideal of $\mathbb{F}$
- Field의 ideal은 $(0)$ 또는 $\mathbb{F}$뿐
- $\phi(1) = 1 \neq 0$이므로 $\ker(\phi) \neq \mathbb{F}$
- 따라서 $\ker(\phi) = (0)$ 
**결과**: Field homomorphism은 injective 또는 trivial (zero map은 homomorphism 아님)

---

# <span class="header-examples">Examples</span>

## Example 1: 유리수

$$\mathbb{Q} = \left\{\frac{a}{b} : a, b \in \mathbb{Z}, b \neq 0\right\}$$

- **Characteristic**: $\text{char}(\mathbb{Q}) = 0$
- **Prime field**: $\mathbb{Q}$ 자신
- 가장 작은 characteristic 0 field

## Example 2: 실수와 복소수

$$\mathbb{R} \subseteq \mathbb{C}$$

- $[\mathbb{C} : \mathbb{R}] = 2$ (basis: $\{1, i\}$)
- $i$ is algebraic over $\mathbb{R}$ (minimal polynomial: $x^2 + 1$)
- $\text{char}(\mathbb{R}) = \text{char}(\mathbb{C}) = 0$

## Example 3: Finite Fields^[유한체]

$$\mathbb{F}_p = \mathbb{Z}/p\mathbb{Z}$$ where $p$ is prime

- **Order**: $|\mathbb{F}_p| = p$
- **Characteristic**: $\text{char}(\mathbb{F}_p) = p$
- **Prime field**: $\mathbb{F}_p$ 자신

**일반 유한체**: $\mathbb{F}_{p^n}$ (order $p^n$)
- 존재: 모든 prime power $p^n$에 대해 유일
- Extension: $\mathbb{F}_{p^n}/\mathbb{F}_p$ with $[\mathbb{F}_{p^n} : \mathbb{F}_p] = n$

## Example 4: Quadratic Extensions^[2차 확대]

$$\mathbb{Q}(\sqrt{d}) = \{a + b\sqrt{d} : a, b \in \mathbb{Q}\}$$ where $d$ is not a perfect square

- $[\mathbb{Q}(\sqrt{d}) : \mathbb{Q}] = 2$
- Basis: $\{1, \sqrt{d}\}$
- $\sqrt{d}$의 minimal polynomial: $x^2 - d$

**예**:
- $\mathbb{Q}(\sqrt{2}) = \{a + b\sqrt{2} : a, b \in \mathbb{Q}\}$
- $\mathbb{Q}(i) = \{a + bi : a, b \in \mathbb{Q}\}$ (Gaussian rationals^[가우스 유리수])

## Example 5: Algebraic Closure^[대수적 폐포]

$$\overline{\mathbb{Q}} = \{\alpha \in \mathbb{C} : \alpha \text{ is algebraic over } \mathbb{Q}\}$$

모든 대수적 수의 집합

**성질**:
- Algebraically closed: 모든 다항식이 근을 가짐
- $[\overline{\mathbb{Q}} : \mathbb{Q}] = \infty$
- Countable: $|\overline{\mathbb{Q}}| = \aleph_0$

## Example 6: Function Fields^[함수체]

$$\mathbb{F}(x) = \left\{\frac{f(x)}{g(x)} : f, g \in \mathbb{F}[x], g \neq 0\right\}$$

Field of rational functions^[유리 함수체]

**예**: $\mathbb{Q}(x)$
- $x$ is transcendental over $\mathbb{Q}$
- $[\mathbb{Q}(x) : \mathbb{Q}] = \infty$

## Example 7: Splitting Field^[분해체]

$p(x) = x^2 + 1 \in \mathbb{R}[x]$

**Splitting field**: $\mathbb{C}$ (smallest field containing all roots)

$$x^2 + 1 = (x-i)(x+i) \in \mathbb{C}[x]$$

## Example 8: $p$-adic Numbers^[p진수]

$$\mathbb{Q}_p = \text{completion of } \mathbb{Q} \text{ with respect to } p\text{-adic norm}$$

- **Characteristic**: 0
- 비아르키메데스적 (non-archimedean)
- 수론에서 중요

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. No Zero Divisors^[영인자 없음]

Field는 integral domain^[정역]

$$ab = 0 \Rightarrow a = 0 \text{ or } b = 0$$

### 2. Cancellation Law^[소거법칙]

$$ac = bc \text{ and } c \neq 0 \Rightarrow a = b$$

### 3. No Proper Ideals^[고유 아이디얼 없음]

Field $\mathbb{F}$의 ideal은 $(0)$과 $\mathbb{F}$뿐

**증명**: $I \triangleleft \mathbb{F}$이고 $I \neq (0)$이면
- $\exists a \in I, a \neq 0$
- $a^{-1} \in \mathbb{F}$
- $1 = a \cdot a^{-1} \in I$ (ideal 성질)
- $\forall b \in \mathbb{F}, \; b = b \cdot 1 \in I$
- 따라서 $I = \mathbb{F}$ 
### 4. Field Homomorphisms are Injective

앞서 정의 섹션에서 증명

## Characteristic^[표수]

Field $\mathbb{F}$의 characteristic는 0 또는 prime

**증명**: Ring의 성질 + Field는 integral domain

$$\text{char}(\mathbb{F}) \in \{0\} \cup \{\text{primes}\}$$

### 표수에 따른 분류

**Characteristic 0**:
- $\mathbb{Q} \subseteq \mathbb{F}$ (prime field)
- "무한한" 구조

**Characteristic $p$ (prime)**:
- $\mathbb{F}_p \subseteq \mathbb{F}$ (prime field)
- $|\mathbb{F}| = p^n$ for some $n$ (finite field의 경우)

## Finite Fields^[유한체]

### Existence and Uniqueness^[존재성과 유일성]

**정리**: 
- 유한체의 위수는 $p^n$ 형태 (where $p$ prime, $n \geq 1$)
- 각 $p^n$에 대해 isomorphism을 제외하고 유일한 field $\mathbb{F}_{p^n}$ 존재

### Structure^[구조]

$$\mathbb{F}_{p^n}^\times \cong C_{p^n - 1}$$

Multiplicative group은 cyclic^[순환]

**Generator**: primitive element^[원시 원소] $\alpha \in \mathbb{F}_{p^n}^\times$

$$\mathbb{F}_{p^n}^\times = \{1, \alpha, \alpha^2, \ldots, \alpha^{p^n-2}\}$$

### Frobenius Endomorphism^[프로베니우스 자기준동형사상]

Characteristic $p$ field $\mathbb{F}$에서:

$$\text{Frob}: \mathbb{F} \to \mathbb{F}, \quad \text{Frob}(x) = x^p$$

**성질**:
1. Field homomorphism ($(x+y)^p = x^p + y^p$ in char $p$)
2. $\mathbb{F}$가 finite $\Rightarrow$ $\text{Frob}$는 automorphism

## Algebraic Extensions^[대수 확대]

### Theorem: Primitive Element^[원시 원소 정리]

Finite extension $\mathbb{F}/K$가 separable^[분리가능]이면:

$$\exists \alpha \in \mathbb{F}, \quad \mathbb{F} = K(\alpha)$$

즉, 단일 원소로 확대 생성 가능

### Algebraic Closure^[대수적 폐포]

모든 field $\mathbb{F}$는 **algebraic closure**^[대수적 폐포] $\overline{\mathbb{F}}$를 가짐:
- $\mathbb{F} \subseteq \overline{\mathbb{F}}$
- $\overline{\mathbb{F}}$는 algebraically closed
- $\overline{\mathbb{F}}/\mathbb{F}$는 algebraic extension
- Isomorphism을 제외하고 유일

**예**:
- $\overline{\mathbb{Q}} \subseteq \mathbb{C}$
- $\overline{\mathbb{R}} = \mathbb{C}$
- $\overline{\mathbb{F}_p}$ (infinite)

## Transcendence Degree^[초월 차수]

Extension $\mathbb{F}/K$의 **transcendence degree**^[초월 차수] $\text{tr.deg}(\mathbb{F}/K)$:

$\mathbb{F}$에서 $K$ 위로 algebraically independent^[대수적 독립]인 원소들의 최대 개수

**예**:
- $\text{tr.deg}(\mathbb{Q}(x) / \mathbb{Q}) = 1$
- $\text{tr.deg}(\mathbb{C} / \mathbb{Q}) = 2^{\aleph_0}$ (uncountable)

---

# <span class="header-theorem">Theorem</span>

## Fundamental Theorem of Galois Theory^[갈루아 이론의 기본 정리]

Galois extension $\mathbb{F}/K$ (finite, normal, separable)에 대해:

### Galois Group^[갈루아 군]

$$\text{Gal}(\mathbb{F}/K) = \{\sigma: \mathbb{F} \to \mathbb{F} : \sigma \text{ is automorphism}, \sigma|_K = \text{id}_K\}$$

### Correspondence^[대응]

다음 사이에 일대일 대응:

$$\{\text{Subfields } E : K \subseteq E \subseteq \mathbb{F}\} \leftrightarrow \{\text{Subgroups } H \leq \text{Gal}(\mathbb{F}/K)\}$$

대응: $E \mapsto \text{Gal}(\mathbb{F}/E)$

역: $H \mapsto \mathbb{F}^H = \{\alpha \in \mathbb{F} : \sigma(\alpha) = \alpha \; \forall \sigma \in H\}$

### Properties

1. $[E : K] = [\text{Gal}(\mathbb{F}/K) : \text{Gal}(\mathbb{F}/E)]$
2. $E/K$ is normal $\Leftrightarrow$ $\text{Gal}(\mathbb{F}/E) \triangleleft \text{Gal}(\mathbb{F}/K)$
3. $|\text{Gal}(\mathbb{F}/K)| = [\mathbb{F} : K]$

## Fundamental Theorem of Algebra^[대수학의 기본 정리]

$$\mathbb{C} \text{ is algebraically closed}$$

즉, 모든 non-constant polynomial $p(x) \in \mathbb{C}[x]$는 $\mathbb{C}$에서 근을 가짐

**결과**: $\overline{\mathbb{C}} = \mathbb{C}$

## Classification of Finite Fields^[유한체의 분류]

Order $q = p^n$ (where $p$ prime)인 모든 finite field는 isomorphic

$$\mathbb{F}_q \cong \mathbb{F}_p[x]/(f(x))$$

where $f(x)$ is irreducible of degree $n$

### Subfield Lattice^[부분체 격자]

$$\mathbb{F}_{p^m} \subseteq \mathbb{F}_{p^n} \Leftrightarrow m \mid n$$

## Cyclotomic Extensions^[원분 확대]

$\zeta_n = e^{2\pi i/n}$ ($n$-th root of unity^[1의 n제곱근])

$$\mathbb{Q}(\zeta_n) / \mathbb{Q}$$

- **Degree**: $[\mathbb{Q}(\zeta_n) : \mathbb{Q}] = \phi(n)$ (Euler's totient function^[오일러 파이 함수])
- **Galois group**: $\text{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q}) \cong (\mathbb{Z}/n\mathbb{Z})^\times$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Field**: "완벽한 산술 구조"

사칙연산 $(+, -, \times, \div)$이 모두 자유롭게 가능 (0으로 나누기 제외)

**계층**:
$$\text{Group} \subset \text{Ring} \subset \text{Integral Domain} \subset \text{Field}$$

각 단계에서 구조가 "더 좋아짐"

## Group vs Ring vs Field

| | **Group** | **Ring** | **Field** |
|---|---|---|---|
| 연산 | 1개 | 2개 | 2개 |
| 역원 | 1개 연산만 | 덧셈만 | 양쪽 다 (0 제외) |
| 예 | $\mathbb{Z}$ (덧셈) | $\mathbb{Z}$ | $\mathbb{Q}$ |

## Field Extensions and Vector Spaces

Field extension $\mathbb{F}/K$ $\Rightarrow$ $\mathbb{F}$는 $K$-vector space

$$[\mathbb{F} : K] = \dim_K \mathbb{F}$$

**예**: $[\mathbb{C} : \mathbb{R}] = 2$
- $\mathbb{C} = \mathbb{R} \oplus \mathbb{R} \cdot i$ (as $\mathbb{R}$-vector space)

이 관점은 Galois theory와 linear algebra를 연결

## 표기법 주의

### $\mathbb{F}/K$ (Field Extension)

**의미**: $K \subseteq \mathbb{F}$ (inclusion)

**주의**: Quotient가 아님!

### $R/I$ (Quotient Ring)

**의미**: Cosets $\{r + I : r \in R\}$

**구별**:
- Field extension: "/는 "over" 의미
- Quotient: "/"는 "modulo" 의미

## 유한체의 응용

**암호학**:
- AES: $\mathbb{F}_{2^8}$ 사용
- Elliptic curve cryptography: $\mathbb{F}_p$ 위의 타원곡선

**코딩 이론**:
- Reed-Solomon codes: $\mathbb{F}_q$ 위에서 정의
- BCH codes

**전산학**:
- CRC (Cyclic Redundancy Check): $\mathbb{F}_2[x]$의 나눗셈

## Galois Theory의 중요성

**역사적 의의**:
- 5차 이상 방정식의 근의 공식 불가능 증명
- 군론의 발전에 핵심 역할

**응용**:
- Ruler and compass constructions^[자와 컴퍼스 작도]
- Impossibility proofs: 각의 3등분, 정육면체의 배적, 원적

## 초월수

**정의**: Transcendental over $\mathbb{Q}$

**알려진 초월수**:
- $\pi$ (Lindemann, 1882)
- $e$ (Hermite, 1873)
- $e^\pi$, $2^\sqrt{2}$ (Gelfond-Schneider theorem)

**미해결**: $\pi + e$, $\pi e$ 등이 초월인지 모름!

**측도론적 사실**: "거의 모든" 실수는 초월수 (대수적 수는 countable, 실수는 uncountable)

## 역사적 배경

**고대**:
- 그리스: 기하학적 수 체계
- 중세: 대수방정식 풀이

**근대**:
- **Évariste Galois** (1811-1832): Galois theory
- **Emmy Noether**: 추상 대수학
- **Emil Artin**: Modern field theory

**현대**:
- Class field theory^[유체론]
- Algebraic geometry^[대수기하학]

## Common Pitfall^[흔한 실수]

### 1. Field = $\mathbb{R}$ or $\mathbb{C}$?

✗ 매우 다양한 field 존재!
- Finite fields: $\mathbb{F}_p$
- $p$-adic fields: $\mathbb{Q}_p$
- Function fields: $\mathbb{F}(x)$

### 2. Subfield vs Ideal

✗ Field에는 proper ideal이 없음!

Subfield $\neq$ Ideal (ring과 다름)

### 3. $[\mathbb{F} : K] = |\mathbb{F}|/|K|$?

✗ Degree는 vector space dimension (위수 나눗셈 아님)

**맞는 경우**: Finite field
$$|\mathbb{F}_{p^n}| = p^n = |\mathbb{F}_p|^n = |\mathbb{F}_p|^{[\mathbb{F}_{p^n} : \mathbb{F}_p]}$$

### 4. Algebraic = Finite extension?

✗ Algebraic extension이 항상 finite은 아님

**반례**: $\overline{\mathbb{Q}}/\mathbb{Q}$
- Algebraic: Yes
- Finite: No ($[\overline{\mathbb{Q}} : \mathbb{Q}] = \infty$)

**맞는 방향**: Finite $\Rightarrow$ Algebraic

### 5. All extensions are Galois?

✗ Galois extension은 특수한 경우 (normal + separable)

**반례**: $\mathbb{Q}(\sqrt[3]{2})/\mathbb{Q}$
- Not normal (doesn't contain $\omega\sqrt[3]{2}$ where $\omega = e^{2\pi i/3}$)
- Not Galois

## 추가 학습 주제

**기초**:
- Polynomial rings: $\mathbb{F}[x]$
- Irreducibility criteria
- Field of fractions

**고급**:
- Galois cohomology
- Class field theory
- Algebraic geometry over fields
- Model theory of fields

