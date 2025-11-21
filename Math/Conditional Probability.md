# <span class="header-prerequisite">Prerequisite</span>
- [[Sample Spaces]]
- [[Borel Sigma Algebra]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Conditional probability^[조건부 확률]

Probability space^[확률 공간] $(\Omega, \mathcal{F}, P)$에서, event $B \in \mathcal{F}$가 주어졌을 때 ($P(B) > 0$), event $A$의 **conditional probability**^[조건부 확률]는:

$$P(A | B) = \frac{P(A \cap B)}{P(B)}$$

이는 "$B$가 발생했을 때 $A$가 발생할 확률"을 의미한다.

### Conditional probability space^[조건부 확률 공간]

$B$가 주어지면, $P(\cdot | B)$는 새로운 probability measure^[확률 측도]이다:
- $P(\Omega | B) = 1$
- $P(A | B) \geq 0$
- Countable additivity^[가산 가법성] 만족

**Measure-theoretic interpretation**^[측도론적 해석]: Conditioning은 normalized subspace measure^[정규화된 부분공간 측도]이다.

**상세한 내용**: [[Subspace Measure]]

---

# <span class="header-properties">Properties</span>

## Basic properties

1. **Range**: $0 \leq P(A | B) \leq 1$

2. **Total probability**: $P(\Omega | B) = 1$

3. **Complement^[여사건]**: $P(A^c | B) = 1 - P(A | B)$

4. **Monotonicity^[단조성]**: $A_1 \subseteq A_2 \Rightarrow P(A_1 | B) \leq P(A_2 | B)$

5. **Multiplication rule^[곱셈 규칙]**: 
   $$P(A \cap B) = P(A | B) \cdot P(B) = P(B | A) \cdot P(A)$$

## Chain rule^[연쇄 법칙]

Events $A_1, \ldots, A_n$에 대해:

$$P(A_1 \cap \cdots \cap A_n) = P(A_1) \cdot P(A_2 | A_1) \cdot P(A_3 | A_1 \cap A_2) \cdots P(A_n | A_1 \cap \cdots \cap A_{n-1})$$

---

# <span class="header-theorem">Theorem</span>

## Law of total probability^[전확률 공식]

$B_1, B_2, \ldots$ 가 partition^[분할]이면 (disjoint하고 $\displaystyle\bigcup_i B_i = \Omega$):

$$P(A) = \displaystyle\sum_{i} P(A | B_i) \cdot P(B_i)$$

**상세한 증명 및 응용**: [[Law of Total Probability]] 참조

### Continuous version^[연속 버전]

Random variable^[확률 변수] $X$에 대해:

$$P(A) = \int P(A | X = x) \, dP_X(x)$$

## Bayes' theorem^[베이즈 정리]

$$P(A | B) = \frac{P(B | A) \cdot P(A)}{P(B)}$$

### Extended form^[확장 형태]

Partition $B_1, \ldots, B_n$에 대해:

$$P(B_i | A) = \frac{P(A | B_i) \cdot P(B_i)}{\displaystyle\sum_{j=1}^n P(A | B_j) \cdot P(B_j)}$$

**용어**:
- $P(B_i)$: **Prior probability^[사전 확률]**
- $P(A | B_i)$: **Likelihood^[가능도]**
- $P(B_i | A)$: **Posterior probability^[사후 확률]**

**베이지안 추론 및 응용**: [[Bayes' Rule]] 참조

---

# <span class="header-examples">Examples</span>

## 1. Medical test^[의학 검사]

질병 유병률 $P(D) = 0.01$ (1%), 검사:
- Sensitivity^[민감도]: $P(+ | D) = 0.99$ (양성 맞출 확률)
- Specificity^[특이도]: $P(- | D^c) = 0.95$ (음성 맞출 확률)

**Question**: 양성 판정 시 실제 질병 확률 $P(D | +)$는?

**Solution** (Bayes' theorem):
$$P(D | +) = \frac{P(+ | D) \cdot P(D)}{P(+ | D) \cdot P(D) + P(+ | D^c) \cdot P(D^c)}$$

$$= \frac{0.99 \times 0.01}{0.99 \times 0.01 + 0.05 \times 0.99} = \frac{0.0099}{0.0594} \approx 0.167$$

놀랍게도 약 **16.7%**만! (Base rate fallacy^[기저율 오류])

## 2. Two coins^[두 개의 동전]

Fair coin (fair) 1개, biased coin (heads both sides) 1개.
- 동전 하나 선택: $P(\text{fair}) = P(\text{biased}) = \frac{1}{2}$
- 선택한 동전 던져서 Heads 나옴

**Question**: Fair coin일 확률?

**Solution**:
$$P(\text{fair} | H) = \frac{P(H | \text{fair}) \cdot P(\text{fair})}{P(H)}$$

$$P(H) = P(H | \text{fair}) \cdot P(\text{fair}) + P(H | \text{biased}) \cdot P(\text{biased}) = \frac{1}{2} \times \frac{1}{2} + 1 \times \frac{1}{2} = \frac{3}{4}$$

$$P(\text{fair} | H) = \frac{\frac{1}{2} \times \frac{1}{2}}{\frac{3}{4}} = \frac{1}{3}$$

## 3. Monty Hall problem^[몬티 홀 문제]

3개 문: 1개에 자동차, 2개에 염소.
1. 참가자가 문 선택
2. 진행자가 염소 있는 다른 문 하나 열어줌
3. 참가자가 선택 바꿀 수 있음

**Question**: 바꾸는 것이 유리한가?

**Solution**:
- 처음 맞을 확률: $\frac{1}{3}$
- 처음 틀릴 확률: $\frac{2}{3}$

처음 틀렸으면 (확률 $\frac{2}{3}$), 바꾸면 무조건 맞음!

**Answer**: 바꾸면 승률 $\frac{2}{3}$, 안 바꾸면 $\frac{1}{3}$ → **바꿔야 함!**

---

# <span class="header-remark">Remark</span>

## Independence^[독립] revisited

Events $A$, $B$가 **independent^[독립]** $\Leftrightarrow$ $P(A | B) = P(A)$

즉, $B$의 발생이 $A$의 확률에 영향을 주지 않음.

이는 $P(A \cap B) = P(A) \cdot P(B)$와 동치.

### Pairwise vs Mutual independence

- **Pairwise independent^[쌍별 독립]**: 모든 쌍이 독립
- **Mutually independent^[상호 독립]**: 모든 부분집합에 대해 독립

Mutual $\Rightarrow$ Pairwise, but not converse!

## Conditional expectation^[조건부 기댓값]

Random variable^[확률 변수] $X$와 event $B$에 대해:

$$E[X | B] = \int_\Omega X \, dP(\cdot | B) = \frac{\int_B X \, dP}{P(B)}$$

Discrete case:
$$E[X | B] = \displaystyle\sum_{x} x \cdot P(X = x | B)$$

**기본 정의 및 성질**: [[Expected Value]] 참조

### Tower property^[탑 성질]

$$E[E[X | Y]] = E[X]$$

## Conditional probability as random variable

$Y$가 random variable일 때, $P(A | Y)$는 $Y$의 함수로 볼 수 있다:

$$P(A | Y)(\omega) = P(A | Y = Y(\omega))$$

이는 새로운 random variable이다!

## Bayesian inference^[베이지안 추론]

Bayesian statistics의 핵심:

$$\text{Posterior} \propto \text{Likelihood} \times \text{Prior}$$

데이터를 보고 belief^[믿음]를 업데이트:

$$P(\theta | \text{data}) = \frac{P(\text{data} | \theta) \cdot P(\theta)}{P(\text{data})}$$

## Conditional probability paradoxes^[조건부 확률 역설]

### Simpson's paradox^[심슨의 역설]

전체에서는 A > B인데, 모든 부분그룹에서는 A < B인 경우 발생 가능!

### Prosecutor's fallacy^[검사의 오류]

$P(\text{evidence} | \text{innocent})$가 작다고 해서 $P(\text{innocent} | \text{evidence})$가 작은 것은 아님!

## Applications^[응용]

### Machine learning
- Naive Bayes classifier^[나이브 베이즈 분류기]
- Bayesian networks^[베이지안 네트워크]
- Hidden Markov models^[은닉 마르코프 모델]

### Signal processing^[신호 처리]
- Kalman filtering^[칼만 필터링]
- Particle filters^[입자 필터]

### Decision theory^[의사결정 이론]
- Expected utility^[기대 효용]
- Bayesian decision theory

### Natural language processing
- Language models^[언어 모델]
- Speech recognition^[음성 인식]

---

# <span class="header-examples">관계도</span>

```
Prior P(B) 
    ↓ observe A
Likelihood P(A|B)
    ↓ Bayes' theorem
Posterior P(B|A)
    ↓ new observation
Updated posterior → new prior
    ↓
Iterative learning
```

## 핵심 공식 요약

| 공식 | 내용 |
|------|------|
| Definition | $P(A\|B) = \frac{P(A \cap B)}{P(B)}$ |
| Multiplication rule | $P(A \cap B) = P(A\|B) \cdot P(B)$ |
| Law of total probability | $P(A) = \displaystyle\sum_i P(A\|B_i) P(B_i)$ |
| Bayes' theorem | $P(B\|A) = \frac{P(A\|B) P(B)}{P(A)}$ |
| Independence | $P(A\|B) = P(A)$ |

---

**확률론 개관**: [[Probability]]
**기본 정의**: [[Sample Spaces]]
**측도론적 관점**: [[Measure Space]], [[Subspace Measure]]
**관련 주제**: [[Joint Probabilities]], [[Marginal Probabilities]], [[Law of Total Probability]], [[Bayes' Rule]], [[Expected Value]]
**재귀적 응용**: [[Recursive Thinking]]
