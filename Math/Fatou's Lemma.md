# <span class="header-prerequisite">Prerequisite</span>
- [[Measure Space]]
- [[Borel Sigma Algebra]]
- Lebesgue integration^[르베스그 적분]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Fatou's Lemma^[파투의 보조정리]

$(X, \mathcal{F}, \mu)$ measure space이고, measurable functions^[가측 함수] $f_n: X \rightarrow [0, \infty]$ ($n = 1, 2, 3, \ldots$)가 non-negative^[비음성]라고 하자.

### 명제

$$\int_X \liminf_{n \to \infty} f_n \, d\mu \leq \liminf_{n \to \infty} \int_X f_n \, d\mu$$

### 핵심 아이디어

**"Non-negative functions의 경우, liminf를 적분 밖으로 꺼낼 수 있다 (부등식)"**

$$\int \liminf f_n \leq \liminf \int f_n$$

**주의**: 
- Equality가 아닌 **inequality**!
- Monotonicity나 domination 조건 **불필요**!
- Non-negativity만 필요

## Reverse Fatou's Lemma^[역 파투 보조정리]

$f_n \leq g$ for all $n$이고 $\int g \, d\mu < \infty$ (integrable dominating function):

$$\int_X \limsup_{n \to \infty} f_n \, d\mu \geq \limsup_{n \to \infty} \int_X f_n \, d\mu$$

**Proof**: Apply Fatou to $g - f_n \geq 0$.

---

# <span class="header-proof">Proof</span>

## Proof of Fatou's Lemma

**Step 1**: Define auxiliary sequence^[보조 수열]

$$g_n(x) = \inf_{k \geq n} f_k(x) = \inf\{f_n(x), f_{n+1}(x), f_{n+2}(x), \ldots\}$$

**Properties of $g_n$**:
1. $g_n \geq 0$ (infimum of non-negative functions)
2. $g_n$ is measurable (infimum of countably many measurable functions)
3. $g_1 \leq g_2 \leq g_3 \leq \cdots$ (monotone increasing!)
4. $g_n(x) \to \liminf_{k \to \infty} f_k(x)$ as $n \to \infty$

**Step 2**: Apply Monotone Convergence Theorem to $g_n$

Since $g_n \nearrow \liminf f_k$:

$$\int \liminf_{k \to \infty} f_k \, d\mu = \int \lim_{n \to \infty} g_n \, d\mu = \lim_{n \to \infty} \int g_n \, d\mu$$

(by MCT)

**Step 3**: Use $g_n \leq f_n$

For all $k \geq n$: $g_n(x) \leq f_k(x)$ (by definition of infimum)

In particular: $g_n \leq f_n$

Therefore:

$$\int g_n \, d\mu \leq \int f_n \, d\mu$$

**Step 4**: Take limits

$$\lim_{n \to \infty} \int g_n \, d\mu \leq \liminf_{n \to \infty} \int f_n \, d\mu$$

**Step 5**: Combine

$$\int \liminf_{k \to \infty} f_k \, d\mu = \lim_{n \to \infty} \int g_n \, d\mu \leq \liminf_{n \to \infty} \int f_n \, d\mu$$

**결론**: Fatou's Lemma 증명 완료. ∎

## Key insight of proof^[증명의 핵심]

1. **Reduce to monotone case**: $g_n = \inf_{k \geq n} f_k$는 monotone!
2. **Apply MCT**: Monotone convergence gives equality for $g_n$
3. **Use inequality**: $g_n \leq f_n$ gives the final inequality

---

# <span class="header-properties">Properties</span>

## When is equality achieved?^[등식이 성립하는 경우]

Fatou's Lemma가 equality가 되는 경우:

### 1. Monotone Convergence Theorem

$f_n \nearrow f$ (monotone increasing):

$$\liminf f_n = \lim f_n = f$$

Fatou gives:

$$\int f \leq \liminf \int f_n$$

But monotonicity also gives $\int f_n \leq \int f$, so:

$$\int f = \lim \int f_n$$

**결론**: MCT는 Fatou + monotonicity.

### 2. Dominated Convergence

$|f_n| \leq g$, $\int g < \infty$:

Fatou alone is not enough, need domination for equality.

### 3. Eventually constant^[결국 상수]

$f_n(x) = f(x)$ for all $n \geq N_0(x)$:

$$\liminf f_n = f$$

Clearly equality.

## Fatou for series^[급수에 대한 파투]

Counting measure on $\mathbb{N}$:

$$\sum_{k=1}^\infty \liminf_{n \to \infty} a_{n,k} \leq \liminf_{n \to \infty} \sum_{k=1}^\infty a_{n,k}$$

for $a_{n,k} \geq 0$.

## Extension: Fatou-Lebesgue Theorem^[파투-르베스그 정리]

$f_n \to f$ a.e. and $\int |f_n| \leq C < \infty$ (uniformly bounded integrals):

$$\int |f| \leq \liminf_{n \to \infty} \int |f_n| \leq C$$

따라서 $f \in L^1$.

---

# <span class="header-examples">Examples</span>

## 1. Strict inequality^[진 부등식]

$f_n = n \mathbb{1}_{[0, 1/n]}$ on $[0, 1]$:

**Pointwise limit**:

$$f_n(x) \to \begin{cases}
0 & x > 0 \\
\infty & x = 0
\end{cases}$$

따라서 $\liminf f_n = 0$ a.e.

**Integrals**:

$$\int_0^1 f_n \, dx = n \cdot \frac{1}{n} = 1 \quad \forall n$$

따라서 $\liminf \int f_n = 1$.

**Fatou's Lemma**:

$$\int \liminf f_n = \int 0 = 0 < 1 = \liminf \int f_n$$

**Strict inequality**! 

**Lesson**: Without monotonicity or domination, we only get inequality.

## 2. Equality case: Monotone

$f_n = \mathbb{1}_{[0, 1 - 1/n]}$ on $[0, 1]$:

- $f_n \nearrow \mathbb{1}_{[0, 1)}$
- $\liminf f_n = \mathbb{1}_{[0, 1)}$
- $\int f_n = 1 - 1/n \to 1$
- $\int \liminf f_n = 1$

**Equality**! (MCT case)

## 3. Sliding bump^[이동하는 융기]

$f_n = \mathbb{1}_{[n, n+1]}$ on $\mathbb{R}$:

- $f_n(x) \to 0$ for all $x$ (eventually outside any fixed interval)
- $\liminf f_n = 0$
- $\int f_n = 1$ for all $n$

**Fatou**:

$$0 = \int \liminf f_n < 1 = \liminf \int f_n$$

**Lesson**: "Mass escapes to infinity".

## 4. Probability: Borel-Cantelli^[보렐-칸텔리]

Events $E_1, E_2, \ldots$ with $\sum P(E_n) < \infty$:

$$P(\limsup E_n) = 0$$

**Proof using Fatou**:

$$\int \sum_{n=k}^\infty \mathbb{1}_{E_n} = \sum_{n=k}^\infty P(E_n) < \infty$$

By Fatou (applied to $\sum_{n=k}^N \mathbb{1}_{E_n}$ as $N \to \infty$).

## 5. Lower semicontinuity^[하반 연속성]

Integral functional $I(f) = \int f$는 lower semicontinuous w.r.t. pointwise convergence:

$$I(\liminf f_n) \leq \liminf I(f_n)$$

**Application**: Calculus of variations^[변분법].

---

# <span class="header-properties">Relationship with Other Theorems</span>

## Fatou's Lemma is fundamental^[파투 보조정리는 기본]

```
Fatou's Lemma (inequality)
    ↓ + monotonicity
Monotone Convergence Theorem (equality)
    ↓ + domination
Dominated Convergence Theorem (equality)
```

## Comparison table^[비교표]

| Theorem | Conditions | Result | Strength |
|---------|------------|--------|----------|
| **Fatou** | $f_n \geq 0$ | $\int \liminf f_n \leq \liminf \int f_n$ | Weakest conditions |
| **MCT** | $f_n \nearrow$, $f_n \geq 0$ | $\int \lim f_n = \lim \int f_n$ | Equality for monotone |
| **DCT** | $\|f_n\| \leq g$, $\int g < \infty$ | $\int \lim f_n = \lim \int f_n$ | Most general equality |

## Proving MCT from Fatou

**Given**: $f_n \nearrow f$, $f_n \geq 0$

**Fatou**: $\int f = \int \liminf f_n \leq \liminf \int f_n$

**Monotonicity**: $\int f_n$ is increasing, so $\liminf \int f_n = \lim \int f_n$

**Also**: $\int f_n \leq \int f$ for all $n$, so $\lim \int f_n \leq \int f$

**결론**: $\int f = \lim \int f_n$ (MCT).

## Proving DCT from Fatou

**Given**: $f_n \to f$, $|f_n| \leq g$, $\int g < \infty$

**Apply Fatou to** $g + f_n \geq 0$:

$$\int (g + f) = \int \liminf(g + f_n) \leq \liminf \int (g + f_n) = \int g + \liminf \int f_n$$

**Apply Fatou to** $g - f_n \geq 0$:

$$\int (g - f) = \int \liminf(g - f_n) \leq \liminf \int (g - f_n) = \int g - \limsup \int f_n$$

**Combine**: 

$$\int f \leq \liminf \int f_n \leq \limsup \int f_n \leq \int f$$

**결론**: $\lim \int f_n = \int f$ (DCT).

---

# <span class="header-remark">Applications</span>

## 1. Lower semicontinuity^[하반 연속성]

Functional $I: L^1 \to \mathbb{R}$, $I(f) = \int f$:

$$I(\liminf f_n) \leq \liminf I(f_n)$$

**Application**: Minimization problems in calculus of variations.

## 2. Probability theory^[확률론]

### Borel-Cantelli Lemma^[보렐-칸텔리 보조정리]

$\sum P(E_n) < \infty \Rightarrow P(\limsup E_n) = 0$

### Fatou for expectations

$X_n \geq 0$ random variables:

$$E[\liminf X_n] \leq \liminf E[X_n]$$

**상세한 내용**: [[Expected Value]]

## 3. Proof of other theorems^[다른 정리의 증명]

- **MCT**: Fatou + monotonicity
- **DCT**: Fatou applied twice (to $g \pm f_n$)

## 4. Weak $L^p$ spaces

Definition of weak $L^p$ uses Fatou-type arguments.

## 5. Ergodic theory^[에르고딕 이론]

Maximal ergodic theorem uses Fatou's Lemma.

## 6. Stochastic processes^[확률 과정]

### Optional stopping theorem

Fatou applied to stopped processes.

### Martingale convergence

$E[\liminf X_n] \leq \liminf E[X_n]$ for non-negative martingales.

---

# <span class="header-remark">Remark</span>

## Why non-negativity is essential^[왜 비음성이 필수인가]

**Counter-example**: $f_n = -\mathbb{1}_{[n, n+1]}$ on $\mathbb{R}$:

- $f_n \to 0$ pointwise
- $\liminf f_n = 0$
- $\int f_n = -1$ for all $n$
- $\liminf \int f_n = -1$

Fatou would say:

$$0 = \int \liminf f_n \leq -1 = \liminf \int f_n$$

**Contradiction**! 따라서 non-negativity 없이는 Fatou 실패.

## Fatou in probability notation^[확률론 표기법]

Random variables $X_n \geq 0$:

$$E\left[\liminf_{n \to \infty} X_n\right] \leq \liminf_{n \to \infty} E[X_n]$$

**Interpretation**: "Expected value of lim is at most lim of expectations."

## Liminf vs limsup^[리밍프 vs 리밍슙]

**Fatou**: $\int \liminf f_n \leq \liminf \int f_n$

**Reverse Fatou** (with domination): $\int \limsup f_n \geq \limsup \int f_n$

**Together** (with domination):

$$\limsup \int f_n \leq \int \limsup f_n$$
$$\int \liminf f_n \leq \liminf \int f_n$$

If $f_n \to f$: both give $\int f = \lim \int f_n$ (DCT).

## Connection to weak convergence^[약한 수렴과의 연결]

$f_n \rightharpoonup f$ weakly in $L^1$:

$$\int fg = \lim \int f_n g \quad \forall g \in L^\infty$$

Fatou is related to lower semicontinuity in weak topology.

## Fatou's Lemma in $\mathbb{R}^n$

Works for any measure space, including:
- Lebesgue measure on $\mathbb{R}^n$
- Product measures
- Probability spaces

## Historical note^[역사적 노트]

**Pierre Fatou** (1878-1929): French mathematician.

Originally proved for bounded domains, later generalized.

Used in his work on iteration of rational functions (complex dynamics).

---

# <span class="header-examples">핵심 개념 요약</span>

## Statement^[명제]

```
f₁, f₂, f₃, ... ≥ 0 (non-negative, measurable)
    ↓ Fatou
∫ liminf fₙ ≤ liminf ∫ fₙ
```

**Key**: Inequality (not equality)!

## Conditions vs Results^[조건 vs 결과]

| What you have | What you get | Theorem |
|---------------|--------------|---------|
| $f_n \geq 0$ | Inequality | **Fatou** |
| $f_n \geq 0$, $f_n \nearrow$ | Equality | **MCT** |
| $\|f_n\| \leq g$, $\int g < \infty$ | Equality | **DCT** |

## When Fatou is useful^[파투가 유용한 경우]

1. **No monotonicity**: $f_n$ oscillates
2. **No domination**: Can't find integrable bound
3. **Lower bound needed**: Want inequality, not equality
4. **Proving other theorems**: MCT, DCT use Fatou

## Common mistakes^[흔한 실수]

1. ✗ Forgetting non-negativity → Counter-examples exist!
2. ✗ Expecting equality → Fatou only gives $\leq$
3. ✗ Applying to signed functions → Need $f_n \geq 0$
4. ✗ Confusing liminf and lim → liminf is more general

## Visual intuition^[시각적 직관]

**Fatou**: "Mass can escape, so integral of limit ≤ limit of integrals"

**Example**: $f_n = \mathbb{1}_{[n, n+1]}$ on $\mathbb{R}$
- Each $\int f_n = 1$
- But $\liminf f_n = 0$ (mass moves to $\infty$)
- So $\int \liminf f_n = 0 < 1 = \liminf \int f_n$

## Proof strategy^[증명 전략]

1. **Define** $g_n = \inf_{k \geq n} f_k$ (monotone!)
2. **Apply MCT** to $g_n \nearrow \liminf f_n$
3. **Use** $g_n \leq f_n$ to get inequality
4. **Conclude** Fatou's Lemma

---

**기초 개념**: [[Measure Space]], [[Borel Sigma Algebra]]
**관련 정리**: [[Monotone Convergence Theorem]], [[Dominated Convergence Theorem]]
**응용**: [[Expected Value]], [[Probability]], [[Sample Spaces]]
**고급 주제**: Weak convergence, Calculus of variations, Ergodic theory

