# Dr. Brooks Services — Project Memory & Session History

> **운영 원칙:** 세션을 종료하거나 주요 작업을 마칠 때 항상 당일의 작업 내역, 주요 결정 사항, 배포 상태를 본 `memory.md`에 기록하고 업데이트합니다.

---

## 1. 프로젝트 개요 (Project Summary)
- **프로젝트명:** Dr. Brooks Services Hub
- **목적:** Dr. Brooks Kim이 개발한 12개 웹 애플리케이션 및 서비스를 모던하고 인터랙티브한 UI(타임라인 뷰 및 그리드 뷰)로 제공하는 포털
- **호스팅 및 인프라:**
  - **GitHub 저장소:** [`https://github.com/drbrookskim/drbrooksservices.git`](https://github.com/drbrookskim/drbrooksservices.git)
  - **Cloudflare Pages:** [https://drbrooks.pages.dev/](https://drbrooks.pages.dev/)
  - **직접 배포 CLI:** `npx wrangler pages deploy . --project-name=drbrooks`

---

## 2. 12개 서비스 목록 (최신 역순 정렬: #12 → #01)

| 순번 | ID | 서비스명 | 카테고리 | 주요 기술 스택 | 배포 URL |
|:---:|:---:|:---|:---|:---|:---|
| 1 | **#12** | **Dr. Brooks Money Report** | 산업 리포트 아카이브 | Cloudflare Pages, GitHub API, HTML Signal Viewer | [`drbrooks-moneyreport.pages.dev`](https://drbrooks-moneyreport.pages.dev/) |
| 2 | **#11** | **NOSTOS: Buy the Dip** | 전략 시뮬레이션 | Chart.js, Chart.js Zoom, FontAwesome 6 | [`drbrookskim.github.io/buythedip`](https://drbrookskim.github.io/buythedip/) |
| 3 | **#10** | **Chart Deep Dive** | 차트 기술적 분석 | Next.js 14, Turbopack, Canvas Chart | [`chartdeepdive.vercel.app`](https://chartdeepdive.vercel.app/) |
| 4 | **#09** | **NELCOME.md (SkillBoard)** | 에이전트 스킬 & 툴킷 | JSZip, Space Grotesk, Vanilla JS | [`drbrookskim.github.io/skillboard`](https://drbrookskim.github.io/skillboard/) |
| 5 | **#08** | **gitmark** | 개발자 툴 & 북마크 | PWA, Supabase JS, Tabler Icons | [`drbrookskim.github.io/gitmark`](https://drbrookskim.github.io/gitmark/) |
| 6 | **#07** | **PITL** | 기획 & 생산성 | Starbucks Design System, Marked.js | [`drbrookskim.github.io/pitl`](https://drbrookskim.github.io/pitl/) |
| 7 | **#06** | **Signnith News Finder** | AI 뉴스 & 검색 | Vite, ES Modules, AI Integration | [`drbrookskim.github.io/newsfinder`](https://drbrookskim.github.io/newsfinder/) |
| 8 | **#05** | **Dr. Brooks Thoughts** | 지식 그래프 & 아카이브 | Vis.js Network, Marked.js, Canvas Particles | [`drbrookskim.github.io/thoughts`](https://drbrookskim.github.io/thoughts/) |
| 9 | **#04** | **EquiSense** | 주식 심층 분석 | Next.js, Turbopack, Tailwind CSS | [`drbrookskim.github.io/equisense`](https://drbrookskim.github.io/equisense/) |
| 10 | **#03** | **SIGNNITH** | 시장 인텔리전스 | Supabase, Chart.js, D3.js | [`drbrookskim.github.io/signnith`](https://drbrookskim.github.io/signnith/) |
| 11 | **#02** | **오늘의 위스키** | 라이프스타일 & AI | React 18, Tailwind CSS, Lucide Icons | [`drbrookskim.github.io/todayswhisky`](https://drbrookskim.github.io/todayswhisky/) |
| 12 | **#01** | **환율 NOW** | 금융 & 통화 | JavaScript, Chart.js, PWA | [`drbrookskim.github.io/exchangenow`](https://drbrookskim.github.io/exchangenow/) |

---

## 3. 핵심 아키텍처 및 디자인 시스템
1. **타이포그래피:** 영문 `Inter`, 한글 `Noto Sans KR`, 고정폭 `JetBrains Mono`
2. **다크/라이트 듀얼 글래스모피즘 테마:**
   - **라이트 모드 (`data-theme="light"`):**
     - 배경: `#f8fafc` (깨끗한 애플 스타일 라이트 캔버스)
     - 카드: `rgba(255, 255, 255, 0.82)` (화사한 화이트 글래스)
     - 텍스트: `--text-primary: #0f172a`, `--card-text-desc: #334155` (또렷한 고대비 슬레이트)
   - **다크 모드 (`data-theme="dark"`):**
     - 배경: `#080c14` (딥 스페이스 네이비/블랙)
     - 카드: `rgba(18, 24, 38, 0.72)` (고급스러운 다크 글래스)
     - 텍스트: `--text-primary: #f8fafc` (부드럽고 선명한 화이트)
   - **카드 호버/선택 인터랙션:** 서비스 고유 시그니처 그라데이션으로 부드럽게 전환되며, 내부 텍스트 및 런치 버튼이 고대비로 자동 전환
3. **캐시 버스팅 (Cache Busting):**
   - 브라우저 및 CDN 캐시 잔류 방지를 위해 `style.css?v=...`, `app.js?v=...`, `services.json?v=...` 버전 쿼리 파라미터 적용
4. **배포 파이프라인:**
   - GitHub 저장소 푸시 + Wrangler CLI(`wrangler pages deploy`) 직접 배포를 병행하여 즉각적인 엣지 배포 보장

---

## 4. 작업 세션 히스토리 (Work Log)

### [2026-08-25] 'About Dr. Brooks Services' 버튼 연동, 타일별 앰비언트 그라데이션 & 슬로우 모션 구축
- **상단 헤더 'About Dr. Brooks Services' 버튼 추가:**
  - 상단 헤더 우측(`.header-actions`)에 알약형 글래스 버튼(`btn-about-service`)을 배치하고, 심층 분석 인터랙티브 문서(`drbrooks_pages_dev_in_depth.html`)를 `target="_blank"`로 연결.
  - 소형 모바일 뷰포트(580px 이하)에서는 아이콘 버튼으로 자동 반응형 전환되도록 CSS 최적화.
- **타일별 앰비언트 컬러 그라데이션 시스템 구축:**
  - 12개 서비스 카드 상단에 각각의 고유 그라데이션 액센트 바(`::before`) 및 12s 주기 순환 애니메이션(`cardGradientFlow`) 적용.
  - 카드 배경에 8~16% 투명도의 은은한 앰비언트 오로라 그라데이션 레이어(`::after`)를 기본 적용하여 각 타일의 고유 컬러 아이덴티티 시각화.
  - 아이콘 박스(`.card-icon-box`)에도 10초 주기로 부드럽게 흐르는 그라데이션 애니메이션 적용.
- **시네마틱 슬로우 모션(0.85s / 12~14s) 템포 튜닝:**
  - `--spring-slow: 0.85s cubic-bezier(0.16, 1, 0.3, 1)` 토큰을 정의하여 카드 호버/리셋, 그림자 확장, 타이포그래피 및 배지 색상 전환에 적용.
  - 마우스 오버 시 급격한 전환 대신 0.85초 동안 스며들듯 차오르고, 마우스 아웃 시에도 우아하고 여유롭게 복귀하도록 튜닝.
- **실제 브라우저 렌더링 검증 및 저장:**
  - Headless Chrome 렌더링 스크린샷 캡처 및 DOM/CSS 구문 무결성 검증 완료, Git 커밋/푸시 반영.

### [2026-08-21 (2차)] 브라우저 스크롤 렌더링 분석 및 원복(Rollback) 동기화
- **브라우저별 스크롤 엔진 분석:** macOS Safari(Core Animation/Metal 직결 및 네이티브 관성 물리 엔진)와 Chrome(Chromium Blink/Skia 합성 스레드) 간 백드롭 블러 및 GPU 래스터화 파이프라인 차이 심층 분석.
- **클린 롤백 및 배포:** 사용자 요청에 따라 실험적 변경 사항을 이전 안정 상태로 100% 원복(`bc6098f`)하고 GitHub 푸시 및 Cloudflare Pages 라이브 동기화 완료.

### [2026-08-21 (1차)] 서비스 역순 정렬, 다크/라이트 테마 최적화 & Wrangler 즉각 배포
- **서비스 역순 재배치:** `services.json` 및 `app.js` 내장 카탈로그를 Release #12부터 #01까지 역순 정렬하고 런타임 내림차순 정렬 로직 적용.
- **다크/라이트 테마 리팩터링:** 라이트 모드(화이트 글래스 + 고대비 다크 텍스트) 및 다크 모드(다크 글래스 + 앰비언트 글로우)의 시각적 명도 대비와 가독성 극대화.
- **캐시 버스팅 및 Wrangler 직접 배포:** `index.html`과 `app.js`에 버전 쿼리스트링(`?v=20260821_01`)을 적용하고 `npx wrangler pages deploy`를 통해 Cloudflare Pages에 즉시 반영.
- **운영 프로세스 수립:** 세션 종료 시 항상 `memory.md`를 기록하고 저장하는 세션 메모리 프로토콜 정의.

### [2026-08-20] Apple Fluid Interface & 폰트 시스템 구축
- **Apple Fluid Motion 적용:** 스프링 애니메이션(0.16, 1, 0.3, 1), 햅틱 터치 스케일링 피드백(0.96) 적용.
- **폰트 체계 확립:** 영문 Inter + 한글 Noto Sans KR + 고정폭 JetBrains Mono 폰트 스택 적용.
- **카드 타일 인터랙션 강화:** 상단 컬러바를 제거하고 마우스 호버 시 카드 전체가 시그니처 그라데이션으로 전환되는 인터랙티브 효과 구현.

### [2026-08-19] 하네스 구축 및 12개 서비스 론칭 쇼케이스
- **초기 서비스 허브 구축:** 12개 서비스 데이터 모델링(`services.json`), 타임라인/그리드 듀얼 뷰 모드 구현.
- **미니멀 UI 정제:** 불필요한 메타 텍스트 및 검색바 제거, 컨트롤 바 레이아웃 정돈.
- **인프라 연결:** GitHub 원격 저장소 및 Cloudflare Pages 최초 연동.
