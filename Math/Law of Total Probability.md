# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Conditional Probability]]

# <span class="header-reference">Reference</span>

---

# <span class="header-theorem">Theorem</span>

## Law of total probability^[전확률 공식]

**Statement^[진술]**: Probability space^[확률 공간] $(\Omega, \mathcal{F}, P)$에서, $\{B_i\}_{i \in I}$가 $\Omega$의 **partition^[분할]**이면 (즉, $B_i \cap B_j = \emptyset$ for $i \neq j$이고 $\displaystyle\bigcup_{i \in I} B_i = \Omega$), 임의의 event $A \in \mathcal{F}$에 대해:

$$P(A) = \displaystyle\sum_{i \in I} P(A | B_i) \cdot P(B_i)$$

(단, $P(B_i) > 0$ for all $i$)

### Interpretation^[해석]

Event $A$가 발생할 확률을 "어떤 경로로 $A$에 도달하는가"로 분해:
- $B_i$를 경유해서 $A$에 도달할 확률: $P(A | B_i) \cdot P(B_i)$
- 모든 가능한 경로를 합산

---

# <span class="header-proof">Proof</span>

## Basic proof^[기본 증명]

$A$를 partition $\{B_i\}$에 의해 분해:

$$A = A \cap \Omega = A \cap \left(\displaystyle\bigcup_{i \in I} B_i\right) = \displaystyle\bigcup_{i \in I} (A \cap B_i)$$

$B_i$들이 disjoint^[서로소]이므로 $A \cap B_i$들도 disjoint.

Countable additivity^[가산 가법성]에 의해:

$$P(A) = P\left(\displaystyle\bigcup_{i \in I} (A \cap B_i)\right) = \displaystyle\sum_{i \in I} P(A \cap B_i)$$

Conditional probability^[조건부 확률]의 정의 $P(A \cap B_i) = P(A | B_i) \cdot P(B_i)$를 적용:

$$P(A) = \displaystyle\sum_{i \in I} P(A | B_i) \cdot P(B_i)$$

$\square$

## Intuitive interpretation^[직관적 해석]

"$A$가 일어나려면 어떤 $B_i$를 거쳐야만 한다"는 관점:

```
          P(B₁)
     ───────────► B₁ ───P(A|B₁)───►
    ╱            P(B₂)               ╲
   Ω ────────────► B₂ ───P(A|B₂)────► A
    ╲            P(B₃)               ╱
     ───────────► B₃ ───P(A|B₃)───►
```

각 경로의 확률을 곱하고, 모든 경로를 합산.

---

# <span class="header-examples">Examples</span>

## 1. Factory production^[공장 생산]

세 공장 A, B, C가 제품을 생산:
- A: 전체의 30%, 불량률 2%
- B: 전체의 50%, 불량률 3%
- C: 전체의 20%, 불량률 5%

**Question**: 랜덤하게 선택한 제품이 불량일 확률은?

**Solution**: 
$D$ = {불량}, 공장들이 partition을 형성.

$$P(D) = P(D | A) \cdot P(A) + P(D | B) \cdot P(B) + P(D | C) \cdot P(C)$$

$$= 0.02 \times 0.30 + 0.03 \times 0.50 + 0.05 \times 0.20$$

$$= 0.006 + 0.015 + 0.010 = 0.031 = 3.1\%$$

## 2. Disease screening^[질병 검사]

모집단을 연령대로 분할:
- 20-30대 (40%): 질병 유병률 1%
- 40-50대 (35%): 질병 유병률 5%
- 60대+ (25%): 질병 유병률 15%

**Question**: 랜덤하게 선택한 사람이 질병이 있을 확률은?

**Solution**:
$$P(D) = \displaystyle\sum_{\text{age}} P(D | \text{age}) \cdot P(\text{age})$$

$$= 0.01 \times 0.40 + 0.05 \times 0.35 + 0.15 \times 0.25$$

$$= 0.004 + 0.0175 + 0.0375 = 0.059 = 5.9\%$$

## 3. Recursive application^[재귀적 적용]

첫 번째 동전 던지기 결과에 따라 두 번째 동전 선택:
- Heads (H): Fair coin 사용 (H 확률 50%)
- Tails (T): Biased coin 사용 (H 확률 80%)

**Question**: 두 번째 동전이 Heads일 확률은?

**Solution**:

먼저 첫 번째 동전: $P(H_1) = P(T_1) = 0.5$

$$P(H_2) = P(H_2 | H_1) \cdot P(H_1) + P(H_2 | T_1) \cdot P(T_1)$$

$$= 0.5 \times 0.5 + 0.8 \times 0.5 = 0.25 + 0.4 = 0.65$$

---

# <span class="header-properties">Properties and Extensions</span>

## Finite vs Countable^[유한 vs 가산]

### Finite partition
Index set $I$가 유한이면 합은 유한합:
$$P(A) = \displaystyle\sum_{i=1}^n P(A | B_i) \cdot P(B_i)$$

### Countable partition
Index set $I$가 가산무한이면 무한급수:
$$P(A) = \displaystyle\sum_{i=1}^\infty P(A | B_i) \cdot P(B_i)$$

급수의 수렴성은 $\displaystyle\sum_{i=1}^\infty P(B_i) = 1$에 의해 보장됨.

## Continuous version^[연속 버전]

Random variable^[확률 변수] $X$에 대해, 조건부 확률을 적분으로 확장:

$$P(A) = \int_{\mathbb{R}} P(A | X = x) \, dP_X(x)$$

또는 $X$가 density^[밀도] $f_X(x)$를 가지면:

$$P(A) = \int_{\mathbb{R}} P(A | X = x) \cdot f_X(x) \, dx$$

### Example: Mixture distribution^[혼합 분포]

Parameter^[모수] $\theta$가 분포를 가질 때:

$$P(A) = \int P(A | \theta) \, dP(\theta)$$

이는 Bayesian statistics의 핵심 개념.

## Generalization to expectation^[기댓값으로 일반화]

Random variable^[확률 변수] $X$의 expectation^[기댓값]:

$$E[X] = \displaystyle\sum_i E[X | B_i] \cdot P(B_i)$$

Continuous case:
$$E[X] = \int E[X | Y = y] \cdot f_Y(y) \, dy$$

이는 **Tower property^[탑 성질]** $E[X] = E[E[X | Y]]$의 특수 경우.

**상세한 내용**: [[Expected Value]] 참조

---

# <span class="header-remark">Remark</span>

## Relation to Bayes' theorem^[베이즈 정리와의 관계]

Law of total probability는 종종 Bayes' theorem의 분모로 사용됨:

$$P(B_i | A) = \frac{P(A | B_i) \cdot P(B_i)}{P(A)} = \frac{P(A | B_i) \cdot P(B_i)}{\displaystyle\sum_j P(A | B_j) \cdot P(B_j)}$$

이는 **[[Bayes' Rule]]**의 핵심.

## Computational strategy^[계산 전략]

복잡한 확률 계산을 단순화하는 전략:
1. 적절한 partition 선택 (조건부 확률이 쉽게 계산되는)
2. 각 부분에서 조건부 확률 계산
3. 가중 평균 (weight = $P(B_i)$)

## Choice of partition^[분할 선택]

효과적인 partition의 조건:
- **Exhaustive^[완전]**: $\displaystyle\bigcup_i B_i = \Omega$
- **Mutually exclusive^[상호 배타적]**: $B_i \cap B_j = \emptyset$
- **Natural^[자연스러움]**: 조건부 확률 $P(A | B_i)$가 쉽게 계산됨
- **Not too fine^[너무 세밀하지 않음]**: 계산 복잡도 고려

### Good partitions
- 원인별 분할 (공장, 질병 유형 등)
- 단계별 분할 (첫 번째 단계 결과)
- 자연스러운 범주 (연령대, 지역 등)

### Bad partitions
- 너무 많은 부분 (계산 복잡)
- 조건부 확률이 원래 확률보다 복잡
- 불균등한 크기 (일부 $P(B_i) \approx 0$)

## Connection to marginalization^[주변화와의 연결]

Joint distribution^[결합 분포] $P(A, B)$에서 marginal^[주변] 분포:

$$P(A) = \displaystyle\sum_b P(A, B = b) = \displaystyle\sum_b P(A | B = b) \cdot P(B = b)$$

이는 Law of total probability와 동일한 원리.

Continuous case:
$$f_X(x) = \int f_{X,Y}(x, y) \, dy = \int f_{X|Y}(x|y) \cdot f_Y(y) \, dy$$

## Applications^[응용]

### Probability theory
- Complex event probability calculation
- Mixture distributions
- Hierarchical models^[계층 모델]

### Statistics
- Missing data^[결측 데이터] imputation^[대체]
- EM algorithm^[EM 알고리즘]
- Model averaging^[모델 평균화]

### Machine learning
- Ensemble methods^[앙상블 방법]
- Mixture of experts^[전문가 혼합]
- Latent variable^[잠재 변수] models

### Decision theory^[의사결정 이론]
- Risk assessment^[위험 평가]
- Scenario analysis^[시나리오 분석]
- Multi-stage decision problems

---

# <span class="header-examples">Visual representation</span>

## Venn diagram perspective

```
        Ω (전체 공간)
    ┌─────────────────────┐
    │  ┌───┐  ┌───┐       │
    │  │ B₁│  │ B₂│       │
    │  │┌─┐│  │┌─┐│       │
    │  ││A││  ││A││  ┌───┐│
    │  │└─┘│  │└─┘│  │ B₃││
    │  └───┘  └───┘  │┌─┐││
    │                ││A│││
    │                │└─┘││
    │                └───┘│
    └─────────────────────┘
```

$A$를 각 $B_i$로 "조각내고", 각 조각의 확률을 합산.

## Tree diagram

```
                    ╱ A  [P(A|B₁)]
              B₁ ──┤
             [P(B₁)]╲ A' [P(A'|B₁)]
            ╱
           ╱         ╱ A  [P(A|B₂)]
          ╱    B₂ ──┤
         ╱   [P(B₂)] ╲ A' [P(A'|B₂)]
    Start           
         ╲            ╱ A  [P(A|B₃)]
          ╲     B₃ ──┤
           ╲  [P(B₃)] ╲ A' [P(A'|B₃)]
            ╲
```

$P(A) = \displaystyle\sum_i P(B_i) \cdot P(A | B_i)$ (각 경로의 확률 합)

---

**확률론 개관**: [[Probability]]
**기본 정의**: [[Sample Spaces]], [[Conditional Probability]]
**관련 주제**: [[Bayes' Rule]], [[Expected Value]]
