# <span class="header-prerequisite">Prerequisite</span>
- [[Function]]
- [[Homomorphism]]
- [[Group]]
- [[Ring]]
- [[Field]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Artin, Algebra
- Lang, Algebra

---

# <span class="header-definition">Definition</span>

## Isomorphism^[동형사상]

**Isomorphism^[동형사상]**: **Bijective^[전단사]** homomorphism^[준동형사상]

함수 $\phi: G \to H$가 **isomorphism^[동형사상]**이다 $\Leftrightarrow$

1. $\phi$는 homomorphism (구조 보존)
2. $\phi$는 bijective (일대일 대응)

**의미**: 두 구조가 "본질적으로 같음"

### 동등 조건

Homomorphism $\phi: G \to H$에 대해 다음은 동등:

1. $\phi$는 isomorphism
2. $\phi$는 injective^[단사] + surjective^[전사]
3. $\phi$는 homomorphism이고 inverse^[역함수] $\phi^{-1}$가 존재하며 $\phi^{-1}$도 homomorphism
4. $\ker(\phi) = \{e\}$ and $\text{im}(\phi) = H$

## Isomorphic Structures^[동형 구조]

두 대수 구조 $G$와 $H$가 **isomorphic^[동형]**이다 (기호: $G \cong H$) $\Leftrightarrow$

$$\exists \text{ isomorphism } \phi: G \to H$$

**의미**: 
- "대수적으로 구별 불가능"
- "같은 구조의 다른 표현"
- "Relabeling"

**주의**: $G \cong H$는 equivalence relation^[동치 관계]

### Related Notation^[관련 표기법]

수학에서 사용되는 유사한 기호들:

| LaTeX | 기호 | 이름 | 의미 |
|-------|------|------|------|
| `\cong` | $\cong$ | Isomorphic^[동형] | 구조가 완전히 같음 (가장 강함) |
| `\simeq` | $\simeq$ | Homotopy equivalent^[호모토피 동치] | 위상적으로 본질적으로 같음 (Topology) |
| `\sim` | $\sim$ | Equivalent/Similar^[동치/닮음] | 어떤 관계로 동치 (일반적) |
| `\approx` | $\approx$ | Approximately equal^[근사 같음] | 수치적으로 가까움 |

**강도 순서**: $\cong$ (강함) > $\simeq$ (중간) > $\sim$ (약함) > $\approx$ (근사)

**Group Theory에서**: 주로 $\cong$ 사용

## Group Isomorphism^[군 동형사상]

Bijective group homomorphism

$$\phi: G \to H \text{ bijective and } \phi(ab) = \phi(a)\phi(b)$$

### 성질

Inverse function $\phi^{-1}: H \to G$도 자동으로 group homomorphism

**증명**: $h_1 = \phi(g_1)$, $h_2 = \phi(g_2)$이면
$$\phi^{-1}(h_1h_2) = \phi^{-1}(\phi(g_1)\phi(g_2)) = \phi^{-1}(\phi(g_1g_2)) = g_1g_2 = \phi^{-1}(h_1)\phi^{-1}(h_2)$$

## Ring Isomorphism^[환 동형사상]

Bijective ring homomorphism

$$\phi: R \to S \text{ bijective, } \phi(a+b) = \phi(a)+\phi(b), \phi(ab) = \phi(a)\phi(b)$$

Inverse $\phi^{-1}$도 ring homomorphism

## Field Isomorphism^[체 동형사상]

Bijective field homomorphism

**중요**: Field homomorphism은 자동으로 injective이므로, surjective만 확인하면 isomorphism!

## Automorphism^[자기동형사상]

Isomorphism $\phi: G \to G$ (domain = codomain)

구조 자기 자신으로의 bijective homomorphism

### Automorphism Group^[자기동형군]

$$\text{Aut}(G) = \{\phi: G \to G : \phi \text{ is automorphism}\}$$

**연산**: Function composition

**성질**: $\text{Aut}(G)$는 group
- Identity: $\text{id}_G$
- Inverse: $\phi^{-1}$
- Associativity: 함수 합성의 결합법칙

### Inner Automorphism^[내부 자기동형사상]

$g \in G$에 대해:

$$\phi_g: G \to G, \quad \phi_g(x) = gxg^{-1}$$

**Conjugation^[켤레]**에 의한 automorphism

**집합**: 
$$\text{Inn}(G) = \{\phi_g : g \in G\} \leq \text{Aut}(G)$$

**성질**: $\text{Inn}(G) \triangleleft \text{Aut}(G)$ (normal subgroup)

**동형**: $\text{Inn}(G) \cong G/Z(G)$ where $Z(G)$는 center^[중심]

### Outer Automorphism^[외부 자기동형사상]

Inner automorphism이 아닌 automorphism

**Outer automorphism group^[외부 자기동형군]**:

$$\text{Out}(G) = \text{Aut}(G) / \text{Inn}(G)$$

---

# <span class="header-examples">Examples</span>

## Example 1: Identity Map^[항등 사상]

$$\text{id}_G: G \to G, \quad \text{id}_G(g) = g$$

**항상 isomorphism** (trivial)

## Example 2: Exponential Isomorphism^[지수 동형사상]

$$\exp: (\mathbb{R}, +) \to (\mathbb{R}^+, \times), \quad \exp(x) = e^x$$

**Isomorphism**:
- Homomorphism: $\exp(x+y) = e^x \cdot e^y$
- Bijective: Yes

**Inverse**: $\ln: (\mathbb{R}^+, \times) \to (\mathbb{R}, +)$

## Example 3: Complex Numbers^[복소수]

$$\mathbb{C} / \mathbb{R}$$

**Isomorphism**: 
$$\phi: \mathbb{C} \to \mathbb{R}^2, \quad \phi(a + bi) = (a, b)$$

As **vector spaces**: $\mathbb{C} \cong \mathbb{R}^2$

**주의**: Ring structure는 다름! (곱셈이 다름)

## Example 4: Cyclic Groups^[순환군]

모든 order $n$인 cyclic group은 isomorphic:

$$C_n \cong \mathbb{Z}/n\mathbb{Z}$$

**Isomorphism**: 
$$\phi: C_n \to \mathbb{Z}/n\mathbb{Z}, \quad \phi(g^k) = [k]$$

where $g$는 generator of $C_n$

**무한 순환군**: $C_\infty \cong (\mathbb{Z}, +)$

## Example 5: Klein Four-Group^[클라인 4-군]

$$V_4 = \{e, a, b, c\} \cong C_2 \times C_2$$

where $a^2 = b^2 = c^2 = e$, $ab = c$

**Isomorphism**:
$$V_4 \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$$

**주의**: $V_4 \not\cong C_4$ (both order 4, but not isomorphic)
- $V_4$: 모든 non-identity 원소의 order = 2
- $C_4$: order 4인 원소 존재

## Example 6: Matrix Representations^[행렬 표현]

$$\text{SO}(2) \cong \text{U}(1) \cong S^1$$

회전군, 단위 복소수, 원은 모두 isomorphic (as groups)

**Explicit isomorphism**:
$$\phi: \text{SO}(2) \to S^1, \quad \phi\left(\begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}\right) = e^{i\theta}$$

## Example 7: Fundamental Theorem of Finite Abelian Groups

모든 finite abelian group은 cyclic groups의 direct product와 isomorphic:

### Invariant Factor Form^[불변 인자 형태]

$$G \cong C_{n_1} \times C_{n_2} \times \cdots \times C_{n_k}$$

where $n_i \mid n_{i+1}$ (즉, $n_i$가 $n_{i+1}$을 나눔)

**예**: $|G| = 12$
- $C_{12}$ (12 = 12)
- $C_2 \times C_6$ (2 | 6 ✓)

### Primary Decomposition Form^[소인수 분해 형태]

$$G \cong C_{p_1^{a_1}} \times C_{p_2^{a_2}} \times \cdots \times C_{p_r^{a_r}}$$

where $p_i$는 소수 (중복 가능)

**예**: $|G| = 12$
- $C_{12} \cong C_4 \times C_3 \cong C_{2^2} \times C_3$
- $C_2 \times C_6 \cong C_2 \times C_2 \times C_3 \cong C_2^2 \times C_3$
- $C_2 \times C_2 \times C_3 \cong C_2^2 \times C_3$

**유일성**: 각 형태에서 표현은 순서를 제외하고 유일

## Example 8: First Isomorphism Theorem

$$\mathbb{Z}/n\mathbb{Z} \cong \text{im}(\pi)$$

where $\pi: \mathbb{Z} \to \mathbb{Z}/n\mathbb{Z}$ is canonical projection

More generally: $G/\ker(\phi) \cong \text{im}(\phi)$

자세한 내용은 [[Homomorphism]] 참조

## Example 9: Field Extensions^[체 확대]

$$\mathbb{Q}(\sqrt{2}) \cong \mathbb{Q}[x]/(x^2 - 2)$$

**Isomorphism**:
$$\phi: \mathbb{Q}[x]/(x^2-2) \to \mathbb{Q}(\sqrt{2}), \quad \phi([p(x)]) = p(\sqrt{2})$$

## Example 10: Quaternions^[사원수]

$$\mathbb{H}^\times / \{\pm 1\} \cong \text{SO}(3)$$

Unit quaternions modulo $\{\pm 1\}$ isomorphic to 3D rotations

자세한 내용은 [[Ring]] 참조

## Example 11: Polynomial Rings^[다항식환]

$$\mathbb{R}[x] \not\cong \mathbb{C}[x]$$

**Not isomorphic** as rings (though both polynomial rings)
- $\mathbb{R}[x]$: $x^2 + 1$ irreducible
- $\mathbb{C}[x]$: $x^2 + 1 = (x-i)(x+i)$ reducible

## Example 12: Complex Conjugation^[복소 켤레]

$$\sigma: \mathbb{C} \to \mathbb{C}, \quad \sigma(a + bi) = a - bi$$

**Field automorphism**:
- $\sigma(z + w) = \sigma(z) + \sigma(w)$
- $\sigma(zw) = \sigma(z)\sigma(w)$
- Bijective

**Order 2**: $\sigma^2 = \text{id}$

**Galois group**: $\text{Gal}(\mathbb{C}/\mathbb{R}) = \{\text{id}, \sigma\} \cong C_2$

---

# <span class="header-properties">Properties</span>

## Isomorphism is Equivalence Relation^[동형은 동치 관계]

집합 $\mathcal{C}$ (같은 종류의 대수 구조들)에서 $\cong$는 equivalence relation:

### 1. Reflexive^[반사적]

$$G \cong G$$

(identity map is isomorphism)

### 2. Symmetric^[대칭적]

$$G \cong H \Rightarrow H \cong G$$

(inverse of isomorphism is isomorphism)

### 3. Transitive^[추이적]

$$G \cong H \text{ and } H \cong K \Rightarrow G \cong K$$

(composition of isomorphisms is isomorphism)

## Isomorphism Preserves All Algebraic Properties^[모든 대수적 성질 보존]

$\phi: G \to H$ isomorphism이면:

### 1. Order^[위수]

$$|G| = |H|$$

**원소의 위수**: $|\phi(g)| = |g|$

### 2. Structure

- $G$ abelian $\Leftrightarrow$ $H$ abelian
- $G$ cyclic $\Leftrightarrow$ $H$ cyclic
- $G$ simple $\Leftrightarrow$ $H$ simple

### 3. Subgroups^[부분군]

$$K \leq G \Leftrightarrow \phi(K) \leq H$$

**Bijection**: $\{K : K \leq G\} \leftrightarrow \{L : L \leq H\}$

### 4. Normal Subgroups^[정규 부분군]

$$N \triangleleft G \Leftrightarrow \phi(N) \triangleleft H$$

### 5. Quotients^[몫]

$$G/N \cong H/\phi(N)$$

### 6. Center^[중심]

$$\phi(Z(G)) = Z(H)$$

**결론**: Isomorphic structures는 **대수적으로 구별 불가능**

## Automorphism Group Properties^[자기동형군의 성질]

### 1. $\text{Aut}(G)$ is a Group

- **Identity**: $\text{id}_G$
- **Inverse**: $\phi^{-1}$
- **Composition**: $\phi \circ \psi$

### 2. Inner Automorphisms Form Normal Subgroup

$$\text{Inn}(G) \triangleleft \text{Aut}(G)$$

**증명**: Conjugation by composition

### 3. Isomorphism with Quotient

$$\text{Inn}(G) \cong G/Z(G)$$

**Homomorphism**: $g \mapsto \phi_g$ with kernel $Z(G)$

### 4. Examples of $\text{Aut}(G)$

- $\text{Aut}(\mathbb{Z}) \cong C_2$
- $\text{Aut}(C_n) \cong (\mathbb{Z}/n\mathbb{Z})^\times$ (units mod $n$)
- $\text{Aut}(C_p) \cong C_{p-1}$ (for prime $p$)
- $\text{Aut}(V_4) \cong S_3$

## Uniqueness up to Isomorphism^[동형을 제외하고 유일]

많은 대수 구조가 "isomorphism을 제외하고 유일":

### Examples

1. **Splitting field^[분해체]**: $p(x) \in K[x]$의 splitting field는 $\cong$ up to isomorphism
2. **Algebraic closure^[대수적 폐포]**: $\overline{K}$는 $\cong$ up to isomorphism
3. **Free group^[자유군]**: Rank $n$인 free group은 $F_n$ unique up to $\cong$
4. **Finite fields^[유한체]**: Order $p^n$인 field는 $\mathbb{F}_{p^n}$ unique up to $\cong$

**의미**: "본질적으로 하나만 존재"

## Non-isomorphic Groups of Same Order^[같은 위수의 비동형 군]

**주의**: $|G| = |H|$ does not imply $G \cong H$!

### Example: Order 4

- $C_4$: Cyclic
- $V_4 = C_2 \times C_2$: Klein four-group

**Not isomorphic**: $C_4$는 order 4 원소 있음, $V_4$는 없음

### Example: Order 8

5개의 non-isomorphic groups:
- $C_8$
- $C_4 \times C_2$
- $C_2 \times C_2 \times C_2$
- $D_4$ (dihedral)
- $Q_8$ (quaternion)

---

# <span class="header-theorem">Theorem</span>

## Cayley's Theorem^[케일리 정리]

모든 group $G$는 어떤 symmetric group의 subgroup과 isomorphic:

$$G \cong \text{subgroup of } S_{|G|}$$

**증명**: Regular representation^[정규 표현]
$$\phi: G \to S_G, \quad \phi(g)(x) = gx$$

**의미**: 모든 군을 permutation group으로 볼 수 있음

## Classification of Finite Simple Groups^[유한 단순군의 분류]

모든 finite simple group은 다음 중 하나와 isomorphic:

1. **Cyclic groups of prime order**: $C_p$
2. **Alternating groups**: $A_n$ ($n \geq 5$)
3. **Groups of Lie type**: e.g., $\text{PSL}_n(\mathbb{F}_q)$
4. **Sporadic groups**: 26개 (e.g., Monster group)

**증명**: ~15,000 페이지 (multiple papers, 1955-2004)

## Fundamental Theorem of Finite Abelian Groups^[유한 생성 아벨군의 기본 정리]

모든 finite abelian group은 cyclic groups의 direct product와 isomorphic

### Two Standard Forms

**1. Invariant Factor Form^[불변 인자 형태]**:

$$G \cong C_{n_1} \times C_{n_2} \times \cdots \times C_{n_k}$$

where $n_i \mid n_{i+1}$ ($n_i$가 $n_{i+1}$을 나눔)

**2. Primary Decomposition Form^[소인수 분해 형태]**:

$$G \cong C_{p_1^{a_1}} \times C_{p_2^{a_2}} \times \cdots \times C_{p_r^{a_r}}$$

where $p_i$는 소수 (중복 가능)

**유일성**: 각 형태에서 표현은 순서를 제외하고 유일

## Structure Theorem for Finitely Generated Abelian Groups^[유한 생성 아벨군의 구조 정리]

**더 일반적인 정리**: Finitely generated abelian group $G$에 대해:

$$G \cong \mathbb{Z}^r \times T(G)$$

where:
- $r = \text{rank}(G) \geq 0$ (free part의 rank)
- $T(G)$ is the torsion subgroup^[비틀림 부분군] (finite)

### Components

**Free part^[자유 부분]**: $\mathbb{Z}^r$ (torsion-free)
- $r$개의 independent generators
- Rank $r$는 invariant (well-defined)

**Torsion part^[비틀림 부분]**: $T(G)$ (finite abelian group)
- Fundamental Theorem으로 분해:
$$T(G) \cong C_{p_1^{a_1}} \times C_{p_2^{a_2}} \times \cdots \times C_{p_k^{a_k}}$$

### Examples

1. $\mathbb{Z}^2$: rank 2, no torsion
2. $\mathbb{Z}/12\mathbb{Z}$: rank 0, pure torsion
3. $\mathbb{Z} \times \mathbb{Z}/6\mathbb{Z}$: rank 1, torsion $\mathbb{Z}/6\mathbb{Z}$
4. $\mathbb{Z}^3 \times C_2 \times C_4$: rank 3, torsion $C_2 \times C_4$

**특수한 경우**:
- Finite abelian groups: $r = 0$ (pure torsion)
- Free abelian groups: $T(G) = \{0\}$ (torsion-free)

자세한 내용은 [[Group]] 참조

## Recognizing Isomorphisms^[동형 인식]

두 groups $G, H$에 대해:

### Necessary Conditions for $G \cong H$

1. $|G| = |H|$
2. Abelian ↔ Abelian
3. Cyclic ↔ Cyclic
4. 같은 order의 원소 개수 일치
5. $|Z(G)| = |Z(H)|$
6. Exponent^[지수] 일치

**주의**: 이들이 모두 만족해도 $G \cong H$는 보장 안 됨!

### Sufficient Conditions

특정 구조에서:
- Cyclic groups: $|G| = |H| \Rightarrow G \cong H$
- Prime order groups: $|G| = p$ (prime) $\Rightarrow G \cong C_p$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Isomorphism**: "Re-labeling" of elements

두 구조가 isomorphic $\Rightarrow$ 원소의 "이름"만 다르고 구조는 동일

**메타포**:
- 같은 건물의 다른 blueprint
- 같은 곡의 다른 key
- 같은 데이터의 다른 encoding

## Isomorphism vs Equality

| | **Equal** | **Isomorphic** |
|---|---|---|
| 의미 | 같은 것 | 구조가 같음 |
| 엄격성 | 매우 엄격 | 더 유연 |
| 예 | $\{1,2\} = \{1,2\}$ | $C_2 \cong \mathbb{Z}/2\mathbb{Z}$ |

**철학적**: 대수학에서는 equality보다 isomorphism이 더 중요!

## Automorphism의 중요성

**Automorphism = Self-symmetry**

$\text{Aut}(G)$는 $G$의 "대칭성"을 측정

### Examples

- $\text{Aut}(\mathbb{Z})$: 작음 ($\cong C_2$)
- $\text{Aut}(S_n)$: 대부분 inner (for $n \neq 6$)
- $\text{Aut}(S_6)$: Exceptional outer automorphism!

## 분류 문제 (Classification Problem)

**목표**: 주어진 조건의 모든 구조를 isomorphism up to 분류

### 해결됨

- Finite abelian groups
- Finite simple groups
- Finite fields

### 어려움/미해결

- Finite groups (일반)
- Finitely generated groups
- Infinite simple groups

## 표기법

| 표기 | 의미 |
|------|------|
| $G \cong H$ | $G$ is isomorphic to $H$ |
| $\text{Aut}(G)$ | Automorphism group |
| $\text{Inn}(G)$ | Inner automorphisms |
| $\text{Out}(G)$ | Outer automorphisms |
| $\phi: G \xrightarrow{\cong} H$ | $\phi$ is isomorphism |

## Galois Theory 관점

**Galois group = Field automorphisms**

$$\text{Gal}(\mathbb{F}/K) = \text{Aut}_K(\mathbb{F})$$

$K$를 고정하는 $\mathbb{F}$의 automorphisms

자세한 내용은 [[Galois Theory]] 참조

## Common Pitfall^[흔한 실수]

### 1. Same cardinality $\Rightarrow$ Isomorphic?

✗ Finite groups: $|G| = |H|$ doesn't imply $G \cong H$

✓ Infinite cyclic groups: All $\cong \mathbb{Z}$

### 2. Isomorphism = Bijection?

✗ Bijection만으로는 부족

✓ Bijection + Homomorphism

### 3. VecTorsion spaces

✓ Same dimension $\Rightarrow$ Isomorphic (finite-dimensional)

But: 명시적 isomorphism은 basis 선택 필요

### 4. All automorphisms are inner?

✗ Not always!

**반례**: $S_6$는 outer automorphism 있음

### 5. Ring isomorphism

주의: Vector space isomorphism $\neq$ Ring isomorphism

**예**: $\mathbb{C} \cong_{\text{vs}} \mathbb{R}^2$ but $\mathbb{C} \not\cong_{\text{ring}} \mathbb{R}^2$

## 역사적 배경

**Isomorphism** (Greek: isos = equal, morphe = form)

**발전**:
- 19세기: Group theory에서 등장
- 20세기: 일반화 (rings, fields, etc.)
- Category theory: Morphism의 특수한 경우

## 응용

**수학**:
- 구조 분류
- 대수방정식 풀이
- Representation theory

**물리학**:
- Symmetry groups
- Gauge theories
- Quantum mechanics

**컴퓨터 과학**:
- Graph isomorphism problem (complexity theory)
- Cryptography
- Type isomorphisms

## 관련 개념

- [[Homomorphism]]: More general concept
- [[Galois Theory]]: Field automorphisms
- [[Quotient Group]]: Isomorphism theorems
- [[Linear mapping]]: Vector space isomorphisms

## Category Theory에서

**Isomorphism = Invertible morphism**

Morphism $f: A \to B$가 isomorphism $\Leftrightarrow$ $\exists g: B \to A$ such that
- $g \circ f = \text{id}_A$
- $f \circ g = \text{id}_B$

자세한 내용은 [[Category Theory]] 참조

## 추가 학습 주제

**기초**:
- Isomorphism theorems
- Automorphism groups
- Classification of small groups

**중급**:
- Representation theory
- Character theory
- Galois theory

**고급**:
- Equivalence of categories
- Derived equivalences
- K-theory

