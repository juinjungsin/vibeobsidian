# 바이브 옵시디언 스타터킷 v1.1

옵시디언 + 클로디안(코덱스/클로드) 환경에서 LLM Wiki를 시작하는 표준 패키지입니다.

## 구성

- 폴더 구조 5단계: `10_Inbox → 20_Raw → 30_Wiki → 40_Query → 50_Output`
- 폴더 간 규칙: `CLAUDE.md`(클로드용) / `AGENTS.md`(코덱스용) — 내용 동일
- 자체 명령어 2종: `/ingest`, `/query` — 원본은 `00_Setup/commands/`에 있고, 온보딩 때 AI가 자동 설치합니다

## 설치 (3단계 — 숨김 폴더를 만질 필요 없습니다)

1. 압축을 풀면 생기는 StarterKit 폴더 **안의 내용물 전체**를
   내 Vault 루트(`.obsidian` 폴더와 같은 층)에 붙여넣습니다.
   - 같은 이름의 폴더가 없으므로 충돌·덮어쓰기 고민이 없습니다.
   - StarterKit 폴더째 넣으면 규칙이 인식되지 않으니 내용물만 넣으세요.

   ```
   내Vault폴더/
   ├─ .obsidian/  .claudian/  .claude/   ← 자동 생성 (신경 쓸 필요 없음)
   ├─ CLAUDE.md  AGENTS.md  README.md
   ├─ 00_Setup/commands/                 ← 명령어 원본 (AI가 자동 설치)
   └─ 10_Inbox/ 20_Raw/ 30_Wiki/ 40_Query/ 50_Output/
   ```

2. 옵시디언에서 클로디안을 열고 입력합니다:
   「CLAUDE.md(또는 AGENTS.md)의 규칙을 읽고 이 Vault에 적용해줘」
   → AI가 명령어 설치(.claude/commands 복사)와 폴더 확인까지 자동으로 수행합니다.

3. 테스트: `10_Inbox` 에 파일 1개를 넣고 `/ingest` 를 입력합니다.
   위키 노트가 생성되면 설치 완료입니다.

## 사용 규칙 한 줄 요약

파일을 넣는 것은 `10_Inbox` 까지만 내 손으로, 나머지는 전부 명령으로.
