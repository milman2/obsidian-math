# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Commutator]]
- [[Abelian Group]]
- [[Solvable Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Commutator Subgroup^[교환자 부분군]

**정의**: Group $G$의 commutators로 generate된 subgroup

$$G' = [G, G] = \langle [a, b] : a, b \in G \rangle$$

where $[a, b] = aba^{-1}b^{-1}$

**Alternative names**: 
- Derived subgroup^[유도 부분군]
- Commutator group

### Generated vs Consisting

**주의**: $G'$는 모든 commutators의 **products**로 이루어짐

$$G' = \{\text{finite products of commutators}\}$$

**Not**: $G' = \{[a,b] : a, b \in G\}$ (일반적으로)

자세한 내용은 [[Commutator]] 참조

## Derived Series^[유도 열]

$$G^{(0)} = G$$
$$G^{(1)} = G' = [G, G]$$
$$G^{(2)} = G'' = [G', G']$$
$$\vdots$$
$$G^{(n)} = [G^{(n-1)}, G^{(n-1)}]$$

**응용**: Solvable groups

자세한 내용은 [[Solvable Group]] 참조

---

# <span class="header-properties">Properties</span>

## Normal Subgroup

**정리**: $G' \triangleleft G$ (항상 normal)

**증명**: $g[a,b]g^{-1} = [gag^{-1}, gbg^{-1}] \in G'$

모든 commutator의 conjugate도 commutator

따라서 $gG'g^{-1} = G'$ 
자세한 내용은 [[Normal Subgroup]] 참조

## Abelianization^[아벨화]

$$G^{\text{ab}} = G/G'$$

**정리**: $G/G'$는 abelian

**증명**: $(aG')(bG') = abG' = baG' = (bG')(aG')$

(since $a^{-1}b^{-1}ab \in G'$) 
**의미**: $G$의 "가장 큰" abelian quotient

자세한 내용은 [[Abelian Group]] 참조

## Universal Property

**정리**: $\phi: G \to A$ (to abelian group)

$$\Rightarrow \phi \text{ factors through } G/G'$$

**Diagram**:
```
G --φ--> A
 \      ↗
  π   φ̄
   ↓ ↗
  G/G'
```

**증명**: $G' \subseteq \ker(\phi)$ (commutators map to identity in abelian group) 
## Characteristic Subgroup

**정리**: $G' \text{ char } G$ (characteristic)

**증명**: $\phi \in \text{Aut}(G)$

$$\phi([a,b]) = [\phi(a), \phi(b)] \in G'$$

따라서 $\phi(G') = G'$ 
**더 강함**: Normal보다 characteristic이 stronger

## Solvability

**정리**: $G$ solvable $\Leftrightarrow$ derived series reaches identity

$$G^{(n)} = \{e\} \text{ for some } n$$

자세한 내용은 [[Solvable Group]] 참조

---

# <span class="header-examples">Examples</span>

## Example 1: Abelian Groups

$G$ abelian $\Rightarrow G' = \{e\}$

**증명**: $[a,b] = aba^{-1}b^{-1} = abb^{-1}a^{-1} = e$ 
**역**: $G' = \{e\} \Rightarrow G$ abelian 
## Example 2: $S_3$

$$S_3' = A_3 = \{e, (123), (132)\}$$

**증명**: 
- $S_3$ non-abelian $\Rightarrow S_3' \neq \{e\}$
- $S_3/A_3 \cong \mathbb{Z}/2\mathbb{Z}$ (abelian)
- $A_3$ smallest normal subgroup with abelian quotient
- Therefore $S_3' = A_3$ 
**확인**: $[(12), (13)] = (123) \in A_3$

자세한 내용은 [[Symmetric Group]] 참조

## Example 3: $S_n$ ($n \geq 3$)

$$S_n' = A_n$$

**증명**: Similar to $S_3$ case

$S_n/A_n \cong \mathbb{Z}/2\mathbb{Z}$ (abelian)

$A_n$ is smallest normal with abelian quotient 
자세한 내용은 [[Alternating Group]] 참조

## Example 4: Dihedral Group $D_n$

### $n$ odd

$$D_n' = \langle r \rangle$$

Rotation subgroup

### $n$ even

$$D_n' = \langle r^2 \rangle$$

Subgroup of order $n/2$

자세한 내용은 [[Dihedral Group]] 참조

## Example 5: $A_n$ ($n \geq 5$)

$$A_n' = A_n$$

**증명**: $A_n$ is perfect (simple)

$A_n = [A_n, A_n]$ 
**의미**: Cannot make more abelian by taking quotient

자세한 내용은 [[Simple Group]] 참조

## Example 6: Heisenberg Group $H_3$

$$H_3' = Z(H_3)$$

Commutator subgroup = Center

**Order**: $|H_3'| = $ dimension of center

---

# <span class="header-theorem">Theorem</span>

## Abelianization is Abelian

**정리**: $G/G'$ is abelian

Moreover, it's the **largest** abelian quotient

**증명**: Any homomorphism $G \to A$ (abelian) factors through $G/G'$

## Perfect Group^[완전군]

$G$가 **perfect**^[완전]이다 $\Leftrightarrow G = G'$

**예**:
- $A_n$ ($n \geq 5$)
- $\text{SL}_n(\mathbb{R})$ ($n \geq 2$)

**성질**: Perfect groups are not solvable (unless trivial)

## Derived Length^[유도 길이]

$G$ solvable일 때:

$$d(G) = \min\{n : G^{(n)} = \{e\}\}$$

**예**:
- Abelian: $d(G) = 1$
- $S_3$: $d(S_3) = 2$
- $S_4$: $d(S_4) = 3$

자세한 내용은 [[Solvable Group]] 참조

## Relationship with Center

**일반적으로**: $G' \cap Z(G)$ arbitrary

**$p$-groups**: Structure theorems relate $G'$ and $Z(G)$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Commutator Subgroup = "비가환성의 측정"**

### 메타포: 오차 부분

**$G'$**: 모든 "교환 오차"들로 generate

**$G/G'$**: 오차 제거 = 완전히 abelian

**Quotient**: "가환화"

### 메타포: 잡음 제거

**$G$**: 원본 (잡음 포함)

**$G'$**: 잡음

**$G/G'$**: 잡음 제거 (깨끗한 신호 = abelian)

## 왜 중요한가?

### 1. Abelianization

$G$를 abelian으로 만드는 가장 효율적인 방법

### 2. Solvability

Derived series로 solvability 판정

### 3. Homology

$H_1(G) \cong G/G'$ (First homology group)

### 4. Classification

$G'$의 구조는 중요한 invariant

## 계산 방법

**Step 1**: Commutators $[a,b]$ 찾기

**Step 2**: 이들의 products generate

**Step 3**: Resulting subgroup = $G'$

**또는**: Abelian quotient 찾기 (indirect)

## $G' = \{e\}$ 판정

$$G' = \{e\} \Leftrightarrow G \text{ abelian}$$

**테스트**: 모든 원소 쌍이 교환하는지 확인

## Derived Series vs Lower Central Series

**Derived**: $G^{(i)} = [G^{(i-1)}, G^{(i-1)}]$

**Lower Central**: $G_i = [G, G_{i-1}]$

**관계**: $G^{(i)} \subseteq G_i$ (derived faster)

자세한 내용은 [[Nilpotent Group]] 참조

## 응용 분야

**Algebraic Topology**:
- Homology groups
- Fundamental group abelianization

**Algebraic K-theory**:
- $K_1$ and abelianization

**Number Theory**:
- Class field theory
- Abelian extensions

**Galois Theory**:
- Solvability by radicals

자세한 내용은 [[Galois Theory]] 참조

## 표기법

| 표기 | 의미 |
|------|------|
| $G'$ or $[G,G]$ | Commutator subgroup |
| $G^{(n)}$ | $n$-th derived subgroup |
| $G^{\text{ab}}$ | Abelianization $G/G'$ |
| $d(G)$ | Derived length |

## Common Pitfall^[흔한 실수]

### 1. $G' \neq \{[a,b] : a,b \in G\}$

$G'$ = **products** of commutators (not just commutators)

### 2. Always normal

$G' \triangleleft G$ (항상!)

Actually char $G$ (더 강함)

### 3. $G' = \{e\}$ means?

$\Leftrightarrow G$ abelian (if and only if!)

### 4. Perfect vs Simple

Perfect ($G = G'$) ≠ Simple

$A_5$ is both, but $\text{SL}_2(\mathbb{R})$ perfect but not simple

### 5. Abelianization size

$|G/G'|$ can be large even if $|G'|$ large

## 관련 개념

- [[Commutator]]: Basic element
- [[Abelian Group]]: $G' = \{e\}$ case
- [[Solvable Group]]: Derived series
- [[Normal Subgroup]]: $G'$ always normal
- [[Simple Group]]: Perfect simple groups

## 추가 학습 주제

**기초**:
- Definition
- Abelianization
- Examples

**중급**:
- Derived series
- Universal property
- Solvability

**고급**:
- Homological algebra
- Schur multiplier
- Central extensions

