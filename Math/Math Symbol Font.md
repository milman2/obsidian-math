# <span class="header-prerequisite">Prerequisite</span>
- LaTeX 기본 문법

# <span class="header-reference">Reference</span>
- LaTeX Mathematical Symbols Guide
- The Comprehensive LaTeX Symbol List

---

# <span class="header-definition">Definition</span>

수학에서 **폰트 스타일**은 수학적 객체의 종류나 성질을 시각적으로 구분하는 데 사용된다. 각 분야마다 관례적으로 특정 폰트를 특정 대상에 사용한다.

---

# <span class="header-examples">Examples</span>

## 1. Blackboard Bold^[칠판 굵은체]

**용도**: Number systems^[수 체계], standard sets^[표준 집합]

**LaTeX**: `\mathbb{}`

**예시**:
- $\mathbb{N}$ - Natural numbers^[자연수]: `\mathbb{N}`
- $\mathbb{Z}$ - Integers^[정수]: `\mathbb{Z}`
- $\mathbb{Q}$ - Rational numbers^[유리수]: `\mathbb{Q}`
- $\mathbb{R}$ - Real numbers^[실수]: `\mathbb{R}`
- $\mathbb{C}$ - Complex numbers^[복소수]: `\mathbb{C}`
- $\mathbb{F}$ - Field^[체]: `\mathbb{F}`
- $\mathbb{P}$ - Projective space^[사영 공간]: `\mathbb{P}`

```latex
\mathbb{R}^n, \quad \mathbb{C}^*, \quad \mathbb{F}_p
```

---

## 2. Calligraphic^[필기체]

**용도**: Sheaves^[층], categories^[범주], algebras^[대수], families of sets^[집합족]

**LaTeX**: `\mathcal{}`

**예시**:
- $\mathcal{F}$ - Sheaf^[층]: `\mathcal{F}`
- $\mathcal{O}$ - Structure sheaf^[구조층]: `\mathcal{O}`
- $\mathcal{C}$ - Category^[범주]: `\mathcal{C}`
- $\mathcal{A}$ - Algebra^[대수]: `\mathcal{A}`
- $\mathcal{B}$ - Basis^[기저]: `\mathcal{B}`
- $\mathcal{L}$ - Lagrangian^[라그랑지안]: `\mathcal{L}`
- $\mathcal{H}$ - Hamiltonian^[해밀토니안]: `\mathcal{H}`

```latex
\mathcal{F}(U), \quad \mathcal{O}_X, \quad \mathcal{C}at
```

---

## 3. Fraktur^[프락투어체] (Gothic^[고딕체])

**용도**: Ideals^[아이디얼], Lie algebras^[리 대수], cardinal numbers^[기수]

**LaTeX**: `\mathfrak{}`

**예시**:
- $\mathfrak{a}, \mathfrak{b}$ - Ideals^[아이디얼]: `\mathfrak{a}, \mathfrak{b}`
- $\mathfrak{g}$ - Lie algebra^[리 대수]: `\mathfrak{g}`
- $\mathfrak{gl}(n)$ - General linear algebra: `\mathfrak{gl}(n)`
- $\mathfrak{sl}(n)$ - Special linear algebra: `\mathfrak{sl}(n)`
- $\mathfrak{p}$ - Prime ideal^[소 아이디얼]: `\mathfrak{p}`
- $\mathfrak{m}$ - Maximal ideal^[극대 아이디얼]: `\mathfrak{m}`
- $\mathfrak{c}$ - Cardinality of continuum^[연속체의 기수]: `\mathfrak{c}`

```latex
\mathfrak{g} \to \mathfrak{h}, \quad [\mathfrak{g}, \mathfrak{g}] \subseteq \mathfrak{g}
```

---

## 4. Bold^[굵은체]

**용도**: Vectors^[벡터], matrices^[행렬], tensors^[텐서]

**LaTeX**: `\mathbf{}` (upright bold) 또는 `\boldsymbol{}` (bold italic)

**예시**:
- $\mathbf{v}, \mathbf{u}$ - Vectors^[벡터]: `\mathbf{v}, \mathbf{u}`
- $\mathbf{A}, \mathbf{B}$ - Matrices^[행렬]: `\mathbf{A}, \mathbf{B}`
- $\mathbf{x}$ - Vector variable^[벡터 변수]: `\mathbf{x}`
- $\mathbf{0}$ - Zero vector^[영벡터]: `\mathbf{0}`
- $\boldsymbol{\sigma}$ - Bold Greek: `\boldsymbol{\sigma}`

```latex
\mathbf{A}\mathbf{x} = \mathbf{b}, \quad \|\mathbf{v}\| = 1
```

**참고**: 일부 문헌에서는 벡터를 $\vec{v}$ (`\vec{v}`) 또는 $v$ (이탤릭)로 표기하기도 함

---

## 5. Script^[스크립트체]

**용도**: Power sets^[멱집합], topology^[위상], special structures^[특수 구조]

**LaTeX**: `\mathscr{}` (requires `mathrsfs` package)

**예시**:
- $\mathscr{P}(X)$ - Power set^[멱집합]: `\mathscr{P}(X)`
- $\mathscr{T}$ - Topology^[위상]: `\mathscr{T}`
- $\mathscr{F}$ - Filtration^[여과]: `\mathscr{F}`
- $\mathscr{L}$ - Linear system^[선형 시스템]: `\mathscr{L}`

```latex
\mathscr{P}(X) = \{A : A \subseteq X\}
```

**참고**: `\mathcal{}`과 비슷하지만 더 장식적임. 일부 패키지에서는 구분이 없을 수 있음

---

## 6. Roman (Upright)^[로만체]

**용도**: Operators^[연산자], functions^[함수], constants^[상수], multi-letter identifiers^[다중 문자 식별자]

**LaTeX**: `\mathrm{}` 또는 predefined operators

**예시**:
- $\sin, \cos, \tan$ - Trig functions: `\sin, \cos, \tan`
- $\log, \ln, \exp$ - Log functions: `\log, \ln, \exp`
- $\det, \dim, \ker, \deg$ - Operators: `\det, \dim, \ker, \deg`
- $\max, \min, \sup, \inf$ - Extrema: `\max, \min, \sup, \inf`
- $\mathrm{d}x$ - Differential: `\mathrm{d}x`
- $\mathrm{e}$ - Euler's number: `\mathrm{e}`
- $\mathrm{i}$ - Imaginary unit: `\mathrm{i}`

```latex
\int_0^1 f(x) \, \mathrm{d}x, \quad \mathrm{e}^{\mathrm{i}\pi} = -1
```

**Custom operators**: `\operatorname{name}`

```latex
\operatorname{tr}(A), \quad \operatorname{Hom}(V, W)
```

---

## 7. Italic^[이탤릭체] (Default)

**용도**: Variables^[변수], function names^[함수명] (single letter), default math mode

**LaTeX**: 기본 수식 모드 (별도 명령어 불필요) 또는 `\mathit{}`

**예시**:
- $x, y, z$ - Variables: `x, y, z`
- $f, g, h$ - Functions: `f, g, h`
- $\alpha, \beta, \gamma$ - Greek letters: `\alpha, \beta, \gamma`
- $A, B, C$ - Sets, constants: `A, B, C`

```latex
f(x) = ax^2 + bx + c
```

---

## 8. Sans-serif^[산세리프체]

**용도**: Categories^[범주], special mathematical objects^[특수 수학 대상]

**LaTeX**: `\mathsf{}`

**예시**:
- $\mathsf{Set}$ - Category of sets: `\mathsf{Set}`
- $\mathsf{Top}$ - Category of topological spaces: `\mathsf{Top}`
- $\mathsf{Grp}$ - Category of groups: `\mathsf{Grp}`
- $\mathsf{Vect}$ - Category of vector spaces: `\mathsf{Vect}`

```latex
\mathsf{Hom}_{\mathsf{C}}(X, Y)
```

---

## 9. Typewriter (Monospace)^[타자기체]

**용도**: Computer code, algorithms^[알고리즘]

**LaTeX**: `\mathtt{}`

**예시**:
- $\mathtt{true}, \mathtt{false}$ - Boolean values: `\mathtt{true}, \mathtt{false}`
- $\mathtt{if}, \mathtt{then}$ - Keywords: `\mathtt{if}, \mathtt{then}`

```latex
\mathtt{return} \; x + y
```

---

# <span class="header-properties">Properties</span>

### Font Mixing

여러 폰트를 혼합하여 사용할 수 있음:

```latex
\mathcal{O}_{\mathbb{P}^n}(d), \quad \mathfrak{g} \subseteq \mathfrak{gl}(n, \mathbb{R})
```

$$\mathcal{O}_{\mathbb{P}^n}(d), \quad \mathfrak{g} \subseteq \mathfrak{gl}(n, \mathbb{R})$$

### Size Independence

폰트 스타일은 수식 크기와 무관하게 적용됨:

```latex
\sum_{i \in \mathbb{N}} x_i, \quad \bigcup_{U \in \mathcal{B}} U
```

$$\sum_{i \in \mathbb{N}} x_i, \quad \bigcup_{U \in \mathcal{B}} U$$

---

# <span class="header-remark">Remark</span>

### 관례의 중요성

폰트 선택은 수학적 정확성의 일부이다. 예를 들어:
- $V$ (이탤릭) vs $\mathbf{V}$ (벡터) vs $\mathbb{V}$ (벡터 공간의 범주)
- $O$ (이탤릭, 일반 기호) vs $\mathcal{O}$ (structure sheaf) vs $\mathbb{O}$ (octonions)

### Package Requirements

일부 폰트는 특정 패키지를 필요로 함:
- `\mathbb{}`: `amsfonts` 또는 `amssymb`
- `\mathscr{}`: `mathrsfs` 패키지
- `\mathfrak{}`: `amsfonts` 또는 `amssymb`

```latex
\usepackage{amsmath, amssymb, mathrsfs}
```

### Unicode Math

최신 LaTeX (XeLaTeX, LuaLaTeX)에서는 `unicode-math` 패키지 사용 가능:

```latex
\usepackage{unicode-math}
\setmathfont{Latin Modern Math}
```

### 분야별 관례

- **Physics**^[물리학]: 벡터는 주로 bold ($\mathbf{v}$) 또는 arrow ($\vec{v}$)
- **Algebra**^[대수학]: Ideals은 fraktur ($\mathfrak{a}$), 체는 blackboard bold ($\mathbb{F}$)
- **Category Theory**^[범주론]: Categories는 calligraphic ($\mathcal{C}$) 또는 sans-serif ($\mathsf{Cat}$)
- **Analysis**^[해석학]: Function spaces는 calligraphic ($\mathcal{L}^p$), 수는 blackboard bold ($\mathbb{R}$)

### Common Conventions Summary

| Font | LaTeX | 주요 용도 | 예시 |
|------|-------|---------|------|
| Blackboard Bold | `\mathbb{}` | 수 체계, 표준 집합 | $\mathbb{R}, \mathbb{C}, \mathbb{Z}$ |
| Calligraphic | `\mathcal{}` | 층, 범주, 집합족 | $\mathcal{F}, \mathcal{O}, \mathcal{B}$ |
| Fraktur | `\mathfrak{}` | 아이디얼, 리 대수 | $\mathfrak{a}, \mathfrak{g}, \mathfrak{m}$ |
| Bold | `\mathbf{}` | 벡터, 행렬 | $\mathbf{v}, \mathbf{A}, \mathbf{x}$ |
| Roman | `\mathrm{}` | 연산자, 상수 | $\mathrm{d}x, \sin, \ker$ |
| Italic | (default) | 변수, 함수 | $x, f, \alpha$ |
| Sans-serif | `\mathsf{}` | 범주 | $\mathsf{Set}, \mathsf{Top}$ |
| Script | `\mathscr{}` | 멱집합, 위상 | $\mathscr{P}(X), \mathscr{T}$ |

