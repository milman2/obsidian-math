# <span class="header-prerequisite">Prerequisite</span>
- [[Real Numbers]]
- [[Function]]
- [[Set Theory]]

# <span class="header-reference">Reference</span>
- Rudin, Principles of Mathematical Analysis
- Abbott, Understanding Analysis
- Tao, Analysis I
- Apostol, Mathematical Analysis

---

# <span class="header-definition">Definition</span>

## Sequence^[수열]

**Sequence**^[수열]는 자연수 집합에서 어떤 집합으로의 함수이다:

$$a: \mathbb{N} \to X$$

**표기**: 
- $a(n)$ 대신 $a_n$으로 쓰고, 수열 전체는 $(a_n)_{n=1}^{\infty}$ 또는 간단히 $(a_n)$으로 표기
- 때로는 $\{a_n\}_{n=1}^{\infty}$ 또는 $\langle a_n \rangle$으로도 표기 (집합과 구분 필요)

**용어**:
- $a_n$: **$n$번째 항**^[term] 또는 **일반항**^[general term]
- $n$: **Index**^[지표]

**시작 지표**: 관례상 $n = 1$부터 시작하지만, $n = 0$ 또는 다른 값부터 시작할 수도 있음

### Finite Sequence^[유한 수열]

유한 개의 항만 있는 수열: $(a_1, a_2, \ldots, a_n)$

함수 $a: \{1, 2, \ldots, n\} \to X$

### Infinite Sequence^[무한 수열]

무한히 많은 항이 있는 수열 (일반적으로 "수열"이라 하면 무한수열을 의미)

## Real Sequence^[실수 수열]

$a: \mathbb{N} \to \mathbb{R}$인 수열

**예**: $(1, 2, 3, 4, \ldots)$, $(1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \ldots)$

## Sequence in Metric Space^[거리공간에서의 수열]

Metric space^[거리 공간] $(X, d)$에서 $a: \mathbb{N} \to X$

**일반화**: Topological space^[위상공간]에서도 정의 가능

---

# <span class="header-properties">Properties</span>

## Boundedness^[유계성]

### Bounded Above^[위로 유계]

실수 수열 $(a_n)$이 **bounded above**^[위로 유계]이다 $\Leftrightarrow$

$$\exists M \in \mathbb{R} \text{ such that } a_n \leq M \text{ for all } n \in \mathbb{N}$$

$M$을 **upper bound**^[상계]라 함

### Bounded Below^[아래로 유계]

실수 수열 $(a_n)$이 **bounded below**^[아래로 유계]이다 $\Leftrightarrow$

$$\exists m \in \mathbb{R} \text{ such that } a_n \geq m \text{ for all } n \in \mathbb{N}$$

$m$을 **lower bound**^[하계]라 함

### Bounded^[유계]

수열 $(a_n)$이 **bounded**^[유계]이다 $\Leftrightarrow$ bounded above이고 bounded below

**동등 조건**: $\exists M > 0$ such that $|a_n| \leq M$ for all $n$

**Metric space에서**: $(x_n) \subseteq X$가 bounded $\Leftrightarrow$ $\exists x_0 \in X, \exists R > 0$ such that $d(x_n, x_0) \leq R$ for all $n$

## Monotonicity^[단조성]

### Monotone Increasing^[단조증가]

실수 수열 $(a_n)$이 **monotone increasing**^[단조증가] (또는 **non-decreasing**^[비감소])이다 $\Leftrightarrow$

$$a_n \leq a_{n+1} \text{ for all } n \in \mathbb{N}$$

### Strictly Increasing^[순증가]

$$a_n < a_{n+1} \text{ for all } n \in \mathbb{N}$$

### Monotone Decreasing^[단조감소]

실수 수열 $(a_n)$이 **monotone decreasing**^[단조감소] (또는 **non-increasing**^[비증가])이다 $\Leftrightarrow$

$$a_n \geq a_{n+1} \text{ for all } n \in \mathbb{N}$$

### Strictly Decreasing^[순감소]

$$a_n > a_{n+1} \text{ for all } n \in \mathbb{N}$$

### Monotone^[단조]

수열이 **monotone**^[단조]이다 $\Leftrightarrow$ monotone increasing 또는 monotone decreasing

## Subsequence^[부분수열]

### Definition

수열 $(a_n)$의 **subsequence**^[부분수열]는 strictly increasing^[순증가] 함수 $n_k: \mathbb{N} \to \mathbb{N}$에 대해:

$$(a_{n_k})_{k=1}^{\infty} = (a_{n_1}, a_{n_2}, a_{n_3}, \ldots)$$

where $n_1 < n_2 < n_3 < \cdots$

**표기**: $(a_{n_k})$ 또는 간단히 $(a_k')$

**의미**: 원래 수열에서 일부 항을 순서를 유지하며 선택

### Properties

1. 모든 수열은 자기 자신의 subsequence
2. Subsequence의 subsequence는 원래 수열의 subsequence
3. $n_k \geq k$ for all $k$ (적어도 $k$번째 항 이상)

**예**: $(1, 2, 3, 4, 5, \ldots)$의 subsequence
- $(2, 4, 6, 8, \ldots)$ (짝수 항)
- $(1, 3, 5, 7, \ldots)$ (홀수 항)
- $(1, 4, 9, 16, \ldots)$ (제곱수 항)

## Eventually^[궁극적으로]

수열 $(a_n)$이 어떤 성질 $P$를 **eventually**^[궁극적으로] 만족한다 $\Leftrightarrow$

$$\exists N \in \mathbb{N} \text{ such that } P(a_n) \text{ is true for all } n \geq N$$

**의미**: "충분히 큰 $n$에 대해" 성질이 성립

**예**:
- $(a_n)$이 eventually positive: $\exists N$ such that $a_n > 0$ for all $n \geq N$
- $(a_n)$이 eventually bounded: $\exists N$ such that $|a_n| \leq M$ for all $n \geq N$

## Frequently^[자주]

수열 $(a_n)$이 어떤 성질 $P$를 **frequently**^[자주] 만족한다 $\Leftrightarrow$

무한히 많은 $n$에 대해 $P(a_n)$이 참

**동등 조건**: 모든 $N \in \mathbb{N}$에 대해 $\exists n \geq N$ such that $P(a_n)$

**예**: $a_n = (-1)^n$은 frequently positive (홀수 항에서)

---

# <span class="header-examples">Examples</span>

## Example 1: Constant Sequence^[상수 수열]

$$a_n = c \text{ for all } n$$

**예**: $(5, 5, 5, 5, \ldots)$

**성질**:
- Bounded
- Monotone (both increasing and decreasing)
- 수렴: $\lim a_n = c$

## Example 2: Arithmetic Sequence^[등차수열]

$$a_n = a_1 + (n-1)d$$

where $a_1$ = 첫째 항, $d$ = 공차^[common difference]

**예**: 
- $(1, 3, 5, 7, 9, \ldots)$ with $a_1 = 1$, $d = 2$
- $(10, 7, 4, 1, -2, \ldots)$ with $a_1 = 10$, $d = -3$

**성질**:
- $d > 0$: Strictly increasing, unbounded
- $d < 0$: Strictly decreasing, unbounded
- $d = 0$: Constant

## Example 3: Geometric Sequence^[등비수열]

$$a_n = a_1 \cdot r^{n-1}$$

where $a_1$ = 첫째 항, $r$ = 공비^[common ratio]

**예**:
- $(2, 6, 18, 54, \ldots)$ with $a_1 = 2$, $r = 3$
- $(1, \frac{1}{2}, \frac{1}{4}, \frac{1}{8}, \ldots)$ with $a_1 = 1$, $r = \frac{1}{2}$

**수렴 조건**:
- $|r| < 1$: 수렴 to 0
- $r = 1$: 수렴 to $a_1$
- $|r| > 1$: 발산
- $r = -1$: 진동

## Example 4: Harmonic Sequence^[조화수열]

$$a_n = \frac{1}{n}$$

수열: $\left(1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \ldots\right)$

**성질**:
- Strictly decreasing
- Bounded: $0 < a_n \leq 1$
- 수렴: $\lim a_n = 0$

## Example 5: Factorial Sequence^[팩토리얼 수열]

$$a_n = n! = 1 \cdot 2 \cdot 3 \cdots n$$

수열: $(1, 2, 6, 24, 120, 720, \ldots)$

**성질**:
- Strictly increasing
- Unbounded
- 발산: $\lim a_n = +\infty$

## Example 6: Fibonacci Sequence^[피보나치 수열]

재귀적 정의^[recursive definition]:

$$a_1 = 1, \quad a_2 = 1, \quad a_n = a_{n-1} + a_{n-2} \text{ for } n \geq 3$$

수열: $(1, 1, 2, 3, 5, 8, 13, 21, 34, \ldots)$

**성질**:
- Eventually strictly increasing
- Unbounded
- Golden ratio와 관련: $\frac{a_{n+1}}{a_n} \to \phi = \frac{1+\sqrt{5}}{2}$

## Example 7: Alternating Sequence^[교대수열]

$$a_n = (-1)^n$$

수열: $(-1, 1, -1, 1, -1, \ldots)$

**성질**:
- Bounded: $|a_n| = 1$
- Not monotone
- 발산 (진동)

## Example 8: Power Sequence^[거듭제곱 수열]

$$a_n = n^p$$

where $p \in \mathbb{R}$

**경우**:
- $p > 0$: Strictly increasing, unbounded
- $p = 0$: Constant (= 1)
- $p < 0$: Strictly decreasing, bounded, 수렴 to 0

**예**: 
- $a_n = n^2$: $(1, 4, 9, 16, 25, \ldots)$
- $a_n = n^{-1}$: $(1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, \ldots)$

## Example 9: Exponential Sequence^[지수수열]

$$a_n = r^n$$

where $r > 0$

**경우**:
- $r > 1$: Strictly increasing, unbounded
- $r = 1$: Constant
- $0 < r < 1$: Strictly decreasing, 수렴 to 0

**예**: $a_n = 2^n$: $(2, 4, 8, 16, 32, \ldots)$

## Example 10: Sequence Defined by Function^[함수로 정의된 수열]

$$a_n = f(n)$$

where $f: \mathbb{R} \to \mathbb{R}$

**예**:
- $a_n = \sin(n)$: bounded but not monotone
- $a_n = \frac{n}{n+1}$: strictly increasing, bounded, 수렴 to 1
- $a_n = \frac{\sin n}{n}$: 수렴 to 0

---

# <span class="header-theorem">Operations on Sequences</span>

## Arithmetic Operations^[산술 연산]

수열 $(a_n)$, $(b_n)$과 상수 $c \in \mathbb{R}$에 대해:

### Addition^[덧셈]

$$(a_n + b_n) = (a_1 + b_1, a_2 + b_2, a_3 + b_3, \ldots)$$

### Scalar Multiplication^[스칼라곱]

$$(c \cdot a_n) = (c \cdot a_1, c \cdot a_2, c \cdot a_3, \ldots)$$

### Multiplication^[곱셈]

$$(a_n \cdot b_n) = (a_1 \cdot b_1, a_2 \cdot b_2, a_3 \cdot b_3, \ldots)$$

### Division^[나눗셈]

$$\left(\frac{a_n}{b_n}\right) = \left(\frac{a_1}{b_1}, \frac{a_2}{b_2}, \frac{a_3}{b_3}, \ldots\right)$$

(단, $b_n \neq 0$ for all $n$)

**주의**: 이러한 연산들은 term-wise^[항별]로 수행됨

## Supremum and Infimum^[상한과 하한]

Bounded 실수 수열 $(a_n)$에 대해:

### Supremum^[상한]

$$\sup\{a_n : n \in \mathbb{N}\} = \text{least upper bound}$$

### Infimum^[하한]

$$\inf\{a_n : n \in \mathbb{N}\} = \text{greatest lower bound}$$

**성질**:
- Monotone increasing이면: $\sup\{a_n\} = \lim_{n \to \infty} a_n$ (if convergent) 또는 $+\infty$
- Monotone decreasing이면: $\inf\{a_n\} = \lim_{n \to \infty} a_n$ (if convergent) 또는 $-\infty$

## Limit Superior and Limit Inferior^[상극한과 하극한]

Bounded 실수 수열 $(a_n)$에 대해:

### Limit Superior^[상극한]

$$\limsup_{n \to \infty} a_n = \lim_{n \to \infty} \left(\sup_{k \geq n} a_k\right) = \inf_{n} \sup_{k \geq n} a_k$$

### Limit Inferior^[하극한]

$$\liminf_{n \to \infty} a_n = \lim_{n \to \infty} \left(\inf_{k \geq n} a_k\right) = \sup_{n} \inf_{k \geq n} a_k$$

**성질**:
1. $\liminf a_n \leq \limsup a_n$ (항상)
2. $\lim a_n$ 존재 $\Leftrightarrow$ $\liminf a_n = \limsup a_n$
3. 이 경우 $\lim a_n = \limsup a_n = \liminf a_n$

**의미**:
- $\limsup a_n$: 수열이 infinitely often 접근하는 가장 큰 값
- $\liminf a_n$: 수열이 infinitely often 접근하는 가장 작은 값

자세한 내용은 [[Convergence and Divergence in Sequences]] 참조

---

# <span class="header-remark">Remark</span>

## Notation^[표기법]

### $(a_n)$ vs $\{a_n\}$ vs $\langle a_n \rangle$

**$(a_n)$**: 가장 표준적 (순서 강조)
- Sequence는 ordered list

**$\{a_n\}$**: 때로 사용하지만 집합과 혼동 가능
- 집합: $\{1, 2, 3\} = \{3, 2, 1\}$ (순서 무관)
- 수열: $(1, 2, 3) \neq (3, 2, 1)$ (순서 중요!)

**$\langle a_n \rangle$**: 일부 저자가 사용 (순서 강조)

**권장**: **$(a_n)$** 사용

### Indexing

**표준**: $n = 1, 2, 3, \ldots$ (자연수)

**변형**:
- $n = 0, 1, 2, \ldots$ (0부터 시작)
- $n = k, k+1, k+2, \ldots$ (임의의 시작점)
- $n \in \mathbb{Z}$ (양방향 무한 수열)

## Sequence vs Series^[수열 vs 급수]

**Sequence**^[수열]: $(a_1, a_2, a_3, \ldots)$
- 개별 항들의 나열

**Series**^[급수]: $\sum_{n=1}^{\infty} a_n$
- 수열의 부분합^[partial sum]의 수열

**연결**: Series $(s_n)$는 partial sum sequence
$$s_n = a_1 + a_2 + \cdots + a_n = \sum_{k=1}^{n} a_k$$

자세한 내용은 [[Series]] 참조

## Function Perspective^[함수 관점]

**Sequence = Discrete function**

수열 $(a_n)$은 함수 $a: \mathbb{N} \to \mathbb{R}$

**비교**:
- **Continuous function**: $f: \mathbb{R} \to \mathbb{R}$
- **Sequence**: $a: \mathbb{N} \to \mathbb{R}$ (discrete domain)

**도표화**: Sequence는 discrete points $(n, a_n)$의 집합

## 직관적 이해

**Sequence**: "무한한 리스트"

**시각화**:
- 수평선상의 점들
- 그래프에서 discrete points

**응용**:
- 근사 (approximation)
- 반복법 (iteration)
- 극한 과정 모델링

## Recursive vs Explicit Definition^[재귀적 vs 명시적 정의]

### Explicit Formula^[명시적 공식]

$$a_n = f(n)$$

직접 $n$으로부터 $a_n$ 계산

**예**: $a_n = 2n + 1$

### Recursive Formula^[재귀적 공식]

$$a_n = g(a_{n-1}, a_{n-2}, \ldots)$$

이전 항들로부터 $a_n$ 계산

**예**: Fibonacci: $a_n = a_{n-1} + a_{n-2}$

**장단점**:
- Explicit: 계산 간편, 분석 용이
- Recursive: 자연스러운 정의, explicit formula 없을 수 있음

## 역사적 배경

**고대**: 
- 그리스 수학자들의 무한 과정 (Zeno's paradoxes)
- 기하급수의 합

**근대**:
- **Newton, Leibniz**: 무한급수와 미적분
- **Cauchy**: 수열의 엄밀한 정의와 수렴 개념

**현대**:
- **Weierstrass**: $\epsilon$-$N$ 정의
- Sequence는 해석학의 기초

## 응용 분야

### 1. Numerical Analysis^[수치해석]

반복법으로 근 찾기:
- Newton's method
- Fixed point iteration

수열 $(x_n)$이 해로 수렴

### 2. Approximation Theory^[근사 이론]

함수의 근사:
- Taylor series
- Fourier series

유한 항의 합으로 근사

### 3. Probability Theory^[확률론]

확률 수열:
- Random walk
- Markov chains
- Law of Large Numbers

### 4. Dynamical Systems^[역학계]

$$x_{n+1} = f(x_n)$$

Iteration의 장기 행동 연구

### 5. Computer Science^[컴퓨터 과학]

- Algorithm analysis (시간 복잡도)
- Recurrence relations
- Data structures

### 6. Economics^[경제학]

- Compound interest
- Population growth models
- Time series analysis

## Common Patterns^[일반적 패턴]

### Pattern 1: Convergence to Limit^[극한으로 수렴]

수열이 특정 값에 접근

**예**: $a_n = \frac{1}{n} \to 0$

### Pattern 2: Divergence to Infinity^[무한대로 발산]

수열이 무한대로 증가/감소

**예**: $a_n = n^2 \to +\infty$

### Pattern 3: Oscillation^[진동]

수열이 여러 값 사이를 오감

**예**: $a_n = (-1)^n$

### Pattern 4: Chaotic Behavior^[혼돈 행동]

예측 불가능한 패턴

**예**: Logistic map with certain parameters

## Convergence^[수렴]

수렴과 발산에 대한 자세한 내용은 [[Convergence and Divergence in Sequences]]를 참조하세요.

**주요 정리들**:
- Monotone Convergence Theorem^[단조수렴정리]
- Bolzano-Weierstrass Theorem^[볼차노-바이어슈트라스 정리]
- Cauchy Criterion^[코시 판정법]

## Common Pitfalls^[흔한 실수]

### 1. Sequence vs Set

✗ $\{1, 2, 3\} = \{3, 2, 1\}$ (as sets)

 $(1, 2, 3) \neq (3, 2, 1)$ (as sequences)

순서가 중요!

### 2. Bounded ≠ Convergent

✗ Bounded이면 수렴한다?

✓ **반례**: $a_n = (-1)^n$ (bounded but divergent)

**맞는 명제**: Monotone + Bounded $\Rightarrow$ Convergent

### 3. Eventually vs Always

✗ "모든 $n$에 대해" vs "충분히 큰 $n$에 대해" 혼동

Eventually positive: $\exists N$ such that $a_n > 0$ for $n \geq N$

### 4. Subsequence Convergence

✗ 일부 subsequence가 수렴하면 원래 수열도 수렴?

✓ **반례**: $a_n = (-1)^n$
- $(a_{2n}) = (1, 1, 1, \ldots) \to 1$
- $(a_{2n-1}) = (-1, -1, -1, \ldots) \to -1$
- 하지만 $(a_n)$ 자체는 발산

**맞는 명제**: **모든** subsequence가 같은 값 $L$로 수렴 $\Rightarrow$ $(a_n) \to L$

### 5. Recursive Definition Uniqueness

재귀적 정의에는 **초기 조건** 필요!

✗ $a_n = 2a_{n-1}$만으로는 부족

 $a_1 = 1$, $a_n = 2a_{n-1}$ for $n \geq 2$

## 관련 개념

- [[Convergence and Divergence in Sequences]]: 수렴과 발산의 상세한 이론
- [[Series]]: 수열의 합으로 정의되는 급수
- [[Function]]: 수열의 일반화
- [[Metric Space]]: 수렴 개념의 일반화
- [[Cauchy Sequence]]: 완비성과 수렴
- [[Limit Point]]: 위상적 극한점과의 관계

