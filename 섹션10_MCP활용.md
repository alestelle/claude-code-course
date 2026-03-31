# 섹션 10. MCP 활용

> **이 섹션을 마치면**: Claude Code에 외부 서비스를 연결해서 Notion, GitHub, 데이터베이스 등을 AI로 제어할 수 있습니다.

---

## 10-1. MCP란 무엇인가?

### 한 줄 정의

> **MCP(Model Context Protocol) = Claude가 외부 서비스와 대화하는 표준 연결 방식**

### 비유로 이해하기

```
Claude Code = 스마트한 직원

기본 상태:
- 내 컴퓨터 파일만 접근 가능

MCP 연결 후:
- Notion 문서를 읽고 쓸 수 있음
- GitHub 이슈를 생성할 수 있음
- Slack 메시지를 보낼 수 있음
- 데이터베이스를 직접 조회할 수 있음

마치 직원에게 각 시스템 접근 권한을 주는 것과 같음
```

---

## 10-2. 어떤 MCP 서버가 있나?

| 카테고리 | 서비스 | 할 수 있는 것 |
|---------|--------|--------------|
| **생산성** | Notion | 페이지 읽기/쓰기, DB 조회 |
| **개발** | GitHub | 이슈/PR 생성, 코드 검색 |
| **커뮤니케이션** | Slack | 메시지 전송, 채널 검색 |
| **데이터베이스** | PostgreSQL | SQL 실행, 데이터 조회 |
| **검색** | Brave Search | 웹 검색 |
| **파일** | Google Drive | 문서 읽기/쓰기 |
| **모니터링** | Sentry | 에러 조회 |

---

## 10-3. MCP 서버 설치하기

### 설정 파일 위치

```
~/.claude/mcp.json       ← 내 모든 프로젝트에 적용
.claude/mcp.json         ← 이 프로젝트에만 적용
```

### 예시: Brave 웹 검색 연결

```json
{
  "mcpServers": {
    "brave-search": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "여기에_API_키_입력"
      }
    }
  }
}
```

### 예시: GitHub 연결

```json
{
  "mcpServers": {
    "github": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "여기에_토큰_입력"
      }
    }
  }
}
```

---

## 10-4. MCP 서버 상태 확인

```
> /mcp
```

연결된 서버 목록과 상태가 표시됩니다:

```
MCP 서버 상태:
✅ brave-search  (도구 3개 사용 가능)
✅ github        (도구 12개 사용 가능)
❌ notion        (연결 실패 - API 키 확인 필요)
```

---

## 10-5. MCP 활용 실습

### 예시 1: 웹 검색으로 최신 정보 가져오기

```
> (brave-search 연결 후)
  현재 K리그 1위 팀을 검색해서 알려줘

> 최근 나온 React 19의 새 기능을 검색해서
  이 프로젝트에 적용할 수 있는 것을 찾아줘
```

### 예시 2: GitHub 이슈 자동 생성

```
> (github 연결 후)
  현재 발견한 버그를 GitHub 이슈로 만들어줘.
  제목: "모바일에서 검색창 키보드 이슈"
  내용: 안드로이드에서 검색창 클릭 시 키보드가 화면을 가림
  라벨: bug, mobile
```

### 예시 3: Notion과 연동

```
> (notion 연결 후)
  Notion의 '프로젝트 현황' 페이지를 읽어서
  이번 주 완료해야 할 작업 목록을 알려줘

> 오늘 개발한 기능을 Notion 개발 일지 페이지에 추가해줘
```

---

## 10-6. 기획자를 위한 MCP 활용 아이디어

```
시나리오: 스포츠 검색 서비스 기획 업무에서

1. Notion 연동
   - 기획서 자동 업데이트
   - 회의록 자동 작성
   - 태스크 상태 관리

2. GitHub 연동
   - 개발 이슈 자동 생성
   - PR 상태 모니터링
   - 스프린트 진행 상황 파악

3. 웹 검색 연동
   - 경쟁 서비스 최신 동향 수집
   - 기술 문서 실시간 참조
   - 스포츠 데이터 API 조사
```

---

## 핵심 정리

```
MCP = Claude Code에게 외부 서비스 접근 권한 부여

설치: ~/.claude/mcp.json 또는 .claude/mcp.json에 설정
확인: /mcp 명령어

가장 유용한 MCP:
- brave-search: 웹 검색
- github: GitHub 제어
- notion: 노션 연동
- postgresql: DB 직접 조회
```

---

## 다음 단계

→ [섹션 11: 모던 기술스택과 개발 워크플로우](./섹션11_모던기술스택과개발워크플로우.md)
