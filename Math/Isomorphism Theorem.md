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

$$\Rightarrow \phi(g_2)^{-1}\phi(g_1) = e \Rightarrow \phi(g_1) = \phi(g_2)$$ ✓

### Homomorphism

$$\bar{\phi}(g_1\ker(\phi) \cdot g_2\ker(\phi)) = \bar{\phi}(g_1g_2\ker(\phi)) = \phi(g_1g_2)$$

$$= \phi(g_1)\phi(g_2) = \bar{\phi}(g_1\ker(\phi))\bar{\phi}(g_2\ker(\phi))$$ ✓

### Injective

$$\bar{\phi}(g\ker(\phi)) = e \Rightarrow \phi(g) = e \Rightarrow g \in \ker(\phi)$$

$$\Rightarrow g\ker(\phi) = \ker(\phi)$$ (identity in $G/\ker(\phi)$) ✓

### Surjective

By construction: image of $\bar{\phi}$ is $\text{im}(\phi)$ ✓

## Interpretation^[해석]

> **"Kernel을 0으로 만들면 bijection이 됨"**

- Kernel = "얼마나 many-to-one인가"
- Quotient by kernel = "many-to-one 제거"
- Result = Bijective map

## Applications^[응용]

### 1. Homomorphism 분석

모든 homomorphism은:
$$G \xrightarrow{\text{surjection}} G/\ker(\phi) \xrightarrow{\text{isomorphism}} \text{im}(\phi) \xrightarrow{\text{inclusion}} H$$

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

**First Isomorphism Theorem 적용**: $H/(H \cap N) \cong HN/N$ ✓

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

**Well-defined**: $K \subseteq N$이므로 $gK = g'K \Rightarrow gN = g'N$ ✓

**Kernel**: $\ker(\phi) = \{gK : gN = N\} = N/K$

**First Isomorphism Theorem**: $(G/K)/(N/K) \cong G/N$ ✓

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

따라서 $|S_n/A_n| = 2$, 즉 $|A_n| = |S_n|/2 = n!/2$ ✓

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
- $|(\mathbb{Z}/6\mathbb{Z})/(3\mathbb{Z}/6\mathbb{Z})| = 6/2 = 3 = |\mathbb{Z}/3\mathbb{Z}|$ ✓

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

모두 $12\mathbb{Z}$를 포함 ✓

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

