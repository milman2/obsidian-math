# <span class="header-prerequisite">Prerequisite</span>
- Vector space

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

$V$, $W$를 field^[체] $\mathbb{F}$ 위의 vector space^[벡터 공간]이라 하자.  
함수 $T: V \rightarrow W$가 **linear mapping^[선형 사상]**이라는 것은 다음을 만족하는 것이다:

$$\forall u, v \in V, \, \forall \alpha, \beta \in \mathbb{F}, \quad T(\alpha u + \beta v) = \alpha T(u) + \beta T(v)$$

---

# <span class="header-properties">Properties</span>

### Basic Properties^[기본 성질]
- $T(0_V) = 0_W$
- $T(-v) = -T(v)$
- $T\left(\displaystyle\sum_{i=1}^n \alpha_i v_i\right) = \displaystyle\sum_{i=1}^n \alpha_i T(v_i)$ (linear combination^[선형결합] 보존)

### Important Subspaces^[중요한 부분공간]
**Kernel^[핵]:**
$$\ker(T) = \{v \in V : T(v) = 0_W\}$$

**Image^[상]:**
$$\text{Im}(T) = \{w \in W : \exists v \in V \text{ s.t. } T(v) = w\}$$

### Injective & Surjective^[단사와 전사]
- $T$가 injective^[단사] $\Leftrightarrow$ $\ker(T) = \{0\}$
- $T$가 surjective^[전사] $\Leftrightarrow$ $\text{Im}(T) = W$
- $T$가 isomorphism^[동형사상] $\Leftrightarrow$ $T$가 injective이면서 surjective

---

# Rank-Nullity Theorem

$V$가 finite-dimensional^[유한차원] vector space^[벡터 공간]이면,

$$\dim(V) = \dim(\ker T) + \dim(\text{Im}(T))$$

---

# <span class="header-examples">Examples</span>

- **Identity map^[항등 사상]**: $I(v) = v$
- **Zero map^[영 사상]**: $0(v) = 0_W$
- **Differential operator^[미분 연산자]**: $D(f) = f'$
- **Matrix multiplication^[행렬 곱셈]**: $T_A(x) = Ax$

---

# <span class="header-remark">Remark</span>

- Vector space^[벡터 공간]의 structure^[구조]를 보존하는 함수
- Finite-dimensional^[유한차원]에서는 matrix^[행렬]로 완전히 표현됨
- Functional analysis^[함수해석학]에서 bounded linear operator, compact operator 등으로 일반화

