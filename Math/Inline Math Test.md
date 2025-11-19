# Inline Math Display Style Test

인라인 수식이 어떻게 표시되는지 테스트하는 파일입니다.

---

## Before (CSS 비활성화)
일반적으로 인라인 수식은 작게 표시됩니다.

## After (CSS 활성화)
인라인 수식이 15% 크게 표시되어 더 명확하게 보입니다!

---

## 분수 비교

**인라인**: 확률 공식 $P(A|B) = \frac{P(A \cap B)}{P(B)}$에서 분수가 명확하게 보입니다.

**Display**: 
$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

---

## 합과 적분

**인라인 (displaystyle 없음)**: 
- 합: $\sum_{i=1}^{n} a_i$ ← 첨자가 옆에
- 적분: $\int_0^1 f(x) \, dx$ ← 범위가 옆에
- 극한: $\lim_{n \to \infty} \frac{1}{n}$ ← 극한이 옆에

**인라인 (displaystyle 사용)**: 
- 합: $\displaystyle\sum_{i=1}^{n} a_i$ ← 첨자가 위아래로!
- 적분: $\displaystyle\int_0^1 f(x) \, dx$ ← 범위가 위아래로!
- 극한: $\displaystyle\lim_{n \to \infty} \frac{1}{n}$ ← 극한이 아래로!

**Display**:
$$\sum_{i=1}^{n} a_i, \quad \int_0^1 f(x) \, dx, \quad \lim_{n \to \infty} \frac{1}{n}$$

---

## 실제 예시

### Linear Mapping^[선형 사상]

$T: V \rightarrow W$가 linear mapping^[선형 사상]이면, 모든 $v \in V$에 대해 $T(0) = 0$이고, $\ker(T) = \{v \in V : T(v) = 0\}$이다.

### Riesz Representation

Hilbert space $H$에서 bounded linear functional $L: H \rightarrow \mathbb{F}$는 유일한 $h_0 \in H$로 표현되어 $L(h) = \langle h, h_0 \rangle$이고 $\|L\| = \|h_0\|$이다.

---

## 복잡한 수식

**Cauchy-Schwarz 부등식**: $|\langle x, y \rangle| \leq \|x\| \cdot \|y\|$

**Rank-Nullity**: $\dim(V) = \dim(\ker T) + \dim(\text{Im}(T))$

**미분 (displaystyle 사용)**: $\displaystyle\frac{d}{dx}\left(\frac{f(x)}{g(x)}\right) = \frac{f'(x)g(x) - f(x)g'(x)}{[g(x)]^2}$

---

## 사용 권장

다음과 같은 경우 인라인에서 `\displaystyle`을 사용하세요:
- $\displaystyle\sum, \prod$ (합, 곱)
- $\displaystyle\int$ (적분)
- $\displaystyle\lim$ (극한)
- $\displaystyle\frac{}{}$ (분수 - 필요시)

### 코드 예시
```markdown
$\displaystyle\sum_{i=1}^{n} a_i = a_1 + a_2 + \cdots + a_n$
```

결과: $\displaystyle\sum_{i=1}^{n} a_i = a_1 + a_2 + \cdots + a_n$

---

CSS가 제대로 적용되었다면 위의 인라인 수식들이 모두 더 크고 명확하게 보일 것입니다! ✨

이 파일은 확인 후 삭제하셔도 됩니다.

