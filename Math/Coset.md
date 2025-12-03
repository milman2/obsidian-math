# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Equivalence Relation and Partitions]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Hungerford, Algebra

---

# <span class="header-definition">Definition</span>

## Coset^[잉여류]

Subgroup $H \leq G$와 원소 $g \in G$에 대해:

### Left Coset^[좌잉여류]

$$gH = \{gh : h \in H\}$$

**의미**: $H$를 $g$로 "왼쪽에서" 이동

### Right Coset^[우잉여류]

$$Hg = \{hg : h \in G\}$$

**의미**: $H$를 $g$로 "오른쪽에서" 이동

### Representative^[대표원]

Coset $gH$에서 $g$를 **representative**^[대표원]라 함

**주의**: 대표원은 유일하지 않음! $gH = g'H \Leftrightarrow g^{-1}g' \in H$

## Equality of Cosets

### Left Coset Equality

$$g_1H = g_2H \Leftrightarrow g_2^{-1}g_1 \in H \Leftrightarrow g_1 \in g_2H$$

**증명**:
- ($\Rightarrow$): $g_1 \in g_1H = g_2H$ $\Rightarrow$ $g_1 = g_2h$ for some $h \in H$ $\Rightarrow$ $g_2^{-1}g_1 = h \in H$ - ($\Leftarrow$): $g_2^{-1}g_1 = h \in H$ $\Rightarrow$ $g_1 = g_2h$ $\Rightarrow$ $g_1H = g_2hH = g_2H$ 
### Right Coset Equality

$$Hg_1 = Hg_2 \Leftrightarrow g_1g_2^{-1} \in H \Leftrightarrow g_1 \in Hg_2$$

### Left vs Right

**일반적으로**: $gH \neq Hg$

**같을 조건**:
1. $G$ abelian^[아벨] (모든 $g, H$에 대해)
2. $H \triangleleft G$ (normal subgroup)^[정규 부분군]

자세한 내용은 [[Normal Subgroup]] 참조

---

# <span class="header-properties">Properties</span>

## Size of Cosets

**정리**: 모든 left (또는 right) coset은 같은 크기

$$|gH| = |H| = |Hg| \quad \forall g \in G$$

**증명**: Bijection $\phi: H \to gH$, $\phi(h) = gh$
- **Injective**: $gh_1 = gh_2 \Rightarrow h_1 = h_2$
- **Surjective**: By definition 
## Partition Property^[분할 성질]

**정리**: Left cosets는 $G$를 partition

$$G = \bigsqcup_{i} g_iH$$

**의미**: 
- 각 원소는 정확히 하나의 coset에 속함
- Cosets는 disjoint or equal

### Equivalence Relation

$$g_1 \sim g_2 \Leftrightarrow g_1H = g_2H \Leftrightarrow g_2^{-1}g_1 \in H$$

**확인**:
- **Reflexive**^[반사]: $g \sim g$ (since $e \in H$) - **Symmetric**^[대칭]: $g_1 \sim g_2 \Rightarrow g_2 \sim g_1$ - **Transitive**^[추이]: $g_1 \sim g_2, g_2 \sim g_3 \Rightarrow g_1 \sim g_3$ 
**Equivalence classes** = Cosets

자세한 내용은 [[Equivalence Relation and Partitions]] 참조

## Index^[지표]

**정의**: $[G : H]$ = left cosets의 개수 = right cosets의 개수

$$[G : H] = |\{gH : g \in G\}| = |\{Hg : g \in G\}|$$

**Finite case**:

$$[G : H] = \frac{|G|}{|H|}$$

자세한 내용은 [[Lagrange's theorem]] 참조

## Coset Multiplication

**일반적으로 정의 안 됨!**

$(g_1H)(g_2H) = ?$

**문제**: Representative 선택에 의존

$g_1H = g_1'H$, $g_2H = g_2'H$이어도

$(g_1g_2)H \neq (g_1'g_2')H$ (일반적으로)

### Normal Subgroup에서만 Well-defined

$H \triangleleft G$일 때:

$$(g_1H)(g_2H) = (g_1g_2)H$$

**Well-defined** $\Rightarrow$ Quotient group $G/H$ 가능

자세한 내용은 [[Quotient Group]] 참조

## Double Cosets^[이중 잉여류]

Subgroups $H, K \leq G$에 대해:

$$HgK = \{hgk : h \in H, k \in K\}$$

**응용**: 표현론, Hecke algebras

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$ and $n\mathbb{Z}$

$H = n\mathbb{Z} = \{nk : k \in \mathbb{Z}\} \leq \mathbb{Z}$

**Left cosets** (= right cosets, abelian):

$$0 + n\mathbb{Z}, 1 + n\mathbb{Z}, 2 + n\mathbb{Z}, \ldots, (n-1) + n\mathbb{Z}$$

**예** ($n = 3$):
- $0 + 3\mathbb{Z} = \{\ldots, -6, -3, 0, 3, 6, \ldots\}$
- $1 + 3\mathbb{Z} = \{\ldots, -5, -2, 1, 4, 7, \ldots\}$
- $2 + 3\mathbb{Z} = \{\ldots, -4, -1, 2, 5, 8, \ldots\}$

**Index**: $[\mathbb{Z} : 3\mathbb{Z}] = 3$

**Quotient**: $\mathbb{Z}/3\mathbb{Z}$ (잘 정의됨, normal)

자세한 내용은 [[Cyclic Group]] 참조

## Example 2: $S_3$ and $A_3$

$G = S_3 = \{e, (12), (13), (23), (123), (132)\}$

$H = A_3 = \{e, (123), (132)\}$ (alternating group)

**Left cosets**:
- $A_3 = \{e, (123), (132)\}$
- $(12)A_3 = \{(12), (12)(123), (12)(132)\} = \{(12), (23), (13)\}$

**Partition**: $S_3 = A_3 \sqcup (12)A_3$ 
**Index**: $[S_3 : A_3] = 2$

**Normal**: $A_3 \triangleleft S_3$ (index 2이므로)

자세한 내용은 [[Symmetric Group]] 참조

## Example 3: Non-Normal Subgroup

$H = \{e, (12)\} \leq S_3$

**Left cosets**:
- $H = \{e, (12)\}$
- $(13)H = \{(13), (13)(12)\} = \{(13), (132)\}$
- $(23)H = \{(23), (23)(12)\} = \{(23), (123)\}$

**Right cosets**:
- $H = \{e, (12)\}$
- $H(13) = \{(13), (12)(13)\} = \{(13), (123)\}$
- $H(23) = \{(23), (12)(23)\} = \{(23), (132)\}$

**관찰**: $(13)H \neq H(13)$ $\Rightarrow$ $H$ not normal!

## Example 4: Dihedral Group $D_4$

$D_4 = \{e, r, r^2, r^3, s, sr, sr^2, sr^3\}$ (order 8)

$H = \langle r^2 \rangle = \{e, r^2\}$ (order 2)

**Left cosets**:
- $H = \{e, r^2\}$
- $rH = \{r, r^3\}$
- $sH = \{s, sr^2\}$
- $srH = \{sr, sr^3\}$

**Index**: $[D_4 : H] = 4$

자세한 내용은 [[Dihedral Group]] 참조

## Example 5: Additive Cosets in $\mathbb{Z}/12\mathbb{Z}$

$G = \mathbb{Z}/12\mathbb{Z}$, $H = \langle [3] \rangle = \{[0], [3], [6], [9]\}$

**Cosets**:
- $[0] + H = \{[0], [3], [6], [9]\}$
- $[1] + H = \{[1], [4], [7], [10]\}$
- $[2] + H = \{[2], [5], [8], [11]\}$

**Index**: $[\mathbb{Z}/12\mathbb{Z} : H] = 3$

**Check**: $|G|/|H| = 12/4 = 3$ 
---

# <span class="header-theorem">Theorem</span>

## Lagrange's Theorem^[라그랑주 정리]

$$|G| = |H| \cdot [G : H]$$

**Finite case**: $|H| \mid |G|$

**증명**: Cosets partition $G$ with equal size

자세한 내용은 [[Lagrange's theorem]] 참조

## Correspondence Theorem Application

$N \triangleleft G$일 때, cosets $G/N$의 subgroups $\leftrightarrow$ $G$의 subgroups containing $N$

자세한 내용은 [[Correspondence Theorem]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Coset = "평행이동된 부분군"**

### 메타포: 평행이동

**Subgroup** $H$: 원점을 지나는 부분공간

**Coset** $gH$: $H$를 $g$만큼 이동

**예**: $\mathbb{Z}$에서 $n\mathbb{Z}$
- $n\mathbb{Z}$: $0$을 지나는 "격자"
- $k + n\mathbb{Z}$: 격자를 $k$만큼 이동

### 메타포: 동치류

**Coset** = **Equivalence class**

$g_1H = g_2H \Leftrightarrow g_1 \sim g_2$ (modulo $H$)

**의미**: "$H$로 보았을 때 같다"

## 왜 중요한가?

### 1. Partition of Group

**Cosets는 group을 분할**

구조 분석의 기본 도구

### 2. Lagrange's Theorem

$$|H| \mid |G|$$

Cosets의 counting으로 증명

### 3. Quotient Groups

**Normal subgroup**: Left = Right cosets

$\Rightarrow$ Coset multiplication well-defined

$\Rightarrow$ Quotient group $G/H$

### 4. Classification

**Group 분류**의 핵심 도구

Coset structure → Group structure

## Left vs Right Cosets

| | **Left Coset** | **Right Coset** |
|---|---|---|
| **정의** | $gH$ | $Hg$ |
| **연산** | 왼쪽 곱셈 | 오른쪽 곱셈 |
| **관례** | 주로 사용 | 상황에 따라 |
| **Abelian** | $gH = Hg$ | $gH = Hg$ |
| **Normal** | $gH = Hg$ | $gH = Hg$ |

**일반적으로**: $gH \neq Hg$ (non-abelian, non-normal)

## Representative 선택

**Coset** $gH$의 모든 원소가 representative 가능

$$gH = g'H \Leftrightarrow g' \in gH$$

**관례**: 
- 가장 "simple" 원소 선택
- 예: $\mathbb{Z}/n\mathbb{Z}$에서 $\{0, 1, \ldots, n-1\}$

## Index의 의미

**$[G : H]$** = "몇 개의 cosets로 나누어지는가?"

**Finite**: $[G : H] = |G|/|H|$

**Infinite**: 
- $[\mathbb{Z} : 2\mathbb{Z}] = 2$ (finite index)
- $[\mathbb{R} : \mathbb{Z}] = \infty$ (infinite index)

## Coset Enumeration

**계산 방법**:
1. Identity coset: $H$
2. $g \notin H$인 $g$ 선택 → $gH$ 계산
3. 반복 (모든 원소가 cover될 때까지)

**Todd-Coxeter algorithm**: 효율적 enumeration

## 응용 분야

**Group Theory**:
- Lagrange's theorem
- Sylow theorems
- Quotient groups

**Number Theory**:
- Modular arithmetic ($\mathbb{Z}/n\mathbb{Z}$)
- Class groups
- Ideal theory

**Topology**:
- Covering spaces
- Fundamental groups
- Homogeneous spaces $G/H$

**Representation Theory**:
- Induced representations
- Frobenius reciprocity

## 역사적 배경

**Évariste Galois** (1811-1832):
- Cosets 개념 도입
- Group theory의 기초

**Joseph-Louis Lagrange** (1736-1813):
- Polynomial equations 연구
- Lagrange's theorem (나중에 공식화)

**발전**:
- 19세기: Galois theory
- 20세기: Abstract algebra
- 현대: Computational group theory

## 표기법

| 표기 | 의미 |
|------|------|
| $gH$ | Left coset |
| $Hg$ | Right coset |
| $[G : H]$ | Index |
| $G/H$ | Set of cosets (or quotient if normal) |
| $\sqcup$ | Disjoint union |

## Common Pitfall^[흔한 실수]

### 1. Coset ≠ Subgroup

$gH$는 일반적으로 subgroup 아님 (unless $g \in H$)

### 2. Representative 유일성

$gH$의 representative는 유일하지 않음

$gH = g'H$ for many $g'$

### 3. Left ≠ Right (일반적으로)

$gH \neq Hg$ (non-abelian, non-normal case)

### 4. Coset multiplication

$(g_1H)(g_2H)$는 일반적으로 well-defined 아님

Normal일 때만 가능!

### 5. $G/H$ 표기

$H$ normal 아니면 $G/H$ = set (group 아님)

## 관련 개념

- [[Subgroup]]: Cosets의 기초
- [[Normal Subgroup]]: Left = Right cosets
- [[Quotient Group]]: Cosets with group structure
- [[Lagrange's theorem]]: Coset counting
- [[Equivalence Relation and Partitions]]: Cosets as equivalence classes

## 추가 학습 주제

**기초**:
- Coset 정의
- Left vs Right
- Partition property

**중급**:
- Index calculations
- Normal subgroups
- Quotient groups

**고급**:
- Double cosets
- Coset enumeration algorithms
- Transversals

