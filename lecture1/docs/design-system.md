# 디자인 시스템 가이드

## 색상 팔레트 (MUI 기반)

### Primary Colors
- `primary.main`: `#1976d2` (Blue 700)
- `primary.light`: `#42a5f5` (Blue 400)
- `primary.dark`: `#1565c0` (Blue 800)

### Secondary Colors
- `secondary.main`: `#dc004e` (Pink A400)
- `secondary.light`: `#ff4081`
- `secondary.dark`: `#9a0036`

### Neutral Colors
- `background.default`: `#ffffff`
- `background.paper`: `#f5f5f5`
- `text.primary`: `rgba(0,0,0,0.87)`
- `text.secondary`: `rgba(0,0,0,0.6)`

---

## 타이포그래피

| 변형 | 크기 | 굵기 | 용도 |
|------|------|------|------|
| h1 | 2.125rem | 500 | 페이지 제목 |
| h2 | 1.5rem | 500 | 섹션 제목 |
| h3 | 1.25rem | 500 | 카드 제목 |
| body1 | 1rem | 400 | 본문 텍스트 |
| body2 | 0.875rem | 400 | 보조 텍스트 |
| caption | 0.75rem | 400 | 캡션/레이블 |

폰트: `Roboto, Helvetica, Arial, sans-serif`

---

## 간격 시스템 (spacing)

기본 단위: `8px` (MUI 기본값)

- `spacing(1)` = 8px
- `spacing(2)` = 16px
- `spacing(3)` = 24px
- `spacing(4)` = 32px

---

## 컴포넌트 규칙

### Button
- 기본: `variant="contained"` + `color="primary"`
- 취소/보조: `variant="outlined"`
- 위험 액션: `color="error"`

### Card
- `elevation={2}` 기본
- padding: `spacing(2)` 내부

### 아이콘
- `@mui/icons-material` 패키지 사용
- 크기: `fontSize="medium"` (기본)

---

## 반응형 브레이크포인트

| 이름 | 값 | 용도 |
|------|----|------|
| xs | 0px | 모바일 |
| sm | 600px | 태블릿 세로 |
| md | 900px | 태블릿 가로 |
| lg | 1200px | 데스크탑 |
| xl | 1536px | 와이드 |
