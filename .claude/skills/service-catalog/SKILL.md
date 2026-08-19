---
name: service-catalog
description: Dr. Brooks Kim의 프로젝트 서비스 목록을 1번부터 12번까지 올림차순으로 체계화하고 JSON 메타데이터 스키마를 생성·검증·관리하는 스킬. 서비스 추가, 메타데이터 수정, 태그 분류, 기술 스택 업데이트 요청 시 반드시 이 스킬을 사용할 것.
---

# Service Catalog Skill

## 목적
Dr. Brooks Kim이 제작한 웹 서비스 12종의 메타데이터를 표준 JSON 규격으로 정제하고, 새로운 서비스 추가나 메타데이터 변경 시 일관된 품질과 올림차순 정렬을 유지한다.

## 데이터 스키마 (Standard JSON Schema)

각 서비스 객체는 아래 속성을 반드시 포함해야 한다:

```json
{
  "id": 1,
  "slug": "exchangenow",
  "title": "환율 NOW",
  "titleEn": "Exchange NOW",
  "tagline": "실시간 교차환율 계산기 및 통화 리포트",
  "taglineEn": "Real-time Cross-Currency Calculator & Interactive Financial Report",
  "description": "다양한 통화(THB, USD, VND, PHP, KRW)를 실시간으로 환산하고 즉각적인 금융 계산을 지원하는 인터랙티브 PWA 서비스",
  "url": "https://drbrookskim.github.io/exchangenow/",
  "category": "Finance",
  "tags": ["Finance", "Currency", "PWA", "Real-time", "Calculator"],
  "techStack": ["JavaScript", "Chart.js", "PWA", "HTML5/CSS3"],
  "icon": "fa-solid fa-coins",
  "themeColor": "#0E9080",
  "badge": "Genesis 01",
  "featured": true,
  "releasedOrder": 1
}
```

## 12개 서비스 표준 카탈로그 목록 (올림차순 정렬)

1. **#01 환율 NOW (`exchangenow`)**
   - URL: `https://drbrookskim.github.io/exchangenow/`
   - 카테고리: `Finance & Trading`
   - 설명: 실시간 교차환율 계산 및 주요 아시아 통화 환율 리포트 제공 PWA

2. **#02 오늘의 위스키 (`todayswhisky`)**
   - URL: `https://drbrookskim.github.io/todayswhisky/`
   - 카테고리: `Lifestyle & Curation`
   - 설명: MBTI 성향 및 당일 바이오리듬/감정 상태 기반 맞춤형 위스키 큐레이션 및 추천

3. **#03 SIGNNITH (`signnith`)**
   - URL: `https://drbrookskim.github.io/signnith/`
   - 카테고리: `Market Intelligence`
   - 설명: 주식 시장 지표, 다차원 센티먼트, 수급 시그널 통합 인텔리전스 대시보드

4. **#04 EquiSense (`equisense`)**
   - URL: `https://drbrookskim.github.io/equisense/`
   - 카테고리: `Stock Analysis`
   - 설명: 펀더멘털 · 해자 · 정성적 · 기술적 지표 4단계 주식 심층 분석 플랫폼

5. **#05 Dr. Brooks Thoughts (`thoughts`)**
   - URL: `https://drbrookskim.github.io/thoughts/`
   - 카테고리: `Knowledge & Archive`
   - 설명: 브런치 연동 옵시디언 스타일 인터랙티브 지식 네트워크 그래프 및 생각 아카이브

6. **#06 Signnith News Finder (`newsfinder`)**
   - URL: `https://drbrookskim.github.io/newsfinder/`
   - 카테고리: `AI & Search`
   - 설명: On-Demand AI 기반 실시간 뉴스 분석 및 주식/산업 핵심 이슈 브리핑 검색 엔진

7. **#07 PITL (`pitl`)**
   - URL: `https://drbrookskim.github.io/pitl/`
   - 카테고리: `Productivity & Planning`
   - 설명: Autonomous Product Planning Workspace (Starbucks Design System 기반 자율 제품 기획 대시보드)

8. **#08 gitmark (`gitmark`)**
   - URL: `https://drbrookskim.github.io/gitmark/`
   - 카테고리: `Developer & Tool`
   - 설명: GitHub 기반 지능형 북마크/아카이브 및 피드 관리 PWA (Supabase 연동)

9. **#09 NELCOME.md / SkillBoard (`skillboard`)**
   - URL: `https://drbrookskim.github.io/skillboard/`
   - 카테고리: `AI Agents & Prompts`
   - 설명: AI 에이전트 스킬, 프롬프트, 커스터마이징 툴킷 대시보드 및 지식 허브

10. **#10 Chart Deep Dive (`chartdeepdive`)**
    - URL: `https://chartdeepdive.vercel.app/`
    - 카테고리: `Technical Analysis`
    - 설명: 종목 캔들 차트 기반 기본 지표 · 패턴 · 고급 기술적 기법 심층 분석 엔진 (KR/US)

11. **#11 NOSTOS: Buy the Dip (`buythedip`)**
    - URL: `https://drbrookskim.github.io/buythedip/`
    - 카테고리: `Trading Strategy`
    - 설명: 주식 눌림목 매수 및 다각적 매도 전략(트레일링 스탑, 타임컷, 손익비) AI 백테스팅 및 시뮬레이터

12. **#12 Dr. Brooks Money Report (`moneyreport`)**
    - URL: `https://drbrooks-moneyreport.pages.dev/`
    - 카테고리: `Signal Intelligence`
    - 설명: 산업 핵심 시그널과 밸류체인 심층 분석 리포트 실시간 아카이브 및 뷰어

## 큐레이션 체크리스트
- [ ] 1번부터 12번까지 `releasedOrder` 및 `id`가 올림차순으로 일치하는가?
- [ ] 모든 URL의 도메인(`github.io`, `vercel.app`, `pages.dev`)이 정확한가?
- [ ] 카테고리 분류가 균형 있게 배치되어 필터링이 유의미하게 작동하는가?
- [ ] 태그 목록이 검색 키워드로서 실효성이 있는가?
