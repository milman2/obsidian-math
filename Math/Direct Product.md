# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Homomorphism]]
- [[Isomorphism]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Hungerford, Algebra

---

# <span class="header-definition">Definition</span>

## Direct Product^[직적]

Groups $G_1, G_2, \ldots, G_n$의 **direct product**^[직적]:

$$G_1 \times G_2 \times \cdots \times G_n$$

### Elements

$$G_1 \times \cdots \times G_n = \{(g_1, \ldots, g_n) : g_i \in G_i\}$$

Ordered tuples (순서쌍)

### Operation

**Component-wise**^[성분별]:

$$(g_1, \ldots, g_n) \cdot (h_1, \ldots, h_n) = (g_1h_1, \ldots, g_nh_n)$$

### Group Structure

**Identity**: $(e_1, e_2, \ldots, e_n)$

**Inverse**: $(g_1, \ldots, g_n)^{-1} = (g_1^{-1}, \ldots, g_n^{-1})$

**Order** (finite case): $|G_1 \times \cdots \times G_n| = |G_1| \cdots |G_n|$

## Infinite Direct Product

Arbitrarily many groups $\{G_i\}_{i \in I}$:

$$\prod_{i \in I} G_i = \{(g_i)_{i \in I} : g_i \in G_i\}$$

**모든 components** 포함 (finite support 불필요)

## Direct Sum vs Direct Product

### Finite Case

$$G_1 \oplus G_2 \oplus \cdots \oplus G_n = G_1 \times G_2 \times \cdots \times G_n$$

**같음!**

### Infinite Case

$$\bigoplus_{i \in I} G_i \subsetneq \prod_{i \in I} G_i$$

**Direct Sum** $\bigoplus$: **Finite support** (유한개만 non-identity)

$$\bigoplus_{i \in I} G_i = \{(g_i) : \text{finitely many } g_i \neq e_i\}$$

**Direct Product** $\prod$: **모든 components** 허용

자세한 내용은 [[Direct Sum]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$

$$G = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$$

**Elements**: $\{([0],[0]), ([0],[1]), ([0],[2]), ([1],[0]), ([1],[1]), ([1],[2])\}$

**Order**: $|G| = 2 \cdot 3 = 6$

**Operation**: $([a],[b]) + ([c],[d]) = ([a+c],[b+d])$

**Structure**: $G \cong \mathbb{Z}/6\mathbb{Z}$ (by Chinese Remainder Theorem)

**이유**: $\gcd(2,3) = 1$

자세한 내용은 [[Cyclic Group]] 참조

## Example 2: Klein Four-Group

$$V_4 = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$$

**Elements**: $\{(0,0), (1,0), (0,1), (1,1)\}$

**Cayley Table**:

| $+$ | $(0,0)$ | $(1,0)$ | $(0,1)$ | $(1,1)$ |
|-----|---------|---------|---------|---------|
| $(0,0)$ | $(0,0)$ | $(1,0)$ | $(0,1)$ | $(1,1)$ |
| $(1,0)$ | $(1,0)$ | $(0,0)$ | $(1,1)$ | $(0,1)$ |
| $(0,1)$ | $(0,1)$ | $(1,1)$ | $(0,0)$ | $(1,0)$ |
| $(1,1)$ | $(1,1)$ | $(0,1)$ | $(1,0)$ | $(0,0)$ |

**Properties**:
- Abelian ✓
- Every non-identity element has order 2
- **NOT cyclic** ($\mathbb{Z}/4\mathbb{Z}$와 다름)

## Example 3: $\mathbb{R}^n$

$$\mathbb{R}^n = \underbrace{\mathbb{R} \times \mathbb{R} \times \cdots \times \mathbb{R}}_{n \text{ times}}$$

**As additive group**

**Elements**: $(x_1, x_2, \ldots, x_n)$ where $x_i \in \mathbb{R}$

**Operation**: Component-wise addition

**Vector space structure**: $\mathbb{R}^n$ over $\mathbb{R}$

자세한 내용은 [[Linear mapping]] 참조

## Example 4: $S_3 \times \mathbb{Z}/2\mathbb{Z}$

**Order**: $|S_3 \times \mathbb{Z}/2\mathbb{Z}| = 6 \cdot 2 = 12$

**Example element**: $((12), [1]) \in S_3 \times \mathbb{Z}/2\mathbb{Z}$

**Operation**: 
$$((12), [1]) \cdot ((13), [0]) = ((12)(13), [1]) = ((132), [1])$$

**Properties**:
- Non-abelian ($S_3$ non-abelian)
- Has normal subgroups: $S_3 \times \{[0]\}$, $\{e\} \times \mathbb{Z}/2\mathbb{Z}$

자세한 내용은 [[Symmetric Group]] 참조

## Example 5: Infinite Direct Product

$$\prod_{n=1}^\infty \mathbb{Z}/2\mathbb{Z}$$

**Elements**: Infinite sequences $(a_1, a_2, a_3, \ldots)$ where $a_i \in \{0,1\}$

**예**: $(1, 0, 1, 1, 0, 0, \ldots)$, $(0, 0, 0, \ldots)$

**Uncountable**: $|\prod_{n=1}^\infty \mathbb{Z}/2\mathbb{Z}| = 2^{\aleph_0}$ (continuum)

**Compare**: $\bigoplus_{n=1}^\infty \mathbb{Z}/2\mathbb{Z}$ (finite support) = countable

## Example 6: $\mathbb{Z} \times \mathbb{Z}$

$$\mathbb{Z}^2 = \mathbb{Z} \times \mathbb{Z}$$

**Elements**: $(m, n)$ where $m, n \in \mathbb{Z}$

**Generators**: $(1, 0)$ and $(0, 1)$

**Not cyclic**: No single element generates all of $\mathbb{Z}^2$

**Fundamental group**: $\pi_1(\text{Torus}) \cong \mathbb{Z} \times \mathbb{Z}$

---

# <span class="header-properties">Properties</span>

## Universal Property

**정리**: $G_1 \times G_2$는 다음 universal property를 만족:

Homomorphisms $\phi_i: H \to G_i$에 대해, 유일한 $\Phi: H \to G_1 \times G_2$ 존재:

$$\Phi(h) = (\phi_1(h), \phi_2(h))$$

such that $\pi_i \circ \Phi = \phi_i$ (where $\pi_i$ = projection)

**Diagram**:
```
      Φ
  H ----→ G₁ × G₂
   \        ↓π₁  ↓π₂
    φ₁ →  G₁    G₂
```

**의미**: Direct product = "Categorical product" in category of groups

자세한 내용은 [[Category Theory]] 참조

## Projection Maps^[사영 사상]

$$\pi_i: G_1 \times \cdots \times G_n \to G_i$$

$$\pi_i(g_1, \ldots, g_n) = g_i$$

**Properties**:
- Surjective homomorphism ✓
- $\ker(\pi_i) = G_1 \times \cdots \times \{e_i\} \times \cdots \times G_n$

## Injection Maps^[포함 사상]

$$\iota_i: G_i \to G_1 \times \cdots \times G_n$$

$$\iota_i(g_i) = (e_1, \ldots, e_{i-1}, g_i, e_{i+1}, \ldots, e_n)$$

**Properties**:
- Injective homomorphism ✓
- $\text{im}(\iota_i) = \{e_1\} \times \cdots \times G_i \times \cdots \times \{e_n\}$

## Normal Subgroups

**정리**: $H_i \triangleleft G_i$ for all $i$ $\Rightarrow$ $H_1 \times \cdots \times H_n \triangleleft G_1 \times \cdots \times G_n$

**Quotient**:

$$(G_1 \times \cdots \times G_n)/(H_1 \times \cdots \times H_n) \cong (G_1/H_1) \times \cdots \times (G_n/H_n)$$

자세한 내용은 [[Normal Subgroup]] 참조

## Center

**정리**: 

$$Z(G_1 \times G_2) = Z(G_1) \times Z(G_2)$$

**증명**: $(g_1, g_2) \in Z(G_1 \times G_2)$

$\Leftrightarrow (g_1, g_2)(h_1, h_2) = (h_1, h_2)(g_1, g_2)$ for all $(h_1, h_2)$

$\Leftrightarrow g_1h_1 = h_1g_1$ and $g_2h_2 = h_2g_2$ for all $h_1, h_2$

$\Leftrightarrow g_1 \in Z(G_1)$ and $g_2 \in Z(G_2)$ ✓

## Commutativity

**정리**: $G_1, G_2$ abelian $\Rightarrow$ $G_1 \times G_2$ abelian

**역**: $G_1 \times G_2$ abelian $\not\Rightarrow$ $G_1, G_2$ abelian (일반적으로 거짓)

Wait, 실제로는:

$G_1 \times G_2$ abelian $\Rightarrow$ $G_1, G_2$ abelian ✓

**증명**: Projections are surjective homomorphisms, abelian property preserved ✓

자세한 내용은 [[Abelian Group]] 참조

## Cyclic Groups

**정리**: $G_1 \times G_2$ cyclic $\Leftrightarrow$ $G_1, G_2$ cyclic and $\gcd(|G_1|, |G_2|) = 1$

**증명**:
- ($\Rightarrow$): If cyclic, then abelian, so components cyclic
- ($\Leftarrow$): Chinese Remainder Theorem ✓

**예**:
- $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z} \cong \mathbb{Z}/6\mathbb{Z}$ (cyclic) ✓
- $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$ (NOT cyclic) ✗

자세한 내용은 [[Cyclic Group]] 참조

## Order of Elements

$(g_1, g_2) \in G_1 \times G_2$의 order:

$$|(g_1, g_2)| = \text{lcm}(|g_1|, |g_2|)$$

**증명**: $(g_1, g_2)^n = (g_1^n, g_2^n) = (e_1, e_2)$

$\Leftrightarrow g_1^n = e_1$ and $g_2^n = e_2$

$\Leftrightarrow |g_1| \mid n$ and $|g_2| \mid n$

$\Leftrightarrow \text{lcm}(|g_1|, |g_2|) \mid n$ ✓

**예**: $|([1], [1])| = \text{lcm}(2, 3) = 6$ in $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$

---

# <span class="header-theorem">Theorem</span>

## Chinese Remainder Theorem (CRT)

$\gcd(m, n) = 1$일 때:

$$\mathbb{Z}/mn\mathbb{Z} \cong \mathbb{Z}/m\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$$

**Isomorphism**:

$$\phi: \mathbb{Z}/mn\mathbb{Z} \to \mathbb{Z}/m\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$$

$$\phi([a]_{mn}) = ([a]_m, [a]_n)$$

**일반화**: $\gcd(n_i, n_j) = 1$ for $i \neq j$

$$\mathbb{Z}/n_1n_2\cdots n_k\mathbb{Z} \cong \mathbb{Z}/n_1\mathbb{Z} \times \cdots \times \mathbb{Z}/n_k\mathbb{Z}$$

자세한 내용은 [[Isomorphism]] 참조

## Fundamental Theorem of Finitely Generated Abelian Groups

Finitely generated abelian group:

$$G \cong \mathbb{Z}^r \times \mathbb{Z}/n_1\mathbb{Z} \times \cdots \times \mathbb{Z}/n_k\mathbb{Z}$$

**Direct product decomposition**

자세한 내용은 [[Abelian Group]] 참조

## Recognition of Direct Products

**Internal Direct Product**: $G = H \times K$ (internally)

**조건**:
1. $H, K \triangleleft G$ (both normal)
2. $H \cap K = \{e\}$
3. $HK = G$ (every element = product)
4. $hk = kh$ for all $h \in H, k \in K$

**결과**: $G \cong H \times K$ (as groups)

## Semidirect Product

**Generalization**: $G = H \rtimes_\phi K$

**조건**:
1. $H \triangleleft G$ (normal)
2. $H \cap K = \{e\}$
3. $HK = G$
4. But $hk \neq kh$ (일반적으로)

**Direct product = trivial semidirect product** ($\phi = \text{trivial}$)

## Structure Theorem for Finite Abelian Groups

Every finite abelian group:

$$G \cong \mathbb{Z}/p_1^{a_1}\mathbb{Z} \times \cdots \times \mathbb{Z}/p_k^{a_k}\mathbb{Z}$$

(Primary decomposition)

또는

$$G \cong \mathbb{Z}/n_1\mathbb{Z} \times \cdots \times \mathbb{Z}/n_m\mathbb{Z}$$

where $n_i \mid n_{i+1}$ (Invariant factors)

**Direct product of cyclic groups**

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Direct Product = "독립적으로 작동"**

### 메타포: 독립 시스템

**$G_1 \times G_2$**: 두 시스템이 독립적으로 작동

- Component 1: $G_1$에서 연산
- Component 2: $G_2$에서 연산
- 서로 간섭 없음

### 메타포: 좌표 평면

**$\mathbb{R}^2 = \mathbb{R} \times \mathbb{R}$**

- $x$-좌표와 $y$-좌표 독립
- 각각 따로 더함: $(x_1, y_1) + (x_2, y_2) = (x_1+x_2, y_1+y_2)$

## 왜 중요한가?

### 1. Decomposition

**복잡한 group → 간단한 groups의 product**

Structure theorem: Abelian groups = products of cyclic groups

### 2. Classification

**Finite abelian groups 완전 분류**

Direct product of prime power cyclic groups

### 3. Building New Groups

**알려진 groups로부터 새로운 groups 구성**

예: $V_4 = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$

### 4. Representation Theory

**Representations of $G_1 \times G_2$** = Tensor products of representations

## Direct Product vs Direct Sum

| | **Finite** | **Infinite** |
|---|---|---|
| **Direct Product** $\times$ or $\prod$ | All components | All components |
| **Direct Sum** $\oplus$ or $\bigoplus$ | Same as product | Finite support only |
| **Equality?** | Yes: $\oplus = \times$ | No: $\bigoplus \subsetneq \prod$ |

### 예시

**Finite**: $\mathbb{Z}/2\mathbb{Z} \oplus \mathbb{Z}/3\mathbb{Z} = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$

**Infinite**: 
- $\bigoplus_{n=1}^\infty \mathbb{Z}$: Finite support sequences (countable)
- $\prod_{n=1}^\infty \mathbb{Z}$: All sequences (uncountable)

## Internal vs External

**External Direct Product**: $G_1 \times G_2$ (construction)

**Internal Direct Product**: $G = H \times K$ where $H, K \leq G$

**Recognition**: 조건 확인 → Isomorphic to external product

## Cartesian Product

**Set theory**: Cartesian product $X \times Y$

**Group theory**: Direct product with group structure

**관계**: Direct product의 underlying set = Cartesian product

## 계산 예시

### $\mathbb{Z}/4\mathbb{Z} \times \mathbb{Z}/6\mathbb{Z}$

**Order**: $|G| = 4 \cdot 6 = 24$

**CRT?**: $\gcd(4, 6) = 2 \neq 1$ ✗

Therefore $G \not\cong \mathbb{Z}/24\mathbb{Z}$

**실제로**:

$$\mathbb{Z}/4\mathbb{Z} \times \mathbb{Z}/6\mathbb{Z} \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/12\mathbb{Z}$$

(Primary decomposition로 확인)

### Element Order

$|([2]_4, [3]_6)| = \text{lcm}(|(2]_4|, |[3]_6|) = \text{lcm}(2, 2) = 2$

## 응용

**Algebra**:
- Structure theorems
- Classification of groups
- Representation theory

**Topology**:
- Product topology
- Fundamental groups: $\pi_1(X \times Y) \cong \pi_1(X) \times \pi_1(Y)$
- Torus: $T^2 = S^1 \times S^1$

자세한 내용은 [[Topology]] 참조

**Number Theory**:
- Chinese Remainder Theorem
- Unit groups: $(\mathbb{Z}/n\mathbb{Z})^\times$

자세한 내용은 [[Euler's theorem]] 참조

**Physics**:
- Product of symmetry groups
- Gauge groups

## 역사적 배경

**19세기**: Finite abelian groups 연구

**Kronecker**: Structure theorem (1870s)

**현대**: Category theory - universal property

## 표기법

| 표기 | 의미 |
|------|------|
| $G_1 \times G_2$ | Direct product |
| $G_1 \oplus G_2$ | Direct sum (= product for finite) |
| $\prod_{i \in I} G_i$ | Infinite direct product |
| $\bigoplus_{i \in I} G_i$ | Infinite direct sum |
| $\pi_i$ | Projection map |
| $\iota_i$ | Injection map |

## Common Pitfall^[흔한 실수]

### 1. CRT 조건

$\mathbb{Z}/mn\mathbb{Z} \cong \mathbb{Z}/m\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$

Only if $\gcd(m, n) = 1$!

### 2. Cyclic test

$G_1 \times G_2$ cyclic $\not\Leftrightarrow$ $G_1, G_2$ cyclic

Need $\gcd(|G_1|, |G_2|) = 1$ also!

### 3. Direct sum ≠ Direct product (infinite)

Infinite case: $\bigoplus \subsetneq \prod$

### 4. Commutativity

$G_1 \times G_2$ abelian $\Leftrightarrow$ $G_1, G_2$ abelian ✓

(Both directions!)

### 5. Normal subgroups

$H_i \triangleleft G_i$ $\Rightarrow$ $H_1 \times H_2 \triangleleft G_1 \times G_2$ ✓

Component-wise normality

## 관련 개념

- [[Direct Sum]]: Finite case same, infinite different
- [[Abelian Group]]: Structure theorem uses products
- [[Cyclic Group]]: CRT for cyclic products
- [[Isomorphism]]: Recognition theorems
- [[Category Theory]]: Universal property

## 추가 학습 주제

**기초**:
- Finite direct products
- Component-wise operations
- CRT

**중급**:
- Internal vs external
- Semidirect products
- Structure theorems

**고급**:
- Infinite products and sums
- Categorical products
- Tensor products

