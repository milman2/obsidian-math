# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Function]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Rotman, An Introduction to the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Subgroup^[부분군]

Group $G$의 부분집합 $H \subseteq G$가 **subgroup^[부분군]**이다 (기호: $H \leq G$) $\Leftrightarrow$

$H$가 $G$의 연산으로 group을 이룸

### Explicit Conditions

$H \leq G$ $\Leftrightarrow$ 다음 네 조건을 만족:

1. **Closure^[닫혀있음]**: $\forall a, b \in H, \; ab \in H$
2. **Associativity^[결합법칙]**: Inherited from $G$
3. **Identity^[항등원]**: $e \in H$
4. **Inverse^[역원]**: $\forall a \in H, \; a^{-1} \in H$

**주의**: Associativity는 자동 상속되므로 확인 불필요

## Subgroup Tests^[부분군 판정법]

### Two-Step Subgroup Test

$H \subseteq G$가 subgroup $\Leftrightarrow$ 다음을 만족:

1. $H \neq \emptyset$
2. $\forall a, b \in H, \; ab \in H$ (closure)
3. $\forall a \in H, \; a^{-1} \in H$ (inverse)

### One-Step Subgroup Test

$H \subseteq G$가 subgroup $\Leftrightarrow$

$$H \neq \emptyset \text{ and } \forall a, b \in H, \; ab^{-1} \in H$$

**증명**:
- Identity: $a \in H \Rightarrow e = aa^{-1} \in H$
- Inverse: $a \in H \Rightarrow a^{-1} = ea^{-1} \in H$
- Closure: $a, b \in H \Rightarrow ab = a(b^{-1})^{-1} \in H$

**장점**: 한 번의 확인으로 충분!

### Finite Subgroup Test

$H \subseteq G$가 finite이고 $H \neq \emptyset$일 때:

$$H \text{ is subgroup} \Leftrightarrow \forall a, b \in H, \; ab \in H$$

**증명**: Finite set에서 closure만 있으면 inverse 자동 존재 (cancellation law)

**주의**: Infinite case에서는 성립 안 함!

## Proper Subgroup^[진부분군]

$H$가 $G$의 **proper subgroup^[진부분군]**이다 (기호: $H < G$) $\Leftrightarrow$

$$H \leq G \text{ and } H \neq G$$

**Trivial subgroups^[자명 부분군]**:
- $\{e\} \leq G$ (trivial subgroup)
- $G \leq G$ (improper subgroup)

**Nontrivial proper subgroup^[비자명 진부분군]**: $\{e\} < H < G$

## Normal Subgroup^[정규 부분군]

Subgroup $N \leq G$가 **normal^[정규]**이다 (기호: $N \triangleleft G$) $\Leftrightarrow$

$$\forall g \in G, \; gNg^{-1} = N$$

즉, conjugation^[켤레]에 대해 불변

### Equivalent Conditions^[동등 조건]

다음은 동등:

1. $gNg^{-1} = N$ for all $g \in G$
2. $gNg^{-1} \subseteq N$ for all $g \in G$
3. $gN = Ng$ for all $g \in G$ (left coset = right coset)
4. $N$은 kernel of some homomorphism

**특수한 경우**: Abelian group의 모든 subgroup은 normal

자세한 내용은 [[Quotient Group]] 참조

## Coset^[코셋]

Subgroup $H \leq G$와 원소 $g \in G$에 대해:

### Left Coset^[왼쪽 코셋]

$$gH = \{gh : h \in H\}$$

### Right Coset^[오른쪽 코셋]

$$Hg = \{hg : h \in H\}$$

### Properties of Cosets

1. $g \in gH$ (자기 자신 포함)
2. $gH = H \Leftrightarrow g \in H$
3. $g_1H = g_2H \Leftrightarrow g_1^{-1}g_2 \in H$
4. $|gH| = |H|$ (bijection via $h \mapsto gh$)
5. Either $g_1H = g_2H$ or $g_1H \cap g_2H = \emptyset$

**결과**: Cosets는 $G$의 partition^[분할]을 형성

자세한 내용은 [[Equivalence Relation and Partitions]] 참조

## Index^[지표]

Subgroup $H \leq G$의 **index^[지표]** $[G : H]$:

$$[G : H] = \text{number of distinct left cosets of } H \text{ in } G$$

**해석**: $G$를 $H$로 "나눈 몫"의 크기

### Properties

1. $[G : H] = [G : H]_{\text{left}} = [G : H]_{\text{right}}$ (left와 right coset 개수 같음)
2. Finite group: $[G : H] = \displaystyle\frac{|G|}{|H|}$ (Lagrange's theorem)
3. $[G : \{e\}] = |G|$
4. $[G : G] = 1$

---

# <span class="header-examples">Examples</span>

## Example 1: Subgroups of $\mathbb{Z}$

$$n\mathbb{Z} = \{nk : k \in \mathbb{Z}\} \leq \mathbb{Z}$$

**모든 subgroups**: $\mathbb{Z}$의 subgroup은 정확히 $n\mathbb{Z}$ ($n \geq 0$) 형태

**Lattice**:
```
    Z
   / \
  2Z 3Z ...
   \ /
   6Z ...
    |
   {0}
```

## Example 2: Subgroups of $\mathbb{Z}/n\mathbb{Z}$

Divisor $d \mid n$에 대해:

$$\langle [d] \rangle = \{[0], [d], [2d], \ldots\} \leq \mathbb{Z}/n\mathbb{Z}$$

**Order**: $|\langle [d] \rangle| = \displaystyle\frac{n}{d}$

**예**: $\mathbb{Z}/12\mathbb{Z}$의 subgroups
- $\langle [1] \rangle = \mathbb{Z}/12\mathbb{Z}$ (order 12)
- $\langle [2] \rangle$ (order 6)
- $\langle [3] \rangle$ (order 4)
- $\langle [4] \rangle$ (order 3)
- $\langle [6] \rangle$ (order 2)
- $\langle [0] \rangle = \{[0]\}$ (order 1)

## Example 3: Subgroups of Symmetric Group $S_3$

$S_3 = \{e, (12), (13), (23), (123), (132)\}$

**All subgroups**:
- $\{e\}$ (trivial)
- $\langle (12) \rangle = \{e, (12)\}$ (order 2)
- $\langle (13) \rangle = \{e, (13)\}$ (order 2)
- $\langle (23) \rangle = \{e, (23)\}$ (order 2)
- $\langle (123) \rangle = A_3 = \{e, (123), (132)\}$ (order 3, normal)
- $S_3$ (improper)

**Normal subgroups**: $\{e\}$, $A_3$, $S_3$

## Example 4: Special Linear Group

$$\text{SL}_n(\mathbb{R}) = \{A \in \text{GL}_n(\mathbb{R}) : \det(A) = 1\} \leq \text{GL}_n(\mathbb{R})$$

**Verification**:
- Closure: $\det(AB) = \det(A)\det(B) = 1 \cdot 1 = 1$ ✓
- Identity: $\det(I) = 1$ ✓
- Inverse: $\det(A^{-1}) = \frac{1}{\det(A)} = 1$ ✓

**Normal**: $\text{SL}_n(\mathbb{R}) \triangleleft \text{GL}_n(\mathbb{R})$ (kernel of determinant)

**Index**: $[\text{GL}_n(\mathbb{R}) : \text{SL}_n(\mathbb{R})] = \infty$

## Example 5: Center^[중심]

Group $G$의 **center^[중심]**:

$$Z(G) = \{g \in G : gx = xg \; \forall x \in G\}$$

$G$의 모든 원소와 교환가능한 원소들

**Subgroup**: $Z(G) \leq G$ (easy to verify)

**Normal**: $Z(G) \triangleleft G$ (characteristic subgroup)

**예**:
- $Z(\mathbb{Z}) = \mathbb{Z}$ (abelian)
- $Z(S_3) = \{e\}$
- $Z(\text{GL}_n(\mathbb{R})) = \{\lambda I : \lambda \in \mathbb{R}^\times\}$ (scalar matrices)

## Example 6: Centralizer^[중심화원]

원소 $a \in G$의 **centralizer^[중심화원]**:

$$C_G(a) = \{g \in G : ga = ag\}$$

$a$와 교환가능한 원소들

**Subgroup**: $C_G(a) \leq G$

**Not normal** (일반적으로)

## Example 7: Normalizer^[정규화원]

Subgroup $H \leq G$의 **normalizer^[정규화원]**:

$$N_G(H) = \{g \in G : gHg^{-1} = H\}$$

$H$를 conjugation으로 보존하는 원소들

**Properties**:
- $N_G(H) \leq G$
- $H \leq N_G(H)$
- $H \triangleleft N_G(H)$ (largest subgroup where $H$ is normal)

## Example 8: Alternating Group

$$A_n = \{\sigma \in S_n : \sigma \text{ is even permutation}\} \leq S_n$$

**Order**: $|A_n| = \displaystyle\frac{n!}{2}$

**Normal**: $A_n \triangleleft S_n$ (kernel of sign homomorphism)

**Index**: $[S_n : A_n] = 2$

**Simple**: $A_n$ is simple for $n \geq 5$ (no nontrivial normal subgroups)

## Example 9: Cyclic Subgroups

모든 $g \in G$에 대해:

$$\langle g \rangle = \{g^n : n \in \mathbb{Z}\} \leq G$$

**Properties**:
- Always cyclic
- $|\langle g \rangle| = \text{ord}(g)$
- Smallest subgroup containing $g$

자세한 내용은 [[Generator]] 참조

## Example 10: Intersection of Subgroups

$H, K \leq G$이면:

$$H \cap K \leq G$$

**Not true for union**: $H \cup K$는 일반적으로 subgroup 아님!

**반례**: $\mathbb{Z}/4\mathbb{Z}$에서 $\langle [2] \rangle \cup \langle [1] \rangle$

---

# <span class="header-properties">Properties</span>

## Lagrange's Theorem^[라그랑주 정리]

Finite group $G$와 subgroup $H \leq G$에 대해:

$$|H| \text{ divides } |G|$$

더 정확히:

$$|G| = |H| \cdot [G : H]$$

### Proof^[증명]

1. Cosets는 $G$의 partition
2. 각 coset의 크기 = $|H|$
3. Coset 개수 = $[G : H]$
4. 따라서 $|G| = |H| \cdot [G : H]$

### Corollaries^[따름정리]

1. **원소의 위수**: $\text{ord}(g) \mid |G|$ for all $g \in G$
2. **Prime order**: $|G| = p$ (prime) $\Rightarrow$ $G \cong \mathbb{Z}/p\mathbb{Z}$ (cyclic)
3. **Fermat's Little Theorem**: $|G| = p$ $\Rightarrow$ $g^p = e$ for all $g \in G$

**주의**: 역은 성립 안 함! $d \mid |G|$이라고 해서 order $d$인 subgroup이 존재하는 것은 아님

**반례**: $A_4$ (order 12)는 order 6인 subgroup 없음

## Subgroup Lattice^[부분군 격자]

Group $G$의 모든 subgroups의 집합은 **lattice^[격자]** 구조:

### Operations

- **Join^[결합]**: $H \vee K = \langle H \cup K \rangle$ (smallest subgroup containing both)
- **Meet^[교]**: $H \wedge K = H \cap K$ (largest subgroup in both)

### Properties

1. $H \cap K \leq H, K$
2. $H, K \leq \langle H \cup K \rangle$
3. Partial order: $H \leq K$ (inclusion)

### Example: $\mathbb{Z}/12\mathbb{Z}$

```
        ⟨[1]⟩ (12)
       /   |   \
      /    |    \
   ⟨[2]⟩  ⟨[3]⟩  ⟨[4]⟩
   (6)    (4)    (3)
      \    |    /
       \   |   /
        ⟨[6]⟩ (2)
          |
        {[0]} (1)
```

## Correspondence Theorem^[대응 정리]

Normal subgroup $N \triangleleft G$에 대해:

$$\{H : N \subseteq H \subseteq G\} \leftrightarrow \{\bar{H} : \bar{H} \leq G/N\}$$

**대응**: $H \mapsto H/N$

**성질 보존**:
- $H_1 \subseteq H_2 \Leftrightarrow H_1/N \subseteq H_2/N$
- $H \triangleleft G \Leftrightarrow H/N \triangleleft G/N$
- $[G : H] = [G/N : H/N]$

자세한 내용은 [[Quotient Group]] 참조

## Tower Law^[탑 법칙]

$$H \leq K \leq G \Rightarrow [G : H] = [G : K][K : H]$$

**증명**: Cosets의 계산

**응용**: Index 계산 간소화

## Cauchy's Theorem^[코시 정리]

Finite group $G$와 prime $p \mid |G|$에 대해:

$$\exists g \in G, \; \text{ord}(g) = p$$

**의미**: $|G|$의 prime divisor마다 그 order의 원소 존재

**강화**: Sylow theorems (더 강한 결과)

## Maximal Subgroup^[극대 부분군]

Proper subgroup $M < G$가 **maximal^[극대]**이다 $\Leftrightarrow$

$$M < H \leq G \Rightarrow H = G$$

$M$보다 큰 proper subgroup이 없음

### Properties

1. Finite group은 항상 maximal subgroup 존재
2. $M$ maximal + $M \triangleleft G$ $\Rightarrow$ $[G : M]$ is prime
3. Maximal normal subgroup: $G/M$ is simple

## Minimal Subgroup^[최소 부분군]

Nontrivial subgroup $m \neq \{e\}$가 **minimal^[최소]**이다 $\Leftrightarrow$

$$\{e\} < H \leq m \Rightarrow H = m$$

$m$보다 작은 nontrivial subgroup이 없음

**특징**: Minimal subgroups는 항상 cyclic of prime order

## Characteristic Subgroup^[특성 부분군]

Subgroup $H \leq G$가 **characteristic^[특성]**이다 (기호: $H \text{ char } G$) $\Leftrightarrow$

$$\forall \phi \in \text{Aut}(G), \; \phi(H) = H$$

모든 automorphism에 대해 불변

### Relationship

$$H \text{ char } G \Rightarrow H \triangleleft G$$

**역은 성립 안 함!**

### Examples

- $Z(G)$ char $G$ (center)
- $G'$ char $G$ (commutator subgroup)
- $\text{Tor}(G)$ char $G$ (torsion subgroup, abelian groups)

---

# <span class="header-theorem">Theorem</span>

## Sylow Theorems^[실로우 정리]

Finite group $G$, $|G| = p^n m$ where $p$ prime, $\gcd(p, m) = 1$

### First Sylow Theorem

Order $p^k$ ($k \leq n$)인 subgroup 존재

특히 order $p^n$인 **Sylow $p$-subgroup^[실로우 p-부분군]** 존재

### Second Sylow Theorem

모든 Sylow $p$-subgroups는 conjugate^[켤레]

### Third Sylow Theorem

Sylow $p$-subgroups의 개수 $n_p$:
1. $n_p \mid m$
2. $n_p \equiv 1 \pmod{p}$

**응용**: Group classification, structure analysis

## Frattini Subgroup^[프라티니 부분군]

$$\Phi(G) = \bigcap_{M \text{ maximal}} M$$

모든 maximal subgroups의 교집합

**Property**: $\Phi(G)$ char $G$

**Frattini's argument**: $G = N_G(P)H$ for Sylow $p$-subgroup $P$ of normal $H$

## Fitting Subgroup^[피팅 부분군]

$$F(G) = \text{largest nilpotent normal subgroup}$$

**Property**: $F(G)$ char $G$

**응용**: Finite group theory

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Subgroup**: "구조 내부의 작은 구조"

**메타포**:
- **Russian dolls**: 작은 인형들이 큰 인형 안에
- **Subset**: 집합의 부분집합과 유사하지만 구조 보존
- **Department in company**: 회사 내 부서 (독립적 운영)

**핵심**: 
- 부모 group의 연산 상속
- 독립적인 group 구조

## Normal Subgroup의 중요성

**Normal subgroup = Quotient 가능**

$$N \triangleleft G \Rightarrow G/N \text{ is a group}$$

**직관**: $N$이 "양립"하면 나눗셈 가능

**Non-normal**: Quotient 정의 불가 (well-defined 안 됨)

자세한 내용은 [[Quotient Group]] 참조

## Index의 의미

$$[G : H] = \frac{\text{"크기 of } G\text{"}}{\text{"크기 of } H\text{"}}$$

**직관**: $G$를 $H$-sized pieces로 나눈 개수

**Finite**: $[G : H] = \displaystyle\frac{|G|}{|H|}$

**Infinite**: 여전히 의미 있음 (cardinal number)

## Coset vs Subgroup

| | **Coset** | **Subgroup** |
|---|---|---|
| 정의 | $gH$ | $H \leq G$ |
| 구조 | Set (not group) | Group |
| 연산 | 일반적으로 없음 | Inherited |
| 예 | $2 + 5\mathbb{Z}$ | $5\mathbb{Z}$ |

**예외**: $gH = H$ $\Leftrightarrow$ $g \in H$

## 표기법

| 표기 | 의미 |
|------|------|
| $H \leq G$ | $H$ is subgroup of $G$ |
| $H < G$ | $H$ is proper subgroup |
| $N \triangleleft G$ | $N$ is normal subgroup |
| $H \text{ char } G$ | $H$ is characteristic |
| $[G : H]$ | Index |
| $gH$ | Left coset |
| $Z(G)$ | Center |
| $C_G(a)$ | Centralizer |
| $N_G(H)$ | Normalizer |

## Subgroup Tests 비교

| Test | Conditions | Usage |
|------|-----------|-------|
| Full | 4 conditions | Definition |
| Two-step | 3 conditions | General |
| One-step | 1 condition | Most efficient |
| Finite | Closure only | Finite groups |

**추천**: One-step test (가장 간편)

## Common Pitfall^[흔한 실수]

### 1. Union of subgroups

✗ $H, K \leq G \Rightarrow H \cup K \leq G$?

✓ 일반적으로 **아니오**!

**반례**: $\langle 2 \rangle \cup \langle 3 \rangle$ in $\mathbb{Z}$
- $2, 3 \in H \cup K$ but $2 + 3 = 5 \notin H \cup K$

✓ $H \cup K \leq G \Leftrightarrow H \subseteq K$ or $K \subseteq H$

### 2. Converse of Lagrange

✗ $d \mid |G| \Rightarrow$ order $d$인 subgroup 존재?

✓ 일반적으로 **아니오**!

**반례**: $A_4$ (order 12)는 order 6인 subgroup 없음

✓ Cyclic groups에서는 성립

### 3. Normal = Subgroup?

✗ 모든 subgroup이 normal?

✓ Abelian groups에서만!

Non-abelian에서는 many non-normal subgroups

### 4. Maximal ⇒ Normal?

✗ Maximal subgroup이 항상 normal?

✓ **아니오** (일반적으로)

**맞는 경우**: Index 2인 subgroup은 항상 normal

### 5. Characteristic ⇔ Normal?

✗ Characteristic = Normal?

✓ Characteristic $\Rightarrow$ Normal (but not conversely)

**반례**: Every subgroup of abelian은 normal, but not all characteristic

## 응용

**Group Classification**:
- Structure analysis
- Composition series
- Simple groups

**Number Theory**:
- Sylow theorems
- Class groups
- Galois groups

**Geometry**:
- Symmetry groups
- Fundamental groups
- Covering spaces

**Physics**:
- Gauge symmetries
- Conservation laws
- Crystal structures

## 역사적 배경

**19세기**:
- Lagrange (1770s): Lagrange's theorem
- Cauchy (1845): Cauchy's theorem
- Sylow (1872): Sylow theorems

**발전**:
- Normal subgroups: Galois theory에서 유래
- Lattice theory: 20세기 발전
- Computational group theory: 현대

## 관련 개념

- [[Group]]: Basic group theory
- [[Quotient Group]]: Normal subgroups and quotients
- [[Generator]]: Cyclic subgroups
- [[Homomorphism]]: Kernels and images
- [[Isomorphism]]: Subgroup structure preservation

## 추가 학습 주제

**기초**:
- Lagrange's theorem
- Normal subgroups
- Cosets and index

**중급**:
- Sylow theorems
- Subgroup lattices
- Composition series

**고급**:
- Frattini subgroup
- Fitting subgroup
- Subnormal series

