# <span class="header-prerequisite">Prerequisite</span>
- [[Field]]
- [[Extension Field]]
- [[Polynomial Ring]]
- [[Irreducible Polynomial]]
- [[Galois Theory]]
- [[Automorphism]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Stewart, Galois Theory
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Algebraic Conjugate Elements^[대수적 켤레 원소]

Field extension^[체 확대] $F/K$에서, $\alpha, \beta \in F$가 **algebraic conjugates**^[대수적 켤레] over $K$이다 $\Leftrightarrow$

$$\alpha \text{ and } \beta \text{ have the same minimal polynomial over } K$$

즉, $m_{\alpha, K}(x) = m_{\beta, K}(x)$

**직관**: 같은 irreducible polynomial^[기약 다항식]의 서로 다른 근들

### Alternative Definition

$\alpha, \beta$가 algebraic conjugates over $K$ $\Leftrightarrow$

$$\exists K\text{-isomorphism } \sigma: K(\alpha) \to K(\beta) \text{ with } \sigma(\alpha) = \beta$$

## Galois Conjugates^[갈루아 켤레]

Galois extension^[갈루아 확대] $F/K$에서, $\alpha \in F$의 **Galois conjugates**^[갈루아 켤레]:

$$\{\sigma(\alpha) : \sigma \in \text{Gal}(F/K)\}$$

Galois group^[갈루아 군]의 모든 원소에 의한 $\alpha$의 image들

**성질**: 모든 Galois conjugates는 같은 minimal polynomial을 가짐

**개수**: $|\{\sigma(\alpha) : \sigma \in \text{Gal}(F/K)\}| \leq [K(\alpha) : K]$

등호는 $K(\alpha)/K$가 Galois일 때 성립

## Conjugate Fields^[켤레 체]

Field extensions $E_1, E_2$ over $K$가 **conjugate over $K$**^[K 위에서 켤레]이다 $\Leftrightarrow$

$$\exists K\text{-isomorphism } \sigma: E_1 \to E_2$$

**예**: $\mathbb{Q}(\sqrt{2})$와 $\mathbb{Q}(-\sqrt{2})$ (actually same field!)

## Set of All Conjugates^[모든 켤레의 집합]

$\alpha \in \overline{K}$ (algebraic closure^[대수적 폐포])가 $K$ 위에서 algebraic^[대수적]일 때:

**All conjugates of $\alpha$ over $K$**:

$$\text{Conj}_K(\alpha) = \{\beta \in \overline{K} : m_{\beta, K}(x) = m_{\alpha, K}(x)\}$$

= 모든 $\alpha$의 $K$-conjugates

**크기**: $|\text{Conj}_K(\alpha)| = \deg(m_{\alpha, K})$ (separable인 경우)

---

# <span class="header-examples">Examples</span>

## Example 1: Quadratic Conjugates

$$\alpha = \sqrt{2} \in \mathbb{R}$$

**Minimal polynomial** over $\mathbb{Q}$: $m_{\sqrt{2}, \mathbb{Q}}(x) = x^2 - 2$

**Roots**: $\sqrt{2}$, $-\sqrt{2}$

**Conjugates of $\sqrt{2}$**: $\{-\sqrt{2}\}$

**Galois group**: $\text{Gal}(\mathbb{Q}(\sqrt{2})/\mathbb{Q}) = \{\text{id}, \sigma\}$ where $\sigma(\sqrt{2}) = -\sqrt{2}$

## Example 2: Complex Conjugation

$$\alpha = i \in \mathbb{C}$$

**Minimal polynomial** over $\mathbb{R}$: $m_{i, \mathbb{R}}(x) = x^2 + 1$

**Roots**: $i$, $-i$

**Conjugates of $i$**: $\{-i\}$

**Complex conjugation**: $\bar{i} = -i$

**Galois group**: $\text{Gal}(\mathbb{C}/\mathbb{R}) = \{\text{id}, \bar{\phantom{z}}\}$ where $\bar{\phantom{z}}$ is complex conjugation

## Example 3: Cube Root of 2

$$\alpha = \sqrt[3]{2} \in \mathbb{R}$$

**Minimal polynomial** over $\mathbb{Q}$: $m_{\sqrt[3]{2}, \mathbb{Q}}(x) = x^3 - 2$

**Roots in $\mathbb{C}$**: 
- $\sqrt[3]{2}$
- $\omega\sqrt[3]{2}$ where $\omega = e^{2\pi i/3}$
- $\omega^2\sqrt[3]{2}$

**Conjugates of $\sqrt[3]{2}$ over $\mathbb{Q}$**: $\{\omega\sqrt[3]{2}, \omega^2\sqrt[3]{2}\}$

**Note**: $\mathbb{Q}(\sqrt[3]{2})/\mathbb{Q}$는 **NOT Galois** (doesn't contain $\omega$)

**Galois closure**: $\mathbb{Q}(\sqrt[3]{2}, \omega)$

## Example 4: Golden Ratio

$$\phi = \frac{1 + \sqrt{5}}{2}$$

**Minimal polynomial** over $\mathbb{Q}$: $x^2 - x - 1$

**Roots**: 
- $\phi = \frac{1 + \sqrt{5}}{2}$
- $\hat{\phi} = \frac{1 - \sqrt{5}}{2}$ (conjugate golden ratio)

**Conjugate**: $\hat{\phi}$

**Relation**: $\phi + \hat{\phi} = 1$, $\phi \cdot \hat{\phi} = -1$

## Example 5: Primitive Root of Unity

$$\zeta_5 = e^{2\pi i/5}$$

**Minimal polynomial** over $\mathbb{Q}$: $\Phi_5(x) = x^4 + x^3 + x^2 + x + 1$ (cyclotomic polynomial^[원분 다항식])

**Roots**: $\zeta_5, \zeta_5^2, \zeta_5^3, \zeta_5^4$

**Conjugates**: $\{\zeta_5^2, \zeta_5^3, \zeta_5^4\}$

**Galois group**: $\text{Gal}(\mathbb{Q}(\zeta_5)/\mathbb{Q}) \cong (\mathbb{Z}/5\mathbb{Z})^\times \cong C_4$

## Example 6: Non-conjugates

$$\alpha = \sqrt{2}, \quad \beta = \sqrt{3}$$

**Minimal polynomials**:
- $m_{\sqrt{2}, \mathbb{Q}}(x) = x^2 - 2$
- $m_{\sqrt{3}, \mathbb{Q}}(x) = x^2 - 3$

**Different minimal polynomials** → **NOT conjugates**

## Example 7: Galois Conjugates in $\mathbb{F}_4$

Finite field $\mathbb{F}_4 = \mathbb{F}_2(\alpha)$ where $\alpha^2 + \alpha + 1 = 0$

**Elements**: $\{0, 1, \alpha, \alpha + 1\}$

**Galois group**: $\text{Gal}(\mathbb{F}_4/\mathbb{F}_2) = \{\text{id}, \text{Frob}\}$ where $\text{Frob}(x) = x^2$

**Conjugates of $\alpha$**:
- $\text{Frob}(\alpha) = \alpha^2 = \alpha + 1$

**Minimal polynomial**: $x^2 + x + 1$ has roots $\{\alpha, \alpha + 1\}$

자세한 내용은 [[Finite Field]] 참조

## Example 8: Quadratic Field

$$K = \mathbb{Q}(\sqrt{d})$$ where $d$ is square-free

**Automorphisms**: $\text{Aut}(\mathbb{Q}(\sqrt{d})/\mathbb{Q}) = \{\text{id}, \sigma\}$

where $\sigma(a + b\sqrt{d}) = a - b\sqrt{d}$

**Every element's conjugate**:
- Conjugate of $a + b\sqrt{d}$ is $a - b\sqrt{d}$

**Norm**: $N(a + b\sqrt{d}) = (a + b\sqrt{d})(a - b\sqrt{d}) = a^2 - db^2$

**Trace**: $\text{Tr}(a + b\sqrt{d}) = (a + b\sqrt{d}) + (a - b\sqrt{d}) = 2a$

---

# <span class="header-properties">Properties</span>

## Conjugates Share Minimal Polynomial

**정리**: $\alpha, \beta$가 conjugates over $K$ $\Leftrightarrow$ $m_{\alpha, K}(x) = m_{\beta, K}(x)$

**증명**: Definition에 의함

## Number of Conjugates

**정리**: $\alpha$ algebraic over $K$, degree $n = \deg(m_{\alpha, K})$

$$|\text{Conj}_K(\alpha)| = n$$

(separable인 경우, i.e., characteristic 0 or separable polynomial)

**Inseparable case**: $|\text{Conj}_K(\alpha)| < \deg(m_{\alpha, K})$ (중근 존재)

## Conjugates in Splitting Field

**정리**: $\alpha$의 모든 conjugates는 $m_{\alpha, K}(x)$의 splitting field^[분해체]에 존재

**증명**: Splitting field는 $m_{\alpha, K}(x)$의 모든 근을 포함

## Galois Group Acts on Conjugates

**정리**: Galois extension $F/K$, $\alpha \in F$

$$\sigma \in \text{Gal}(F/K) \Rightarrow \sigma(\alpha) \text{ is conjugate of } \alpha$$

**증명**: 
- $m_{\alpha, K}(\alpha) = 0$
- $\sigma(m_{\alpha, K}(\alpha)) = m_{\alpha, K}(\sigma(\alpha)) = 0$ ($\sigma$ fixes $K$)
- 따라서 $\sigma(\alpha)$도 $m_{\alpha, K}$의 근

## Orbit-Stabilizer for Conjugates

**정리**: Galois extension $F/K$, $\alpha \in F$

$$|\text{Gal}(F/K(\alpha))| = \frac{|\text{Gal}(F/K)|}{|\{\sigma(\alpha) : \sigma \in \text{Gal}(F/K)\}|}$$

**Orbit-Stabilizer Theorem** 적용

자세한 내용은 [[Orbit-Stabilizer Theorem]] 참조

## Transitivity of Conjugates

**정리**: Galois extension $F/K$

$\text{Gal}(F/K)$ acts **transitively** on conjugates of $\alpha$ $\Leftrightarrow$ $K(\alpha)/K$ is Galois

**의미**: Galois group이 모든 conjugates를 "섞을 수 있음"

## Symmetric Functions of Conjugates

**정리**: $\alpha_1, \ldots, \alpha_n$이 $\alpha$의 모든 conjugates이면:

Elementary symmetric polynomials^[기본 대칭 다항식]:
- $s_1 = \sum \alpha_i \in K$
- $s_2 = \sum_{i < j} \alpha_i\alpha_j \in K$
- ...
- $s_n = \prod \alpha_i \in K$

**이유**: Vieta's formulas^[비에타 공식] - coefficients of $m_{\alpha, K}(x) \in K[x]$

자세한 내용은 [[Vieta's Formulas]] 참조

## Conjugates Preserve Degree

**정리**: $\alpha, \beta$ conjugates over $K$

$$[K(\alpha) : K] = [K(\beta) : K]$$

**증명**: 같은 minimal polynomial → 같은 degree

## Field Isomorphism

**정리**: $\alpha, \beta$ conjugates over $K$

$$\exists K\text{-isomorphism } \phi: K(\alpha) \to K(\beta) \text{ with } \phi(\alpha) = \beta$$

**증명**:
- $K(\alpha) \cong K[x]/(m_{\alpha, K}(x))$
- $K(\beta) \cong K[x]/(m_{\beta, K}(x))$
- $m_{\alpha, K} = m_{\beta, K}$ → isomorphic quotients

---

# <span class="header-theorem">Theorems</span>

## Fundamental Theorem of Galois Theory (Conjugates Version)

**정리**: Galois extension $F/K$, $\alpha \in F$

$$|\{\sigma(\alpha) : \sigma \in \text{Gal}(F/K)\}| = [K(\alpha) : K]$$

$\Leftrightarrow$ $K(\alpha)/K$ is Galois

## Primitive Element Theorem (Conjugates)

**정리**: Finite separable extension $F/K$

$$\exists \alpha \in F: F = K(\alpha)$$

Such $\alpha$ is called **primitive element**^[원시 원소]

**결과**: $F$의 모든 원소는 $\alpha$의 polynomial로 표현 가능

자세한 내용은 [[Extension Field]] 참조

## Discriminant and Conjugates

**정리**: $\alpha_1, \ldots, \alpha_n$이 $\alpha$의 모든 conjugates

**Discriminant**^[판별식]:

$$\Delta = \prod_{i < j} (\alpha_i - \alpha_j)^2 \in K$$

**성질**:
- $\Delta \neq 0 \Leftrightarrow$ separable (no repeated roots)
- $\Delta$ is square in $K \Leftrightarrow$ Galois group $\subseteq A_n$

## Norm and Trace

**정리**: $\alpha \in F$, $F/K$ finite separable, degree $n$

**Norm**^[노름]:
$$N_{F/K}(\alpha) = \prod_{\sigma \in \text{Gal}(\overline{K}/K)} \sigma(\alpha) = \prod_{i=1}^{n/[K(\alpha):K]} \alpha_i^{[K(\alpha):K]}$$

**Trace**^[대각합]:
$$\text{Tr}_{F/K}(\alpha) = \sum_{\sigma \in \text{Gal}(\overline{K}/K)} \sigma(\alpha) = \frac{n}{[K(\alpha):K]} \sum_{i=1}^{n/[K(\alpha):K]} \alpha_i$$

where $\alpha_1, \ldots, \alpha_m$ are distinct conjugates

**성질**:
- $N_{F/K}(\alpha) \in K$
- $\text{Tr}_{F/K}(\alpha) \in K$
- Multiplicative: $N_{F/K}(\alpha\beta) = N_{F/K}(\alpha)N_{F/K}(\beta)$
- Additive: $\text{Tr}_{F/K}(\alpha + \beta) = \text{Tr}_{F/K}(\alpha) + \text{Tr}_{F/K}(\beta)$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Algebraic conjugates = "같은 방정식의 서로 다른 해"**

**핵심 아이디어**:
- Minimal polynomial = defining equation
- Conjugates = all solutions to that equation
- Galois group = symmetries permuting solutions

**기하학적**:
- Polynomial의 근들 = 대칭적 위치
- Galois group = 근들의 permutation symmetries

## Complex Conjugation vs Algebraic Conjugation

| Aspect | Complex Conjugation | Algebraic Conjugation |
|--------|---------------------|----------------------|
| **Definition** | $\overline{a+bi} = a-bi$ | Same minimal polynomial |
| **Field** | $\mathbb{C}/\mathbb{R}$ | General $F/K$ |
| **Uniqueness** | One conjugate | Multiple conjugates possible |
| **Example** | $\bar{3+4i} = 3-4i$ | Conjugates of $\sqrt[3]{2}$: $\{\omega\sqrt[3]{2}, \omega^2\sqrt[3]{2}\}$ |

**Relation**: Complex conjugation은 algebraic conjugation의 특수한 경우!

## 응용 분야

### 1. Number Theory^[정수론]

**Algebraic number theory**: Conjugates of algebraic integers

**Norm and ideal**: $N(\alpha) = \prod \text{conjugates}$

**Class field theory**: Conjugacy classes in Galois groups

### 2. Galois Theory^[갈루아 이론]

**Fundamental Theorem**: Conjugates ↔ Galois group orbits

**Solvability**: Galois group actions on roots

**Resolvent equations**: Symmetric functions of conjugates

### 3. Coding Theory^[부호 이론]

**Minimal polynomials**: Error-correcting codes

**Conjugate pairs**: BCH codes over finite fields

### 4. Algebraic Geometry^[대수기하학]

**Varieties**: Conjugate points on varieties

**Automorphism groups**: Action on points

### 5. Cryptography^[암호학]

**Elliptic curves**: Frobenius action on points

**Pairing-based crypto**: Trace maps

## Computing Conjugates

### Method 1: Factor Minimal Polynomial

**Step 1**: Find $m_{\alpha, K}(x)$

**Step 2**: Factor $m_{\alpha, K}(x)$ in splitting field

**Step 3**: All roots are conjugates

### Method 2: Apply Galois Group

**Step 1**: Find $\text{Gal}(F/K)$

**Step 2**: Apply each $\sigma \in \text{Gal}(F/K)$ to $\alpha$

**Step 3**: $\{\sigma(\alpha)\}$ = Galois conjugates

### Example: $\sqrt{2} + \sqrt{3}$

**Field**: $\mathbb{Q}(\sqrt{2}, \sqrt{3})$

**Degree**: $[\mathbb{Q}(\sqrt{2}, \sqrt{3}) : \mathbb{Q}] = 4$

**Galois group**: $V_4$ (Klein four-group)

**Automorphisms**:
- $\sigma_1$: $\sqrt{2} \mapsto \sqrt{2}$, $\sqrt{3} \mapsto \sqrt{3}$
- $\sigma_2$: $\sqrt{2} \mapsto -\sqrt{2}$, $\sqrt{3} \mapsto \sqrt{3}$
- $\sigma_3$: $\sqrt{2} \mapsto \sqrt{2}$, $\sqrt{3} \mapsto -\sqrt{3}$
- $\sigma_4$: $\sqrt{2} \mapsto -\sqrt{2}$, $\sqrt{3} \mapsto -\sqrt{3}$

**Conjugates of $\sqrt{2} + \sqrt{3}$**:
- $\sqrt{2} + \sqrt{3}$
- $-\sqrt{2} + \sqrt{3}$
- $\sqrt{2} - \sqrt{3}$
- $-\sqrt{2} - \sqrt{3}$

**Minimal polynomial**: $(x^2 - 2 - 3 - 2\sqrt{6})(x^2 - 2 - 3 + 2\sqrt{6}) = x^4 - 10x^2 + 1$

## Common Pitfalls

### 1. Conjugates ≠ Negatives

✗ "Conjugate of $\alpha$ is $-\alpha$"?

✓ Depends on minimal polynomial!

$\sqrt{2}$의 conjugate: $-\sqrt{2}$ (correct)

But $\sqrt[3]{2}$의 conjugate: $\omega\sqrt[3]{2} \neq -\sqrt[3]{2}$

### 2. All Roots ≠ All Conjugates (in given field)

✗ "$\mathbb{Q}(\sqrt[3]{2})$ contains all conjugates of $\sqrt[3]{2}$"?

✓ **NO!** $\mathbb{Q}(\sqrt[3]{2}) \subseteq \mathbb{R}$, but $\omega\sqrt[3]{2} \notin \mathbb{R}$

Need Galois closure: $\mathbb{Q}(\sqrt[3]{2}, \omega)$

### 3. Number of Conjugates

✗ "Always $n$ conjugates for degree $n$"?

✓ **Separable case**: Yes (distinct roots)

✗ **Inseparable case**: May have repeated roots

### 4. Galois Conjugates vs All Conjugates

✗ "Galois conjugates = all conjugates"?

✓ Galois conjugates ⊆ all conjugates

Equality when extension is Galois

### 5. Conjugate Fields

✗ "$K(\alpha)$ and $K(\beta)$ are conjugate $\Rightarrow$ same field"?

✓ **May be different fields** (but $K$-isomorphic)

Example: $\mathbb{Q}(\sqrt{2})$ and $\mathbb{Q}(\sqrt{3})$ are **NOT** conjugate (different minimal polynomials)

## Related Concepts

- [[Extension Field]]: Basic definitions
- [[Galois Theory]]: Galois groups and conjugates
- [[Automorphism]]: Field automorphisms
- [[Irreducible Polynomial]]: Minimal polynomials
- [[Splitting Field]]: Contains all conjugates
- [[Finite Field]]: Frobenius conjugates
- [[Norm and Trace]]: Functions of conjugates
- [[Cyclotomic Polynomial]]: Conjugate roots of unity
- [[Primitive Element]]: Single generator

