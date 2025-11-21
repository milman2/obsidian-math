# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Borel Sigma Algebra]]
- Set theory (집합론 기초)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Probability^[확률]

**Probability**^[확률]는 불확실한 사건^[사건]의 발생 가능성을 수량화하는 측도^[측도]이다.

Formally, probability는 **probability measure**^[확률 측도] $P: \mathcal{F} \rightarrow [0, 1]$로 정의되며, Kolmogorov axioms^[콜모고로프 공리]를 만족한다.

**상세한 수학적 정의**: [[Sample Spaces]] 참조

### Key components^[핵심 구성 요소]

Probability를 다루기 위한 수학적 프레임워크:

1. **[[Sample Spaces]]** $\Omega$: 가능한 모든 결과들의 집합
2. **Event space^[사건 공간]** $\mathcal{F}$: Sigma algebra of events
3. **Probability measure^[확률 측도]** $P$: $[0, 1]$ 값을 할당

Triple $(\Omega, \mathcal{F}, P)$를 **probability space**^[확률 공간]이라 한다.

---

# <span class="header-properties">Interpretations of Probability</span>

확률의 의미를 해석하는 여러 관점들:

## Classical interpretation^[고전적 해석]

**Equally likely outcomes^[동등하게 가능한 결과]** 가정:

$$P(E) = \frac{\text{number of favorable outcomes}}{\text{total number of outcomes}} = \frac{|E|}{|\Omega|}$$

### Example: Fair die^[공정한 주사위]

$$P(\text{even number}) = \frac{3}{6} = \frac{1}{2}$$

### Limitation^[한계]
- Finite sample space에만 적용 가능
- "Equally likely"의 순환 정의 문제

## Frequentist interpretation^[빈도주의 해석]

Probability는 **장기적 빈도^[long-run frequency]**:

$$P(E) = \lim_{n \to \infty} \frac{\text{number of times } E \text{ occurs}}{n}$$

### Example: Coin flip^[동전 던지기]

동전을 $n$번 던졌을 때 앞면 비율:
$$\frac{\text{# heads}}{n} \xrightarrow{n \to \infty} P(\text{heads}) = 0.5$$

이는 **Law of large numbers**^[큰 수의 법칙]로 정당화됨.

### Strength^[강점]
- 실험적으로 검증 가능
- 통계학의 기초

### Limitation^[한계]
- 반복 불가능한 사건에는 부적합 (예: "내일 비 올 확률")
- 무한 반복은 현실적으로 불가능

## Bayesian interpretation^[베이지안 해석]

Probability는 **subjective belief^[주관적 믿음]**의 정도:

$$P(E) = \text{degree of belief that } E \text{ will occur}$$

새로운 evidence^[증거]를 관찰하면 belief를 update:

$$P(\text{hypothesis} | \text{evidence}) = \frac{P(\text{evidence} | \text{hypothesis}) \cdot P(\text{hypothesis})}{P(\text{evidence})}$$

**상세한 내용**: [[Bayes' Rule]] 참조

### Strength^[강점]
- 일회성 사건에도 적용 가능
- 사전 지식을 체계적으로 통합

### Limitation^[한계]
- Prior^[사전 확률]의 주관성
- 서로 다른 prior는 다른 결론 도출 가능

## Propensity interpretation^[성향 해석]

Probability는 물리적 시스템의 **고유한 성향^[inherent propensity]**:

양자역학에서 입자의 위치 측정 확률은 시스템의 물리적 성질.

---

# <span class="header-remark">Core Concepts</span>

## Probability measure^[확률 측도]

**Kolmogorov axioms**^[콜모고로프 공리] (1933):

1. $P(E) \geq 0$ (Non-negativity^[비음성])
2. $P(\Omega) = 1$ (Normalization^[정규화])
3. Countable additivity^[가산 가법성]

이 공리들로부터 모든 확률 이론이 유도됨.

**상세한 성질**: [[Sample Spaces]] 참조

## Random variables^[확률 변수]

확률 실험의 결과를 수치화하는 함수 $X: \Omega \rightarrow \mathbb{R}$:

$$P(X \in B) = P(\{\omega : X(\omega) \in B\})$$

**상세한 내용**: [[Random Variables]] 참조

## Conditional probability^[조건부 확률]

새로운 정보가 주어졌을 때 확률 업데이트:

$$P(A | B) = \frac{P(A \cap B)}{P(B)}$$

**상세한 내용**: [[Conditional Probability]] 참조

## Independence^[독립]

Events $A$, $B$가 **independent**^[독립] $\Leftrightarrow$:

$$P(A \cap B) = P(A) \cdot P(B)$$

즉, $B$의 발생이 $A$의 확률에 영향을 주지 않음.

**상세한 내용**: [[Sample Spaces]], [[Conditional Probability]] 참조

## Expected value^[기댓값]

Random variable의 "평균값":

$$E[X] = \int_\Omega X \, dP$$

**상세한 내용**: [[Expected Value]] 참조

---

# <span class="header-examples">Examples and Applications</span>

## Gambling and games of chance^[도박과 우연 게임]

확률론의 역사적 기원 (16-17세기):
- Cardano, Fermat, Pascal의 주사위/카드 게임 분석
- Fair game^[공정한 게임]의 개념

**Example**: Coin toss^[동전 던지기]
- Sample space: $\Omega = \{H, T\}$
- $P(H) = P(T) = \frac{1}{2}$ (fair coin)

## Statistics and data analysis^[통계와 데이터 분석]

- Parameter estimation^[모수 추정]
- Hypothesis testing^[가설 검정]
- Confidence intervals^[신뢰 구간]
- Regression^[회귀 분석]

Probability는 통계적 추론의 이론적 기초.

## Physics^[물리학]

### Statistical mechanics^[통계 역학]
- Gas molecules의 운동 → Maxwell-Boltzmann distribution
- Entropy^[엔트로피]와 probability

### Quantum mechanics^[양자 역학]
- Wave function $|\psi|^2$ → Probability density
- Heisenberg uncertainty principle^[하이젠베르크 불확정성 원리]
- Born rule^[본 규칙]

## Machine learning and AI

### Probabilistic models
- **Naive Bayes classifier**^[나이브 베이즈 분류기]
- **Hidden Markov models**^[은닉 마르코프 모델]
- **Bayesian networks**^[베이지안 네트워크]

### Inference and learning
- Maximum likelihood estimation^[최대 가능도 추정]
- Bayesian inference^[베이지안 추론]: [[Bayes' Rule]]
- Variational inference^[변분 추론]

### Deep learning
- Dropout^[드롭아웃]: Probabilistic regularization
- Stochastic gradient descent^[확률적 경사 하강법]
- Generative models^[생성 모델] (VAE, GAN)

## Finance and economics^[금융과 경제]

- **Asset pricing^[자산 가격 결정]**: Black-Scholes model
- **Risk management^[위험 관리]**: Value at Risk (VaR)
- **Portfolio optimization^[포트폴리오 최적화]**: Markowitz theory
- **Insurance^[보험]**: Actuarial science^[보험계리학]

## Biology and medicine^[생물학과 의학]

- **Genetics^[유전학]**: Mendelian inheritance
- **Epidemiology^[역학]**: Disease spread models
- **Clinical trials^[임상 시험]**: Treatment effect estimation
- **Medical diagnosis^[의학 진단]**: [[Conditional Probability]] 예제 참조

## Engineering^[공학]

- **Reliability theory^[신뢰성 이론]**: System failure probability
- **Signal processing^[신호 처리]**: Noise modeling
- **Control theory^[제어 이론]**: Stochastic control
- **Telecommunications^[통신]**: Error correction codes

---

# <span class="header-theorem">Fundamental Theorems</span>

## Law of large numbers^[큰 수의 법칙]

Independent, identically distributed (i.i.d.) random variables $X_1, X_2, \ldots$에 대해:

$$\frac{X_1 + \cdots + X_n}{n} \xrightarrow{n \to \infty} E[X]$$

이는 frequentist interpretation을 정당화.

### Weak law^[약한 법칙]
Convergence in probability^[확률 수렴]:
$$\forall \epsilon > 0, \quad P\left(\left|\frac{X_1 + \cdots + X_n}{n} - E[X]\right| > \epsilon\right) \xrightarrow{n \to \infty} 0$$

### Strong law^[강한 법칙]
Almost sure convergence^[거의 확실한 수렴]:
$$P\left(\lim_{n \to \infty} \frac{X_1 + \cdots + X_n}{n} = E[X]\right) = 1$$

## Central limit theorem^[중심극한정리]

I.i.d. random variables $X_1, X_2, \ldots$에 대해 ($E[X_i] = \mu$, $\text{Var}(X_i) = \sigma^2$):

$$\frac{X_1 + \cdots + X_n - n\mu}{\sigma\sqrt{n}} \xrightarrow{d} \mathcal{N}(0, 1)$$

평균의 분포는 $n$이 크면 **정규 분포^[normal distribution]**에 가까워짐!

### Importance^[중요성]
- 많은 자연/사회 현상이 정규 분포를 따르는 이유 설명
- 통계적 추론의 이론적 기초
- Sample mean의 분포 근사

## Bayes' theorem^[베이즈 정리]

$$P(H | E) = \frac{P(E | H) \cdot P(H)}{P(E)}$$

Prior belief를 evidence로 update하여 posterior belief 계산.

**상세한 내용**: [[Bayes' Rule]] 참조

## Law of total probability^[전확률 공식]

Partition $\{B_i\}$에 대해:

$$P(A) = \displaystyle\sum_i P(A | B_i) \cdot P(B_i)$$

**상세한 내용**: [[Law of Total Probability]] 참조

---

# <span class="header-remark">Historical Development</span>

## Origins^[기원] (16-17th century)

### Cardano (1501-1576)
- "Liber de Ludo Aleae" (Book on Games of Chance)
- 최초의 체계적인 확률 계산

### Fermat & Pascal (1654)
- "Problem of points"^[점수 문제] 서신 교환
- 기댓값과 공정한 분배 개념

## Classical period^[고전기] (18th century)

### Jakob Bernoulli (1654-1705)
- "Ars Conjectandi" (The Art of Conjecturing)
- Law of large numbers의 최초 증명

### De Moivre (1667-1754)
- Normal distribution 발견
- Central limit theorem의 특수 경우

### Laplace (1749-1827)
- "Théorie Analytique des Probabilités"
- Classical probability theory 체계화
- Bayesian inference의 선구자

## Modern foundations^[현대적 기초] (20th century)

### Kolmogorov (1933)
- "Foundations of the Theory of Probability"
- Measure-theoretic formulation^[측도론적 정식화]
- 현대 확률론의 공리적 기초 확립

이후 확률론은 엄밀한 수학 이론으로 발전.

---

# <span class="header-remark">Probability vs Statistics</span>

| | **Probability^[확률론]** | **Statistics^[통계학]** |
|---|---|---|
| **Direction** | Model → Data | Data → Model |
| **Question** | "주어진 모델에서 어떤 데이터가 나올까?" | "주어진 데이터로부터 어떤 모델을 추론할까?" |
| **Nature** | Deductive^[연역적] | Inductive^[귀납적] |
| **Example** | Fair coin 100번 던지면 앞면 약 50번 | 100번 중 53번 앞면 → Coin이 fair한가? |
| **Goal** | Theoretical framework | Data analysis & inference |

**관계**: Statistics는 probability theory를 기반으로 한 응용 분야.

---

# <span class="header-remark">Common Misconceptions</span>

## Gambler's fallacy^[도박사의 오류]

"동전을 5번 던져서 모두 앞면이 나왔으니, 다음은 뒷면이 나올 확률이 높다"

**Wrong!** Independent events^[독립 사건]에서는 과거가 미래에 영향 없음:
$$P(\text{heads on 6th toss} | \text{5 heads}) = P(\text{heads}) = 0.5$$

## Hot hand fallacy^[핫핸드 오류]

"농구 선수가 연속으로 성공했으니 다음도 성공할 확률이 높다"

통계적 분석 결과: 대부분의 경우 착각 (random streak^[무작위 연속])

## Prosecutor's fallacy^[검사의 오류]

$P(\text{evidence} | \text{innocent})$가 작다고 $P(\text{innocent} | \text{evidence})$가 작은 것은 아님!

**올바른 계산**: [[Bayes' Rule]] 사용

## Base rate neglect^[기저율 무시]

희귀 질병의 검사에서 양성이 나왔을 때, 실제 질병일 확률은?

Prior probability $P(\text{disease})$를 고려해야 함.

**예시**: [[Conditional Probability]]의 medical test 예제 참조

---

# <span class="header-remark">Related Topics</span>

## Foundation and core concepts
- [[Sample Spaces]]: 수학적 기초
- [[Borel Sigma Algebra]]: 측도론적 배경
- [[Random Variables]]: 확률 변수
- [[Conditional Probability]]: 조건부 확률
- [[Expected Value]]: 기댓값

## Advanced topics
- **Stochastic processes^[확률 과정]**: Time-dependent random phenomena
- **Markov chains^[마르코프 연쇄]**: Memoryless random processes
- **Martingales^[마팅게일]**: Fair game generalization
- **Brownian motion^[브라운 운동]**: Continuous random walk
- **Information theory^[정보 이론]**: Entropy and information

## Applications
- [[Bayes' Rule]]: Bayesian inference
- [[Law of Total Probability]]: 확률 계산 전략
- **Statistical inference^[통계적 추론]**
- **Machine learning^[기계 학습]**
- **Quantitative finance^[계량 금융]**

---

# <span class="header-examples">핵심 개념 요약</span>

```
Probability Space (Ω, ℱ, P)
    ↓
Sample Space Ω (모든 가능한 결과)
    ↓
Events E ∈ ℱ (관심 있는 결과 집합)
    ↓
Probability Measure P(E) (0과 1 사이 값)
    ↓
Random Variables X: Ω → ℝ (결과를 수치화)
    ↓
Distribution P_X (확률 측도 유도)
    ↓
Expected Value E[X] (평균값)
    ↓
Statistical Inference (데이터로부터 학습)
```

---

**수학적 정의**: [[Sample Spaces]], [[Random Variables]]
**분포 함수**: [[Probability Mass Function]], [[Probability Density Function]]
**핵심 정리**: [[Joint Probabilities]], [[Marginal Probabilities]], [[Conditional Probability]], [[Law of Total Probability]], [[Bayes' Rule]]
**주요 개념**: [[Expected Value]], [[Recursive Thinking]]
**계수 기법**: [[Permutations and Combinations]]
