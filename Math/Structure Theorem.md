# <span class="header-prerequisite">Prerequisite</span>
- [[Module]]
- [[Principal Ideal Domain]]
- [[Abelian Group]]
- [[Direct Sum]]
- [[Ideal]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra
- Hungerford, Algebra

---

# <span class="header-definition">Definition</span>

## Structure Theorem for Finitely Generated Modules over PID

**정리** (**Fundamental Theorem**): $R$ PID, $M$ finitely generated^[유한 생성] $R$-module^[가군]

$$M \cong R^r \oplus R/(d_1) \oplus R/(d_2) \oplus \cdots \oplus R/(d_n)$$

where $d_1 \mid d_2 \mid \cdots \mid d_n$ (divisibility chain)

**구성 요소**:
1. **Free part^[자유 부분]**: $R^r$ (rank $r \geq 0$)
2. **Torsion part^[비틀림 부분]**: $R/(d_1) \oplus \cdots \oplus R/(d_n)$

**불변량^[Invariants]**:
- **Rank**: $r$ (uniquely determined)
- **Invariant factors^[불변 인자]**: $d_1, d_2, \ldots, d_n$ (unique up to units)

### Invariant Factor Form^[불변 인자 형태]

위의 표현:

$$M \cong R^r \oplus \bigoplus_{i=1}^{n} R/(d_i)$$

where $d_1 \mid d_2 \mid \cdots \mid d_n$

**특징**: Divisibility chain이 핵심

### Elementary Divisor Form^[기본 인자 형태]

**Alternative form**: 소 원소^[prime elements]의 거듭제곱으로 분해

$$M \coss R^r \oplus \bigoplus_{i=1}^{k} R/(p_i^{e_i})$$

where $p_i$ are (not necessarily distinct) primes

**특징**: Chinese Remainder Theorem으로 변환 가능

$$R/(d_i) \cong R/(p_1^{a_1}) \oplus \cdots \oplus R/(p_m^{a_m})$$

if $d_i = p_1^{a_1} \cdots p_m^{a_m}$

## Fundamental Theorem of Finitely Generated Abelian Groups

**특수 경우**: $R = \mathbb{Z}$인 경우

Finitely generated abelian group $G$:

$$G \cong \mathbb{Z}^r \oplus \mathbb{Z}/(d_1) \oplus \cdots \oplus \mathbb{Z}/(d_n)$$

where $d_1 \mid d_2 \mid \cdots \mid d_n$

**구성 요소**:
1. **Free part**: $\mathbb{Z}^r$ (rank $r$)
2. **Torsion part**: $T(G) = \mathbb{Z}/(d_1) \oplus \cdots \oplus \mathbb{Z}/(d_n)$ (finite)

**Primary decomposition^[소인수 분해]**:

$$G \cong \mathbb{Z}^r \oplus \bigoplus_{p \text{ prime}} G_p$$

where $G_p$ is $p$-primary component^[$p$-일차 성분]:

$$G_p \cong \mathbb{Z}/p^{a_1}\mathbb{Z} \oplus \cdots \oplus \mathbb{Z}/p^{a_k}\mathbb{Z}$$

자세한 내용은 [[Abelian Group]], [[Isomorphism]] 참조

## Fundamental Theorem of Finite Abelian Groups

**더 특수한 경우**: $r = 0$ (no free part, pure torsion)

Finite abelian group $G$:

**Invariant Factor Form**:

$$G \cong \mathbb{Z}/n_1\mathbb{Z} \times \mathbb{Z}/n_2\mathbb{Z} \times \cdots \times \mathbb{Z}/n_k\mathbb{Z}$$

where $n_1 \mid n_2 \mid \cdots \mid n_k$

**Primary Decomposition Form**:

$$G \cong \mathbb{Z}/p_1^{a_1}\mathbb{Z} \times \mathbb{Z}/p_2^{a_2}\mathbb{Z} \times \cdots \times \mathbb{Z}/p_m^{a_m}\mathbb{Z}$$

where $p_i$ are primes (possibly repeated)

**유일성**: 각 form에서 표현은 순서를 제외하고 유일

자세한 내용은 [[Generator]] 참조

---

# <span class="header-theorem">Theorems</span>

## Uniqueness of Decomposition

**정리**: Invariant factors $d_1, \ldots, d_n$과 rank $r$은 **유일하게 결정**됨 (up to units)

**증명 개요**:
1. Rank는 localization으로 결정
2. Invariant factors는 quotients로 결정

$$d_i \sim \frac{|\Lambda_i(M)|}{|\Lambda_{i-1}(M)|}$$

where $\Lambda_i$ are exterior powers

## Existence of Decomposition

**증명 방법**: 두 가지 접근

### 1. Smith Normal Form^[스미스 표준형]

**핵심**: Presentation matrix를 Smith normal form으로 변환

$$M = R^m / \text{im}(A)$$

where $A: R^n \to R^m$

**과정**:
1. Row/column operations로 $A$를 diagonal로 만듦
2. Diagonal entries: $d_1 \mid d_2 \mid \cdots$
3. 결과:

$$M \cong R^r \oplus R/(d_1) \oplus \cdots \oplus R/(d_k)$$

### 2. Primary Decomposition

**핵심**: Torsion part를 $p$-primary components로 분해

$$T(M) = \bigoplus_{p \text{ prime}} T_p(M)$$

where $T_p(M) = \{m \in M : p^k m = 0 \text{ for some } k\}$

## Relationship Between Forms

**정리**: Invariant factor form $\Leftrightarrow$ Elementary divisor form

**변환**:
1. Invariant factors $\to$ Elementary divisors:
   - 각 $d_i$를 prime powers로 분해
   - Chinese Remainder Theorem 적용

2. Elementary divisors $\to$ Invariant factors:
   - Prime powers를 appropriate하게 combine
   - Divisibility chain 만족하도록 재배열

**예**: $d_1 = 6$, $d_2 = 12$
- Prime decomposition: $6 = 2 \cdot 3$, $12 = 2^2 \cdot 3$
- Elementary divisors: $2, 2^2, 3, 3$
- Group: $\mathbb{Z}/2\mathbb{Z} \oplus \mathbb{Z}/4\mathbb{Z} \oplus \mathbb{Z}/3\mathbb{Z} \oplus \mathbb{Z}/3\mathbb{Z}$

## Classification Theorem

**결과**: Structure theorem은 finitely generated modules over PID를 **완전히 분류**

$$M \cong N \quad \Leftrightarrow \quad \text{Same invariant factors}$$

**의미**: Isomorphism problem이 완전히 해결됨!

---

# <span class="header-examples">Examples</span>

## Example 1: $\mathbb{Z}$-modules (Abelian Groups)

### Free Abelian Group

$$\mathbb{Z}^3 \cong \mathbb{Z} \oplus \mathbb{Z} \oplus \mathbb{Z}$$

- Rank: $r = 3$
- Torsion: none
- Invariant factors: (none)

### Finite Abelian Group

$$G = \mathbb{Z}/12\mathbb{Z}$$

**Invariant factor form**: $\mathbb{Z}/12\mathbb{Z}$

**Elementary divisor form**: 
- $12 = 2^2 \cdot 3$
- $G \cong \mathbb{Z}/4\mathbb{Z} \oplus \mathbb{Z}/3\mathbb{Z}$

### Mixed Group

$$G = \mathbb{Z}^2 \oplus \mathbb{Z}/6\mathbb{Z} \oplus \mathbb{Z}/12\mathbb{Z}$$

- Rank: $r = 2$
- Invariant factors: $6 \mid 12$
- Elementary divisors: $2, 2^2, 3, 3$

## Example 2: Classification of Groups of Order 12

$$|G| = 12 = 2^2 \cdot 3$$

**Abelian groups of order 12** (up to isomorphism):

1. $\mathbb{Z}/12\mathbb{Z}$ (cyclic)
   - Invariant factors: $12$
   - Elementary divisors: $4, 3$

2. $\mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/6\mathbb{Z}$
   - Invariant factors: $2 \mid 6$
   - Elementary divisors: $2, 2, 3$

**확인**: $2 \times 6 = 12$ 
**Total**: 2개의 non-isomorphic abelian groups

## Example 3: $k[x]$-modules (Vector Spaces with Linear Operator)

$V$ finite-dimensional vector space over field $k$

$T: V \to V$ linear operator

$V$는 $k[x]$-module:
- Scalar multiplication: $f(x) \cdot v = f(T)(v)$

**Structure theorem 적용**:

$$V \cong k[x]/(p_1(x)) \oplus \cdots \oplus k[x]/(p_n(x))$$

where $p_1(x) \mid p_2(x) \mid \cdots \mid p_n(x)$

**의미**: $p_n(x)$ = minimal polynomial of $T$

**응용**: Rational Canonical Form^[유리 표준형]

## Example 4: Rational Canonical Form

$T: \mathbb{Q}^5 \to \mathbb{Q}^5$ with invariant factors:
- $d_1(x) = x - 1$
- $d_2(x) = (x-1)(x-2)$
- $d_3(x) = (x-1)^2(x-2)$

**Decomposition**:

$$V \cong \mathbb{Q}[x]/(x-1) \oplus \mathbb{Q}[x]/((x-1)(x-2)) \oplus \mathbb{Q}[x]/((x-1)^2(x-2))$$

**Dimensions**: $1 + 2 + 3 = 6$ (오류 - should be 5)

수정:
- $d_1(x) = x - 2$
- $d_2(x) = (x-1)^2(x-2)$

**Dimensions**: $1 + 4 = 5$ 
## Example 5: Jordan Canonical Form

**특수 경우**: $k$ algebraically closed^[대수적으로 닫힌]

Elementary divisors가 모두 linear:

$$p_i(x) = (x - \lambda_i)^{e_i}$$

**결과**: Jordan blocks

$$V \cong \bigoplus_{i} k[x]/(x - \lambda_i)^{e_i}$$

**Jordan block**: Size $e_i \times e_i$ with eigenvalue $\lambda_i$

## Example 6: Direct Sum of Cyclic Groups

$$\mathbb{Z}/2\mathbb{Z} \oplus \mathbb{Z}/3\mathbb{Z} \oplus \mathbb{Z}/4\mathbb{Z}$$

**Order**: $2 \times 3 \times 4 = 24$

**Invariant factor form으로 변환**:
- Elementary divisors: $2, 3, 4 = 2^2$
- Combine: $\gcd(2, 3, 4) = 1$, $\text{lcm}(2, 3, 4) = 12$
- Invariant factors: $2 \mid 12$

$$G \cong \mathbb{Z}/2\mathbb{Z} \oplus \mathbb{Z}/12\mathbb{Z}$$

**확인**: $2 \times 12 = 24$ 
## Example 7: $\mathbb{Z}[i]$-modules

$\mathbb{Z}[i]$ is PID (Gaussian integers)

Finitely generated $\mathbb{Z}[i]$-module $M$:

$$M \cong \mathbb{Z}[i]^r \oplus \mathbb{Z}[i]/(d_1) \oplus \cdots \oplus \mathbb{Z}[i]/(d_n)$$

where $d_i \in \mathbb{Z}[i]$, $d_1 \mid d_2 \mid \cdots \mid d_n$

**예**: $M = \mathbb{Z}[i]/(3 + 4i)$

## Example 8: Non-example (Not PID)

$\mathbb{Z}[x]$ is **NOT** PID

Structure theorem **does NOT apply** directly!

**반례**: Ideal $\langle 2, x \rangle$ is not principal

$$M = \mathbb{Z}[x] / \langle 2, x \rangle \cong \mathbb{Z}/2\mathbb{Z}$$

as $\mathbb{Z}[x]$-module은 structure theorem 형태가 아님

(하지만 $\mathbb{Z}$-module로는: $\mathbb{Z}/2\mathbb{Z}$ )

---

# <span class="header-properties">Properties</span>

## Torsion Submodule

**정의**: $T(M) = \{m \in M : rm = 0 \text{ for some nonzero } r \in R\}$

**정리**: PID $R$, finitely generated $M$에서:

$$T(M) = R/(d_1) \oplus \cdots \oplus R/(d_n)$$

**Torsion-free part**: $M/T(M) \cong R^r$ (free)

## Rank

**정의**: $\text{rank}(M) = r$ where $M/T(M) \cong R^r$

**Alternative**: Localization at $(0)$:

$$\text{rank}(M) = \dim_{\text{Frac}(R)} (M \otimes_R \text{Frac}(R))$$

**불변량**: Rank는 isomorphism invariant

## Annihilator

**정의**: $\text{Ann}(M) = \{r \in R : rm = 0 \text{ for all } m \in M\}$

**정리**: Torsion module $M = R/(d_1) \oplus \cdots \oplus R/(d_n)$에서:

$$\text{Ann}(M) = \langle d_n \rangle$$

**의미**: Largest invariant factor가 annihilator를 결정

## Order (for Finite Abelian Groups)

$$|G| = n_1 n_2 \cdots n_k$$

where $n_i$ are invariant factors

**Elementary divisor form**:

$$|G| = p_1^{a_1} p_2^{a_2} \cdots p_m^{a_m}$$

## Minimal Generating Set

Finitely generated module $M$:

$$M \cong R^r \oplus R/(d_1) \oplus \cdots \oplus R/(d_n)$$

**Minimal number of generators**: $r + n$

**예**: $\mathbb{Z}^2 \oplus \mathbb{Z}/6\mathbb{Z}$ needs $3$ generators

## Submodules of Free Modules

**정리**: PID $R$, free module $R^n$의 submodule $N$:

$$N \cong R^m$$ 

for some $m \leq n$

**의미**: Submodule of free is free!

---

# <span class="header-remark">Remark</span>

## 응용: Linear Algebra

### Rational Canonical Form

$T: V \to V$ linear operator over field $k$

$V$를 $k[x]$-module로 보면:

**Structure theorem**:

$$V \cong k[x]/(f_1(x)) \oplus \cdots \oplus k[x]/(f_m(x))$$

where $f_1(x) \mid f_2(x) \mid \cdots \mid f_m(x)$

**Invariant factors**: $f_i(x)$

**Minimal polynomial**: $f_m(x)$

**Characteristic polynomial**: $f_1(x) \cdots f_m(x)$

**Matrix form**: Rational canonical form (companion matrices)

### Jordan Canonical Form

$k$ algebraically closed인 경우:

$$f_i(x) = \prod_{j} (x - \lambda_{ij})^{e_{ij}}$$

**Elementary divisors**: $(x - \lambda)^e$

**Jordan blocks**: $e \times e$ block with eigenvalue $\lambda$

**Matrix**: Jordan canonical form

자세한 내용은 [[Rational Canonical Form]], [[Jordan Canonical Form]] 참조

## 응용: Classification Problems

### Finite Abelian Groups

Order $n$인 모든 abelian groups 분류:

1. $n$을 소인수 분해: $n = p_1^{a_1} \cdots p_k^{a_k}$
2. 각 $p_i^{a_i}$의 partitions 찾기
3. Partitions의 곱 = 가능한 groups

**예**: $n = 12 = 2^2 \cdot 3$
- $2^2$: partitions $(2, 2)$, $(4)$ → 2가지
- $3$: partition $(3)$ → 1가지
- Total: $2 \times 1 = 2$ groups

### Modules over $k[x]$

Similarity classes of matrices 분류

**Invariants**: Invariant factors or elementary divisors

## Smith Normal Form Algorithm

**입력**: Matrix $A$ over PID $R$

**출력**: Diagonal matrix $D$ with $d_1 \mid d_2 \mid \cdots$

**방법**:
1. Row/column operations (elementary matrices)
2. Make $(1,1)$ entry minimal
3. Clear row 1 and column 1
4. Recursively apply to $(n-1) \times (m-1)$ submatrix

**결과**: $D = UAV$ for invertible $U, V$

**응용**: Structure theorem 계산

## Computational Aspects

**문제**: Invariant factors 계산

**입력**: Presentation matrix $A$

**알고리즘**:
1. Smith normal form
2. Diagonal entries = invariant factors

**복잡도**: Polynomial time (for $\mathbb{Z}$)

## Historical Context

**개발자**:
- **Frobenius** (1878): Elementary divisors
- **Jordan** (1870): Jordan form
- **Smith** (1861): Smith normal form
- **Kronecker** (1890): General theory

**현대적 접근**: Homological algebra

## Generalizations

### Non-PID Cases

**문제**: Structure theorem fails for general rings!

**대안**:
1. **Dedekind domains**: Ideal class group
2. **Noetherian rings**: Primary decomposition
3. **General rings**: Krull-Schmidt theorem

### Infinitely Generated Modules

**문제**: Structure theorem requires finite generation!

**반례**: $\mathbb{Q}$ as $\mathbb{Z}$-module (divisible group)

$$\mathbb{Q} \not\cong \mathbb{Z}^r \oplus \text{torsion}$$

## Related Theorems

1. **Krull-Schmidt Theorem**: Direct sum decomposition (modules of finite length)
2. **Fundamental Theorem of Algebra**: Special case (companion matrix)
3. **Chinese Remainder Theorem**: Primary decomposition
4. **Sylow Theorems**: $p$-subgroups (non-abelian case와 대조)

자세한 내용은 [[Chinese Remainder Theorem]], [[Krull-Schmidt Theorem]] 참조

## Common Pitfalls

1. **Confusion**: Invariant factors vs elementary divisors
   - 같은 group, 다른 표현!

2. **Domain assumption**: PID 필수!
   - $\mathbb{Z}[x]$는 PID 아님

3. **Finite generation**: 필수 조건
   - $\mathbb{Q}$는 finitely generated $\mathbb{Z}$-module 아님

4. **Uniqueness**: Up to order and units
   - $(2)$와 $(-2)$는 같은 invariant factor

5. **Free part**: May be zero
   - Finite groups: $r = 0$

## Comparison Table

| Theorem | Domain | Objects | Form |
|---------|--------|---------|------|
| Structure Theorem | PID | Finitely generated modules | $R^r \oplus R/(d_i)$ |
| FTFGAG | $\mathbb{Z}$ | Finitely generated abelian groups | $\mathbb{Z}^r \oplus \mathbb{Z}/n_i\mathbb{Z}$ |
| FTFAG | $\mathbb{Z}$ | Finite abelian groups | $\mathbb{Z}/n_i\mathbb{Z}$ |
| RCF | $k[x]$ | Vector spaces + operator | $k[x]/(f_i(x))$ |
| JCF | $k[x]$ ($k$ alg. closed) | Vector spaces + operator | $k[x]/(x-\lambda)^e$ |

**FTFGAG**: Fundamental Theorem of Finitely Generated Abelian Groups

**FTFAG**: Fundamental Theorem of Finite Abelian Groups

**RCF**: Rational Canonical Form

**JCF**: Jordan Canonical Form

