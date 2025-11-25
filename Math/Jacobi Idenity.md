# <span class="header-prerequisite">Prerequisite</span>
- [[Commutator in Ring]]
- [[Commutator]]
- [[Group]]
- [[Ring]]

# <span class="header-reference">Reference</span>
- Jacobson, Lie Algebras
- Humphreys, Introduction to Lie Algebras and Representation Theory
- Hall, Lie Groups, Lie Algebras, and Representations

---

# <span class="header-definition">Definition</span>

## Jacobi Identity^[야코비 항등식]

### For Rings/Lie Algebras

Ring $R$ (or Lie algebra)의 원소 $a, b, c$에 대해:

$$[[a, b], c] + [[b, c], a] + [[c, a], b] = 0$$

where $[x, y] = xy - yx$ (commutator^[교환자])

**Alternative form** (cyclic sum):

$$\sum_{\text{cyc}} [[a, b], c] = 0$$

자세한 내용은 [[Commutator in Ring]] 참조

### For Groups

Group $G$의 원소 $x, y, z$에 대해:

$$[[x, y], z] \cdot [[y, z], x] \cdot [[z, x], y] = e$$

where $[g, h] = ghg^{-1}h^{-1}$ (group commutator)

**더 복잡한 형태**: Group은 곱셈 구조이므로 ring보다 복잡

자세한 내용은 [[Commutator]] 참조

## Lie Algebra^[리 대수]

Set $\mathfrak{g}$ with binary operation $[\cdot, \cdot]: \mathfrak{g} \times \mathfrak{g} \to \mathfrak{g}$가 **Lie algebra**^[리 대수]이다 $\Leftrightarrow$ 다음을 만족:

1. **Bilinearity**^[쌍선형성]: $[a\alpha + b\beta, c] = a[a,c] + b[\beta,c]$ (linear in both arguments)
2. **Anticommutativity**^[반교환성]: $[a, b] = -[b, a]$
3. **Jacobi identity**: $[[a, b], c] + [[b, c], a] + [[c, a], b] = 0$

**의미**: Jacobi identity는 Lie algebra의 핵심 조건!

## Alternative Forms^[대안 형태]

### Cyclic Form

$$[[a, b], c] + [[b, c], a] + [[c, a], b] = 0$$

### Derivation Form

$$[a, [b, c]] = [[a, b], c] + [b, [a, c]]$$

**의미**: $\text{ad}_a([\cdot, \cdot])$ is derivation

### Operator Form

For $\text{ad}_a: x \mapsto [a, x]$,

$$\text{ad}_{[a,b]} = [\text{ad}_a, \text{ad}_b]$$

**의미**: ad-map is Lie algebra homomorphism

---

# <span class="header-properties">Properties</span>

## Consequence of Associativity

**정리**: In associative ring, Jacobi identity **자동으로 성립**

**증명**: Expand $[[a,b], c] + [[b,c], a] + [[c,a], b]$ using associativity

Direct computation shows sum = 0 ✓

**의미**: Associative algebra → Lie algebra (자연스럽게)

## Bilinearity + Anticommutativity ≠ Jacobi

**주의**: Bilinearity와 anticommutativity만으로는 Jacobi identity 유도 안 됨!

**필요**: Additional constraint (associativity or explicit Jacobi)

## Equivalent Formulations

### Form 1: Standard

$$[[a, b], c] + [[b, c], a] + [[c, a], b] = 0$$

### Form 2: Derivation

$$[a, [b, c]] = [[a, b], c] + [b, [a, c]]$$

**증명**: 
$$[a, [b,c]] = a(bc-cb) - (bc-cb)a$$
$$= abc - acb - bca + cba$$

$$[[a,b], c] + [b, [a,c]] = (ab-ba)c - c(ab-ba) + b(ac-ca) - (ac-ca)b$$
$$= abc - bac - cab + cba + bac - bca - acb + cab$$
$$= abc - acb - bca + cba$$ ✓

### Form 3: Operator

$$[\text{ad}_a, \text{ad}_b] = \text{ad}_{[a,b]}$$

where $[\text{ad}_a, \text{ad}_b](c) = \text{ad}_a(\text{ad}_b(c)) - \text{ad}_b(\text{ad}_a(c))$

## Relation to Associativity

**Associative algebra**: $(ab)c = a(bc)$

**Lie algebra**: No associativity, but Jacobi identity instead

**관계**: Jacobi = "weak form of associativity"

## Adjoint Representation

**정리**: Map $\text{ad}: \mathfrak{g} \to \text{End}(\mathfrak{g})$ defined by

$$\text{ad}_a(b) = [a, b]$$

is **Lie algebra homomorphism**

**증명**: Jacobi identity $\Leftrightarrow$ $\text{ad}_{[a,b]} = [\text{ad}_a, \text{ad}_b]$ ✓

---

# <span class="header-examples">Examples</span>

## Example 1: Matrix Commutators

**$M_n(\mathbb{R})$**: $n \times n$ matrices with $[A, B] = AB - BA$

$$A = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}, \quad B = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}, \quad C = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}$$

**Verify**: $[[A, B], C] + [[B, C], A] + [[C, A], B] = 0$

**자동**: Matrices form associative algebra!

## Example 2: Quaternions

**$\mathbb{H}$**: $\{a + bi + cj + dk\}$

$$i, j, k \text{ satisfy: } [i, j] = 2k, \; [j, k] = 2i, \; [k, i] = 2j$$

**Check Jacobi**:

$$[[i, j], k] + [[j, k], i] + [[k, i], j] = [2k, k] + [2i, i] + [2j, j] = 0 + 0 + 0 = 0$$ ✓

## Example 3: Vector Fields

**Lie bracket of vector fields** $X, Y$ on manifold:

$$[X, Y] = XY - YX$$

(composition of differential operators)

**Jacobi identity**: Geometric meaning
- Relates curvature
- Triple bracket vanishes

## Example 4: Derivations

**Der($A$)**: Derivations of algebra $A$

For derivations $D_1, D_2$:

$$[D_1, D_2] = D_1 \circ D_2 - D_2 \circ D_1$$

**Jacobi identity**: Automatically satisfied (associativity of composition)

## Example 5: Poisson Brackets

**Classical mechanics**: Phase space with Poisson bracket

$$\{f, g\} = \sum_i \left( \frac{\partial f}{\partial q_i} \frac{\partial g}{\partial p_i} - \frac{\partial f}{\partial p_i} \frac{\partial g}{\partial q_i} \right)$$

**Jacobi identity**: 

$$\{\{f, g\}, h\} + \{\{g, h\}, f\} + \{\{h, f\}, g\} = 0$$

**물리적 의미**: Conservation laws, symmetries

## Example 6: Cross Product

**$\mathbb{R}^3$ with cross product** $\times$:

$$[\mathbf{a}, \mathbf{b}] = \mathbf{a} \times \mathbf{b}$$

**Jacobi identity**:

$$\mathbf{a} \times (\mathbf{b} \times \mathbf{c}) + \mathbf{b} \times (\mathbf{c} \times \mathbf{a}) + \mathbf{c} \times (\mathbf{a} \times \mathbf{b}) = \mathbf{0}$$

**Check**: Use vector triple product formula ✓

---

# <span class="header-proof">Proof</span>

## Proof in Associative Algebra

**정리**: In associative ring $R$, Jacobi identity holds

**증명**: Expand using $[a,b] = ab - ba$ and associativity

$$[[a, b], c] = [ab - ba, c] = (ab-ba)c - c(ab-ba)$$
$$= abc - bac - cab + cba$$

$$[[b, c], a] = (bc-cb)a - a(bc-cb)$$
$$= bca - cba - abc + acb$$

$$[[c, a], b] = (ca-ac)b - b(ca-ac)$$
$$= cab - acb - bca + bac$$

**Sum**:
$$(abc - bac - cab + cba) + (bca - cba - abc + acb) + (cab - acb - bca + bac)$$
$$= 0$$ ✓

All terms cancel!

## Proof Using Derivation Property

**정리**: $[a, [b,c]] = [[a,b], c] + [b, [a,c]]$ (Leibniz rule)

**증명**:
$$[a, [b,c]] = a(bc-cb) - (bc-cb)a = abc - acb - bca + cba$$

$$[[a,b], c] = (ab-ba)c - c(ab-ba) = abc - bac - cab + cba$$

$$[b, [a,c]] = b(ac-ca) - (ac-ca)b = bac - bca - acb + cab$$

**Sum**: $[[a,b], c] + [b, [a,c]] = abc - acb - bca + cba$ ✓

## Geometric Interpretation

**Vector fields** on manifold:

**Jacobi identity**: 

$$[X, [Y, Z]] = [[X, Y], Z] + [Y, [X, Z]]$$

**의미**: "Covariant derivative" structure
- Compatibility with Lie bracket
- Curvature constraints

---

# <span class="header-theorem">Theorem</span>

## Universal Enveloping Algebra

**정리**: Every Lie algebra $\mathfrak{g}$ embeds into associative algebra $U(\mathfrak{g})$

$$\mathfrak{g} \hookrightarrow U(\mathfrak{g})$$

where Lie bracket = commutator in $U(\mathfrak{g})$

**Jacobi identity**: Automatically satisfied in $U(\mathfrak{g})$

## Poincaré-Birkhoff-Witt Theorem

**정리**: If $\{x_i\}$ basis of $\mathfrak{g}$, then $\{x_{i_1} \cdots x_{i_k} : i_1 \leq \cdots \leq i_k\}$ is basis of $U(\mathfrak{g})$

**응용**: Structure theory of Lie algebras

## Classification of Simple Lie Algebras

**정리**: Finite-dimensional simple Lie algebras (over $\mathbb{C}$) classified:
- Classical: $A_n, B_n, C_n, D_n$
- Exceptional: $G_2, F_4, E_6, E_7, E_8$

**Jacobi identity**: Essential in classification

## Ado's Theorem

**정리**: Every finite-dimensional Lie algebra over field of characteristic 0 has faithful finite-dimensional representation

**의미**: Can realize Lie algebra as matrices

---

# <span class="header-remark">Remark</span>

## 직관적 이해

**Jacobi Identity = "Consistency condition"**

### 메타포: 경로 독립성

**3개 원소** $a, b, c$를 bracket으로 결합

**여러 순서**: $(ab)c$ vs $a(bc)$ vs ...

**Jacobi**: 모든 경로가 consistent

**결과**: Well-defined structure

### 메타포: 미분

**Leibniz rule**: $\frac{d}{dx}(fg) = f'g + fg'$

**Jacobi**: Similar structure for Lie brackets

$$[a, [b,c]] = [[a,b], c] + [b, [a,c]]$$

**의미**: $\text{ad}_a$ acts like "differentiation"

### 메타포: 물리학

**Quantum mechanics**: Observables don't commute

**Jacobi**: Consistency of measurements

**Poisson brackets**: Classical analog

## 왜 중요한가?

### 1. Defines Lie Algebras

**Fundamental axiom**: Lie algebra = vector space + bracket + Jacobi

**Without Jacobi**: Just alternating bilinear form

### 2. Symmetries

**Lie groups**: Continuous symmetries

**Lie algebras**: Infinitesimal symmetries

**Jacobi**: Ensures consistent structure

### 3. Physics

**Quantum mechanics**: Observables as Lie algebra

**Symmetries**: Conservation laws (Noether's theorem)

**Gauge theories**: Yang-Mills, Standard Model

### 4. Differential Geometry

**Vector fields**: Lie bracket of vector fields

**Curvature**: Related to Jacobi identity

**Connection**: Differential structure

### 5. Representation Theory

**Modules**: Lie algebra representations

**Classification**: Uses Jacobi heavily

## Associative vs Lie

| | **Associative Algebra** | **Lie Algebra** |
|---|---|---|
| **Binary operation** | Associative | Jacobi identity |
| **Identity** | May have unit | No identity |
| **Commutativity** | Optional | Anticommutative |
| **예** | Matrix algebra | $\mathfrak{gl}_n$ with $[A,B]$ |

**관계**: Associative algebra → Lie algebra via commutator

## 계산 방법

### Verify Jacobi Identity

**Step 1**: Compute $[a, b]$, $[b, c]$, $[c, a]$

**Step 2**: Compute $[[a,b], c]$, $[[b,c], a]$, $[[c,a], b]$

**Step 3**: Add: Check if sum = 0

### For Associative Algebra

**Automatic**: Don't need to check!

Just verify associativity of multiplication

### For General Bracket

**Must verify explicitly**: Bilinearity, anticommutativity, Jacobi

## 표기법

| 표기 | 의미 |
|------|------|
| $[a, b]$ | Lie bracket / Commutator |
| $\text{ad}_a(b)$ | Adjoint action $[a, b]$ |
| $\mathfrak{g}$ | Lie algebra |
| $U(\mathfrak{g})$ | Universal enveloping algebra |
| $\sum_{\text{cyc}}$ | Cyclic sum |

## Common Pitfall^[흔한 실수]

### 1. Assuming Associativity

Lie algebras are **NOT** associative!

$(ab)c \neq a(bc)$ in general

Jacobi is weaker than associativity

### 2. Group vs Lie Algebra Jacobi

**Different forms**!

Lie algebra: Sum = 0 (additive)

Group: Product = e (multiplicative)

### 3. Forgetting Anticommutativity

$[a, b] = -[b, a]$ must hold!

Not just bilinearity

### 4. Bilinear ≠ Jacobi

Can have bilinear, anticommutative operation without Jacobi

**Example**: Not every bilinear alternating form gives Lie algebra

### 5. Assuming Identity Element

Lie algebras have **NO** identity element for bracket!

$[a, e] = a$ doesn't make sense

## 응용 분야

**Physics**:
- Quantum mechanics
- Particle physics (gauge theories)
- Classical mechanics (Poisson manifolds)
- String theory

**Mathematics**:
- Lie groups and Lie algebras
- Differential geometry
- Algebraic topology
- Representation theory

**Engineering**:
- Control theory
- Robotics (configuration spaces)

**Computer Science**:
- Quantum computing
- Geometric algorithms

## 역사적 맥락

**Sophus Lie** (1870s): Studied continuous symmetry groups

**Carl Gustav Jacob Jacobi** (1804-1851): Poisson brackets, dynamics

**Wilhelm Killing, Élie Cartan** (1890s): Classification of Lie algebras

**Hermann Weyl** (1920s): Representation theory

## 관련 개념

- [[Commutator in Ring]]: Definition of bracket
- [[Commutator]]: Group version
- [[Ring]]: Associative structure
- [[Group]]: Basic structure

## 추가 학습 주제

**기초**:
- Definition
- Verification in examples
- Derivation form

**중급**:
- Lie algebras
- Adjoint representation
- Structure theory

**고급**:
- Classification of simple Lie algebras
- Universal enveloping algebras
- PBW theorem
- Representation theory
- Kac-Moody algebras
- Quantum groups

