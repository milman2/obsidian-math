# <span class="header-prerequisite">Prerequisite</span>
- [[Ring]]
- [[Group]]
- [[Field]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Lang, Algebra
- Atiyah & Macdonald, Introduction to Commutative Algebra

---

# <span class="header-definition">Definition</span>

## Unit^[단원]

Ring^[환] $R$에서 원소 $u \in R$가 **unit**^[단원] (또는 **invertible element**^[가역원])이다 $\Leftrightarrow$

$$\exists v \in R : uv = vu = 1$$

여기서 $v$를 $u$의 **multiplicative inverse**^[곱셈 역원]라 하고 $u^{-1}$로 표기

## Group of Units^[단원군]

Ring $R$의 **group of units**^[단원군] (또는 **unit group**^[단원군])는:

$$R^\times = \{u \in R : u \text{ is a unit}\}$$

**다른 표기**: $R^*$, $U(R)$, $\text{Units}(R)$

### 군 구조

$(R^\times, \cdot)$는 곱셈에 대한 group:

1. **Closure**^[닫힘]: $u, v \in R^\times \Rightarrow uv \in R^\times$
   - $(uv)(v^{-1}u^{-1}) = u(vv^{-1})u^{-1} = 1$ 
2. **Identity**^[항등원]: $1 \in R^\times$
   - $1 \cdot 1 = 1$ 
3. **Inverse**^[역원]: $u \in R^\times \Rightarrow u^{-1} \in R^\times$
   - $u^{-1}$의 역원은 $u$ 
4. **Associativity**^[결합법칙]: Ring의 곱셈에서 상속 
---

# <span class="header-examples">Examples</span>

## Example 1: Integers^[정수]

$$\mathbb{Z}^\times = \{1, -1\}$$

**이유**: $ab = 1$이고 $a, b \in \mathbb{Z}$ $\Rightarrow$ $a = \pm 1$

**군 구조**: Cyclic group of order 2, $\mathbb{Z}^\times \cong \mathbb{Z}/2\mathbb{Z}$

## Example 2: Rational Numbers^[유리수]

$$\mathbb{Q}^\times = \mathbb{Q} \setminus \{0\}$$

모든 nonzero rational이 역원 가짐 (field이므로)

**군 구조**: Abelian group, not cyclic

$$\mathbb{Q}^\times \cong \mathbb{Z}/2\mathbb{Z} \times \bigoplus_{\text{primes } p} \mathbb{Z}$$

## Example 3: Real Numbers^[실수]

$$\mathbb{R}^\times = \mathbb{R} \setminus \{0\}$$

**부분군**:
- $\mathbb{R}_{>0}^\times = (0, \infty)$ (positive reals)
- $\{-1, 1\} \cong \mathbb{Z}/2\mathbb{Z}$

**분해**: $\mathbb{R}^\times \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{R}_{>0}$

## Example 4: Complex Numbers^[복소수]

$$\mathbb{C}^\times = \mathbb{C} \setminus \{0\}$$

**표현**: $z = re^{i\theta}$ (polar form)

**부분군**:
- $S^1 = \{e^{i\theta} : \theta \in [0, 2\pi)\}$ (unit circle)
- $\mathbb{R}_{>0}^\times$ (positive reals)

**분해**: $\mathbb{C}^\times \cong S^1 \times \mathbb{R}_{>0}$

## Example 5: Modular Arithmetic^[잉여류]

$$(\mathbb{Z}/n\mathbb{Z})^\times = \{[a] : \gcd(a, n) = 1\}$$

**예**: $n = 8$
$$(\mathbb{Z}/8\mathbb{Z})^\times = \{[1], [3], [5], [7]\}$$

**크기**: $|(\mathbb{Z}/n\mathbb{Z})^\times| = \phi(n)$ (Euler's totient function^[오일러 파이 함수])

**군 구조**: 
- $n = p$ (prime): Cyclic, $\cong \mathbb{Z}/(p-1)\mathbb{Z}$
- General $n$: Chinese Remainder Theorem 사용

자세한 내용은 [[Euler's theorem]] 참조

## Example 6: Polynomial Rings^[다항식환]

$$R[x]^\times = R^\times$$

**정리**: 다항식환의 단원 = 상수항이 단원인 상수

**증명**:
- $f(x)g(x) = 1$ for $f, g \in R[x]$
- Degree: $\deg(f) + \deg(g) = 0$
- 따라서 $\deg(f) = \deg(g) = 0$
- $f, g \in R$ (상수)
- $fg = 1$ in $R$ $\Rightarrow$ $f, g \in R^\times$ 
## Example 7: Matrix Rings^[행렬환]

$$M_n(R)^\times = \text{GL}_n(R)$$

General Linear Group^[일반 선형군]

**Field $F$ 위에서**:
$$\text{GL}_n(F) = \{A \in M_n(F) : \det(A) \neq 0\}$$

**부분군**:
- $\text{SL}_n(F) = \{A : \det(A) = 1\}$ (Special Linear Group^[특수 선형군])
- $O_n(\mathbb{R})$ (Orthogonal Group^[직교군])
- $U_n(\mathbb{C})$ (Unitary Group^[유니타리군])

## Example 8: Quaternions^[사원수]

$$\mathbb{H}^\times = \mathbb{H} \setminus \{0\}$$

Hamilton's quaternions^[해밀턴 사원수]

**부분군**: $S^3 = \{q \in \mathbb{H} : |q| = 1\}$ (unit quaternions)

## Example 9: Function Rings

$$C([0,1], \mathbb{R})^\times = \{f : f(x) \neq 0 \; \forall x \in [0,1]\}$$

연속함수 중 어디서도 0이 아닌 것들

---

# <span class="header-properties">Properties</span>

## Basic Properties

### 1. Zero is Never a Unit

$0 \notin R^\times$ (in any ring with $1 \neq 0$)

**이유**: $0 \cdot r = 0 \neq 1$ for all $r$

### 2. One is Always a Unit

$1 \in R^\times$

**이유**: $1 \cdot 1 = 1$

### 3. Units are Closed under Multiplication

$u, v \in R^\times \Rightarrow uv \in R^\times$

$(uv)^{-1} = v^{-1}u^{-1}$

### 4. Inverse is Unique

$u \in R^\times$이면 $u^{-1}$은 유일

**증명**: $uv = uw = 1$이면 $v = 1v = (wu)v = w(uv) = w1 = w$ 
## Field Characterization^[체 특징화]

**정리**: Ring $R$가 field^[체] $\Leftrightarrow$ $R^\times = R \setminus \{0\}$

즉, 0을 제외한 모든 원소가 단원

**증명**:
- ($\Rightarrow$) Field의 정의
- ($\Leftarrow$) 모든 nonzero element가 역원을 가지므로 field 
## Division Ring^[나눗셈환]

Ring with $R^\times = R \setminus \{0\}$ but not necessarily commutative

**예**: Quaternions $\mathbb{H}$

## Integral Domain^[정역]

Integral domain $D$에서:

$$u \in D^\times \Leftrightarrow u \mid 1$$

$u$ divides 1 $\Leftrightarrow$ $u$ is unit

## Size of Unit Group

### For Fields

$$|F^\times| = |F| - 1$$

### For $\mathbb{Z}/n\mathbb{Z}$

$$|(\mathbb{Z}/n\mathbb{Z})^\times| = \phi(n)$$

Euler's totient function

### Chinese Remainder Theorem

$$\mathbb{Z}/mn\mathbb{Z} \cong \mathbb{Z}/m\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$$ when $\gcd(m,n) = 1$

$$\Rightarrow (\mathbb{Z}/mn\mathbb{Z})^\times \cong (\mathbb{Z}/m\mathbb{Z})^\times \times (\mathbb{Z}/n\mathbb{Z})^\times$$

$$\phi(mn) = \phi(m)\phi(n)$$

---

# <span class="header-theorem">Theorem</span>

## Euler's Theorem^[오일러 정리]

$\gcd(a, n) = 1$이면:

$$a^{\phi(n)} \equiv 1 \pmod{n}$$

**증명**: $(\mathbb{Z}/n\mathbb{Z})^\times$는 order $\phi(n)$인 group

Lagrange's Theorem: $[a]^{\phi(n)} = [1]$ 
자세한 내용은 [[Euler's theorem]] 참조

## Fermat's Little Theorem^[페르마 소정리]

$p$ prime, $\gcd(a, p) = 1$:

$$a^{p-1} \equiv 1 \pmod{p}$$

**증명**: Euler's Theorem with $\phi(p) = p-1$ 
## Structure of $(\mathbb{Z}/p\mathbb{Z})^\times$

$p$ prime:

$$(\mathbb{Z}/p\mathbb{Z})^\times \cong \mathbb{Z}/(p-1)\mathbb{Z}$$

**의미**: Cyclic group of order $p-1$

**Primitive root**^[원시근]: Generator of this cyclic group

## Units in Product Rings

$$(R \times S)^\times = R^\times \times S^\times$$

**증명**: $(r, s)$ invertible $\Leftrightarrow$ $r, s$ both invertible 
---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Unit = "나눗셈 가능한 원소"**

Ring에서:
- 덧셈: 항상 가능 (모든 원소가 역원)
- 곱셈: 일부만 가능 (unit만 역원)

**Unit group = "나눗셈 가능한 원소들의 군"**

## Terminology^[용어]

| 영어 | 한국어 | 설명 |
|------|--------|------|
| Unit | 단원 | Invertible element |
| Group of units | 단원군 | Set of all units |
| Unit group | 단원군 | (같은 의미) |
| Multiplicative group | 곱셈군 | (같은 의미) |

## Notation^[표기법]

| 표기 | 의미 | 비고 |
|------|------|------|
| $R^\times$ | Unit group | 가장 일반적 |
| $R^*$ | Unit group | 때로 사용 |
| $U(R)$ | Unit group | Dummit & Foote |
| $\text{GL}_n(R)$ | $M_n(R)^\times$ | Matrix case |

**주의**: $R^*$는 때로 $R \setminus \{0\}$를 의미하기도 함 (혼동 주의!)

## Applications^[응용]

### Number Theory^[정수론]

**Modular arithmetic**:
- RSA cryptography: $(\mathbb{Z}/n\mathbb{Z})^\times$
- Primitive roots modulo $p$
- Quadratic residues

### Algebraic Geometry^[대수기하]

**Sheaf of units**: $\mathcal{O}_X^\times$

**Picard group**: $\text{Pic}(X) = H^1(X, \mathcal{O}_X^\times)$

### Group Theory^[군론]

**Example of groups**: Finite abelian groups

**Structure theory**: Classification via CRT

### Ring Theory^[환론]

**Local rings**: $R$ local $\Leftrightarrow$ $R \setminus R^\times$ is an ideal

**Dedekind domains**: Units in number fields

## Computing Unit Groups

### Strategy for $(\mathbb{Z}/n\mathbb{Z})^\times$

1. **Prime power**: $n = p^k$
   - $|(\mathbb{Z}/p^k\mathbb{Z})^\times| = p^{k-1}(p-1)$
   - Structure: depends on $p$ (cyclic for odd $p$)

2. **General $n$**: Factor $n = p_1^{k_1} \cdots p_r^{k_r}$
   - CRT: $(\mathbb{Z}/n\mathbb{Z})^\times \cong \prod (\mathbb{Z}/p_i^{k_i}\mathbb{Z})^\times$

### Example: $n = 360 = 2^3 \cdot 3^2 \cdot 5$

$$(\mathbb{Z}/360\mathbb{Z})^\times \cong (\mathbb{Z}/8\mathbb{Z})^\times \times (\mathbb{Z}/9\mathbb{Z})^\times \times (\mathbb{Z}/5\mathbb{Z})^\times$$

$$\cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/6\mathbb{Z} \times \mathbb{Z}/4\mathbb{Z}$$

$$\phi(360) = 4 \cdot 6 \cdot 4 = 96$$

## Historical Note

**Leonhard Euler** (1707-1783):
- Euler's totient function $\phi(n)$
- Euler's theorem

**Carl Friedrich Gauss** (1777-1855):
- Primitive roots
- Structure of $(\mathbb{Z}/p\mathbb{Z})^\times$

**Pierre de Fermat** (1607-1665):
- Fermat's little theorem

## Common Mistakes^[흔한 실수]

### 1. Zero as unit

✗ $0 \in R^\times$ (never!)

### 2. Additive vs Multiplicative

$R^\times$ is **multiplicative** group (not additive)

### 3. Field test

$R^\times = R \setminus \{0\}$ $\Rightarrow$ $R$ is field (only if commutative!)

Non-commutative: Division ring

### 4. $R^*$ notation

$R^*$ can mean:
- Unit group $R^\times$ - Nonzero elements $R \setminus \{0\}$ (less common)

Context matters!

## Related Concepts

- [[Ring]]: Basic structure
- [[Field]]: $F^\times = F \setminus \{0\}$
- [[Group]]: $(R^\times, \cdot)$ is a group
- [[Euler's theorem]]: $a^{\phi(n)} \equiv 1 \pmod{n}$
- [[Homomorphism]]: Unit-preserving maps

## Further Topics

**Advanced**:
- Dirichlet's unit theorem (number fields)
- Class groups and ideal class groups
- $K$-theory ($K_1(R) = R^\times / [R^\times, R^\times]$)
- Brauer groups

