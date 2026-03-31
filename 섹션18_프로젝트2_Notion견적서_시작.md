# 섹션 18. [프로젝트2] Notion 기반 온라인 견적서 - 시작하기

> **이 섹션을 마치면**: Notion API를 연동한 실제 서비스의 기획과 초기 설정을 완료합니다.

---

## 프로젝트 개요

### 무엇을 만드는가?

```
Notion 데이터베이스를 백엔드로 활용한
온라인 견적서 생성 서비스

사용자가 웹에서 견적을 작성하면
→ Notion DB에 자동 저장
→ PDF로 다운로드 가능
→ 관리자는 Notion에서 모든 견적 관리
```

### 이 프로젝트를 배우는 이유

```
배울 수 있는 것:
✅ 외부 API(Notion) 연동 방법
✅ 폼 데이터 처리 및 저장
✅ PDF 생성
✅ Notion MCP 활용
✅ 실무에서 바로 쓸 수 있는 패턴
```

---

## 기획 단계: PRD 작성

```
> /prd 명령어 활용:

> /prd
  다음 아이디어로 PRD를 작성해줘:
  서비스명: SmartQuote
  개념: Notion 데이터베이스를 활용한 온라인 견적서 서비스
  타겟: 프리랜서, 소규모 에이전시, 1인 기업
  핵심 기능:
  - 웹에서 견적서 작성
  - Notion에 자동 저장
  - PDF 다운로드
  - 관리자 대시보드 (Notion)
```

---

## Notion API 설정

### 1. Notion Integration 만들기

```
1. notion.so/my-integrations 접속
2. "New Integration" 클릭
3. 이름: SmartQuote
4. API Key 복사 → .env에 저장
```

### 2. Notion 데이터베이스 만들기

```
Notion에서 새 페이지 → 데이터베이스 생성

견적서 DB 컬럼:
- 제목 (Title)
- 고객명 (Text)
- 이메일 (Email)
- 금액 (Number)
- 상태 (Select: 대기/확인/완료/거절)
- 생성일 (Date)
- 품목 (Text/JSON)
```

### 3. Notion MCP 설정

```json
// .claude/mcp.json
{
  "mcpServers": {
    "notion": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "@notionhq/notion-mcp-server"],
      "env": {
        "NOTION_API_KEY": "${NOTION_API_KEY}"
      }
    }
  }
}
```

---

## 프로젝트 초기 설정

```bash
mkdir ~/Documents/smart-quote
cd ~/Documents/smart-quote
claude
```

```
> SmartQuote 프로젝트를 시작해줘.

  기술 스택:
  - Next.js 14, TypeScript, Tailwind CSS
  - Notion API (공식 SDK)
  - react-pdf (PDF 생성)

  첫 번째로 만들 것:
  1. 프로젝트 기본 구조
  2. Notion API 연결 설정
  3. 견적서 작성 폼 (기본 버전)
  4. CLAUDE.md 작성

  .env.example도 만들어줘.
```

---

## 실습 미션

```
1. Notion Integration 생성 및 API 키 발급

2. 견적서 데이터베이스 Notion에 생성

3. Claude Code로 프로젝트 초기화:
   > SmartQuote 프로젝트 설정해줘.
     Notion DB ID: [복사한 ID]
     견적서 폼의 필드: 고객명, 이메일, 서비스항목, 단가, 수량

4. 개발 서버 실행 후 폼 확인:
   npm run dev → localhost:3000 접속
```

---

→ [섹션 19: 작업 관리 도구](./섹션19_작업관리도구.md)
