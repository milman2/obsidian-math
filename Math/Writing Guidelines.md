# Math Notes Writing Guidelines

이 문서는 수학 노트 작성시 따라야 할 규칙과 가이드라인을 정리한 것입니다.

---

# Language & Terminology (언어 및 용어 규칙)

## Rule 1: 전문 용어 표기
**전문 용어는 영어를 기준으로 하고, 한글 번역은 Obsidian footnote로 작성**

### Footnote 문법
```markdown
term^[한글 번역]
```

마우스 커서를 올리면 한글 번역이 팝업으로 표시됩니다.

### Examples
- ✓ `linear mapping^[선형 사상]`
- ✓ `**kernel**^[핵]` ← footnote는 볼드 밖에
- ✗ `**kernel^[핵]**` ← 볼드 안에 footnote를 넣으면 렌더링 오류
- ✗ `선형 사상 (linear mapping)`
- ✗ `linear mapping (선형 사상)` ← 구식 방법

## Rule 2: 수식 표기
- **내적**: `\langle \cdot, \cdot \rangle`
- **집합**: `\mathbb{F}`, `\mathbb{R}`, `\mathbb{C}`, `\mathbb{N}` 등
- **중요 공식**: display math (`$$...$$`) 사용
- **인라인 수식**: `$...$` 사용
- **인라인 displaystyle**: sum, int, lim 등에 `\displaystyle` 사용
  - 예: `$\displaystyle\sum_{i=1}^{n} a_i$` → 위/아래 첨자가 시그마 위아래로 표시
  - 예: `$\displaystyle\int_0^1 f(x) \, dx$` → 적분 범위가 위아래로 표시
  - 예: `$\displaystyle\lim_{n \to \infty}$` → 극한이 아래로 표시

---

# Document Structure (문서 구조)

## 기본 템플릿

```markdown
# Prerequisite
- [[관련 개념 1]]
- [[관련 개념 2]]

# Reference

---

# Definition

[정의 내용 - 간단명료하게]

---

# Properties

### [Property 1]
[설명]

### [Property 2]
[설명]

---

# Examples

- **Example 1**: [설명]
- **Example 2**: [설명]

---

# Remark

- [비고 1]
- [비고 2]
```

## Sections 설명

| Section | 용도 | 필수 여부 |
|---------|------|-----------|
| Prerequisite | 선수 개념 링크 | 필수 |
| Reference | 참고 문헌/링크 | 필수 (비어있어도 됨) |
| Definition | 핵심 정의 | 필수 |
| Properties | 주요 성질 | 선택 |
| Proof | 증명 (sketch) | 선택 |
| Examples | 구체적 예시 | 선택 |
| Remark | 추가 설명/직관 | 권장 |

---

# Formatting Rules (서식 규칙)

## 시각적 구분
- 주요 섹션 사이: `---` (수평선) 사용
- 최상위 제목: `#`
- 하위 제목: `###` (##는 가급적 피함)

## 강조
- **볼드체**: 중요 용어, 개념 이름
- *이탤릭체*: 강조가 필요한 일반 텍스트
- 코드 블록: 알고리즘이나 프로그램 코드

## 리스트
- 순서 없는 항목: `-` 또는 `*` 사용
- 순서 있는 항목: `1.`, `2.`, ... 사용
- 중첩된 리스트: 들여쓰기 2칸

---

# Style Guide (스타일 가이드)

## DO ✓
- 간결하고 명확한 문장
- 핵심 내용 위주 정리
- 관련 노트 링크 적극 활용
- 직관적인 설명 추가 (Remark에)
- 구체적인 예시 포함

## DON'T ✗
- 장황한 설명
- 불필요한 영어 표현 (for all, such that 등은 수식에서만)
- 중복된 정보
- 증명의 과도한 디테일 (sketch만으로 충분)

---

# Quick Reference

## 자주 쓰는 LaTeX 기호

```latex
\langle x, y \rangle      # 내적
\mathbb{F}, \mathbb{R}    # 집합
\ker, \text{Im}           # 연산자
\Leftrightarrow           # 동치
\exists, \forall          # 한정사
\rightarrow, \mapsto      # 화살표
```

## 자주 쓰는 용어 (Footnote로 작성)

| 작성법 | 기호 | 비고 |
|--------|------|------|
| `kernel^[핵]` | $\ker$ | - |
| `image^[상]` | $\text{Im}$ | - |
| `injective^[단사]` | - | - |
| `surjective^[전사]` | - | - |
| `isomorphism^[동형사상]` | $\cong$ | - |
| `orthogonal^[직교]` | $\perp$ | - |
| `complement^[여공간]` | $^\perp$ | - |
| `vector space^[벡터 공간]` | - | - |
| `linear mapping^[선형 사상]` | - | - |

---

# Related
- [[Linear mapping]]
- [[Riesz Representation Theorem]]

