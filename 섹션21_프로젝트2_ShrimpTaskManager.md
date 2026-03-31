# 섹션 21. [프로젝트2] Shrimp Task Manager 도입

> **이 섹션을 마치면**: AI 기반 작업 관리 도구 Shrimp을 설치하고 프로젝트에 적용할 수 있습니다.

---

## Shrimp Task Manager란?

```
Shrimp = Claude Code와 통합되는 AI 기반 작업 관리 MCP 도구

일반 Todo와의 차이:
일반 Todo: 작업 목록 나열
Shrimp:    작업을 분석하고, 의존성 파악하고,
           자동으로 단계를 나눠서 실행
```

---

## Shrimp 설치

```json
// .claude/mcp.json에 추가
{
  "mcpServers": {
    "shrimp-task-manager": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "@anthropic-ai/shrimp-task-manager"],
      "env": {
        "DATA_DIR": ".shrimp"
      }
    }
  }
}
```

---

## Shrimp 초기화

```
> Shrimp을 초기화하고 SmartQuote 프로젝트의
  남은 개발 작업들을 모두 등록해줘.
  ROADMAP.md를 참고해서 작업을 분해하고
  의존성 순서에 맞게 정렬해줘.
```

---

## Shrimp 활용 패턴

### 작업 계획 세우기

```
> Shrimp으로 "PDF 다운로드 기능" 구현을 계획해줘.
  필요한 하위 작업들을 분해하고
  각각의 예상 작업량도 평가해줘.
```

### 작업 실행

```
> Shrimp에서 다음 우선순위 작업을 실행해줘.
```

### 진행 상황 확인

```
> Shrimp에서 현재 진행 중인 작업 상태를 알려줘.
```

---

## 실습 미션

```
1. Shrimp MCP 설치

2. SmartQuote 프로젝트 작업 등록:
   > Shrimp 초기화하고 ROADMAP.md의 Phase 1 작업을 모두 등록해줘

3. 첫 번째 작업 실행:
   > Shrimp에서 "견적서 폼 완성" 작업을 시작해줘
```

---

→ [섹션 22: MVP 개발 및 배포](./섹션22_프로젝트2_MVP개발및배포.md)
