# <span class="header-prerequisite">Prerequisite</span>
- [[Field]]
- [[Group]]
- [[Quotient Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Lang, Algebra
- Stewart, Galois Theory

---

# <span class="header-definition">Definition</span>

## Galois Extension^[갈루아 확대]

Field extension^[체 확대] $\mathbb{F}/K$가 **Galois extension^[갈루아 확대]**이다 $\Leftrightarrow$ 다음을 만족:

1. **Normal^[정규]**: 모든 irreducible polynomial^[기약 다항식] $p(x) \in K[x]$가 $\mathbb{F}$에서 한 개의 근을 가지면, 모든 근을 가짐
2. **Separable^[분리가능]**: 모든 $\alpha \in \mathbb{F}$의 minimal polynomial^[최소 다항식]이 중근을 갖지 않음

### 동등 조건

Finite extension^[유한 확대] $\mathbb{F}/K$에 대해 다음은 동등:

1. $\mathbb{F}/K$는 Galois extension
2. $\mathbb{F}$는 어떤 separable polynomial의 splitting field^[분해체]
3. $|\text{Aut}(\mathbb{F}/K)| = [\mathbb{F} : K]$
4. $K = \mathbb{F}^{\text{Aut}(\mathbb{F}/K)}$ (fixed field^[고정체])

**주의**: Characteristic 0에서는 모든 polynomial이 separable이므로 normal만 확인하면 됨

## Galois Group^[갈루아 군]

Galois extension $\mathbb{F}/K$의 **Galois group^[갈루아 군]** $\text{Gal}(\mathbb{F}/K)$:

$$\text{Gal}(\mathbb{F}/K) = \{\sigma: \mathbb{F} \to \mathbb{F} : \sigma \text{ is automorphism}, \sigma|_K = \text{id}_K\}$$

즉, $K$를 pointwise로 고정하는 $\mathbb{F}$의 모든 automorphism^[자기동형사상]의 집합

**연산**: Function composition^[함수 합성]

**성질**: $\text{Gal}(\mathbb{F}/K)$는 group (군 공리 만족)

**위수**: $|\text{Gal}(\mathbb{F}/K)| = [\mathbb{F} : K]$

## Normal Extension^[정규 확대]

Field extension $\mathbb{F}/K$가 **normal^[정규]**이다 $\Leftrightarrow$ 다음 중 하나:

1. 모든 irreducible $p(x) \in K[x]$가 $\mathbb{F}$에서 한 근을 가지면, 완전히 분해됨 (splits completely)
2. $\mathbb{F}$는 어떤 polynomial들의 집합의 splitting field
3. 모든 $K$-embedding $\sigma: \mathbb{F} \to \overline{K}$에 대해 $\sigma(\mathbb{F}) = \mathbb{F}$

**직관**: $\mathbb{F}$가 다항식의 "모든 근"을 포함

## Separable Extension^[분리가능 확대]

### Separable Polynomial^[분리가능 다항식]

Polynomial $p(x) \in K[x]$가 **separable^[분리가능]**이다 $\Leftrightarrow$ 모든 irreducible factor가 중근을 갖지 않음

**동등 조건**: $\gcd(p(x), p'(x)) = 1$ (where $p'$ is derivative^[도함수])

### Separable Element^[분리가능 원소]

$\alpha \in \mathbb{F}$가 **separable over $K$^[K 위에서 분리가능]**이다 $\Leftrightarrow$ $\alpha$의 minimal polynomial이 separable

### Separable Extension^[분리가능 확대]

Extension $\mathbb{F}/K$가 **separable^[분리가능]**이다 $\Leftrightarrow$ 모든 $\alpha \in \mathbb{F}$가 separable over $K$

**중요**: Characteristic 0 field (e.g., $\mathbb{Q}, \mathbb{R}, \mathbb{C}$)에서는 모든 extension이 separable

**문제 발생**: Characteristic $p > 0$에서만 inseparable extension 존재 가능

## Splitting Field^[분해체]

Polynomial $p(x) \in K[x]$의 **splitting field^[분해체]** $\mathbb{F}$:

1. $p(x)$가 $\mathbb{F}$에서 완전히 linear factor로 분해
2. $\mathbb{F} = K(\alpha_1, \ldots, \alpha_n)$ where $\alpha_i$는 $p(x)$의 모든 근
3. 이 성질을 만족하는 최소 field

**유일성**: Splitting field는 isomorphism을 제외하고 유일

**예**: $x^2 + 1 \in \mathbb{R}[x]$의 splitting field는 $\mathbb{C} = \mathbb{R}(i)$

## Fixed Field^[고정체]

Subgroup $H \leq \text{Gal}(\mathbb{F}/K)$의 **fixed field^[고정체]** $\mathbb{F}^H$:

$$\mathbb{F}^H = \{\alpha \in \mathbb{F} : \sigma(\alpha) = \alpha \; \forall \sigma \in H\}$$

$H$의 모든 원소에 의해 고정되는 $\mathbb{F}$의 원소들

**성질**: $\mathbb{F}^H$는 $K$와 $\mathbb{F}$ 사이의 subfield

---

# <span class="header-theorem">Theorem</span>

## Fundamental Theorem of Galois Theory^[갈루아 이론의 기본 정리]

Galois extension $\mathbb{F}/K$ (finite)에 대해:

### Main Correspondence^[주 대응]

다음 사이에 **일대일 대응**:

$$\{\text{Subfields } E : K \subseteq E \subseteq \mathbb{F}\} \leftrightarrow \{\text{Subgroups } H \leq \text{Gal}(\mathbb{F}/K)\}$$

**대응 함수**:
- Forward: $E \mapsto \text{Gal}(\mathbb{F}/E)$
- Backward: $H \mapsto \mathbb{F}^H$

**역순 관계**: 
- $E_1 \subseteq E_2 \Leftrightarrow \text{Gal}(\mathbb{F}/E_1) \supseteq \text{Gal}(\mathbb{F}/E_2)$

### Properties of Correspondence^[대응의 성질]

1. **Degree formula^[차수 공식]**: 
$$[E : K] = [\text{Gal}(\mathbb{F}/K) : \text{Gal}(\mathbb{F}/E)] = \frac{|\text{Gal}(\mathbb{F}/K)|}{|\text{Gal}(\mathbb{F}/E)|}$$

2. **Normal subextension^[정규 부분확대]**:
$$E/K \text{ is normal (Galois)} \Leftrightarrow \text{Gal}(\mathbb{F}/E) \triangleleft \text{Gal}(\mathbb{F}/K)$$

3. **Quotient isomorphism^[몫 동형]**: $E/K$가 Galois이면
$$\text{Gal}(E/K) \cong \text{Gal}(\mathbb{F}/K) / \text{Gal}(\mathbb{F}/E)$$

4. **Cardinality^[크기]**:
$$|\text{Gal}(\mathbb{F}/K)| = [\mathbb{F} : K]$$

### Diagram^[도표]

```
         F
        / \
       /   \
  Gal(F/E)  \
     /       \
    E    <->  H = Gal(F/E)
     \       /
      \     /
   Gal(F/K)
        \ /
         K
```

## Primitive Element Theorem^[원시 원소 정리]

Finite separable extension^[유한 분리가능 확대] $\mathbb{F}/K$에 대해:

$$\exists \alpha \in \mathbb{F}, \quad \mathbb{F} = K(\alpha)$$

즉, **단일 원소**로 전체 extension을 생성 가능

$\alpha$를 **primitive element^[원시 원소]**라 함

**중요**: Finite field 위에서는 항상 성립 (모든 extension이 separable)

**반례** (inseparable case): Characteristic $p$에서 $\mathbb{F}_p(t)[x]/(x^p - t)$

## Fundamental Theorem of Algebra^[대수학의 기본 정리]

$$\mathbb{C} \text{ is algebraically closed}$$

모든 non-constant polynomial $p(x) \in \mathbb{C}[x]$는 $\mathbb{C}$에서 근을 가짐

**결과**: $\overline{\mathbb{C}} = \mathbb{C}$ (자기 자신이 algebraic closure)

**Galois theory 관점**: $\mathbb{C}/\mathbb{R}$는 Galois extension
$$\text{Gal}(\mathbb{C}/\mathbb{R}) \cong C_2 = \{1, \sigma\}$$
where $\sigma$ is complex conjugation^[복소 켤레]: $\sigma(a+bi) = a-bi$

## Solvability by Radicals^[근의 공식]

Polynomial $p(x) \in K[x]$가 **solvable by radicals^[근호로 풀 수 있음]**이다 $\Leftrightarrow$ 

근들을 $K$의 원소들로부터 $+, -, \times, \div$와 $n$-th roots만 사용하여 표현 가능

### Galois Criterion^[갈루아 판정법]

$p(x)$가 solvable by radicals $\Leftrightarrow$ splitting field의 Galois group이 **solvable group^[가해군]**

**Solvable group**: Subnormal series^[정규 부분열]
$$\{e\} = G_0 \triangleleft G_1 \triangleleft \cdots \triangleleft G_n = G$$
where each $G_{i+1}/G_i$는 abelian^[아벨]

### Abel-Ruffini Theorem^[아벨-루피니 정리]

**일반 5차 이상 방정식은 근의 공식이 없음**

$$\text{General polynomial of degree } n \geq 5 \text{ is not solvable by radicals}$$

**이유**: $S_n$ (symmetric group)은 $n \geq 5$일 때 not solvable
- $A_n$ (alternating group)은 $n \geq 5$일 때 simple and non-abelian

**주의**: 특정 5차 방정식은 풀 수 있음 (e.g., $x^5 - 1 = 0$)

---

# <span class="header-examples">Examples</span>

## Example 1: Quadratic Extensions^[2차 확대]

$$\mathbb{Q}(\sqrt{2}) / \mathbb{Q}$$

**Minimal polynomial**: $x^2 - 2$

**Basis**: $\{1, \sqrt{2}\}$

**Galois group**: $\text{Gal}(\mathbb{Q}(\sqrt{2})/\mathbb{Q}) \cong C_2$

**Automorphisms**:
- $\text{id}: \sqrt{2} \mapsto \sqrt{2}$
- $\sigma: \sqrt{2} \mapsto -\sqrt{2}$

**Structure**:
$$\begin{array}{c}
\mathbb{Q}(\sqrt{2}) \\
| \\
\mathbb{Q}
\end{array}
\quad \leftrightarrow \quad
\begin{array}{c}
\{e\} \\
| \\
C_2
\end{array}$$

## Example 2: Cyclotomic Extensions^[원분 확대]

$$\mathbb{Q}(\zeta_n) / \mathbb{Q}$$ where $\zeta_n = e^{2\pi i/n}$

**Cyclotomic polynomial^[원분 다항식]**: $\Phi_n(x) = \displaystyle\prod_{\substack{1 \leq k \leq n \\ \gcd(k,n)=1}} (x - \zeta_n^k)$

**Degree**: $[\mathbb{Q}(\zeta_n) : \mathbb{Q}] = \phi(n)$ (Euler's totient function^[오일러 파이 함수])

**Galois group**: 
$$\text{Gal}(\mathbb{Q}(\zeta_n)/\mathbb{Q}) \cong (\mathbb{Z}/n\mathbb{Z})^\times$$

**Automorphisms**: $\sigma_k: \zeta_n \mapsto \zeta_n^k$ for $\gcd(k,n) = 1$

**예**: $n = 5$
- $\phi(5) = 4$
- $\text{Gal}(\mathbb{Q}(\zeta_5)/\mathbb{Q}) \cong (\mathbb{Z}/5\mathbb{Z})^\times \cong C_4$

## Example 3: Biquadratic Extension^[이중 2차 확대]

$$\mathbb{Q}(\sqrt{2}, \sqrt{3}) / \mathbb{Q}$$

**Degree**: $[\mathbb{Q}(\sqrt{2}, \sqrt{3}) : \mathbb{Q}] = 4$

**Basis**: $\{1, \sqrt{2}, \sqrt{3}, \sqrt{6}\}$

**Galois group**: $\text{Gal}(\mathbb{Q}(\sqrt{2}, \sqrt{3})/\mathbb{Q}) \cong C_2 \times C_2$ (Klein four-group)

**Automorphisms**:
- $e$: identity
- $\sigma: \sqrt{2} \mapsto -\sqrt{2}, \sqrt{3} \mapsto \sqrt{3}$
- $\tau: \sqrt{2} \mapsto \sqrt{2}, \sqrt{3} \mapsto -\sqrt{3}$
- $\sigma\tau: \sqrt{2} \mapsto -\sqrt{2}, \sqrt{3} \mapsto -\sqrt{3}$

**Subfield lattice**:

```
      Q(√2, √3)
      /   |   \
     /    |    \
Q(√2)  Q(√3)  Q(√6)
     \    |    /
      \   |   /
         Q
```

**Corresponding subgroups**:

```
        {e}
       / | \
      /  |  \
  <σ>  <τ>  <στ>
      \  |  /
       \ | /
    C₂ × C₂
```

## Example 4: Cubic Extension^[3차 확대]

$$p(x) = x^3 - 2 \in \mathbb{Q}[x]$$

**Roots**: $\sqrt[3]{2}, \omega\sqrt[3]{2}, \omega^2\sqrt[3]{2}$ where $\omega = e^{2\pi i/3}$

**Splitting field**: $\mathbb{F} = \mathbb{Q}(\sqrt[3]{2}, \omega)$

**Degree**: $[\mathbb{F} : \mathbb{Q}] = 6$

**Galois group**: $\text{Gal}(\mathbb{F}/\mathbb{Q}) \cong S_3$ (symmetric group)

**Structure**:
- $\mathbb{Q}(\sqrt[3]{2})/\mathbb{Q}$: Not Galois (not normal)
- $\mathbb{Q}(\omega)/\mathbb{Q}$: Galois, $\text{Gal}(\mathbb{Q}(\omega)/\mathbb{Q}) \cong C_2$

## Example 5: Finite Fields^[유한체]

$$\mathbb{F}_{p^n} / \mathbb{F}_p$$

**Galois extension**: 항상 Galois (모든 finite field extension은 Galois)

**Galois group**: Cyclic of order $n$
$$\text{Gal}(\mathbb{F}_{p^n}/\mathbb{F}_p) \cong C_n$$

**Generator**: Frobenius automorphism^[프로베니우스 자기동형사상]
$$\text{Frob}: x \mapsto x^p$$

**예**: $\mathbb{F}_4 = \mathbb{F}_2(\alpha)$ where $\alpha^2 + \alpha + 1 = 0$
- $\text{Gal}(\mathbb{F}_4/\mathbb{F}_2) = \{\text{id}, \text{Frob}\}$
- $\text{Frob}(\alpha) = \alpha^2 = \alpha + 1$

## Example 6: Not Galois Extension^[비갈루아 확대]

$$\mathbb{Q}(\sqrt[3]{2}) / \mathbb{Q}$$

**Not normal**: $x^3 - 2$가 한 근 $\sqrt[3]{2}$를 포함하지만 $\omega\sqrt[3]{2}$ 불포함

**Automorphisms**: $\text{Aut}(\mathbb{Q}(\sqrt[3]{2})/\mathbb{Q}) = \{\text{id}\}$

**Degree**: $[\mathbb{Q}(\sqrt[3]{2}) : \mathbb{Q}] = 3$

**Not Galois**: $|\text{Aut}(\mathbb{Q}(\sqrt[3]{2})/\mathbb{Q})| = 1 \neq 3 = [\mathbb{Q}(\sqrt[3]{2}) : \mathbb{Q}]$

## Example 7: Inseparable Extension^[비분리가능 확대]

Characteristic $p$에서:

$$K = \mathbb{F}_p(t), \quad \mathbb{F} = K(\alpha) \text{ where } \alpha^p = t$$

**Minimal polynomial**: $x^p - t = (x - \alpha)^p$ (in characteristic $p$)

**Not separable**: 중근 가짐

**Not Galois**: $\text{Aut}(\mathbb{F}/K) = \{\text{id}\}$ but $[\mathbb{F} : K] = p$

---

# <span class="header-properties">Properties</span>

## Galois Closure^[갈루아 폐포]

모든 extension $\mathbb{F}/K$에 대해 **Galois closure^[갈루아 폐포]** $\widetilde{\mathbb{F}}$ 존재:
- $\mathbb{F} \subseteq \widetilde{\mathbb{F}}$
- $\widetilde{\mathbb{F}}/K$는 Galois
- 최소성: 이 성질을 만족하는 최소 field

**구성**: $\widetilde{\mathbb{F}}$는 $\mathbb{F}$를 생성하는 원소들의 minimal polynomial들의 splitting field

## Tower of Galois Extensions^[갈루아 확대의 탑]

$$K \subseteq E \subseteq \mathbb{F}$$

### Case 1: $\mathbb{F}/K$ Galois

$\mathbb{F}/E$는 항상 Galois

$E/K$ Galois $\Leftrightarrow$ $\text{Gal}(\mathbb{F}/E) \triangleleft \text{Gal}(\mathbb{F}/K)$

### Case 2: $\mathbb{F}/E$ and $E/K$ Galois

$\mathbb{F}/K$가 Galois인 것은 **아님** (일반적으로)

**추가 조건 필요**: Normal + Separable을 각각 확인

## Compositum^[합성체]

Extensions $\mathbb{F}_1/K$, $\mathbb{F}_2/K$에 대해 **compositum^[합성체]** $\mathbb{F}_1 \mathbb{F}_2$:

$K$를 포함하는 가장 작은 field containing both $\mathbb{F}_1$ and $\mathbb{F}_2$

### Galois Compositum^[갈루아 합성]

$\mathbb{F}_1/K$, $\mathbb{F}_2/K$ 모두 Galois이면 $\mathbb{F}_1\mathbb{F}_2/K$도 Galois

**Galois group**: 
$$\text{Gal}(\mathbb{F}_1\mathbb{F}_2/K) \cong \frac{\text{Gal}(\mathbb{F}_1/K) \times \text{Gal}(\mathbb{F}_2/K)}{\text{Gal}(\mathbb{F}_1 \cap \mathbb{F}_2/K)}$$

(if $\mathbb{F}_1 \cap \mathbb{F}_2$ Galois over $K$)

## Discriminant^[판별식]

Polynomial $p(x) = \displaystyle\prod_{i=1}^n (x - \alpha_i) \in K[x]$의 **discriminant^[판별식]**:

$$\Delta(p) = \prod_{i < j} (\alpha_i - \alpha_j)^2$$

**성질**:
1. $\Delta(p) \in K$ (symmetric polynomial이므로)
2. $\Delta(p) = 0 \Leftrightarrow$ $p$가 중근을 가짐
3. $\sqrt{\Delta(p)} \in K \Leftrightarrow$ Galois group $\subseteq A_n$

**예**: Quadratic $ax^2 + bx + c$
$$\Delta = b^2 - 4ac$$

## Resolvent^[분해식]

Galois group을 결정하는 도구

Polynomial $p(x)$에 대해 특정 형태의 **resolvent polynomial^[분해식]** 구성

**Cubic resolvent**: 4차 방정식의 Galois group 판정에 사용

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Galois Theory**: "대칭성과 체의 구조 사이의 다리"

**핵심 아이디어**:
- **Field extensions** $\leftrightarrow$ **Symmetry groups**
- 방정식의 근들의 대칭성이 체 구조를 결정
- 군론적 성질 (solvability)이 대수적 풀이 가능성 결정

**메타포**: 
- Subfield = "보이는 것"
- Galois group = "대칭성"
- 더 많은 대칭 = 더 작은 subfield

## 역사적 배경

**Évariste Galois** (1811-1832):
- 20세에 이론 완성
- 21세에 결투로 사망
- 논문이 사후 14년 뒤 출판

**동기**: 5차 방정식의 일반 근의 공식 불가능성 증명

**영향**:
- 군론의 탄생
- 현대 대수학의 기초
- 대칭성 개념의 수학적 형식화

## Galois Theory의 응용

### 1. 작도 가능성^[Ruler and Compass Constructions]

Constructible numbers^[작도 가능 수]: $\mathbb{Q}$에서 시작하여 $+, -, \times, \div, \sqrt{\phantom{x}}$로 얻을 수 있는 수

**결과**: $\alpha$ constructible $\Leftrightarrow$ $[\mathbb{Q}(\alpha) : \mathbb{Q}] = 2^n$

**고대 그리스 문제 해결**:
- ✗ **각의 3등분**: $[\mathbb{Q}(\cos 20°) : \mathbb{Q}] = 3 \neq 2^n$
- ✗ **정육면체의 배적**: $[\mathbb{Q}(\sqrt[3]{2}) : \mathbb{Q}] = 3$
- ✗ **원적**: $\pi$ is transcendental

**가능**: 정 $n$각형 작도 $\Leftrightarrow$ $\phi(n) = 2^k$ $\Leftrightarrow$ $n = 2^k p_1 \cdots p_r$ (Fermat primes)

### 2. 대수방정식의 풀이

**1-4차**: 근의 공식 존재 (Galois group이 solvable)
- 1차: Linear
- 2차: Quadratic formula
- 3차: Cardano's formula
- 4차: Ferrari's formula

**5차 이상**: 일반적으로 근의 공식 없음 (Abel-Ruffini)

**특수한 경우**: 풀 수 있음
- $x^n - 1 = 0$: Cyclotomic
- $x^5 - x - 1 = 0$: Solvable by radicals

### 3. 수론

**Class field theory^[유체론]**: Abelian Galois extensions 분류

**Fermat's Last Theorem**: Galois representations 사용

**Iwasawa theory**: $\mathbb{Z}_p$-extensions의 Galois theory

### 4. 암호학

**Pairing-based cryptography**: Galois field extensions 사용

**Post-quantum cryptography**: Galois group actions

## Galois vs Non-Galois

| | **Galois** | **Non-Galois** |
|---|---|---|
| Normal | Yes | No (usually) |
| Separable | Yes | Maybe |
| $\|\text{Aut}\|$ | $= [\mathbb{F} : K]$ | $< [\mathbb{F} : K]$ |
| 예시 | $\mathbb{Q}(\sqrt{2})$ | $\mathbb{Q}(\sqrt[3]{2})$ |

## 표기법

| 표기 | 의미 |
|------|------|
| $\text{Gal}(\mathbb{F}/K)$ | Galois group |
| $\mathbb{F}^H$ | Fixed field of $H$ |
| $[\mathbb{F} : K]$ | Degree of extension |
| $\mathbb{F}/K$ | Extension (not quotient!) |
| $\zeta_n$ | Primitive $n$-th root of unity |

## Common Pitfall^[흔한 실수]

### 1. Normal = Galois?

✗ Normal + Separable = Galois

**반례** (characteristic $p$): Normal but not separable extension 존재

### 2. $|\text{Gal}(\mathbb{F}/K)| \leq [\mathbb{F} : K]$?

✓ 항상 성립! 

등호 $\Leftrightarrow$ Galois extension

### 3. Tower of Galois?

✗ $\mathbb{F}/E$ Galois + $E/K$ Galois $\not\Rightarrow$ $\mathbb{F}/K$ Galois

**반례**: $\mathbb{F}_4/\mathbb{F}_2$, $\mathbb{F}_2/\mathbb{F}_2$ (both Galois trivially)

### 4. Splitting field = Normal extension?

✓ Splitting field는 **항상 normal** (definition by)

### 5. All subfields correspond to subgroups?

✗ Galois extension에서만!

Non-Galois extension에서는 대응 성립 안 함

## 현대적 발전

**Inverse Galois Problem**: 모든 finite group이 어떤 field의 Galois group인가?

- 해결됨: Symmetric groups, Alternating groups
- 미해결: 일반적인 경우

**Differential Galois Theory**: ODE의 해에 대한 Galois theory

**Model-theoretic Galois Theory**: 논리학과 연결

## 추가 학습 주제

**기초**:
- Polynomial rings and irreducibility
- Finite fields
- Symmetric and alternating groups

**중급**:
- Kummer theory
- Artin-Schreier theory
- Profinite groups

**고급**:
- Étale cohomology
- Grothendieck's Galois theory
- Motivic Galois groups

