# 가구 에디터 (Furniture Editor)

React + TypeScript + Three.js 기반의 인터랙티브 가구 설계 애플리케이션입니다.

## 🚀 주요 기능

### 📋 단계별 설계 프로세스
- **Step 0**: 기본 정보 입력 (제목, 위치)
- **Step 1**: 공간 정보 설정 (크기, 설치 타입, 바닥 마감재, 에어컨 단내림)
- **Step 2**: 맞춤 설정 (서라운드, 받침대)

### 🎨 2D/3D 시각화
- **2D 뷰어**: SVG 기반 정확한 치수 표시
- **3D 뷰어**: Three.js 기반 실시간 3D 렌더링
- **실시간 미리보기**: 설정 변경 시 즉시 반영

### 🎛️ 중앙화된 컨트롤 시스템
- 모든 Step에서 재사용 가능한 컨트롤 컴포넌트
- 일관된 스타일링과 유효성 검사
- 타입 안전성 보장

### 💾 자동 저장
- localStorage 기반 자동 저장
- 브라우저 종료 후에도 데이터 복원

## 🛠️ 기술 스택

### 프론트엔드
- **React 18** - UI 라이브러리
- **TypeScript** - 타입 안전성
- **Vite** - 빌드 도구
- **Zustand** - 상태 관리
- **Three.js** - 3D 렌더링
- **@react-three/fiber** - React Three.js 통합
- **@react-three/drei** - Three.js 유틸리티

### 스타일링
- **CSS Modules** - 컴포넌트별 스타일링
- **반응형 디자인** - 다양한 화면 크기 지원

## 📁 프로젝트 구조

```
src/
├── components/          # 공통 컴포넌트
│   └── common/         # 버튼, 입력 필드 등
├── editor/             # 에디터 관련 컴포넌트
│   ├── Step0/          # 기본 정보 입력
│   ├── Step1/          # 공간 정보 설정
│   ├── Step2/          # 맞춤 설정
│   └── shared/         # 공유 컴포넌트
│       ├── controls/   # 중앙화된 컨트롤 시스템
│       ├── viewer/     # 2D 뷰어 (SVG)
│       └── viewer3d/   # 3D 뷰어 (Three.js)
├── store/              # 전역 상태 관리
└── utils/              # 유틸리티 함수
```

## 🚀 시작하기

### 필수 요구사항
- Node.js 18+ 
- npm 또는 yarn

### 설치 및 실행

```bash
# 저장소 클론
git clone [repository-url]
cd furniture-editor

# 의존성 설치
npm install

# 개발 서버 실행
npm run dev

# 빌드
npm run build

# 빌드 결과 미리보기
npm run preview
```

## 📖 사용법

### 1. 기본 정보 입력 (Step 0)
- 프로젝트 제목 입력
- 가구 설치 위치 선택 (안방, 작은방, 드레스룸 등)

### 2. 공간 정보 설정 (Step 1)
- **공간 크기**: 폭(1200-8000mm), 높이(1500-2500mm)
- **설치 타입**: 빌트인/세미스탠딩/프리스탠딩
- **바닥 마감재**: 유무 및 높이 설정
- **에어컨 단내림**: 위치 및 크기 설정

### 3. 맞춤 설정 (Step 2)
- **서라운드**: 프레임 유무 및 크기 설정
- **받침대**: 없음/받침대/띄움 타입 선택

### 4. 2D/3D 뷰어 활용
- **2D 모드**: 정확한 치수 확인
- **3D 모드**: 실제 설치 모습 미리보기
- **마우스 컨트롤**: 회전, 줌, 팬 기능

## 🎯 주요 특징

### 중앙화된 컨트롤 시스템
- `src/editor/shared/controls/`에서 모든 컨트롤 통합 관리
- 코드 중복 제거 및 일관된 사용자 경험
- 새로운 Step 추가 시 기존 컨트롤 재사용 가능

### 고급 3D 시각화
- **벽면별 그라데이션**: 깊이감 있는 시각 효과
- **카메라 모드 전환**: Perspective ↔ Orthographic
- **줌 제한 시스템**: 2D/3D 모드별 최적화
- **재질 메모이제이션**: 성능 최적화

### 실시간 유효성 검사
- 입력값 범위 제한 및 에러 메시지
- 동적 범위 조정 (공간 크기에 따른 제한)
- 시각적 피드백 제공

## 🔧 개발 가이드

### 새로운 컨트롤 추가
1. `src/editor/shared/controls/` 디렉토리에 컴포넌트 생성
2. 공통 스타일 `common.module.css` 활용
3. `types.ts`에 타입 정의 추가
4. `index.ts`에서 내보내기 추가

### 3D 요소 추가
1. `src/editor/shared/viewer3d/components/elements/`에 컴포넌트 생성
2. `utils/materials.ts`에 재질 정의
3. `utils/geometry.ts`에 기하학 계산 함수 추가

### 상태 관리
- Zustand store (`src/store/editorStore.ts`) 사용
- localStorage 자동 저장 활용
- 컨텍스트 API로 뷰어 상태 관리

## 📚 문서

- [컴포넌트 구조](docs/COMPONENTS_STRUCTURE.md)
- [사용자 가이드](docs/USER_GUIDE.md)
- [데이터 구조](docs/DATA_STRUCTURE.md)
- [변경 로그](docs/CHANGELOG.md)

## 🤝 기여하기

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.

## 🔮 향후 계획

- [ ] 서버 연동 및 프로젝트 저장/불러오기
- [ ] 재질 및 색상 커스터마이징 시스템
- [ ] 3D 모델 파일 내보내기 (GLTF, OBJ)
- [ ] 2D 도면 PDF 생성
- [ ] VR/AR 지원
- [ ] 애니메이션 효과
- [ ] 견적서 생성 기능

## 📞 지원

문제가 발생하거나 질문이 있으시면 [Issues](../../issues)를 통해 문의해 주세요.
