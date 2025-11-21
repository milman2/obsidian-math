# <span class="header-prerequisite">Prerequisite</span>
- [[Conditional Probability]]
- [[Sample Spaces]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Bayes' theorem^[베이즈 정리]

**Bayes' theorem**^[베이즈 정리] (또는 Bayes' rule):

$$P(B | A) = \frac{P(A | B) \cdot P(B)}{P(A)}$$

여기서:
- $P(B)$: **Prior probability^[사전 확률]** (evidence 전의 belief)
- $P(A | B)$: **Likelihood^[가능도]** (B가 참일 때 A의 확률)
- $P(A)$: **Marginal probability^[주변 확률]** or **Evidence^[증거]**
- $P(B | A)$: **Posterior probability^[사후 확률]** (evidence 후의 updated belief)

### Extended form with partition

Events $\{B_i\}$가 partition^[분할]이면:

$$P(B_i | A) = \frac{P(A | B_i) \cdot P(B_i)}{\displaystyle\sum_{j} P(A | B_j) \cdot P(B_j)}$$

분모는 **[[Law of Total Probability]]**를 사용하여 $P(A)$를 계산한 것.

**참고**: 기본 유도는 [[Conditional Probability]] 참조

---

# <span class="header-properties">Properties</span>

## Bayesian updating^[베이지안 업데이트]

Bayes' theorem은 **learning mechanism^[학습 메커니즘]**:

```
Prior belief → Observe data → Update belief → Posterior
```

Posterior는 새로운 prior가 되어 iterative learning^[반복 학습]:

$$P(B | A_1, A_2) = \frac{P(A_2 | B, A_1) \cdot P(B | A_1)}{P(A_2 | A_1)}$$

## Odds form^[승산 형태]

**Prior odds^[사전 승산]**: $\displaystyle\frac{P(B)}{P(B^c)}$

**Posterior odds^[사후 승산]**: $\displaystyle\frac{P(B | A)}{P(B^c | A)}$

**Bayes factor^[베이즈 인자]**: $\displaystyle\frac{P(A | B)}{P(A | B^c)}$

관계:
$$\frac{P(B | A)}{P(B^c | A)} = \frac{P(A | B)}{P(A | B^c)} \cdot \frac{P(B)}{P(B^c)}$$

즉: **Posterior odds = Bayes factor × Prior odds**

---

# <span class="header-examples">Examples</span>

## 1. Spam filter^[스팸 필터]

Email에 "free"라는 단어가 있을 때, spam일 확률은?

**Given**:
- Prior: $P(\text{spam}) = 0.3$
- Likelihood: $P(\text{"free"} | \text{spam}) = 0.8$
- Evidence: $P(\text{"free"} | \text{not spam}) = 0.1$

**Solution**:
$$P(\text{"free"}) = 0.8 \times 0.3 + 0.1 \times 0.7 = 0.31$$

$$P(\text{spam} | \text{"free"}) = \frac{0.8 \times 0.3}{0.31} \approx 0.77$$

약 77% 확률로 spam!

## 2. Crime investigation^[범죄 수사]

DNA match: 1 in 1,000,000 확률로 일치.
- 용의자 풀: 1,000,000명
- Prior: $P(\text{guilty}) = \frac{1}{1,000,000}$

**Prosecutor's argument**: DNA 일치 → 99.9999% 유죄!

**Defense's argument** (Bayes):
$$P(\text{guilty} | \text{match}) = \frac{P(\text{match} | \text{guilty}) \cdot P(\text{guilty})}{P(\text{match})}$$

Random match in population:
$$P(\text{match}) \approx 1 \times \frac{1}{1,000,000} + \frac{1}{1,000,000} \times \frac{999,999}{1,000,000} \approx \frac{2}{1,000,000}$$

$$P(\text{guilty} | \text{match}) \approx \frac{1}{2} = 50\%$$

**Base rate fallacy^[기저율 오류]**를 보여주는 예!

## 3. Multiple testing^[다중 검정]

Drug testing with 95% accuracy:
- Sensitivity: $P(+ | \text{user}) = 0.95$
- Specificity: $P(- | \text{non-user}) = 0.95$
- Base rate: $P(\text{user}) = 0.005$ (0.5%)

**First test positive**:
$$P(\text{user} | +) = \frac{0.95 \times 0.005}{0.95 \times 0.005 + 0.05 \times 0.995} \approx 0.087$$

Only 8.7%! But if **second test also positive**:

Using first posterior as new prior:
$$P(\text{user} | +, +) \approx 0.64$$

64% - much more confident!

---

# <span class="header-remark">Remark</span>

## Frequentist vs Bayesian^[빈도주의 대 베이지안]

| Aspect | Frequentist^[빈도주의] | Bayesian^[베이지안] |
|--------|------------------------|---------------------|
| Probability | Long-run frequency | Degree of belief |
| Parameters | Fixed but unknown | Random variables |
| Inference | Confidence intervals | Credible intervals |
| Prior | Not used | Essential |
| Philosophy | Objective | Subjective |

### Example: Coin flip

**Frequentist**: "True probability $p$ exists, we estimate it"
- Point estimate: $\hat{p} = \frac{\text{heads}}{n}$
- 95% CI: $\hat{p} \pm 1.96\sqrt{\frac{\hat{p}(1-\hat{p})}{n}}$

**Bayesian**: "Probability $p$ has distribution"
- Prior: $p \sim \text{Beta}(\alpha, \beta)$
- After $n_H$ heads, $n_T$ tails:
- Posterior: $p \sim \text{Beta}(\alpha + n_H, \beta + n_T)$

## Conjugate priors^[켤레 사전분포]

Prior와 posterior가 같은 family일 때:

| Likelihood | Conjugate prior | Posterior |
|------------|----------------|-----------|
| Bernoulli | Beta | Beta |
| Normal (known $\sigma^2$) | Normal | Normal |
| Poisson | Gamma | Gamma |
| Exponential | Gamma | Gamma |

**장점**: Closed-form posterior!

## Bayes factor^[베이즈 인자]

Model comparison^[모델 비교]:

$$BF_{12} = \frac{P(D | M_1)}{P(D | M_2)}$$

**Interpretation** (Kass & Raftery):
- $BF > 100$: Decisive evidence
- $BF > 10$: Strong evidence
- $BF > 3$: Positive evidence
- $BF < 1$: Evidence for $M_2$

## Empirical Bayes^[경험적 베이즈]

Prior를 data로부터 estimate:
1. Assume prior distribution with hyperparameters
2. Estimate hyperparameters from data
3. Use estimated prior in Bayes' theorem

**Trade-off**: Not fully Bayesian, but more objective

## Computational methods^[계산 방법]

Posterior가 analytically intractable^[해석적으로 계산 불가능]할 때:

### Markov Chain Monte Carlo (MCMC)
- **Metropolis-Hastings algorithm**
- **Gibbs sampling**
- Sample from posterior distribution

### Variational Bayes
- Approximate posterior with simpler distribution
- Optimize to minimize KL divergence

### Approximate Bayesian Computation (ABC)
- Simulation-based approach
- When likelihood is unavailable

---

# <span class="header-examples">Applications</span>

## Machine learning^[기계 학습]

### Naive Bayes classifier^[나이브 베이즈 분류기]

Assume features $X_1, \ldots, X_n$ independent given class $C$:

$$P(C | X_1, \ldots, X_n) \propto P(C) \displaystyle\prod_{i=1}^n P(X_i | C)$$

**Applications**: Spam filtering, text classification

### Bayesian networks^[베이지안 네트워크]

Directed acyclic graph (DAG) representing conditional dependencies:
- Nodes: Random variables
- Edges: Direct dependencies
- Efficient inference via factorization

### Gaussian processes^[가우스 과정]

Bayesian approach to regression:
- Prior: Function is GP
- Posterior: Updated GP after observing data

## Medical diagnosis^[의학 진단]

Expert systems combining:
- Disease prevalence (prior)
- Test accuracy (likelihood)
- Symptom patterns
- Sequential testing strategies

## Natural language processing

- **Language models**: $P(\text{word} | \text{context})$
- **Machine translation**: $P(\text{target} | \text{source})$
- **Speech recognition**: $P(\text{text} | \text{audio})$

## Finance and economics^[금융과 경제학]

- **Portfolio optimization**: Update beliefs about returns
- **Risk assessment**: Dynamic risk models
- **Economic forecasting**: Combine models and data

## Scientific inference^[과학적 추론]

- **Parameter estimation**: Physics, biology, climate science
- **Model selection**: Compare competing theories
- **Experimental design**: Optimal next experiment

---

# <span class="header-remark">Philosophy & Interpretation</span>

## Bayesian epistemology^[베이지안 인식론]

Bayes' theorem as **rational belief updating**:
1. Start with prior beliefs (subjective but explicit)
2. Observe evidence
3. Update beliefs consistently
4. Iterate

**Principle**: "All models are wrong, but some are useful" + quantify uncertainty

## The priors debate^[사전분포 논쟁]

**Criticism**: Prior is subjective!

**Response**:
1. **Objectivity through transparency**: Make assumptions explicit
2. **Sensitivity analysis**: Test robustness to prior choice
3. **Non-informative priors**: Jeffreys prior, maximum entropy
4. **Data-driven**: More data → prior matters less

## Dutch book argument^[더치북 논증]

Coherent beliefs must satisfy probability axioms, otherwise vulnerable to sure loss (Dutch book).

Bayes' theorem ensures coherent belief updating!

---

# <span class="header-examples">베이지안 추론 순환</span>

```
Prior distribution P(θ)
    ↓ observe data D
Likelihood P(D|θ)
    ↓ Bayes' theorem
Posterior P(θ|D) ∝ P(D|θ) · P(θ)
    ↓ prediction
Posterior predictive P(D_new|D)
    ↓ new data
Updated posterior → new prior
    ↓
Continuous learning
```

## 핵심 아이디어

**"Bayes' Rule = Optimal learning under uncertainty"**

- **Uncertainty quantification**: 항상 확률로 표현
- **Belief updating**: 증거에 따라 일관되게 업데이트
- **Decision making**: Posterior를 사용해 최적 결정
- **Iterative refinement**: 데이터가 쌓이면서 점점 정확해짐

---

**더 자세한 수학적 유도와 성질**: [[Conditional Probability]] 참조

