# <span class="header-prerequisite">Prerequisite</span>
- Set theory (집합론 기초)
- Topology (위상수학 기초)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Sigma algebra^[시그마 대수]

집합 $X$에 대해, $X$의 부분집합들의 모임 $\mathcal{F}$가 **sigma algebra**^[시그마 대수] (또는 $\sigma$-algebra)이다 $\Leftrightarrow$ 다음을 만족:

1. $X \in \mathcal{F}$ (전체 집합 포함)
2. $A \in \mathcal{F} \Rightarrow A^c \in \mathcal{F}$ (complement^[여집합]에 대해 닫힘)
3. $A_1, A_2, \ldots \in \mathcal{F} \Rightarrow \displaystyle\bigcup_{n=1}^\infty A_n \in \mathcal{F}$ (countable union^[가산 합]에 대해 닫힘)

쌍 $(X, \mathcal{F})$를 **measurable space**^[가측 공간]이라 한다.

### 기본 성질

Sigma algebra는 다음도 만족:
- $\emptyset \in \mathcal{F}$ (공집합 포함)
- Countable intersection^[가산 교집합]에 대해 닫힘: $\displaystyle\bigcap_{n=1}^\infty A_n \in \mathcal{F}$

## Borel sigma algebra^[보렐 시그마 대수]

Topological space^[위상 공간] $(X, \tau)$에 대해, **Borel sigma algebra**^[보렐 시그마 대수] $\mathcal{B}(X)$는:

$$\mathcal{B}(X) = \sigma(\tau)$$

즉, open sets^[열린집합]들을 포함하는 **smallest sigma algebra**^[최소 시그마 대수]이다.

$\mathcal{B}(X)$의 원소를 **Borel sets**^[보렐 집합]이라 한다.

### Generated sigma algebra^[생성된 시그마 대수]

집합 $X$와 $X$의 부분집합들의 모임 $\mathcal{E}$에 대해:

$$\sigma(\mathcal{E}) = \bigcap \{\mathcal{F} : \mathcal{F} \text{ is a sigma algebra containing } \mathcal{E}\}$$

이는 $\mathcal{E}$를 포함하는 최소 sigma algebra이다.

---

# <span class="header-properties">Properties</span>

## Borel sets의 구조

$\mathbb{R}$의 Borel sigma algebra $\mathcal{B}(\mathbb{R})$는 다음에 의해 생성된다:

1. Open intervals: $(a, b)$ for $a < b$
2. Closed intervals: $[a, b]$ for $a \leq b$
3. Half-open intervals: $(a, b]$ or $[a, b)$
4. Rays: $(-\infty, a)$, $(-\infty, a]$, $(a, \infty)$, $[a, \infty)$

이들 중 **어느 하나**로도 $\mathcal{B}(\mathbb{R})$를 생성할 수 있다.

## Borel hierarchy^[보렐 계층]

Borel sets는 복잡도에 따라 계층 구조를 이룬다:

- $\Sigma^0_1$: Open sets^[열린집합]
- $\Pi^0_1$: Closed sets^[닫힌집합]
- $\Sigma^0_2$: Countable unions of closed sets (= $F_\sigma$ sets)
- $\Pi^0_2$: Countable intersections of open sets (= $G_\delta$ sets)
- $\vdots$

모든 Borel set는 어떤 countable ordinal^[가산 서수] $\alpha$에 대해 이 계층에 속한다.

## Product sigma algebra^[곱 시그마 대수]

$(X_1, \mathcal{F}_1)$, $(X_2, \mathcal{F}_2)$가 measurable spaces이면:

$$\mathcal{F}_1 \otimes \mathcal{F}_2 = \sigma(\{A_1 \times A_2 : A_1 \in \mathcal{F}_1, A_2 \in \mathcal{F}_2\})$$

**중요**: $\mathcal{B}(\mathbb{R}^n) = \mathcal{B}(\mathbb{R}) \otimes \cdots \otimes \mathcal{B}(\mathbb{R})$ ($n$번)

---

# <span class="header-examples">Examples</span>

## 1. Trivial sigma algebras

**Smallest**: $\mathcal{F} = \{\emptyset, X\}$

**Largest**: $\mathcal{F} = \mathcal{P}(X)$ (power set^[멱집합])

## 2. $\mathcal{B}(\mathbb{R})$ (Real line)

$\mathbb{R}$의 standard topology에 대한 Borel sigma algebra.

**Examples of Borel sets**:
- All open intervals: $(a, b)$
- All closed intervals: $[a, b]$
- Countable sets: $\mathbb{Q}$, $\mathbb{Z}$
- Cantor set^[칸토어 집합]
- Irrational numbers $\mathbb{R} \setminus \mathbb{Q}$

**Non-Borel sets**: Vitali set^[비탈리 집합] (with Axiom of Choice^[선택 공리])

## 3. $\mathcal{B}(\mathbb{R}^n)$

$n$-dimensional Euclidean space의 Borel sigma algebra.

Open balls, closed balls, rectangles 등을 포함.

## 4. Discrete space

$X$가 discrete topology^[이산 위상]를 가지면:
$$\mathcal{B}(X) = \mathcal{P}(X)$$

모든 부분집합이 Borel set.

## 5. Indiscrete space

$X$가 indiscrete topology^[비이산 위상] $\{\emptyset, X\}$를 가지면:
$$\mathcal{B}(X) = \{\emptyset, X\}$$

---

# <span class="header-remark">Remark</span>

## Measure theory^[측도론]와의 관계

**Measure**^[측도] $\mu$는 함수 $\mu: \mathcal{F} \rightarrow [0, \infty]$로:
- $\mu(\emptyset) = 0$
- Countable additivity^[가산 가법성]: Disjoint sets $A_1, A_2, \ldots$에 대해
  $$\mu\left(\displaystyle\bigcup_{n=1}^\infty A_n\right) = \displaystyle\sum_{n=1}^\infty \mu(A_n)$$

Borel sigma algebra는 measure를 정의하는 자연스러운 domain^[정의역]을 제공한다.

## Probability theory^[확률론]와의 관계

**Probability space**^[확률 공간] $(\Omega, \mathcal{F}, P)$:
- $\Omega$: Sample space^[표본 공간]
- $\mathcal{F}$: Sigma algebra of events^[사건들의 시그마 대수]
- $P$: Probability measure^[확률 측도] ($P(\Omega) = 1$)

$\mathbb{R}$-valued random variable^[확률 변수] $X: \Omega \rightarrow \mathbb{R}$는:
$$X^{-1}(B) \in \mathcal{F} \quad \forall B \in \mathcal{B}(\mathbb{R})$$

즉, **measurable function**^[가측 함수]이어야 한다.

## Lebesgue measure^[르베스그 측도]

$\mathbb{R}$에서 가장 중요한 measure:

$$\lambda([a, b]) = b - a$$

Lebesgue measure는 $\mathcal{B}(\mathbb{R})$에서 정의되며:
- Translation invariant^[평행이동 불변]
- Countably additive^[가산 가법적]

**Lebesgue measurable sets**: $\mathcal{B}(\mathbb{R})$를 포함하는 더 큰 sigma algebra

## Cardinality^[기수]

$\mathcal{B}(\mathbb{R})$의 cardinality:
$$|\mathcal{B}(\mathbb{R})| = \mathfrak{c} = 2^{\aleph_0}$$

(continuum^[연속체])

하지만 $|\mathcal{P}(\mathbb{R})| = 2^{\mathfrak{c}} > \mathfrak{c}$이므로, non-Borel sets^[비보렐 집합]이 존재한다.

## Continuous functions^[연속함수]

$f: X \rightarrow Y$가 continuous^[연속]이면, $f$는 Borel measurable^[보렐 가측]:

$$f^{-1}(B) \in \mathcal{B}(X) \quad \forall B \in \mathcal{B}(Y)$$

따라서: Continuous functions preserve Borel structure.

## Applications^[응용]

### Integration theory^[적분 이론]
Lebesgue integral^[르베스그 적분]은 measurable functions에 대해 정의:
$$\int_X f \, d\mu$$

### Probability theory^[확률론]
Random variables, expectations^[기댓값], distributions^[분포]

### Stochastic processes^[확률 과정]
Filtrations^[여과], stopping times^[정지 시간]

### Ergodic theory^[에르고딕 이론]
Measure-preserving transformations^[측도 보존 변환]

---

# <span class="header-examples">구조 요약</span>

```
Topology (열린집합들)
    ↓ generate
Borel sigma algebra (최소 시그마 대수)
    ↓ define measure on
Measure space (측도 공간)
    ↓ integrate on
Lebesgue integration (르베스그 적분)
```

## 핵심 개념

**Borel sigma algebra = Topology를 측도론으로 연결하는 다리**

- Topology: 연속성, 수렴
- Borel sets: 가측성
- Measure: 크기, 확률
- Integration: 함수의 평균, 기댓값

