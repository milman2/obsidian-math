# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Homomorphism]]
- [[Isomorphism]]
- [[Permutation Group]]
- [[Symmetric Group]]
- [[Group Action]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Rotman, An Introduction to the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Cayley's Theorem^[케일리 정리]

**정리**: 모든 group은 어떤 symmetric group의 subgroup과 isomorphic하다

$$\forall G, \; \exists X : G \cong H \leq \text{Sym}(X)$$

**구체적으로**: $G$를 $X = G$ (자기 자신)로 선택하면

$$G \hookrightarrow \text{Sym}(G)$$

**Finite case**: Order $n$인 group $G$는

$$G \cong H \leq S_n$$

for some subgroup $H$ of $S_n$

## Left Regular Representation^[왼쪽 정칙 표현]

**정의**: $\lambda: G \to \text{Sym}(G)$

$$\lambda(g)(h) = gh \quad \forall g, h \in G$$

즉, $\lambda(g)$는 left multiplication by $g$

**Alternative notation**: $L_g : G \to G$, $L_g(h) = gh$

### 성질

1. **Homomorphism**: $\lambda(g_1 g_2) = \lambda(g_1) \circ \lambda(g_2)$
2. **Injective**: $\ker(\lambda) = \{e\}$
3. **Image**: $\lambda(G) \leq \text{Sym}(G)$

**결론**: $G \cong \lambda(G)$ ✓

## Right Regular Representation^[오른쪽 정칙 표현]

**정의**: $\rho: G \to \text{Sym}(G)$

$$\rho(g)(h) = hg^{-1} \quad \forall g, h \in G$$

**주의**: $g^{-1}$ 필요 (homomorphism 되려면)

**성질**: 동일하게 injective homomorphism

**관계**: $\rho(g) = \lambda(g^{-1})$

---

# <span class="header-proof">Proof</span>

## Cayley's Theorem 증명

### Step 1: $\lambda$가 well-defined

$g \in G$에 대해 $\lambda(g): G \to G$

**Bijection 확인**:
- **Injective**: $\lambda(g)(h_1) = \lambda(g)(h_2) \Rightarrow gh_1 = gh_2 \Rightarrow h_1 = h_2$ ✓
- **Surjective**: $\forall h \in G, \; \lambda(g)(g^{-1}h) = h$ ✓

따라서 $\lambda(g) \in \text{Sym}(G)$ ✓

### Step 2: $\lambda$는 homomorphism

$$\lambda(g_1 g_2)(h) = (g_1 g_2)h = g_1(g_2 h) = \lambda(g_1)(g_2 h) = \lambda(g_1)(\lambda(g_2)(h))$$

$$= (\lambda(g_1) \circ \lambda(g_2))(h)$$

따라서 $\lambda(g_1 g_2) = \lambda(g_1) \circ \lambda(g_2)$ ✓

### Step 3: $\lambda$는 injective

$$\ker(\lambda) = \{g \in G : \lambda(g) = \text{id}_G\}$$

$$= \{g \in G : gh = h \; \forall h \in G\}$$

$$= \{g \in G : g = e\} = \{e\}$$

따라서 $\lambda$ injective ✓

### Step 4: First Isomorphism Theorem

$$G / \ker(\lambda) \cong \text{im}(\lambda)$$

$\ker(\lambda) = \{e\} \Rightarrow G \cong \lambda(G) \leq \text{Sym}(G)$ ✓

자세한 내용은 [[Isomorphism]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Cyclic Group $\mathbb{Z}/3\mathbb{Z}$

$G = \{[0], [1], [2]\}$ with addition

**Left regular representation**:

$$\lambda([0]) = \text{id} = \begin{pmatrix} [0] & [1] & [2] \\ [0] & [1] & [2] \end{pmatrix}$$

$$\lambda([1]) = \begin{pmatrix} [0] & [1] & [2] \\ [1] & [2] & [0] \end{pmatrix} = (012) \text{ in cycle notation}$$

$$\lambda([2]) = \begin{pmatrix} [0] & [1] & [2] \\ [2] & [0] & [1] \end{pmatrix} = (021)$$

**Image**: $\lambda(\mathbb{Z}/3\mathbb{Z}) = \langle (012) \rangle \leq S_3$

**확인**: $\mathbb{Z}/3\mathbb{Z} \cong \langle (012) \rangle$ ✓

자세한 내용은 [[Cyclic Group]] 참조

## Example 2: Klein Four-Group $V_4$

$V_4 = \{e, a, b, c\}$ where $a^2 = b^2 = c^2 = e$, $ab = c$

**Elements as permutations**:

$$\lambda(e) = \text{id}$$

$$\lambda(a) = (bc) \quad (a \text{ swaps } b \text{ and } c, \text{ fixes } e, a)$$

$$\lambda(b) = (ac)$$

$$\lambda(c) = (ab)$$

**Image**: $\lambda(V_4) = \{e, (bc), (ac), (ab)\} \leq S_4$

**확인**: 이것은 $V_4$와 isomorphic (자기 자신의 permutation 표현)

## Example 3: $S_3$ itself

$S_3$ acts on itself by left multiplication

**Embedding**: $S_3 \hookrightarrow \text{Sym}(S_3) \cong S_6$

**주의**: $|S_3| = 6$이므로 $\text{Sym}(S_3) \cong S_6$

**Cayley's theorem**: $S_3 \cong H \leq S_6$ for some $H$

**하지만**: $S_3$는 이미 permutation group!

**Identity embedding**: $S_3 \leq S_3$ (trivial)

**교훈**: Cayley's theorem은 항상 작동하지만, 항상 "useful"은 아님

자세한 내용은 [[Symmetric Group]] 참조

## Example 4: Dihedral Group $D_3$

$D_3 = \{e, r, r^2, s, sr, sr^2\}$ (order 6)

$D_3 \cong S_3$ (dihedral group of triangle = $S_3$)

**Cayley embedding**: $D_3 \hookrightarrow S_6$

**Better embedding**: $D_3$ acts on vertices $\{1,2,3\}$ $\Rightarrow$ $D_3 \hookrightarrow S_3$

**실제로**: $D_3 = S_3$ (동형)

자세한 내용은 [[Dihedral Group]] 참조

## Example 5: Infinite Group $\mathbb{Z}$

$\mathbb{Z}$ acts on itself by translation

$$\lambda(n)(m) = n + m$$

**Image**: $\lambda(\mathbb{Z}) \leq \text{Sym}(\mathbb{Z})$

**성질**:
- Free action (no fixed points except $n=0$)
- Transitive (one orbit)
- $\mathbb{Z} \cong \lambda(\mathbb{Z})$ ✓

**주의**: $\text{Sym}(\mathbb{Z})$는 infinite!

## Example 6: Quaternion Group $Q_8$

$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$ (order 8)

**Cayley embedding**: $Q_8 \hookrightarrow S_8$

**Multiplication table로** left regular representation 구성

**특징**: $Q_8$는 non-abelian, no element of order 4는 잘못됨 (사실 $i, j, k$ order 4)

Actually $Q_8$는 order 8이고, $i^2 = j^2 = k^2 = -1$, $i^4 = 1$

**Better representation**: Matrix groups (not via Cayley)

---

# <span class="header-properties">Properties</span>

## Consequences of Cayley's Theorem

### 1. Every Finite Group is a Permutation Group

Group theory $\subseteq$ Study of permutations

**Reduction**: 모든 finite group 문제 → Permutation group 문제

### 2. Concrete Realization

**Abstract group** → **Concrete permutations**

Cayley table → Permutation representation

### 3. Size Bound

Order $n$ group embeds in $S_n$

$$G \hookrightarrow S_n \quad (|G| = n)$$

**하지만**: 보통 더 작은 symmetric group에 embedding 가능

### 4. Regular Action is Faithful and Transitive

**Faithful**: $\ker(\lambda) = \{e\}$

**Transitive**: Single orbit (모든 $g \in G$는 $e$에서 reach 가능)

자세한 내용은 [[Group Action]] 참조

## Left vs Right Regular Representation

**Left**: $\lambda(g)(h) = gh$

**Right**: $\rho(g)(h) = hg^{-1}$

### 관계

$$\rho(g) = \lambda(g^{-1})$$

**증명**: $\rho(g)(h) = hg^{-1} = \lambda(g^{-1})(h)$ ✓

### Images

$$\lambda(G) \cap \rho(G) = ?$$

**Abelian case**: $\lambda(G) = \rho(G)$

**Non-abelian**: Generally $\lambda(G) \cap \rho(G) = \{e\}$? No!

Actually for $D_3$: $\lambda$ and $\rho$ generate different subgroups

## Efficiency of Cayley Embedding

**Question**: $G$ of order $n$이 embed in $S_m$인 최소 $m$?

**Cayley**: $m = n$

**Better**: 보통 $m < n$ 가능

### 예시

**$\mathbb{Z}/4\mathbb{Z}$**:
- Cayley: $m = 4$ ($\mathbb{Z}/4\mathbb{Z} \hookrightarrow S_4$)
- Better: $m = 4$ (실제로 이미 최소)

**$D_n$**:
- Cayley: $m = 2n$ ($D_n \hookrightarrow S_{2n}$)
- Better: $m = n$ ($D_n \hookrightarrow S_n$ by action on vertices)

**General**: Finding minimal $m$은 어려운 문제

## Cayley Graph^[케일리 그래프]

**정의**: Group $G$의 generators $S$에 대한 directed graph

- **Vertices**: Elements of $G$
- **Edges**: $g \to gs$ for $s \in S$

**Visualization**: Group structure를 graph로

**응용**:
- Geometric group theory
- Random walks on groups
- Computational group theory

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Cayley's Theorem = "모든 대칭은 permutation이다"**

### 메타포: 움직임

**Group**: 추상적 "대칭성"

**Permutation**: 구체적 "재배열"

**Cayley**: 모든 대칭을 재배열로 볼 수 있다

### 메타포: 행동으로 정의

사람을 **행동**으로 정의:
- Person = How they transform the world
- Group element = How it permutes the group

## 왜 중요한가?

### 1. Reduction Theorem

**모든 group theory** → **Permutation group theory**

유한군 연구를 permutations로 환원

### 2. Concrete vs Abstract

**추상적 정의** → **구체적 구현**

Cayley table → Explicit permutations

### 3. Historical Significance

**19세기**: Groups = Permutation groups (Galois, Cauchy)

**Cayley**: 추상적 group도 결국 permutations

**현대**: Abstract group theory + Cayley's connection

### 4. 계산 가능성

Computer에서 group 표현:
- Cayley table (size $n^2$)
- Permutation representation (size $n \log n$)

## 한계

### 1. Not Always Efficient

Order $n$ group → $S_n$

하지만 더 작은 representation 가능할 수 있음

**예**: $D_n$ order $2n$ → Can embed in $S_n$ (not $S_{2n}$)

### 2. Loses Structure

Permutation representation는 group structure "숨김"

**예**: $\mathbb{Z}/4\mathbb{Z}$ → 4 permutations
- Cyclic structure not obvious

### 3. Regular Action may not be natural

**Natural actions** often better:
- $D_n$ on vertices of polygon
- $\text{GL}_n$ on vectors
- Galois group on roots

자세한 내용은 [[Group Action]] 참조

## Cayley vs Other Embeddings

| | **Cayley Embedding** | **Natural Action** |
|---|---|---|
| **Exists?** | Always (모든 group) | Depends on group |
| **Size** | $m = n$ (order) | Often $m < n$ |
| **Structure** | Regular (free, transitive) | May have fixed points |
| **Natural?** | No (artificial) | Yes (meaningful) |

**Trade-off**: Cayley는 universal하지만 natural하지 않음

## Permutation Degree

**정의**: Minimal $m$ such that $G \hookrightarrow S_m$

**Notation**: $\deg(G)$

**Bounds**:
- Cayley: $\deg(G) \leq |G|$
- Index theorem: $\deg(G) = [G : H]$ for some $H \leq G$

**Computing $\deg(G)$**: 어려운 문제 (일반적으로)

## 역사적 배경

**Arthur Cayley** (1821-1895):
- 영국 수학자
- 1854: Cayley's theorem 발표
- "On the theory of groups, as depending on the symbolic equation $\theta^n = 1$"
- Abstract group theory의 창시자 중 한 명

**발전**:
- **Before Cayley**: Groups = Permutation groups
- **Cayley**: Abstract groups + Reduction to permutations
- **After**: Abstract group theory 독립적으로 발전

**영향**:
- Group theory를 추상 대수학으로
- Representation theory의 시작
- Modern algebra의 기초

## 응용

**Computational Group Theory**:
- GAP, Magma: Groups를 permutations로 표현
- Algorithms for group operations

**Galois Theory**:
- Galois groups는 roots의 permutations
- Cayley's theorem: Abstract characterization

자세한 내용은 [[Galois Theory]] 참조

**Cryptography**:
- Rubik's cube group
- Puzzle-based cryptosystems

**Combinatorics**:
- Symmetry groups of objects
- Pólya enumeration

## Generalizations

### Representation Theory

**Cayley's theorem**: Permutation representation (special case)

**General representation**: $G \to \text{GL}(V)$ (linear transformations)

**모든 finite group**: Embeds in some $\text{GL}_n(\mathbb{C})$

### Category Theory

**Cayley's theorem**: Every group is a group of automorphisms

**Yoneda lemma**: Every object is representable (category theory 일반화)

자세한 내용은 [[Category Theory]] 참조

## 표기법

| 표기 | 의미 |
|------|------|
| $\lambda$ | Left regular representation |
| $\rho$ | Right regular representation |
| $L_g$ | Left multiplication by $g$ |
| $R_g$ | Right multiplication by $g$ |
| $\text{Sym}(X)$ | Symmetric group on $X$ |
| $S_n$ | Symmetric group (order $n!$) |

## Common Pitfall^[흔한 실수]

### 1. $S_n$ has order $n!$, not $n$

Group of order $n$ embeds in $S_n$ (order $n!$)

Size difference: $n$ vs $n!$

### 2. Regular action ≠ Identity

Embedding $G \hookrightarrow \text{Sym}(G)$ is not trivial

Each $g$ acts as specific permutation

### 3. Right regular representation needs $g^{-1}$

$\rho(g)(h) = hg^{-1}$ (not $hg$!)

이유: Homomorphism 되려면

### 4. Cayley not always optimal

Order $n$ group may embed in $S_m$ with $m < n$

Cayley gives upper bound: $\deg(G) \leq n$

### 5. $G \cong \lambda(G) \leq S_n$

$G$는 $S_n$의 subgroup과 isomorphic ($S_n$ 자체가 아님!)

## 관련 개념

- [[Group Action]]: Regular action is key
- [[Permutation Group]]: Target of embedding
- [[Symmetric Group]]: $S_n$ contains all order $n$ groups
- [[Homomorphism]]: $\lambda$ is injective homomorphism
- [[Isomorphism]]: $G \cong \lambda(G)$

## 추가 학습 주제

**기초**:
- Regular action
- Permutation groups
- Isomorphism theorems

**중급**:
- Cayley graphs
- Permutation degree
- Natural representations

**고급**:
- Representation theory
- Computational group theory
- Geometric group theory

