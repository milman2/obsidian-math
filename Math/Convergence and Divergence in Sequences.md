# <span class="header-prerequisite">Prerequisite</span>
- [[Real Numbers]]
- [[Metric Space]]
- [[Limit Point]]

# <span class="header-reference">Reference</span>
- Rudin, Principles of Mathematical Analysis
- Abbott, Understanding Analysis
- Tao, Analysis I

---

# <span class="header-definition">Definition</span>

## Sequence^[수열]

**Sequence^[수열]**는 자연수 집합에서 어떤 집합으로의 함수이다:

$$a: \mathbb{N} \to X$$

**표기**: \(a(n)\) 대신 \(a_n\)으로 쓰고, 수열 전체는 \((a_n)_{n=1}^{\infty}\) 또는 간단히 \((a_n)\)으로 표기

## Convergence^[수렴]

### Metric Space에서의 정의

Metric space^[거리 공간] \((X, d)\)에서 수열 \((x_n)\)이 점 \(x \in X\)로 **converge^[수렴]**한다:

$$\lim_{n \to \infty} x_n = x$$

$$\Leftrightarrow \forall \epsilon > 0, \, \exists N \in \mathbb{N} \text{ such that } \forall n \geq N: \, d(x_n, x) < \epsilon$$

**의미**: \(n\)이 충분히 크면 \(x_n\)이 \(x\)에 임의로 가까워진다

### 실수에서의 정의

\(\mathbb{R}\)에서 수열 \((a_n)\)이 \(L \in \mathbb{R}\)로 수렴한다:

$$\lim_{n \to \infty} a_n = L$$

$$\Leftrightarrow \forall \epsilon > 0, \, \exists N \in \mathbb{N} \text{ such that } \forall n \geq N: \, |a_n - L| < \epsilon$$

**표기**:
- \(a_n \to L\) as \(n \to \infty\)
- \(\displaystyle\lim_{n \to \infty} a_n = L\)

### Topological Space에서의 정의

Topological space^[위상공간] \((X, \tau)\)에서 수열 \((x_n)\)이 점 \(x\)로 수렴한다:

$$\lim_{n \to \infty} x_n = x$$

$$\Leftrightarrow \forall U \in \tau \text{ with } x \in U, \, \exists N \in \mathbb{N} \text{ such that } \forall n \geq N: \, x_n \in U$$

즉, \(x\)를 포함하는 모든 open set^[열린 집합]이 eventually^[궁극적으로] 수열의 모든 항을 포함한다.

## Divergence^[발산]

수열 \((x_n)\)이 **diverge^[발산]**한다 \(\Leftrightarrow\) 수렴하지 않는다

### Special Cases (실수 수열)

**Divergence to \(+\infty\)**:

$$\lim_{n \to \infty} a_n = +\infty \Leftrightarrow \forall M \in \mathbb{R}, \, \exists N \in \mathbb{N} \text{ such that } \forall n \geq N: \, a_n > M$$

**Divergence to \(-\infty\)**:

$$\lim_{n \to \infty} a_n = -\infty \Leftrightarrow \forall M \in \mathbb{R}, \, \exists N \in \mathbb{N} \text{ such that } \forall n \geq N: \, a_n < M$$

**Oscillation^[진동]**: \(+\infty\)나 \(-\infty\)로도 발산하지 않는 경우

---

# <span class="header-properties">Properties</span>

## Uniqueness of Limit^[극한의 유일성]

**정리**: Hausdorff space^[하우스도르프 공간]에서 수열의 극한은 유일하다

Metric space는 Hausdorff이므로:

$$\lim_{n \to \infty} x_n = x \text{ and } \lim_{n \to \infty} x_n = y \Rightarrow x = y$$

**주의**: Non-Hausdorff space에서는 극한이 유일하지 않을 수 있음

## Boundedness^[유계성]

**정리**: 수렴하는 수열은 bounded^[유계]이다

\(\mathbb{R}\)에서 \(\displaystyle\lim_{n \to \infty} a_n = L\)이면:

$$\exists M > 0 \text{ such that } |a_n| \leq M \text{ for all } n$$

**증명**: \(\epsilon = 1\)로 택하면 \(N\) 이상의 모든 \(n\)에 대해 \(|a_n - L| < 1\)

따라서 \(|a_n| < |L| + 1\)

\(M = \max\{|a_1|, |a_2|, \ldots, |a_{N-1}|, |L| + 1\}\)로 택하면 됨 ✓

**역은 거짓**: Bounded이어도 수렴하지 않을 수 있음 (예: \((-1)^n\))

## Algebra of Limits^[극한의 대수]

\(\mathbb{R}\) (또는 \(\mathbb{C}\))에서 \(\displaystyle\lim_{n \to \infty} a_n = a\), \(\displaystyle\lim_{n \to \infty} b_n = b\)이면:

1. **덧셈**: \(\displaystyle\lim_{n \to \infty} (a_n + b_n) = a + b\)

2. **곱셈**: \(\displaystyle\lim_{n \to \infty} (a_n \cdot b_n) = a \cdot b\)

3. **스칼라곱**: \(\displaystyle\lim_{n \to \infty} (c \cdot a_n) = c \cdot a\) for \(c \in \mathbb{R}\)

4. **나눗셈**: \(b \neq 0\)이고 \(b_n \neq 0\)이면 \(\displaystyle\lim_{n \to \infty} \frac{a_n}{b_n} = \frac{a}{b}\)

## Squeeze Theorem^[조임정리]

**정리** (**Squeeze Theorem**, **Sandwich Theorem**):

\(a_n \leq b_n \leq c_n\) for all \(n \geq N_0\)이고

$$\lim_{n \to \infty} a_n = \lim_{n \to \infty} c_n = L$$

이면:

$$\lim_{n \to \infty} b_n = L$$

**직관**: \(b_n\)이 두 수렴하는 수열 사이에 "끼어" 있으면, 같은 극한값으로 수렴

## Order Preservation^[순서 보존]

\(\displaystyle\lim_{n \to \infty} a_n = a\), \(\displaystyle\lim_{n \to \infty} b_n = b\)이고 \(a_n \leq b_n\) for all \(n \geq N_0\)이면:

$$a \leq b$$

**주의**: 엄격한 부등호 \(a_n < b_n\)이어도 \(a < b\)는 보장되지 않음 (예: \(a_n = 0\), \(b_n = \frac{1}{n}\))

## Subsequence^[부분수열]

**정의**: 수열 \((a_n)\)의 **subsequence^[부분수열]**는 strictly increasing^[순증가] 함수 \(n_k: \mathbb{N} \to \mathbb{N}\)에 대해:

$$(a_{n_k})_{k=1}^{\infty}$$

**정리**: \(\displaystyle\lim_{n \to \infty} a_n = L\)이면 모든 subsequence도 \(L\)로 수렴

**역 (부분적)**: 모든 subsequence가 같은 값 \(L\)로 수렴하면 원래 수열도 \(L\)로 수렴

## Monotone Sequences^[단조수열]

**정의**:
- **Monotone increasing^[단조증가]**: \(a_n \leq a_{n+1}\) for all \(n\)
- **Monotone decreasing^[단조감소]**: \(a_n \geq a_{n+1}\) for all \(n\)
- **Monotone^[단조]**: increasing 또는 decreasing

---

# <span class="header-theorem">Theorems</span>

## Monotone Convergence Theorem^[단조수렴정리]

**정리** (**Monotone Convergence Theorem**):

\(\mathbb{R}\)에서 수열 \((a_n)\)이:
1. Monotone increasing이고
2. Bounded above^[위로 유계]이면

\(\Rightarrow\) \((a_n)\)은 수렴하고, \(\displaystyle\lim_{n \to \infty} a_n = \sup\{a_n : n \in \mathbb{N}\}\)

**Dual version**: Monotone decreasing이고 bounded below^[아래로 유계]이면 수렴하고,

$$\lim_{n \to \infty} a_n = \inf\{a_n : n \in \mathbb{N}\}$$

**증명 개요**:
- \(L = \sup\{a_n : n \in \mathbb{N}\}\)라 하자 (supremum은 completeness^[완비성]에 의해 존재)
- 임의의 \(\epsilon > 0\)에 대해 \(L - \epsilon\)은 상계가 아니므로 \(\exists N\) such that \(a_N > L - \epsilon\)
- Monotone increasing이므로 \(n \geq N\)이면 \(a_n \geq a_N > L - \epsilon\)
- 또한 \(a_n \leq L\) (상계의 정의)
- 따라서 \(L - \epsilon < a_n \leq L < L + \epsilon\), 즉 \(|a_n - L| < \epsilon\) ✓

**중요성**: \(\mathbb{R}\)의 completeness를 이용한 핵심 정리

## Cauchy Sequence^[코시 수열]

**정의**: Metric space \((X, d)\)에서 수열 \((x_n)\)이 **Cauchy sequence^[코시 수열]**이다:

$$\Leftrightarrow \forall \epsilon > 0, \, \exists N \in \mathbb{N} \text{ such that } \forall m, n \geq N: \, d(x_m, x_n) < \epsilon$$

**의미**: 수열의 항들이 서로 임의로 가까워진다

**정리**: 수렴하는 수열은 Cauchy 수열이다

**증명**: \(x_n \to x\)이면, \(\epsilon/2\)에 대해 \(N\) 존재하여 \(n \geq N\)이면 \(d(x_n, x) < \epsilon/2\)

따라서 \(m, n \geq N\)이면:

$$d(x_m, x_n) \leq d(x_m, x) + d(x, x_n) < \epsilon/2 + \epsilon/2 = \epsilon$$ ✓

## Completeness^[완비성]

**정의**: Metric space \((X, d)\)가 **complete^[완비]**이다

$$\Leftrightarrow \text{모든 Cauchy 수열이 } X \text{에서 수렴}$$

**정리** (**Completeness of } \(\mathbb{R}\)**):

\(\mathbb{R}\)은 complete metric space이다

즉, \(\mathbb{R}\)에서:

$$\text{수렴} \Leftrightarrow \text{Cauchy}$$

**예**:
- \(\mathbb{R}\), \(\mathbb{C}\), \(\mathbb{R}^n\): Complete ✓
- \(\mathbb{Q}\): Not complete (예: \(\sqrt{2}\)로 수렴하는 유리수 Cauchy 수열)
- \((0, 1)\): Not complete (예: \(\frac{1}{n}\))

## Bolzano-Weierstrass Theorem^[볼차노-바이어슈트라스 정리]

**정리** (**Bolzano-Weierstrass Theorem**):

\(\mathbb{R}\)에서 모든 bounded^[유계] 수열은 수렴하는 subsequence^[부분수열]를 갖는다

**\(\mathbb{R}^n\) 버전**: \(\mathbb{R}^n\)에서 모든 bounded 수열은 수렴하는 subsequence를 갖는다

**증명 개요** (실수의 경우):
1. Bounded 수열 \((a_n)\)을 \([a, b]\)에 포함되도록 할 수 있음
2. 구간을 반으로 나누어 무한히 많은 항을 포함하는 쪽 선택 (bisection method^[이분법])
3. 이를 반복하여 nested intervals^[축소구간] \([a_k, b_k]\) 구성
4. \(b_k - a_k = \frac{b-a}{2^k} \to 0\)
5. Completeness에 의해 교집합은 한 점 \(L\)
6. 각 구간에서 선택한 수열의 항들이 \(L\)로 수렴하는 subsequence 형성 ✓

**연결**: Compactness와 관련 (Heine-Borel: bounded + closed = compact)

## Limit Superior and Inferior^[상극한과 하극한]

**정의**: Bounded 실수 수열 \((a_n)\)에 대해:

$$\limsup_{n \to \infty} a_n = \lim_{n \to \infty} \left( \sup_{k \geq n} a_k \right) = \inf_{n} \sup_{k \geq n} a_k$$

$$\liminsup_{n \to \infty} a_n = \lim_{n \to \infty} \left( \inf_{k \geq n} a_k \right) = \sup_{n} \inf_{k \geq n} a_k$$

**성질**:
1. \(\displaystyle\liminf_{n \to \infty} a_n \leq \limsup_{n \to \infty} a_n\)

2. \(\displaystyle\lim_{n \to \infty} a_n\) 존재 \(\Leftrightarrow\) \(\displaystyle\liminf_{n \to \infty} a_n = \limsup_{n \to \infty} a_n\)

3. 이 경우 \(\displaystyle\lim_{n \to \infty} a_n = \limsup_{n \to \infty} a_n = \liminf_{n \to \infty} a_n\)

**직관**:
- \(\limsup\): 수열이 infinitely often^[무한히 자주] 접근하는 가장 큰 값
- \(\liminf\): 수열이 infinitely often 접근하는 가장 작은 값

---

# <span class="header-examples">Examples</span>

## Example 1: 간단한 수렴 수열

$$a_n = \frac{1}{n}$$

$$\lim_{n \to \infty} \frac{1}{n} = 0$$

**증명**: 임의의 \(\epsilon > 0\)에 대해 \(N > \frac{1}{\epsilon}\) (Archimedean property^[아르키메데스 성질])

그러면 \(n \geq N\)이면 \(\left|\frac{1}{n} - 0\right| = \frac{1}{n} \leq \frac{1}{N} < \epsilon\) ✓

## Example 2: 기하수열

$$a_n = r^n \quad (r \in \mathbb{R})$$

**수렴 조건**:
- \(|r| < 1\): \(\displaystyle\lim_{n \to \infty} r^n = 0\)
- \(r = 1\): \(\displaystyle\lim_{n \to \infty} r^n = 1\)
- \(r > 1\): \(\displaystyle\lim_{n \to \infty} r^n = +\infty\) (발산)
- \(r = -1\): 진동 (발산)
- \(r < -1\): 진동하며 발산

## Example 3: 조화급수의 부분합

$$a_n = 1 + \frac{1}{2} + \frac{1}{3} + \cdots + \frac{1}{n} = \sum_{k=1}^{n} \frac{1}{k}$$

$$\lim_{n \to \infty} a_n = +\infty$$

Monotone increasing이지만 unbounded → 발산

## Example 4: 진동 수열

$$a_n = (-1)^n$$

수열: \(-1, 1, -1, 1, \ldots\)

**발산**: 수렴하지 않음 (두 subsequence가 다른 값으로 수렴)

$$\limsup_{n \to \infty} a_n = 1, \quad \liminf_{n \to \infty} a_n = -1$$

## Example 5: Squeeze Theorem 응용

$$a_n = \frac{\sin n}{n}$$

\(-1 \leq \sin n \leq 1\)이므로:

$$-\frac{1}{n} \leq \frac{\sin n}{n} \leq \frac{1}{n}$$

\(\displaystyle\lim_{n \to \infty} \frac{1}{n} = \lim_{n \to \infty} \left(-\frac{1}{n}\right) = 0\)

Squeeze theorem에 의해:

$$\lim_{n \to \infty} \frac{\sin n}{n} = 0$$ ✓

## Example 6: Monotone Convergence

$$a_n = \left(1 + \frac{1}{n}\right)^n$$

**성질**:
- Monotone increasing: \(a_n < a_{n+1}\)
- Bounded above: \(a_n < 3\) for all \(n\)

Monotone convergence theorem에 의해 수렴하고:

$$\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e \approx 2.71828...$$

## Example 7: Cauchy이지만 수렴하지 않는 경우

\(\mathbb{Q}\)에서 수열:

$$a_1 = 1, \quad a_2 = 1.4, \quad a_3 = 1.41, \quad a_4 = 1.414, \ldots$$

(\(\sqrt{2}\)의 decimal expansion)

- \(\mathbb{Q}\)에서 Cauchy ✓
- 하지만 \(\mathbb{Q}\)에서 수렴하지 않음 (\(\sqrt{2} \notin \mathbb{Q}\))
- \(\mathbb{R}\)에서는 \(\sqrt{2}\)로 수렴 ✓

이는 \(\mathbb{Q}\)가 complete하지 않음을 보여줌

## Example 8: Bolzano-Weierstrass 응용

$$a_n = \sin n$$

- Bounded: \(-1 \leq \sin n \leq 1\) ✓
- 수렴하지 않음 (dense한 값들)

하지만 Bolzano-Weierstrass에 의해 수렴하는 subsequence 존재!

실제로 \(\pi\)의 무리성 때문에 \(\{\sin n : n \in \mathbb{N}\}\)는 \([-1, 1]\)에서 dense

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**수렴**: "결국에는 한 점 근처에 머문다"

**발산**: "계속 벗어난다" 또는 "여러 값을 오간다"

**Cauchy**: "항들끼리 가까워진다" (극한 없이도 정의 가능!)

## \(\epsilon\)-\(N\) 정의의 의미

\(\epsilon\)-\(N\) 정의는 Weierstrass가 해석학을 엄밀화하면서 도입:

- \(\epsilon\): 임의로 작은 오차 허용 범위
- \(N\): 충분히 큰 index (이후로는 오차 범위 내)
- "임의의 \(\epsilon\)"이 먼저, "적절한 \(N\) 존재"가 나중 (순서 중요!)

## Metric Space vs Topological Space

**Metric space**: \(\epsilon\)-\(\delta\) 정의 (거리 이용)

**Topological space**: Open set 정의

**차이점**:
- Metric space: 수열로 모든 위상적 성질 특징지을 수 있음
- General topological space: 수열로 부족 (net이나 filter 필요)

**예**: First-countable^[제1가산] 공간에서는 수열로 충분

## Completeness의 중요성

**Complete space**:
- 내부에서 "닫혀" 있음 (Cauchy 수열의 극한이 항상 존재)
- 해석학의 많은 정리들이 completeness 의존
- 예: Contraction mapping theorem^[축약사상정리], Baire category theorem^[베르 범주 정리]

**\(\mathbb{R}\)의 construction**:
- Cauchy 수열로 \(\mathbb{R}\) 구성 가능 (Dedekind cut의 대안)
- \(\mathbb{Q}\)의 completion

## Rate of Convergence^[수렴 속도]

수렴 속도를 측정하는 방법들:

**Linear convergence^[선형 수렴]**: \(|a_n - L| \leq C \cdot r^n\) for some \(0 < r < 1\)

**Quadratic convergence^[이차 수렴]**: \(|a_{n+1} - L| \leq C |a_n - L|^2\)

**예**:
- \(\frac{1}{n}\): Slow (\(\frac{1}{n}\))
- \(r^n\) with \(|r| < 1\): Exponential (geometric)
- Newton's method: Quadratic

## 응용 분야

### 1. Numerical Analysis^[수치해석]

수치 알고리즘의 수렴성 분석:
- Iterative methods^[반복법]
- Root finding algorithms^[근 찾기 알고리즘]
- Convergence criteria^[수렴 판정]

### 2. Probability Theory^[확률론]

**Law of Large Numbers^[큰 수의 법칙]**:

$$\lim_{n \to \infty} \frac{1}{n} \sum_{i=1}^{n} X_i = \mathbb{E}[X]$$

(거의 확실하게)

### 3. Fourier Analysis^[푸리에 해석]

Fourier series의 수렴:
- Pointwise convergence^[점별 수렴]
- Uniform convergence^[균등 수렴]
- \(L^2\) convergence

### 4. Optimization^[최적화]

Gradient descent^[경사하강법]와 같은 알고리즘의 수렴 보장

### 5. Differential Equations^[미분방정식]

해의 존재성 증명 (Picard iteration)

## 일반화

**Net**: 일반 topological space에서 수열의 일반화

**Filter**: 또 다른 일반화 (dual notion to net)

**Modes of Convergence**:
- Pointwise^[점별]
- Uniform^[균등]
- \(L^p\)
- Almost everywhere^[거의 모든 곳에서]
- In measure^[측도에서]

## 역사적 배경

**Augustin-Louis Cauchy** (1789-1857):
- Cauchy 수열 정의
- 엄밀한 극한 개념 도입

**Karl Weierstrass** (1815-1897):
- \(\epsilon\)-\(\delta\) 정의
- 해석학의 엄밀화

**Bernhard Bolzano** (1781-1848):
- Bolzano-Weierstrass theorem
- Intermediate value theorem

**Richard Dedekind** (1831-1916):
- Dedekind cut으로 실수 구성

## Common Pitfalls^[흔한 실수]

1. **\(\epsilon\)과 \(N\)의 순서 혼동**
   - 올바름: \(\forall \epsilon\) \(\exists N\) ✓
   - 잘못됨: \(\exists N\) \(\forall \epsilon\) ✗

2. **Bounded ≠ Convergent**
   - 반례: \((-1)^n\)

3. **Convergent subsequence ≠ Convergent sequence**
   - 반례: \((-1)^n\)은 수렴하는 subsequence를 가짐

4. **\(\mathbb{Q}\)에서의 Cauchy ≠ 수렴**
   - \(\mathbb{Q}\)는 complete하지 않음

## 관련 개념

- [[Limit Point]]: 집합론적 극한점과 수열의 극한 연결
- [[Metric Space]]: 수렴의 일반적 framework
- [[Cauchy Sequence]]: Completeness의 핵심
- [[Continuous Function]]: 수렴 수열 보존
- [[Series]]: 수열의 부분합으로 정의
- [[Topology]]: 수렴의 위상적 일반화

