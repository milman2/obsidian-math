# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Quotient Group]]
- [[Homomorphism]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Hungerford, Algebra

---

# <span class="header-definition">Definition</span>

## Correspondence Theorem^[대응 정리]

**Alternative names**: Lattice Isomorphism Theorem, Fourth Isomorphism Theorem

$N \triangleleft G$ (normal subgroup)에 대해, 다음 두 집합 사이에 **bijection^[일대일 대응]**이 존재:

$$\{H : N \subseteq H \subseteq G\} \longleftrightarrow \{\bar{H} : \bar{H} \leq G/N\}$$

### 대응 방식

**Forward map**: $H \mapsto H/N = \{hN : h \in H\}$

**Inverse map**: $\bar{H} \mapsto \pi^{-1}(\bar{H}) = \{g \in G : gN \in \bar{H}\}$

여기서 $\pi: G \to G/N$는 canonical projection^[표준 사영], $\pi(g) = gN$

### 의미

**"$G/N$의 subgroup 구조는 $N$ 위의 $G$ 구조를 정확히 반영"**

- $G/N$의 모든 subgroup은 $G$의 어떤 subgroup (containing $N$)에서 유래
- $N$보다 작은 $G$의 subgroup들은 quotient에서 사라짐
- $N$을 포함하는 $G$의 subgroup들만 $G/N$에 남음

---

# <span class="header-properties">Properties</span>

## 보존되는 성질들

Correspondence $H \leftrightarrow H/N$은 다음을 보존:

### 1. Inclusion^[포함 관계]

$$H_1 \subseteq H_2 \Leftrightarrow H_1/N \subseteq H_2/N$$

**의미**: Subgroup lattice 구조 보존

### 2. Normality^[정규성]

$$H \triangleleft G \Leftrightarrow H/N \triangleleft G/N$$

**중요**: Normal인지 여부를 quotient에서도 확인 가능!

### 3. Index^[지표]

$$[G : H] = [G/N : H/N]$$

**증명**: 

$$[G : H] = \frac{|G|}{|H|}, \quad [G/N : H/N] = \frac{|G/N|}{|H/N|} = \frac{|G|/|N|}{|H|/|N|} = \frac{|G|}{|H|}$$

### 4. Intersection^[교집합]

$$(H_1 \cap H_2)/N = (H_1/N) \cap (H_2/N)$$

### 5. Product^[곱]

$$(H_1H_2)/N = (H_1/N)(H_2/N)$$

여기서 $H_1H_2 = \{h_1h_2 : h_1 \in H_1, h_2 \in H_2\}$

### 6. Order^[위수]

$$|H/N| = \frac{|H|}{|N|}$$

(finite case)

### 7. Abelian Property^[아벨 성질]

$$H \text{ abelian} \not\Rightarrow H/N \text{ abelian (일반적으로)}$$

하지만: $H$ abelian이고 $N \subseteq Z(H)$이면 $H/N$ abelian

## Lattice Structure^[격자 구조]

$\mathcal{L}(G, \supseteq N) = \{H : N \subseteq H \subseteq G\}$: $G$에서 $N$을 포함하는 subgroups

$\mathcal{L}(G/N) = \{\bar{H} : \bar{H} \leq G/N\}$: $G/N$의 모든 subgroups

**정리**: $\mathcal{L}(G, \supseteq N) \cong \mathcal{L}(G/N)$ as lattices

**연산 보존**:
- Join: $H_1 \vee H_2 = \langle H_1, H_2 \rangle$
- Meet: $H_1 \wedge H_2 = H_1 \cap H_2$

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}/6\mathbb{Z}$

$G = \mathbb{Z}$, $N = 6\mathbb{Z}$

### $G$의 subgroups containing $6\mathbb{Z}$

| Subgroup | Index | Generators |
|----------|-------|------------|
| $\mathbb{Z}$ | $[\mathbb{Z} : \mathbb{Z}] = 1$ | $\langle 1 \rangle$ |
| $2\mathbb{Z}$ | $[\mathbb{Z} : 2\mathbb{Z}] = 2$ | $\langle 2 \rangle$ |
| $3\mathbb{Z}$ | $[\mathbb{Z} : 3\mathbb{Z}] = 3$ | $\langle 3 \rangle$ |
| $6\mathbb{Z}$ | $[\mathbb{Z} : 6\mathbb{Z}] = 6$ | $\langle 6 \rangle$ |

**Lattice**:
```
      ℤ
     / \
   2ℤ  3ℤ
     \ /
     6ℤ
```

### $\mathbb{Z}/6\mathbb{Z}$의 subgroups

| Subgroup | Order | Elements | 대응 |
|----------|-------|----------|------|
| $\mathbb{Z}/6\mathbb{Z}$ | 6 | $\{[0],[1],[2],[3],[4],[5]\}$ | $\mathbb{Z}/6\mathbb{Z}$ |
| $\langle [2] \rangle$ | 3 | $\{[0],[2],[4]\}$ | $2\mathbb{Z}/6\mathbb{Z}$ |
| $\langle [3] \rangle$ | 2 | $\{[0],[3]\}$ | $3\mathbb{Z}/6\mathbb{Z}$ |
| $\{[0]\}$ | 1 | $\{[0]\}$ | $6\mathbb{Z}/6\mathbb{Z}$ |

**Lattice**:
```
   ℤ/6ℤ
    / \
  〈2〉〈3〉
    \ /
   {[0]}
```

**대응 확인**:
- $\mathbb{Z} \leftrightarrow \mathbb{Z}/6\mathbb{Z}$ ✓
- $2\mathbb{Z} \leftrightarrow \langle [2] \rangle$ ✓
- $3\mathbb{Z} \leftrightarrow \langle [3] \rangle$ ✓
- $6\mathbb{Z} \leftrightarrow \{[0]\}$ ✓

**Normality 보존**: 모든 subgroup이 normal (abelian group이므로)

## Example 2: $S_3/A_3$

$G = S_3$, $N = A_3 = \{e, (123), (132)\}$

### $S_3$의 subgroups containing $A_3$

- $S_3$ 전체 (order 6)
- $A_3$ (order 3)

**이유**: $A_3$는 maximal subgroup (index 2)

### $S_3/A_3$의 subgroups

$S_3/A_3 \cong \mathbb{Z}/2\mathbb{Z}$ (order 2)

- $S_3/A_3 = \{A_3, (12)A_3\}$ 전체
- $\{A_3\}$ (identity)

**Order 2인 group은 subgroup이 정확히 2개**

### 대응

$$S_3 \longleftrightarrow S_3/A_3$$
$$A_3 \longleftrightarrow \{A_3\}$$

**Normality**: 
- $A_3 \triangleleft S_3$ ✓
- $\{A_3\} \triangleleft S_3/A_3$ ✓

## Example 3: $\mathbb{Z}/12\mathbb{Z}$ from $\mathbb{Z}/4\mathbb{Z}$

$G = \mathbb{Z}$, $N = 4\mathbb{Z}$

$G/N = \mathbb{Z}/4\mathbb{Z} = \{[0], [1], [2], [3]\}$

### Subgroup $H = 2\mathbb{Z}$

$N = 4\mathbb{Z} \subseteq H = 2\mathbb{Z} \subseteq G = \mathbb{Z}$

**대응**: $H/N = 2\mathbb{Z}/4\mathbb{Z} = \{[0], [2]\} \leq \mathbb{Z}/4\mathbb{Z}$

**확인**:
- $[2\mathbb{Z} : 4\mathbb{Z}] = 2$
- $|\{[0], [2]\}| = 2$ ✓
- $[\mathbb{Z}/4\mathbb{Z} : \{[0], [2]\}] = 4/2 = 2$ ✓

## Example 4: Direct Product

$G = H \times K$, $N = H \times \{e\}$

$G/N = (H \times K)/(H \times \{e\}) \cong K$

### Subgroups containing $N$

$H \times K_1$ where $K_1 \leq K$

**대응**: $(H \times K_1)/N \cong K_1$

**Lattice isomorphism**: $\mathcal{L}(K) \cong \mathcal{L}(G/N)$

## Example 5: Non-example (N not contained)

$G = \mathbb{Z}$, $N = 6\mathbb{Z}$

**Consider**: $H = 4\mathbb{Z}$

$H \not\supseteq N$ (왜냐하면 $6 \notin 4\mathbb{Z}$)

**결과**: $H$는 correspondence에 참여하지 않음!

$H \cap N = 12\mathbb{Z}$ (이것은 $N$을 포함하지 않음)

**교훈**: Correspondence는 $N$을 포함하는 subgroup들만 해당

---

# <span class="header-proof">Proof</span>

## Bijection 증명

$\phi: \{H : N \subseteq H \subseteq G\} \to \{\bar{H} : \bar{H} \leq G/N\}$

$\phi(H) = H/N$

### Well-defined

$N \subseteq H \subseteq G \Rightarrow H/N \leq G/N$?

**증명**:
1. $H/N \subseteq G/N$ (obvious)
2. $H/N$은 subgroup:
   - Identity: $N = eN \in H/N$ ✓
   - Closure: $(h_1N)(h_2N) = (h_1h_2)N \in H/N$ ✓
   - Inverse: $(hN)^{-1} = h^{-1}N \in H/N$ ✓

### Injective^[단사]

$H_1/N = H_2/N \Rightarrow H_1 = H_2$?

**증명**: 
- $h \in H_1 \Rightarrow hN \in H_1/N = H_2/N \Rightarrow hN = h_2N$ for some $h_2 \in H_2$
- $\Rightarrow h = h_2n$ for some $n \in N \subseteq H_2$
- $\Rightarrow h \in H_2$ (since $h_2, n \in H_2$)
- Similarly $H_2 \subseteq H_1$
- Therefore $H_1 = H_2$ ✓

### Surjective^[전사]

$\bar{H} \leq G/N \Rightarrow \exists H$ with $\phi(H) = \bar{H}$?

**구성**: $H = \pi^{-1}(\bar{H}) = \{g \in G : \pi(g) \in \bar{H}\}$

**확인**:
1. $H$는 subgroup (homomorphism의 preimage)
2. $N \subseteq H$: $n \in N \Rightarrow \pi(n) = nN = N = e_{G/N} \in \bar{H}$ ✓
3. $H/N = \bar{H}$:
   - $hN \in H/N \Rightarrow \pi(h) \in \bar{H} \Rightarrow hN \in \bar{H}$ ✓
   - $\bar{h} \in \bar{H} \Rightarrow \bar{h} = gN$ for some $g \in H \Rightarrow \bar{h} \in H/N$ ✓

따라서 $\phi$는 bijection ✓

## Normality 보존 증명

$H \triangleleft G \Leftrightarrow H/N \triangleleft G/N$

### ($\Rightarrow$)

Assume $H \triangleleft G$

$(gN)(hN)(gN)^{-1} = ghg^{-1}N$

$H \triangleleft G \Rightarrow ghg^{-1} \in H \Rightarrow ghg^{-1}N \in H/N$ ✓

### ($\Leftarrow$)

Assume $H/N \triangleleft G/N$

$ghg^{-1} \in H$?

$(gN)(hN)(gN)^{-1} \in H/N \Rightarrow ghg^{-1}N \in H/N$

$\Rightarrow ghg^{-1} \in H$ (by definition of $H/N$) ✓

---

# <span class="header-theorem">Theorem</span>

## Connection to Isomorphism Theorems

### Third Isomorphism Theorem

$K \subseteq N \triangleleft G \Rightarrow (G/K)/(N/K) \cong G/N$

**Correspondence view**: 

Quotient $G/K$에서:
- $N/K$는 subgroup containing identity
- $(G/K)/(N/K)$는 다시 quotient

**결과**: "Quotient의 quotient = 전체의 quotient"

### First Isomorphism Theorem

$\phi: G \to H$ homomorphism

$\text{im}(\phi) \cong G/\ker(\phi)$

**Correspondence**: $\mathcal{L}(\text{im}(\phi)) \cong \mathcal{L}(G/\ker(\phi))$

Subgroups of image $\leftrightarrow$ Subgroups of quotient by kernel

## Maximal Subgroups^[극대 부분군]

**정리**: $M \triangleleft G$ maximal normal $\Leftrightarrow G/M$ simple

**증명**: Correspondence theorem으로

$M$ maximal normal $\Leftrightarrow$ $\{M, G\}$만이 $M$을 포함하는 normal subgroups

$\Leftrightarrow$ $G/M$이 nontrivial proper normal subgroup이 없음

$\Leftrightarrow$ $G/M$ simple ✓

## Composition Series^[합성 열]

$$\{e\} = G_0 \triangleleft G_1 \triangleleft \cdots \triangleleft G_n = G$$

where each $G_{i+1}/G_i$ simple

**Correspondence 적용**:

$G/G_1$의 composition series는 $\{G_1, \ldots, G_n\}$에 대응

**Jordan-Hölder Theorem**: Composition factors 유일 (up to order)

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Correspondence Theorem = "Quotient의 투명성"**

Quotient를 취해도 (적어도 $N$ 위의) 구조는 그대로 보인다

### 메타포: 망원경

- $G$: 전체 우주
- $N$: "해상도 한계" - 이보다 작은 것은 보이지 않음
- $G/N$: $N$의 해상도로 본 우주
- Correspondence: $N$보다 큰 구조는 quotient에서도 보임

### 메타포: 압축

- $N$: "손실 압축의 단위"
- $G/N$: 압축된 데이터
- Correspondence: $N$보다 큰 패턴은 압축 후에도 복원 가능

## 왜 중요한가?

### 1. Quotient 구조 파악

$G/N$의 모든 subgroup이 어디서 왔는지 정확히 알 수 있음

### 2. Simplification

복잡한 $G$를 더 단순한 $G/N$으로 분석

$G/N$에서 발견한 구조 → $G$의 구조 (containing $N$)

### 3. Induction

Group의 성질을 induction으로 증명:
- Base: Simple group
- Step: $G/N$에 대해 성립 → $G$에 대해 성립

### 4. Classification

Groups를 분류할 때 quotient structure 사용

## Correspondence가 보존하지 않는 것

### 1. Order of elements

$g \in H$의 order ≠ $gN \in H/N$의 order (일반적으로)

**예**: $\mathbb{Z}/6\mathbb{Z}$에서
- $2 \in \mathbb{Z}$의 order = $\infty$
- $[2] \in \mathbb{Z}/6\mathbb{Z}$의 order = 3

### 2. Generating sets

$H = \langle S \rangle \not\Rightarrow H/N = \langle \{sN : s \in S\} \rangle$ (일반적으로)

더 적은 원소로 generate 가능할 수 있음

### 3. Simplicity of intersection

$H_1, H_2$ simple $\not\Rightarrow$ $H_1/N, H_2/N$ simple

$N$이 nontrivial subgroup을 포함할 수 있음

## 일반화

### Ring Theory

Ideal $I \triangleleft R$에 대해:

$$\{\text{ideals } J : I \subseteq J \subseteq R\} \leftrightarrow \{\text{ideals of } R/I\}$$

자세한 내용은 [[Ring]] 참조

### Module Theory

Submodule $N \subseteq M$에 대해:

$$\{\text{submodules } L : N \subseteq L \subseteq M\} \leftrightarrow \{\text{submodules of } M/N\}$$

### Galois Theory

Field extension $K/F$에 대해:

**Fundamental Theorem of Galois Theory**:

$$\{\text{intermediate fields}\} \leftrightarrow \{\text{subgroups of } \text{Gal}(K/F)\}$$

자세한 내용은 [[Galois Theory]] 참조

### Universal Algebra

Congruence $\theta$에 대해:

$$\{\text{congruences } \phi : \theta \subseteq \phi\} \leftrightarrow \{\text{congruences on } A/\theta\}$$

## 응용

**Group Theory**:
- Sylow subgroups 분석
- Solvable/nilpotent groups
- Simple groups classification

**Representation Theory**:
- Module structure
- Character theory

**Algebraic Topology**:
- Fundamental group의 quotient
- Covering spaces

**Galois Theory**:
- Field extensions
- Solvability by radicals

## 역사적 배경

**Emmy Noether** (1882-1935):
- Lattice theory 발전에 기여
- Isomorphism theorems 정리
- Abstract algebra의 현대화

**발전**:
- 1930s: Lattice theory formalization
- 1940s: Universal algebra
- 현대: Category theory와 연결

## 관련 개념

- [[Quotient Group]]: Correspondence의 대상
- [[Normal Subgroup]]: Correspondence의 조건
- [[Isomorphism]]: Structure preservation
- [[Homomorphism]]: Preimage and correspondence
- [[Galois Theory]]: Field theory analogue

## 추가 학습 주제

**기초**:
- Lattice of subgroups
- Quotient construction
- Isomorphism theorems

**중급**:
- Subnormal series
- Chief series
- Maximal subgroups

**고급**:
- Lattice theory
- Universal algebra
- Category theory perspective

