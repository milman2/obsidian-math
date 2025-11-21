# <span class="header-prerequisite">Prerequisite</span>
- [[Measure Space]]
- [[Monotone Convergence Theorem]]
- [[Borel Sigma Algebra]]
- Lebesgue integration^[르베스그 적분]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Dominated Convergence Theorem (DCT)^[지배 수렴 정리]

$(X, \mathcal{F}, \mu)$ measure space이고, measurable functions^[가측 함수] $f_n: X \rightarrow \mathbb{R}$ (또는 $\mathbb{C}$)가 다음을 만족한다고 하자:

### 조건

1. **Pointwise convergence**^[점별 수렴]: $f_n(x) \to f(x)$ for almost every $x \in X$
   (여기서 almost every^[거의 모든]는 measure zero set^[측도 0 집합]을 제외)

2. **Domination**^[지배]: $\exists$ integrable function^[적분 가능 함수] $g: X \rightarrow [0, \infty)$ s.t.
   $$|f_n(x)| \leq g(x) \quad \text{for almost every } x, \forall n$$
   and $\int_X g \, d\mu < \infty$

### 결론

$$\lim_{n \to \infty} \int_X f_n \, d\mu = \int_X f \, d\mu = \int_X \lim_{n \to \infty} f_n \, d\mu$$

또한:

$$\lim_{n \to \infty} \int_X |f_n - f| \, d\mu = 0$$

즉, $f_n \to f$ in $L^1$ (norm convergence^[노름 수렴]).

## 핵심 아이디어

**"Dominating function이 있으면, pointwise convergence만으로 limit과 integral을 교환할 수 있다"**

$$\lim_{n \to \infty} \int f_n = \int \lim_{n \to \infty} f_n$$

**주의**: Monotonicity 불필요! Domination이 핵심.

---

# <span class="header-proof">Proof Sketch</span>

## Key tool: Fatou's Lemma^[파투의 보조정리]

Non-negative $h_n \geq 0$에 대해:

$$\int \liminf_{n \to \infty} h_n \, d\mu \leq \liminf_{n \to \infty} \int h_n \, d\mu$$

## Proof of DCT

**Step 1**: $|f_n| \leq g$이고 $f_n \to f$ a.e.이므로, $|f| \leq g$ a.e.

따라서 $f$도 integrable^[적분 가능].

**Step 2**: $g + f_n \geq 0$이고 $g - f_n \geq 0$에 Fatou's Lemma 적용:

$$\int \liminf(g + f_n) \leq \liminf \int (g + f_n)$$
$$\int \liminf(g - f_n) \leq \liminf \int (g - f_n)$$

**Step 3**: $\liminf(g + f_n) = g + f$, $\liminf(g - f_n) = g - f$이므로:

$$\int (g + f) \leq \int g + \liminf \int f_n$$
$$\int (g - f) \leq \int g - \limsup \int f_n$$

**Step 4**: 정리하면:

$$\int f \leq \liminf \int f_n$$
$$\int f \geq \limsup \int f_n$$

따라서:

$$\liminf \int f_n = \limsup \int f_n = \int f$$

즉, $\lim \int f_n = \int f$.

**Step 5**: $L^1$ convergence:

$$\int |f_n - f| \leq \int (g - f) + \int (g + f_n) \to 0$$

(Fatou's Lemma를 $2g - |f_n - f|$에 적용)

---

# <span class="header-properties">Properties</span>

## Corollary 1: Differentiation under integral^[적분 속 미분]

Parameter^[매개변수] $t$에 대해, $f(x, t)$가:
1. Differentiable in $t$ for each $x$
2. $\left|\frac{\partial f}{\partial t}(x, t)\right| \leq g(x)$ with $\int g < \infty$

Then:

$$\frac{d}{dt} \int_X f(x, t) \, d\mu(x) = \int_X \frac{\partial f}{\partial t}(x, t) \, d\mu(x)$$

**Proof**: Apply DCT to $\frac{f(x, t+h) - f(x, t)}{h}$.

## Corollary 2: Bounded convergence theorem^[유계 수렴 정리]

$\mu(X) < \infty$ (finite measure)이고 $|f_n| \leq M$ (uniformly bounded):

$$f_n \to f \text{ a.e.} \Rightarrow \int f_n \to \int f$$

**Proof**: Dominating function $g = M$ is integrable.

**Special case**: Probability measures ($P(\Omega) = 1$).

## Corollary 3: Continuity of translation^[평행이동의 연속성]

$f \in L^1(\mathbb{R})$이면, $h \to 0$일 때:

$$\int |f(x + h) - f(x)| \, dx \to 0$$

**Proof**: DCT with dominating function (convolution argument).

## Extension to $L^p$ spaces

$1 \leq p < \infty$, $|f_n|^p \leq g \in L^1$이면:

$$\int |f_n - f|^p \to 0$$

---

# <span class="header-examples">Examples</span>

## 1. Limit of integrals^[적분의 극한]

$$\lim_{n \to \infty} \int_0^\infty \frac{n}{1 + n^2 x^2} \, dx$$

**Solution**: 
- $f_n(x) = \frac{n}{1 + n^2 x^2} \to 0$ pointwise
- Dominating function: $g(x) = \frac{1}{x}$ on $(0, \infty)$? No! Not integrable.
- Better: For $x \geq 1/n$, $f_n(x) \leq \frac{1}{nx^2}$
- Actually, $\int f_n = \pi/2$ for all $n$ (exact calculation)

**Alternative approach**: Direct calculation shows answer is $\pi/2$.

## 2. Differentiation under integral^[적분 속 미분]

$$F(t) = \int_0^\infty e^{-tx^2} \, dx$$

Find $F'(t)$:

$$F'(t) = \int_0^\infty \frac{\partial}{\partial t} e^{-tx^2} \, dx = \int_0^\infty (-x^2) e^{-tx^2} \, dx$$

**Justification**: $\left|x^2 e^{-tx^2}\right| \leq x^2 e^{-x^2/2}$ for $t \geq 1$ (integrable).

## 3. Expectation convergence^[기댓값 수렴]

Random variables $X_n \to X$ a.e., $|X_n| \leq Y$ with $E[Y] < \infty$:

$$E[X_n] \to E[X]$$

**Application**: Law of Large Numbers^[큰 수의 법칙]에서 사용.

**상세한 내용**: [[Expected Value]]

## 4. Fourier transform continuity^[푸리에 변환의 연속성]

$f \in L^1(\mathbb{R})$이면, Fourier transform^[푸리에 변환]:

$$\hat{f}(\xi) = \int_{\mathbb{R}} f(x) e^{-2\pi i x \xi} \, dx$$

is continuous in $\xi$.

**Proof**: Apply DCT to $f(x) e^{-2\pi i x \xi_n}$ as $\xi_n \to \xi$.

## 5. Probability: Convergence in distribution^[분포 수렴]

$X_n \to X$ in distribution, and $|X_n| \leq M$ (uniformly bounded):

$$E[g(X_n)] \to E[g(X)]$$

for any bounded continuous $g$.

## 6. Power series^[멱급수]

$$f(x) = \displaystyle\sum_{n=0}^\infty a_n x^n$$

Integrate term-by-term on $[0, r]$ with $r < R$ (radius of convergence):

$$\int_0^r f(x) \, dx = \displaystyle\sum_{n=0}^\infty a_n \int_0^r x^n \, dx = \displaystyle\sum_{n=0}^\infty \frac{a_n r^{n+1}}{n+1}$$

**Justification**: DCT with counting measure on $\mathbb{N}$.

---

# <span class="header-properties">Comparison with Other Theorems</span>

## MCT vs DCT

| | **MCT** | **DCT** |
|---|---|---|
| **Condition** | $f_n \nearrow$, $f_n \geq 0$ | $\|f_n\| \leq g$, $\int g < \infty$ |
| **Convergence** | Monotone | Arbitrary (pointwise) |
| **Sign** | Non-negative only | Can be signed |
| **Generality** | Special case | More general |
| **Ease of verification** | Check monotonicity | Find dominating function |

**Relationship**: MCT는 DCT의 special case (take $g = \sup_n f_n < \infty$).

## Fatou's Lemma

DCT는 Fatou's Lemma를 사용하여 증명됨.

**Fatou**: Inequality (one direction)
**DCT**: Equality (both directions with domination)

**상세한 내용**: [[Fatou's Lemma]]

## Bounded Convergence Theorem

DCT의 special case (finite measure + uniform bounds).

---

# <span class="header-remark">Applications</span>

## 1. Probability theory^[확률론]

### Convergence of expectations^[기댓값의 수렴]

$X_n \to X$ a.e., $|X_n| \leq Y$, $E[Y] < \infty$:

$$E[X_n] \to E[X]$$

### Uniform integrability^[균일 적분가능성]

DCT는 uniform integrability의 특수 경우.

### Central Limit Theorem^[중심극한정리]

Characteristic functions^[특성 함수]의 수렴 증명에 사용.

## 2. Real analysis^[실해석학]

### Differentiation under integral

$$\frac{d}{dt} \int f(x, t) \, dx = \int \frac{\partial f}{\partial t}(x, t) \, dx$$

### Continuity of convolution^[합성곱의 연속성]

$$f * g(x) = \int f(x - y) g(y) \, dy$$

is continuous if $f, g \in L^1$.

## 3. Fourier analysis^[푸리에 해석학]

### Fourier transform properties

- Continuity of $\hat{f}$
- Inversion theorem^[역변환 정리]
- Plancherel theorem

## 4. Functional analysis^[함수해석학]

### $L^p$ spaces

- Completeness of $L^p$
- Dense subsets
- Duality theory

**상세한 내용**: [[Hilbert Space]]

## 5. Partial differential equations^[편미분방정식]

### Heat equation^[열방정식]

Solution representation using fundamental solution.

### Weak derivatives^[약한 도함수]

Differentiation under integral in weak sense.

## 6. Stochastic processes^[확률 과정]

### Martingale convergence

Optional stopping theorem에서 사용.

### Brownian motion^[브라운 운동]

Path properties, quadratic variation.

---

# <span class="header-remark">Remark</span>

## Why domination is necessary^[왜 지배가 필요한가]

**Counter-example without domination**:

$$f_n(x) = n \mathbb{1}_{[0, 1/n]}(x) \quad \text{on } [0, 1]$$

- $f_n(x) \to 0$ pointwise
- But $\int_0^1 f_n \, dx = 1$ for all $n$

따라서:

$$\lim \int f_n = 1 \neq 0 = \int \lim f_n$$

**No dominating integrable function**: $|f_n| = n$ on $[0, 1/n]$.

## Uniform integrability^[균일 적분가능성]

DCT의 일반화: Domination 대신 **uniform integrability**^[균일 적분가능성]:

$$\lim_{M \to \infty} \sup_n \int_{|f_n| > M} |f_n| = 0$$

**Vitali convergence theorem**^[비탈리 수렴 정리]: Finite measure + uniform integrability.

## Almost everywhere convergence^[거의 모든 곳에서의 수렴]

DCT는 almost everywhere convergence만 필요:

$$\mu(\{x : f_n(x) \not\to f(x)\}) = 0$$

Measure zero set에서는 수렴 안 해도 됨!

## Extension to $\mathbb{C}$-valued functions

DCT는 complex-valued functions에도 성립:

$$f_n: X \to \mathbb{C}$$

**Domination**: $|f_n| \leq g$ (modulus^[절댓값]).

## Weak convergence in $L^1$

$f_n \to f$ in $L^1$ (DCT) implies **weak convergence**^[약한 수렴]:

$$\int f_n \cdot h \to \int f \cdot h \quad \forall h \in L^\infty$$

## Counterexample: Need finite integral of dominating function

$f_n = \mathbb{1}_{[n, n+1]}$, dominating function $g = 1$ (constant):

- $|f_n| \leq 1$ but $\int_\mathbb{R} 1 \, d\lambda = \infty$
- DCT does NOT apply!
- Indeed, $\int f_n = 1$ but $\int \lim f_n = \int 0 = 0$

---

# <span class="header-examples">핵심 개념 요약</span>

## Statement^[명제]

```
fₙ → f pointwise a.e.
|fₙ| ≤ g with ∫ g < ∞
    ↓ DCT
∫ fₙ → ∫ f
```

## 조건 체크리스트

| Condition | Required? | Why? |
|-----------|-----------|------|
| Pointwise convergence (a.e.) | ✓ Yes | Define limit |
| Dominating function $g$ | ✓ Yes | Control tails |
| $\int g < \infty$ | ✓ Yes | Integrability |
| Monotonicity | ✗ No | Not needed! |
| Uniform convergence | ✗ No | Too strong |
| Non-negativity | ✗ No | Can be signed |

## Key applications^[핵심 응용]

| Application | Context |
|-------------|---------|
| Differentiation under $\int$ | Parameter-dependent integrals |
| Expectation convergence | $E[X_n] \to E[X]$ |
| Fourier transform | Continuity |
| $L^p$ convergence | Completeness |
| PDE solutions | Weak derivatives |

## When to use which theorem?^[어떤 정리를 사용할까?]

| Situation | Theorem | Why? |
|-----------|---------|------|
| $f_n$ increasing, $\geq 0$ | **MCT** | Natural choice |
| $f_n$ bounded, $\mu(X) < \infty$ | **BCT** (DCT special case) | Easy |
| $f_n$ arbitrary, have bound | **DCT** | Most general |
| Only lower bound | **Fatou** | Get inequality |

## Finding dominating functions^[지배 함수 찾기]

**Strategy**:
1. **Uniform bound**: $|f_n| \leq M$ (constant) and $\mu(X) < \infty$ → $g = M$
2. **Pointwise bound**: $|f_n(x)| \leq h(x)$ for all $n$ → try $g = h$
3. **Eventual bound**: $|f_n| \leq g$ for $n \geq N_0$ → check $\int g < \infty$
4. **Exponential decay**: $e^{-x}$, $e^{-x^2}$ often work
5. **Power decay**: $x^{-\alpha}$ with $\alpha > 1$ on $[1, \infty)$

---

**기초 개념**: [[Measure Space]], [[Borel Sigma Algebra]]
**관련 정리**: [[Monotone Convergence Theorem]], [[Fatou's Lemma]]
**응용**: [[Expected Value]], [[Probability]], [[Hilbert Space]]
**확률론**: [[Sample Spaces]], [[Random Variables]]

