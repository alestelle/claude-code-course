# 섹션 5. Cursor AI IDE 통합

> **이 섹션을 마치면**: Cursor 에디터를 설치하고 Claude Code와 함께 사용하는 환경을 갖춥니다.

---

## 5-1. IDE란 무엇인가

### 기획자 언어로 설명

```
IDE (Integrated Development Environment) = 통합 개발 환경

비유: 워드프로세서 vs 메모장

메모장 = 그냥 텍스트 파일 편집
워드    = 맞춤법 검사, 서식, 목차, 미리보기 등 통합

마찬가지로:
메모장 = 코드 파일 그냥 열기
IDE    = 코드 자동 완성, 오류 표시, 파일 탐색기,
         터미널 내장, AI 지원 등 통합
```

### 왜 Cursor인가?

- VS Code 기반 (세계에서 가장 많이 쓰는 에디터)
- **AI 기능이 기본 내장** (Claude, GPT 등 지원)
- Claude Code와 함께 쓰면 강력한 시너지
- 무료 플랜 제공

---

## 5-2. Cursor 설치

### 다운로드 및 설치

```
1. cursor.com 접속
2. "Download for Mac" 클릭
3. 다운로드된 .dmg 파일 실행
4. Applications 폴더로 드래그
5. Cursor 실행
```

### 첫 실행 설정

```
1. "Sign Up" 또는 "Log In" 선택
2. 테마 선택 (어두운 테마 권장)
3. VS Code 설정 가져올지 묻는 경우 → Skip (처음이면)
```

---

## 5-3. Cursor 기본 사용법

### 화면 구성

```
┌─────────────────────────────────────────┐
│  [파일 탐색기]  │  [코드 편집 영역]       │
│                 │                         │
│  📁 my-project  │  index.html             │
│   ├ index.html  │  ─────────────────────  │
│   ├ style.css   │  <html>                 │
│   └ script.js   │    <head>...</head>     │
│                 │    <body>...</body>     │
│                 │  </html>               │
├─────────────────────────────────────────┤
│  [내장 터미널]                            │
│  user@MacBook ~/my-project %             │
└─────────────────────────────────────────┘
```

### 핵심 단축키

| 단축키 | 기능 |
|--------|------|
| `Cmd + P` | 파일 빠른 열기 |
| `Cmd + Shift + P` | 명령 팔레트 |
| `` Cmd + ` `` | 내장 터미널 열기/닫기 |
| `Cmd + /` | 주석 토글 |
| `Cmd + Z` | 실행 취소 |
| `Ctrl + K` | AI 인라인 편집 |
| `Cmd + L` | AI 채팅 열기 |

---

## 5-4. Cursor와 Claude Code 함께 사용하기

### 이상적인 작업 흐름

```
Cursor (시각적 편집 + 파일 확인)
    +
터미널에서 Claude Code (자동화 + 복잡한 작업)
    =
최강의 AI 개발 환경
```

### 실제 사용 패턴

**패턴 1: Claude Code로 생성 → Cursor로 확인**
```
1. 터미널에서: claude
   > "로그인 페이지 만들어줘"
2. Claude Code가 파일 생성
3. Cursor에서 생성된 파일 확인 및 세부 수정
```

**패턴 2: Cursor에서 파일 선택 → Claude Code에 넘기기**
```
1. Cursor에서 수정할 파일 파악
2. 터미널로 전환
3. claude
   > "login.html 파일에서 버튼 색상을 파란색으로 바꿔줘"
```

---

## 5-5. Cursor 내장 AI 기능

### 인라인 편집 (Ctrl + K)

코드를 선택한 후 `Ctrl+K`를 누르면 AI에게 수정 요청 가능:

```
[코드 선택 후 Ctrl+K]
> 이 버튼에 hover 효과 추가해줘
```

### AI 채팅 (Cmd + L)

파일을 참조하며 대화 가능:

```
[Cmd+L로 채팅 열기]
> @index.html 이 파일의 구조를 설명해줘
> @style.css 반응형 스타일을 추가하려면?
```

---

## 5-6. Cursor 터미널에서 Claude Code 실행

Cursor 안에서 터미널을 열고 Claude Code를 바로 실행할 수 있습니다:

```bash
# Cursor 내장 터미널 열기
Cmd + `  (백틱)

# Claude Code 실행
claude
```

이렇게 하면 한 화면 안에서:
- 왼쪽: 파일 탐색기
- 가운데: 코드 미리보기
- 아래: Claude Code 대화

---

## 5-7. 실습 미션

### 미션: Cursor + Claude Code로 간단한 랜딩 페이지 만들기

```bash
# 1. 새 프로젝트 폴더 생성
mkdir ~/Documents/landing-page
cd ~/Documents/landing-page

# 2. Cursor에서 폴더 열기
# Cursor → File → Open Folder → landing-page 선택

# 3. 내장 터미널에서 Claude Code 실행
claude

# 4. 요청하기
> 스포츠 정보 검색 서비스의 랜딩 페이지를 만들어줘.
  주요 기능: 선수 검색, 경기 일정, 팀 순위
  디자인: 깔끔하고 현대적, 주색상 짙은 남색
  파일: index.html, style.css 분리해서
```

---

## 핵심 정리

```
Cursor = 시각적인 코드 편집 + AI 보조
Claude Code = 자율적인 코딩 에이전트

두 가지를 함께 쓰는 것이 가장 효율적:
- Claude Code로 큰 작업 처리
- Cursor로 세부 확인 및 수정
```

---

## 다음 단계

→ [섹션 6: 클로드 코드 권한](./섹션06_클로드코드권한.md)
