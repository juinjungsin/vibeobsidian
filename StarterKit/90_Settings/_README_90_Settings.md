# 90_Settings — 시스템 설정 및 명령어 보관소

## 역할
Vault 운영에 필요한 **명령어 원본·템플릿·시스템 파일** 보관소.
온보딩 시 AI가 `commands/` 의 파일을 `.claude/commands/`로 자동 설치한다.

## 하위 구조

| 경로 | 내용 |
|---|---|
| `90_Settings/commands/ingest.md` | `/ingest` 명령어 원본 |
| `90_Settings/commands/query.md` | `/query` 명령어 원본 |
| `90_Settings/` (기타) | 템플릿·이미지·CSS snippet 등 시스템 파일 |

## 온보딩에서의 역할
사용자가 "규칙을 적용해줘"라고 하면 AI가:
1. `90_Settings/commands/` → `.claude/commands/` 복사
   (폴더 없으면 생성, 동명 파일은 이 스타터킷 버전으로 덮어씀)
2. 필수 폴더 7종 존재 확인 및 생성

## 쓰기 권한

| 주체 | 권한 |
|---|---|
| 사용자 | 읽기 + 쓰기 (템플릿 추가·관리) |
| AI (온보딩) | `commands/` 파일 읽기·복사만 허용 |
| AI (일반) | **읽기·참조만. 쓰기·삭제 절대 금지** |

## 금지
- AI는 온보딩 복사 외 상황에서 이 폴더를 수정·삭제하지 않는다
- 규칙 파일(CLAUDE.md·AGENTS.md)을 이 폴더로 이동하지 않는다
  (규칙 파일은 Vault 루트에 있어야 AI가 자동 인식함)
