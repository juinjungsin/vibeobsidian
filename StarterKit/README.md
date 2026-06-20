# 바이브 옵시디언 스타터킷 v1.1

옵시디언 + 클로디안(코덱스/클로드) 환경에서 LLM Wiki를 시작하는 표준 패키지입니다.

## 폴더 구조

```
Vault/
├── CLAUDE.md / AGENTS.md / README.md   ← 규칙·안내 (Vault 루트 필수)
├── 10_Inbox/        ← 사용자가 파일을 넣는 유일한 폴더
├── 20_Raw/          ← 메타데이터 장착 원본 (영구 보관, 수정 금지)
├── 30_Wiki/         ← AI 자동 생성 지식 베이스 (사용자 직접 편집 금지)
│   ├── Concept/
│   ├── Entity/
│   ├── Guide/
│   └── MOC/
├── 40_Query/        ← /query 질문·답변 임시 기록
├── 50_Project/      ← Wiki 기반 작업 공간 (사용자 검토·수정 가능)
│   ├── 51_PCD/
│   ├── 52_Empathy_Map/
│   └── 53_Customer_Journey_Map/
├── 60_Output/       ← 최종 완성 산출물만 저장
└── 90_Settings/     ← 명령어 원본·시스템 파일 (AI 쓰기 금지)
    └── commands/
        ├── ingest.md
        └── query.md
```

처리 흐름: **Inbox → Raw → Wiki → Project → Output**
Query는 흐름과 병행하는 탐색 지원 계층.

## 설치 (2단계)

1. 이 폴더 **안의 내용물 전체**를 Vault 루트(`.obsidian` 폴더와 같은 층)에 붙여넣는다.

2. 클로드(또는 코덱스)에게 입력한다:
   「CLAUDE.md의 규칙을 읽고 이 Vault에 적용해줘」
   → AI가 `90_Settings/commands/` → `.claude/commands/` 자동 설치 + 폴더 확인까지 수행.

3. 테스트: `10_Inbox`에 파일 1개를 넣고 `/ingest` 입력. 위키 노트가 생성되면 완료.

## 사용 규칙 요약

- 파일 입력: `10_Inbox`만
- Wiki(`30_Wiki`): AI 전용, 사용자 직접 편집 금지
- Project(`50_Project`): 사용자 자유롭게 검토·수정 가능
- Settings(`90_Settings`): 사용자 전용, AI 읽기만 허용
