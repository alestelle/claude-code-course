# 섹션 12. [프로젝트1] Starter Kit 만들기 - AI 활용

> **이 섹션을 마치면**: AI를 활용해서 새 프로젝트의 뼈대를 빠르게 만들 수 있습니다.

---

## Starter Kit이란?

```
Starter Kit = 새 프로젝트를 시작할 때 필요한 기본 구성 패키지

포함 요소:
- 폴더 구조
- 기본 설정 파일
- 공통 컴포넌트
- 개발 환경 설정
- 기본 라우팅
- 인증 구조
```

매 프로젝트마다 처음부터 만들지 않고, Starter Kit을 복제해서 시작합니다.

---

## AI로 Starter Kit 만들기

### 1단계: 요구사항 정의

```
> 스포츠 검색 웹 서비스를 위한 Starter Kit을 만들어줘.

  기술 스택:
  - Next.js 14 (App Router)
  - TypeScript
  - Tailwind CSS
  - Prisma + PostgreSQL

  포함할 것:
  - 기본 레이아웃 (헤더, 푸터, 사이드바)
  - 인증 페이지 (로그인, 회원가입)
  - 검색 페이지 기본 구조
  - API 폴더 구조
  - 환경변수 파일 (.env.example)
  - README.md

  코딩 규칙:
  - 컴포넌트는 src/components/ 폴더
  - 페이지는 src/app/ 폴더
  - API는 src/app/api/ 폴더
```

### 2단계: 생성 결과 확인

Claude Code가 생성한 파일들:

```
starter-kit/
├── src/
│   ├── app/
│   │   ├── layout.tsx       ← 전체 레이아웃
│   │   ├── page.tsx         ← 홈 페이지
│   │   ├── search/
│   │   │   └── page.tsx     ← 검색 페이지
│   │   └── api/
│   │       └── search/
│   │           └── route.ts ← 검색 API
│   ├── components/
│   │   ├── Header.tsx
│   │   ├── Footer.tsx
│   │   └── SearchBar.tsx
│   └── lib/
│       └── prisma.ts        ← DB 연결
├── prisma/
│   └── schema.prisma        ← DB 스키마
├── .env.example
├── CLAUDE.md
└── README.md
```

---

## AI 활용 프롬프트 패턴

### 패턴 1: 단계적 생성

```
# 1단계: 구조 먼저
> 폴더 구조만 먼저 만들어줘. 파일은 비워도 돼.

# 2단계: 핵심 파일 채우기
> 이제 Header 컴포넌트를 만들어줘.
  로고, 검색창, 네비게이션 메뉴 포함.

# 3단계: 기능 연결
> 검색창에서 Enter 누르면 /search 페이지로 이동하게 해줘
```

### 패턴 2: 예시 참조

```
> Naver Sports 같은 레이아웃으로 만들어줘.
  - 상단: 로고 + 검색창
  - 좌측: 스포츠 종목 선택
  - 우측: 검색 결과 목록
```

---

## 실습 미션

```bash
mkdir ~/Documents/sports-starter
cd ~/Documents/sports-starter
claude

> 스포츠 검색 서비스 Starter Kit을 만들어줘.
  Next.js 14, TypeScript, Tailwind CSS 기반으로.
  일단 기본 페이지 3개 (홈, 검색, 선수 상세)와
  공통 레이아웃만 만들어줘.
  개발 서버가 바로 실행될 수 있어야 해.
```

---

## 다음 단계

→ [섹션 13: Starter Kit 만들기 - 공식문서 활용](./섹션13_프로젝트1_StarterKit_공식문서.md)
