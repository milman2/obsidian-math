# <span class="header-prerequisite">Prerequisite</span>
- [[Function]]
- [[Group]]
- [[Ring]]
- [[Field]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Lang, Algebra

---

# <span class="header-definition">Definition</span>

## Homomorphism^[준동형사상]

**Homomorphism**^[준동형사상]: 대수 구조 사이에서 **연산을 보존하는 함수**

핵심 아이디어: "구조를 존중하는 mapping"

## Group Homomorphism^[군 준동형사상]

함수 $\phi: G \to H$ (where $G, H$ are groups^[군])가 **group homomorphism**^[군 준동형사상]이다 $\Leftrightarrow$

$$\forall a, b \in G, \quad \phi(a \cdot_G b) = \phi(a) \cdot_H \phi(b)$$

**의미**: 곱셈 연산을 보존

### 기본 성질

Group homomorphism $\phi: G \to H$에 대해:

1. **항등원 보존**: $\phi(e_G) = e_H$
2. **역원 보존**: $\phi(a^{-1}) = \phi(a)^{-1}$
3. **거듭제곱 보존**: $\phi(a^n) = \phi(a)^n$ for all $n \in \mathbb{Z}$

**증명 (1)**: 
$$\phi(e_G) = \phi(e_G \cdot e_G) = \phi(e_G) \cdot \phi(e_G)$$
양변에 $\phi(e_G)^{-1}$을 곱하면 $e_H = \phi(e_G)$

## Ring Homomorphism^[환 준동형사상]

함수 $\phi: R \to S$ (where $R, S$ are rings^[환])가 **ring homomorphism**^[환 준동형사상]이다 $\Leftrightarrow$

1. $\phi(a + b) = \phi(a) + \phi(b)$ (덧셈 보존)
2. $\phi(a \cdot b) = \phi(a) \cdot \phi(b)$ (곱셈 보존)

**주의**: Identity 보존 여부는 정의에 따라 다름
- 일부 정의: $\phi(1_R) = 1_S$도 요구
- 본 노트: Identity 보존도 요구

### 기본 성질

Ring homomorphism $\phi: R \to S$에 대해:

1. $\phi(0_R) = 0_S$
2. $\phi(-a) = -\phi(a)$
3. $\phi(1_R) = 1_S$ (if rings have identity)
4. $u \in R^\times \Rightarrow \phi(u) \in S^\times$ and $\phi(u^{-1}) = \phi(u)^{-1}$

## Field Homomorphism^[체 준동형사상]

함수 $\phi: \mathbb{F} \to \mathbb{E}$ (where $\mathbb{F}, \mathbb{E}$ are fields^[체])가 **field homomorphism**^[체 준동형사상]이다 $\Leftrightarrow$ ring homomorphism

### 중요한 성질

**정리**: 모든 field homomorphism은 **injective**^[단사]!

**증명**: $\ker(\phi)$는 ideal of $\mathbb{F}$
- Field의 ideal은 $(0)$ 또는 $\mathbb{F}$뿐
- $\phi(1) = 1 \neq 0$이므로 $\ker(\phi) \neq \mathbb{F}$
- 따라서 $\ker(\phi) = (0)$ 
**결과**: Non-trivial field homomorphism은 항상 injective

## Vector Space Homomorphism^[벡터 공간 준동형사상]

함수 $T: V \to W$ (where $V, W$ are vector spaces^[벡터 공간] over field $\mathbb{F}$)가 **linear map**^[선형 사상] (또는 **linear transformation**^[선형 변환])이다 $\Leftrightarrow$

1. $T(v_1 + v_2) = T(v_1) + T(v_2)$ (덧셈 보존)
2. $T(cv) = cT(v)$ for all $c \in \mathbb{F}$ (스칼라 곱 보존)

**동등 조건**: $T(\alpha v_1 + \beta v_2) = \alpha T(v_1) + \beta T(v_2)$

자세한 내용은 [[Linear mapping]] 참조

## Kernel^[핵]

Homomorphism $\phi: G \to H$의 **kernel**^[핵]:

$$\ker(\phi) = \{g \in G : \phi(g) = e_H\}$$

항등원으로 mapping되는 원소들의 집합

### 성질

**Group homomorphism**: $\ker(\phi) \triangleleft G$ (normal subgroup^[정규 부분군])

**Ring homomorphism**: $\ker(\phi) \triangleleft R$ (ideal^[아이디얼])

**Field homomorphism**: $\ker(\phi) = \{0\}$ or $\mathbb{F}$ (field는 proper ideal 없음)

**Linear map**: $\ker(T)$ is subspace^[부분 공간]

## Image^[상]

Homomorphism $\phi: G \to H$의 **image**^[상]:

$$\text{im}(\phi) = \phi(G) = \{\phi(g) : g \in G\}$$

또는 **range**^[치역]라고도 함

### 성질

**Group homomorphism**: $\text{im}(\phi) \leq H$ (subgroup)

**Ring homomorphism**: $\text{im}(\phi)$ is subring of $H$

**Field homomorphism**: $\text{im}(\phi)$ is subfield of $\mathbb{E}$

**Linear map**: $\text{im}(T)$ is subspace of $W$

## Special Types of Homomorphisms

### Monomorphism^[단사 준동형사상]

Homomorphism이 **injective**^[단사]

$$\phi(a) = \phi(b) \Rightarrow a = b$$

**동등 조건**: $\ker(\phi) = \{e\}$ (or $\{0\}$)

### Epimorphism^[전사 준동형사상]

Homomorphism이 **surjective**^[전사]

$$\text{im}(\phi) = H$$

모든 $h \in H$에 대해 $\exists g \in G$ such that $\phi(g) = h$

### Endomorphism^[자기준동형사상]

Homomorphism $\phi: G \to G$ (domain = codomain)

**예**: 
- Group: Conjugation^[켤레] $\phi_g(x) = gxg^{-1}$
- Vector space: Linear operator^[선형 작용소]

### Automorphism^[자기동형사상]

Bijective^[전단사] endomorphism

**집합**: $\text{Aut}(G) = \{$ automorphisms of $G\}$

**구조**: $\text{Aut}(G)$는 group (under composition)

자세한 내용은 [[Isomorphism]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Trivial Homomorphism^[자명 준동형사상]

$$\phi: G \to H, \quad \phi(g) = e_H \; \forall g \in G$$

**Kernel**: $\ker(\phi) = G$

**Image**: $\text{im}(\phi) = \{e_H\}$

**항상 homomorphism** (but usually uninteresting)

## Example 2: Inclusion Map^[포함 사상]

$H \leq G$에 대해:

$$\iota: H \to G, \quad \iota(h) = h$$

**Injective**: Yes

**Kernel**: $\ker(\iota) = \{e\}$

**Image**: $\text{im}(\iota) = H$

## Example 3: Canonical Projection^[표준 사영]

Normal subgroup $N \triangleleft G$에 대해:

$$\pi: G \to G/N, \quad \pi(g) = gN$$

**Surjective**: Yes (모든 coset이 상)

**Kernel**: $\ker(\pi) = N$

**Image**: $\text{im}(\pi) = G/N$

자세한 내용은 [[Quotient Group]] 참조

## Example 4: Determinant^[행렬식]

$$\det: \text{GL}_n(\mathbb{R}) \to \mathbb{R}^\times$$

Group homomorphism:
$$\det(AB) = \det(A)\det(B)$$

**Kernel**: $\ker(\det) = \text{SL}_n(\mathbb{R})$ (special linear group, $\det = 1$)

**Image**: $\text{im}(\det) = \mathbb{R}^\times$ (all non-zero reals)

**Surjective**: Yes

## Example 5: Sign Homomorphism^[부호 준동형사상]

$$\text{sgn}: S_n \to \{\pm 1\} \cong C_2$$

**정의**: 
$$\text{sgn}(\sigma) = \begin{cases} +1 & \text{if } \sigma \text{ is even permutation} \\ -1 & \text{if } \sigma \text{ is odd permutation} \end{cases}$$

**Homomorphism**: $\text{sgn}(\sigma\tau) = \text{sgn}(\sigma)\text{sgn}(\tau)$

**Kernel**: $\ker(\text{sgn}) = A_n$ (alternating group)

**Image**: $\text{im}(\text{sgn}) = \{\pm 1\}$

## Example 6: Exponential Map^[지수 사상]

$$\exp: (\mathbb{R}, +) \to (\mathbb{R}^+, \times), \quad \exp(x) = e^x$$

Group homomorphism:
$$\exp(x + y) = e^{x+y} = e^x \cdot e^y = \exp(x) \cdot \exp(y)$$

**Injective**: Yes

**Surjective**: Yes

**Isomorphism**: $(\mathbb{R}, +) \cong (\mathbb{R}^+, \times)$

## Example 7: Complex Exponential^[복소 지수]

$$\exp: (\mathbb{C}, +) \to (\mathbb{C}^\times, \times), \quad \exp(z) = e^z$$

Group homomorphism

**Kernel**: $\ker(\exp) = 2\pi i \mathbb{Z} = \{2\pi i n : n \in \mathbb{Z}\}$

**Image**: $\text{im}(\exp) = \mathbb{C}^\times$ (모든 non-zero complex numbers)

**Surjective**: Yes (but not injective)

## Example 8: Evaluation Homomorphism^[평가 준동형사상]

$a \in \mathbb{R}$에 대해:

$$\text{ev}_a: \mathbb{R}[x] \to \mathbb{R}, \quad \text{ev}_a(p(x)) = p(a)$$

Ring homomorphism:
- $\text{ev}_a(p + q) = (p+q)(a) = p(a) + q(a)$
- $\text{ev}_a(p \cdot q) = (p \cdot q)(a) = p(a) \cdot q(a)$

**Kernel**: $\ker(\text{ev}_a) = (x-a)$ (ideal of polynomials vanishing at $a$)

**Surjective**: Yes (constant polynomials)

## Example 9: Frobenius Homomorphism^[프로베니우스 준동형사상]

Characteristic $p$ field $\mathbb{F}$에서:

$$\text{Frob}: \mathbb{F} \to \mathbb{F}, \quad \text{Frob}(x) = x^p$$

Field homomorphism (in char $p$):
$$(x + y)^p = x^p + y^p \quad \text{(Frobenius property)}$$

**Injective**: Yes (field homomorphism)

**Surjective**: Yes for finite fields

자세한 내용은 [[Field]] 참조

## Example 10: Reduction Modulo $n$^[모듈로 n 축약]

$$\pi: \mathbb{Z} \to \mathbb{Z}/n\mathbb{Z}, \quad \pi(a) = [a]$$

Ring homomorphism:
- $\pi(a + b) = [a + b] = [a] + [b]$
- $\pi(ab) = [ab] = [a][b]$

**Kernel**: $\ker(\pi) = n\mathbb{Z}$

**Surjective**: Yes

## Example 11: Conjugation^[켤레 사상]

$g \in G$에 대해:

$$\phi_g: G \to G, \quad \phi_g(x) = gxg^{-1}$$

Group homomorphism (automorphism):
$$\phi_g(xy) = g(xy)g^{-1} = (gxg^{-1})(gyg^{-1}) = \phi_g(x)\phi_g(y)$$

**Kernel**: $\ker(\phi_g) = \{x : gxg^{-1} = x\} = C_G(g)$ (centralizer^[중심화원])

**Inner automorphism**^[내부 자기동형사상]

## Example 12: Dual Map^[쌍대 사상]

Linear map $T: V \to W$에 대해:

$$T^*: W^* \to V^*, \quad T^*(\phi) = \phi \circ T$$

Linear map (dual space^[쌍대 공간] 사이)

자세한 내용은 [[Dual Spaces]] 참조

---

# <span class="header-theorem">Theorem</span>

## First Isomorphism Theorem^[제1 동형 정리]

Homomorphism $\phi: G \to H$에 대해:

$$G/\ker(\phi) \cong \text{im}(\phi)$$

**자연스러운 isomorphism**:

$$\bar{\phi}: G/\ker(\phi) \to \text{im}(\phi), \quad \bar{\phi}(g\ker(\phi)) = \phi(g)$$

**의미**: Kernel을 quotient하면 bijection이 됨

**다이어그램**:

```
G ----φ---→ H
|         ↗
π       φ̄
↓     ↗
G/ker(φ) ⊆ im(φ)
```

**증명 아이디어**:
1. $\bar{\phi}$ well-defined: $g_1\ker(\phi) = g_2\ker(\phi) \Rightarrow \phi(g_1) = \phi(g_2)$
2. $\bar{\phi}$ injective: $\ker(\bar{\phi}) = \{\ker(\phi)\}$
3. $\bar{\phi}$ surjective: by definition of image

자세한 내용은 [[Quotient Group]] 참조

## Second Isomorphism Theorem^[제2 동형 정리]

$H \leq G$이고 $N \triangleleft G$이면:

$$H/(H \cap N) \cong (HN)/N$$

where $HN = \{hn : h \in H, n \in N\}$

**증명**: Homomorphism $\phi: H \to HN/N$, $\phi(h) = hN$
- $\ker(\phi) = H \cap N$
- $\text{im}(\phi) = HN/N$

## Third Isomorphism Theorem^[제3 동형 정리]

$K, N \triangleleft G$이고 $K \subseteq N$이면:

$$(G/K)/(N/K) \cong G/N$$

**직관**: "몫의 몫은 전체의 몫"

**증명**: Homomorphism $\phi: G/K \to G/N$, $\phi(gK) = gN$

## Correspondence Theorem^[대응 정리]

$N \triangleleft G$에 대해, 다음 사이에 일대일 대응:

$$\{H : N \subseteq H \subseteq G\} \leftrightarrow \{\bar{H} : \bar{H} \leq G/N\}$$

대응: $H \mapsto H/N$

**성질 보존**:
- $H_1 \subseteq H_2 \Leftrightarrow H_1/N \subseteq H_2/N$
- $H \triangleleft G \Leftrightarrow H/N \triangleleft G/N$
- $[G : H] = [G/N : H/N]$

## Rank-Nullity Theorem^[계수-퇴화차수 정리]

Linear map $T: V \to W$ (finite-dimensional)에 대해:

$$\dim(V) = \dim(\ker(T)) + \dim(\text{im}(T))$$

$$\dim(V) = \text{nullity}(T) + \text{rank}(T)$$

**증명**: First Isomorphism Theorem의 결과
$$V/\ker(T) \cong \text{im}(T)$$

자세한 내용은 [[Linear mapping]] 참조

---

# <span class="header-properties">Properties</span>

## Composition of Homomorphisms^[준동형사상의 합성]

$\phi: G \to H$, $\psi: H \to K$ homomorphisms이면:

$$\psi \circ \phi: G \to K \text{ is also a homomorphism}$$

**증명**:
$$(\psi \circ \phi)(ab) = \psi(\phi(ab)) = \psi(\phi(a)\phi(b)) = \psi(\phi(a))\psi(\phi(b))$$

### Kernel and Image under Composition

1. $\ker(\phi) \subseteq \ker(\psi \circ \phi)$
2. $\text{im}(\psi \circ \phi) \subseteq \text{im}(\psi)$
3. $\psi$ injective $\Rightarrow$ $\ker(\psi \circ \phi) = \ker(\phi)$
4. $\phi$ surjective $\Rightarrow$ $\text{im}(\psi \circ \phi) = \text{im}(\psi)$

## Injectivity Test^[단사성 판정]

Homomorphism $\phi: G \to H$에 대해:

$$\phi \text{ is injective} \Leftrightarrow \ker(\phi) = \{e_G\}$$

**증명** ($\Rightarrow$): $\phi(g) = e_H = \phi(e_G) \Rightarrow g = e_G$

**증명** ($\Leftarrow$): $\phi(a) = \phi(b) \Rightarrow \phi(ab^{-1}) = e_H \Rightarrow ab^{-1} = e_G \Rightarrow a = b$

## Surjectivity Test^[전사성 판정]

Homomorphism $\phi: G \to H$에 대해:

$$\phi \text{ is surjective} \Leftrightarrow \text{im}(\phi) = H$$

(by definition)

## Homomorphism Preserves Structure^[구조 보존]

### Substructures^[부분구조]

$\phi: G \to H$ homomorphism이고 $K \leq G$이면:
$$\phi(K) \leq H$$

단, $\phi(K)$는 subgroup of $H$

### Normal Subgroups^[정규 부분군]

$\phi: G \to H$ **surjective** homomorphism이고 $N \triangleleft G$이면:
$$\phi(N) \triangleleft H$$

**주의**: Surjective 조건 필요!

### Order^[위수]

$\phi: G \to H$ homomorphism이면:
$$|\text{im}(\phi)| \cdot |\ker(\phi)| = |G|$$

(if $G$ is finite)

## Universal Property^[보편성질]

Quotient map $\pi: G \to G/N$은 다음 universal property를 만족:

Homomorphism $\phi: G \to H$ with $N \subseteq \ker(\phi)$에 대해, 유일한 homomorphism $\bar{\phi}: G/N \to H$ 존재하여:

$$\phi = \bar{\phi} \circ \pi$$

**다이어그램**:

```
    φ
G ----→ H
|     ↗
π   φ̄
↓ ↗
G/N
```

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Homomorphism**: "구조를 보존하는 함수"

**핵심**: 
- Domain에서 연산 수행 = Codomain에서 연산 수행
- "Where you do the operation doesn't matter"

**메타포**:
- 함수: 점을 점으로 mapping
- Homomorphism: 구조를 구조로 mapping

## Kernel의 역할

**Kernel**: "무엇이 collapse되는가?"

- $\ker(\phi) = \{e\}$: 아무것도 collapse 안 됨 (injective)
- $\ker(\phi)$ 클수록 더 많이 collapse

**First Isomorphism Theorem**: Kernel을 제거하면 injection이 됨

## Homomorphism vs Function

| | **Function** | **Homomorphism** |
|---|---|---|
| 정의역 | Any set | Algebraic structure |
| 치역 | Any set | Algebraic structure |
| 조건 | None | Operation preserving |
| 예 | $f(x) = x^2$ | $\phi(x) = e^x$ |

## 표기법

| 표기 | 의미 |
|------|------|
| $\phi: G \to H$ | Homomorphism |
| $\ker(\phi)$ | Kernel |
| $\text{im}(\phi)$ | Image |
| $G/\ker(\phi)$ | Quotient |
| $\cong$ | Isomorphic |

## Category Theory 관점

**Homomorphisms = Morphisms**

대수 구조들과 homomorphism들은 category^[범주]를 형성:
- **Objects**: Groups, Rings, Fields, etc.
- **Morphisms**: Homomorphisms
- **Composition**: Function composition

자세한 내용은 [[Category Theory]] 참조

## Common Pitfall^[흔한 실수]

### 1. Identity 보존 확인 안 함

✗ Homomorphism이면 자동으로 $\phi(e) = e$

 증명 필요 (but easy)

### 2. Ring homomorphism에서 곱셈만 확인

✗ 곱셈만 보존하면 ring homomorphism

 덧셈 + 곱셈 모두 보존해야

### 3. $\phi(G)$ notation

주의: $\phi(G) = \text{im}(\phi)$ (not $\phi$ applied to set $G$)

### 4. Subgroup 보존?

✗ $H \triangleleft G \Rightarrow \phi(H) \triangleleft \phi(G)$?

✓ **반례**: Non-surjective homomorphism

 Surjective이면 성립

### 5. Kernel은 항상 normal?

 Group homomorphism의 kernel은 항상 normal subgroup

증명: $g \in \ker(\phi) \Rightarrow \phi(hgh^{-1}) = \phi(h)\phi(g)\phi(h)^{-1} = e$

## 역사적 배경

**Homomorphism** (Greek: homos = same, morphe = form/structure)

**19세기**:
- 군론에서 처음 등장
- Galois, Cayley의 연구

**20세기**:
- Emmy Noether: 추상적 정의
- Category theory: 일반화

## 응용

**수학**:
- 대수학의 기본 도구
- 구조 분류 및 이해

**물리학**:
- Symmetry groups
- Gauge theory (gauge transformations)

**컴퓨터 과학**:
- Cryptography (RSA)
- Type theory

## 관련 개념

- [[Isomorphism]]: Bijective homomorphism
- [[Quotient Group]]: Canonical projection
- [[Linear mapping]]: Vector space homomorphism
- [[Galois Theory]]: Field automorphisms

## 추가 학습 주제

**기초**:
- Kernel and image
- Isomorphism theorems
- Quotient structures

**중급**:
- Universal properties
- Free objects
- Limits and colimits

**고급**:
- Derived functors
- Homological algebra
- Category theory

