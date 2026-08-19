---
name: showcase-ui-system
description: Dr. Brooks Kim 서비스 허브 포털의 디자인 시스템, 반응형 레이아웃, 인터랙티브 뷰(타임라인/그리드), 라이브 프리뷰, 테마 전환 등 UI/UX 구현 규칙을 제공하는 스킬. 웹사이트 프론트엔드 디자인 및 인터랙션 구현 시 반드시 이 스킬을 사용할 것.
---

# Showcase UI System Skill

## 목적
Dr. Brooks Kim의 12개 서비스를 게시하는 포털 웹사이트를 현대적이고 세련된 인터페이스로 구현하기 위한 디자인 토큰, 레이아웃 가이드라인, 인터랙션 패턴을 정의한다.

## 핵심 UX 원칙
1. **듀얼 뷰 모드 (Dual View Mode)**:
   - **Chronological Timeline View (올림차순 타임라인)**: 1번 서비스부터 12번 서비스까지의 창작 여정과 빌드업 과정을 시각적인 스토리라인으로 전달.
   - **Card Grid View (카드 그리드)**: 한눈에 전체 서비스를 탐색하고 카테고리별로 빠르게 필터링할 수 있는 모던 카드 레이아웃.
2. **원클릭 빠른 탐색 & 프리뷰**:
   - 직접 방문 버튼 (Direct Launch, 새 탭)
   - 서비스 요약 및 상세 정보 모달 (Quick Details / Preview Drawer)
   - 링크 복사 및 공유 기능
3. **즉각적인 실시간 검색 & 필터링**:
   - 키워드(서비스명, 태그, 기술스택, 설명) 실시간 필터링
   - 카테고리 필터 탭 (전체, 금융/투자, AI/데이터, 라이프스타일/툴, 전체)
   - 통계 바 (총 서비스 수: 12개, 카테고리 분포)
4. **다크 모드 & 라이트 모드 (Zero-Flicker Theme System)**:
   - 시스템 설정 감지 + 사용자 로컬스토리지 저장 지원.

## 디자인 토큰 (CSS Variables)

```css
:root {
  /* 라이트 모드 기본 */
  --bg-primary: #f8fafc;
  --bg-secondary: #ffffff;
  --bg-glass: rgba(255, 255, 255, 0.85);
  --border-color: rgba(226, 232, 240, 0.8);
  --text-primary: #0f172a;
  --text-secondary: #475569;
  --text-muted: #94a3b8;
  --accent-primary: #3b82f6;
  --accent-secondary: #06b6d4;
  --accent-gradient: linear-gradient(135deg, #3b82f6 0%, #8b5cf6 50%, #ec4899 100%);
  --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
  --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  --card-radius: 16px;
  --font-display: 'Space Grotesk', -apple-system, BlinkMacSystemFont, sans-serif;
  --font-body: 'Pretendard', 'Inter', -apple-system, sans-serif;
  --font-mono: 'JetBrains Mono', monospace;
}

[data-theme="dark"] {
  /* 다크 모드 */
  --bg-primary: #0a0f1d;
  --bg-secondary: #111827;
  --bg-glass: rgba(17, 24, 39, 0.85);
  --border-color: rgba(31, 41, 55, 0.9);
  --text-primary: #f8fafc;
  --text-secondary: #cbd5e1;
  --text-muted: #64748b;
  --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.3);
  --shadow-md: 0 4px 12px 0 rgba(0, 0, 0, 0.4);
  --shadow-xl: 0 20px 30px -5px rgba(0, 0, 0, 0.6);
}
```

## 반응형 브레이크포인트
- Mobile: `< 640px` (단일 컬럼, 하단 액션)
- Tablet: `640px ~ 1024px` (2컬럼 그리드)
- Desktop: `> 1024px` (3컬럼 그리드 / 풀 와이드 타임라인)
