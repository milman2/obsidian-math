# <span class="header-prerequisite">Prerequisite</span>
- Set theory (집합론 기초)
- Basic arithmetic (기초 산술)

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

## Factorial^[계승]

자연수 $n$에 대해 **factorial**^[계승] $n!$은:

$$n! = n \times (n-1) \times (n-2) \times \cdots \times 2 \times 1$$

**Convention^[관례]**:
- $0! = 1$ (정의)
- $1! = 1$

### Examples
- $3! = 3 \times 2 \times 1 = 6$
- $5! = 5 \times 4 \times 3 \times 2 \times 1 = 120$
- $10! = 3,628,800$

### Recursive definition^[재귀적 정의]

$$n! = \begin{cases}
1 & \text{if } n = 0 \\
n \cdot (n-1)! & \text{if } n > 0
\end{cases}$$

---

# <span class="header-definition">Permutations</span>

## Permutation^[순열]

집합에서 원소들을 **순서를 고려하여** 배열하는 방법.

### Full permutation^[전체 순열]

$n$개의 서로 다른 원소를 모두 배열하는 경우의 수:

$$P(n) = n!$$

**Reasoning^[이유]**:
- 첫 번째 자리: $n$가지 선택
- 두 번째 자리: $n-1$가지 선택
- 세 번째 자리: $n-2$가지 선택
- ...
- 마지막 자리: $1$가지 선택

따라서: $n \times (n-1) \times (n-2) \times \cdots \times 1 = n!$

### $r$-permutation^[r-순열]

$n$개의 서로 다른 원소 중 $r$개를 **순서를 고려하여** 선택:

$$P(n, r) = \frac{n!}{(n-r)!} = n \times (n-1) \times \cdots \times (n-r+1)$$

**Notation^[표기법]**:
- $P(n, r)$, $_nP_r$, $P_r^n$, $A_n^r$ (다양한 표기법 존재)

**Example**: 10명 중 회장, 부회장, 총무 선출
$$P(10, 3) = \frac{10!}{7!} = 10 \times 9 \times 8 = 720$$

## Circular permutation^[원순열]

$n$개의 원소를 **원형으로** 배열:

$$\frac{n!}{n} = (n-1)!$$

**Reasoning**: 원형 배열은 회전해도 같은 것으로 간주 → $n$가지 회전을 하나로 봄.

**Example**: 5명이 원탁에 앉는 경우의 수
$$(5-1)! = 4! = 24$$

### With reflection symmetry^[반사 대칭 포함]

목걸이처럼 뒤집어도 같은 경우:

$$\frac{(n-1)!}{2}$$

## Permutation with repetition^[중복 순열]

$n$개의 원소를 중복을 허용하여 $r$개 선택 (순서 고려):

$$n^r$$

**Example**: 주사위를 3번 던지는 경우의 수
$$6^3 = 216$$

## Permutation with identical objects^[같은 것이 있는 순열]

$n$개 원소 중 같은 것이 $n_1$개, $n_2$개, ..., $n_k$개 있을 때:

$$\frac{n!}{n_1! \cdot n_2! \cdots n_k!}$$

**Example**: "MISSISSIPPI"의 글자 배열 (11글자: M 1개, I 4개, S 4개, P 2개)
$$\frac{11!}{1! \cdot 4! \cdot 4! \cdot 2!} = 34,650$$

---

# <span class="header-definition">Combinations</span>

## Combination^[조합]

집합에서 원소들을 **순서를 고려하지 않고** 선택하는 방법.

### $r$-combination^[r-조합]

$n$개의 서로 다른 원소 중 $r$개를 선택 (순서 무관):

$$C(n, r) = \binom{n}{r} = \frac{n!}{r!(n-r)!}$$

**Notation^[표기법]**:
- $C(n, r)$, $_nC_r$, $\binom{n}{r}$ (binomial coefficient^[이항 계수])

**Relation to permutation^[순열과의 관계]**:
$$C(n, r) = \frac{P(n, r)}{r!}$$

선택한 $r$개를 배열하는 $r!$가지를 하나로 봄.

**Example**: 10명 중 3명 선발
$$C(10, 3) = \binom{10}{3} = \frac{10!}{3! \cdot 7!} = \frac{10 \times 9 \times 8}{3 \times 2 \times 1} = 120$$

## Properties of binomial coefficients^[이항 계수의 성질]

### Symmetry^[대칭성]

$$\binom{n}{r} = \binom{n}{n-r}$$

$r$개를 선택 = $(n-r)$개를 제외

### Pascal's identity^[파스칼 항등식]

$$\binom{n}{r} = \binom{n-1}{r-1} + \binom{n-1}{r}$$

특정 원소를 포함하는 경우 + 포함하지 않는 경우

**Pascal's triangle^[파스칼의 삼각형]**:
```
             1
           1   1
         1   2   1
       1   3   3   1
     1   4   6   4   1
   1   5  10  10   5   1
```

### Sum identities^[합 항등식]

$$\displaystyle\sum_{r=0}^n \binom{n}{r} = 2^n$$

$n$개 원소의 부분집합 개수.

$$\displaystyle\sum_{r=0}^n (-1)^r \binom{n}{r} = 0$$

## Combination with repetition^[중복 조합]

$n$개의 서로 다른 원소 중 중복을 허용하여 $r$개 선택 (순서 무관):

$$H(n, r) = \binom{n+r-1}{r} = \binom{n+r-1}{n-1}$$

**Notation**: $H(n, r)$, $_nH_r$

**Stars and bars method^[칸막이 방법]**: $r$개의 별과 $(n-1)$개의 칸막이 배열

**Example**: 3종류 과일을 5개 선택
$$H(3, 5) = \binom{3+5-1}{5} = \binom{7}{5} = 21$$

---

# <span class="header-examples">Examples</span>

## 1. Seating arrangement^[좌석 배치]

**Question**: 남자 3명, 여자 2명을 일렬로 배치하되, 여자 2명이 이웃하도록?

**Solution**:
- 여자 2명을 하나의 단위로: $2!$ (여자들끼리 배열)
- 남자 3명 + 여자(단위) 1개 = 4개 배열: $4!$
- 총: $4! \times 2! = 24 \times 2 = 48$

## 2. Committee selection^[위원회 선발]

**Question**: 남자 6명, 여자 4명 중 5명 위원회 구성 (최소 2명 여자 포함)?

**Solution**:
전체에서 여자 0명, 1명인 경우 제외:

$$\binom{10}{5} - \binom{6}{5}\binom{4}{0} - \binom{6}{4}\binom{4}{1} = 252 - 6 - 60 = 186$$

또는 직접:
- 여자 2명: $\binom{4}{2}\binom{6}{3} = 6 \times 20 = 120$
- 여자 3명: $\binom{4}{3}\binom{6}{2} = 4 \times 15 = 60$
- 여자 4명: $\binom{4}{4}\binom{6}{1} = 1 \times 6 = 6$
- 총: $120 + 60 + 6 = 186$

## 3. Password creation^[비밀번호 생성]

**Question**: 숫자 6자리 비밀번호 (0-9 사용), 서로 다른 숫자만?

**Solution**:
$$P(10, 6) = \frac{10!}{4!} = 10 \times 9 \times 8 \times 7 \times 6 \times 5 = 151,200$$

## 4. Distribution problem^[분배 문제]

**Question**: 동일한 공 10개를 서로 다른 상자 3개에 넣는 경우의 수?

**Solution** (중복 조합):
$$H(3, 10) = \binom{3+10-1}{10} = \binom{12}{10} = \binom{12}{2} = 66$$

## 5. Paths on a grid^[격자 위 경로]

**Question**: $(0, 0)$에서 $(m, n)$까지 오른쪽/위로만 이동?

**Solution**:
- 총 $m+n$번 이동: 오른쪽 $m$번, 위 $n$번
- $m+n$번 중 오른쪽 갈 위치 $m$개 선택

$$\binom{m+n}{m} = \binom{m+n}{n}$$

**Example**: $(0, 0) \rightarrow (3, 2)$
$$\binom{3+2}{3} = \binom{5}{3} = 10$$

---

# <span class="header-theorem">Binomial Theorem</span>

## Binomial expansion^[이항 정리]

$$(x + y)^n = \displaystyle\sum_{r=0}^n \binom{n}{r} x^{n-r} y^r$$

**Examples**:
$$(x + y)^2 = \binom{2}{0}x^2 + \binom{2}{1}xy + \binom{2}{2}y^2 = x^2 + 2xy + y^2$$

$$(x + y)^3 = x^3 + 3x^2y + 3xy^2 + y^3$$

### Special cases

**$x = y = 1$**:
$$2^n = \displaystyle\sum_{r=0}^n \binom{n}{r}$$

**$x = 1, y = -1$**:
$$0 = \displaystyle\sum_{r=0}^n (-1)^r \binom{n}{r}$$

**$x = 1$**:
$$(1 + y)^n = \displaystyle\sum_{r=0}^n \binom{n}{r} y^r$$

## Multinomial theorem^[다항 정리]

$$(x_1 + x_2 + \cdots + x_k)^n = \displaystyle\sum_{\substack{r_1 + r_2 + \cdots + r_k = n \\ r_i \geq 0}} \binom{n}{r_1, r_2, \ldots, r_k} x_1^{r_1} x_2^{r_2} \cdots x_k^{r_k}$$

여기서 **multinomial coefficient^[다항 계수]**:

$$\binom{n}{r_1, r_2, \ldots, r_k} = \frac{n!}{r_1! r_2! \cdots r_k!}$$

이는 "같은 것이 있는 순열"과 동일한 공식.

---

# <span class="header-properties">Advanced Topics</span>

## Inclusion-exclusion principle^[포함-배제 원리]

집합 $A_1, \ldots, A_n$에 대해:

$$\left|\bigcup_{i=1}^n A_i\right| = \displaystyle\sum_{i} |A_i| - \displaystyle\sum_{i<j} |A_i \cap A_j| + \displaystyle\sum_{i<j<k} |A_i \cap A_j \cap A_k| - \cdots$$

### Example: Derangement^[완전 순열]

$n$개 원소의 permutation 중 어느 원소도 원래 위치에 없는 경우:

$$D_n = n! \left(1 - \frac{1}{1!} + \frac{1}{2!} - \frac{1}{3!} + \cdots + (-1)^n \frac{1}{n!}\right) \approx \frac{n!}{e}$$

## Pigeonhole principle^[비둘기집 원리]

$n+1$개 이상의 물체를 $n$개 상자에 넣으면, 적어도 하나의 상자에는 2개 이상 들어감.

**Generalized^[일반화]**: $kn+1$개 물체를 $n$개 상자에 넣으면, 적어도 하나의 상자에는 $k+1$개 이상.

### Applications
- Birthday problem^[생일 문제]: 23명 중 같은 생일 확률 > 50%
- Ramsey theory^[램지 이론]

## Catalan numbers^[카탈란 수]

$$C_n = \frac{1}{n+1}\binom{2n}{n} = \frac{(2n)!}{(n+1)! n!}$$

**Applications**:
- Valid parentheses sequences^[올바른 괄호 배열]: $(())$, $()(())$, ...
- Binary trees^[이진 트리] with $n$ nodes
- Paths not crossing diagonal^[대각선을 넘지 않는 경로]

**First few**: $C_0 = 1, C_1 = 1, C_2 = 2, C_3 = 5, C_4 = 14, C_5 = 42$

## Stirling numbers^[스털링 수]

### Stirling numbers of the first kind^[제1종 스털링 수]

$s(n, k)$: $n$개 원소를 $k$개 cycles로 배열하는 방법.

### Stirling numbers of the second kind^[제2종 스털링 수]

$S(n, k)$: $n$개 원소를 $k$개 non-empty subsets로 분할.

$$S(n, k) = \frac{1}{k!} \displaystyle\sum_{j=0}^k (-1)^{k-j} \binom{k}{j} j^n$$

**Bell number^[벨 수]**: $B_n = \displaystyle\sum_{k=0}^n S(n, k)$ (모든 분할 방법)

---

# <span class="header-remark">Applications</span>

## Probability theory^[확률론]

Counting techniques는 확률 계산의 핵심:

$$P(E) = \frac{|E|}{|\Omega|}$$

**Example**: 52장 카드에서 5장 뽑을 때 풀하우스 확률

$$P(\text{full house}) = \frac{\binom{13}{1} \cdot \binom{4}{3} \cdot \binom{12}{1} \cdot \binom{4}{2}}{\binom{52}{5}} = \frac{3,744}{2,598,960} \approx 0.00144$$

**관련 주제**: [[Probability]], [[Sample Spaces]]

## Computer science^[컴퓨터 과학]

- **Algorithm analysis^[알고리즘 분석]**: Time/space complexity
- **Data structures^[자료 구조]**: Hash tables, trees
- **Cryptography^[암호학]**: Key space size
- **Coding theory^[코딩 이론]**: Error correction

## Statistics^[통계학]

- **Sampling^[표본 추출]**: Sample size calculation
- **Experimental design^[실험 설계]**: Treatment combinations
- **Hypothesis testing^[가설 검정]**: Permutation tests

## Genetics^[유전학]

- Allele combinations^[대립유전자 조합]
- Genetic crosses^[유전 교배]
- DNA sequences^[DNA 서열]

## Operations research^[운영 과학]

- **Scheduling^[스케줄링]**: Job assignments
- **Network optimization^[네트워크 최적화]**: Routing
- **Inventory management^[재고 관리]**: Stock levels

---

# <span class="header-remark">Summary Table</span>

| Type | Formula | Order matters? | Repetition? |
|------|---------|----------------|-------------|
| Permutation^[순열] | $\frac{n!}{(n-r)!}$ | ✓ Yes | ✗ No |
| Combination^[조합] | $\frac{n!}{r!(n-r)!}$ | ✗ No | ✗ No |
| Permutation with repetition^[중복 순열] | $n^r$ | ✓ Yes | ✓ Yes |
| Combination with repetition^[중복 조합] | $\binom{n+r-1}{r}$ | ✗ No | ✓ Yes |

## Decision tree for choosing formula^[공식 선택 결정 트리]

```
원소 선택 문제
    ↓
순서가 중요한가?
    ├─ Yes → 중복 허용?
    │         ├─ Yes → n^r (중복 순열)
    │         └─ No  → n!/(n-r)! (순열)
    │
    └─ No  → 중복 허용?
              ├─ Yes → C(n+r-1, r) (중복 조합)
              └─ No  → C(n, r) (조합)
```

---

# <span class="header-examples">핵심 공식 요약</span>

| 개념 | 공식 | 예시 |
|------|------|------|
| Factorial | $n! = n \times (n-1) \times \cdots \times 1$ | $5! = 120$ |
| Permutation | $P(n, r) = \frac{n!}{(n-r)!}$ | $P(5, 3) = 60$ |
| Combination | $C(n, r) = \frac{n!}{r!(n-r)!}$ | $C(5, 3) = 10$ |
| Circular perm. | $(n-1)!$ | 5명 원탁: $4! = 24$ |
| With identical | $\frac{n!}{n_1! n_2! \cdots}$ | AABBC: $\frac{5!}{2!2!} = 30$ |
| With repetition (순서 ○) | $n^r$ | 주사위 3번: $6^3 = 216$ |
| With repetition (순서 ✗) | $\binom{n+r-1}{r}$ | $H(3, 5) = 21$ |

---

**확률론 응용**: [[Probability]], [[Sample Spaces]]

