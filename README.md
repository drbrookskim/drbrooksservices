# Dr. Brooks Services

Dr. Brooks Kim의 12개 인터랙티브 웹 애플리케이션 및 서비스 허브 포털입니다.

## 12개 서비스 목록 (최신 역순 정렬)

1. **[Dr. Brooks Money Report](https://drbrooks-moneyreport.pages.dev/)** (#12) — 산업 핵심 시그널 & 밸류체인 심층 분석 리포트 아카이브
2. **[NOSTOS: Buy the Dip](https://drbrookskim.github.io/buythedip/)** (#11) — 눌림목 매수 & 다각적 매도 전략 AI 백테스팅 시뮬레이터
3. **[Chart Deep Dive](https://chartdeepdive.vercel.app/)** (#10) — 종목 캔들 차트 기반 지표 · 패턴 · 고급 기법 심층 분석 엔진
4. **[NELCOME.md (SkillBoard)](https://drbrookskim.github.io/skillboard/)** (#09) — AI 에이전트 스킬 & 프롬프트 커스터마이징 툴킷 대시보드
5. **[gitmark](https://drbrookskim.github.io/gitmark/)** (#08) — GitHub 기반 지능형 북마크 & 아카이브 피드 PWA
6. **[PITL](https://drbrookskim.github.io/pitl/)** (#07) — Starbucks Design System 기반 자율 제품 기획 워크스페이스
7. **[Signnith News Finder](https://drbrookskim.github.io/newsfinder/)** (#06) — On-Demand AI 실시간 금융/산업 뉴스 브리핑 검색 엔진
8. **[Dr. Brooks Thoughts](https://drbrookskim.github.io/thoughts/)** (#05) — 브런치 연동 지식 네트워크 그래프 & 생각 아카이브
9. **[EquiSense](https://drbrookskim.github.io/equisense/)** (#04) — 펀더멘털 · 해자 · 정성적 · 기술적 4단계 주식 심층 분석 플랫폼
10. **[SIGNNITH](https://drbrookskim.github.io/signnith/)** (#03) — 실시간 주식 시장 시그널 & 수급 인텔리전스 대시보드
11. **[오늘의 위스키](https://drbrookskim.github.io/todayswhisky/)** (#02) — MBTI & 바이오리듬 맞춤형 위스키 큐레이션 엔진
12. **[환율 NOW](https://drbrookskim.github.io/exchangenow/)** (#01) — 실시간 교차환율 계산기 및 통화 리포트 PWA

## 프로젝트 구조

```
drbrooks-services/
├── index.html        # 메인 웹 애플리케이션 진입점
├── style.css         # 반응형 글래스모피즘 스타일시트 & 다크/라이트 디자인 토큰
├── app.js            # 타임라인/그리드 뷰, 카테고리 필터링, 모달, 테마 로직
├── services.json     # 12개 서비스 런타임 데이터셋 (최신 역순)
├── CLAUDE.md         # 하네스 포인터 및 변경 이력
└── .claude/          # 에이전트 및 스킬 정의
```

## 기술 스택
- **HTML5 / Modern CSS3** (CSS Variables, Flexbox, Grid, Glassmorphism)
- **Vanilla JavaScript (ES6+)**
- **Dual View Modes**: Chronological Timeline View & Card Grid View
- **Theme**: Zero-Flicker Dark / Light Mode with System Preference & LocalStorage Persistence
