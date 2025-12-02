# <span class="header-prerequisite">Prerequisite</span>
- [[Homology]]
- [[Exact Sequence]]
- [[Chain Complex]]
- [[Topological Space]]

# <span class="header-reference">Reference</span>
- Hatcher, Algebraic Topology
- Spanier, Algebraic Topology
- Bredon, Topology and Geometry

---

# <span class="header-definition">Definition</span>

## Mayer-Vietoris Sequence^[마이어-비에토리스 수열]

**Setup**^[설정]: 위상공간 \(X = A \cup B\) (where \(A, B\) are open or closed subspaces)

**Mayer-Vietoris sequence**^[마이어-비에토리스 수열]는 다음과 같은 **long exact sequence**^[긴 완전 수열]:

$$\cdots \to H_n(A \cap B) \xrightarrow{\phi_n} H_n(A) \oplus H_n(B) \xrightarrow{\psi_n} H_n(X) \xrightarrow{\partial_n} H_{n-1}(A \cap B) \to \cdots$$

여기서:
- \(H_n\): \(n\)-th homology group^[n차 호모로지군]
- \(\phi_n\): Inclusion map^[포함 사상] induced by \(A \cap B \hookrightarrow A\), \(A \cap B \hookrightarrow B\)
- \(\psi_n\): Sum map^[합 사상] from \(H_n(A) \oplus H_n(B) \to H_n(X)\)
- \(\partial_n\): **Connecting homomorphism**^[연결 준동형사상] (boundary map)

**핵심 아이디어**: "전체 공간의 호모로지 = 부분공간들의 호모로지로부터 복원"

## Explicit Maps^[명시적 사상]

### \(\phi_n\): Inclusion Map

$$\phi_n: H_n(A \cap B) \to H_n(A) \oplus H_n(B)$$

$$\phi_n([c]) = (i_*[c], j_*[c])$$

where:
- \(i: A \cap B \hookrightarrow A\)
- \(j: A \cap B \hookrightarrow B\)

### \(\psi_n\): Sum Map

$$\psi_n: H_n(A) \oplus H_n(B) \to H_n(X)$$

$$\psi_n([a], [b]) = i'_*[a] + j'_*[b]$$

where:
- \(i': A \hookrightarrow X\)
- \(j': B \hookrightarrow X\)

### \(\partial_n\): Connecting Homomorphism

$$\partial_n: H_n(X) \to H_{n-1}(A \cap B)$$

**구성**: Snake lemma^[뱀 보조정리]로부터 유도

**기하학적 의미**: \(X\)의 \(n\)-cycle에서 \((n-1)\)-boundary on \(A \cap B\)로

## Cohomology Version^[코호모로지 버전]

**Dual^[쌍대] version**: Arrows reverse!

$$\cdots \leftarrow H^n(A \cap B) \xleftarrow{\phi^n} H^n(A) \oplus H^n(B) \xleftarrow{\psi^n} H^n(X) \xleftarrow{\delta^n} H^{n+1}(A \cap B) \leftarrow \cdots$$

또는 화살표를 오른쪽으로 쓰면:

$$\cdots \to H^n(X) \xrightarrow{\delta^n} H^n(A) \oplus H^n(B) \xrightarrow{\phi^n} H^n(A \cap B) \xrightarrow{\delta^{n+1}} H^{n+1}(X) \to \cdots$$

**차이점**: Cohomology는 contravariant^[반변]이므로 degree가 증가

## de Rham Cohomology Version^[드람 코호모로지 버전]

Smooth manifolds \(M = U \cup V\)에 대해:

$$\cdots \to H^k_{dR}(M) \to H^k_{dR}(U) \oplus H^k_{dR}(V) \to H^k_{dR}(U \cap V) \to H^{k+1}_{dR}(M) \to \cdots$$

**응용**: Differential forms를 이용한 cohomology 계산

자세한 내용은 [[Differential Forms]] 참조

---

# <span class="header-properties">Properties</span>

## Exactness^[완전성]

**정리**: Mayer-Vietoris sequence는 **exact**^[완전]

$$\text{im}(\phi_n) = \ker(\psi_n), \quad \text{im}(\psi_n) = \ker(\partial_n), \quad \text{im}(\partial_n) = \ker(\phi_{n-1})$$

**의미**: 각 위치에서 image = kernel

자세한 내용은 [[Exact Sequence]] 참조

## Naturality^[자연성]

**정리**: Continuous map^[연속 사상] \(f: X \to X'\)에 대해, diagram commutes:

```
H_n(A ∩ B) → H_n(A) ⊕ H_n(B) → H_n(X) → H_{n-1}(A ∩ B)
    ↓              ↓               ↓              ↓
H_n(A'∩B') → H_n(A')⊕ H_n(B') → H_n(X') → H_{n-1}(A'∩B')
```

**의미**: Functorial^[함자적] in \(X\)

## Functoriality^[함자성]

Mayer-Vietoris sequence는 **functorial**^[함자적]

- Maps of pairs \((X, A, B) \to (X', A', B')\) induce maps of sequences
- Composition preserved

## Additivity^[가법성]

$$H_n(A) \oplus H_n(B) = H_n(A \sqcup B) \text{ (disjoint union)}$$

**특수 경우**: \(A \cap B = \emptyset\)이면:

$$H_n(X) \cong H_n(A) \oplus H_n(B)$$

---

# <span class="header-examples">Examples</span>

## Example 1: Homology of Sphere \(S^2\)

**Setup**: \(S^2 = U \cup V\)
- \(U\): Upper hemisphere (contractible^[축약가능])
- \(V\): Lower hemisphere (contractible)
- \(U \cap V \simeq S^1\) (equator)

**Mayer-Vietoris**:

$$\cdots \to H_n(S^1) \to H_n(U) \oplus H_n(V) \to H_n(S^2) \to H_{n-1}(S^1) \to \cdots$$

**For \(n = 2\)**:

$$0 \to 0 \oplus 0 \to H_2(S^2) \to H_1(S^1) \to \cdots$$

$$H_2(S^2) \cong \mathbb{Z}$$

**For \(n = 1\)**:

$$\cdots \to H_1(S^1) \to 0 \oplus 0 \to H_1(S^2) \to H_0(S^1) \to \cdots$$

$$\mathbb{Z} \to 0 \to H_1(S^2) \to \mathbb{Z} \xrightarrow{\text{iso}} \mathbb{Z}$$

$$H_1(S^2) = 0$$

**결과**:

$$H_n(S^2) = \begin{cases} \mathbb{Z} & n = 0, 2 \\ 0 & \text{otherwise} \end{cases}$$

## Example 2: Homology of Torus \(T^2 = S^1 \times S^1\)

**Setup**: \(T^2 = A \cup B\)
- \(A\): Solid torus \(S^1 \times D^1\) (homotopy equivalent to \(S^1\))
- \(B\): Solid torus \(S^1 \times D^1\)
- \(A \cap B \simeq S^1 \vee S^1\) (two circles)

**Mayer-Vietoris** (\(n = 2\)):

$$H_2(S^1 \vee S^1) \to H_2(A) \oplus H_2(B) \to H_2(T^2) \to H_1(S^1 \vee S^1) \to \cdots$$

$$0 \to 0 \to H_2(T^2) \to \mathbb{Z} \oplus \mathbb{Z} \to \cdots$$

**계산**:

$$H_2(T^2) \cong \mathbb{Z}$$

$$H_1(T^2) \cong \mathbb{Z} \oplus \mathbb{Z}$$

**결과**:

$$H_n(T^2) = \begin{cases} \mathbb{Z} & n = 0, 2 \\ \mathbb{Z}^2 & n = 1 \\ 0 & n \geq 3 \end{cases}$$

자세한 내용은 [[Torus]] 참조

## Example 3: Homology of \(S^n\)

**Induction**^[귀납법]: \(S^n = U \cup V\) (two hemispheres)

- \(U, V \simeq \text{pt}\) (contractible)
- \(U \cap V \simeq S^{n-1}\)

**Mayer-Vietoris**:

$$H_k(S^{n-1}) \to 0 \to H_k(S^n) \to H_{k-1}(S^{n-1})$$

**Inductive step**:

$$H_k(S^n) \cong H_{k-1}(S^{n-1})$$

**Base case**: \(H_0(S^0) = \mathbb{Z} \oplus \mathbb{Z}\)

**결과**:

$$H_k(S^n) = \begin{cases} \mathbb{Z} & k = 0, n \\ 0 & \text{otherwise} \end{cases}$$

## Example 4: Klein Bottle^[클라인 병]

**Setup**: \(K = A \cup B\)
- Both \(A, B\) are Möbius strips
- \(A \cap B \simeq S^1 \vee S^1\)

**Result**:

$$H_1(K) \cong \mathbb{Z} \oplus \mathbb{Z}/2\mathbb{Z}$$

$$H_2(K) = 0$$

**의미**: Klein bottle은 non-orientable^[방향불가능]

## Example 5: Connected Sum^[연결합]

**Setup**: \(M_1 \# M_2 = (M_1 \setminus D^n) \cup (M_2 \setminus D^n)\)

**Mayer-Vietoris**: Compute \(H_*(M_1 \# M_2)\) from \(H_*(M_1)\), \(H_*(M_2)\)

**For surfaces**:

$$H_1(M_1 \# M_2) \cong H_1(M_1) \oplus H_1(M_2)$$

## Example 6: Wedge Sum^[쐐기합]

**Setup**: \(X \vee Y = X \sqcup Y / (x_0 \sim y_0)\)

Choose \(A, B\) such that \(A \cap B = \{x_0\}\) (single point)

**Mayer-Vietoris**:

$$H_n(X \vee Y) \cong H_n(X) \oplus H_n(Y) \quad (n \geq 1)$$

**For \(n = 0\)**:

$$H_0(X \vee Y) \cong \mathbb{Z}$$

## Example 7: CW Complex^[CW 복체]

**Attaching \(n\)-cell**: \(X^n = X^{n-1} \cup_\phi D^n\)

**Mayer-Vietoris** + Cellular homology:

$$H_k(X^n, X^{n-1}) \cong \begin{cases} \mathbb{Z}^{\# \text{ of } n\text{-cells}} & k = n \\ 0 & k \neq n \end{cases}$$

자세한 내용은 [[CW Complex]] 참조

## Example 8: Complement of Knot^[매듭의 여공간]

**Setup**: \(S^3 \setminus K\) (knot complement)

**Mayer-Vietoris**: Decompose using tubular neighborhood

**결과**: Compute knot invariants (Alexander polynomial, etc.)

자세한 내용은 [[Knot Theory]] 참조

---

# <span class="header-theorem">Theorem</span>

## Mayer-Vietoris Theorem

**정리**: For topological space \(X = A \cup B\) (open or closed), there exists a long exact sequence:

$$\cdots \to H_n(A \cap B) \to H_n(A) \oplus H_n(B) \to H_n(X) \to H_{n-1}(A \cap B) \to \cdots$$

**증명 idea**:
1. Construct short exact sequence of chain complexes:

$$0 \to C_*(A \cap B) \to C_*(A) \oplus C_*(B) \to C_*(X) \to 0$$

2. Apply Snake Lemma or Long Exact Sequence of Homology

3. Get connecting homomorphism \(\partial_n\)

자세한 내용은 [[Snake Lemma]] 참조

## Reduced Homology Version^[축약 호모로지 버전]

**정리**: Using reduced homology^[축약 호모로지] \(\tilde{H}_*\):

$$\cdots \to \tilde{H}_n(A \cap B) \to \tilde{H}_n(A) \oplus \tilde{H}_n(B) \to \tilde{H}_n(X) \to \tilde{H}_{n-1}(A \cap B) \to \cdots$$

**장점**: Simpler for \(n = 0\) (no \(\mathbb{Z}\) correction)

## Relative Mayer-Vietoris

**정리**: For pairs \((X, C) = (A, C) \cup (B, C)\):

$$\cdots \to H_n(A \cap B, C) \to H_n(A, C) \oplus H_n(B, C) \to H_n(X, C) \to H_{n-1}(A \cap B, C) \to \cdots$$

**응용**: Relative homology 계산

자세한 내용은 [[Relative Homology]] 참조

## Good Cover Theorem^[좋은 덮개 정리]

**정리**: If \(X\) has a good cover^[좋은 덮개] (all finite intersections contractible), then:

$$H^*(X) \cong H^*(\text{Čech complex of cover})$$

**의미**: Iterated Mayer-Vietoris computes cohomology

자세한 내용은 [[Čech Cohomology]] 참조

---

# <span class="header-proof">Proof</span>

## Construction of Short Exact Sequence

**Step 1**: Define chain map^[사슬 사상]

$$\phi: C_n(A \cap B) \to C_n(A) \oplus C_n(B), \quad \phi(c) = (i_\#(c), j_\#(c))$$

$$\psi: C_n(A) \oplus C_n(B) \to C_n(X), \quad \psi(a, b) = i'_\#(a) + j'_\#(b)$$

**Step 2**: Check exactness at chain level

$$0 \to C_*(A \cap B) \xrightarrow{\phi} C_*(A) \oplus C_*(B) \xrightarrow{\psi} C_*(X) \to 0$$

**Exactness at \(C_*(A) \oplus C_*(B)\)**:

$$\ker(\psi) = \{(a, b) : i'_\#(a) = -j'_\#(b)\} = \text{im}(\phi)$$

**Surjectivity of \(\psi\)**:

Use partition of unity or barycentric subdivision:
- Every chain in \(X\) can be written as sum of chains in \(A\) and \(B\)

## Long Exact Sequence of Homology

**Step 3**: Apply functor \(H_*\) to short exact sequence

From short exact sequence of chain complexes, get long exact sequence:

$$\cdots \to H_n(C_*(A \cap B)) \to H_n(C_*(A) \oplus C_*(B)) \to H_n(C_*(X)) \to H_{n-1}(C_*(A \cap B)) \to \cdots$$

**Step 4**: Identify with homology groups

$$H_n(C_*(Y)) = H_n(Y)$$

자세한 내용은 [[Chain Complex]] 참조

## Connecting Homomorphism^[연결 준동형사상]

**Diagram chase**: Given \([x] \in H_n(X)\)

1. Lift \(x\) to \((a, b) \in C_n(A) \oplus C_n(B)\) (surjectivity)
2. Compute \(\partial(a, b) = (\partial a, \partial b)\)
3. Note: \(\psi(\partial a, \partial b) = \partial \psi(a, b) = \partial x = 0\)
4. So \((\partial a, \partial b) \in \ker(\psi) = \text{im}(\phi)\)
5. Find \(c \in C_{n-1}(A \cap B)\) with \(\phi(c) = (\partial a, \partial b)\)
6. Define \(\partial_n[x] = [c] \in H_{n-1}(A \cap B)\)

**Well-defined**: Independent of choices

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**핵심 아이디어**: "전체를 부분으로 나누어 이해"

**메타포**: 퍼즐 조각
- \(A\), \(B\): 두 퍼즐 조각
- \(A \cap B\): 겹치는 부분
- Mayer-Vietoris: 조각들의 정보로부터 전체 그림 복원

**Connecting homomorphism \(\partial\)**:
- \(X\)의 cycle이 \(A\)와 \(B\)에서 "mismatch"하는 정도
- Mismatch가 \(A \cap B\)의 boundary

## 역사적 배경

**Walther Mayer** (1887-1948):
- Austrian mathematician
- Worked with Einstein on unified field theory

**Leopold Vietoris** (1891-2002):
- Austrian mathematician, topologist
- Lived 110 years!
- Independently discovered the sequence (1927-1930)

**Original context**: Homology theory development in 1920s-1930s

## 응용 분야

### 1. Computational Topology^[계산 위상수학]

**알고리즘**: Decompose complex spaces recursively

**효율성**: \(O(\log n)\) depth for balanced decomposition

### 2. Algebraic Topology^[대수적 위상수학]

**Classification**: Surfaces, 3-manifolds, higher dimensions

**Invariants**: Betti numbers, Euler characteristic

$$\chi(X) = \chi(A) + \chi(B) - \chi(A \cap B)$$

자세한 내용은 [[Euler Characteristic]] 참조

### 3. Differential Geometry^[미분기하학]

**de Rham cohomology**: Using differential forms

**Integration**: Stokes' theorem on manifolds with boundary

자세한 내용은 [[de Rham Cohomology]] 참조

### 4. Algebraic Geometry^[대수기하학]

**Sheaf cohomology**: Mayer-Vietoris for sheaves

**Covering**: Compute cohomology via open covers

자세한 내용은 [[Sheaf Cohomology]] 참조

### 5. Data Analysis^[데이터 분석]

**Persistent homology**: Compute barcodes via Mayer-Vietoris

**Divide and conquer**: Large datasets

## Generalization^[일반화]

### Čech Cohomology^[체흐 코호모로지]

**Idea**: Iterate Mayer-Vietoris for arbitrary covers

$$X = \bigcup_{i \in I} U_i$$

**Čech complex**: Intersections of open sets

자세한 내용은 [[Čech Cohomology]] 참조

### Sheaf Theory^[층 이론]

**Mayer-Vietoris for sheaves**: 

$$0 \to \mathcal{F}(X) \to \mathcal{F}(U) \oplus \mathcal{F}(V) \to \mathcal{F}(U \cap V)$$

**Long exact sequence**: Sheaf cohomology

자세한 내용은 [[Sheaf Cohomology]] 참조

### Excision Theorem^[절제 정리]

**관계**: Mayer-Vietoris is consequence of Excision

**Excision**: \(H_*(X, A) \cong H_*(X \setminus Z, A \setminus Z)\) for "good" \(Z\)

자세한 내용은 [[Excision Theorem]] 참조

## Comparison: Homology vs Cohomology

| Concept | Homology | Cohomology |
|---------|----------|------------|
| **Direction** | Covariant^[공변] | Contravariant^[반변] |
| **Connecting map** | \(\partial_n: H_n(X) \to H_{n-1}(A \cap B)\) | \(\delta^n: H^n(A \cap B) \to H^{n+1}(X)\) |
| **Degree change** | Decreases by 1 | Increases by 1 |
| **Maps from** | Chains | Cochains |
| **Structure** | Abelian group | Ring (cup product) |

**의미**: Cohomology has richer structure (ring, cup product)

자세한 내용은 [[Cup Product]] 참조

## Common Pitfalls^[흔한 실수]

### 1. Exactness Misunderstanding

✗ "\(\phi_n\) injective?"

✓ **NO!** Only \(\text{im}(\partial_{n+1}) = \ker(\phi_n)\)

### 2. Connecting Map Direction

✗ Cohomology connecting map decreases degree?

✓ **Increases!** \(\delta^n: H^n(A \cap B) \to H^{n+1}(X)\)

### 3. Open vs Closed

✗ Must \(A, B\) be open?

✓ Open **or** closed (or satisfy excision property)

### 4. Formula for \(\partial\)

✗ Explicit formula always computable?

✓ Diagram chase needed; formula depends on chain representatives

### 5. Reduced vs Unreduced

✗ Reduced and unreduced give same sequence?

✓ Differ at \(n = 0\); reduced is simpler

## Related Concepts^[관련 개념]

### Exact Sequences

- [[Exact Sequence]]: Definition and properties
- [[Snake Lemma]]: Connecting homomorphism
- [[Five Lemma]]: Diagram chasing
- [[Long Exact Sequence]]: General construction

### Homology Theories

- [[Singular Homology]]: Definition via singular simplices
- [[Cellular Homology]]: CW complexes
- [[Simplicial Homology]]: Simplicial complexes
- [[de Rham Cohomology]]: Differential forms

### Applications

- [[CW Complex]]: Cellular decomposition
- [[Fundamental Group]]: \(\pi_1\) computation
- [[Euler Characteristic]]: Inclusion-exclusion
- [[Knot Invariants]]: Knot complements

## Computational Strategy^[계산 전략]

**How to use Mayer-Vietoris**:

1. **Decompose**: Choose \(A, B\) such that:
   - \(H_*(A)\), \(H_*(B)\), \(H_*(A \cap B)\) are known
   - Preferably contractible or simple

2. **Write sequence**: Long exact sequence for desired \(n\)

3. **Use exactness**: 
   - Image = Kernel at each position
   - Rank-nullity theorem

4. **Identify maps**: 
   - \(\phi_n\) often diagonal
   - \(\psi_n\) often addition/subtraction

5. **Solve**: 
   - Use exactness to determine \(H_n(X)\)
   - May need multiple degrees

**Example strategy**: For \(S^2\), use contractible hemispheres \(\Rightarrow H_*(U) = H_*(V) = 0\)

