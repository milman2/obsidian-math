# <span class="header-prerequisite">Prerequisite</span>
- Group theory (군론 기초)
- [[Equivalence Relation and Partitions]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Normal Subgroup^[정규 부분군]

Group^[군] $G$와 subgroup^[부분군] $H \leq G$에 대해, $H$가 **normal subgroup^[정규 부분군]**이다 (기호: $H \triangleleft G$ 또는 $H \trianglelefteq G$) $\Leftrightarrow$ 다음 중 하나를 만족:

### 동등한 정의들

1. **Conjugation^[켤레] 불변**: $\forall g \in G, \; gHg^{-1} = H$
2. **왼쪽과 오른쪽 coset이 같음**: $\forall g \in G, \; gH = Hg$
3. **Conjugation이 $H$를 보존**: $\forall g \in G, \forall h \in H, \; ghg^{-1} \in H$

여기서 $gHg^{-1} = \{ghg^{-1} : h \in H\}$

**직관**: $H$가 $G$의 구조와 "양립"하는 부분군

## Coset^[코셋]

Group $G$와 subgroup $H \leq G$, 원소 $g \in G$에 대해:

### Left Coset^[왼쪽 코셋]

$$gH = \{gh : h \in H\}$$

### Right Coset^[오른쪽 코셋]

$$Hg = \{hg : h \in H\}$$

**주의**: 일반적으로 $gH \neq Hg$ (abelian^[아벨] 군이거나 $H \triangleleft G$일 때만 같음)

## Quotient Group^[몫군]

$G$가 group이고 $N \triangleleft G$ (normal subgroup)일 때, **quotient group^[몫군]** $G/N$은:

### 집합으로서

$$G/N = \{gN : g \in G\}$$

모든 left coset(=right coset)들의 집합

### 군 연산

$$(g_1N) \cdot (g_2N) = (g_1 g_2)N$$

**핵심**: Normal subgroup이어야만 이 연산이 well-defined^[잘 정의됨]

## Canonical Projection^[표준 사영]

$$\pi: G \to G/N, \quad \pi(g) = gN$$

$\pi$는 surjective group homomorphism^[전사 군 준동형사상]

---

# <span class="header-properties">Properties</span>

## Well-definedness^[잘 정의됨]

Quotient group의 연산이 well-defined인 이유:

$g_1N = g_1'N$이고 $g_2N = g_2'N$이면, $(g_1g_2)N = (g_1'g_2')N$인가?

**증명**: $g_1' = g_1n_1$, $g_2' = g_2n_2$ for some $n_1, n_2 \in N$

$$g_1'g_2' = g_1n_1g_2n_2 = g_1g_2(g_2^{-1}n_1g_2)n_2$$

$N$이 normal이므로 $g_2^{-1}n_1g_2 \in N$, 따라서 $(g_2^{-1}n_1g_2)n_2 \in N$

즉, $g_1'g_2' \in g_1g_2N$ ✓

**중요**: Normal subgroup이 아니면 well-defined 안 됨!

## 군 공리

$G/N$은 다음을 만족:

1. **Associativity^[결합법칙]**: $((g_1N)(g_2N))(g_3N) = (g_1N)((g_2N)(g_3N))$
2. **Identity^[항등원]**: $eN = N$ (where $e$ is identity of $G$)
3. **Inverse^[역원]**: $(gN)^{-1} = g^{-1}N$

따라서 $G/N$은 group

## 위수^[Order]

유한군 $G$에 대해:

$$|G/N| = \frac{|G|}{|N|} = [G : N]$$

여기서 $[G : N]$은 index^[지표] (coset의 개수)

**Lagrange's Theorem^[라그랑주 정리]**의 일반화

## Kernel과 Normal Subgroup

Group homomorphism $\phi: G \to H$의 **kernel^[핵]**:

$$\ker(\phi) = \{g \in G : \phi(g) = e_H\}$$

**정리**: $\ker(\phi) \triangleleft G$ (kernel은 항상 normal)

**증명**: $g \in \ker(\phi)$이면, $\phi(hgh^{-1}) = \phi(h)\phi(g)\phi(h)^{-1} = \phi(h)e_H\phi(h)^{-1} = e_H$

---

# <span class="header-examples">Examples</span>

## Example 1: 정수의 잉여류

$G = \mathbb{Z}$ (덧셈 군), $N = n\mathbb{Z} = \{nk : k \in \mathbb{Z}\}$

**Quotient group**: $\mathbb{Z}/n\mathbb{Z}$

**원소**: $\{0 + n\mathbb{Z}, 1 + n\mathbb{Z}, \ldots, (n-1) + n\mathbb{Z}\}$

**표기**: $\overline{0}, \overline{1}, \ldots, \overline{n-1}$ 또는 $[0], [1], \ldots, [n-1]$

**연산**: $\overline{a} + \overline{b} = \overline{a+b}$

**위수**: $|\mathbb{Z}/n\mathbb{Z}| = n$

**예**: $\mathbb{Z}/5\mathbb{Z} = \{\overline{0}, \overline{1}, \overline{2}, \overline{3}, \overline{4}\}$

자세한 내용은 [[Equivalence Relation and Partitions]] 참조

## Example 2: $\mathbb{R}/\mathbb{Z}$

$G = \mathbb{R}$ (덧셈 군), $N = \mathbb{Z}$

**Quotient group**: $\mathbb{R}/\mathbb{Z}$

**해석**: 실수를 정수만큼 이동한 것을 같다고 봄

**기하학적**: Circle group^[원군] $S^1$ (단위원)과 isomorphic^[동형]

$$\phi: \mathbb{R}/\mathbb{Z} \to S^1, \quad \phi(x + \mathbb{Z}) = e^{2\pi i x}$$

**예**: $0.3 + \mathbb{Z} = \{\ldots, -0.7, 0.3, 1.3, 2.3, \ldots\}$

## Example 3: Klein Four-Group

$V_4 = \{e, a, b, c\}$ (Klein four-group, 모든 원소의 위수가 2)

$N = \{e, a\} \triangleleft V_4$

**Quotient**: $V_4/N = \{\{e, a\}, \{b, c\}\}$

**위수**: $|V_4/N| = 2$ (cyclic group of order 2와 동형)

## Example 4: $\mathbb{R}^n/\mathbb{Z}^n$

$G = \mathbb{R}^n$ (vector addition), $N = \mathbb{Z}^n$

**Quotient**: $\mathbb{R}^n/\mathbb{Z}^n$ (n-dimensional torus^[n차원 토러스])

**기하학적**:
- $n=1$: Circle $S^1$
- $n=2$: Torus (도넛 모양)
- $n=3$: 3-torus

## Example 5: Special Linear Group

$G = \text{GL}_n(\mathbb{R})$ (가역 행렬들), $N = \{cI : c \in \mathbb{R}^\times\}$ (scalar matrices)

**Quotient**: $\text{PGL}_n(\mathbb{R})$ (projective general linear group^[사영 일반 선형군])

행렬을 scalar 배수만큼 같다고 봄

## Example 6: Abelian Group

$G$가 abelian^[아벨]이면 **모든** subgroup이 normal

이유: $gHg^{-1} = gg^{-1}H = H$ (abelian이므로 $hg = gh$)

따라서 abelian group에서는 항상 quotient group 구성 가능

---

# <span class="header-theorem">Theorem</span>

## First Isomorphism Theorem^[제1 동형 정리]

Group homomorphism $\phi: G \to H$에 대해:

$$G/\ker(\phi) \cong \text{im}(\phi)$$

**자연스러운 isomorphism^[동형사상]**:

$$\bar{\phi}: G/\ker(\phi) \to \text{im}(\phi), \quad \bar{\phi}(g\ker(\phi)) = \phi(g)$$

**직관**: Kernel을 "0으로 만들면" bijection이 됨

**다이어그램**:

```
G ----φ--→ H
|        ↗
π      φ̄
↓    ↗
G/ker(φ)
```

## Second Isomorphism Theorem^[제2 동형 정리]

$H \leq G$이고 $N \triangleleft G$이면:

$$H/(H \cap N) \cong (HN)/N$$

여기서 $HN = \{hn : h \in H, n \in N\}$

## Third Isomorphism Theorem^[제3 동형 정리]

$K, N \triangleleft G$이고 $K \subseteq N$이면:

$$(G/K)/(N/K) \cong G/N$$

**직관**: "몫의 몫은 전체의 몫"

## Correspondence Theorem^[대응 정리]

$N \triangleleft G$에 대해, 다음 사이에 일대일 대응:

$$\{H : N \subseteq H \subseteq G\} \leftrightarrow \{\bar{H} : \bar{H} \leq G/N\}$$

대응: $H \mapsto H/N$

**중요**: 
- $H \triangleleft G \Leftrightarrow H/N \triangleleft G/N$
- $|G/H| = |(G/N)/(H/N)|$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Quotient Group**: "차이를 무시하기"

Normal subgroup $N$의 원소들을 "0으로 취급" (또는 identity로)

**예**: $\mathbb{Z}/5\mathbb{Z}$에서 $7 = 2$ (mod 5)
- $7 - 2 = 5 \in 5\mathbb{Z}$이므로 차이를 무시

**기하학적**: 공간을 $N$에 의해 "접기" (folding)

## Normal Subgroup의 중요성

**왜 Normal이어야 하나?**

연산이 well-defined되려면:
- 왼쪽 코셋과 오른쪽 코셋이 일치해야
- Conjugation으로 닫혀있어야

**반례**: $S_3$의 subgroup $H = \{e, (12)\}$는 normal이 아님
- $(13)H = \{(13), (132)\}$
- $H(13) = \{(13), (123)\}$
- $(13)H \neq H(13)$ ✗

## Abelian vs Non-Abelian

**Abelian group**: 
- 모든 subgroup이 normal
- Quotient group 자유롭게 구성 가능

**Non-abelian group**:
- Normal subgroup만 quotient 가능
- 구조가 더 복착

## 선형대수와의 관계

**Vector space quotient**: $V/W$ (where $W$ is subspace)

$$V/W = \{v + W : v \in V\}$$

연산: $(v_1 + W) + (v_2 + W) = (v_1 + v_2) + W$

**차이점**:
- Vector space는 항상 abelian (덧셈)
- 모든 subspace가 "normal"
- Linear map의 kernel은 subspace

자세한 내용은 [[Linear mapping]] 참조

## 위상수학과의 관계

**Quotient topology^[몫 위상]**: $X/\sim$ with quotient topology

Canonical projection $\pi: X \to X/\sim$이 continuous가 되는 finest topology

**예**: 
- Torus = Square with opposite sides identified
- Projective space = Sphere with antipodal points identified

자세한 내용은 [[Topology]] 참조

## 범주론에서

**Quotient = Coequalizer**

Group의 quotient는 category theory에서 coequalizer의 특수한 경우

Kernel은 equalizer

자세한 내용은 [[Category Theory]] 참조

## 응용

**대수학**:
- Galois theory^[갈루아 이론]: Field extensions
- Ring theory^[환론]: Ideals and quotient rings

**기하학**:
- Lie groups^[리 군]: Quotient manifolds
- Covering spaces^[덮개 공간]

**물리학**:
- Gauge theory^[게이지 이론]: Quotient by gauge group
- Symmetry breaking^[대칭성 깨짐]

**암호학**:
- RSA: $\mathbb{Z}/n\mathbb{Z}$의 multiplicative group
- Elliptic curve cryptography

## 역사적 배경

**Évariste Galois** (1811-1832):
- Normal subgroup 개념 도입
- Group theory의 기초 확립
- 21세에 사망 (결투)

**발전**:
- 19세기: 방정식의 풀이 가능성 연구
- 20세기: 추상 대수학의 핵심 도구
- 현대: 거의 모든 수학 분야에서 사용

## 표기법

| 표기 | 의미 |
|------|------|
| $H \triangleleft G$ | $H$는 $G$의 normal subgroup |
| $G/N$ | Quotient group |
| $gN$ | Coset |
| $[G : N]$ | Index (coset의 개수) |
| $\ker(\phi)$ | Kernel |
| $\text{im}(\phi)$ | Image |

## Common Pitfall^[흔한 실수]

**잘못된 생각**: "모든 subgroup으로 quotient 가능"

✗ Normal subgroup만 가능!

**예시**: $D_4$ (정사각형의 대칭군)의 일부 subgroup은 normal이 아님

**확인 방법**: 
- Abelian group: 항상 OK
- Non-abelian: $gHg^{-1} = H$ for all $g$ 확인 필요

