# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Subgroup]]
- [[Normal Subgroup]]
- [[Quotient Group]]
- [[Abelian Group]]
- [[Solvable Group]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Rotman, An Introduction to the Theory of Groups
- Robinson, A Course in the Theory of Groups

---

# <span class="header-definition">Definition</span>

## Nilpotent Group^[멱영군]

Group $G$가 **nilpotent**^[멱영]이다 $\Leftrightarrow$ 다음 중 하나:

### Definition 1: Upper Central Series^[상중심 열]

**Upper central series**^[상중심 열]가 $G$에 도달:

$$\{e\} = Z_0(G) \triangleleft Z_1(G) \triangleleft \cdots \triangleleft Z_n(G) = G$$

where $Z_{i+1}(G)/Z_i(G) = Z(G/Z_i(G))$ (center of quotient)

### Definition 2: Lower Central Series^[하중심 열]

**Lower central series**^[하중심 열]가 identity에 도달:

$$G = G_0 \trianglerighteq G_1 \trianglerighteq \cdots \trianglerighteq G_n = \{e\}$$

where $G_{i+1} = [G, G_i]$

### 동등성

두 정의는 동등함

**핵심 아이디어**: "Center가 충분히 크거나, commutators가 충분히 빨리 소멸"

## Upper Central Series^[상중심 열]

**Center**^[중심]: 
$$Z(G) = Z_1(G) = \{z \in G : zg = gz \; \forall g \in G\}$$

**재귀적 정의**:
$$Z_0(G) = \{e\}$$
$$Z_{i+1}(G)/Z_i(G) = Z(G/Z_i(G))$$

**직관**: "$i$-번째로 중심적인 원소들"

## Lower Central Series^[하중심 열]

$$G_0 = G$$
$$G_1 = [G, G] = G'$$
$$G_2 = [G, G_1]$$
$$\vdots$$
$$G_{i+1} = [G, G_i]$$

**Commutator**: $[G, H] = \langle [g, h] = ghg^{-1}h^{-1} : g \in G, h \in H \rangle$

**직관**: "점점 더 비가환적인 부분"

## Nilpotency Class^[멱영류]

$G$가 nilpotent일 때, **nilpotency class**^[멱영류] $c(G)$:

$$c(G) = \min\{n : Z_n(G) = G\} = \min\{n : G_n = \{e\}\}$$

**예**:
- Abelian group: $c(G) = 1$ (since $Z_1(G) = Z(G) = G$)
- Non-abelian nilpotent: $c(G) \geq 2$

## Nilpotent vs Solvable

$$\text{Abelian} \subset \text{Nilpotent} \subset \text{Solvable} \subset \text{All groups}$$

**Nilpotent $\Rightarrow$ Solvable** (but not conversely)

**차이점**:
- Nilpotent: Upper central series (center 기반)
- Solvable: Derived series (commutator 기반)

---

# <span class="header-examples">Examples</span>

## Example 1: Abelian Groups

**정리**: 모든 abelian group은 nilpotent (class 1)

**증명**: $G$ abelian $\Rightarrow Z(G) = G$

Upper central series: $\{e\} \triangleleft G$ (길이 1) 
**Nilpotency class**: $c(G) = 1$

자세한 내용은 [[Abelian Group]] 참조

## Example 2: Heisenberg Group

$$H_3(\mathbb{R}) = \left\{ \begin{pmatrix}
1 & a & c \\
0 & 1 & b \\
0 & 0 & 1
\end{pmatrix} : a,b,c \in \mathbb{R} \right\}$$

**Center**:
$$Z(H_3) = \left\{ \begin{pmatrix}
1 & 0 & c \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix} : c \in \mathbb{R} \right\} \cong \mathbb{R}$$

**Quotient**: $H_3/Z(H_3) \cong \mathbb{R}^2$ (abelian)

**Upper central series**:
$$\{e\} \triangleleft Z(H_3) \triangleleft H_3$$

**Nilpotency class**: $c(H_3) = 2$

**중요성**: "가장 간단한" non-abelian nilpotent group

## Example 3: Unitriangular Matrices

$$U_n(\mathbb{F}) = \left\{ \begin{pmatrix}
1 & * & * & \cdots & * \\
0 & 1 & * & \cdots & * \\
0 & 0 & 1 & \cdots & * \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & 1
\end{pmatrix} \right\}$$

(upper triangular with 1's on diagonal)

**정리**: $U_n(\mathbb{F})$ is nilpotent

**Nilpotency class**: $c(U_n) = n-1$

**증명**: Lower central series

$$G_i = \{\text{matrices with } 0 \text{ in first } i \text{ superdiagonals}\}$$

## Example 4: Finite $p$-groups

**정리**: 모든 finite $p$-group은 nilpotent

$p$-group: $|G| = p^n$ for some prime $p$

**증명**: $Z(G) \neq \{e\}$ (class equation)

Induction on $|G|$로 upper central series 구성 
**중요성**: Finite nilpotent groups의 핵심 예시

**따름정리**: Finite nilpotent $\Leftrightarrow$ Direct product of $p$-groups

## Example 5: Dihedral Groups $D_n$

**질문**: $D_n$ nilpotent인가?

**답변**: **NO** (일반적으로)

**이유**: $Z(D_n)$이 작음

- $n$ odd: $Z(D_n) = \{e\}$ $\Rightarrow$ not nilpotent
- $n$ even: $Z(D_n) = \{e, r^{n/2}\}$ but still not nilpotent

**하지만**: $D_n$ is solvable!

**교훈**: Solvable $\not\Leftarrow$ Nilpotent

자세한 내용은 [[Dihedral Group]] 참조

## Example 6: $S_3$

Upper central series:
- $Z_0(S_3) = \{e\}$
- $Z_1(S_3) = Z(S_3) = \{e\}$ (non-abelian이고 order 6)
- Stops!

**결론**: $S_3$ is **NOT nilpotent**

**하지만**: $S_3$ **IS solvable** (derived length 2)

**예**: Solvable but not nilpotent

자세한 내용은 [[Symmetric Group]] 참조

## Example 7: Direct Product

$$G, H \text{ nilpotent} \Rightarrow G \times H \text{ nilpotent}$$

**Nilpotency class**: $c(G \times H) = \max(c(G), c(H))$

**증명**: $Z_i(G \times H) = Z_i(G) \times Z_i(H)$ 
## Example 8: Quaternion Group $Q_8$

$$Q_8 = \{\pm 1, \pm i, \pm j, \pm k\}$$

**Center**: $Z(Q_8) = \{1, -1\} \cong \mathbb{Z}/2\mathbb{Z}$

**Quotient**: $Q_8/Z(Q_8) \cong V_4$ (Klein four-group, abelian)

**Upper central series**:
$$\{1\} \triangleleft \{1, -1\} \triangleleft Q_8$$

**Nilpotency class**: $c(Q_8) = 2$

**결론**: $Q_8$ is nilpotent

---

# <span class="header-properties">Properties</span>

## Closure Properties^[닫힘 성질]

### 1. Subgroups

$G$ nilpotent, $H \leq G \Rightarrow H$ nilpotent

**증명**: $H \cap Z_i(G)$가 $H$의 upper central series 형성 
### 2. Quotients

$G$ nilpotent, $N \triangleleft G \Rightarrow G/N$ nilpotent

**증명**: $(Z_i(G)N)/N$이 $G/N$의 upper central series 
### 3. Extensions (with condition!)

$N \triangleleft G$일 때:

$$N \text{ and } G/N \text{ nilpotent} \Rightarrow G \text{ nilpotent}$$

**주의**: Solvable과 동일한 성질!

### 4. Direct Products

$$G, H \text{ nilpotent} \Rightarrow G \times H \text{ nilpotent}$$

**Nilpotency class**: $c(G \times H) = \max(c(G), c(H))$

## Center Properties

### Non-trivial Center

**정리**: $G$ nilpotent, $G \neq \{e\} \Rightarrow Z(G) \neq \{e\}$

**증명**: Upper central series에서 $Z_1(G) = Z(G) \neq \{e\}$ 
**대우**: $Z(G) = \{e\}$ and $G \neq \{e\} \Rightarrow G$ not nilpotent

### Every Maximal Subgroup is Normal

**정리**: $G$ nilpotent $\Rightarrow$ 모든 maximal subgroup은 normal

**증명**: $M$ maximal, $M \not\triangleleft G$ $\Rightarrow$ $N_G(M) = M$

But normalizer contains $Z(G) \neq \{e\}$ $\Rightarrow$ contradiction 
**응용**: Nilpotent groups의 구조 분석

### Normalizer Condition

**정리**: $H < G$ proper subgroup $\Rightarrow H < N_G(H)$

**즉**: Proper subgroup은 자신의 normalizer에 strictly contained

**증명**: Upper central series 사용

## Nilpotent $\Rightarrow$ Solvable

**정리**: 모든 nilpotent group은 solvable

**증명**: Lower central series가 derived series보다 빠르게 수렴

$$G_i \subseteq G^{(i)} \text{ for all } i$$

$G_n = \{e\} \Rightarrow G^{(n)} = \{e\}$ 
**역은 성립 안 함**: $S_3$ solvable but not nilpotent

자세한 내용은 [[Solvable Group]] 참조

## Finite Nilpotent Groups

**정리**: Finite group $G$ nilpotent $\Leftrightarrow G$는 $p$-groups의 direct product

$$G \cong P_1 \times P_2 \times \cdots \times P_k$$

where each $P_i$는 $p_i$-group (different primes)

**증명**: Sylow subgroups가 모두 normal (maximal subgroup property)

**응용**: Finite nilpotent groups의 완전한 특성화!

## Frattini Subgroup^[프라티니 부분군]

$$\Phi(G) = \bigcap_{M \text{ maximal}} M$$

**정리**: $G$ nilpotent $\Rightarrow \Phi(G)$ nilpotent

**성질**: $\Phi(G)$ is characteristic, nilpotent

---

# <span class="header-theorem">Theorem</span>

## Characterization of Finite Nilpotent Groups

$G$ finite group. **TFAE** (The following are equivalent):

1. $G$ is nilpotent
2. Upper central series reaches $G$
3. Lower central series reaches $\{e\}$
4. Every Sylow subgroup is normal
5. $G$ is direct product of its Sylow subgroups
6. Every maximal subgroup is normal
7. $G$ satisfies normalizer condition

**증명**: (1) $\Leftrightarrow$ (2) $\Leftrightarrow$ (3): Definition

(1) $\Rightarrow$ (6): Shown above

(6) $\Rightarrow$ (4): Sylow subgroups in maximal subgroups

(4) $\Leftrightarrow$ (5): Chinese remainder theorem

(5) $\Rightarrow$ (1): $p$-groups nilpotent 
## $p$-groups are Nilpotent

**정리**: $|G| = p^n$ ($p$ prime) $\Rightarrow G$ nilpotent

**증명**: Class equation

$$|G| = |Z(G)| + \sum [G : C_G(x)]$$

$p \mid |G| \Rightarrow p \mid |Z(G)|$ (since $p \mid [G : C_G(x)]$ for $x \notin Z(G)$)

$\Rightarrow Z(G) \neq \{e\}$

Induction: $G/Z(G)$도 $p$-group $\Rightarrow$ nilpotent 
**Nilpotency class**: $c(G) \leq \log_2 n + 1$ (loose bound)

## Hall-Higman Theorem

$G$ finite nilpotent $\Leftrightarrow$ Normal Sylow subgroups

**응용**: 유한군의 nilpotency 판정

## Fitting Subgroup^[피팅 부분군]

$$\text{Fit}(G) = \text{largest nilpotent normal subgroup of } G$$

**존재성**: Nilpotent normal subgroups의 product도 nilpotent

**성질**:
- $\text{Fit}(G) \triangleleft G$ (characteristic)
- Contains all nilpotent normal subgroups
- $C_G(\text{Fit}(G)) \subseteq \text{Fit}(G)$ (self-centralizing)

## Nilpotency and Derived Length

$G$ nilpotent with class $c$

**정리**: Derived length $d(G) \leq \log_2 c + 1$

**의미**: Nilpotent groups는 "빠르게" abelian에 수렴

## Three Subgroups Lemma

$[A, B, C] = \langle [[a,b],c] : a \in A, b \in B, c \in C \rangle$

**정리**: $[A,B,C] = \{e\}$ and $[B,C,A] = \{e\} \Rightarrow [C,A,B] = \{e\}$

**응용**: Lower central series 계산

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Nilpotent = "Center가 충분히 큼"**

### 메타포: 양파 껍질

**Center**: 가장 안쪽 (모든 것과 교환)

**$Z_2(G)$**: 두 번째 층 (modulo center에서 중심적)

**계속 벗기면**: 결국 전체 group

### 메타포: 위계 구조

**Nilpotent group**: 명확한 "중심성" 위계

- Level 0: Identity
- Level 1: Center
- Level 2: "Almost central"
- ...
- Level $n$: 전체 group

## 왜 "Nilpotent"인가?

**이름의 유래**: "Nil" = nothing, "potent" = powerful

**Ring theory에서**:

원소 $x$가 **nilpotent** $\Leftrightarrow$ $x^n = 0$ for some $n$

**Group theory 연결**:

Lie algebra에서 nilpotent $\Rightarrow$ Lie group nilpotent

**직관**: "충분히 반복하면 사라짐" (commutators vanish)

## Nilpotent vs Solvable vs Abelian

| | **Abelian** | **Nilpotent** | **Solvable** |
|---|---|---|---|
| **정의** | $ab = ba$ | Upper central series | Derived series |
| **포함** | Most restrictive | Middle | Least restrictive |
| **Center** | $Z(G) = G$ | $Z(G) \neq \{e\}$ | No constraint |
| **예** | $\mathbb{Z}, \mathbb{Z}/n\mathbb{Z}$ | $p$-groups, $H_3$ | $S_4, D_n$ |
| **Non-예** | $S_3$ | $S_3, D_3$ | $S_5, A_5$ |

**관계**:
$$\text{Abelian} \subsetneq \text{Nilpotent} \subsetneq \text{Solvable}$$

## 경계 예시

**$S_3$**: Solvable , Nilpotent ✗

**이유**: $Z(S_3) = \{e\}$

**$D_3 \cong S_3$**: 동일

**$Q_8$**: Nilpotent  (class 2)

**$D_4$**: 복잡 - NOT nilpotent (일반적으로)

## Practical Tests for Nilpotency

### 1. Compute Center

$Z(G) = \{e\}$ and $G \neq \{e\}$ $\Rightarrow$ Not nilpotent

### 2. Check if $p$-group

$|G| = p^n$ $\Rightarrow$ Nilpotent 
### 3. Finite Group: Sylow Subgroups

All Sylow subgroups normal $\Rightarrow$ Nilpotent

### 4. Upper Central Series

Compute iteratively: $Z_i(G)$

Reaches $G$? $\Rightarrow$ Nilpotent

### 5. Maximal Subgroups

Some maximal subgroup not normal $\Rightarrow$ Not nilpotent

## 응용

**Finite Group Theory**:
- $p$-groups
- Sylow theory
- Hall subgroups

**Lie Theory**:
- Nilpotent Lie algebras
- Solvable Lie groups
- Structure theory

**Number Theory**:
- Class field theory
- Galois representations

**Topology**:
- Fundamental groups
- Nilpotent spaces

## 역사적 배경

**1930s-1940s**: Hall, Fitting - Nilpotent groups 체계화

**1950s**: Lazard - $p$-groups와 Lie algebras 연결

**1960s**: Mal'cev - Nilpotent groups의 일반 이론

**현대**: Computational group theory

## 표기법

| 표기 | 의미 |
|------|------|
| $Z_i(G)$ | $i$-th term of upper central series |
| $G_i$ | $i$-th term of lower central series |
| $c(G)$ | Nilpotency class |
| $\text{Fit}(G)$ | Fitting subgroup |
| $\Phi(G)$ | Frattini subgroup |
| $[G,H]$ | Commutator subgroup |

## Common Pitfall^[흔한 실수]

### 1. Nilpotent ≠ Abelian

Nilpotent는 abelian보다 일반적

**예**: $H_3, Q_8$ nilpotent but not abelian

### 2. Solvable ≠ Nilpotent

**예**: $S_3$ solvable but not nilpotent

### 3. $Z(G) \neq \{e\}$ doesn't imply nilpotent

Non-trivial center는 필요조건이지만 충분조건 아님

**반례**: Some groups with non-trivial center but not nilpotent

### 4. Direct product of nilpotent is nilpotent

 True! (Unlike solvable)

### 5. Lower central series vs Derived series

Lower central series $\subseteq$ Derived series

Nilpotent $\Rightarrow$ Solvable (but not conversely)

## 연결: Lie Theory

**Lie algebra** $\mathfrak{g}$ nilpotent $\Leftrightarrow$

$$[\mathfrak{g}, [\mathfrak{g}, \cdots [\mathfrak{g}, \mathfrak{g}]\cdots]] = 0$$

**Connected Lie group** nilpotent $\Leftrightarrow$ Lie algebra nilpotent

**예**: Heisenberg group $\leftrightarrow$ Heisenberg Lie algebra

## 계산 예시

### $Q_8$ Upper Central Series

$$Z_0 = \{1\}$$
$$Z_1 = Z(Q_8) = \{1, -1\}$$
$$Z_2 = Q_8$$ (since $Q_8/Z_1 \cong V_4$ abelian)

**Nilpotency class**: 2

### $H_3(\mathbb{R})$ Lower Central Series

$$G_0 = H_3$$
$$G_1 = [H_3, H_3] = Z(H_3) \cong \mathbb{R}$$
$$G_2 = [H_3, Z(H_3)] = \{e\}$$

**Nilpotency class**: 2

## 관련 개념

- [[Abelian Group]]: Nilpotent of class 1
- [[Solvable Group]]: Weaker condition
- [[Group]]: Basic structure
- [[Center]]: Key to nilpotency
- [[Sylow Theorems]]: Finite nilpotent characterization

## 추가 학습 주제

**기초**:
- Upper/Lower central series
- $p$-groups
- Heisenberg group

**중급**:
- Fitting subgroup
- Frattini subgroup
- Hall-Higman theorems

**고급**:
- Lazard correspondence
- Mal'cev completion
- Nilpotent Lie groups

