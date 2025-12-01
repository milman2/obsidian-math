# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Quotient Group, Factor Group]]
- [[Homomorphism]]
- [[Isomorphism]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Lang, Algebra

---

# <span class="header-theorem">First Isomorphism Theorem</span>

## Statement^[명제]

Group homomorphism^[군 준동형사상] $\phi: G \to H$에 대해:

$$G/\ker(\phi) \cong \text{im}(\phi)$$

**자연스러운 isomorphism^[동형사상]**:

$$\bar{\phi}: G/\ker(\phi) \to \text{im}(\phi), \quad \bar{\phi}(g\ker(\phi)) = \phi(g)$$

## Diagram

```
G -------φ-----→ H
|              ↗
π            φ̄
↓          ↗
G/ker(φ)
```

여기서:
- $\pi: G \to G/\ker(\phi)$는 canonical projection^[표준 사영]
- $\bar{\phi}$는 induced isomorphism
- $\phi = \bar{\phi} \circ \pi$

## Proof^[증명]

### Well-defined

$g_1\ker(\phi) = g_2\ker(\phi)$이면:

$$g_2^{-1}g_1 \in \ker(\phi) \Rightarrow \phi(g_2^{-1}g_1) = e$$

$$\Rightarrow \phi(g_2)^{-1}\phi(g_1) = e \Rightarrow \phi(g_1) = \phi(g_2)$$

### Homomorphism

$$\bar{\phi}(g_1\ker(\phi) \cdot g_2\ker(\phi)) = \bar{\phi}(g_1g_2\ker(\phi)) = \phi(g_1g_2)$$

$$= \phi(g_1)\phi(g_2) = \bar{\phi}(g_1\ker(\phi))\bar{\phi}(g_2\ker(\phi))$$

### Injective

$$\bar{\phi}(g\ker(\phi)) = e \Rightarrow \phi(g) = e \Rightarrow g \in \ker(\phi)$$

$$\Rightarrow g\ker(\phi) = \ker(\phi)$$ 
(identity in $G/\ker(\phi))$

### Surjective

By construction: image of $\bar{\phi}$ is $\text{im}(\phi)$

## Interpretation^[해석]

> **"Kernel을 0으로 만들면 bijection이 됨"**

- Kernel = "얼마나 many-to-one인가"
- Quotient by kernel = "many-to-one 제거"
- Result = Bijective map

## Applications^[응용]

### 1. Homomorphism 분석

모든 homomorphism은:

$$G \to G/\ker(\phi) \cong \text{im}(\phi) \hookrightarrow H$$

- $G \to G/\ker(\phi)$: Canonical projection^[표준 사영] (surjective)
- $G/\ker(\phi) \cong \text{im}(\phi)$: Isomorphism
- $\text{im}(\phi) \hookrightarrow H$: Inclusion^[포함] (injective)

### 2. Image 계산

$$|\text{im}(\phi)| = \frac{|G|}{|\ker(\phi)|}$$

(유한군인 경우)

### 3. Isomorphism 확인

$\phi$ surjective $\Rightarrow$ $G/\ker(\phi) \cong H$

---

# <span class="header-theorem">Second Isomorphism Theorem</span>

(Also known as **Diamond Isomorphism Theorem^[다이아몬드 동형 정리]**)

## Statement

$H \leq G$이고 $N \triangleleft G$이면:

$$H/(H \cap N) \cong (HN)/N$$

여기서:
- $HN = \{hn : h \in H, n \in N\}$
- $H \cap N \triangleleft H$ (normal in $H$)
- $HN \leq G$

## Diagram (Diamond Shape)

```
      HN
     /  \
    H    N
     \  /
     H∩N
```

## Proof Sketch

**Homomorphism 정의**:

$$\phi: H \to HN/N, \quad \phi(h) = hN$$

**Kernel**:

$$\ker(\phi) = \{h \in H : hN = N\} = \{h \in H : h \in N\} = H \cap N$$

**Image**: $\text{im}(\phi) = HN/N$

**First Isomorphism Theorem 적용**: $H/(H \cap N) \cong HN/N$

## Applications

### 1. Subgroup Lattice 분석

Diamond 구조에서 index 관계:

$$[HN : N] = [H : H \cap N]$$

### 2. Order 계산

$$|HN| = \frac{|H| \cdot |N|}{|H \cap N|}$$

---

# <span class="header-theorem">Third Isomorphism Theorem</span>

(Also known as **Correspondence Theorem^[대응 정리]** or **Lattice Theorem^[격자 정리]**)

## Statement

$K, N \triangleleft G$이고 $K \subseteq N$이면:

$$(G/K)/(N/K) \cong G/N$$

## Interpretation

> **"몫의 몫은 전체의 몫"**

$$\frac{G/K}{N/K} = \frac{G}{N}$$

## Proof Sketch

**Homomorphism**:

$$\phi: G/K \to G/N, \quad \phi(gK) = gN$$

**Well-defined**: $K \subseteq N$이므로 $gK = g'K \Rightarrow gN = g'N$

**Kernel**: $\ker(\phi) = \{gK : gN = N\} = N/K$

**First Isomorphism Theorem**: $(G/K)/(N/K) \cong G/N$

## Applications

### 1. Iterative Quotients

여러 단계로 quotient 가능:

$$G \to G/K \to (G/K)/(N/K) = G/N$$

### 2. Normal Subgroup Chain

$$K \triangleleft N \triangleleft G \Rightarrow \text{각 단계에서 quotient}$$

---

# <span class="header-theorem">Fourth Isomorphism Theorem</span>

(Also known as **Correspondence Theorem^[대응 정리]**)

## Statement

$N \triangleleft G$에 대해, 다음 사이에 **일대일 대응**:

$$\{H : N \subseteq H \subseteq G\} \leftrightarrow \{\bar{H} : \bar{H} \leq G/N\}$$

**대응 관계**:

$$H \mapsto H/N = \{hN : h \in H\}$$

$$\bar{H} = H/N \mapsto H = \pi^{-1}(\bar{H})$$

여기서 $\pi: G \to G/N$은 canonical projection

## Properties Preserved^[보존되는 성질]

이 대응은 다음을 보존:

1. **Inclusion^[포함]**: $H_1 \subseteq H_2 \Leftrightarrow H_1/N \subseteq H_2/N$

2. **Normality^[정규성]**: $H \triangleleft G \Leftrightarrow H/N \triangleleft G/N$

3. **Index^[지표]**: $[G : H] = [G/N : H/N]$

4. **Abelianness^[가환성]**: $H$ abelian $\Leftrightarrow$ $H/N$ abelian

5. **Generation^[생성]**: $H = \langle S \rangle \Leftrightarrow H/N = \langle \{sN : s \in S\} \rangle$

## Diagram

```
Subgroups of G         Subgroups of G/N
containing N
      G          ←→         G/N
      ↑                      ↑
      H          ←→         H/N
      ↑                      ↑
      N          ←→         {e}
```

## Applications

### 1. Subgroup Structure 분석

$G/N$의 subgroup 연구 = $G$의 $N$을 포함하는 subgroup 연구

### 2. Normal Subgroups Count

$$|\{H \triangleleft G : N \subseteq H\}| = |\{H \triangleleft G/N\}|$$

### 3. Quotient Simplification

복잡한 $G$ → 간단한 $G/N$으로 문제 단순화

---

# <span class="header-examples">Examples</span>

## Example 1: First Isomorphism Theorem

**Sign homomorphism**: $\phi: S_n \to \{\pm 1\}$

$$\phi(\sigma) = \text{sign}(\sigma)$$

**Kernel**: $\ker(\phi) = A_n$ (alternating group^[교대군])

**Image**: $\text{im}(\phi) = \{\pm 1\} \cong \mathbb{Z}/2\mathbb{Z}$

**First Isomorphism Theorem**:

$$S_n/A_n \cong \mathbb{Z}/2\mathbb{Z}$$

따라서 $|S_n/A_n| = 2$, 즉 $|A_n| = |S_n|/2 = n!/2$

## Example 2: Second Isomorphism Theorem

$G = S_4$, $H = A_4$ (alternating), $N = V_4$ (Klein four-group)

- $H \cap N = V_4$ (Klein four-group)
- $HN = S_4$ (전체)

**Second Isomorphism Theorem**:

$$H/(H \cap N) \cong HN/N$$

$$A_4/V_4 \cong S_4/V_4$$

$$|A_4/V_4| = 12/4 = 3$$

## Example 3: Third Isomorphism Theorem

$G = \mathbb{Z}$, $K = 6\mathbb{Z}$, $N = 3\mathbb{Z}$

$K \subseteq N$ (since $6\mathbb{Z} \subseteq 3\mathbb{Z}$)

**Third Isomorphism Theorem**:

$$(\mathbb{Z}/6\mathbb{Z})/(3\mathbb{Z}/6\mathbb{Z}) \cong \mathbb{Z}/3\mathbb{Z}$$

확인: 
- $|\mathbb{Z}/6\mathbb{Z}| = 6$
- $|3\mathbb{Z}/6\mathbb{Z}| = 2$ (원소: $\{0+6\mathbb{Z}, 3+6\mathbb{Z}\}$)
- $|(\mathbb{Z}/6\mathbb{Z})/(3\mathbb{Z}/6\mathbb{Z})| = 6/2 = 3 = |\mathbb{Z}/3\mathbb{Z}|$

## Example 4: Fourth Isomorphism Theorem

$G = \mathbb{Z}$, $N = 12\mathbb{Z}$

**Subgroups of $\mathbb{Z}/12\mathbb{Z}$**:
- $\{0\}$, $\langle 1 \rangle$, $\langle 2 \rangle$, $\langle 3 \rangle$, $\langle 4 \rangle$, $\langle 6 \rangle$

**Correspondence**:
- $\{0\} \leftrightarrow 12\mathbb{Z}$
- $\langle 1 \rangle \leftrightarrow \mathbb{Z}$
- $\langle 2 \rangle \leftrightarrow 2\mathbb{Z}$
- $\langle 3 \rangle \leftrightarrow 3\mathbb{Z}$
- $\langle 4 \rangle \leftrightarrow 4\mathbb{Z}$
- $\langle 6 \rangle \leftrightarrow 6\mathbb{Z}$

모두 $12\mathbb{Z}$를 포함

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### First Isomorphism Theorem

**"Kernel을 무시하면 bijection"**

Homomorphism이 many-to-one인 이유 = kernel

Kernel을 quotient out = many-to-one 제거

### Second Isomorphism Theorem

**"Diamond 구조의 대칭성"**

```
     HN
    /  \
   H    N
    \  /
    H∩N
```

위아래가 "비슷한" 구조

### Third Isomorphism Theorem

**"두 번 나누기 = 한 번에 나누기"**

$$\frac{G/K}{N/K} = \frac{G}{N}$$

분수의 약분과 유사

### Fourth Isomorphism Theorem

**"Quotient는 정보를 보존"**

$N$을 quotient out해도 $N$ 위의 구조는 보존됨

## Unified View

모든 isomorphism theorem은 **First Isomorphism Theorem의 응용**:

1. **Second**: 적절한 homomorphism 구성 → First 적용
2. **Third**: Natural map $G/K \to G/N$ → First 적용
3. **Fourth**: Inverse image로 correspondence 구성

## 이름의 혼란

**주의**: 문헌마다 번호가 다를 수 있음!

| This Note | Alternative Names |
|-----------|-------------------|
| First | Fundamental Homomorphism Theorem |
| Second | Diamond Theorem |
| Third | - |
| Fourth | Correspondence Theorem, Lattice Theorem |

일부 책에서는 Fourth를 Third로 부르기도 함!

## 실용적 조언

### When to Use

**First**: 
- Homomorphism 분석
- Image, kernel 계산
- Isomorphism 증명

**Second**:
- Subgroup 교집합/곱 계산
- Index 관계
- Lattice 구조

**Third**:
- Iterative quotients
- Normal subgroup chains
- Tower of extensions

**Fourth**:
- Quotient의 subgroup 구조
- Normal subgroup counting
- Structure preservation

## Common Patterns

### Pattern 1: Kernel 찾기

$\phi: G \to H$ 주어짐 → $\ker(\phi)$ 계산 → $G/\ker(\phi) \cong \text{im}(\phi)$

### Pattern 2: Quotient 단순화

복잡한 $G$ → 간단한 $N$ 찾기 → $G/N$ 연구 → Fourth Theorem으로 $G$ 이해

### Pattern 3: Chain of Quotients

$$G \twoheadrightarrow G/N_1 \twoheadrightarrow G/N_2 \twoheadrightarrow \cdots$$

Third Theorem으로 연결

## Applications in Algebra

### Galois Theory^[갈루아 이론]

**Fundamental Theorem of Galois Theory** = Fourth Isomorphism Theorem의 변형

Field extensions $\leftrightarrow$ Subgroups of Galois group

### Ring Theory^[환론]

같은 isomorphism theorems가 rings, modules에도 적용

**Ideal quotients**: $R/I$

자세한 내용은 아래 "Ring Isomorphism Theorems" 참조

### Universal Algebra^[보편 대수학]

모든 algebraic structures에 일반화 가능

## Historical Note

**Emmy Noether** (1882-1935):
- Isomorphism theorems의 현대적 형식화
- Homomorphism과 quotient 개념 확립
- Abstract algebra의 기초 확립

**"Noether Isomorphism Theorems"**라고도 불림

## Related Concepts

- [[Homomorphism]]: 기본 정의
- [[Quotient Group, Factor Group]]: Quotient 구조
- [[Normal Subgroup]]: Quotient 가능 조건
- [[Correspondence Theorem]]: Fourth Isomorphism Theorem의 다른 이름
- [[Kernel and Image]]: First Isomorphism Theorem 핵심

## Further Topics

**Advanced**:
- Zassenhaus Lemma (butterfly lemma)
- Jordan-Hölder Theorem
- Schreier Refinement Theorem
- Category theory perspective (universal properties)

---

# <span class="header-theorem">Ring Isomorphism Theorems</span>

## Comparison: Groups vs Rings

| Aspect | Groups | Rings |
|--------|--------|-------|
| Structure | $(G, \cdot)$ | $(R, +, \cdot)$ |
| Homomorphism | $\phi(ab) = \phi(a)\phi(b)$ | $\phi(a+b) = \phi(a)+\phi(b)$, $\phi(ab) = \phi(a)\phi(b)$ |
| Kernel | Normal subgroup | Two-sided ideal |
| Quotient | $G/N$ ($N \triangleleft G$) | $R/I$ ($I$ two-sided ideal) |
| Image | Subgroup | Subring |

**핵심 차이점**:
- Ring homomorphism은 **두 연산** 모두 보존
- Kernel은 **ideal** (단순 subring이 아님!)
- Quotient 가능 조건: **Two-sided ideal** 필요

## First Isomorphism Theorem (Rings)

### Statement

Ring homomorphism^[환 준동형사상] $\phi: R \to S$에 대해:

$$R/\ker(\phi) \cong \text{im}(\phi)$$

**Natural isomorphism**:

$$\bar{\phi}: R/\ker(\phi) \to \text{im}(\phi), \quad \bar{\phi}(r + \ker(\phi)) = \phi(r)$$

### Key Points

1. $\ker(\phi) = \{r \in R : \phi(r) = 0\}$ is **two-sided ideal**^[양측 아이디얼]
2. $\text{im}(\phi)$ is **subring** of $S$
3. $\bar{\phi}$ is **ring isomorphism** (preserves both $+$ and $\cdot$)

### Examples

#### Example 1: Evaluation Homomorphism

$\phi: \mathbb{Z}[x] \to \mathbb{Z}$, $\phi(f(x)) = f(0)$

- **Kernel**: $\ker(\phi) = \langle x \rangle$ (polynomials with constant term 0)
- **Image**: $\mathbb{Z}$

**First Isomorphism Theorem**:

$$\mathbb{Z}[x]/\langle x \rangle \cong \mathbb{Z}$$

#### Example 2: Reduction Modulo $n$

$\phi: \mathbb{Z} \to \mathbb{Z}/n\mathbb{Z}$, $\phi(a) = [a]_n$

- **Kernel**: $n\mathbb{Z}$
- **Image**: $\mathbb{Z}/n\mathbb{Z}$

**First Isomorphism Theorem**:

$$\mathbb{Z}/n\mathbb{Z} \cong \mathbb{Z}/n\mathbb{Z}$$

#### Example 3: Complex Numbers

$\phi: \mathbb{R}[x] \to \mathbb{C}$, $\phi(f(x)) = f(i)$

- **Kernel**: $\langle x^2 + 1 \rangle$
- **Image**: $\mathbb{C}$

**First Isomorphism Theorem**:

$$\mathbb{R}[x]/\langle x^2 + 1 \rangle \cong \mathbb{C}$$

자세한 내용은 [[Evaluation Homomorphism]] 참조

## Second Isomorphism Theorem (Rings)

### Statement

$S$ subring of $R$, $I$ two-sided ideal of $R$:

$$S/(S \cap I) \cong (S + I)/I$$

where $S + I = \{s + a : s \in S, a \in I\}$

### Comparison with Groups

| Groups | Rings |
|--------|-------|
| $H$ subgroup | $S$ subring |
| $N$ normal subgroup | $I$ ideal |
| $HN$ | $S + I$ |
| $H \cap N$ | $S \cap I$ |

**주의**: Ring에서는 $S + I$가 subring (곱셈에서 닫혀있지 않을 수 있음)

### Example

$R = \mathbb{Z}$, $S = 2\mathbb{Z}$, $I = 3\mathbb{Z}$

- $S \cap I = 6\mathbb{Z}$
- $S + I = \mathbb{Z}$ (gcd(2,3) = 1이므로)

$$2\mathbb{Z}/6\mathbb{Z} \cong \mathbb{Z}/3\mathbb{Z}$$

## Third Isomorphism Theorem (Rings)

### Statement

$I, J$ two-sided ideals of $R$, $I \subseteq J$:

$$(R/I)/(J/I) \cong R/J$$

### Interpretation

**"몫의 몫은 전체의 몫"** (Groups와 동일)

### Example

$R = \mathbb{Z}$, $I = 12\mathbb{Z}$, $J = 4\mathbb{Z}$

$I \subseteq J$ (since $12\mathbb{Z} \subseteq 4\mathbb{Z}$)

$$(\mathbb{Z}/12\mathbb{Z})/(4\mathbb{Z}/12\mathbb{Z}) \cong \mathbb{Z}/4\mathbb{Z}$$

확인:
- $|\mathbb{Z}/12\mathbb{Z}| = 12$
- $|4\mathbb{Z}/12\mathbb{Z}| = 3$ (원소: $\{0, 4, 8\} + 12\mathbb{Z}$)
- $|(\mathbb{Z}/12\mathbb{Z})/(4\mathbb{Z}/12\mathbb{Z})| = 12/3 = 4$

## Fourth Isomorphism Theorem (Rings)

### Statement

$I$ two-sided ideal of $R$, 다음 사이에 **일대일 대응**:

$$\{\text{Ideals } J : I \subseteq J \subseteq R\} \leftrightarrow \{\text{Ideals } \bar{J} : \bar{J} \triangleleft R/I\}$$

**Correspondence**:

$$J \mapsto J/I$$

### Properties Preserved

1. **Inclusion**: $J_1 \subseteq J_2 \Leftrightarrow J_1/I \subseteq J_2/I$
2. **Prime ideals**: $P$ prime $\Leftrightarrow$ $P/I$ prime (if $I \subseteq P$)
3. **Maximal ideals**: $M$ maximal $\Leftrightarrow$ $M/I$ maximal (if $I \subseteq M$)

### Example

$R = \mathbb{Z}$, $I = 60\mathbb{Z}$

**Ideals of $\mathbb{Z}/60\mathbb{Z}$**:
- $\langle 1 \rangle = \mathbb{Z}/60\mathbb{Z}$ ↔ $\mathbb{Z}$
- $\langle 2 \rangle$ ↔ $2\mathbb{Z}$
- $\langle 3 \rangle$ ↔ $3\mathbb{Z}$
- $\langle 4 \rangle$ ↔ $4\mathbb{Z}$
- $\langle 5 \rangle$ ↔ $5\mathbb{Z}$
- $\langle 6 \rangle$ ↔ $6\mathbb{Z}$
- ...
- $\langle 60 \rangle = \{0\}$ ↔ $60\mathbb{Z}$

모두 $60\mathbb{Z}$를 포함하는 $\mathbb{Z}$의 ideals

## Key Differences: Groups vs Rings

### 1. Kernel Structure

**Groups**:
- $\ker(\phi)$ is **normal subgroup**
- Normality: $gNg^{-1} = N$

**Rings**:
- $\ker(\phi)$ is **two-sided ideal**
- $rIr' \subseteq I$ for all $r, r' \in R$
- Much stronger condition!

### 2. Quotient Construction

**Groups**:
- $G/N$ requires $N \triangleleft G$
- Cosets: $gN$

**Rings**:
- $R/I$ requires $I$ two-sided ideal
- Cosets: $r + I$
- Additive cosets (not multiplicative!)

### 3. Homomorphism Conditions

**Groups**:
- $\phi(ab) = \phi(a)\phi(b)$
- One operation

**Rings**:
- $\phi(a + b) = \phi(a) + \phi(b)$
- $\phi(ab) = \phi(a)\phi(b)$
- Two operations!
- Often also: $\phi(1) = 1$ (unital rings)

### 4. Image Properties

**Groups**:
- $\text{im}(\phi)$ is **subgroup** of $H$

**Rings**:
- $\text{im}(\phi)$ is **subring** of $S$
- NOT necessarily an ideal!

### 5. Important: Not Every Subring is Quotient

**Groups**: Every subgroup of $G/N$ corresponds to some $H \supseteq N$

**Rings**: Not every subring of $R/I$ comes from quotient!

**Example**: $\mathbb{Z}/6\mathbb{Z}$ has subring $\{0, 2, 4\}$ (under addition)
- But this is NOT of the form $J/6\mathbb{Z}$ for any ideal $J$ of $\mathbb{Z}$!
- Because $\{0, 2, 4\}$ is not an ideal of $\mathbb{Z}/6\mathbb{Z}$ (not closed under multiplication by units)

## Applications in Ring Theory

### 1. Field Extensions

$K[x]/(f(x)) \cong K(\alpha)$ where $f(\alpha) = 0$

**Example**: $\mathbb{Q}[x]/(x^2 - 2) \cong \mathbb{Q}(\sqrt{2})$

자세한 내용은 [[Extension Field]], [[Kronecker Theorem]] 참조

### 2. Chinese Remainder Theorem

$\gcd(m, n) = 1$이면:

$$\mathbb{Z}/mn\mathbb{Z} \cong \mathbb{Z}/m\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$$

Isomorphism theorems의 응용!

자세한 내용은 [[Chinese Remainder Theorem]] 참조

### 3. Quotient Rings in Algebraic Geometry

Coordinate ring: $k[x_1, \ldots, x_n]/I$

**Variety** = Zero set of $I$

Isomorphism theorems로 geometric properties 분석

### 4. Maximal and Prime Ideals

**정리**: $M$ maximal ideal $\Leftrightarrow$ $R/M$ is field

**정리**: $P$ prime ideal $\Leftrightarrow$ $R/P$ is integral domain

Fourth Isomorphism Theorem로 ideal hierarchy 분석

자세한 내용은 [[Maximal Ideal]], [[Prime Ideal]] 참조

## Common Pitfalls: Groups vs Rings

### 1. Kernel ≠ Subring

✗ "Kernel은 subring이다"?

✓ Kernel은 **ideal** (특별한 subring)
- Subring: $1 \in S$, 곱셈/덧셈 닫힘
- Ideal: 모든 $r \in R$에 대해 $rI, Ir \subseteq I$

### 2. Every Subring ≠ Kernel

✗ "모든 subring이 어떤 homomorphism의 kernel"?

✓ **Ideal만** kernel이 될 수 있음!

**반례**: $\mathbb{Z} \subseteq \mathbb{Q}$ is subring but not ideal

### 3. Quotient ≠ Subring

✗ "$R/I$는 $R$의 subring"?

✓ $R/I$는 **새로운 ring** (not subring of $R$)

### 4. Ideal in Quotient

✗ "$R/I$의 모든 ideal이 $J/I$ 형태"?

✓ Fourth Isomorphism Theorem이 이를 보장!

### 5. One-sided Ideals

✗ "One-sided ideal로 quotient 가능"?

✓ **Two-sided ideal** 필요!

**Non-commutative rings**: Left ideal ≠ right ideal ≠ two-sided ideal

## Summary Table

| Theorem | Groups | Rings |
|---------|--------|-------|
| **First** | $G/\ker(\phi) \cong \text{im}(\phi)$ | $R/\ker(\phi) \cong \text{im}(\phi)$ |
| **Second** | $H/(H \cap N) \cong HN/N$ | $S/(S \cap I) \cong (S+I)/I$ |
| **Third** | $(G/K)/(N/K) \cong G/N$ | $(R/I)/(J/I) \cong R/J$ |
| **Fourth** | Subgroups ↔ Subgroups | Ideals ↔ Ideals |
| **Kernel** | Normal subgroup | Two-sided ideal |
| **Quotient** | $gN$ | $r + I$ |
| **Operations** | 1 (multiplication) | 2 (addition, multiplication) |

## Related Ring Theorems

- [[Ring]]: Basic definitions
- [[Ideal]]: Kernel structure
- [[Quotient Ring]]: Quotient construction
- [[Prime Ideal]]: Prime ideal characterization
- [[Maximal Ideal]]: Maximal ideal characterization
- [[Homomorphism]]: Ring homomorphisms
- [[Chinese Remainder Theorem]]: Product decomposition

