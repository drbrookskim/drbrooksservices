# Dr. Brooks Services Hub

## 하네스: drbrooks-services-hub

**목표:** Dr. Brooks Kim이 제작한 12개 웹 서비스를 올림차순(1번~12번)으로 전시하는 고품질 인터랙티브 서비스 쇼케이스 포털 구축 및 운영

**트리거:** 서비스 추가/수정, 정렬/카테고리 변경, UI 테마/기능 업데이트 요청 시 `service-portal-orchestrator` 스킬을 사용하라. 단순 질문은 직접 응답 가능.

**배포 엔드포인트:**
- GitHub 저장소: [`https://github.com/drbrookskim/drbrooksservices.git`](https://github.com/drbrookskim/drbrooksservices.git)
- Cloudflare Pages: [https://drbrooks.pages.dev/](https://drbrooks.pages.dev/)

**디자인 & 기술 스펙:**
- Typography: 영문 `Inter`, 한글 `Noto Sans KR`, 고정폭 `JetBrains Mono`
- Theme: 기본 **Black Glassmorphism** (`data-theme="light"` 기반 스모키 블랙 글래스), 다크모드 시 **White Glassmorphism** 지원
- Motion: Apple Fluid Interface Guidelines 기반 스프링 트랜지션 및 즉각적인 터치 피드백
- Order: 1번 환율 NOW부터 12번 Dr. Brooks Money Report까지 올림차순 정렬

**변경 이력:**
| 날짜 | 변경 내용 | 대상 | 사유 |
|------|----------|------|------|
| 2026-08-19 | 하네스 초기 구성 (3개 에이전트, 3개 스킬) 및 12개 서비스 올림차순 포털 구축 | 전체 | 프로젝트 초기화 및 12개 서비스 론칭 쇼케이스 구축 |
| 2026-08-19 | 불필요한 메타 텍스트 및 검색바 제거, 컨트롤 바 레이아웃 정돈 | `index.html`, `style.css`, `app.js` | 사용자 요청에 따른 미니멀 UI 정제 |
| 2026-08-19 | GitHub 원격 저장소(`drbrooksservices.git`) 및 Cloudflare Pages(`drbrooks.pages.dev`) 연동 | 배포 인프라 | 실시간 웹 호스팅 및 자동 동기화 구축 |
| 2026-08-20 | Apple Design & Fluid Interface System 적용, 상단 컬러바 제거 및 타일 그라데이션 전환 | `style.css`, `app.js` | 고급스러운 Apple Glassmorphism 인터랙션 강화 |
| 2026-08-20 | 영문 Inter / 한글 Noto Sans KR 폰트 적용, 디폴트 Black Glassmorphism 테마 설정 | `index.html`, `style.css`, `app.js` | 최적의 가독성 및 디자인 아이덴티티 확립 |
