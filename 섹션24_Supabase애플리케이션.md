# 섹션 24. Supabase 애플리케이션 시작하기

> **이 섹션을 마치면**: Supabase로 인증, 데이터베이스, 실시간 기능을 갖춘 풀스택 앱의 기반을 만들 수 있습니다.

---

## Supabase란?

```
Supabase = 오픈소스 Firebase 대안
         = "백엔드를 코드 없이 만들어주는 서비스"

포함된 것:
✅ PostgreSQL 데이터베이스
✅ 인증 (이메일, 소셜 로그인)
✅ 파일 스토리지
✅ 실시간 구독
✅ Edge Functions (서버리스)
✅ RESTful & GraphQL API 자동 생성
```

### 기획자에게 왜 좋은가?

```
기존 방식:
서버 코드 작성 → DB 설계 → API 만들기 → 인증 구현
= 혼자 개발 시 몇 주 소요

Supabase + Claude Code:
Supabase 설정 + Claude Code 연동
= 몇 시간 만에 가능
```

---

## Supabase 계정 설정

```
1. supabase.com 접속
2. GitHub으로 로그인
3. "New Project" 클릭
4. 프로젝트명, DB 비밀번호, 리전(Northeast Asia) 설정
5. 생성 완료까지 약 2분 대기
```

---

## Supabase 핵심 개념

### 테이블 에디터

```
Notion 표처럼 생긴 DB 관리 UI
→ 테이블 생성, 컬럼 추가, 데이터 직접 입력 가능
```

### Row Level Security (RLS)

```
누가 어떤 데이터에 접근할 수 있는지 규칙 설정
예: "자기 데이터만 볼 수 있음"
```

### Realtime

```
DB 변경사항을 실시간으로 프론트엔드에 전달
예: 채팅, 라이브 대시보드
```

---

## Claude Code로 Supabase 연동

### 프로젝트 초기화

```bash
mkdir ~/Documents/supabase-app
cd ~/Documents/supabase-app
claude
```

```
> Next.js + Supabase 프로젝트를 시작해줘.

  Supabase 프로젝트 정보:
  - URL: [Supabase 대시보드에서 복사]
  - Anon Key: [Supabase 대시보드에서 복사]

  설정할 것:
  1. @supabase/supabase-js 설치
  2. Supabase 클라이언트 설정
  3. 인증 (이메일/비밀번호 + Google)
  4. 로그인/회원가입 페이지
  5. 인증된 사용자만 접근 가능한 보호 라우트
```

### 데이터베이스 테이블 생성

```
> Supabase에 다음 테이블을 생성하는 SQL을 작성해줘:
  (Supabase SQL Editor에서 실행할 것)

  users_profile 테이블:
  - id (UUID, FK to auth.users)
  - username (text, unique)
  - avatar_url (text)
  - created_at (timestamp)

  RLS 정책도 추가해줘:
  - 자기 프로필만 수정 가능
  - 모든 사용자 프로필은 조회 가능
```

---

## 실시간 기능 구현

```
> 이벤트 관리 앱을 위해 Supabase Realtime을 설정해줘.
  이벤트 테이블의 변경사항이 실시간으로
  화면에 반영되도록 해줘.
```

---

## 파일 업로드

```
> Supabase Storage를 사용해서
  이벤트 썸네일 이미지를 업로드하는 기능을 만들어줘.
  버킷 이름: 'event-images'
  파일 크기 제한: 5MB
  허용 형식: jpg, png, webp
```

---

## 실습 미션

```
> Supabase 앱을 완성해줘:

  1. Supabase 연동 설정
  2. 이메일 로그인/회원가입 구현
  3. 로그인 후 대시보드 페이지 (사용자 정보 표시)
  4. 로그아웃 기능
  5. Vercel 배포

  모든 API 키는 .env에 관리해줘.
```

---

→ [섹션 25: 이벤트 관리 앱 - 시작하기](./섹션25_프로젝트3_이벤트관리앱_시작.md)
