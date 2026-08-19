---
name: service-portal-orchestrator
description: Dr. Brooks Kim 서비스 허브 포털의 전체 생명주기(메타데이터 큐레이션, UI 구축, 올림차순 정렬 검증, QA 및 유지보수)를 총괄 조율하는 오케스트레이터 스킬. 서비스 추가, 재정렬, UI 업데이트, 리포트 재실행 요청 시 반드시 이 스킬을 사용할 것.
---

# Service Portal Orchestrator Skill

## 목적
`drbrooks-services` 포털의 전체 워크플로우를 관장하며, `service-curator`, `frontend-architect`, `qa-verifier` 3인 에이전트 팀의 협업을 조율하여 고품질의 서비스 게시 웹사이트를 생성 및 유지보수한다.

## 팀 구성 및 역할 분담
- **`service-curator`**: 12개 서비스 메타데이터 수집, 스키마 검증, 올림차순 번호 매김, 카테고리 태깅
- **`frontend-architect`**: 반응형 웹 UI, 타임라인/그리드 뷰, 검색/필터, 다크모드, 모달, 애니메이션 구현
- **`qa-verifier`**: 12개 링크 검증, 접근성, 반응형 렌더링, 콘솔 에러 전수 테스트

## 단계별 워크플로우 (Orchestration Phases)

### Phase 0: 컨텍스트 및 변경 요청 확인
1. 기존 `services.json` 및 `_workspace/` 산출물 유무 확인
2. 신규 빌드인지, 서비스 추가인지, 디자인 변경인지 분기 판단

### Phase 1: 메타데이터 큐레이션 (`service-curator`)
- **실행 모드**: 에이전트 팀 (`SendMessage` 및 `_workspace/01_curated_services.json` 파일 기반 전달)
- 12개 서비스의 URL, 제목, 설명, 태그, 테마 컬러, 올림차순 번호(1~12) 정제
- 산출물: `_workspace/01_curated_services.json` 및 `services.json`

### Phase 2: 프론트엔드 아키텍처 및 구현 (`frontend-architect`)
- **실행 모드**: 에이전트 팀
- `_workspace/01_curated_services.json`을 소비하여 `index.html`, `style.css`, `app.js` 생성/업데이트
- 1번(`exchangenow`)부터 12번(`moneyreport`)까지 올림차순 정렬된 뷰 렌더링
- 올림차순 타임라인(Journey Timeline) + 직관적인 카드 그리드(Card Grid) 듀얼 뷰 제공
- 실시간 키워드 검색, 카테고리 필터, 통계 카운터, 다크/라이트 테마 토글, 상세 모달 구현

### Phase 3: 품질 보증 및 무결성 감사 (`qa-verifier`)
- **실행 모드**: 에이전트 팀
- 12개 링크의 유효성 검증
- 1번 시작 올림차순 정렬 상태 검증
- 모바일/데스크톱 뷰포트 및 테마 스위칭 동작 확인
- 산출물: `_workspace/02_qa_verification_report.md`

### Phase 4: 최종 보고 및 피드백 수집
- 사용자에게 완성된 포털의 구조 및 기능 요약 보고
- 지속적 진화를 위한 피드백 옵션 제공

## 테스트 시나리오
- **정상 흐름**: 1번부터 12번까지 순서대로 나열되며 타임라인 뷰와 그리드 뷰 간 전환이 매끄럽고, 각 카드의 바로가기 링크를 클릭하면 새 탭에서 해당 서비스가 올바르게 열린다.
- **에러 흐름**: 외부 사이트의 임베드 차단 시 프리뷰 모달이 안전하게 새 창 열기 버튼으로 유도하고 친절한 안내를 표시한다.
