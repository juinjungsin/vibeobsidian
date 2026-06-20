# 바이브 옵시디언 강의 Workbook 작업 로그

작성일: 2026-06-11
용도: 작업 인계 / 다음 세션 이어가기 / 변경 이력 추적
표기: [확정] 사용자 승인 완료 / [제안] 설계자 판단 / [미결] 후속 검토 필요

---

## 1. 산출물 파일 구조 (NOW_바이브옵시디언/)

```
NOW_바이브옵시디언/
├─ 옵시디언_LLM_Wiki_강의_커리큘럼.md / .html   ← 강의 설계서 (8개 섹션)
├─ design.md                                  ← IBM Carbon 디자인 시스템 명세
├─ 작업로그_바이브옵시디언_Workbook.md          ← 본 문서
├─ StarterKit/                                ← 스타터킷 v1.1 (실폴더)
│   ├─ CLAUDE.md / AGENTS.md                  ← 볼트 운영 규칙 (내용 동일, 8개 절)
│   ├─ README.md                              ← 설치·온보딩 안내
│   ├─ 10_Inbox / 20_Raw / 30_Wiki(Concept·Entity·Guide·MOC) / 40_Query
│   ├─ 50_Project(51_PCD·52_Empathy_Map·53_Customer_Journey_Map) / 60_Output
│   ├─ 90_Settings/commands/ingest.md, query.md  ← 명령어 원본 (온보딩 시 AI가 .claude/commands로 복사)
│   └─ 각 폴더에 _README 안내 노트
├─ StarterKit.zip                             ← 배포용 (zip에는 .claude 미포함)
└─ workbook/                                  ← 수강생용 HTML 19개
    ├─ index.html                             ← 목차 (스타터킷·용어집 카드 연결)
    ├─ A_사전준비물 ~ H_산출물문서 (입문 8)
    ├─ I_GraphRAG ~ O_프레임워크종합 (후속 7, 순서 I→J→L→K→M→N→O)
    ├─ 용어집.html                            ← 58개 용어, 검색·카테고리 필터
    └─ 스타터킷.html                          ← 구조·규칙·설치 안내
```

---

## 2. 작업 이력 (시간순)

1. **자료 검토** — raw_data 녹취록 3건(옵2팀 6/8 1·2부, 2차 줌미팅), 김동준 박사 의견 md 2건, PDF 4건(A~O 손글씨 노트 포함) 분석
2. **커리큘럼 설계** [확정] — 김동준 박사 구조(Raw→Distill→Wiki→Query→Output)를 뼈대로, 박종빈 소장 A~O를 실행 순서로 반영. 입문(A~H)+후속(I~O) 2단계 분리, 도구 표준 코덱스+클로디안. md+화이트 HTML 생성
3. **Workbook 제작** [확정] — A~O 15개 + index, 6단 구조(목표/개념/따라하기 체크박스/막힘/퀴즈/산출물), 체크 상태 localStorage 저장
4. **용어집** [확정] — 58개 용어 6분류, 실시간 검색, 전 모듈 상단에 링크
5. **index 표기 정리** — "(2일×4시간)", "(1일 4시간)" 삭제. A 핵심개념 파트 삭제, C 구단 비유 삭제
6. **파일 처리 흐름 검토·확정** [확정] — inbox(원본 삭제) → Raw(영구 보관·출처 추적) → Wiki(N개 분할, Concept·Entity·Guide·MOC) → Query(40_Query 기록, 승격 시 위키 직접+컨펌) → Output(산출물 보관). 사용자 초안의 4개 항목 보정(Raw 임시 대기 아님, 4개 분할 아닌 N개, Query→Raw 경유 제거, Output은 노트 집결지 아님)
7. **스타터킷 v1.0 제작** [확정] — 폴더 5단계 + 규칙 파일 + /ingest·/query 이중 등록 + zip + HTML 페이지
8. **프론트매터 확장** [확정] — 7항목 → 자료연구용 15항목(기본 6 자동 + 출처 5 추출·모르면 빈칸 + 연구 메모 4 선택)
9. **디자인 변경** [확정] — design.md 저장, HTML 19개 전체를 IBM Carbon으로 교체(0px 플랫, 1px 헤어라인, IBM Plex Sans KR, 제목 300/본문 400+0.16px, IBM Blue 단일 액센트). 코드 블록은 Plex Mono [제안]
10. **B_설치 보강** — Node.js 다운로드 URL(nodejs.org/ko/download)+다운로드 페이지 모형(.msi 버튼 강조), node -v 터미널 모형, 클로드 CLI 설치 추가(@anthropic-ai/claude-code), codex·claude 실행+CLI 모드 진입 화면, obsidian.md 하이퍼링크
11. **압축 해제 위치 명료화** [확정] — 내용물을 Vault 루트(.obsidian과 같은 층)에. 이후 **방안 A 채택: .claude 배포 제거** → 00_Setup/commands로 이동, 온보딩 때 AI가 자동 복사(스타터킷 v1.1). 충돌·덮어쓰기 고민 원천 제거
12. **D_온보딩 보강** — 적용 명령 실행 화면(2단: 탐색기+Claudian), 스킬 설치 링크 확정(github.com/kepano/obsidian-skills.git), 6단계 신설: 파일 변환 스킬 프롬프트(/convert·/convert-eval, OCR eval 옵션, ingest 연동) [확정], 도구 탐지·폴백 항목 추가 + 접이식 "OCR 품질 높이기"(PATH 해결법+선택 설치) [확정], 7단계 /ingest 실행·완료(PDF 1건→위키 14개) 화면, 8단계 그래프 뷰 SVG
13. **복사 버튼** — 전체 19개 HTML의 pre 블록(25개)에 클립보드 복사 버튼
14. **E_Ingest 재구성** [확정] — 웹 클리퍼 중심으로 전환(D와 중복 제거). 클리퍼 공식 링크(obsidian.md/clipper), 설정 2원화 명료화(보관소=Vault 이름 / 템플릿 노트 위치=10_Inbox, 잘못된 입력 경고 모형), 위치 고정 원리(템플릿이 결정, 기본 템플릿 1개 유지), 클리핑 템플릿 15항목 매핑 선택 옵션({{title}}{{url}}{{author}}{{published}}{{site}}{{description}}{{date}}), 실습을 YouTube 본인이 잘 아는 영상 3건으로 변경, 8단계 완료 화면(3건→위키 15개 신규+기존 2개 누적), 9단계 선택: 대용량 책 멀티 에이전트 인제스트(클로드·코덱스 분기)
15. **F_Query 정합화** [확정 A+B] — 규칙에 자연어 트리거 추가(위키 안에서만~ → QUERY 절차, 인박스 처리해줘 → INGEST 절차), 따라하기를 /query 중심으로 통일. 가치 곡선 차트(RAG 평행 vs LLM Wiki 가속, IBM Blue 변환), /query 답변 화면, 승격 과정 화면(confirmed false→true), 그래프 뷰 Before(D)&After(F) 비교
16. **G_개념정리 구도 수정** [확정] — 3파전 → 2진영(LLM Wiki vs RAG·NotebookLM). NotebookLM=RAG 진영 대표 제품 명시. F·H·index의 제목 참조 4건 일괄 교체
17. **스타터킷 v1.1 구조 개편** [확정] (2026-06-20) — 폴더 체계 재편: `00_Setup`→`90_Settings`, `50_Output`→`60_Output`, `50_Project`(51_PCD·52_Empathy_Map·53_Customer_Journey_Map) 신설. 처리 흐름 `Wiki → Project → Output`(Query는 병행 탐색 계층). CLAUDE/AGENTS에 PROJECT 절·금지 2항(위키 직접편집·90_Settings AI수정) 추가, 프론트매터 `type`에 `project` 추가. 실패키지(StarterKit/)·배포 StarterKit.zip 교체, 교재(스타터킷·D_온보딩·F_Query)와 루트 README 동기화

---

## 3. 확정된 규칙·구조 요약

- **폴더 흐름**: 10_Inbox → 20_Raw → 30_Wiki → 50_Project → 60_Output (40_Query는 병행 탐색 계층 · 90_Settings는 명령어 원본 보관)
- **명령어**: /ingest, /query (+ 자연어 트리거 동의어 인식) — 클로드는 .claude/commands 정식 명령, 코덱스는 AGENTS.md 규칙으로 동작
- **프론트매터 15항목**: title, type, created, origin, confirmed, tags / source_type, source, author, published, publisher / summary, key_question, related, status — 모르면 빈칸(추측 금지), 질문은 1·2·3+주관식
- **핵심 운영 규칙**: 인박스까지만 내 손, Raw 수정·삭제 금지, 위키 안에서만 답변(근거 없으면 "없음"), 같은 개념은 기존 노트에 누적, 승격 시 confirmed: true
- **도구 표준**: 코덱스 + 클로디안 (클로드 코드는 선택 병기)
- **디자인**: design.md(IBM Carbon) — 0px, 1px 헤어라인, IBM Blue 단일 액센트, Plex Sans 300/400

## 4. 미결·후속 검토 항목

1. [미결] H 모듈 전제 보완 — E가 YouTube 클리핑으로 바뀌어 프레임워크 자료(PCD·MRD 링크) 수집 시점이 비어 있음. H 또는 차시 간 과제로 재배치 검토
2. [해소] StarterKit/.claude/ 빈 폴더 잔존 → v1.1 개편 시 정리 완료(현재 디스크·zip 모두 미포함)
3. [미결] 코덱스에서 /ingest·/query 자동완성 표시 — 환경별 차이 [추정], 실환경 1회 테스트 권장
4. [미결] 커리큘럼 문서(옵시디언_LLM_Wiki_강의_커리큘럼.md)의 G 모듈 표기는 "RAG vs LLM Wiki vs NotebookLM"(미팅 합의 원문) 유지 중 — Workbook과 표기 통일 여부 결정 필요
5. [미결] 후속 과정(I~O) 모듈은 요약 수준 — 개설 시 세부 확정

## 5. 다음 작업 후보

- H 모듈에 프레임워크 자료 클리핑 실습 배치 (미결 1 해소)
- G·H 모듈에 실행 화면 모형 추가 (D·E·F와 동일한 밀도로)
- 강사용 런시트(분 단위 진행표), 수강생 사전 안내문
- 후속 과정(I~O) Workbook 상세화
