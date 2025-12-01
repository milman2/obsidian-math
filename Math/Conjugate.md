# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Group Action]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Conjugation^[켤레]

### Conjugation of Elements^[원소의 켤레]

Group $G$에서 원소 $a, b \in G$에 대해, $b$가 $a$의 **conjugate^[켤레]**이다 $\Leftrightarrow$

$$\exists g \in G : b = gag^{-1}$$

**표기**: $b = {}^g a$ 또는 $b = a^g$

**직관**: $g$로 "$a$를 변환"한 것

### Conjugation of Subgroups^[부분군의 켤레]

Subgroups $H_1, H_2 \leq G$에 대해, $H_2$가 $H_1$의 **conjugate^[켤레]**이다 $\Leftrightarrow$

$$\exists g \in G : H_2 = gH_1g^{-1}$$

여기서:

$$gH_1g^{-1} = \{ghg^{-1} : h \in H_1\}$$

## Conjugacy Class^[켤레류]

원소 $a \in G$의 **conjugacy class^[켤레류]**:

$$\text{cl}(a) = \{gag^{-1} : g \in G\}$$

**동등한 정의**: Conjugation action의 orbit^[궤도]

$$\text{cl}(a) = \mathcal{O}_a$$

$G$ acts on itself by conjugation: $g \cdot a = gag^{-1}$

## Conjugation as Group Action

**Conjugation action**: $G$ acts on itself (또는 subgroups)

$$\phi: G \times G \to G, \quad (g, a) \mapsto gag^{-1}$$

**확인**:
1. Identity: $e \cdot a = eae^{-1} = a$ 2. Compatibility: $(g_1g_2) \cdot a = g_1g_2 \cdot a \cdot (g_1g_2)^{-1} = g_1 \cdot (g_2 \cdot a)$ 
자세한 내용은 [[Group Action]] 참조

---

# <span class="header-definition">Related Subgroups</span>

## Centralizer^[중심화군]

원소 $a \in G$의 **centralizer^[중심화군]**:

$$C_G(a) = \{g \in G : ga = ag\} = \{g \in G : gag^{-1} = a\}$$

**의미**: $a$와 교환가능한(commute) 모든 원소

**다른 관점**: $a$의 stabilizer^[안정화군] under conjugation action

$$C_G(a) = \text{Stab}_G(a) = G_a$$

### 성질

1. $C_G(a) \leq G$ (subgroup)
2. $a \in C_G(a)$ (자기 자신과는 교환)
3. $C_G(a) = G \Leftrightarrow a \in Z(G)$ (center^[중심])

## Centralizer of Subgroup

Subgroup $H \leq G$의 **centralizer^[중심화군]**:

$$C_G(H) = \{g \in G : gh = hg \; \forall h \in H\}$$

**의미**: $H$의 모든 원소와 교환가능한 원소들

### 성질

1. $C_G(H) \leq G$
2. $C_G(H) \triangleleft N_G(H)$ (normal in normalizer)
3. $H \cap C_G(H) = Z(H)$ (center of $H$)

## Normalizer^[정규화군]

Subgroup $H \leq G$의 **normalizer^[정규화군]**:

$$N_G(H) = \{g \in G : gHg^{-1} = H\}$$

**의미**: Conjugation으로 $H$를 보존하는 원소들

### 동등한 정의

$$N_G(H) = \{g \in G : gH = Hg\}$$

좌 코셋 = 우 코셋

### 성질

1. $N_G(H) \leq G$ (subgroup)
2. $H \leq N_G(H)$ (항상)
3. $H \triangleleft N_G(H)$ ($H$ is normal in its normalizer)
4. $H \triangleleft G \Leftrightarrow N_G(H) = G$

### Hierarchy^[계층]

$$C_G(H) \subseteq N_G(H) \subseteq G$$

$$H \subseteq N_G(H) \subseteq G$$

- **Centralizer**: 모든 $h \in H$와 교환
- **Normalizer**: $H$ 전체를 보존
- **$H \triangleleft G$**: 모든 $g$가 $H$ 보존

## Center^[중심]

Group $G$의 **center^[중심]**:

$$Z(G) = \{z \in G : gz = zg \; \forall g \in G\}$$

**동등한 정의들**:

1. $Z(G) = C_G(G)$ (모든 원소와 교환)
2. $Z(G) = \bigcap_{a \in G} C_G(a)$ (모든 centralizer의 교집합)
3. $Z(G) = \{a \in G : |\text{cl}(a)| = 1\}$ (conjugacy class가 singleton)

### 성질

1. $Z(G) \triangleleft G$ (normal subgroup)
2. $Z(G)$는 abelian^[아벨]
3. $G$ abelian $\Leftrightarrow Z(G) = G$

---

# <span class="header-properties">Properties</span>

## Conjugation is Equivalence Relation

원소들에 대한 conjugation은 equivalence relation^[동치 관계]:

$$a \sim b \Leftrightarrow \exists g : b = gag^{-1}$$

**확인**:
1. **Reflexivity^[반사성]**: $a = eae^{-1}$ 2. **Symmetry^[대칭성]**: $b = gag^{-1} \Rightarrow a = g^{-1}bg$ 3. **Transitivity^[추이성]**: $b = g_1ag_1^{-1}$, $c = g_2bg_2^{-1} \Rightarrow c = (g_2g_1)a(g_2g_1)^{-1}$ 
**Equivalence classes**: Conjugacy classes

자세한 내용은 [[Equivalence Relation and Partitions]] 참조

## Partition by Conjugacy Classes

$$G = \bigsqcup_{i} \text{cl}(a_i)$$

$G$는 conjugacy classes로 분할됨

**Representative system**: 각 class에서 하나씩 선택

## Class Equation^[류 방정식]

$$|G| = |Z(G)| + \sum_{i} [G : C_G(a_i)]$$

여기서 합은 non-central conjugacy classes에 대해

**유도**:
- Center: $|\text{cl}(z)| = 1$ for $z \in Z(G)$
- Non-central: $|\text{cl}(a_i)| = [G : C_G(a_i)] > 1$

자세한 내용은 [[Group Action]], [[Orbit-Stabilizer Theorem]] 참조

## Conjugacy Class Size

Orbit-Stabilizer Theorem^[궤도-안정화군 정리]에 의해:

$$|\text{cl}(a)| = [G : C_G(a)] = \frac{|G|}{|C_G(a)|}$$

**따름정리**: $|\text{cl}(a)|$은 $|G|$의 약수

## Conjugation Preserves Properties

$b = gag^{-1}$이면:

1. **Order^[위수]**: $|b| = |a|$
2. **Abelianness**: $ab = ba \Leftrightarrow gbg^{-1} \cdot gag^{-1} = gag^{-1} \cdot gbg^{-1}$
3. **Subgroup structure**: $H \leq G \Rightarrow gHg^{-1} \leq G$
4. **Normality**: $H \triangleleft K \Rightarrow gHg^{-1} \triangleleft gKg^{-1}$

**직관**: Conjugation은 "내부 자기동형사상^[inner automorphism]"

## Inner Automorphism^[내부 자기동형사상]

각 $g \in G$에 대해:

$$\phi_g: G \to G, \quad \phi_g(a) = gag^{-1}$$

**성질**:
1. $\phi_g$는 group homomorphism^[군 준동형사상]
2. $\phi_g$는 bijection (automorphism^[자기동형사상])
3. $\phi_g \circ \phi_h = \phi_{gh}$

**Inner automorphism group**:

$$\text{Inn}(G) = \{\phi_g : g \in G\} \leq \text{Aut}(G)$$

**정리**: $\text{Inn}(G) \cong G/Z(G)$

---

# <span class="header-examples">Examples</span>

## Example 1: Abelian Groups

$G$가 abelian^[아벨]이면:

$$gag^{-1} = agg^{-1} = a$$

- 모든 conjugacy class는 singleton: $\text{cl}(a) = \{a\}$
- $C_G(a) = G$ for all $a$
- $Z(G) = G$
- Class equation: $|G| = |G|$ (자명)

## Example 2: $S_3$

**Conjugacy classes**:

1. $\text{cl}(e) = \{e\}$
2. $\text{cl}((12)) = \{(12), (13), (23)\}$ (모든 transpositions)
3. $\text{cl}((123)) = \{(123), (132)\}$ (모든 3-cycles)

**크기**: $1 + 3 + 2 = 6 = |S_3|$ 
**Centralizers**:
- $C_{S_3}(e) = S_3$
- $C_{S_3}((12)) = \{e, (12)\}$ (order 2)
- $C_{S_3}((123)) = \{e, (123), (132)\}$ (order 3)

**Center**: $Z(S_3) = \{e\}$

## Example 3: $D_4$ (Dihedral Group)

정사각형의 대칭군, $|D_4| = 8$

**Conjugacy classes**:
1. $\{e\}$
2. $\{r, r^3\}$ (90°, 270° 회전)
3. $\{r^2\}$ (180° 회전)
4. $\{s, r^2s\}$ (대각선 반사)
5. $\{rs, r^3s\}$ (변 반사)

**Class equation**: $8 = 1 + 2 + 1 + 2 + 2$

**Center**: $Z(D_4) = \{e, r^2\}$ (order 2)

## Example 4: Matrix Groups

$G = \text{GL}_n(\mathbb{R})$

**Conjugate matrices**: Same eigenvalues

$$B = PAP^{-1} \Leftrightarrow \text{det}(B - \lambda I) = \text{det}(A - \lambda I)$$

**Conjugacy class**: Matrices with same Jordan canonical form^[조르당 표준형]

## Example 5: Normalizer in $S_4$

$H = \{e, (12)(34)\} \leq S_4$

**Normalizer**: $N_{S_4}(H) = \{g \in S_4 : gHg^{-1} = H\}$

포함하는 원소:
- $H$ 자체
- $(13)(24)$, $(14)(23)$
- All permutations preserving $\{\{1,2\}, \{3,4\}\}$

$|N_{S_4}(H)| = 8$

## Example 6: Sylow Subgroups

**Sylow Second Theorem**: 모든 Sylow $p$-subgroups는 conjugate

예: $|G| = 12 = 2^2 \cdot 3$

- Sylow 2-subgroups: order 4, 서로 conjugate
- Sylow 3-subgroups: order 3, 서로 conjugate

자세한 내용은 [[Sylow Theorem]] 참조

---

# <span class="header-theorem">Theorem</span>

## Conjugacy and Normality

**정리**: $H \triangleleft G$ (normal^[정규]) $\Leftrightarrow$ $gHg^{-1} = H$ for all $g \in G$

즉, **$H$가 normal $\Leftrightarrow$ $H$는 자기 자신과만 conjugate**

**따름정리**: 
- Unique Sylow $p$-subgroup $\Rightarrow$ Normal
- $[G:H] = 2 \Rightarrow H \triangleleft G$

## N/C Theorem

**정리**: $H \leq G$에 대해

$$\frac{N_G(H)}{C_G(H)} \hookrightarrow \text{Aut}(H)$$

$N_G(H)/C_G(H)$는 $\text{Aut}(H)$의 subgroup과 isomorphic

**의미**: Normalizer와 centralizer 사이의 관계

## Conjugacy in Quotients

$N \triangleleft G$이면, $G/N$의 conjugacy class는:

$$\text{cl}_{G/N}(aN) = \{gag^{-1}N : g \in G\}$$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

### Conjugation = "내부 관점의 대칭"

**$b = gag^{-1}$**:
1. $g^{-1}$: "좌표계를 $g^{-1}$만큼 이동"
2. $a$: "원래 위치에서 $a$ 작용"
3. $g$: "좌표계를 원래대로"

**기하학적**: $g$로 회전/변환 후 $a$ 적용, 다시 역변환

### Centralizer = "교환가능한 것들"

$ga = ag$ $\Leftrightarrow$ "$a$와 $g$의 순서 바꿔도 됨"

### Normalizer = "구조 보존"

$gHg^{-1} = H$ $\Leftrightarrow$ "Conjugation으로 $H$ 불변"

## 계층 구조

```
G
|
N_G(H)  ← H를 집합으로 보존
|
C_G(H)  ← H의 모든 원소와 교환
|
H       ← H 자체
```

## 응용 분야

### Group Theory^[군론]

**핵심 도구**:
- Normal subgroups 특징화
- Sylow theorems
- Class equation
- $p$-groups 연구

### Representation Theory^[표현론]

**Character theory**: Conjugacy classes가 기본 단위

**Class functions**: Conjugacy class에서 constant

### Galois Theory^[갈루아 이론]

**Galois group action**: Field automorphisms의 conjugacy

### Lie Theory^[리 이론]

**Adjoint action**: Lie groups의 conjugation

$$\text{Ad}_g(X) = gXg^{-1}$$

### Chemistry^[화학]

**Point groups**: 분자 대칭의 conjugacy classes

### Physics^[물리학]

**Gauge theory**: Gauge transformations = conjugations

## 계산 팁

### Conjugacy Class 찾기

1. **Center 먼저**: $Z(G) = \{$ singleton classes $\}$
2. **Order 같은 것끼리**: Same order $\Rightarrow$ 같은 class 가능
3. **Group action 사용**: Orbit-Stabilizer로 크기 계산

### Normalizer/Centralizer 찾기

1. **정의 직접 사용**: $gHg^{-1} = H$ 확인
2. **Index 계산**: $[G : N_G(H)]$ = conjugacy classes 개수
3. **Known subgroups**: $H \subseteq N_G(H)$ 부터 시작

## 표기법

| 표기 | 의미 |
|------|------|
| $gag^{-1}$ or ${}^g a$ | $a$의 $g$-conjugate |
| $\text{cl}(a)$ | Conjugacy class of $a$ |
| $C_G(a)$ | Centralizer of $a$ |
| $N_G(H)$ | Normalizer of $H$ |
| $Z(G)$ | Center of $G$ |
| $\text{Inn}(G)$ | Inner automorphisms |

## Common Pitfalls^[흔한 실수]

### 1. Conjugation vs Cosets

$gHg^{-1} \neq gH$ (일반적으로)

### 2. Normalizer ≠ Centralizer

$N_G(H) \supseteq C_G(H)$ (strict inclusion 보통)

### 3. Center는 항상 Normal

$Z(G) \triangleleft G$ (자동)

### 4. Conjugacy preserves order

$|gag^{-1}| = |a|$ 항상

## Related Concepts

- [[Normal Subgroup]]: $H \triangleleft G \Leftrightarrow gHg^{-1} = H$ for all $g$
- [[Group Action]]: Conjugation as action
- [[Sylow Theorem]]: Conjugacy of Sylow subgroups
- [[Quotient Group, Factor Group]]: $N_G(H)/H$
- [[Orbit-Stabilizer Theorem]]: $|\text{cl}(a)| = [G : C_G(a)]$

