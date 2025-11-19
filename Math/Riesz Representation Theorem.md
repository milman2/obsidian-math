# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]

# <span class="header-reference">Reference</span>

---

# <span class="header-definition">Definition</span>

$H$를 field^[체] $\mathbb{F}$ (실수 또는 복소수) 위의 Hilbert space라 하자.  
$L: H \rightarrow \mathbb{F}$가 bounded linear functional이면,

$$\exists! \, h_0 \in H \text{ s.t. } \forall h \in H, \quad L(h) = \langle h, h_0 \rangle$$

이 성립하며, $\|L\| = \|h_0\|$이다.

---

# <span class="header-proof">Proof (Sketch)</span>

1. **Existence^[존재성]**: $\ker(L)$의 orthogonal complement^[직교여공간] $(\ker L)^\perp$를 이용
2. **Uniqueness^[유일성]**: inner product^[내적]의 positive definite 성질로부터 자명
3. **Norm equality^[노름 동등성]**: Cauchy-Schwarz inequality 활용

---

# <span class="header-remark">Remark</span>

- Hilbert space의 dual space $H^*$와 $H$ 자신 사이의 **antilinear isomorphism^[반선형 동형사상]** 제공
- 모든 bounded linear functional은 inner product^[내적]로 유일하게 표현됨
- Infinite-dimensional^[무한차원]에서도 "linear functional^[선형범함수] = vector^[벡터]와의 inner product^[내적]"이라는 직관을 일반화
