# 섹션 8. Git과 Github

> **이 섹션을 마치면**: 코드를 안전하게 저장하고, GitHub에 올리고, 이전 버전으로 되돌릴 수 있습니다.

---

## 8-1. Git과 GitHub의 차이

```
Git    = 내 컴퓨터에서 변경 이력을 관리하는 도구
GitHub = Git 저장소를 인터넷에 저장하는 서비스

비유:
Git    = 문서 변경 이력 자동 저장 기능 (로컬)
GitHub = 그 문서를 클라우드에 백업하는 서비스
```

---

## 8-2. Git 핵심 개념 3가지

### 1. 저장소 (Repository = Repo)
```
프로젝트 폴더 + Git 이력 관리 = 저장소

git init   ← 일반 폴더를 Git 저장소로 만들기
```

### 2. 커밋 (Commit)
```
"지금 이 상태를 저장해줘"

기획 문서로 비유:
v1 커밋: "로그인 페이지 초안 완성"
v2 커밋: "검색 기능 추가"
v3 커밋: "모바일 반응형 적용"

언제든 v1, v2, v3로 돌아갈 수 있음
```

### 3. 브랜치 (Branch)
```
메인 작업물을 건드리지 않고 '복사본'에서 실험하는 기능

메인 브랜치 (main)     ← 실제 서비스 코드
  ├── feature/login    ← 로그인 기능 개발 중
  └── feature/search   ← 검색 기능 개발 중

완성되면 메인에 합칩니다 (merge)
```

---

## 8-3. Git 기본 워크플로우

```
[작업 흐름]

1. 파일 수정
       ↓
2. git add .        (스테이징: "이 변경을 저장 목록에 추가")
       ↓
3. git commit -m "설명"   (커밋: "지금 상태 저장")
       ↓
4. git push         (GitHub에 올리기)
```

### 실제 명령어

```bash
# 현재 상태 확인 (가장 많이 씀)
git status

# 변경된 파일 스테이징
git add .                  # 모든 변경 파일
git add index.html         # 특정 파일만

# 커밋 (변경 이력 저장)
git commit -m "로그인 페이지 초안 완성"

# GitHub에 올리기
git push

# GitHub에서 받아오기
git pull
```

---

## 8-4. GitHub 계정 설정

### GitHub 계정 만들기

```
1. github.com 접속
2. "Sign Up" 클릭
3. 이메일, 비밀번호, 사용자명 입력
4. 이메일 인증
```

### SSH 키 설정 (최초 1회)

비밀번호 없이 GitHub에 접근하는 방법:

```bash
# SSH 키 생성
ssh-keygen -t ed25519 -C "your@email.com"
# Enter 3번 (기본값 사용)

# 공개 키 확인
cat ~/.ssh/id_ed25519.pub

# 출력된 내용을 복사해서:
# GitHub → Settings → SSH keys → New SSH key에 붙여넣기
```

---

## 8-5. 새 프로젝트를 GitHub에 올리기

```bash
# 1. 로컬 저장소 초기화
git init

# 2. 첫 번째 커밋
git add .
git commit -m "프로젝트 초기 설정"

# 3. GitHub에서 새 저장소 만들기
# github.com → New Repository → 이름 입력 → Create

# 4. 원격 저장소 연결
git remote add origin git@github.com:사용자명/저장소명.git

# 5. 업로드
git push -u origin main
```

---

## 8-6. Claude Code와 Git 함께 사용하기

Claude Code는 Git을 자동으로 활용합니다:

```
> 로그인 기능을 추가하고, Git에 커밋해줘
```

Claude Code가 자동으로:
1. 로그인 기능 코드 작성
2. `git add` 실행
3. 의미 있는 커밋 메시지로 `git commit`

### Claude Code에서 자주 쓰는 Git 요청

```
> 현재 변경사항을 Git에 커밋해줘
> 새 브랜치 "feature/search"를 만들고 전환해줘
> main 브랜치와 현재 브랜치의 차이를 보여줘
> 마지막 커밋을 취소해줘 (코드는 유지하고)
> GitHub에 push해줘
```

---

## 8-7. 자주 쓰는 Git 명령어 정리

```bash
# 상태 확인
git status          # 변경된 파일 목록
git log --oneline   # 커밋 이력 한 줄씩

# 브랜치 관리
git branch          # 브랜치 목록
git branch 이름     # 새 브랜치 생성
git checkout 이름   # 브랜치 전환
git checkout -b 이름 # 생성+전환 동시에

# 되돌리기
git restore 파일명  # 마지막 커밋 상태로 파일 복원
git revert HEAD     # 마지막 커밋 취소 (이력 유지)

# GitHub 연동
git clone 주소      # 저장소 복제
git pull            # 최신 내용 가져오기
git push            # 내용 올리기
```

---

## 8-8. 실습 미션

```bash
# 1. 실습 폴더로 이동
cd ~/Documents/claude-practice

# 2. Git 저장소 초기화
git init

# 3. Claude Code 실행
claude

# 4. 다음을 요청
> index.html 파일을 만들고, 커밋해줘.
  커밋 메시지는 "feat: 프로젝트 초기 파일 추가"로 해줘

# 5. 이력 확인
git log --oneline
```

---

## 핵심 정리

```
Git 3단계 워크플로우:
수정 → git add . → git commit -m "설명" → git push

브랜치: 실험용 복사본 만들기
GitHub: 인터넷 백업 + 협업 공간

Claude Code는 Git 명령을 자동으로 실행해줍니다.
직접 명령어를 치지 않아도 됩니다.
```

---

## 다음 단계

→ [섹션 9: 설정 파일과 메모리 관리](./섹션09_설정파일과메모리관리.md)
