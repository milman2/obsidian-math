# <span class="header-prerequisite">Prerequisite</span>
- [[Linear mapping]]
- Set theory (basic)

# <span class="header-reference">Reference</span>
- [Category Theory for Beginners](https://www.youtube.com/watch?v=-KarQL5H3GI)

---

# <span class="header-definition">Definition</span>

## Category^[범주]

**Category**^[범주] $\mathcal{C}$는 다음으로 구성된다:

1. **Objects**^[대상들] (collection): $\text{Ob}(\mathcal{C})$
2. **Morphisms**^[사상들] (arrows): 각 object 쌍 $A, B$에 대해 $\text{Hom}(A, B)$ 또는 $\mathcal{C}(A,B)$
3. **Composition**^[합성]: morphisms의 합성 연산 $\circ$
4. **Identity morphisms**^[항등 사상]: 각 object $A$에 대해 $\text{id}_A: A \rightarrow A$

### Laws (공리)

다음을 만족해야 한다:

**Associativity**^[결합법칙]:
$$h \circ (g \circ f) = (h \circ g) \circ f$$

**Identity**^[항등원]:
$$f \circ \text{id}_A = f = \text{id}_B \circ f$$
for $f: A \rightarrow B$.

## Functor^[함자]

Categories 사이의 mapping. Functor $F: \mathcal{C} \rightarrow \mathcal{D}$는:
- Objects를 objects로: $F(A) \in \text{Ob}(\mathcal{D})$
- Morphisms를 morphisms로: $F(f: A \rightarrow B) = F(f): F(A) \rightarrow F(B)$

다음을 보존:
- Composition: $F(g \circ f) = F(g) \circ F(f)$
- Identity: $F(\text{id}_A) = \text{id}_{F(A)}$

## Natural transformation^[자연 변환]

Functors 사이의 morphism. $F, G: \mathcal{C} \rightarrow \mathcal{D}$에 대해, natural transformation $\eta: F \Rightarrow G$는:

각 object $A \in \mathcal{C}$에 대해 morphism $\eta_A: F(A) \rightarrow G(A)$를 할당하며, 다음이 commute^[가환]:

$$\eta_B \circ F(f) = G(f) \circ \eta_A$$

for all $f: A \rightarrow B$.

---

# <span class="header-examples">Examples: Categories 분류</span>

## 1. Concrete Categories^[구체적 범주]

Objects가 sets with structure인 경우:

### **Set**
- **Objects**: Sets (집합)
- **Morphisms**: Functions (함수)
- 가장 기본적인 category

### **Grp**
- **Objects**: Groups (군)
- **Morphisms**: Group homomorphisms (군 준동형사상)

### **Ring**
- **Objects**: Rings (환)
- **Morphisms**: Ring homomorphisms (환 준동형사상)

### **Top**
- **Objects**: Topological spaces (위상공간)
- **Morphisms**: Continuous functions (연속함수)

### **TopHaus** (또는 **Haus**)
- **Objects**: Hausdorff topological spaces (하우스도르프 위상공간)
- **Morphisms**: Continuous functions (연속함수)
- Top의 full subcategory^[완전 부분범주]

### **Homeo**
- **Objects**: Topological spaces (위상공간)
- **Morphisms**: Homeomorphisms (위상동형사상)
- Top의 isomorphisms만 포함하는 subcategory

### **Vect**_$\mathbb{F}$
- **Objects**: Vector spaces over field $\mathbb{F}$
- **Morphisms**: Linear maps (선형 사상)
- 예: **Vect**_$\mathbb{R}$, **Vect**_$\mathbb{C}$

### **Man**
- **Objects**: Smooth manifolds (미분가능 다양체)
- **Morphisms**: Smooth maps (매끄러운 함수)

### **Diff**
- **Objects**: Smooth manifolds (미분가능 다양체)
- **Morphisms**: Diffeomorphisms (미분동형사상)
- Man의 isomorphisms만 포함하는 subcategory

---

## 2. Abstract/Algebraic Categories^[추상적 범주]

### **Cat**
- **Objects**: Small categories (작은 범주들)
- **Morphisms**: Functors (함자)
- Category of categories!

### **Poset** (Partially ordered sets)
- **Objects**: Posets (부분순서집합)
- **Morphisms**: Order-preserving maps (순서 보존 함수)

### Monoid as a category
- **Objects**: Single object (하나의 대상)
- **Morphisms**: Monoid elements (모노이드 원소)
- Composition = monoid operation

---

## 3. Dual Categories^[쌍대 범주]

### **$\mathcal{C}^{\text{op}}$** (Opposite category)
- $\mathcal{C}$의 모든 arrow를 reverse
- $f: A \rightarrow B$ in $\mathcal{C}$ becomes $f^{\text{op}}: B \rightarrow A$ in $\mathcal{C}^{\text{op}}$

---

## 4. Product/Slice Categories^[곱 범주/슬라이스 범주]

### **$\mathcal{C} \times \mathcal{D}$** (Product category)
- **Objects**: Pairs $(A, B)$ where $A \in \mathcal{C}, B \in \mathcal{D}$
- **Morphisms**: Pairs of morphisms

### **$\mathcal{C}/A$** (Slice category over $A$)
- **Objects**: Morphisms $f: X \rightarrow A$ in $\mathcal{C}$
- **Morphisms**: Commutative triangles

---

# <span class="header-properties">Key Concepts</span>

## Universal properties^[보편 성질]

많은 수학적 구조를 category theory로 characterize:

- **Initial object**^[시작 대상]: 모든 object로 가는 unique morphism
- **Terminal object**^[끝 대상]: 모든 object에서 오는 unique morphism
- **Product**^[곱]: $A \times B$ with projections
- **Coproduct**^[쌍대곱]: $A \sqcup B$ with injections

## Isomorphism^[동형사상]

Morphism $f: A \rightarrow B$가 **isomorphism**이다 $\Leftrightarrow$ inverse $g: B \rightarrow A$가 존재:
$$g \circ f = \text{id}_A, \quad f \circ g = \text{id}_B$$

## Equivalence of categories^[범주의 동치]

$\mathcal{C} \simeq \mathcal{D}$ if there exist functors $F: \mathcal{C} \rightarrow \mathcal{D}$, $G: \mathcal{D} \rightarrow \mathcal{C}$ and natural isomorphisms:
$$G \circ F \cong \text{Id}_{\mathcal{C}}, \quad F \circ G \cong \text{Id}_{\mathcal{D}}$$

---

# <span class="header-remark">Remark</span>

## Philosophy^[철학]

Category theory는 "objects 자체"보다 "objects 사이의 관계 (morphisms)"에 초점:
- "What an object is" < "How objects relate to each other"
- Structure-preserving maps가 핵심

## "Abstract nonsense"^[추상적 무의미함]

Category theory는 때때로 이렇게 불림 (애정 어린 별명):
- 매우 추상적이고 일반적
- 하지만 수학 전반에 걸쳐 통일된 언어 제공

## Applications^[응용]

### Mathematics
- Homological algebra (호몰로지 대수)
- Algebraic topology (대수적 위상수학)
- Algebraic geometry (대수기하학)

### Computer Science
- Type theory (타입 이론)
- Functional programming (함수형 프로그래밍)
  - Haskell의 Monad는 category theory에서 유래

### Physics
- Quantum mechanics (양자역학)
- Topological quantum field theory (위상적 양자장이론)

## Subcategories^[부분범주]

Category $\mathcal{C}$의 **subcategory**^[부분범주] $\mathcal{D}$는:
- $\text{Ob}(\mathcal{D}) \subseteq \text{Ob}(\mathcal{C})$
- Morphisms도 $\mathcal{C}$의 부분집합

**Full subcategory**^[완전 부분범주]: 같은 objects 사이의 모든 morphisms 포함

예시:
- **TopHaus** ⊂ **Top** (full subcategory)
- **Homeo** ⊂ **Top** (subcategory, not full - isomorphisms만)
- **Diff** ⊂ **Man** (subcategory, not full - diffeomorphisms만)

## 관련 개념

- **Adjoint functors**^[수반 함자]: $F \dashv G$ (매우 중요한 개념)
- **Limits and colimits**^[극한과 여극한]
- **Yoneda lemma**^[요네다 보조정리]: "An object is determined by its relationships"
- **Monoidal categories**^[모노이드 범주]
- **Abelian categories**^[아벨 범주]: Homological algebra의 기초

---

# <span class="header-examples">Category Theory 계층 구조</span>

```
Level 0: Objects (대상)
    ↓ morphisms
Level 1: Category (범주)
    ↓ functors
Level 2: Functor category (함자 범주)
    ↓ natural transformations
Level 3: Natural transformation (자연 변환)
    ↓
Higher category theory (고차 범주론)
```

## 비유

**Category theory is the "mathematics of mathematics"**
- 수학의 여러 분야를 통합하는 meta-language
- "Common language" for all mathematical structures

