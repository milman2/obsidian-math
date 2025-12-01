# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Ring]]
- [[Linear mapping]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Lang, Algebra

---

# <span class="header-definition">Definition</span>

## Direct Sum^[직접합] vs Direct Product^[직접곱]

**직관**: 여러 대수 구조를 "독립적으로" 결합

**표기**:
- **Direct sum^[직접합]**: $G_1 \oplus G_2 \oplus \cdots \oplus G_n$ (유한합, 또는 성분이 finitely supported)
- **Direct product^[직접곱]**: $G_1 \times G_2 \times \cdots \times G_n$ (일반적)

**주의**: Finite case에서는 $\oplus$와 $\times$가 같지만, infinite case에서는 다름!

## Direct Product of Groups^[군의 직접곱]

Groups $G_1, G_2, \ldots, G_n$의 **direct product^[직접곱]** $G_1 \times G_2 \times \cdots \times G_n$:

### Set^[집합]

$$G_1 \times G_2 \times \cdots \times G_n = \{(g_1, g_2, \ldots, g_n) : g_i \in G_i\}$$

Cartesian product^[데카르트 곱]

### Operation^[연산]

$$(g_1, g_2, \ldots, g_n) \cdot (h_1, h_2, \ldots, h_n) = (g_1h_1, g_2h_2, \ldots, g_nh_n)$$

**Component-wise^[성분별] 연산**

### Group Structure

- **Identity**: $(e_1, e_2, \ldots, e_n)$
- **Inverse**: $(g_1, g_2, \ldots, g_n)^{-1} = (g_1^{-1}, g_2^{-1}, \ldots, g_n^{-1})$
- **Order**: $|G_1 \times G_2 \times \cdots \times G_n| = |G_1| \cdot |G_2| \cdots |G_n|$

## Direct Sum of Abelian Groups^[아벨군의 직접합]

Abelian groups $G_1, G_2, \ldots$의 **direct sum^[직접합]**:

### Finite Case^[유한 경우]

$$G_1 \oplus G_2 \oplus \cdots \oplus G_n = G_1 \times G_2 \times \cdots \times G_n$$

Finite case에서는 direct product와 같음

### Infinite Case^[무한 경우]

$$\bigoplus_{i \in I} G_i = \{(g_i)_{i \in I} : g_i \in G_i, \text{ finitely many } g_i \neq 0\}$$

**핵심 차이**: 유한개를 제외한 모든 성분이 0 (finitely supported^[유한 지지])

**반면 Direct Product**:
$$\prod_{i \in I} G_i = \{(g_i)_{i \in I} : g_i \in G_i\}$$
(모든 성분 허용)

### Relationship

$$\bigoplus_{i \in I} G_i \subseteq \prod_{i \in I} G_i$$

Direct sum은 direct product의 subgroup

## Direct Sum of Vector Spaces^[벡터 공간의 직접합]

Vector spaces $V_1, V_2, \ldots, V_n$ over field $\mathbb{F}$의 **direct sum^[직접합]**:

### External Direct Sum^[외부 직접합]

$$V_1 \oplus V_2 \oplus \cdots \oplus V_n = \{(v_1, v_2, \ldots, v_n) : v_i \in V_i\}$$

**Operations**:
- Addition: $(v_1, \ldots, v_n) + (w_1, \ldots, w_n) = (v_1+w_1, \ldots, v_n+w_n)$
- Scalar multiplication: $c(v_1, \ldots, v_n) = (cv_1, \ldots, cv_n)$

**Dimension**:
$$\dim(V_1 \oplus \cdots \oplus V_n) = \dim(V_1) + \cdots + \dim(V_n)$$

### Internal Direct Sum^[내부 직접합]

Vector space $V$와 subspaces $W_1, W_2, \ldots, W_n$에 대해:

$V$가 $W_1, \ldots, W_n$의 **internal direct sum^[내부 직접합]**이다 (기호: $V = W_1 \oplus \cdots \oplus W_n$) $\Leftrightarrow$

1. $V = W_1 + W_2 + \cdots + W_n$ (span)
2. 표현의 유일성: 모든 $v \in V$는 유일하게 $v = w_1 + \cdots + w_n$ ($w_i \in W_i$)로 표현

### Equivalent Conditions^[동등 조건]

$V = W_1 \oplus \cdots \oplus W_n$ $\Leftrightarrow$ 다음 중 하나:

1. $W_i \cap (W_1 + \cdots + W_{i-1} + W_{i+1} + \cdots + W_n) = \{0\}$ for all $i$
2. $\dim(V) = \dim(W_1) + \cdots + \dim(W_n)$ and $V = W_1 + \cdots + W_n$
3. 각 $W_i$의 basis를 합치면 $V$의 basis가 됨

## Projection and Inclusion^[사영과 포함]

Direct sum $G = G_1 \oplus G_2 \oplus \cdots \oplus G_n$에 대해:

### Projection Maps^[사영 사상]

$$\pi_i: G \to G_i, \quad \pi_i(g_1, g_2, \ldots, g_n) = g_i$$

**성질**:
- Homomorphism (surjective)
- $\ker(\pi_i) = G_1 \oplus \cdots \oplus G_{i-1} \oplus \{e\} \oplus G_{i+1} \oplus \cdots \oplus G_n$

### Inclusion Maps^[포함 사상]

$$\iota_i: G_i \to G, \quad \iota_i(g_i) = (e_1, \ldots, e_{i-1}, g_i, e_{i+1}, \ldots, e_n)$$

**성질**:
- Homomorphism (injective)
- $\text{im}(\iota_i) = \{e\} \oplus \cdots \oplus G_i \oplus \cdots \oplus \{e\}$

### Relationships

$$\pi_i \circ \iota_i = \text{id}_{G_i}$$

$$\pi_i \circ \iota_j = 0 \text{ if } i \neq j$$

## Universal Property^[보편성질]

Direct sum의 **universal property^[보편성질]**:

Homomorphisms $\phi_i: G_i \to H$가 주어졌을 때, 유일한 homomorphism $\Phi: G_1 \oplus \cdots \oplus G_n \to H$ 존재하여:

$$\Phi(g_1, \ldots, g_n) = \phi_1(g_1) + \cdots + \phi_n(g_n)$$

즉, $\Phi \circ \iota_i = \phi_i$ for all $i$

**다이어그램**:

```
G_i --φᵢ-→ H
 |       ↗
ιᵢ     Φ
 ↓   ↗
⊕Gⱼ
```

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}^n$

$$\mathbb{Z}^n = \underbrace{\mathbb{Z} \oplus \mathbb{Z} \oplus \cdots \oplus \mathbb{Z}}_{n \text{ times}}$$

**원소**: $(a_1, a_2, \ldots, a_n)$ where $a_i \in \mathbb{Z}$

**연산**: Component-wise addition

**구조**: Free abelian group of rank $n$

## Example 2: $\mathbb{R}^n$

$$\mathbb{R}^n = \underbrace{\mathbb{R} \oplus \mathbb{R} \oplus \cdots \oplus \mathbb{R}}_{n \text{ times}}$$

**Vector space structure**: Standard $n$-dimensional Euclidean space

**Basis**: $\{e_1, e_2, \ldots, e_n\}$ where $e_i = (0, \ldots, 0, 1, 0, \ldots, 0)$

## Example 3: Cyclic Groups

$$C_2 \times C_3 \cong C_6$$

**이유**: $\gcd(2, 3) = 1$

**일반화**: $C_m \times C_n \cong C_{mn}$ $\Leftrightarrow$ $\gcd(m, n) = 1$

**반례**: $C_2 \times C_2 \not\cong C_4$ (모든 원소가 order $\leq 2$)

## Example 4: Klein Four-Group

$$V_4 = C_2 \times C_2 = \{(0,0), (1,0), (0,1), (1,1)\}$$

Direct product of two cyclic groups of order 2

**성질**: 
- Abelian
- 모든 non-identity 원소가 order 2
- Not cyclic

## Example 5: Fundamental Theorem of Finite Abelian Groups

모든 finite abelian group은 cyclic groups의 direct sum:

$$G \cong C_{p_1^{a_1}} \oplus C_{p_2^{a_2}} \oplus \cdots \oplus C_{p_r^{a_r}}$$

**예**: $|G| = 12$
- $C_{12} \cong C_4 \oplus C_3$
- $C_2 \oplus C_2 \oplus C_3$

자세한 내용은 [[Group]], [[Isomorphism]] 참조

## Example 6: Vector Space Decomposition

$$\mathbb{C}^n = \mathbb{R}^n \oplus i\mathbb{R}^n$$

Internal direct sum:
- Real part: $\mathbb{R}^n$
- Imaginary part: $i\mathbb{R}^n$

모든 $z \in \mathbb{C}^n$는 유일하게 $z = x + iy$ ($x, y \in \mathbb{R}^n$)

## Example 7: Eigenspace Decomposition

Linear operator $T: V \to V$가 diagonalizable^[대각화가능]이면:

$$V = E_{\lambda_1} \oplus E_{\lambda_2} \oplus \cdots \oplus E_{\lambda_k}$$

where $E_{\lambda_i}$는 eigenvalue^[고유값] $\lambda_i$에 대한 eigenspace^[고유공간]

자세한 내용은 [[Linear mapping]] 참조

## Example 8: Polynomial Ring

$$\mathbb{R}[x] \text{ vs } \bigoplus_{n=0}^\infty \mathbb{R}$$

**Direct sum** (as abelian group):
$$\mathbb{R}[x] \cong \bigoplus_{n=0}^\infty \mathbb{R}$$

각 polynomial은 유한 차수 (finitely many non-zero coefficients)

**Not direct product**: $\displaystyle\prod_{n=0}^\infty \mathbb{R}$는 무한 급수 포함 (not polynomials)

## Example 9: Matrix Blocks

$$M_n(\mathbb{R}) = M_k(\mathbb{R}) \oplus M_{n-k}(\mathbb{R})$$

Block diagonal matrices:
$$\left\{\begin{pmatrix} A & 0 \\ 0 & B \end{pmatrix} : A \in M_k, B \in M_{n-k}\right\}$$

(as vector spaces, not as rings!)

## Example 10: Direct Sum vs Direct Product (Infinite)

$$\bigoplus_{i=1}^\infty \mathbb{Z} \subsetneq \prod_{i=1}^\infty \mathbb{Z}$$

**Direct sum**: $(1, 0, 0, 0, \ldots) \in \bigoplus$

**Direct product**: $(1, 1, 1, 1, \ldots) \in \prod$ but $\notin \bigoplus$

**크기**:
- $\left|\bigoplus_{i=1}^\infty \mathbb{Z}\right| = \aleph_0$ (countable)
- $\left|\prod_{i=1}^\infty \mathbb{Z}\right| = 2^{\aleph_0}$ (uncountable)

---

# <span class="header-properties">Properties</span>

## Commutativity and Associativity^[교환법칙과 결합법칙]

### Commutativity

$$G_1 \oplus G_2 \cong G_2 \oplus G_1$$

**Isomorphism**: $(g_1, g_2) \mapsto (g_2, g_1)$

### Associativity

$$(G_1 \oplus G_2) \oplus G_3 \cong G_1 \oplus (G_2 \oplus G_3) \cong G_1 \oplus G_2 \oplus G_3$$

**Isomorphism**: $((g_1, g_2), g_3) \mapsto (g_1, (g_2, g_3)) \mapsto (g_1, g_2, g_3)$

## Direct Summands^[직접 성분]

$G = H \oplus K$일 때:

### 1. $H, K \triangleleft G$ (Normal Subgroups)

Direct summands는 normal subgroups (abelian groups의 경우)

### 2. $H \cap K = \{e\}$

Intersection은 trivial

### 3. $HK = G$

Every element can be written as $hk$

### 4. Commutativity

$hk = kh$ for all $h \in H, k \in K$

**역**: 이 조건들이 만족되면 $G \cong H \oplus K$ (in abelian groups)

## Homomorphisms and Direct Sums^[준동형사상과 직접합]

### Homomorphism to Direct Sum

$$\text{Hom}(G, H_1 \oplus H_2) \cong \text{Hom}(G, H_1) \times \text{Hom}(G, H_2)$$

**의미**: $G$에서 direct sum으로의 homomorphism은 각 성분으로의 homomorphism 쌍

### Homomorphism from Direct Sum

$$\text{Hom}(G_1 \oplus G_2, H) \cong \text{Hom}(G_1, H) \times \text{Hom}(G_2, H)$$

(abelian groups의 경우)

## Subgroups of Direct Sums^[직접합의 부분군]

### Direct Summands

$H \leq G_1 \oplus G_2$가 다음 형태면 **direct summand^[직접 성분]**:

$$H = H_1 \oplus H_2 \text{ where } H_i \leq G_i$$

### Not All Subgroups are Direct Summands

**반례**: $\mathbb{Z}^2 = \mathbb{Z} \oplus \mathbb{Z}$에서

$$H = \{(n, 2n) : n \in \mathbb{Z}\} \leq \mathbb{Z}^2$$

$H$는 subgroup이지만 $H_1 \oplus H_2$ 형태가 아님

## Direct Sum Decomposition^[직접합 분해]

### Unique Decomposition?

**질문**: Direct sum 분해가 유일한가?

**답**: 일반적으로 **아니오**

**예**: $\mathbb{Z}^2$
$$\mathbb{Z}^2 = \mathbb{Z} \oplus \mathbb{Z} = \langle(1,0)\rangle \oplus \langle(0,1)\rangle$$
$$\mathbb{Z}^2 = \langle(1,0)\rangle \oplus \langle(1,1)\rangle$$

Different decompositions!

### Indecomposable^[기약]

Group $G$가 **indecomposable^[기약]**이다 $\Leftrightarrow$

$$G = H \oplus K \Rightarrow H = \{e\} \text{ or } K = \{e\}$$

Non-trivial direct sum 분해 불가능

**예**: $\mathbb{Z}$, $C_p$ (prime $p$)는 indecomposable

## Krull-Schmidt Theorem^[크룰-슈미트 정리]

Finitely generated abelian group $G$에 대해:

$$G \cong H_1 \oplus \cdots \oplus H_m \cong K_1 \oplus \cdots \oplus K_n$$

where all $H_i, K_j$는 indecomposable이면:

1. $m = n$
2. (적절한 순서 변경 후) $H_i \cong K_i$

**의미**: Indecomposable factors로의 분해는 본질적으로 유일

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Direct Sum/Product**: "독립적인 구조들을 나란히 놓기"

**메타포**:
- **Apartment building**: 각 층(component)이 독립적
- **Parallel universes**: 각각 독립적으로 작동
- **Coordinate system**: 각 축이 독립적

**핵심**: 
- 각 component는 독립적으로 작동
- 전체는 parts의 "합"

## Direct Sum vs Direct Product

### Finite Case

$$G_1 \oplus G_2 \oplus \cdots \oplus G_n = G_1 \times G_2 \times \cdots \times G_n$$

**완전히 같음!** 표기법만 다름

### Infinite Case

| | **Direct Sum** $\bigoplus$ | **Direct Product** $\prod$ |
|---|---|---|
| 원소 | Finitely supported | 모든 sequences |
| 크기 | Countable (often) | Uncountable (often) |
| 예 | Polynomials | Power series |
| 표기 선호 | Vector spaces, Modules | General groups |

**기억**: Sum은 finite, Product는 infinite를 허용

## Internal vs External Direct Sum

### External^[외부]

$$V_1 \oplus V_2 = \{(v_1, v_2) : v_i \in V_i\}$$

새로운 구조를 **구성** (튜플)

### Internal^[내부]

$$V = W_1 \oplus W_2 \text{ where } W_i \subseteq V$$

기존 구조를 **분해** (decomposition)

**관계**: External $\cong$ Internal (canonical isomorphism)

$$V_1 \oplus V_2 \cong V_1 + V_2 \text{ (in } V)$$

## 표기법

| 표기 | 의미 |
|------|------|
| $G_1 \oplus G_2$ | Direct sum |
| $G_1 \times G_2$ | Direct product (또는 Cartesian product) |
| $\bigoplus_{i \in I} G_i$ | Infinite direct sum |
| $\displaystyle\prod_{i \in I} G_i$ | Infinite direct product |
| $G = H \oplus K$ | Internal direct sum |

## When to Use $\oplus$ vs $\times$?

### Use $\oplus$ (Direct Sum)

- Abelian groups (관례)
- Vector spaces (항상)
- Modules
- Emphasis on "finite support" (infinite case)

### Use $\times$ (Direct Product)

- General groups (non-abelian)
- Sets (Cartesian product)
- Topological spaces
- General "product" concept

**혼용 주의**: 문헌마다 다를 수 있음!

## Category Theory 관점

**Direct sum = Coproduct + Product**

Category에 따라:
- **Groups**: Coproduct ≠ Product (general)
- **Abelian Groups**: Coproduct = Product (finite)
- **Vector Spaces**: Coproduct = Product

자세한 내용은 [[Category Theory]] 참조

## Common Pitfall^[흔한 실수]

### 1. $C_m \times C_n \cong C_{mn}$?

✗ 항상 성립하는 것은 아님!

 $\gcd(m, n) = 1$일 때만

**반례**: $C_2 \times C_2 \not\cong C_4$

### 2. Internal direct sum 판정

✗ $V = W_1 + W_2$이면 $V = W_1 \oplus W_2$?

✓ 추가 조건 필요: $W_1 \cap W_2 = \{0\}$

**반례**: $\mathbb{R}^2 = \text{span}\{(1,0)\} + \text{span}\{(1,1)\}$
- $\text{span}\{(1,0)\} \cap \text{span}\{(1,1)\} = \{0\}$ - 하지만 두 번째 조건에서: $(0,1) \notin$ span!

### 3. Subgroups of direct sums

✗ $H \leq G_1 \oplus G_2 \Rightarrow H = H_1 \oplus H_2$?

✓ 모든 subgroup이 direct summand인 것은 아님!

### 4. Uniqueness of decomposition

✗ Direct sum 분해가 유일?

✓ Indecomposable factors로 분해하면 "본질적으로" 유일 (Krull-Schmidt)

### 5. $\oplus$ always = $\times$?

✗ Infinite case에서 다름!

 Finite case에서만 같음

## 응용

**대수학**:
- Group structure classification
- Module theory
- Representation theory

**선형대수**:
- Eigenspace decomposition
- Jordan canonical form
- Spectral theorem

**위상수학**:
- Homology groups
- Fundamental groups

**범함수 해석학**:
- Hilbert space decomposition
- Direct integral

## 관련 개념

- [[Group]]: Direct product of groups
- [[Isomorphism]]: Structure preservation
- [[Linear mapping]]: Eigenspace decomposition
- [[Category Theory]]: Products and coproducts

## 추가 학습 주제

**기초**:
- Direct sum properties
- Internal vs external
- Projections and inclusions

**중급**:
- Semidirect product
- Tensor product
- Free products

**고급**:
- Direct limits and inverse limits
- Krull-Schmidt theorem
- Category-theoretic products

