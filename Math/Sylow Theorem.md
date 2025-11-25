# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Coset]]
- [[Lagrange's theorem]]
- [[Group Action]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Rotman, An Introduction to the Theory of Groups

---

# <span class="header-definition">Definition</span>

## $p$-group^[$p$-군]

Group $G$가 **$p$-group**^[$p$-군]이다 $\Leftrightarrow$

$$|G| = p^n \text{ for some prime } p \text{ and } n \geq 0$$

**의미**: Order가 prime의 거듭제곱

**성질**: 모든 $p$-group은 nilpotent^[멱영]

자세한 내용은 [[Nilpotent Group]] 참조

## Sylow $p$-subgroup^[실로우 $p$-부분군]

Finite group $G$, $|G| = p^k m$ where $\gcd(p, m) = 1$

Subgroup $P \leq G$가 **Sylow $p$-subgroup**^[실로우 $p$-부분군]이다 $\Leftrightarrow$

$$|P| = p^k$$

**의미**: Maximal $p$-subgroup (가능한 가장 큰 $p$-power order)

**표기**: $\text{Syl}_p(G)$ = 모든 Sylow $p$-subgroups의 집합

## $p$-power Order Subgroups

$|H| = p^i$ for some $i \leq k$인 subgroup

**Sylow $p$-subgroup**: $i = k$ (maximal)

---

# <span class="header-theorem">Theorem</span>

## Sylow's First Theorem^[실로우 제1정리]

**정리**: $|G| = p^k m$ where $\gcd(p, m) = 1$

$$\Rightarrow \exists P \leq G \text{ with } |P| = p^k$$

**의미**: Prime power divisor → 해당 order의 subgroup 존재

**Lagrange's theorem의 부분적 역**!

### 일반화

$$p^i \mid |G| \Rightarrow \exists H \leq G \text{ with } |H| = p^i$$

for $0 \leq i \leq k$

### 증명 (Sketch)

Group action on cosets 사용

$G$ acts on $X = \{S : S \subseteq G, |S| = p^k\}$ by left multiplication

Counting + Orbit-stabilizer theorem

자세한 내용은 [[Group Action]] 참조

## Sylow's Second Theorem^[실로우 제2정리]

**정리**: 모든 Sylow $p$-subgroups는 conjugate

$$P_1, P_2 \in \text{Syl}_p(G) \Rightarrow \exists g \in G : P_2 = gP_1g^{-1}$$

**의미**: Sylow $p$-subgroups는 "본질적으로 같다"

### 따름정리

1. **Uniqueness $\Leftrightarrow$ Normality**:

$$|\text{Syl}_p(G)| = 1 \Leftrightarrow P \triangleleft G$$

2. **모든 maximal $p$-subgroups는 Sylow**

$H$ maximal $p$-subgroup $\Rightarrow H \in \text{Syl}_p(G)$

## Sylow's Third Theorem^[실로우 제3정리]

**정리**: $n_p = |\text{Syl}_p(G)|$ (Sylow $p$-subgroups의 개수)

$$n_p \equiv 1 \pmod{p}$$

$$n_p \mid m \quad \text{where } |G| = p^k m, \gcd(p,m) = 1$$

**의미**: $n_p$에 대한 강력한 제약 조건

### 따름정리

$$n_p \in \{1, 1+p, 1+2p, 1+3p, \ldots\} \cap \{\text{divisors of } m\}$$

**응용**: Group의 가능한 구조 제한

---

# <span class="header-examples">Examples</span>

## Example 1: $S_3$ (Order 6)

$|S_3| = 6 = 2 \cdot 3$

### Sylow 2-subgroups

$|P| = 2$

**Subgroups**: $\langle (12) \rangle, \langle (13) \rangle, \langle (23) \rangle$

**Count**: $n_2 = 3$

**Check**:
- $n_2 \equiv 1 \pmod{2}$? $3 \equiv 1 \pmod{2}$ ✓
- $n_2 \mid 3$? $3 \mid 3$ ✓

### Sylow 3-subgroups

$|P| = 3$

**Subgroup**: $A_3 = \{e, (123), (132)\}$

**Count**: $n_3 = 1$

**Check**:
- $n_3 \equiv 1 \pmod{3}$? $1 \equiv 1 \pmod{3}$ ✓
- $n_3 \mid 2$? $1 \mid 2$ ✓

**결론**: $A_3 \triangleleft S_3$ (유일하므로 normal)

자세한 내용은 [[Symmetric Group]] 참조

## Example 2: Group of Order 12

$|G| = 12 = 2^2 \cdot 3$

### Sylow 2-subgroups

$|P| = 4$

**$n_2$ 가능성**:
- $n_2 \equiv 1 \pmod{2}$: odd
- $n_2 \mid 3$: $n_2 \in \{1, 3\}$

**따라서**: $n_2 \in \{1, 3\}$

### Sylow 3-subgroups

$|P| = 3$

**$n_3$ 가능성**:
- $n_3 \equiv 1 \pmod{3}$: $n_3 \in \{1, 4, 7, \ldots\}$
- $n_3 \mid 4$: $n_3 \in \{1, 2, 4\}$

**따라서**: $n_3 \in \{1, 4\}$

### 가능한 경우들

1. $n_2 = 1, n_3 = 1$: 둘 다 normal → $G \cong \mathbb{Z}/4\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z} \cong \mathbb{Z}/12\mathbb{Z}$
2. $n_2 = 1, n_3 = 4$: 하나만 normal → 특정 구조
3. $n_2 = 3, n_3 = 1$: 하나만 normal (예: $A_4$)
4. $n_2 = 3, n_3 = 4$: 둘 다 non-normal

**실제 groups**: $\mathbb{Z}/12\mathbb{Z}, A_4, D_6, Q_{12}$, etc.

## Example 3: Group of Order 15

$|G| = 15 = 3 \cdot 5$

### Sylow 3-subgroups

$n_3 \equiv 1 \pmod{3}$, $n_3 \mid 5$

$\Rightarrow n_3 \in \{1\}$ (only 1!)

### Sylow 5-subgroups

$n_5 \equiv 1 \pmod{5}$, $n_5 \mid 3$

$\Rightarrow n_5 \in \{1\}$ (only 1!)

**결론**: 둘 다 normal subgroups

$$G \cong \mathbb{Z}/3\mathbb{Z} \times \mathbb{Z}/5\mathbb{Z} \cong \mathbb{Z}/15\mathbb{Z}$$

**따라서**: Order 15인 group은 cyclic (up to isomorphism) ✓

## Example 4: $A_5$ (Order 60)

$|A_5| = 60 = 2^2 \cdot 3 \cdot 5$

### Sylow 5-subgroups

$n_5 \equiv 1 \pmod{5}$, $n_5 \mid 12$

$\Rightarrow n_5 \in \{1, 6\}$

**실제**: $n_5 = 6$ (각각 order 5)

### Simplicity

$n_5 = 6 > 1$ $\Rightarrow$ no normal Sylow 5-subgroup

Similar for $p = 2, 3$

**결론**: $A_5$ is simple (모든 Sylow subgroups non-normal)

자세한 내용은 [[Simple Group]] 참조

## Example 5: $p$-groups

$|G| = p^n$

**Sylow $p$-subgroup**: $G$ 자체!

$n_p = 1$ $\Rightarrow$ $G \triangleleft G$ (trivial)

**성질**: $Z(G) \neq \{e\}$ (non-trivial center)

자세한 내용은 [[Nilpotent Group]] 참조

---

# <span class="header-properties">Properties</span>

## Conjugacy of Sylow Subgroups

**정리**: $P \in \text{Syl}_p(G)$, $Q$ any $p$-subgroup

$$Q \subseteq N_G(P) \text{ or } \exists g : Q \subseteq gPg^{-1}$$

**의미**: 모든 $p$-subgroups는 어떤 Sylow $p$-subgroup에 포함

## Normalizer

$P \in \text{Syl}_p(G)$에 대해:

$$N_G(P) = \{g \in G : gPg^{-1} = P\}$$

**성질**: $P \triangleleft N_G(P)$ (항상)

**Count formula**:

$$n_p = [G : N_G(P)]$$

**증명**: $G$ acts on $\text{Syl}_p(G)$ by conjugation, $P$의 stabilizer = $N_G(P)$

자세한 내용은 [[Group Action]] 참조

## Frattini Argument

$N \triangleleft G$, $P \in \text{Syl}_p(N)$

$$G = N_G(P) \cdot N$$

**증명**: Conjugation action 사용

**응용**: Simplicity proofs, Structure theorems

## Embedding in Normalizer

**정리**: $H$ $p$-subgroup, $P \in \text{Syl}_p(N_G(H))$

$$\Rightarrow P \in \text{Syl}_p(G)$$

## Partial Converse to Lagrange

**Lagrange**: $|H| \mid |G|$ (항상)

**역**: $d \mid |G| \Rightarrow \exists H$ with $|H| = d$? (일반적으로 거짓)

**Sylow**: $p^k \mid |G| \Rightarrow \exists H$ with $|H| = p^k$ ✓

**제한**: Prime powers에만 성립!

자세한 내용은 [[Lagrange's theorem]] 참조

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Sylow Theorems = "Prime power subgroups의 완전한 특성화"**

### 메타포: 소인수분해

**Group order**: $|G| = p_1^{k_1} \cdots p_r^{k_r}$

**Sylow subgroups**: 각 $p_i^{k_i}$에 대응하는 subgroup

**구조**: Prime power pieces로 분해

### 메타포: 원자 구조

**Sylow $p$-subgroups**: "$p$-원자들"

**Conjugacy**: 모든 $p$-원자는 같은 "종류"

**Count**: 몇 개의 $p$-원자가 있나?

## 왜 중요한가?

### 1. Classification of Finite Groups

**Small order groups 분류**

Sylow theorems로 가능한 구조 제한

**예**: Order $pq$ ($p < q$ primes)
- If $q \not\equiv 1 \pmod{p}$: cyclic
- Otherwise: cyclic or non-abelian

### 2. Simplicity Testing

**Simple groups 판정**

$n_p = 1$ for some $p$ $\Rightarrow$ Not simple (normal Sylow subgroup)

**예**: $A_5$ simple (모든 $n_p > 1$)

### 3. Partial Converse to Lagrange

**Lagrange의 한계 극복**

Prime powers에 대해서는 역이 성립!

### 4. Structure Theorems

**Finite groups의 구조 분석**

Composition series, Solvability 등

자세한 내용은 [[Solvable Group]] 참조

## Sylow Theorems 요약

| | **Statement** | **의미** |
|---|---|---|
| **First** | $p^k \mid \|G\| \Rightarrow \exists H$ with $\|H\| = p^k$ | 존재성 |
| **Second** | 모든 Sylow $p$-subgroups conjugate | 유일성 (up to conjugacy) |
| **Third** | $n_p \equiv 1 \pmod{p}$, $n_p \mid m$ | 개수 제약 |

## 계산 전략

**Group order 분석**:

1. **Factor**: $|G| = p_1^{k_1} \cdots p_r^{k_r}$
2. **각 prime $p_i$에 대해**:
   - $n_{p_i}$의 가능한 값 계산
   - Sylow theorems로 제약
3. **Normal subgroups 찾기**:
   - $n_p = 1$ $\Rightarrow$ Normal
4. **구조 추론**:
   - Normal subgroups로 quotient/extensions

## 증명 기법

### Group Actions 사용

**핵심**: Conjugation action on Sylow subgroups

$$G \text{ acts on } \text{Syl}_p(G) \text{ by } g \cdot P = gPg^{-1}$$

**Orbit-stabilizer**: $n_p = [G : N_G(P)]$

### Counting Arguments

**Class equation 변형**

**Fixed points**: Burnside's lemma

### Induction

**Smaller groups로 귀납**

Normalizers, Quotients 사용

## 응용 예시

### Order 30 Groups

$|G| = 30 = 2 \cdot 3 \cdot 5$

**Sylow 5-subgroups**:
- $n_5 \equiv 1 \pmod{5}$, $n_5 \mid 6$
- $\Rightarrow n_5 = 1$ or $6$

**If $n_5 = 1$**: $P_5 \triangleleft G$ (normal)

**Sylow 3-subgroups**:
- $n_3 \equiv 1 \pmod{3}$, $n_3 \mid 10$
- $\Rightarrow n_3 \in \{1, 10\}$

**Analysis**: 
- Both normal $\Rightarrow$ abelian (likely cyclic or $\mathbb{Z}/15\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$)
- One normal $\Rightarrow$ semidirect product

### Non-simplicity Proofs

**정리**: $|G| = p^a q^b$ ($p, q$ distinct primes) $\Rightarrow$ $G$ not simple

**증명**: At least one $n_p = 1$ (by counting)

자세한 내용은 [[Simple Group]] 참조

## 역사적 배경

**Ludwig Sylow** (1832-1918):
- 노르웨이 수학자
- 1872: Sylow theorems 발표
- Galois theory 연구

**이전**:
- Lagrange (1770s): Order divides
- Cauchy (1845): Prime divisor → element of that order

**이후**:
- Classification of finite simple groups
- Burnside, Hall theorems (일반화)

## Hall's Theorem (일반화)

**Solvable groups에서**:

$|G| = mn$, $\gcd(m,n) = 1$

$\Rightarrow \exists H \leq G$ with $|H| = m$ (Hall subgroup)

**Sylow = Hall theorem for $m = p^k$**

자세한 내용은 [[Solvable Group]] 참조

## 표기법

| 표기 | 의미 |
|------|------|
| $\text{Syl}_p(G)$ | Sylow $p$-subgroups의 집합 |
| $n_p$ | $\|\text{Syl}_p(G)\|$ |
| $N_G(P)$ | Normalizer of $P$ |
| $p^k \mid\mid \|G\|$ | $p^k \mid \|G\|$ but $p^{k+1} \nmid \|G\|$ |

## Common Pitfall^[흔한 실수]

### 1. 역은 성립 안 함

$d \mid |G|$ $\not\Rightarrow$ $\exists H$ with $|H| = d$ (일반적으로)

**Sylow**: Prime powers만!

### 2. $n_p$ 계산

$n_p \equiv 1 \pmod{p}$ **AND** $n_p \mid m$ (둘 다!)

교집합 취해야 함

### 3. Normality

$n_p = 1$ $\Leftrightarrow$ $P \triangleleft G$

$n_p > 1$ $\Rightarrow$ Not normal (하지만 일부는 normal일 수 있음)

### 4. Maximal vs Sylow

Sylow = **maximal $p$-subgroup** (order로)

Not maximal subgroup (일반적으로)

### 5. Conjugacy

"Conjugate" = $gPg^{-1}$ ($g \in G$로)

Isomorphic와 다름!

## 관련 정리들

**Cauchy's Theorem**: $p \mid |G| \Rightarrow$ order $p$ element

**Lagrange's Theorem**: $|H| \mid |G|$

**Burnside's $p^a q^b$ Theorem**: Not simple

모두 연결되어 있음!

## 관련 개념

- [[Subgroup]]: Sylow subgroups는 특별한 subgroups
- [[Normal Subgroup]]: $n_p = 1$ case
- [[Group Action]]: 증명에 필수적
- [[Lagrange's theorem]]: Sylow는 부분적 역
- [[Simple Group]]: Simplicity testing
- [[Nilpotent Group]]: $p$-groups

## 추가 학습 주제

**기초**:
- $p$-groups
- Sylow theorems statements
- Small order groups

**중급**:
- Sylow theorems 증명
- Normalizers
- Classification applications

**고급**:
- Hall's theorem
- Transfer theory
- Burnside's theorems

