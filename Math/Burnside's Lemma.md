# <span class="header-prerequisite">Prerequisite</span>
- [[Group Action]]
- [[Orbit-Stabilizer Theorem]]
- [[Equivalence Relation and Partitions]]

# <span class="header-reference">Reference</span>
- Dummit & Foote, Abstract Algebra
- Cameron, Combinatorics
- Stanley, Enumerative Combinatorics

---

# <span class="header-definition">Definition</span>

## Burnside's Lemma

(Also known as **Cauchy-Frobenius Lemma^[코시-프로베니우스 보조정리]** or **Orbit-Counting Theorem^[궤도 계수 정리]**)

Group $G$가 finite set^[유한 집합] $X$에 작용할 때, **orbit^[궤도]의 개수**는:

$$|\text{Orbits}| = \frac{1}{|G|} \sum_{g \in G} |X^g|$$

여기서 $X^g = \{x \in X : g \cdot x = x\}$는 $g$의 **fixed points^[고정점]**

### 다른 표현

$$|\text{Orbits}| = \frac{1}{|G|} \sum_{g \in G} |\text{Fix}(g)|$$

또는

$$|X/G| = \frac{1}{|G|} \sum_{g \in G} |X^g|$$

여기서 $X/G$는 orbit들의 집합

---

# <span class="header-proof">Proof</span>

## 증명 (Double Counting)

쌍 $(g, x)$의 집합을 두 가지 방법으로 센다:

$$S = \{(g, x) \in G \times X : g \cdot x = x\}$$

### Method 1: $g$로 먼저 세기

각 $g \in G$에 대해, $g \cdot x = x$인 $x$의 개수는 $|X^g|$

$$|S| = \sum_{g \in G} |X^g|$$

### Method 2: $x$로 먼저 세기

각 $x \in X$에 대해, $g \cdot x = x$인 $g$의 개수는 $|G_x|$ (stabilizer^[안정화군])

$$|S| = \sum_{x \in X} |G_x|$$

### Orbit별로 정리

$X$를 orbit들로 분할: $X = \bigsqcup_{i=1}^{k} \mathcal{O}_i$

각 orbit $\mathcal{O}_i$의 representative를 $x_i$라 하면:

$$\sum_{x \in X} |G_x| = \sum_{i=1}^{k} \sum_{x \in \mathcal{O}_i} |G_x|$$

**Orbit-Stabilizer Theorem^[궤도-안정화군 정리]**에 의해: $|\mathcal{O}_i| = \frac{|G|}{|G_{x_i}|}$

같은 orbit의 모든 점은 conjugate stabilizer를 가지므로 같은 크기:

$$\sum_{x \in \mathcal{O}_i} |G_x| = |\mathcal{O}_i| \cdot |G_{x_i}| = \frac{|G|}{|G_{x_i}|} \cdot |G_{x_i}| = |G|$$

따라서:

$$\sum_{x \in X} |G_x| = \sum_{i=1}^{k} |G| = k \cdot |G|$$

여기서 $k = |\text{Orbits}|$

### 결론

$$\sum_{g \in G} |X^g| = k \cdot |G|$$

$$\therefore \; k = \frac{1}{|G|} \sum_{g \in G} |X^g|$$ ✓

---

# <span class="header-examples">Examples</span>

## Example 1: Necklace Problem (3 beads, 2 colors)

**문제**: 3개의 구슬, 2가지 색깔, 회전 대칭을 고려할 때 구별되는 목걸이는 몇 개?

**Setup**:
- $X = \{0, 1\}^3$ (모든 가능한 색칠, $|X| = 8$)
- $G = C_3 = \{e, r, r^2\}$ (회전군, $|G| = 3$)
  - $e$ = identity
  - $r$ = rotation by $120°$
  - $r^2$ = rotation by $240°$

**Fixed points 계산**:

1. **$g = e$ (identity)**:
   - 모든 색칠이 고정: $|X^e| = 8$

2. **$g = r$ (120° 회전)**:
   - 회전해도 같으려면 모든 구슬이 같은 색
   - $(0,0,0)$, $(1,1,1)$만 가능
   - $|X^r| = 2$

3. **$g = r^2$ (240° 회전)**:
   - 마찬가지로 모든 구슬이 같은 색
   - $|X^{r^2}| = 2$

**Burnside's Lemma 적용**:

$$|\text{Orbits}| = \frac{1}{3}(8 + 2 + 2) = \frac{12}{3} = 4$$

**답**: 4가지 구별되는 목걸이

**확인**: 직접 세면
- 3개 같은 색: $(0,0,0)$, $(1,1,1)$ → 2개 orbit
- 2개 같은 색: $(0,0,1)$, $(0,1,1)$ → 각각 1개 orbit
- 총 4개 ✓

## Example 2: Square Colorings

**문제**: 정사각형의 4개 꼭짓점을 2가지 색으로 칠할 때, 회전과 반사를 고려한 구별되는 색칠은?

**Setup**:
- $X = \{0, 1\}^4$ ($|X| = 16$)
- $G = D_4$ (정사각형의 대칭군, $|G| = 8$)
  - 4개 회전: $0°, 90°, 180°, 270°$
  - 4개 반사: 2개 대각선, 2개 변의 중점 축

**Fixed points**:

1. **Identity**: $|X^e| = 16$ (모든 색칠)

2. **90° 회전**: 모든 꼭짓점이 같은 색
   - $|X^{r_{90}}| = 2$

3. **180° 회전**: 대각 꼭짓점끼리 같은 색
   - $(a, b, a, b)$ 형태
   - $|X^{r_{180}}| = 4$

4. **270° 회전**: 모든 꼭짓점이 같은 색
   - $|X^{r_{270}}| = 2$

5. **대각선 반사** (2개): 대각선 양쪽이 대칭
   - 각각 $2^3 = 8$ (3개 자유 선택)
   - 총 $2 \times 8 = 16$

6. **변 중점 축 반사** (2개): 대변끼리 같은 색
   - 각각 $2^2 = 4$
   - 총 $2 \times 4 = 8$

**Burnside's Lemma**:

$$|\text{Orbits}| = \frac{1}{8}(16 + 2 + 4 + 2 + 8 + 8) = \frac{40}{8} = 5$$

**답**: 5가지

## Example 3: Hexagon with 3 colors

**문제**: 정육각형의 6개 변을 3가지 색으로 칠할 때, 회전 대칭 고려한 구별되는 색칠은?

**Setup**:
- $X = \{1, 2, 3\}^6$ ($|X| = 3^6 = 729$)
- $G = C_6$ (회전군, $|G| = 6$)

**Fixed points**:

| Rotation | Angle | Fixed Condition | Count |
|----------|-------|----------------|-------|
| $e$ | $0°$ | 모두 | $3^6 = 729$ |
| $r$ | $60°$ | 모든 변 같은 색 | $3^1 = 3$ |
| $r^2$ | $120°$ | 주기 2 | $3^2 = 9$ |
| $r^3$ | $180°$ | 대변끼리 같은 색 | $3^3 = 27$ |
| $r^4$ | $240°$ | 주기 2 | $3^2 = 9$ |
| $r^5$ | $300°$ | 모든 변 같은 색 | $3^1 = 3$ |

**Burnside's Lemma**:

$$|\text{Orbits}| = \frac{1}{6}(729 + 3 + 9 + 27 + 9 + 3) = \frac{780}{6} = 130$$

**답**: 130가지

## Example 4: Conjugacy Classes

**Setup**: $G$ acts on itself by conjugation^[켤레]

$$g \cdot x = gxg^{-1}$$

**Orbits**: Conjugacy classes^[켤레류]

**Fixed points**: $X^g = \{x \in G : gxg^{-1} = x\} = C_G(g)$ (centralizer^[중심화군])

**Burnside's Lemma**:

$$|\text{Conjugacy Classes}| = \frac{1}{|G|} \sum_{g \in G} |C_G(g)|$$

이것이 바로 **Class Equation^[류 방정식]**의 다른 형태!

## Example 5: Graph Automorphisms

**문제**: 3개 꼭짓점의 labeled graph 중 isomorphic^[동형]하지 않은 것은?

**Setup**:
- $X$ = 모든 가능한 edge 집합 = $2^{\binom{3}{2}} = 2^3 = 8$
- $G = S_3$ (꼭짓점의 permutation, $|G| = 6$)

**Fixed points**:

| Element | Type | Fixed Graphs | Count |
|---------|------|--------------|-------|
| $e$ | Identity | 모두 | 8 |
| $(12)$ | Transposition | Edge $\{1,2\}$ 없거나 있어야 | 4 |
| $(13)$ | Transposition | Edge $\{1,3\}$ 없거나 있어야 | 4 |
| $(23)$ | Transposition | Edge $\{2,3\}$ 없거나 있어야 | 4 |
| $(123)$ | 3-cycle | 모두 같거나 모두 다른 edge | 2 |
| $(132)$ | 3-cycle | 모두 같거나 모두 다른 edge | 2 |

**Burnside's Lemma**:

$$|\text{Orbits}| = \frac{1}{6}(8 + 4 + 4 + 4 + 2 + 2) = \frac{24}{6} = 4$$

**답**: 4가지 non-isomorphic graphs
- Empty graph
- 1 edge
- 2 edges (path)
- Complete graph $K_3$

---

# <span class="header-properties">Properties</span>

## Interpretation^[해석]

Burnside's Lemma는 다음을 말한다:

> **Orbit의 개수 = $g \in G$에 대한 fixed point 개수의 평균**

$$|\text{Orbits}| = \frac{1}{|G|} \sum_{g \in G} |X^g| = \text{Average of } |X^g|$$

## Special Cases

### Trivial Action

$g \cdot x = x$ for all $g, x$ (모든 원소가 고정)

$$|X^g| = |X| \text{ for all } g$$

$$|\text{Orbits}| = \frac{1}{|G|} \sum_{g \in G} |X| = \frac{|G| \cdot |X|}{|G|} = |X|$$

각 점이 자기 자신의 orbit ✓

### Free Action^[자유 작용]

$g \cdot x \neq x$ for all $g \neq e, x \in X$

$$|X^g| = 0 \text{ for } g \neq e, \quad |X^e| = |X|$$

$$|\text{Orbits}| = \frac{1}{|G|}|X|$$

즉, $|X| = |G| \cdot |\text{Orbits}|$ ✓

### Transitive Action^[추이적 작용]

$|\text{Orbits}| = 1$

$$1 = \frac{1}{|G|} \sum_{g \in G} |X^g|$$

$$\sum_{g \in G} |X^g| = |G|$$

## Relationship to Orbit-Stabilizer

Burnside's Lemma는 Orbit-Stabilizer Theorem의 "dual"

**Orbit-Stabilizer**: 한 orbit의 크기

$$|\mathcal{O}_x| = \frac{|G|}{|G_x|}$$

**Burnside**: 모든 orbit의 개수

$$|\text{Orbits}| = \frac{1}{|G|} \sum_{g \in G} |X^g|$$

## Computational Efficiency

**Naive approach**: 각 원소의 orbit 직접 계산 → $O(|X| \cdot |G|)$

**Burnside's Lemma**: Fixed points 계산 → 종종 더 효율적
- Symmetry가 높을수록 $|X^g|$ 계산이 쉬움
- Group 원소별로 병렬 계산 가능

---

# <span class="header-theorem">Theorem</span>

## Generalization: Pólya Enumeration Theorem

Burnside's Lemma의 강력한 일반화

**Setup**: 
- $G$ acts on $X$
- $Y$ = set of colors/labels
- $Y^X$ = all functions $X \to Y$ (colorings)
- $G$ acts on $Y^X$ by $(g \cdot f)(x) = f(g^{-1} \cdot x)$

**Cycle Index**:

$$Z(G; x_1, x_2, \ldots) = \frac{1}{|G|} \sum_{g \in G} x_1^{c_1(g)} x_2^{c_2(g)} \cdots$$

여기서 $c_i(g)$ = $g$의 permutation에서 length $i$인 cycle의 개수

**Pólya's Theorem**: 구별되는 coloring의 개수는

$$Z(G; |Y|, |Y|, \ldots) = \frac{1}{|G|} \sum_{g \in G} |Y|^{c(g)}$$

여기서 $c(g)$ = $g$의 total cycle 개수

**Burnside's Lemma는 특수한 경우**: $|Y| = 1$일 때

자세한 내용은 [[Pólya Enumeration Theorem]] 참조

## Weighted Burnside's Lemma

각 coloring에 weight를 부여할 수도 있음

$$\sum_{\text{orbits}} w(\text{orbit representative}) = \frac{1}{|G|} \sum_{g \in G} \sum_{x \in X^g} w(x)$$

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**핵심 아이디어**: "대칭성을 고려한 counting"

### 왜 작동하는가?

각 orbit은 $|G|/|G_x|$개의 원소를 가짐

모든 orbit에서:
$$\text{기여도} = |G_x| \times \frac{1}{|G|} = \frac{|G_x|}{|G|}$$

이것들을 $g$별로 모으면 fixed points!

### 메타포: 투표

각 $g \in G$가 "얼마나 많은 $x$를 고정시키는가" 투표

평균 = orbit 개수

## 이름의 역사

**실제 발견자**: Augustin-Louis Cauchy (1845), Ferdinand Georg Frobenius (1887)

**Burnside**: William Burnside가 1897년 책에서 소개했지만, 증명 없이 인용

**오명**: "Burnside's Lemma"는 역사적으로 부정확
- 올바른 이름: Cauchy-Frobenius Lemma
- 하지만 "Burnside's Lemma"가 널리 사용됨

**농담**: "Burnside's Lemma: Not Burnside's, not a lemma"
- Burnside가 발견하지 않음
- 중요한 정리이지 단순한 보조정리가 아님

## 실용적 조언

### Fixed Points 계산 전략

1. **Identity는 쉽다**: $|X^e| = |X|$ 항상

2. **Symmetry 활용**: 
   - 높은 대칭 = 적은 fixed points
   - 낮은 대칭 = 많은 fixed points

3. **패턴 찾기**:
   - Rotation by $360°/n$: 주기 $n$인 패턴
   - Reflection: 축에 대한 대칭

4. **작은 예시로 확인**: 손으로 직접 세서 검증

## 응용 분야

### Combinatorics^[조합론]

**핵심 도구**:
- Necklace/bracelet problems
- Graph enumeration
- Molecular structures (Chemistry)

### Chemistry^[화학]

**분자 이성질체 counting**:
- Stereoisomers
- Chiral molecules
- Crystal structures

### Computer Science^[컴퓨터 과학]

**알고리즘**:
- Graph isomorphism
- Pattern matching with symmetry
- Computational group theory

### Music Theory^[음악 이론]

**음악적 패턴**:
- Chord progressions under transposition
- Rhythmic patterns under rotation

### Art and Design^[예술과 디자인]

**패턴 디자인**:
- Wallpaper groups
- Tessellations
- Symmetrical designs

## Common Mistakes^[흔한 실수]

### 1. Wrong averaging

✗ 잘못: $X$ 원소들에 대해 평균
✓ 올바름: $G$ 원소들에 대해 평균

### 2. Forgetting identity

Identity는 항상 모든 것을 고정: $|X^e| = |X|$

### 3. Overcounting cycles

$n$-cycle rotation: fixed points는 주기 $\gcd(n, k)$인 것들

### 4. Confusion with orbits

**Counting**: Orbit 개수 (Burnside)
**Not**: Orbit 크기 (Orbit-Stabilizer)

## 계산 예시 템플릿

```
문제: G acts on X, orbit 개수는?

1. G의 원소 나열
2. 각 g에 대해:
   - g의 구조 분석 (cycle, 회전, 반사 등)
   - |X^g| 계산 (어떤 x가 g에 고정?)
3. Burnside's Lemma:
   |Orbits| = (1/|G|) Σ |X^g|
4. 검증 (가능하면 작은 예시로)
```

## Related Concepts

- [[Group Action]]: 기본 정의
- [[Orbit-Stabilizer Theorem]]: Dual theorem
- [[Sylow Theorem]]: Group structure
- [[Permutation Group]]: Natural actions
- [[Equivalence Relation and Partitions]]: Orbits as equivalence classes

## Further Reading

**입문**:
- Cameron, Combinatorics: Topics, Techniques, Algorithms
- Stanley, Enumerative Combinatorics

**중급**:
- Pólya, Tarjan, and Woods, Notes on Introductory Combinatorics
- de Bruijn, Pólya's theory of counting

**고급**:
- Harary & Palmer, Graphical Enumeration
- Read & Corneil, Graph Isomorphism

## 연습 문제

1. **Basic**: 4개 구슬, 2가지 색, 회전 대칭 목걸이
2. **Intermediate**: 정육각형 꼭짓점을 3가지 색으로 칠하기 (회전 + 반사)
3. **Advanced**: 4개 꼭짓점 labeled graphs의 isomorphism classes
4. **Challenge**: 정십이면체의 면을 5가지 색으로 칠하는 방법 (회전만)

