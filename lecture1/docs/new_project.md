# 새 프로젝트 시작 가이드

## 빠른 시작 (템플릿 복사)

```bash
# _template_settings를 새 프로젝트명으로 복사
cp -r _template_settings my-new-project
cd my-new-project

# 의존성 재설치 (node_modules는 복사 안 됨)
npm install

# 개발 서버 시작
npm run dev
```

---

## 프로젝트 초기 체크리스트

### 필수 설정
- [ ] `package.json` → `name` 필드를 새 프로젝트명으로 변경
- [ ] `index.html` → `<title>` 태그 업데이트
- [ ] `vite.config.js` → 포트 설정 확인 (기본 5173, 충돌 시 변경)
- [ ] `src/theme.js` → 프로젝트에 맞는 색상 팔레트 조정

### 디렉토리 구조 생성
```bash
mkdir -p src/components src/pages src/hooks src/utils
```

### 라우터 설정 (react-router-dom v7)
```jsx
// src/App.jsx
import { BrowserRouter, Routes, Route } from 'react-router-dom'
import HomePage from './pages/HomePage'

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<HomePage />} />
      </Routes>
    </BrowserRouter>
  )
}
```

---

## 설치된 패키지 목록

| 패키지 | 버전 | 용도 |
|--------|------|------|
| react | ^19 | UI 라이브러리 |
| react-dom | ^19 | DOM 렌더링 |
| react-router-dom | ^7 | 라우팅 |
| @mui/material | ^9 | UI 컴포넌트 |
| @mui/icons-material | ^9 | 아이콘 |
| @emotion/react | ^11 | MUI 스타일 엔진 |
| @emotion/styled | ^11 | styled 컴포넌트 |
| @fontsource/roboto | ^5 | Roboto 폰트 |
| vite | ^8 | 빌드 도구 |

---

## 폰트 적용 (main.jsx에 추가)

```jsx
import '@fontsource/roboto/300.css'
import '@fontsource/roboto/400.css'
import '@fontsource/roboto/500.css'
import '@fontsource/roboto/700.css'
```

---

## 자주 쓰는 MUI 컴포넌트 임포트

```jsx
import {
  Box, Container, Grid, Stack,
  Typography, Button, IconButton,
  Card, CardContent, CardActions,
  TextField, Select, MenuItem,
  AppBar, Toolbar, Drawer,
  Dialog, DialogTitle, DialogContent,
  Snackbar, Alert,
  CircularProgress, LinearProgress,
  List, ListItem, ListItemText, ListItemIcon,
  Divider, Chip, Avatar, Badge,
} from '@mui/material'

import {
  Menu as MenuIcon,
  Home as HomeIcon,
  Search as SearchIcon,
  Add as AddIcon,
  Delete as DeleteIcon,
  Edit as EditIcon,
  Close as CloseIcon,
} from '@mui/icons-material'
```

---

## 빌드 및 배포

```bash
# 프로덕션 빌드
npm run build

# 빌드 결과물 미리보기
npm run preview
```

빌드 결과물: `dist/` 폴더
