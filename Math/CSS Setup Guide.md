# CSS 스니펫 설정 가이드

Obsidian에서 컬러 헤더를 사용하기 위한 설정 방법입니다.

---

## 1. CSS 스니펫 활성화

1. Obsidian 설정 열기 (`Ctrl+,` 또는 `Cmd+,`)
2. **Appearance** (외관) 섹션으로 이동
3. **CSS snippets** 항목 찾기
4. `math-headers` 스니펫 옆의 토글 버튼 클릭하여 활성화
5. Obsidian 재시작 또는 설정 창 닫기

---

## 2. 적용되는 스타일

활성화 후 다음이 적용됩니다:

### 헤더 색상

| 헤더 | 색상 | 용도 |
|------|------|------|
| Prerequisite | 회색 | 선수 지식 |
| Reference | 회색 | 참고 문헌 |
| Definition | 🟢 초록색 | 정의 |
| Properties | 🔵 파란색 | 성질 |
| Proof | 🔵 파란색 | 증명 |
| Examples | 🟡 노란색 | 예시 |
| Remark | 🟣 보라색 | 비고 |
| Theorem | 🔴 빨간색 | 정리 |

### 인라인 수식 스타일
- 인라인 수식에서 `\displaystyle`을 사용하면 보기 좋게 표시됩니다
- `$\displaystyle\sum_{i=1}^n$` → 첨자가 위아래로 표시
- `$\displaystyle\int_0^1$` → 적분 범위가 위아래로 표시
- `$\displaystyle\lim_{n \to \infty}$` → 극한이 아래로 표시

---

## 3. 사용법

헤더 작성시 다음 형식을 사용하세요:

```markdown
# <span class="header-definition">Definition</span>
```

### 모든 헤더 클래스:
- `header-prerequisite`
- `header-reference`
- `header-definition`
- `header-properties`
- `header-proof`
- `header-examples`
- `header-remark`
- `header-theorem`

---

## 4. 테스트

[[Linear mapping]] 또는 [[Riesz Representation Theorem]] 노트를 열어 색상이 제대로 적용되었는지 확인하세요.

---

## 5. 문제 해결

### 색상이 보이지 않는 경우:
1. CSS 스니펫이 활성화되어 있는지 확인
2. 읽기 모드(Reading mode)로 전환해보기 (`Ctrl+E`)
3. Obsidian 재시작

### 색상이 마음에 들지 않는 경우:
`Math/.obsidian/snippets/math-headers.css` 파일을 직접 편집하여 색상 코드를 변경할 수 있습니다.

---

이 가이드는 설정 후 삭제하셔도 됩니다.

