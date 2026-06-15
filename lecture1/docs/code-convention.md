# 코드 컨벤션 가이드

## 파일 & 디렉토리 네이밍

- 컴포넌트 파일: `PascalCase.jsx` (예: `UserCard.jsx`)
- 훅 파일: `camelCase.js` (예: `useAuth.js`)
- 유틸 파일: `camelCase.js` (예: `formatDate.js`)
- 페이지 파일: `PascalCase.jsx` (예: `HomePage.jsx`)

```
src/
├── components/     # 재사용 컴포넌트
│   └── Button/
│       ├── index.jsx
│       └── Button.jsx
├── pages/          # 라우트 페이지
├── hooks/          # 커스텀 훅
├── utils/          # 유틸리티 함수
├── theme.js        # MUI 테마
└── main.jsx        # 진입점
```

---

## 컴포넌트 작성 규칙

### 함수형 컴포넌트 사용
```jsx
// Good
const UserCard = ({ name, email }) => {
  return (
    <Card>
      <CardContent>
        <Typography>{name}</Typography>
      </CardContent>
    </Card>
  )
}

export default UserCard
```

### Props 구조 분해
```jsx
// Good
const Button = ({ label, onClick, variant = 'contained' }) => { ... }

// Bad
const Button = (props) => { ... props.label ... }
```

---

## Import 순서

```jsx
// 1. React
import React, { useState, useEffect } from 'react'

// 2. 외부 라이브러리 (react-router, MUI 등)
import { useNavigate } from 'react-router-dom'
import { Button, Typography } from '@mui/material'
import { Home as HomeIcon } from '@mui/icons-material'

// 3. 내부 컴포넌트
import UserCard from './UserCard'

// 4. 유틸/훅
import { formatDate } from '../utils/formatDate'

// 5. 스타일/에셋
import './styles.css'
```

---

## MUI 사용 규칙

### sx prop 활용 (인라인 스타일 최소화)
```jsx
// Good - MUI sx prop
<Box sx={{ p: 2, display: 'flex', gap: 1 }}>

// Bad - 인라인 스타일
<div style={{ padding: '16px', display: 'flex', gap: '8px' }}>
```

### Grid 레이아웃
```jsx
import Grid from '@mui/material/Grid'

<Grid container spacing={2}>
  <Grid size={6}><Component /></Grid>
  <Grid size={6}><Component /></Grid>
</Grid>
```

---

## 상태 관리 규칙

- 로컬 상태: `useState`
- 사이드 이펙트: `useEffect` (의존성 배열 필수)
- 전역 상태: Context API 또는 외부 라이브러리

```jsx
// useEffect 의존성 배열 항상 명시
useEffect(() => {
  fetchData()
}, [userId]) // userId 변경 시마다 실행
```

---

## 주석 규칙

- 컴포넌트 목적은 파일명으로 표현 (주석 최소화)
- 복잡한 비즈니스 로직에만 간단 주석 추가
- TODO는 `// TODO: 설명` 형식
