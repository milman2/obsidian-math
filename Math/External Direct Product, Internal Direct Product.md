# <span class="header-prerequisite">Prerequisite</span>
- [[Group Theory]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Homomorphism]]
- [[Isomorphism]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Hungerford, Algebra
- Lang, Algebra
- Aluffi, Algebra: Chapter 0

---

# <span class="header-definition">Definition</span>

## External Direct Product^[외부 직접곱]

### Definition (Groups)

**External direct product**^[외부 직접곱] of groups $G_1, G_2, \ldots, G_n$:

$$G_1 \times G_2 \times \cdots \times G_n$$

**Elements**: Ordered tuples $(g_1, g_2, \ldots, g_n)$ where $g_i \in G_i$

**Operation**: Component-wise**^[성분별]

$$(g_1, g_2, \ldots, g_n) \cdot (h_1, h_2, \ldots, h_n) = (g_1 h_1, g_2 h_2, \ldots, g_n h_n)$$

**Identity**: $(e_1, e_2, \ldots, e_n)$ where $e_i$ is identity of $G_i$

**Inverse**: $(g_1, g_2, \ldots, g_n)^{-1} = (g_1^{-1}, g_2^{-1}, \ldots, g_n^{-1})$

**표기**: $G_1 \times G_2$ 또는 $\prod_{i=1}^n G_i$

### Infinite Direct Product

For infinite family $\{G_i\}_{i \in I}$:

$$\prod_{i \in I} G_i = \{(g_i)_{i \in I} : g_i \in G_i\}$$

**Operation**: Component-wise on all components

---

## Internal Direct Product^[내부 직접곱]

### Definition

Group $G$ is the **internal direct product**^[내부 직접곱] of subgroups $H_1, H_2, \ldots, H_n$ if:

1. Each $H_i \trianglelefteq G$ (normal subgroup^[정규 부분군])
2. $G = H_1 H_2 \cdots H_n = \{h_1 h_2 \cdots h_n : h_i \in H_i\}$
3. $H_i \cap (H_1 \cdots H_{i-1} H_{i+1} \cdots H_n) = \{e\}$ for each $i$

**표기**: $G = H_1 \times H_2 \times \cdots \times H_n$ (내부적으로)

**Alternative condition** (for two subgroups):

$G = H_1 \times H_2$ internally if:
1. $H_1, H_2 \trianglelefteq G$
2. $G = H_1 H_2$
3. $H_1 \cap H_2 = \{e\}$

### Equivalent Characterization

**정리**: $G$ is internal direct product of $H_1, \ldots, H_n$ if and only if:

1. Every $g \in G$ can be written **uniquely** as $g = h_1 h_2 \cdots h_n$ with $h_i \in H_i$
2. Elements from different $H_i$ commute: $h_i h_j = h_j h_i$ for $i \neq j$

---

## Direct Sum^[직합] (Abelian Groups)

For **abelian groups**, notation often uses $\oplus$:

$$G_1 \oplus G_2 \oplus \cdots \oplus G_n$$

**Same as direct product** for finite case, but different for infinite:

### Finite Case

$$\bigoplus_{i=1}^n G_i = \prod_{i=1}^n G_i$$

### Infinite Case

**Direct sum**^[직합]: Elements with **finitely many non-zero components**

$$\bigoplus_{i \in I} G_i = \{(g_i)_{i \in I} : g_i \in G_i, \text{ all but finitely many } g_i = e\}$$

**Direct product**^[직곱]: All elements (possibly infinitely many non-zero)

$$\prod_{i \in I} G_i = \{(g_i)_{i \in I} : g_i \in G_i\}$$

**관계**: $\displaystyle\bigoplus_{i \in I} G_i \subseteq \prod_{i \in I} G_i$ (proper subgroup for infinite $I$)

---

# <span class="header-properties">Properties</span>

## External Direct Product Properties

### Order

**정리**: If $G_1, \ldots, G_n$ are finite groups:

$$|G_1 \times \cdots \times G_n| = |G_1| \cdot |G_2| \cdots |G_n|$$

**증명**: Counting tuples ✓

### Abelian Property

**정리**: $G_1 \times G_2$ is abelian $\Leftrightarrow$ both $G_1, G_2$ are abelian

**증명**:
- ($\Rightarrow$): If product abelian, projections to components show each is abelian
- ($\Leftarrow$): $(g_1, g_2)(h_1, h_2) = (g_1h_1, g_2h_2) = (h_1g_1, h_2g_2) = (h_1, h_2)(g_1, g_2)$ ✓

### Universal Property

**정리** (Universal property of product):

For groups $G_i$ and homomorphisms $f_i: H \to G_i$, there exists unique homomorphism

$$f: H \to \prod_i G_i$$

such that $\pi_i \circ f = f_i$ where $\pi_i$ is projection

**의미**: Product is universal with respect to maps into it

### Projection Homomorphisms

**Projection maps**^[사영 사상]:

$$\pi_i: G_1 \times \cdots \times G_n \to G_i, \quad (g_1, \ldots, g_n) \mapsto g_i$$

- Surjective homomorphisms
- $\ker(\pi_i) = G_1 \times \cdots \times G_{i-1} \times \{e\} \times G_{i+1} \times \cdots \times G_n$

### Injection Homomorphisms

**Injection maps**^[포함 사상]:

$$\iota_i: G_i \to G_1 \times \cdots \times G_n, \quad g_i \mapsto (e_1, \ldots, e_{i-1}, g_i, e_{i+1}, \ldots, e_n)$$

- Injective homomorphisms
- $\text{im}(\iota_i) \cong G_i$

## Internal Direct Product Properties

### Recognition Theorem

**정리**: $G$ is internal direct product of $H_1, H_2$ if and only if:

1. $H_1, H_2 \trianglelefteq G$
2. $H_1 H_2 = G$
3. $H_1 \cap H_2 = \{e\}$

**Corollary**: Elements from different factors commute

**증명**: For $h_1 \in H_1, h_2 \in H_2$:

$$h_1 h_2 h_1^{-1} h_2^{-1} = (h_1 h_2 h_1^{-1}) h_2^{-1} \in H_2$$

$$h_1 h_2 h_1^{-1} h_2^{-1} = h_1 (h_2 h_1^{-1} h_2^{-1}) \in H_1$$

Therefore $h_1 h_2 h_1^{-1} h_2^{-1} \in H_1 \cap H_2 = \{e\}$, so $h_1 h_2 = h_2 h_1$ ✓

### Uniqueness of Decomposition

**정리**: If $G = H_1 \times \cdots \times H_n$ internally, every $g \in G$ has **unique** representation

$$g = h_1 h_2 \cdots h_n \quad (h_i \in H_i)$$

## Connection Between External and Internal

**정리** (Fundamental Isomorphism):

If $G = H_1 \times H_2$ (internally), then

$$G \cong H_1 \times H_2 \quad \text{(externally)}$$

**Isomorphism**:

$$\phi: H_1 \times H_2 \to G, \quad (h_1, h_2) \mapsto h_1 h_2$$

**증명**:
- Well-defined by unique representation ✓
- Homomorphism: $(h_1, h_2)(h_1', h_2') \mapsto h_1h_2h_1'h_2' = h_1h_1'h_2h_2'$ (elements commute) ✓
- Bijective by uniqueness ✓

**의미**: Internal and external direct products are "the same" up to isomorphism

---

## Fundamental Theorem of Finitely Generated Abelian Groups

**정리**: Every finitely generated abelian group $G$ is isomorphic to

$$\mathbb{Z}^r \oplus \mathbb{Z}/n_1\mathbb{Z} \oplus \cdots \oplus \mathbb{Z}/n_k\mathbb{Z}$$

where $n_1 | n_2 | \cdots | n_k$

**의미**: Every such group is (internal/external) direct product of cyclic groups

**Alternative form** (primary decomposition):

$$G \cong \mathbb{Z}^r \oplus \mathbb{Z}/p_1^{e_1}\mathbb{Z} \oplus \cdots \oplus \mathbb{Z}/p_m^{e_m}\mathbb{Z}$$

where $p_i$ are primes (not necessarily distinct)

---

# <span class="header-examples">Examples</span>

## Example 1: Klein Four-Group

**External construction**:

$$V_4 = \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$$

**Elements**: $\{(0,0), (0,1), (1,0), (1,1)\}$

**Operation table**:

| $\cdot$ | $(0,0)$ | $(1,0)$ | $(0,1)$ | $(1,1)$ |
|---------|---------|---------|---------|---------|
| $(0,0)$ | $(0,0)$ | $(1,0)$ | $(0,1)$ | $(1,1)$ |
| $(1,0)$ | $(1,0)$ | $(0,0)$ | $(1,1)$ | $(0,1)$ |
| $(0,1)$ | $(0,1)$ | $(1,1)$ | $(0,0)$ | $(1,0)$ |
| $(1,1)$ | $(1,1)$ | $(0,1)$ | $(1,0)$ | $(0,0)$ |

**Properties**:
- Abelian ✓
- Every non-identity element has order 2
- Not cyclic

## Example 2: $\mathbb{Z}/6\mathbb{Z}$ as Direct Product

**Internal decomposition**:

$$\mathbb{Z}/6\mathbb{Z} \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$$

**Subgroups**:
- $H_1 = \{0, 3\} \cong \mathbb{Z}/2\mathbb{Z}$
- $H_2 = \{0, 2, 4\} \cong \mathbb{Z}/3\mathbb{Z}$

**Verification**:
- $H_1 \cap H_2 = \{0\}$ ✓
- $|H_1| \cdot |H_2| = 2 \cdot 3 = 6 = |\mathbb{Z}/6\mathbb{Z}|$ ✓
- Both normal (abelian group) ✓

**Chinese Remainder Theorem**: General principle

## Example 3: $\mathbb{Z}/4\mathbb{Z} \not\cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$

**Why not isomorphic?**

- $\mathbb{Z}/4\mathbb{Z}$ is cyclic (has element of order 4)
- $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$ has no element of order 4

**Element orders in $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$**:
- $(0,0)$: order 1
- $(1,0), (0,1), (1,1)$: order 2

**Conclusion**: NOT isomorphic ✗

## Example 4: $\mathbb{R}^2$ as Direct Product

**External**:

$$\mathbb{R}^2 = \mathbb{R} \times \mathbb{R}$$

(additive group)

**Internal**: 

$$\mathbb{R}^2 = H_1 \times H_2$$

where:
- $H_1 = \{(x, 0) : x \in \mathbb{R}\}$ (x-axis)
- $H_2 = \{(0, y) : y \in \mathbb{R}\}$ (y-axis)

**Verification**: Every $(x, y) = (x, 0) + (0, y)$ uniquely ✓

## Example 5: Quaternion Group NOT Direct Product

**$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$**

**Claim**: $Q_8$ is NOT internal direct product of proper subgroups

**Reason**: 
- All proper subgroups have order dividing 4
- Cannot satisfy $H_1 \cap H_2 = \{e\}$ with $|H_1| \cdot |H_2| = 8$

**Conclusion**: Some groups cannot be decomposed ✗

## Example 6: Dihedral Group $D_8$

**$D_8$ = Symmetries of square**

Can write as internal direct product? 

**Answer**: No (similar to $Q_8$)

But can write: $D_8 \cong \mathbb{Z}/4\mathbb{Z} \rtimes \mathbb{Z}/2\mathbb{Z}$ (semi-direct product^[반직접곱])

## Example 7: Torus $T^2 = S^1 \times S^1$

**Topological direct product**:

$$T^2 = S^1 \times S^1$$

**As groups** (fundamental group**^[기본군]):

$$\pi_1(T^2) = \pi_1(S^1) \times \pi_1(S^1) \cong \mathbb{Z} \times \mathbb{Z} = \mathbb{Z}^2$$

**Homology**:

$$H_1(T^2) = \mathbb{Z} \oplus \mathbb{Z}$$

## Example 8: Infinite Direct Sum vs Product

**Direct sum**:

$$\bigoplus_{i=1}^\infty \mathbb{Z} = \{(a_1, a_2, \ldots) : a_i \in \mathbb{Z}, \text{ finitely many non-zero}\}$$

**Direct product**:

$$\prod_{i=1}^\infty \mathbb{Z} = \{(a_1, a_2, \ldots) : a_i \in \mathbb{Z}\}$$

**Difference**: $(1, 1, 1, \ldots) \in \prod$ but $\notin \bigoplus$

**Properties**:
- $\bigoplus$ is countable
- $\prod$ is uncountable (by Cantor diagonal argument)

---

# <span class="header-remark">Remark</span>

## External vs Internal: Conceptual Difference

**External direct product**:
- Start with separate groups
- Build new group from scratch
- Cartesian product construction

**Internal direct product**:
- Start with one group
- Decompose into subgroups
- Recognition problem

**Connection**: Isomorphic when conditions met!

$$\text{External: } G_1 \times G_2 \quad \cong \quad \text{Internal: } H_1 \times H_2 \subseteq G$$

## When Can Groups Be Decomposed?

**Question**: Given group $G$, when is $G \cong H_1 \times H_2$ for proper subgroups?

**Necessary**:
- Must have normal subgroups $H_1, H_2$ satisfying conditions
- $|H_1| \cdot |H_2| = |G|$ (if finite)

**Not always possible**:
- Simple groups (no non-trivial normal subgroups)
- Groups like $Q_8$, $D_8$ (no suitable decomposition)

**Abelian groups**: Always decompose (by Fundamental Theorem)

## Notation Conventions

### Group Theory

**Direct product**: $G_1 \times G_2 \times \cdots \times G_n$

Used for both external and internal (context clarifies)

### Abelian Groups / Modules

**Direct sum**: $G_1 \oplus G_2 \oplus \cdots \oplus G_n$

Emphasizes additive notation

**For finite case**: $\times$ and $\oplus$ are the same

**For infinite case**: $\oplus \subsetneq \times$

### Category Theory

**Product**: $\prod_{i \in I} G_i$ (universal property)

**Coproduct**: $\coprod_{i \in I} G_i$ (for groups = free product**^[자유곱])

**Note**: In category of abelian groups, coproduct = direct sum

## Direct Sum vs Direct Product (Infinite)

**Key difference**: Finite support**^[유한 지지]

| Property | Direct Sum $\bigoplus$ | Direct Product $\prod$ |
|----------|------------------------|------------------------|
| Elements | Finitely many non-zero | Arbitrary components |
| Generators | Yes | Not always |
| Countable | If each $G_i$ countable | Not always |
| Universal property | Coproduct | Product |

**Example**: $\displaystyle\bigoplus_{i=1}^\infty \mathbb{Z}$ is free abelian of countable rank

## Chinese Remainder Theorem

**정리** (CRT for Groups):

If $\gcd(m, n) = 1$, then

$$\mathbb{Z}/mn\mathbb{Z} \cong \mathbb{Z}/m\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$$

**Generalization**:

$$\mathbb{Z}/n\mathbb{Z} \cong \mathbb{Z}/p_1^{e_1}\mathbb{Z} \times \cdots \times \mathbb{Z}/p_k^{e_k}\mathbb{Z}$$

where $n = p_1^{e_1} \cdots p_k^{e_k}$ (prime factorization)

**Connection**: Internal direct product decomposition of cyclic groups

## Semi-direct Product^[반직접곱]

**Generalization**: When normality condition relaxed

$$G = H \rtimes K$$

**Conditions**:
- $H \trianglelefteq G$ (only $H$ normal, not $K$)
- $G = HK$
- $H \cap K = \{e\}$

**Example**: $D_n \cong \mathbb{Z}/n\mathbb{Z} \rtimes \mathbb{Z}/2\mathbb{Z}$

**Difference**: Elements from $H$ and $K$ may not commute

## Applications

### 1. Classifying Finite Abelian Groups

**Fundamental Theorem**: Every finite abelian group is direct product of cyclic groups

**Example**: All abelian groups of order 12:
- $\mathbb{Z}/12\mathbb{Z}$
- $\mathbb{Z}/6\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$
- $\mathbb{Z}/4\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$
- $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$

### 2. Cryptography

**RSA Algorithm**: Uses $\mathbb{Z}/n\mathbb{Z} \cong \mathbb{Z}/p\mathbb{Z} \times \mathbb{Z}/q\mathbb{Z}$ for primes $p, q$

### 3. Representation Theory

**Tensor products**: $V_1 \otimes V_2$ for representations

Related to direct products of groups

### 4. Algebraic Topology

**Fundamental groups**: $\pi_1(X \times Y) \cong \pi_1(X) \times \pi_1(Y)$

**Homology**: Künneth formula relates $H_*(X \times Y)$ to $H_*(X) \otimes H_*(Y)$

## Module Theory Generalization

**Direct sum of modules**: $M_1 \oplus M_2 \oplus \cdots \oplus M_n$

**Properties**:
- Universal property (coproduct in $R$-Mod)
- Free modules: $R^n = \bigoplus_{i=1}^n R$

**Structure theorem**: Finitely generated modules over PID

## Categorical Perspective

**Product in category**: Universal object with projections

**Coproduct in category**: Universal object with injections

**In $\mathbf{Grp}$ (groups)**:
- Product = direct product $\prod$
- Coproduct = free product $*$

**In $\mathbf{Ab}$ (abelian groups)**:
- Product = direct product $\prod$
- Coproduct = direct sum $\bigoplus$

**Special**: In $\mathbf{Ab}$, finite product $=$ finite coproduct

## 관련 개념

- [[Group Theory]]: 기본 구조
- [[Normal Subgroup]]: Internal direct product 조건
- [[Quotient Group]]: $G/H_1 \cong H_2$ in direct product
- [[Cyclic Group]]: Building blocks of abelian groups
- [[Chinese Remainder Theorem]]: Special case of direct product
- [[Semi-direct Product]]: 일반화
- [[Free Product]]: Non-abelian "sum"
- [[Tensor Product]]: Bilinear analog
- [[Universal Property]]: Categorical characterization

