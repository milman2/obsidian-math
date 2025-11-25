# <span class="header-prerequisite">Prerequisite</span>
- [[Function]]
- Binary operation (이항 연산 기초)

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra

---

# <span class="header-definition">Definition</span>

## Group^[군]

집합 $G$와 binary operation^[이항 연산] $\cdot: G \times G \to G$에 대해, $(G, \cdot)$가 **group^[군]**이다 $\Leftrightarrow$ 다음 네 가지 공리를 만족:

### 1. Closure^[닫혀있음]

$$\forall a, b \in G, \quad a \cdot b \in G$$

### 2. Associativity^[결합법칙]

$$\forall a, b, c \in G, \quad (a \cdot b) \cdot c = a \cdot (b \cdot c)$$

### 3. Identity Element^[항등원]

$$\exists e \in G, \; \forall a \in G, \quad e \cdot a = a \cdot e = a$$

### 4. Inverse Element^[역원]

$$\forall a \in G, \; \exists a^{-1} \in G, \quad a \cdot a^{-1} = a^{-1} \cdot a = e$$

**표기**: 연산이 명확할 때 $a \cdot b$를 $ab$로 표기

## Abelian Group^[아벨군]

Group $G$가 **abelian^[아벨]** (또는 **commutative^[가환]**)이다 $\Leftrightarrow$ 다음을 만족:

### Commutativity^[교환법칙]

$$\forall a, b \in G, \quad a \cdot b = b \cdot a$$

**표기**: Abelian group의 연산은 종종 $+$로 표기 (additive notation^[덧셈 표기])

## Order^[위수]

### Group의 위수

$$|G| = \text{cardinality of } G$$

- **Finite group^[유한군]**: $|G| < \infty$
- **Infinite group^[무한군]**: $|G| = \infty$

### 원소의 위수

원소 $g \in G$의 **order^[위수]** $\text{ord}(g)$:

$$\text{ord}(g) = \min\{n \in \mathbb{N} : g^n = e\}$$

만약 그런 $n$이 없으면 $\text{ord}(g) = \infty$

## Subgroup^[부분군]

$H \subseteq G$가 **subgroup^[부분군]**이다 (기호: $H \leq G$) $\Leftrightarrow$ $H$가 $G$의 연산으로 group

### Subgroup Test

$H \leq G$ $\Leftrightarrow$ 다음을 만족:
1. $H \neq \emptyset$
2. $\forall a, b \in H, \quad ab \in H$
3. $\forall a \in H, \quad a^{-1} \in H$

**간편 판정법**: $\forall a, b \in H, \quad ab^{-1} \in H$ $\Leftrightarrow$ $H \leq G$

## Group Homomorphism^[군 준동형사상]

함수 $\phi: G \to H$ (where $G, H$ are groups)가 **homomorphism^[준동형사상]**이다 $\Leftrightarrow$

$$\forall a, b \in G, \quad \phi(ab) = \phi(a)\phi(b)$$

### 중요한 성질

1. $\phi(e_G) = e_H$ (항등원을 항등원으로)
2. $\phi(a^{-1}) = \phi(a)^{-1}$ (역원을 역원으로)
3. $\phi(a^n) = \phi(a)^n$ for all $n \in \mathbb{Z}$

### 특수한 경우

- **Isomorphism^[동형사상]**: bijective^[전단사] homomorphism
  - 기호: $G \cong H$
- **Endomorphism^[자기준동형사상]**: $\phi: G \to G$
- **Automorphism^[자기동형사상]**: isomorphism $\phi: G \to G$

## Kernel and Image^[핵과 상]

Homomorphism $\phi: G \to H$에 대해:

### Kernel^[핵]

$$\ker(\phi) = \{g \in G : \phi(g) = e_H\}$$

**성질**: $\ker(\phi) \triangleleft G$ (normal subgroup^[정규 부분군])

### Image^[상]

$$\text{im}(\phi) = \{\phi(g) : g \in G\} = \phi(G)$$

**성질**: $\text{im}(\phi) \leq H$ (subgroup)

## Torsion Element and Torsion Subgroup^[비틀림 원소와 비틀림 부분군]

**주의**: 이 개념은 주로 abelian groups에서 사용 (additive notation)

### Torsion Element^[비틀림 원소]

Abelian group $(G, +)$의 원소 $g \in G$가 **torsion element^[비틀림 원소]**이다 $\Leftrightarrow$

$$\exists n \in \mathbb{N}, n > 0 : ng = 0$$

즉, finite order^[유한 위수]를 가짐

**Multiplicative notation**: $g^n = e$ for some $n > 0$

### Torsion Subgroup^[비틀림 부분군]

Abelian group $G$의 **torsion subgroup^[비틀림 부분군]**:

$$T(G) = \{g \in G : g \text{ has finite order}\}$$

모든 torsion elements의 집합

**성질**: $T(G) \leq G$ (abelian group의 subgroup)

**증명**: 
- $0 \in T(G)$ (identity)
- $g, h \in T(G)$이고 $ng = 0$, $mh = 0$이면 $nm(g-h) = 0$ (abelian이므로)

### Torsion-free Group^[비틀림 없는 군]

Abelian group $G$가 **torsion-free^[비틀림 없는]**이다 $\Leftrightarrow$

$$T(G) = \{0\}$$

Identity를 제외한 모든 원소가 infinite order

### Examples

**Torsion groups** (모든 원소가 torsion):
- $\mathbb{Z}/n\mathbb{Z}$ (finite abelian groups는 모두 torsion)
- $\mathbb{Q}/\mathbb{Z}$ (rational numbers mod integers)

**Torsion-free groups**:
- $\mathbb{Z}$ (0 외의 모든 원소가 infinite order)
- $\mathbb{Q}$ (rational numbers)
- $\mathbb{R}$ (real numbers)

**Mixed** (torsion + torsion-free):
- $\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$
- $T(G) = \{0\} \times \mathbb{Z}/n\mathbb{Z}$

### Structure Theorem for Finitely Generated Abelian Groups

Finitely generated abelian group $G$에 대해:

$$G \cong \mathbb{Z}^r \times T(G)$$

where:
- $r = \text{rank}(G)$ (torsion-free part의 rank)
- $T(G)$ is finite (torsion part)

**분해**: Free part $\oplus$ Torsion part

---

# <span class="header-examples">Examples</span>

## Example 1: 정수의 덧셈

$$(\mathbb{Z}, +)$$

- **Identity**: $0$
- **Inverse**: $-n$ for $n \in \mathbb{Z}$
- **Abelian**: Yes
- **Order**: $|\mathbb{Z}| = \infty$

## Example 2: Modular Arithmetic^[모듈러 산술]

$$(\mathbb{Z}/n\mathbb{Z}, +)$$

- **원소**: $\{\overline{0}, \overline{1}, \ldots, \overline{n-1}\}$
- **Identity**: $\overline{0}$
- **Inverse**: $\overline{k}^{-1} = \overline{n-k}$
- **Order**: $n$

## Example 3: 실수의 곱셈

$$(\mathbb{R}^\times, \cdot)$$ where $\mathbb{R}^\times = \mathbb{R} \setminus \{0\}$

- **Identity**: $1$
- **Inverse**: $\frac{1}{x}$ for $x \neq 0$
- **Abelian**: Yes

## Example 4: General Linear Group^[일반 선형군]

$$\text{GL}_n(\mathbb{R}) = \{A \in \mathbb{R}^{n \times n} : \det(A) \neq 0\}$$

행렬 곱셈에 대한 group

- **Identity**: $I_n$ (identity matrix^[항등행렬])
- **Inverse**: $A^{-1}$
- **Abelian**: No (for $n \geq 2$)

## Example 5: Symmetric Group^[대칭군]

$$S_n = \{\text{permutations of } \{1, 2, \ldots, n\}\}$$

- **Order**: $|S_n| = n!$
- **Identity**: identity permutation
- **Abelian**: No (for $n \geq 3$)

**예**: $S_3$ has 6 elements

## Example 6: Cyclic Group^[순환군]

$$C_n = \langle g \rangle = \{e, g, g^2, \ldots, g^{n-1}\}$$

where $g^n = e$

- **Generator^[생성원]**: $g$
- **Order**: $n$
- **Abelian**: Yes (항상)

**무한 순환군**: $C_\infty = \langle g \rangle = \{g^n : n \in \mathbb{Z}\}$ where $g^n \neq e$ for all $n \neq 0$

## Example 7: Dihedral Group^[이면체군]

$$D_n = \text{symmetries of regular } n\text{-gon}$$

- **Order**: $|D_n| = 2n$
- **원소**: $n$ rotations + $n$ reflections
- **Abelian**: No (for $n \geq 3$)

**예**: $D_4$ = symmetries of square (8 elements)

## Example 8: Quaternion Group^[사원수군]

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

with relations: $i^2 = j^2 = k^2 = ijk = -1$

- **Order**: 8
- **Abelian**: No

---

# <span class="header-properties">Properties</span>

## Uniqueness^[유일성]

### 항등원의 유일성

Group의 identity element는 유일

**증명**: $e, e'$가 모두 identity면,
$$e = ee' = e'$$

### 역원의 유일성

각 원소의 inverse는 유일

**증명**: $b, c$가 모두 $a$의 inverse면,
$$b = b(ac) = (ba)c = c$$

## Cancellation Laws^[소거법칙]

### Left Cancellation^[왼쪽 소거]

$$ab = ac \Rightarrow b = c$$

### Right Cancellation^[오른쪽 소거]

$$ba = ca \Rightarrow b = c$$

## Lagrange's Theorem^[라그랑주 정리]

유한군 $G$와 subgroup $H \leq G$에 대해:

$$|H| \text{ divides } |G|$$

더 정확히:

$$|G| = |H| \cdot [G : H]$$

여기서 $[G : H]$는 index^[지표] (coset의 개수)

### 따름정리

1. 원소의 위수는 군의 위수를 나눔: $\text{ord}(g) \mid |G|$
2. $|G| = p$ (prime^[소수]) $\Rightarrow$ $G \cong C_p$ (cyclic)

## Cayley's Theorem^[케일리 정리]

모든 group은 어떤 symmetric group의 subgroup과 isomorphic

$$G \cong \text{subgroup of } S_{|G|}$$

**의미**: 모든 군을 permutation group으로 볼 수 있음

---

# <span class="header-theorem">Theorem</span>

## Classification of Small Groups^[작은 군의 분류]

### 위수 1-5

- $|G| = 1$: $G \cong \{e\}$ (trivial group^[자명군])
- $|G| = 2$: $G \cong C_2$
- $|G| = 3$: $G \cong C_3$
- $|G| = 4$: $G \cong C_4$ 또는 $G \cong C_2 \times C_2$ (Klein four-group)
- $|G| = 5$: $G \cong C_5$

### 위수 6

- $G \cong C_6$ 또는 $G \cong S_3$ (only two)

## Fundamental Theorem of Finite Abelian Groups^[유한 아벨군의 기본 정리]

모든 finite abelian group은 cyclic group들의 direct product^[직접곱]와 isomorphic

### Invariant Factor Form^[불변 인자 형태]

$$G \cong C_{n_1} \times C_{n_2} \times \cdots \times C_{n_k}$$

where $n_i \mid n_{i+1}$ (즉, $n_i$가 $n_{i+1}$을 나눔)

### Primary Decomposition Form^[소인수 분해 형태]

$$G \cong C_{p_1^{a_1}} \times C_{p_2^{a_2}} \times \cdots \times C_{p_r^{a_r}}$$

where $p_i$는 소수 (중복 가능)

**예**: $|G| = 12$
- $C_{12}$
- $C_2 \times C_6$ (invariant factor form: $2 \mid 6$)
- $C_2 \times C_2 \times C_3$ (primary form: $C_2^2 \times C_3$)

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Group**: "대칭성"의 수학적 표현

- **기하학적 대칭**: 회전, 반사, 평행이동
- **대수적 대칭**: 방정식의 근의 치환

**핵심 아이디어**: 연산을 "되돌릴 수 있다" (invertibility^[가역성])

## 표기 관례

### Multiplicative Notation^[곱셈 표기]

- 연산: $ab$ 또는 $a \cdot b$
- 항등원: $e$ 또는 $1$
- 역원: $a^{-1}$
- 거듭제곱: $a^n = \underbrace{a \cdots a}_{n \text{ times}}$

### Additive Notation^[덧셈 표기]

Abelian group에서 주로 사용:
- 연산: $a + b$
- 항등원: $0$
- 역원: $-a$
- 거듭제곱: $na = \underbrace{a + \cdots + a}_{n \text{ times}}$

## 역사적 배경

**초기 발전** (19세기):
- **Évariste Galois**: 방정식의 풀이 가능성 연구
- **Arthur Cayley**: 추상적 group 정의 (1854)

**응용**:
- 결정학 (crystallography^[결정학]): 대칭 구조
- 암호학: RSA, 타원곡선암호
- 물리학: 대칭성과 보존법칙 (Noether's theorem)
- 화학: 분자 대칭

## 관련 개념

### 더 약한 구조

- **Semigroup^[반군]**: Closure + Associativity
- **Monoid^[모노이드]**: Semigroup + Identity

### 더 강한 구조

- **Ring^[환]**: Group + 곱셈 구조
- **Field^[체]**: Ring + 나눗셈

자세한 내용은 [[Ring]], [[Field]] 참조

### 관련 주제

- [[Quotient Group]]: Normal subgroup으로 나눈 몫
- [[Equivalence Relation and Partitions]]: Coset과 분할

## Torsion의 직관

**Torsion element**: "반복하면 원점으로 돌아오는" 원소

**기하학적 해석**:
- **Torsion**: 원 위의 회전 (유한번 반복하면 원점)
- **Torsion-free**: 직선 위의 이동 (영원히 원점으로 안 돌아옴)

**예시**:
- $\mathbb{Z}/12\mathbb{Z}$: 시계의 숫자들 (12시간 후 원점)
- $\mathbb{Z}$: 수직선 (끝없이 계속)

**이름의 유래**: "Torsion" = 비틀림, 뒤틀림 (topology에서 유래)

**중요성**:
- Finitely generated abelian groups: Free part $\oplus$ Torsion part
- Algebraic topology: Torsion in homology groups
- Number theory: Class groups의 torsion

## Common Pitfall^[흔한 실수]

### 1. 항등원이 여러 개?

✗ 항등원은 항상 유일 (증명 필요)

### 2. Abelian이 아닌데 교환법칙 사용

✗ $ab = ba$는 일반적으로 성립 안 함
- 행렬 곱셈: $AB \neq BA$ in general
- Permutation: $(12)(23) \neq (23)(12)$

### 3. $|ab| = |a||b|$?

✗ 원소의 위수는 곱셈에 대해 일반적으로 곱하지 않음

**반례**: $S_3$에서 $(12)(13) = (132)$
- $|(12)| = 2$, $|(13)| = 2$
- $|(132)| = 3 \neq 2 \times 2$

### 4. Subgroup 판정

✗ $H \subseteq G$이고 닫혀있다고 해서 subgroup이 아님
- 역원 존재도 확인 필요!

**반례**: $\mathbb{N} \subseteq \mathbb{Z}$는 덧셈에 닫혀있지만 역원 없음

