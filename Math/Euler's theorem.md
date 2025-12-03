# <span class="header-prerequisite">Prerequisite</span>
- [[Group]]
- [[Cyclic Group]]
- [[Lagrange's theorem]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Ireland & Rosen, A Classical Introduction to Modern Number Theory
- Apostol, Introduction to Analytic Number Theory

---

# <span class="header-definition">Definition</span>

## Euler's Theorem^[오일러 정리]

**정리**: $\gcd(a, n) = 1$이면

$$a^{\phi(n)} \equiv 1 \pmod{n}$$

where $\phi(n)$ = Euler's totient function^[오일러 파이 함수]

### Euler's Totient Function^[오일러 파이 함수]

$$\phi(n) = |\{k : 1 \leq k \leq n, \gcd(k, n) = 1\}|$$

**의미**: $n$과 서로소인 $1$부터 $n$까지 정수의 개수

**Alternative**: $\phi(n) = |(\mathbb{Z}/n\mathbb{Z})^\times|$ (units in $\mathbb{Z}/n\mathbb{Z}$)

## Fermat's Little Theorem^[페르마의 소정리]

**특수 경우**: $n = p$ (prime)

$$\phi(p) = p - 1$$

$$\gcd(a, p) = 1 \Rightarrow a^{p-1} \equiv 1 \pmod{p}$$

**또는**: $a^p \equiv a \pmod{p}$ for all $a$

**Euler's theorem의 특수 경우**

---

# <span class="header-proof">Proof</span>

## Group Theory Proof

### Multiplicative Group

$$(\mathbb{Z}/n\mathbb{Z})^\times = \{[a] : \gcd(a, n) = 1\}$$

**연산**: 곱셈 modulo $n$

**Group 확인**:
- **Closure**: $\gcd(a,n) = \gcd(b,n) = 1 \Rightarrow \gcd(ab,n) = 1$
- **Associativity**: 곱셈은 associative
- **Identity**: $[1]$
- **Inverse**: Bézout's identity로 존재 
**Order**: $|(\mathbb{Z}/n\mathbb{Z})^\times| = \phi(n)$

### Lagrange's Theorem 적용

$G = (\mathbb{Z}/n\mathbb{Z})^\times$, $|G| = \phi(n)$

$[a] \in G$에 대해 Lagrange's theorem:

$$|[a]| \mid \phi(n)$$

따라서:

$$[a]^{\phi(n)} = [1]$$

즉:

$$a^{\phi(n)} \equiv 1 \pmod{n}$$ 
자세한 내용은 [[Lagrange's theorem]] 참조

## Direct Proof (Elementary)

$\gcd(a, n) = 1$일 때, $\{a, 2a, 3a, \ldots, \phi(n) \cdot a\}$ (mod $n$)

Let $S = \{r_1, r_2, \ldots, r_{\phi(n)}\}$ = 모든 $n$과 서로소인 residues

**주장**: $\{ar_1, ar_2, \ldots, ar_{\phi(n)}\}$ (mod $n$) = $S$의 permutation

**증명**:
1. $\gcd(ar_i, n) = 1$ (since $\gcd(a,n) = \gcd(r_i,n) = 1$) 2. $ar_i \equiv ar_j \pmod{n} \Rightarrow r_i \equiv r_j \pmod{n}$ (cancel $a$) 
따라서:

$$(ar_1)(ar_2)\cdots(ar_{\phi(n)}) \equiv r_1 r_2 \cdots r_{\phi(n)} \pmod{n}$$

$$a^{\phi(n)} (r_1 r_2 \cdots r_{\phi(n)}) \equiv r_1 r_2 \cdots r_{\phi(n)} \pmod{n}$$

$\gcd(r_1 r_2 \cdots r_{\phi(n)}, n) = 1$이므로 cancel:

$$a^{\phi(n)} \equiv 1 \pmod{n}$$ 
---

# <span class="header-examples">Examples</span>

## Example 1: $n = 10$

$$\phi(10) = |\{1, 3, 7, 9\}| = 4$$

**Euler's theorem**: $\gcd(a, 10) = 1 \Rightarrow a^4 \equiv 1 \pmod{10}$

**확인**:
- $3^4 = 81 \equiv 1 \pmod{10}$ - $7^4 = 2401 \equiv 1 \pmod{10}$ - $9^4 = 6561 \equiv 1 \pmod{10}$ 
## Example 2: Fermat's Little Theorem ($n = 7$)

$$\phi(7) = 6$$

**Euler's theorem**: $\gcd(a, 7) = 1 \Rightarrow a^6 \equiv 1 \pmod{7}$

**확인** ($a = 2$):
$$2^6 = 64 = 9 \cdot 7 + 1 \equiv 1 \pmod{7}$$ 
## Example 3: $n = 15$

$$\phi(15) = \phi(3 \cdot 5) = \phi(3) \cdot \phi(5) = 2 \cdot 4 = 8$$

**Euler's theorem**: $\gcd(a, 15) = 1 \Rightarrow a^8 \equiv 1 \pmod{15}$

**확인** ($a = 2$):
$$2^8 = 256 = 17 \cdot 15 + 1 \equiv 1 \pmod{15}$$ 
## Example 4: Computing Large Powers

**문제**: $7^{222} \pmod{10}$ 계산

**풀이**:
- $\gcd(7, 10) = 1$ - $\phi(10) = 4$
- $222 = 55 \cdot 4 + 2$

$$7^{222} = (7^4)^{55} \cdot 7^2 \equiv 1^{55} \cdot 49 \equiv 9 \pmod{10}$$

**답**: $7^{222} \equiv 9 \pmod{10}$

## Example 5: RSA Cryptography

**RSA 기본**: $n = pq$ (두 소수의 곱)

$$\phi(n) = (p-1)(q-1)$$

**Encryption**: $c \equiv m^e \pmod{n}$

**Decryption**: $m \equiv c^d \pmod{n}$ where $ed \equiv 1 \pmod{\phi(n)}$

**작동 원리**: Euler's theorem!

$$c^d \equiv (m^e)^d = m^{ed} = m^{1 + k\phi(n)} = m \cdot (m^{\phi(n)})^k \equiv m \pmod{n}$$

---

# <span class="header-properties">Properties</span>

## Euler's Totient Function Properties

### 1. Multiplicative Function

$\gcd(m, n) = 1 \Rightarrow \phi(mn) = \phi(m) \phi(n)$

**증명**: Chinese Remainder Theorem

$$(\mathbb{Z}/mn\mathbb{Z})^\times \cong (\mathbb{Z}/m\mathbb{Z})^\times \times (\mathbb{Z}/n\mathbb{Z})^\times$$

### 2. Prime Powers

$$\phi(p^k) = p^k - p^{k-1} = p^{k-1}(p-1)$$

**증명**: $p$의 배수들만 서로소가 아님

$p, 2p, 3p, \ldots, p^{k-1}p$ = $p^{k-1}$개

따라서 $\phi(p^k) = p^k - p^{k-1}$ 
### 3. Formula from Prime Factorization

$$n = p_1^{a_1} p_2^{a_2} \cdots p_k^{a_k}$$

$$\phi(n) = n \prod_{p \mid n} \left(1 - \frac{1}{p}\right) = n \left(1 - \frac{1}{p_1}\right)\left(1 - \frac{1}{p_2}\right) \cdots \left(1 - \frac{1}{p_k}\right)$$

**예**: $n = 12 = 2^2 \cdot 3$

$$\phi(12) = 12 \left(1 - \frac{1}{2}\right)\left(1 - \frac{1}{3}\right) = 12 \cdot \frac{1}{2} \cdot \frac{2}{3} = 4$$

### 4. Sum over Divisors

$$\sum_{d \mid n} \phi(d) = n$$

**예**: $n = 6$, divisors: $1, 2, 3, 6$

$$\phi(1) + \phi(2) + \phi(3) + \phi(6) = 1 + 1 + 2 + 2 = 6$$ 
### 5. Values

| $n$ | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 12 | 15 | 16 |
|-----|---|---|---|---|---|---|---|---|---|----|----|----|-----|
| $\phi(n)$ | 1 | 1 | 2 | 2 | 4 | 2 | 6 | 4 | 6 | 4 | 4 | 8 | 8 |

## Generalizations

### Carmichael's Function^[카마이클 함수]

$$\lambda(n) = \text{lcm of orders in } (\mathbb{Z}/n\mathbb{Z})^\times$$

**성질**: $\lambda(n) \mid \phi(n)$

**Stronger result**: $a^{\lambda(n)} \equiv 1 \pmod{n}$ (smaller exponent!)

### Order of Element

Element $[a] \in (\mathbb{Z}/n\mathbb{Z})^\times$의 **order**^[위수]:

$$\text{ord}_n(a) = \min\{k > 0 : a^k \equiv 1 \pmod{n}\}$$

**Lagrange**: $\text{ord}_n(a) \mid \phi(n)$

자세한 내용은 [[Cyclic Group]] 참조

## Primitive Roots^[원시근]

$\text{ord}_n(a) = \phi(n)$일 때 $a$를 **primitive root** modulo $n$

**의미**: $(\mathbb{Z}/n\mathbb{Z})^\times = \langle [a] \rangle$ (cyclic)

**Existence**: Primitive root exists $\Leftrightarrow$ $n = 1, 2, 4, p^k, 2p^k$ (where $p$ odd prime)

**예**: 
- $n = 7$: $\phi(7) = 6$, primitive root = $3$ (since $\text{ord}_7(3) = 6$)
- $n = 8$: No primitive root ($(\mathbb{Z}/8\mathbb{Z})^\times \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/2\mathbb{Z}$)

---

# <span class="header-theorem">Theorem</span>

## Chinese Remainder Theorem

$\gcd(m, n) = 1$일 때:

$$\mathbb{Z}/mn\mathbb{Z} \cong \mathbb{Z}/m\mathbb{Z} \times \mathbb{Z}/n\mathbb{Z}$$

**Units**:

$$(\mathbb{Z}/mn\mathbb{Z})^\times \cong (\mathbb{Z}/m\mathbb{Z})^\times \times (\mathbb{Z}/n\mathbb{Z})^\times$$

**따라서**: $\phi(mn) = \phi(m) \phi(n)$ 
## Wilson's Theorem

$$p \text{ prime} \Rightarrow (p-1)! \equiv -1 \pmod{p}$$

**연결**: Product of all units in $(\mathbb{Z}/p\mathbb{Z})^\times$

## Fermat's Two-Square Theorem

Prime $p$가 두 제곱수의 합으로 표현 가능:

$$p = a^2 + b^2 \Leftrightarrow p = 2 \text{ or } p \equiv 1 \pmod{4}$$

**증명에 Euler's theorem 사용**

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Euler's Theorem = "Units의 Lagrange's theorem"**

### 메타포: 순환

$\gcd(a, n) = 1$이면 $a$를 반복 곱하면:

$$a, a^2, a^3, \ldots, a^{\phi(n)} \equiv 1$$

**순환**: 최대 $\phi(n)$ 번이면 $1$로 돌아옴

### 메타포: 시계

**시계**: 12시간 후 같은 위치

**Modular arithmetic**: $a^{\phi(n)}$ 후 $1$로

## 왜 중요한가?

### 1. Modular Exponentiation

**큰 거듭제곱 계산**:

$$a^N \equiv a^{N \bmod \phi(n)} \pmod{n}$$

(when $\gcd(a,n) = 1$)

**응용**: 계산 효율성 ↑

### 2. Cryptography

**RSA**: Euler's theorem 기반

**Public key cryptography**: Modular arithmetic의 어려움

**Security**: Factoring $n$의 어려움 = $\phi(n)$ 계산의 어려움

### 3. Number Theory

**Diophantine equations**: $x^k \equiv a \pmod{n}$ 해 존재성

**Quadratic reciprocity**: Euler's criterion

**Primitive roots**: Cyclic structure

### 4. Group Theory 연결

**Abstract algebra** ↔ **Number theory**

Groups → Modular arithmetic

## Euler vs Fermat

| | **Fermat** | **Euler** |
|---|---|---|
| **조건** | $p$ prime | $n$ any |
| **Exponent** | $p-1$ | $\phi(n)$ |
| **일반성** | Special case | General |
| **증명** | Elementary | Group theory |

**Fermat = Euler when $n = p$**

## 계산 팁

### $\phi(n)$ 빠르게 계산

1. **Prime factorization**: $n = p_1^{a_1} \cdots p_k^{a_k}$
2. **Formula**: $\phi(n) = n \prod (1 - 1/p_i)$

**예**: $n = 100 = 2^2 \cdot 5^2$

$$\phi(100) = 100 \left(1 - \frac{1}{2}\right)\left(1 - \frac{1}{5}\right) = 100 \cdot \frac{1}{2} \cdot \frac{4}{5} = 40$$

### Large Power Modulo $n$

**Step 1**: Compute $\phi(n)$

**Step 2**: Reduce exponent: $N \mapsto N \bmod \phi(n)$

**Step 3**: Compute $a^{N \bmod \phi(n)} \pmod{n}$

## 응용: RSA 예시

**Setup**:
- $p = 61, q = 53$ (primes)
- $n = pq = 3233$
- $\phi(n) = 60 \cdot 52 = 3120$
- $e = 17$ (public exponent, $\gcd(e, \phi(n)) = 1$)
- $d = 2753$ (private exponent, $ed \equiv 1 \pmod{\phi(n)}$)

**Encryption**: $m = 123$
$$c = 123^{17} \bmod 3233 = 855$$

**Decryption**: 
$$m = 855^{2753} \bmod 3233 = 123$$ 
**Why it works**: Euler's theorem!

## 역사적 배경

**Leonhard Euler** (1707-1783):
- 스위스 수학자
- 1736: Euler's totient function 도입
- 1763: Euler's theorem 증명
- Fermat's theorem 일반화

**이전**:
- Fermat (1640): Fermat's Little Theorem (without proof)

**이후**:
- Gauss (1801): Primitive roots, Quadratic reciprocity
- Modern: Group theory로 재해석

## 표기법

| 표기 | 의미 |
|------|------|
| $\phi(n)$ | Euler's totient function |
| $\lambda(n)$ | Carmichael function |
| $\text{ord}_n(a)$ | Order of $a$ modulo $n$ |
| $(\mathbb{Z}/n\mathbb{Z})^\times$ | Units modulo $n$ |
| $a \equiv b \pmod{n}$ | $a$ congruent to $b$ modulo $n$ |

## Common Pitfall^[흔한 실수]

### 1. $\gcd(a, n) = 1$ 필수!

$\gcd(a, n) \neq 1$이면 Euler's theorem 적용 안 됨

**예**: $2^{\phi(10)} = 2^4 = 16 \not\equiv 1 \pmod{10}$ (하지만 $\gcd(2,10) = 2 \neq 1$)

### 2. $\phi(n)$이 minimal exponent 아님

$a^{\phi(n)} \equiv 1$이지만, 더 작은 exponent 가능

**Order**: $\text{ord}_n(a) \mid \phi(n)$ (smaller divisor 가능)

### 3. Fermat $\neq$ Primality test

$a^{n-1} \equiv 1 \pmod{n}$ $\not\Rightarrow$ $n$ prime

**Carmichael numbers**: Composite but satisfy Fermat for all $a$

### 4. $\phi(mn) = \phi(m)\phi(n)$?

Only if $\gcd(m,n) = 1$!

**예**: $\phi(4 \cdot 6) = \phi(24) = 8 \neq \phi(4)\phi(6) = 2 \cdot 2 = 4$

### 5. Power reduction

$a^N \equiv a^{N \bmod \phi(n)} \pmod{n}$ only when $\gcd(a,n) = 1$

## 관련 개념

- [[Lagrange's theorem]]: Group theory foundation
- [[Group]]: $(\mathbb{Z}/n\mathbb{Z})^\times$ structure
- [[Cyclic Group]]: Primitive roots
- [[Chinese Remainder Theorem]]: $\phi$ multiplicativity
- [[Fermat's Little Theorem]]: Special case

## 추가 학습 주제

**기초**:
- Euler's totient function
- Modular arithmetic
- Fermat's Little Theorem

**중급**:
- Primitive roots
- Carmichael function
- RSA cryptography

**고급**:
- Quadratic reciprocity
- Dirichlet characters
- Analytic number theory

