# <span class="header-prerequisite">Prerequisite</span>
- [[Injective Function]]
- [[Continuous Function]]
- [[Homomorphism]]
- [[Topological Space]]

# <span class="header-reference">Reference</span>
- Munkres, Topology
- Lee, Introduction to Smooth Manifolds
- Aluffi, Algebra: Chapter 0

---

# <span class="header-definition">Definition</span>

## General Concept^[일반 개념]

**Embedding**^[매장/포함 사상]은 한 수학적 구조를 다른 구조 안에 **구조를 보존하며** 포함시키는 사상이다.

**핵심**: Embedding은 항상 injective^[단사]이지만, 단순한 injection보다 **더 강한 조건**을 만족한다.

---

## Topological Embedding^[위상 매장]

### 정의

Topological space^[위상공간] $X$에서 $Y$로의 연속 함수 $f: X \to Y$가 **topological embedding**이다:

$$\Leftrightarrow \begin{cases}
f \text{ is injective} \\
f \text{ is continuous} \\
f: X \to f(X) \text{ is a homeomorphism}
\end{cases}$$

여기서 $f(X)$는 $Y$의 subspace topology^[부분공간 위상]를 갖는다.

**동치 조건**: $f$가 embedding $\Leftrightarrow$ $f$가 injective이고 continuous이며, $f^{-1}: f(X) \to X$가 continuous

**의미**: $X$를 $Y$ 안에 "왜곡 없이" 넣는다

### Open/Closed Embedding

**Open embedding**^[열린 매장]: Topological embedding이고 $f(X)$가 $Y$에서 open^[열린]

**Closed embedding**^[닫힌 매장]: Topological embedding이고 $f(X)$가 $Y$에서 closed^[닫힌]

---

## Algebraic Embedding^[대수적 매장]

### Ring/Field Embedding

**Ring embedding**: Injective ring homomorphism**^[환 준동형사상]

Ring $R$에서 $S$로의 함수 $\phi: R \to S$가 ring embedding이다:

$$\Leftrightarrow \begin{cases}
\phi \text{ is injective} \\
\phi(a + b) = \phi(a) + \phi(b) \\
\phi(ab) = \phi(a)\phi(b) \\
\phi(1_R) = 1_S
\end{cases}$$

**Field embedding**: Field 사이의 injective field homomorphism

**중요**: Field homomorphism은 자동으로 injective! (kernel이 trivial)

**표기**: $F \hookrightarrow K$ (field $F$를 $K$에 embed)

### Group Embedding

**Group embedding**: Injective group homomorphism

Group $G$에서 $H$로의 함수 $f: G \to H$가 group embedding이다:

$$\Leftrightarrow \begin{cases}
f \text{ is injective} \\
f(g_1 g_2) = f(g_1)f(g_2) \text{ for all } g_1, g_2 \in G
\end{cases}$$

**의미**: $G$를 $H$의 subgroup과 isomorphic**^[동형]하게 만든다

---

## Smooth Embedding^[매끄러운 매장]

### 정의 (Differential Geometry)

Smooth manifold^[매끄러운 다양체] $M$에서 $N$으로의 smooth map $f: M \to N$이 **smooth embedding**이다:

$$\Leftrightarrow \begin{cases}
f \text{ is injective} \\
f \text{ is an immersion (}df_p \text{ is injective for all } p \in M\text{)} \\
f: M \to f(M) \text{ is a homeomorphism}
\end{cases}$$

**Immersion vs Embedding**:
- **Immersion**^[몰입]: $df_p$ injective everywhere (tangent map injective)
- **Embedding**: Immersion + topological embedding

---

## Metric Embedding^[거리 매장]

Metric space^[거리 공간] $(X, d_X)$에서 $(Y, d_Y)$로의 함수 $f: X \to Y$가 **isometric embedding**^[등거리 매장]이다:

$$\Leftrightarrow d_Y(f(x_1), f(x_2)) = d_X(x_1, x_2) \text{ for all } x_1, x_2 \in X$$

**약한 버전**: $f$가 **Lipschitz embedding**이면 $\exists c > 0$ such that

$$c \cdot d_X(x_1, x_2) \leq d_Y(f(x_1), f(x_2)) \leq C \cdot d_X(x_1, x_2)$$

---

# <span class="header-properties">Properties</span>

## General Properties

### Composition

**정리**: Embedding의 composition**^[합성]은 embedding이다

$f: X \hookrightarrow Y$, $g: Y \hookrightarrow Z$가 embedding이면 $g \circ f: X \hookrightarrow Z$도 embedding
### Inverse

**정리**: Embedding $f: X \hookrightarrow Y$에 대해 $f^{-1}: f(X) \to X$는 (적절한 구조에서) embedding

## Topological Embedding Properties

### Subspace 특성

**정리**: $f: X \hookrightarrow Y$가 topological embedding이면:

$$U \subset X \text{ is open in } X \Leftrightarrow f(U) \text{ is open in } f(X)$$

**증명**: $f: X \to f(X)$가 homeomorphism이므로 open/closed sets 보존
### Compactness 보존

**정리**: $f: X \hookrightarrow Y$가 embedding이고 $X$가 compact**^[옹골]이면 $f(X)$도 compact

또한 $Y$가 Hausdorff^[하우스도르프]이면 $f(X)$는 closed in $Y$

## Algebraic Embedding Properties

### Structure Preservation

**정리**: Ring embedding $\phi: R \hookrightarrow S$는:
- Ideals의 구조 보존 (일부)
- Units^[단원] 보존: $u \in R^{\times} \Rightarrow \phi(u) \in S^{\times}$

### Extension

**정리** (Field embedding): $\phi: F \hookrightarrow K$가 field embedding이면 $\phi(F) \cong F$는 $K$의 subfield**^[부분체]

---

# <span class="header-examples">Examples</span>

## Example 1: Natural Embeddings

### 수체계의 embedding

$$\mathbb{N} \hookrightarrow \mathbb{Z} \hookrightarrow \mathbb{Q} \hookrightarrow \mathbb{R} \hookrightarrow \mathbb{C}$$

각 단계는 field/ring embedding (또는 additive group embedding)

**Example**: $\mathbb{Q} \hookrightarrow \mathbb{R}$
- Injective ring homomorphism- Dense in $\mathbb{R}$ (topology)
- 대수 구조 완벽히 보존

## Example 2: Circle in Plane

**Standard embedding**: $S^1 \hookrightarrow \mathbb{R}^2$

$$f: S^1 \to \mathbb{R}^2, \quad f(e^{i\theta}) = (\cos\theta, \sin\theta)$$

- Injective- Continuous- Homeomorphism onto image- Topological embedding
## Example 3: Non-embedding

**Counterexample**: $f: [0, 2\pi) \to \mathbb{R}^2$ by $f(t) = (\cos t, \sin t)$

- Injective- Continuous- NOT homeomorphism onto image ✗

**이유**: $[0, 2\pi)$에서 $2\pi$에 가까운 sequence는 수렴하지 않지만, image에서는 $(1, 0)$으로 수렴

따라서 embedding이 아님!

## Example 4: Matrix Embedding

**Embedding**: $\mathbb{C} \hookrightarrow M_2(\mathbb{R})$

$$a + bi \mapsto \begin{pmatrix} a & -b \\ b & a \end{pmatrix}$$

- Injective ring homomorphism- Field 구조 보존- $\mathbb{C} \cong$ Subring of $M_2(\mathbb{R})$

## Example 5: Algebraic Field Extension

**Extension field**: $\mathbb{Q}(\sqrt{2}) \hookrightarrow \mathbb{R}$

$$a + b\sqrt{2} \mapsto a + b\sqrt{2} \quad (a, b \in \mathbb{Q})$$

- Field embedding- $[\mathbb{Q}(\sqrt{2}) : \mathbb{Q}] = 2$
- Preserves all field operations

## Example 6: Graph Embedding

**Graph embedding**: 평면 그래프의 $\mathbb{R}^2$ embedding

Graph $G = (V, E)$를 평면에 그리기 (edge가 교차하지 않게)

- Vertices → Points in $\mathbb{R}^2$
- Edges → Curves (not crossing)

**예**: $K_4$ (complete graph on 4 vertices) → planar graph

$K_5$ → NOT embeddable in $\mathbb{R}^2$ (Kuratowski's theorem)

## Example 7: Möbius Strip

**Embedding**: Möbius strip $M \hookrightarrow \mathbb{R}^3$

$$f: [0, 1] \times [-1, 1] \to \mathbb{R}^3$$

$$(t, s) \mapsto \left((2 + s\cos(\pi t))\cos(2\pi t), (2 + s\cos(\pi t))\sin(2\pi t), s\sin(\pi t)\right)$$

- Smooth embedding- Non-orientable surface in $\mathbb{R}^3$
## Example 8: Cayley's Theorem

**정리** (Cayley): 모든 group $G$는 symmetric group $S_G$에 embed 가능

$$\phi: G \hookrightarrow S_G, \quad g \mapsto (x \mapsto gx)$$

- Injective group homomorphism- $G \cong \text{Subgroup of } S_G$
**의미**: 모든 abstract group은 permutation group으로 realized 가능

---

# <span class="header-remark">Remark</span>

## Embedding vs Injection

**핵심 차이**:

| | Injection | Embedding |
|---|---|---|
| **정의** | $f(x_1) = f(x_2) \Rightarrow x_1 = x_2$ | Injection + 구조 보존 |
| **구조** | 보존 불필요 | 반드시 보존 |
| **역함수** | 정의되지만 연속성 보장 안 됨 | 역함수도 "좋은" 성질 |
| **예** | 모든 embedding | Counter: $[0, 2\pi) \to S^1$ |

**일반 원칙**: 
- 모든 embedding은 injection
- 모든 injection이 embedding은 아님

## Notation

**화살표 표기**:
- $\hookrightarrow$: Embedding (또는 injection)
- $\to$: General map
- $\twoheadrightarrow$: Surjection
- $\xrightarrow{\sim}$: Isomorphism

**LaTeX**: `\hookrightarrow`

## Importance in Category Theory

**Categorical view**: Embedding은 monomorphism**^[단사 사상]의 특수한 경우

**Universal property**: "가장 자연스러운" inclusion

## Applications

### 1. Topology

- Manifold theory: Smooth manifolds를 $\mathbb{R}^n$에 embed
- **Whitney embedding theorem**: 모든 smooth $n$-manifold는 $\mathbb{R}^{2n}$에 embed 가능

### 2. Algebra

- Field extensions: $F \hookrightarrow K$
- Galois theory: Intermediate fields의 lattice
- Cayley's theorem: Abstract groups → Permutation groups

### 3. Analysis

- Function spaces embedding: $L^p \hookrightarrow L^q$ (under conditions)
- Sobolev embedding theorem

### 4. Computer Science

- Graph embedding: Network visualization
- Word embedding: NLP (Word2Vec, GloVe)
- Metric embedding: Approximation algorithms

## Whitney Embedding Theorem

**정리** (Whitney, 1936):

모든 smooth compact $n$-manifold는 $\mathbb{R}^{2n}$에 smoothly embed 가능

**Strong version**: Generic하게 $\mathbb{R}^{2n-1}$에도 embed 가능 (if $n > 1$)

**의미**: Abstract manifold은 항상 Euclidean space의 submanifold로 생각 가능

## Nash Embedding Theorem

**정리** (Nash, 1956):

모든 Riemannian manifold^[리만 다양체]는 어떤 Euclidean space에 isometrically embed 가능

**의미**: Abstract Riemannian geometry는 extrinsic geometry로 realized 가능

## Historical Context

**Development**:
1. 19세기: Topology에서 embedding 개념 등장
2. 1930s: Whitney의 manifold embedding 연구
3. 1950s: Nash의 isometric embedding
4. Modern: Category theory에서 일반화

## Common Pitfalls^[흔한 실수]

1. **Injection = Embedding?**
   - 반례: $[0, 2\pi) \to S^1$
   - Embedding은 더 강한 조건

2. **Continuous bijection = Homeomorphism?**
   - 반례: Identity map $(X, \tau_1) \to (X, \tau_2)$ where $\tau_1$ finer than $\tau_2$
   - Embedding 정의에서 역함수 연속성 필수

3. **Field homomorphism의 자동 injectivity**
   - Field homomorphism은 항상 injective (kernel = $\{0\}$)
   - 따라서 field homomorphism = field embedding

## 관련 개념

- [[Injective Function]]: Embedding의 기본 조건
- [[Homeomorphism]]: Topological embedding의 핵심
- [[Immersion]]: Smooth embedding의 약한 버전
- [[Submanifold]]: Embedding의 image
- [[Field Extension]]: Algebraic embedding의 맥락
- [[Homomorphism]]: Structure-preserving map

