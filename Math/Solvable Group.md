# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Quotient Group]]
- [[Abelian Group]]
- [[Simple Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Rotman, An Introduction to the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Solvable Group^[가해군]

Group $G$가 **solvable**^[가해] (또는 **soluble**^[가용])이다 $\Leftrightarrow$ 다음 중 하나:

### Definition 1: Derived Series^[유도 열]

**Derived series**^[유도 열]가 identity에 도달:

$$G = G^{(0)} \trianglerighteq G^{(1)} \trianglerighteq G^{(2)} \trianglerighteq \cdots \trianglerighteq G^{(n)} = \{e\}$$

where $G^{(i+1)} = [G^{(i)}, G^{(i)}]$ (commutator subgroup)

### Definition 2: Normal Series with Abelian Quotients

Normal series가 존재:

$$\{e\} = G_0 \triangleleft G_1 \triangleleft \cdots \triangleleft G_n = G$$

where each $G_{i+1}/G_i$ is **abelian**

### 동등성

두 정의는 동등함

**핵심 아이디어**: "Repeatedly taking quotients by commutator subgroups eventually gives identity"

## Derived Series^[유도 열]

$$G^{(0)} = G$$
$$G^{(1)} = G' = [G, G]$$
$$G^{(2)} = (G')' = [G', G']$$
$$\vdots$$
$$G^{(n)} = [G^{(n-1)}, G^{(n-1)}]$$

**Commutator**^[교환자]: $[a, b] = aba^{-1}b^{-1}$

**Commutator subgroup**^[교환자 부분군]: $[H, K] = \langle [h, k] : h \in H, k \in K \rangle$

## Derived Length^[유도 길이]

$G$가 solvable일 때, **derived length**^[유도 길이] $d(G)$:

$$d(G) = \min\{n : G^{(n)} = \{e\}\}$$

**예**:
- Abelian group: $d(G) = 1$ (since $G' = \{e\}$)
- Non-abelian but solvable: $d(G) \geq 2$

## Solvability and Composition Series

**Alternative characterization**:

$G$ solvable $\Leftrightarrow$ Composition series의 모든 factors가 cyclic of prime order

즉, 모든 composition factors가 **abelian simple groups**

---

# <span class="header-examples">Examples</span>

## Example 1: Abelian Groups

**정리**: 모든 abelian group은 solvable

**증명**: $G$ abelian $\Rightarrow G' = \{e\}$

Derived series: $G \trianglerighteq \{e\}$ (길이 1) 
자세한 내용은 [[Abelian Group]] 참조

## Example 2: $S_3$

Derived series:
- $S_3^{(0)} = S_3$ (order 6)
- $S_3^{(1)} = A_3 \cong \mathbb{Z}/3\mathbb{Z}$ (order 3, abelian)
- $S_3^{(2)} = \{e\}$

**Derived length**: $d(S_3) = 2$

**Normal series**: $\{e\} \triangleleft A_3 \triangleleft S_3$
- $A_3/\{e\} \cong A_3$ (abelian) - $S_3/A_3 \cong \mathbb{Z}/2\mathbb{Z}$ (abelian) 
**결론**: $S_3$ is solvable

## Example 3: $S_4$

Derived series:
- $S_4^{(0)} = S_4$ (order 24)
- $S_4^{(1)} = A_4$ (order 12)
- $S_4^{(2)} = V_4 = \{e, (12)(34), (13)(24), (14)(23)\}$ (order 4, abelian)
- $S_4^{(3)} = \{e\}$

**Derived length**: $d(S_4) = 3$

**결론**: $S_4$ is solvable

## Example 4: Dihedral Groups $D_n$

**정리**: 모든 dihedral group은 solvable

**증명 sketch**:
- $D_n = \langle r, s : r^n = s^2 = e, srs = r^{-1} \rangle$
- $[D_n, D_n] = \langle r^2 \rangle$ or $\langle r \rangle$ (depending on $n$)
- Eventually reaches identity

**Derived length**: $d(D_n) = 2$ or $3$ (depending on $n$)

자세한 내용은 [[Dihedral Group]] 참조

## Example 5: Non-example: $A_n$ ($n \geq 5$)

**정리**: $A_n$ is **NOT solvable** for $n \geq 5$

**이유**: $A_n$ is simple and non-abelian

Derived series:
- $A_n^{(0)} = A_n$
- $A_n^{(1)} = A_n$ (since $A_n$ is perfect: $A_n = [A_n, A_n]$)
- Never reaches identity!

**결론**: $A_n$ ($n \geq 5$) not solvable

자세한 내용은 [[Simple Group]] 참조

## Example 6: Non-example: $S_n$ ($n \geq 5$)

**정리**: $S_n$ is **NOT solvable** for $n \geq 5$

**증명**: $S_n' = A_n$ (for $n \geq 5$)

$A_n$ is simple and non-abelian $\Rightarrow A_n' = A_n$

Derived series gets stuck at $A_n$ ✗

**Small cases**:
- $S_1, S_2$ trivial/abelian (solvable)
- $S_3, S_4$ solvable (shown above)
- $S_n$ ($n \geq 5$) NOT solvable

## Example 7: Nilpotent Groups

**정리**: 모든 nilpotent group은 solvable

Nilpotent $\Rightarrow$ Solvable (but not conversely)

**예**: $p$-groups는 nilpotent $\Rightarrow$ solvable

자세한 내용은 [[Nilpotent Group]] 참조

## Example 8: Upper Triangular Matrices

$$B_n(\mathbb{F}) = \left\{ \begin{pmatrix}
* & * & \cdots & * \\
0 & * & \cdots & * \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & *
\end{pmatrix} : * \in \mathbb{F}^\times \right\}$$

**정리**: $B_n(\mathbb{F})$ is solvable

**Normal series**: Diagonal $\subseteq$ Upper triangular

각 quotient는 abelian 
---

# <span class="header-properties">Properties</span>

## Closure Properties^[닫힘 성질]

### 1. Subgroups

$G$ solvable, $H \leq G \Rightarrow H$ solvable

**증명**: $H^{(i)} \subseteq G^{(i)}$ for all $i$ 
### 2. Quotients

$G$ solvable, $N \triangleleft G \Rightarrow G/N$ solvable

**증명**: $(G/N)^{(i)} = G^{(i)}N/N$ 
### 3. Extensions

$N \triangleleft G$일 때:

$$N \text{ and } G/N \text{ solvable} \Rightarrow G \text{ solvable}$$

**증명**: Normal series를 연결

**역은 자동** (by properties 1 and 2)

### 4. Direct Products

$$G, H \text{ solvable} \Rightarrow G \times H \text{ solvable}$$

**증명**: $(G \times H)^{(i)} = G^{(i)} \times H^{(i)}$ 
**Derived length**: $d(G \times H) = \max(d(G), d(H))$

## Commutator Subgroup Properties

### Basic Properties

1. $[G, G] \triangleleft G$ (always normal)
2. $G/[G, G]$ is abelian (largest abelian quotient)
3. $[G, G] = \{e\} \Leftrightarrow G$ abelian

### Functoriality

$\phi: G \to H$ homomorphism

$$\phi([G, G]) \subseteq [H, H]$$

**응용**: Derived series는 functorial

## Perfect Group^[완전군]

$G$가 **perfect**^[완전]이다 $\Leftrightarrow G = [G, G]$

**성질**:
- Perfect group은 non-solvable (unless trivial)
- $A_n$ ($n \geq 5$)는 perfect

**예**:
- $A_n$ ($n \geq 5$)
- $\text{SL}_n(\mathbb{R})$ ($n \geq 2$)

## Solvable $\not\Rightarrow$ Nilpotent

**정리**: Solvable ⊃ Nilpotent (proper inclusion)

**예**: $S_3$ is solvable but NOT nilpotent

**이유**: $Z(S_3) = \{e\}$, so upper central series = $\{e\}$

자세한 내용은 [[Nilpotent Group]] 참조

## Hall Subgroups

$G$ finite solvable group

**정리** (Hall): $\pi$-Hall subgroups exist and conjugate

$\pi$-Hall subgroup: $|H| = \prod_{p \in \pi} p^{a_p}$

**응용**: Sylow theorems의 일반화

---

# <span class="header-theorem">Theorem</span>

## Feit-Thompson Theorem (Odd Order Theorem)

**정리**: Odd order group은 solvable

$$|G| \text{ odd} \Rightarrow G \text{ solvable}$$

**증명**: 255 페이지 (1963)

**따름정리**: Non-abelian simple groups는 모두 even order

**중요성**: Classification of finite simple groups의 핵심

자세한 내용은 [[Simple Group]] 참조

## Burnside's $p^a q^b$ Theorem

**정리**: $|G| = p^a q^b$ (두 소수의 거듭제곱곱) $\Rightarrow G$ solvable

**증명**: Character theory 사용

**예**:
- $|G| = 12 = 2^2 \cdot 3$ $\Rightarrow$ solvable
- $|G| = 60 = 2^2 \cdot 3 \cdot 5$? No! ($A_5$ not solvable)

## Solvable = Composition Factors Abelian

**정리**: $G$ solvable $\Leftrightarrow$ 모든 composition factors가 cyclic of prime order

**증명**:
- ($\Rightarrow$): Normal series with abelian quotients $\Rightarrow$ refine to composition series $\Rightarrow$ simple abelian factors
- ($\Leftarrow$): Composition factors abelian $\Rightarrow$ series with abelian quotients 
**Jordan-Hölder**: Composition factors 유일 (up to order and isomorphism)

## Galois Theory Connection

**정리** (Abel-Ruffini): 5차 이상 방정식은 근의 공식 없음

**Group theory version**: Galois group이 solvable $\Leftrightarrow$ 방정식이 radicals로 풀림

**핵심**:
- $S_n$ ($n \geq 5$) not solvable
- General degree $n$ equation ($n \geq 5$)의 Galois group = $S_n$
- 따라서 근의 공식 불가능

자세한 내용은 [[Galois Theory]] 참조

## Derived Series vs Upper Central Series

**Derived series** (from top):
$$G \trianglerighteq G' \trianglerighteq G'' \trianglerighteq \cdots$$

**Upper central series** (from bottom):
$$\{e\} \trianglelefteq Z_1(G) \trianglelefteq Z_2(G) \trianglelefteq \cdots$$

**비교**:
- Nilpotent: Upper central series reaches $G$
- Solvable: Derived series reaches $\{e\}$

**관계**: Nilpotent $\Rightarrow$ Solvable

## Schreier Refinement and Solvability

두 normal series는 common refinement를 가짐

**응용**: Solvability는 어떤 normal series를 선택하든 동일

## Derived Length Bounds

$G$ finite solvable group of order $n$

**정리** (Fitting): 
$$d(G) \leq \log_2(\log_2 n) + \text{constant}$$

**매우 느린 성장**: 대부분의 solvable groups는 작은 derived length

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Solvable = "충분히 abelian에 가까움"**

### 메타포: 퍼즐 풀기

**Composition series**: Group을 simple pieces로 분해

**Solvable**: 모든 pieces가 "easy" (abelian simple = prime cyclic)

**Non-solvable**: 어떤 pieces가 "hard" (non-abelian simple)

### 메타포: 계층 구조

$$\text{Abelian} \subset \text{Nilpotent} \subset \text{Solvable} \subset \text{All groups}$$

각 단계에서 "약간 더 복잡"해짐

## 왜 "Solvable"인가?

**이름의 유래**: "Solvability by radicals"

**Galois theory**: 
- 방정식이 radicals로 풀림 $\Leftrightarrow$ Galois group solvable
- 5차 방정식: $S_5$ not solvable $\Rightarrow$ no formula

**역사적**: 대수방정식의 "해결 가능성"에서 유래

## Solvable vs Non-Solvable

| | **Solvable** | **Non-Solvable** |
|---|---|---|
| **Composition factors** | All abelian (prime cyclic) | Some non-abelian simple |
| **Derived series** | Reaches identity | Gets stuck |
| **예 (small)** | $S_3, S_4, D_n$ | $A_5, S_5$ |
| **예 (large)** | $p$-groups, nilpotent | $A_n$ ($n \geq 5$), most simple |
| **Galois** | Solvable by radicals | No general formula |

## 경계선: $n = 5$

**Small symmetric groups**:
- $S_1, S_2$: Trivial/abelian (solvable)
- $S_3, S_4$: Solvable

**Large symmetric groups**:
- $S_n$ ($n \geq 5$): Not solvable

**이유**: $A_5$가 simple non-abelian (smallest such group)

## Practical Tests for Solvability

### 1. Compute Derived Series

반복적으로 commutator subgroup 계산

$G^{(n)} = \{e\}$에 도달? → Solvable

### 2. Check Order

- Odd order → Solvable (Feit-Thompson)
- $p^a q^b$ → Solvable (Burnside)

### 3. Known Families

- Abelian → Solvable
- Nilpotent → Solvable
- $S_n, A_n$ ($n \geq 5$) → Not solvable

### 4. Composition Factors

Simple factors all abelian? → Solvable

## 응용

**Galois Theory**:
- Solvability by radicals
- 방정식의 대칭성

자세한 내용은 [[Galois Theory]] 참조

**Group Theory**:
- Structure theory
- Hall subgroups
- Transfer theorems

**Number Theory**:
- Class field theory
- Local-global principles

**Topology**:
- Fundamental groups
- 3-manifolds

## 역사적 배경

**1824**: Abel - 5차 방정식 불가능 증명

**1830s**: Galois - Galois theory, solvability 개념

**1963**: Feit-Thompson - Odd order theorem

**1980s**: CFSG - Simple groups 분류 완성

## 표기법

| 표기 | 의미 |
|------|------|
| $G'$ or $[G,G]$ | Commutator subgroup |
| $G^{(n)}$ | $n$-th derived subgroup |
| $d(G)$ | Derived length |
| $[a,b]$ | Commutator $aba^{-1}b^{-1}$ |

## Common Pitfall^[흔한 실수]

### 1. Solvable ≠ "Has solution"

"Solvable"은 group 이론 용어 (특정 성질)

방정식의 "해가 존재"와는 다름!

### 2. Derived length는 composition length가 아님

Derived length ≤ Composition length (일반적으로)

### 3. Subgroup of solvable is solvable

 True

But: Quotient of non-solvable might be solvable

### 4. $G/N, N$ solvable $\Rightarrow G$ solvable

 True! (Extension property)

Powerful tool for proving solvability

## 관련 개념

- [[Abelian Group]]: Simplest solvable groups
- [[Nilpotent Group]]: Stronger than solvable
- [[Simple Group]]: Obstructions to solvability
- [[Galois Theory]]: Original motivation
- [[Composition Series]]: Structure analysis

## 추가 학습 주제

**기초**:
- Derived series
- Commutator subgroups
- $S_3, S_4$ examples

**중급**:
- Feit-Thompson theorem (statement)
- Burnside's $p^a q^b$ theorem
- Hall subgroups

**고급**:
- Schreier refinement theorem
- Carter subgroups
- Formation theory

