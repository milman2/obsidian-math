# <span class="header-prerequisite">Prerequisite</span>
- [[Measure Space]]
- [[Borel Sigma Algebra]]
- Lebesgue integration^[르베스그 적분]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Monotone Convergence Theorem (MCT)^[단조 수렴 정리]

$(X, \mathcal{F}, \mu)$ measure space이고, measurable functions^[가측 함수] $f_n: X \rightarrow [0, \infty]$ ($n = 1, 2, 3, \ldots$)가 다음을 만족한다고 하자:

### 조건

1. **Non-negativity**^[비음성]: $f_n \geq 0$ for all $n$
2. **Monotonicity**^[단조성]: $f_1 \leq f_2 \leq f_3 \leq \cdots$ (pointwise^[점별])
3. **Pointwise convergence**^[점별 수렴]: $f_n(x) \to f(x)$ for all $x \in X$

여기서 $f(x) = \lim_{n \to \infty} f_n(x) = \sup_n f_n(x)$.

### 결론

$$\int_X f \, d\mu = \lim_{n \to \infty} \int_X f_n \, d\mu$$

또는 equivalently^[동등하게]:

$$\int_X \sup_n f_n \, d\mu = \sup_n \int_X f_n \, d\mu$$

## 핵심 아이디어

**"Monotone increasing functions의 경우, limit과 integral을 교환할 수 있다"**

$$\lim_{n \to \infty} \int f_n = \int \lim_{n \to \infty} f_n$$

**주의**: Non-negativity와 monotonicity 조건이 **필수적**!

---

# <span class="header-proof">Proof Sketch</span>

## Step 1: $\leq$ direction

Monotonicity에 의해 $f_n \leq f_{n+1} \leq f$이므로:

$$\int f_n \, d\mu \leq \int f_{n+1} \, d\mu \leq \int f \, d\mu$$

따라서:

$$\lim_{n \to \infty} \int f_n \, d\mu = \sup_n \int f_n \, d\mu \leq \int f \, d\mu$$

## Step 2: $\geq$ direction

Simple function^[단순 함수] $s \leq f$에 대해, $0 < c < 1$를 고정하고:

$$E_n = \{x : f_n(x) \geq c \cdot s(x)\}$$

**Key observation**:
1. $E_1 \subseteq E_2 \subseteq E_3 \subseteq \cdots$ (increasing)
2. $\bigcup_n E_n = X$ (since $f_n \to f \geq s$)

Continuity from below^[아래로부터의 연속성]에 의해:

$$\mu(E_n) \to \mu(X)$$

따라서:

$$\int f_n \, d\mu \geq \int_{E_n} f_n \, d\mu \geq c \int_{E_n} s \, d\mu$$

$n \to \infty$로 보내면:

$$\lim_{n \to \infty} \int f_n \, d\mu \geq c \int_X s \, d\mu$$

$c \to 1$로 보내면:

$$\lim_{n \to \infty} \int f_n \, d\mu \geq \int_X s \, d\mu$$

모든 simple function $s \leq f$에 대해 성립하므로:

$$\lim_{n \to \infty} \int f_n \, d\mu \geq \int_X f \, d\mu$$

**결론**: 양방향 부등식이 성립하므로 등식.

---

# <span class="header-properties">Properties</span>

## Corollary 1: Series summation^[급수 합]

Non-negative measurable functions $g_n \geq 0$에 대해:

$$\int_X \displaystyle\sum_{n=1}^\infty g_n \, d\mu = \displaystyle\sum_{n=1}^\infty \int_X g_n \, d\mu$$

**Proof**: $f_n = \displaystyle\sum_{k=1}^n g_k$로 놓으면 monotone increasing.

**Key application**: Infinite series와 integral 교환!

## Corollary 2: Countable additivity of integral^[적분의 가산 가법성]

Disjoint measurable sets $A_1, A_2, \ldots \in \mathcal{F}$에 대해:

$$\int_{\bigcup_n A_n} f \, d\mu = \displaystyle\sum_{n=1}^\infty \int_{A_n} f \, d\mu$$

**Proof**: $g_n = f \cdot \mathbb{1}_{A_n}$로 놓고 Corollary 1 적용.

## Corollary 3: Definition of $L^1$ integral^[L^1 적분의 정의]

Non-negative function $f \geq 0$의 integral은:

$$\int f \, d\mu = \sup \left\{\int s \, d\mu : s \text{ simple}, 0 \leq s \leq f\right\}$$

이는 monotone increasing simple functions의 limit.

## Extension to general functions^[일반 함수로의 확장]

$f = f^+ - f^-$ (positive and negative parts):

$$\int f \, d\mu = \int f^+ \, d\mu - \int f^- \, d\mu$$

MCT를 각각 $f^+$, $f^-$에 적용.

---

# <span class="header-examples">Examples</span>

## 1. Summation of series^[급수의 합]

$X = \mathbb{N}$, $\mu$ = counting measure.

$$f_n(k) = \begin{cases}
\frac{1}{k^2} & k \leq n \\
0 & k > n
\end{cases}$$

Then $f_n \nearrow f$ where $f(k) = \frac{1}{k^2}$.

**MCT**:

$$\int_\mathbb{N} f \, d\mu = \lim_{n \to \infty} \displaystyle\sum_{k=1}^n \frac{1}{k^2} = \displaystyle\sum_{k=1}^\infty \frac{1}{k^2} = \frac{\pi^2}{6}$$

## 2. Interchange of sum and integral^[합과 적분의 교환]

Non-negative functions $g_n: [0, 1] \rightarrow [0, \infty)$:

$$\int_0^1 \displaystyle\sum_{n=1}^\infty g_n(x) \, dx = \displaystyle\sum_{n=1}^\infty \int_0^1 g_n(x) \, dx$$

**Example**: $g_n(x) = x^n$ for $x \in [0, 1)$:

$$\int_0^1 \displaystyle\sum_{n=1}^\infty x^n \, dx = \int_0^1 \frac{x}{1-x} \, dx$$

$$= \displaystyle\sum_{n=1}^\infty \int_0^1 x^n \, dx = \displaystyle\sum_{n=1}^\infty \frac{1}{n+1}$$

## 3. Limit of integrals^[적분의 극한]

$f_n(x) = \mathbb{1}_{[0, 1/n]}(x)$ on $[0, 1]$:

$$f_n \nearrow \mathbb{1}_{\{0\}}$$

**MCT**:

$$\int_0^1 \mathbb{1}_{\{0\}} \, d\lambda = \lim_{n \to \infty} \int_0^1 \mathbb{1}_{[0, 1/n]} \, d\lambda = \lim_{n \to \infty} \frac{1}{n} = 0$$

## 4. Probability: Sum of random variables^[확률 변수의 합]

Non-negative random variables $X_n \geq 0$:

$$E\left[\displaystyle\sum_{n=1}^\infty X_n\right] = \displaystyle\sum_{n=1}^\infty E[X_n]$$

**Application**: Total expected value = sum of expectations.

**상세한 내용**: [[Expected Value]]

## 5. Construction of Lebesgue integral^[르베스그 적분의 구성]

Simple functions $s_n \nearrow f$:

$$\int f \, d\mu = \lim_{n \to \infty} \int s_n \, d\mu$$

**Key step**: MCT는 Lebesgue integral의 well-definedness를 보장.

## 6. Fatou's Lemma에서 유도

MCT는 Fatou's Lemma의 special case로 볼 수도 있음 (equality가 성립).

---

# <span class="header-properties">Relationship with Other Theorems</span>

## Fatou's Lemma^[파투의 보조정리]

Non-negative $f_n \geq 0$ (monotone 아니어도):

$$\int \liminf_{n \to \infty} f_n \, d\mu \leq \liminf_{n \to \infty} \int f_n \, d\mu$$

**Relationship**: MCT는 Fatou's Lemma의 equality case.

**Proof of MCT using Fatou**:
- $f_n \nearrow f$ implies $\liminf f_n = f$
- Also $\lim \int f_n$ exists (monotone sequence)
- Fatou gives $\leq$, reverse inequality is trivial

**상세한 내용**: [[Fatou's Lemma]]

## Dominated Convergence Theorem^[지배 수렴 정리]

MCT의 더 일반적인 버전 (monotonicity 불필요, domination 필요).

**상세한 내용**: [[Dominated Convergence Theorem]]

## Beppo Levi's Theorem^[베포 레비 정리]

MCT의 다른 이름. 두 정리는 동일함.

---

# <span class="header-remark">Applications</span>

## 1. Probability theory^[확률론]

### Expectation of non-negative sums

$$E\left[\displaystyle\sum_{n=1}^\infty X_n\right] = \displaystyle\sum_{n=1}^\infty E[X_n]$$

### Generating functions^[생성 함수]

$$M_X(t) = E[e^{tX}] = \displaystyle\sum_{n=0}^\infty \frac{t^n}{n!} E[X^n]$$

## 2. Construction of measures^[측도의 구성]

**Carathéodory's extension theorem**^[카라테오도리 확장 정리]에서 MCT 사용:
- Pre-measure를 measure로 확장
- Countable additivity 증명

## 3. $L^p$ spaces^[L^p 공간]

$\|f\|_p = \left(\int |f|^p \, d\mu\right)^{1/p}$의 well-definedness:

$$\int |f|^p = \int \lim_{n \to \infty} (\min(|f|, n))^p$$

## 4. Fubini's theorem^[푸비니 정리]

Product measures에서 iterated integrals:

$$\int_X \left(\int_Y f(x, y) \, d\nu(y)\right) d\mu(x)$$

MCT를 사용하여 non-negative functions부터 시작.

## 5. Change of variables^[변수 변환]

Radon-Nikodym derivative를 통한 적분 변환에서 MCT 사용.

**상세한 내용**: [[Measure Space]] (Radon-Nikodym theorem)

## 6. Ergodic theory^[에르고딕 이론]

Birkhoff ergodic theorem 증명에서 MCT 사용.

## 7. Stochastic processes^[확률 과정]

- Martingale convergence theorem
- Kolmogorov's three-series theorem

---

# <span class="header-remark">Remark</span>

## Why monotonicity matters^[왜 단조성이 중요한가]

**Counter-example without monotonicity**:

$f_n(x) = \mathbb{1}_{[n, n+1]}(x)$ on $\mathbb{R}$:

$$f_n(x) \to 0 \text{ for all } x$$

But:

$$\int_\mathbb{R} f_n \, d\lambda = 1 \quad \forall n$$

따라서:

$$\lim_{n \to \infty} \int f_n = 1 \neq 0 = \int \lim_{n \to \infty} f_n$$

**Lesson**: Without monotonicity, limit and integral do NOT commute!

## Comparison with uniform convergence^[균일 수렴과의 비교]

### Riemann integration

Requires **uniform convergence**^[균일 수렴]:

$$f_n \rightrightarrows f \Rightarrow \lim_{n \to \infty} \int f_n = \int f$$

### Lebesgue integration (MCT)

Only requires **pointwise convergence + monotonicity**^[점별 수렴 + 단조성]:

$$f_n \nearrow f \Rightarrow \lim_{n \to \infty} \int f_n = \int f$$

**Advantage**: Much weaker condition!

## Extension to decreasing sequences^[감소 수열로의 확장]

$f_n \searrow f$ (decreasing) and $\int f_1 < \infty$:

$$\int f \, d\mu = \lim_{n \to \infty} \int f_n \, d\mu$$

**Proof**: Apply MCT to $g_n = f_1 - f_n \nearrow f_1 - f$.

**주의**: $\int f_1 < \infty$ 조건 필요!

**Counter-example**: $f_n = \mathbb{1}_{[n, \infty)}$ on $\mathbb{R}$:
- $f_n \searrow 0$
- But $\int f_n = \infty$ for all $n$

## Non-negativity is essential^[비음성은 필수적]

**Counter-example**: $f_n = -\mathbb{1}_{[n, \infty)}$ on $\mathbb{R}$:
- $f_n \nearrow 0$ (increasing!)
- $\int f_n = -\infty$ for all $n$
- But $\int 0 = 0$

따라서 non-negativity 없이는 MCT 실패.

---

# <span class="header-examples">핵심 개념 요약</span>

## Statement^[명제]

```
f₁ ≤ f₂ ≤ f₃ ≤ ⋯ (non-negative, measurable)
    ↓ pointwise
f = lim fₙ = sup fₙ
    ↓ MCT
∫ f dμ = lim ∫ fₙ dμ
```

## 조건 체크리스트

| Condition | Required? | Why? |
|-----------|-----------|------|
| Non-negativity |  Yes | Prevent $\infty - \infty$ |
| Monotonicity |  Yes | Enable limit exchange |
| Pointwise convergence |  Yes | Define limit function |
| Uniform convergence | ✗ No | Too strong! |
| Domination | ✗ No | Not needed (monotone) |

## Key applications^[핵심 응용]

| Application | Formula |
|-------------|---------|
| Series interchange | $\int \sum g_n = \sum \int g_n$ |
| Countable additivity | $\int_{\bigcup A_n} f = \sum \int_{A_n} f$ |
| Expected value | $E[\sum X_n] = \sum E[X_n]$ |
| Integral construction | $\int f = \sup \int s$ (simple $s \leq f$) |

## Comparison of convergence theorems^[수렴 정리 비교]

| Theorem | Conditions | Generality |
|---------|------------|------------|
| **MCT** | $f_n \nearrow$, $f_n \geq 0$ | Special case |
| **Fatou** | $f_n \geq 0$ | Inequality only |
| **DCT** | $\|f_n\| \leq g$, $\int g < \infty$ | More general |

---

**기초 개념**: [[Measure Space]], [[Borel Sigma Algebra]]
**관련 정리**: [[Dominated Convergence Theorem]], [[Fatou's Lemma]]
**응용**: [[Expected Value]], [[Probability]], [[Hilbert Space]]

