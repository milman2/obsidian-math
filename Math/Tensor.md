# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- [[Dual Spaces]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

$V$를 field^[체] $\mathbb{F}$ 위의 vector space^[벡터 공간]라 하자.

## Tensor product^[텐서곱]

두 vector space $V$, $W$의 **tensor product**^[텐서곱] $V \otimes W$는 다음을 만족하는 vector space이다:

Bilinear map^[쌍선형 사상] $\otimes : V \times W \rightarrow V \otimes W$가 존재하여, 임의의 vector space $U$와 bilinear map $B: V \times W \rightarrow U$에 대해, 유일한 linear map^[선형 사상] $\tilde{B}: V \otimes W \rightarrow U$가 존재하여 다음이 commute^[가환]한다:

$$B(v, w) = \tilde{B}(v \otimes w)$$

### 기본 성질
$v \otimes w \in V \otimes W$를 **elementary tensor**^[기본 텐서]라 한다. 다음이 성립:
- $(\alpha v_1 + \beta v_2) \otimes w = \alpha(v_1 \otimes w) + \beta(v_2 \otimes w)$
- $v \otimes (\alpha w_1 + \beta w_2) = \alpha(v \otimes w_1) + \beta(v \otimes w_2)$

## $(r,s)$-Tensor

Vector space $V$와 그 dual^[쌍대] $V^*$에 대해, **$(r,s)$-tensor**는 다음의 원소이다:

$$T \in \underbrace{V \otimes \cdots \otimes V}_{r \text{ times}} \otimes \underbrace{V^* \otimes \cdots \otimes V^*}_{s \text{ times}}$$

- $r$ = **contravariant rank**^[반변 계수]
- $s$ = **covariant rank**^[공변 계수]

### 다른 정의 (Multilinear map으로)

$(r,s)$-tensor는 다음과 같은 multilinear map^[다중선형 사상]으로도 정의할 수 있다:

$$T: \underbrace{V^* \times \cdots \times V^*}_{r} \times \underbrace{V \times \cdots \times V}_{s} \rightarrow \mathbb{F}$$

---

# <span class="header-properties">Properties</span>

### Dimension^[차원]

$\dim(V) = n$이면,
$$\dim(V \otimes W) = \dim(V) \cdot \dim(W)$$

Basis^[기저] $\{e_1, \ldots, e_n\}$ of $V$와 $\{f_1, \ldots, f_m\}$ of $W$에 대해:
$$\{e_i \otimes f_j : 1 \leq i \leq n, 1 \leq j \leq m\}$$
는 $V \otimes W$의 basis이다.

### $(r,s)$-Tensor space의 차원

$\dim(V) = n$이면, $(r,s)$-tensor space의 차원은:
$$n^{r+s}$$

### Tensor contraction^[텐서 축약]

$(r,s)$-tensor에서 하나의 contravariant index와 하나의 covariant index를 trace^[대각합]로 축약하면 $(r-1,s-1)$-tensor를 얻는다.

---

# <span class="header-examples">Examples</span>

### $(0,0)$-Tensor
Scalars^[스칼라]: $T \in \mathbb{F}$

### $(1,0)$-Tensor
Vectors^[벡터]: $v \in V$

### $(0,1)$-Tensor
Covectors^[여벡터] (linear functionals^[선형 범함수]): $f \in V^*$

### $(1,1)$-Tensor
Linear operators^[선형 연산자]: $T: V \rightarrow V$

성분 표기: $T^i_j$ (위 첨자는 contravariant, 아래 첨자는 covariant)

### $(0,2)$-Tensor
**Bilinear forms**^[쌍선형 형식]: $g: V \times V \rightarrow \mathbb{F}$

예시:
- Inner product^[내적]
- Riemannian metric^[리만 계량] (differential geometry에서)

### $(2,0)$-Tensor  
$T \in V \otimes V$

성분 표기: $T^{ij}$

### Specific examples

**Kronecker delta**: $(1,1)$-tensor
$$\delta^i_j = \begin{cases} 1 & \text{if } i = j \\ 0 & \text{if } i \neq j \end{cases}$$

**Metric tensor in $\mathbb{R}^3$**: $(0,2)$-tensor (Euclidean metric)
$$g_{ij} = \delta_{ij}$$

---

# <span class="header-remark">Remark</span>

### Einstein summation convention^[아인슈타인 합 표기법]

같은 첨자가 위아래로 반복되면 합을 의미:
$$T^i_j v^j = \displaystyle\sum_{j=1}^n T^i_j v^j$$

이는 tensor 계산을 간결하게 만든다.

### Tensor vs Tensor field^[텐서장]

- **Tensor**: 한 점에서의 multilinear map
- **Tensor field**^[텐서장]: 다양체의 각 점에서 정의된 tensor의 smooth^[매끄러운] 할당

Differential geometry에서는 주로 tensor field를 다룬다.

### Physics와의 관계

물리학에서 많은 양들이 tensor로 표현된다:
- Stress tensor^[응력 텐서] (역학)
- Electromagnetic field tensor^[전자기장 텐서]
- Energy-momentum tensor^[에너지-운동량 텐서] (일반상대성이론)
- Riemann curvature tensor^[리만 곡률 텐서] (일반상대성이론)

### Tensor algebra^[텐서 대수]

$V$ 위의 모든 tensor들의 직합:
$$T(V) = \bigoplus_{r,s=0}^{\infty} T^r_s(V)$$

이는 tensor product를 곱셈으로 하는 algebra^[대수]를 이룬다.

### 관련 개념
- [[Differential Forms]]: Antisymmetric covariant tensors
- Symmetric tensors: $T(v_1, v_2) = T(v_2, v_1)$
- Tensor decomposition: 임의의 tensor를 symmetric과 antisymmetric 부분으로 분해

