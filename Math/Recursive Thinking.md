# <span class="header-prerequisite">Prerequisite</span>
- [[Probability]]
- [[Conditional Probability]]
- [[Expected Value]]
- [[Law of Total Probability]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Recursive thinking^[재귀적 사고]

**Recursive thinking**^[재귀적 사고]는 복잡한 확률 문제를 더 작고 비슷한 구조의 부분 문제로 분해하여 해결하는 사고 방식이다.

### Core principle^[핵심 원리]

$$P(\text{problem}) = f(P(\text{smaller subproblems}))$$

큰 문제의 해를 작은 부분 문제들의 해로 표현.

### Key components^[핵심 요소]

1. **Base case^[기저 경우]**: 재귀 없이 직접 해결 가능한 가장 단순한 경우
2. **Recursive case^[재귀 경우]**: 문제를 더 작은 문제로 환원
3. **Reduction^[환원]**: 큰 문제 → 작은 문제로의 변환 규칙

---

# <span class="header-properties">Types of Recursive Approaches</span>

## 1. First-step analysis^[첫 단계 분석]

첫 번째 단계에서 일어날 수 있는 모든 경우를 **condition**^[조건]으로 하여 분해.

### Template

$$P(E) = \displaystyle\sum_{i} P(E | \text{First step } = i) \cdot P(\text{First step } = i)$$

이는 **[[Law of Total Probability]]**의 재귀적 적용.

### Example: Random walk^[랜덤 워크]

위치 0에서 시작, +1 또는 -1로 이동 (각각 확률 $p$, $1-p$).
$P_n$ = 위치 $n$에서 출발하여 $k$에 도달할 확률.

**Recursive relation**:
$$P_n = p \cdot P_{n+1} + (1-p) \cdot P_{n-1}$$

**Base cases**:
- $P_k = 1$ (이미 목표에 도달)
- $P_0 = 0$ (barrier가 있다면)

## 2. Conditioning on outcomes^[결과에 대한 조건화]

여러 가능한 결과에 대해 조건화하여 재귀 관계 수립.

### Template

$$X = \displaystyle\sum_i (X | \text{Outcome } i) \cdot \mathbb{1}_{\{\text{Outcome } i\}}$$

### Example: Gambler's ruin^[도박사의 파산]

자본 $n$을 가진 도박사, 각 게임에서 $\pm 1$ (확률 $p$, $1-p$).
$P_n$ = 자본 $n$에서 시작하여 자본 $N$에 도달할 확률 (0에 도달하면 파산).

**Recursive relation**:
$$P_n = p \cdot P_{n+1} + (1-p) \cdot P_{n-1}, \quad 0 < n < N$$

**Boundary conditions**:
- $P_0 = 0$ (파산)
- $P_N = 1$ (목표 달성)

**Solution**:
- If $p = 1/2$: $P_n = \frac{n}{N}$
- If $p \neq 1/2$: $P_n = \frac{1 - (q/p)^n}{1 - (q/p)^N}$ where $q = 1-p$

## 3. Tower property^[탑 성질]

Conditional expectation^[조건부 기댓값]의 재귀적 구조:

$$E[X] = E[E[X | Y]]$$

더 일반적으로:
$$E[X | \mathcal{G}_1] = E[E[X | \mathcal{G}_2] | \mathcal{G}_1] \quad (\mathcal{G}_1 \subseteq \mathcal{G}_2)$$

**상세한 내용**: [[Expected Value]], [[Conditional Probability]]

### Application: Multi-stage processes

여러 단계를 거치는 과정:
$$E[\text{Final}] = E[E[\text{Final} | \text{Stage 2}] | \text{Stage 1}]$$

각 단계에서 조건화하여 재귀적으로 계산.

---

# <span class="header-examples">Classic Examples</span>

## 1. Coin flips until first heads^[첫 앞면까지 동전 던지기]

**Question**: Fair coin을 첫 앞면이 나올 때까지 던질 때, 기댓값은?

### Recursive approach

$E$ = 첫 앞면까지 던지는 횟수의 기댓값.

**First-step analysis**:
- 첫 번째가 앞면 (확률 1/2): 1번
- 첫 번째가 뒷면 (확률 1/2): 1번 + 다시 처음부터 ($E$)

**Recursive equation**:
$$E = \frac{1}{2} \cdot 1 + \frac{1}{2} \cdot (1 + E)$$

$$E = \frac{1}{2} + \frac{1}{2} + \frac{1}{2} E$$

$$\frac{1}{2} E = 1$$

$$E = 2$$

**Answer**: 평균 2번.

## 2. Coupon collector problem^[쿠폰 수집 문제]

**Question**: $n$종류의 쿠폰이 있고, 각 쿠폰이 균등하게 나올 때, 모든 종류를 수집할 때까지 기댓값은?

### Recursive approach

$E_k$ = 이미 $k$종류를 수집했을 때, 새로운 종류를 얻을 때까지 기댓값.

**Analysis**:
- 새로운 종류가 나올 확률: $\frac{n-k}{n}$
- 이는 Geometric distribution^[기하 분포]: $E_k = \frac{n}{n-k}$

**Total expectation**:
$$E = E_0 + E_1 + \cdots + E_{n-1} = \displaystyle\sum_{k=0}^{n-1} \frac{n}{n-k} = n \displaystyle\sum_{j=1}^n \frac{1}{j} = n H_n$$

여기서 $H_n$은 $n$-th harmonic number^[조화수].

**Asymptotic**: $E \approx n \ln n$

## 3. Two-envelope problem^[두 봉투 문제] (Modified)

**Setup**: 봉투 A에 $x$, 봉투 B에 $2x$ (각각 확률 1/2로 어느 것이 어느 것인지 모름).
A를 선택했는데 $y$가 들어있음. B로 바꿀까?

### Recursive analysis

$E_A$ = A의 기댓값, $E_B$ = B의 기댓값.

**Conditioning**:
- If $A = x$: $E[B | A = x] = 2x$, prob = 1/2
- If $A = 2x$: $E[B | A = 2x] = x$, prob = 1/2

**Issue**: Prior distribution^[사전 분포]이 필요!

이는 재귀적 사고의 한계를 보여주는 예시 (paradox).

## 4. Expected value of maximum^[최댓값의 기댓값]

**Question**: $n$번의 i.i.d. trials에서 최댓값의 기댓값?

### Recursive approach

$M_n$ = $n$개 중 최댓값.

**Recursive relation**:
$$M_n = \max(X_n, M_{n-1})$$

**Expectation** (일반적으로 closed form은 어려움):
$$E[M_n] = E[\max(X_n, M_{n-1})]$$

**Uniform(0,1) case**:
$$E[M_n] = \frac{n}{n+1}$$

(Order statistics 이론 사용)

## 5. Secretary problem^[비서 문제]

**Question**: $n$명의 후보를 순차적으로 면접, 즉시 결정 (나중에 되돌릴 수 없음). 최고의 후보를 선택할 확률 최대화 전략?

### Recursive strategy

$V_k(n)$ = $k$번째 위치부터 시작하여 $n$명 중 최고를 선택할 확률.

**Optimal stopping rule**:
처음 $r-1$명은 거절하고, 그 이후 첫 번째로 "지금까지 본 것 중 최고"인 사람 선택.

**Optimal $r$**: $r \approx \frac{n}{e}$

**Success probability**: $\approx \frac{1}{e} \approx 0.368$

---

# <span class="header-theorem">Recurrence Relations</span>

## Linear recurrence^[선형 재귀]

$$a_n = c_1 a_{n-1} + c_2 a_{n-2} + \cdots + c_k a_{n-k}$$

### Solution methods

1. **Characteristic equation^[특성 방정식]**:
   $$r^k = c_1 r^{k-1} + c_2 r^{k-2} + \cdots + c_k$$

2. **General solution**: Roots $r_1, \ldots, r_k$이면
   $$a_n = A_1 r_1^n + A_2 r_2^n + \cdots + A_k r_k^n$$

3. **Initial conditions**로 constants $A_i$ 결정.

### Example: Fibonacci with probability

$p_n$ = $n$단계에서 특정 상태에 도달할 확률.
$$p_n = \alpha p_{n-1} + \beta p_{n-2}$$

Characteristic equation: $r^2 = \alpha r + \beta$

## Non-homogeneous recurrence^[비동차 재귀]

$$a_n = c_1 a_{n-1} + \cdots + c_k a_{n-k} + f(n)$$

**Solution** = Homogeneous solution + Particular solution

## Probabilistic interpretation

재귀 관계 $\Leftrightarrow$ Markov property^[마르코프 성질]:

미래는 현재 상태에만 의존 (과거 경로와 무관).

---

# <span class="header-properties">Dynamic Programming Connection</span>

## Bellman equation^[벨만 방정식]

최적화 문제의 재귀적 구조:

$$V(s) = \max_a \left\{R(s, a) + \gamma \displaystyle\sum_{s'} P(s' | s, a) V(s')\right\}$$

여기서:
- $V(s)$: State $s$의 value^[가치]
- $R(s, a)$: Reward^[보상]
- $\gamma$: Discount factor^[할인 계수]
- $P(s' | s, a)$: Transition probability^[전이 확률]

**Interpretation**: 현재의 최적 결정 = 즉각적 보상 + 미래 최적 가치의 기댓값

## Backward induction^[역방향 귀납법]

1. **Final stage**: 직접 계산
2. **Previous stages**: 미래 단계의 결과를 이용하여 재귀적으로 계산

### Example: Optimal stopping

각 시점에서 "지금 멈출까, 계속할까?" 결정.

$$V_t = \max\left\{X_t, E[V_{t+1} | \mathcal{F}_t]\right\}$$

- $X_t$: 지금 멈추면 얻는 보상
- $E[V_{t+1} | \mathcal{F}_t]$: 계속했을 때의 기댓값

---

# <span class="header-examples">Advanced Applications</span>

## 1. Martingales^[마팅게일]

**Definition**: $E[X_{n+1} | X_1, \ldots, X_n] = X_n$

재귀적 성질: 미래 기댓값 = 현재 값.

**Applications**:
- Fair games^[공정한 게임] 모델링
- Optional stopping theorem^[선택적 정지 정리]
- Gambling strategies 분석

## 2. Markov chains^[마르코프 연쇄]

**Markov property**: 
$$P(X_{n+1} = j | X_0, \ldots, X_n) = P(X_{n+1} = j | X_n)$$

미래는 현재에만 의존 (재귀적 구조).

### Stationary distribution^[정상 분포]

$$\pi = \pi P$$

재귀적 방정식의 fixed point^[고정점].

## 3. Branching processes^[분기 과정]

**Setup**: 각 개체가 확률 분포에 따라 자손 생성.

$Z_n$ = $n$세대의 개체 수.

**Recursive structure**:
$$Z_{n+1} = \displaystyle\sum_{i=1}^{Z_n} X_i^{(n)}$$

여기서 $X_i^{(n)}$은 $i$번째 개체의 자손 수.

**Extinction probability^[멸종 확률]**:
$$q = G(q)$$

여기서 $G(s) = E[s^X]$는 probability generating function.

재귀적으로 해결!

## 4. Wald's equation^[발드 방정식]

Random number^[확률적 개수]의 random variables 합:

$$E\left[\displaystyle\sum_{i=1}^N X_i\right] = E[N] \cdot E[X]$$

(if $N$ is stopping time and $X_i$ i.i.d.)

재귀적 사고의 응용.

---

# <span class="header-remark">Problem-Solving Strategies</span>

## Step 1: Identify the state space^[상태 공간 식별]

문제를 상태(state)로 표현:
- 위치, 자본, 수집한 쿠폰 수 등

## Step 2: Define the quantity of interest^[관심 대상 정의]

각 상태에서:
- $P_s$ = 특정 사건의 확률
- $E_s$ = 특정 변수의 기댓값
- $V_s$ = 최적 가치

## Step 3: First-step analysis^[첫 단계 분석]

현재 상태에서 가능한 첫 단계들을 열거:

$$Q(s) = \displaystyle\sum_{\text{outcomes}} P(\text{outcome}) \cdot f(Q(s'), \text{outcome})$$

여기서 $s'$는 다음 상태.

## Step 4: Set up recurrence^[재귀 관계 수립]

Step 3의 분석을 방정식으로:

$$Q(s) = \text{function of } Q(s_1'), Q(s_2'), \ldots$$

## Step 5: Boundary conditions^[경계 조건]

Base cases 식별:
- 더 이상 재귀가 필요 없는 상태들

## Step 6: Solve^[해결]

방법:
- **Closed-form solution**: 특성 방정식 등
- **Numerical solution**: Iteration, dynamic programming
- **Approximation**: Asymptotic analysis

---

# <span class="header-remark">Common Pitfalls</span>

## 1. Missing boundary conditions^[경계 조건 누락]

재귀 관계만으로는 불충분!

**Example**: $a_n = a_{n-1} + a_{n-2}$
- Fibonacci: $a_0 = 0, a_1 = 1$
- Lucas: $a_0 = 2, a_1 = 1$

다른 경계 조건 → 완전히 다른 수열.

## 2. Incorrect conditioning^[잘못된 조건화]

조건화할 때 모든 경우를 빠짐없이 포함해야 함.

**Check**: $\displaystyle\sum_i P(\text{case } i) = 1$

## 3. Circular reasoning^[순환 논리]

$P(A)$를 구하는데 $P(A)$를 사용하면 안 됨!

**Check**: 재귀 관계가 acyclic^[비순환]인지 확인.

## 4. Infinite regress^[무한 후퇴]

재귀가 종료되지 않는 경우.

**Solution**: 
- Proper base case 확인
- Convergence 조건 확인

## 5. State space explosion^[상태 공간 폭발]

너무 많은 상태 → 계산 불가능.

**Solution**:
- 상태 공간 단순화
- Approximation methods
- Monte Carlo simulation

---

# <span class="header-examples">Comparison with Other Approaches</span>

| Approach | When to Use | Pros | Cons |
|----------|-------------|------|------|
| **Recursive** | Multi-stage, sequential problems | Natural decomposition, elegant | May need numerical solution |
| **Direct calculation** | Simple problems | Explicit formula | Hard for complex cases |
| **Generating functions** | Counting, combinatorics | Powerful algebraic tool | Requires algebra skills |
| **Simulation** | Complex, intractable | Always feasible | Not exact, computationally expensive |

---

# <span class="header-examples">핵심 원리 요약</span>

## Recursive thinking framework

```
1. Problem Definition
       ↓
2. State Representation
       ↓
3. First-Step Analysis
       ↓
4. Recurrence Relation
       ↓
5. Boundary Conditions
       ↓
6. Solution (Analytical/Numerical)
       ↓
7. Verification
```

## Key equations

| Concept | Formula |
|---------|---------|
| First-step | $P(E) = \displaystyle\sum_i P(E\|i) P(i)$ |
| Tower property | $E[X] = E[E[X\|Y]]$ |
| Bellman | $V(s) = \max_a \{R(s,a) + \gamma \displaystyle\sum_{s'} P(s'\|s,a) V(s')\}$ |
| Linear recurrence | $a_n = c_1 a_{n-1} + \cdots + c_k a_{n-k}$ |

## Problem-solving checklist

- [ ] 상태 공간 정의
- [ ] 관심 있는 양 정의 ($P$, $E$, $V$ 등)
- [ ] 첫 단계 분석
- [ ] 재귀 관계 수립
- [ ] 경계 조건 확인
- [ ] 해 구하기
- [ ] 결과 검증

---

**기초 개념**: [[Probability]], [[Conditional Probability]]
**핵심 도구**: [[Law of Total Probability]], [[Expected Value]]
**응용**: [[Random Variables]], [[Joint Probabilities]]

