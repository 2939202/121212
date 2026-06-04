cat > /mnt/user-data/outputs/myduck-cafe.html << 'HTMLEOF'
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=1280">
<title>MY DUCK – 슬기로운 덕질 커뮤니티</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;700;900&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Noto Sans KR',sans-serif;background:#f4f5f7;color:#1a1a1a;min-width:1280px;font-size:13px;}

/* ── 최상단 글로벌 바 ── */
.global-bar{background:#1f2937;height:32px;display:flex;align-items:center;padding:0 20px;gap:16px;}
.global-bar a{color:#9ca3af;font-size:11px;text-decoration:none;}
.global-bar a:hover{color:#fff;}
.global-bar .sep{color:#374151;}
.global-bar-right{margin-left:auto;display:flex;gap:12px;align-items:center;}
.gb-btn{padding:3px 10px;border-radius:3px;font-size:11px;border:1px solid #374151;color:#9ca3af;background:none;cursor:pointer;font-family:'Noto Sans KR',sans-serif;}
.gb-btn.accent{background:#FFCB2B;border-color:#FFCB2B;color:#1a1a1a;font-weight:700;}

/* ── 서비스 헤더 ── */
.service-header{background:#fff;border-bottom:1px solid #e5e7eb;padding:0 20px;height:52px;display:flex;align-items:center;gap:0;}
.service-logo{display:flex;align-items:center;gap:10px;padding-right:24px;border-right:1px solid #e5e7eb;margin-right:20px;}
.duck-svg{width:30px;height:30px;}
.logo-wordmark{font-weight:900;font-size:18px;color:#1a1a1a;letter-spacing:-0.5px;}
.logo-sub{font-size:10px;color:#9ca3af;margin-top:1px;}
.service-search{flex:1;max-width:480px;display:flex;gap:0;}
.service-search input{flex:1;height:34px;border:1.5px solid #FFCB2B;border-right:none;border-radius:4px 0 0 4px;padding:0 12px;font-size:13px;font-family:'Noto Sans KR',sans-serif;outline:none;color:#1a1a1a;}
.service-search button{height:34px;padding:0 16px;background:#FFCB2B;border:1.5px solid #FFCB2B;border-radius:0 4px 4px 0;font-size:12px;font-weight:700;cursor:pointer;font-family:'Noto Sans KR',sans-serif;color:#1a1a1a;}
.service-header-right{margin-left:auto;display:flex;align-items:center;gap:12px;}
.header-icon-btn{display:flex;flex-direction:column;align-items:center;gap:2px;background:none;border:none;cursor:pointer;color:#6b7280;font-size:10px;padding:4px 8px;border-radius:4px;}
.header-icon-btn:hover{background:#f9fafb;color:#1a1a1a;}
.header-icon-btn .ico{font-size:18px;}
.write-btn{padding:7px 18px;background:#FFCB2B;border:none;border-radius:4px;font-size:12px;font-weight:700;cursor:pointer;font-family:'Noto Sans KR',sans-serif;color:#1a1a1a;}

/* ── 카페 네비게이션 탭 ── */
.cafe-nav{background:#fff;border-bottom:2px solid #FFCB2B;}
.cafe-nav-inner{max-width:1240px;margin:0 auto;display:flex;align-items:center;padding:0 20px;}
.cafe-nav-tab{padding:12px 18px;font-size:13px;font-weight:500;color:#4b5563;border-bottom:2px solid transparent;margin-bottom:-2px;cursor:pointer;white-space:nowrap;transition:color .15s;}
.cafe-nav-tab:hover{color:#1a1a1a;}
.cafe-nav-tab.active{color:#1a1a1a;font-weight:700;border-bottom-color:#FFCB2B;}

/* ── AI 상태 알림바 ── */
.ai-notice{background:#f0fdf4;border-bottom:1px solid #bbf7d0;padding:7px 20px;display:flex;align-items:center;gap:8px;}
.ai-notice-inner{max-width:1240px;margin:0 auto;display:flex;align-items:center;gap:8px;width:100%;}
.ai-dot{width:7px;height:7px;border-radius:50%;background:#22c55e;animation:blink 1.5s infinite;}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:.4;}}
.ai-notice-text{font-size:11px;color:#166534;font-weight:500;}
.ai-count{font-weight:700;color:#15803d;}
.ai-notice-right{margin-left:auto;font-size:11px;color:#166534;}

/* ── 메인 3단 레이아웃 ── */
.main-wrap{max-width:1240px;margin:0 auto;padding:16px 20px;display:grid;grid-template-columns:188px 1fr 200px;gap:12px;align-items:start;}

/* ── 왼쪽 사이드바 ── */
.left-col{display:flex;flex-direction:column;gap:0;}

/* 카페 프로필 박스 */
.cafe-profile{background:#fff;border:1px solid #e5e7eb;border-radius:6px;overflow:hidden;margin-bottom:8px;}
.cafe-profile-banner{height:72px;background:linear-gradient(135deg,#1f2937 0%,#374151 100%);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden;}
.cafe-profile-banner::after{content:'🦆';position:absolute;font-size:40px;opacity:.25;right:10px;bottom:-4px;}
.cafe-profile-body{padding:12px;}
.cafe-name{font-size:14px;font-weight:700;color:#1a1a1a;margin-bottom:2px;}
.cafe-slogan{font-size:10px;color:#9ca3af;margin-bottom:10px;}
.cafe-stats-row{display:grid;grid-template-columns:1fr 1fr;gap:4px;margin-bottom:10px;}
.cafe-stat{text-align:center;padding:6px 4px;background:#f9fafb;border-radius:4px;}
.cafe-stat .n{font-size:14px;font-weight:700;color:#1a1a1a;}
.cafe-stat .l{font-size:10px;color:#9ca3af;margin-top:1px;}
.cafe-join-btn{width:100%;padding:8px;background:#FFCB2B;border:none;border-radius:4px;font-size:12px;font-weight:700;cursor:pointer;font-family:'Noto Sans KR',sans-serif;color:#1a1a1a;}

/* 왼쪽 메뉴 박스 */
.left-menu-box{background:#fff;border:1px solid #e5e7eb;border-radius:6px;overflow:hidden;margin-bottom:8px;}
.lmb-title{padding:10px 12px;font-size:12px;font-weight:700;color:#1a1a1a;border-bottom:1px solid #f3f4f6;background:#f9fafb;display:flex;align-items:center;gap:6px;}
.menu-section-label{padding:8px 12px 4px;font-size:10px;font-weight:700;color:#9ca3af;text-transform:uppercase;letter-spacing:.5px;}
.menu-item{display:flex;align-items:center;gap:8px;padding:7px 12px;cursor:pointer;transition:background .12s;border-left:2px solid transparent;}
.menu-item:hover{background:#f9fafb;}
.menu-item.active{background:#fffbeb;border-left-color:#FFCB2B;}
.menu-item.active .mi-name{font-weight:700;color:#1a1a1a;}
.mi-icon{width:18px;height:18px;border-radius:3px;display:flex;align-items:center;justify-content:center;font-size:11px;flex-shrink:0;}
.mi-name{font-size:12px;color:#374151;flex:1;}
.mi-count{font-size:10px;color:#9ca3af;background:#f3f4f6;padding:1px 6px;border-radius:10px;}
.menu-sub{padding:5px 12px 5px 34px;cursor:pointer;display:flex;align-items:center;justify-content:space-between;}
.menu-sub:hover .ms-name{color:#1a1a1a;}
.ms-name{font-size:11px;color:#6b7280;}
.ms-count{font-size:10px;color:#9ca3af;}

/* AI 위젯 */
.ai-widget{background:#fff;border:1px solid #e5e7eb;border-radius:6px;overflow:hidden;margin-bottom:8px;}
.ai-widget-header{padding:10px 12px;background:linear-gradient(135deg,#065f46,#047857);display:flex;align-items:center;gap:7px;}
.ai-widget-header .t{font-size:12px;font-weight:700;color:#fff;}
.ai-widget-header .s{font-size:10px;color:rgba(255,255,255,.7);margin-top:1px;}
.ai-widget-body{padding:10px 12px;display:flex;flex-direction:column;gap:6px;}
.ai-stat-row{display:flex;align-items:center;justify-content:space-between;}
.ai-stat-label{font-size:11px;color:#4b5563;display:flex;align-items:center;gap:5px;}
.ai-stat-val{font-size:12px;font-weight:700;}
.ai-bar-wrap{height:4px;background:#f3f4f6;border-radius:2px;margin:2px 0 6px;overflow:hidden;}
.ai-bar{height:4px;border-radius:2px;background:linear-gradient(90deg,#22c55e,#16a34a);}

/* 일정 위젯 */
.schedule-widget{background:#fff;border:1px solid #e5e7eb;border-radius:6px;overflow:hidden;}
.sw-header{padding:10px 12px;border-bottom:1px solid #f3f4f6;font-size:12px;font-weight:700;display:flex;align-items:center;gap:6px;}
.sw-body{padding:8px 12px;display:flex;flex-direction:column;gap:6px;}
.sw-item{display:flex;gap:8px;align-items:flex-start;padding:6px 0;border-bottom:1px solid #f9fafb;}
.sw-item:last-child{border-bottom:none;}
.sw-date{background:#e0e7ff;color:#4338ca;font-size:10px;font-weight:700;padding:3px 6px;border-radius:3px;white-space:nowrap;flex-shrink:0;margin-top:1px;}
.sw-date.today{background:#dcfce7;color:#16a34a;}
.sw-date.soon{background:#fef3c7;color:#92400e;}
.sw-info .name{font-size:11px;font-weight:600;color:#1a1a1a;line-height:1.3;}
.sw-info .sub{font-size:10px;color:#9ca3af;margin-top:1px;}

/* ── 중앙 피드 ── */
.center-col{display:flex;flex-direction:column;gap:8px;}

/* 배너 */
.hero-banner{background:linear-gradient(135deg,#1f2937 0%,#111827 100%);border-radius:6px;height:180px;overflow:hidden;position:relative;display:flex;align-items:center;margin-bottom:4px;}
.banner-text-area{padding:24px 28px;z-index:2;flex-shrink:0;}
.banner-badge{display:inline-flex;align-items:center;gap:5px;background:rgba(255,203,43,.15);border:1px solid rgba(255,203,43,.35);border-radius:3px;padding:3px 10px;font-size:10px;font-weight:700;color:#FFCB2B;margin-bottom:8px;}
.banner-title{font-size:22px;font-weight:900;color:#fff;line-height:1.25;letter-spacing:-.5px;}
.banner-title em{color:#FFCB2B;font-style:normal;}
.banner-sub{font-size:12px;color:rgba(255,255,255,.55);margin-top:6px;}
.banner-btns{display:flex;gap:8px;margin-top:14px;}
.banner-btn-p{padding:8px 18px;background:#FFCB2B;border:none;border-radius:4px;font-size:12px;font-weight:700;cursor:pointer;font-family:'Noto Sans KR',sans-serif;color:#1a1a1a;}
.banner-btn-s{padding:8px 16px;background:rgba(255,255,255,.1);border:1px solid rgba(255,255,255,.2);border-radius:4px;font-size:12px;font-weight:500;cursor:pointer;font-family:'Noto Sans KR',sans-serif;color:rgba(255,255,255,.8);}
/* Characters SVG area */
.banner-chars{flex:1;height:100%;position:relative;}

/* 브랜드 룸 슬라이드 */
.brand-row{background:#fff;border:1px solid #e5e7eb;border-radius:6px;padding:10px 14px;}
.brand-row-title{font-size:11px;font-weight:700;color:#9ca3af;margin-bottom:8px;display:flex;align-items:center;gap:5px;}
.brand-chips{display:flex;gap:6px;flex-wrap:wrap;}
.brand-chip{display:flex;align-items:center;gap:5px;padding:4px 10px 4px 6px;background:#f9fafb;border:1px solid #e5e7eb;border-radius:3px;font-size:11px;font-weight:600;color:#374151;cursor:pointer;white-space:nowrap;transition:border-color .12s,background .12s;}
.brand-chip:hover{border-color:#FFCB2B;background:#fffbeb;}
.brand-chip .bci{width:18px;height:18px;border-radius:2px;display:flex;align-items:center;justify-content:center;font-size:11px;flex-shrink:0;}
.brand-chip .new{background:#ef4444;color:#fff;font-size:9px;font-weight:700;padding:1px 4px;border-radius:2px;margin-left:2px;}

/* 게시판 탭 */
.board-tabs{background:#fff;border:1px solid #e5e7eb;border-radius:6px 6px 0 0;border-bottom:none;padding:0 14px;display:flex;align-items:center;justify-content:space-between;}
.board-tab-left{display:flex;}
.board-tab{padding:11px 14px;font-size:12px;font-weight:500;color:#6b7280;border-bottom:2px solid transparent;cursor:pointer;white-space:nowrap;transition:color .12s;}
.board-tab:hover{color:#1a1a1a;}
.board-tab.active{font-weight:700;color:#1a1a1a;border-bottom-color:#FFCB2B;}
.board-write{padding:6px 14px;background:#FFCB2B;border:none;border-radius:3px;font-size:11px;font-weight:700;cursor:pointer;font-family:'Noto Sans KR',sans-serif;color:#1a1a1a;}

/* 게시글 테이블 (네이버 카페 스타일) */
.post-table{background:#fff;border:1px solid #e5e7eb;border-radius:0 0 6px 6px;overflow:hidden;}
.post-table-head{display:grid;grid-template-columns:60px 1fr 80px 60px 52px;background:#f9fafb;border-bottom:1px solid #e5e7eb;padding:7px 14px;gap:8px;}
.pth{font-size:11px;font-weight:700;color:#9ca3af;}
.post-row{display:grid;grid-template-columns:60px 1fr 80px 60px 52px;padding:9px 14px;gap:8px;border-bottom:1px solid #f3f4f6;align-items:center;cursor:pointer;transition:background .1s;}
.post-row:last-child{border-bottom:none;}
.post-row:hover{background:#fffbeb;}
.post-row.notice{background:#fffdf0;}
.pr-cat{display:inline-block;padding:2px 7px;border-radius:2px;font-size:10px;font-weight:700;white-space:nowrap;}
.cat-official{background:#fef3c7;color:#92400e;}
.cat-anime{background:#ede9fe;color:#6d28d9;}
.cat-idol{background:#fce7f3;color:#be185d;}
.cat-game{background:#dbeafe;color:#1d4ed8;}
.cat-info{background:#d1fae5;color:#065f46;}
.cat-event{background:#fff7ed;color:#c2410c;}
.cat-free{background:#f3f4f6;color:#4b5563;}
.cat-notice{background:#fee2e2;color:#991b1b;}
.pr-title-wrap{display:flex;align-items:center;gap:6px;min-width:0;}
.pr-title{font-size:13px;color:#1a1a1a;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;flex:1;}
.pr-title:hover{text-decoration:underline;}
.post-row.notice .pr-title{font-weight:700;}
.pr-new{color:#ef4444;font-size:10px;font-weight:700;flex-shrink:0;}
.pr-img-ico{font-size:11px;color:#9ca3af;flex-shrink:0;}
.pr-ai{display:flex;align-items:center;gap:3px;font-size:10px;color:#16a34a;flex-shrink:0;}
.pr-author{font-size:11px;color:#6b7280;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.pr-date{font-size:11px;color:#9ca3af;white-space:nowrap;}
.pr-views{font-size:11px;color:#9ca3af;text-align:right;}
.pr-likes{font-size:11px;color:#9ca3af;text-align:right;}

/* 페이지네이션 */
.pagination{background:#fff;border:1px solid #e5e7eb;border-top:none;border-radius:0 0 6px 6px;padding:10px;display:flex;justify-content:center;gap:3px;}
.pg-btn{width:28px;height:28px;border-radius:3px;border:1px solid #e5e7eb;background:#fff;font-size:12px;color:#4b5563;cursor:pointer;display:flex;align-items:center;justify-content:center;font-family:'Noto Sans KR',sans-serif;}
.pg-btn.active{background:#FFCB2B;border-color:#FFCB2B;font-weight:700;color:#1a1a1a;}
.pg-btn:hover:not(.active){background:#f9fafb;}

/* 인기글 박스 */
.hot-box{background:#fff;border:1px solid #e5e7eb;border-radius:6px;overflow:hidden;}
.hot-box-header{padding:10px 14px;border-bottom:1px solid #f3f4f6;display:flex;align-items:center;justify-content:space-between;}
.hot-box-title{font-size:12px;font-weight:700;color:#1a1a1a;display:flex;align-items:center;gap:5px;}
.hot-box-more{font-size:11px;color:#9ca3af;cursor:pointer;}
.hot-box-more:hover{color:#1a1a1a;}
.hot-row{display:flex;align-items:center;gap:8px;padding:8px 14px;border-bottom:1px solid #f9fafb;cursor:pointer;}
.hot-row:last-child{border-bottom:none;}
.hot-row:hover{background:#f9fafb;}
.hot-rank{width:18px;height:18px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:700;flex-shrink:0;}
.rank-1{background:#FFCB2B;color:#1a1a1a;}
.rank-2{background:#e2e8f0;color:#475569;}
.rank-3{background:#fed7aa;color:#7c2d12;}
.rank-n{background:#f3f4f6;color:#9ca3af;}
.hot-row-title{font-size:12px;color:#1a1a1a;flex:1;white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.hot-row-likes{font-size:10px;color:#9ca3af;flex-shrink:0;display:flex;align-items:center;gap:2px;}

/* ── 오른쪽 사이드바 ── */
.right-col{display:flex;flex-direction:column;gap:8px;}

/* 통계 박스 */
.stats-box{background:#fff;border:1px solid #e5e7eb;border-radius:6px;overflow:hidden;}
.stats-box-header{padding:9px 12px;border-bottom:1px solid #f3f4f6;font-size:12px;font-weight:700;display:flex;align-items:center;gap:5px;}
.stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:0;}
.stat-cell{padding:10px 12px;text-align:center;border-right:1px solid #f3f4f6;border-bottom:1px solid #f3f4f6;}
.stat-cell:nth-child(2n){border-right:none;}
.stat-cell:nth-child(3),.stat-cell:nth-child(4){border-bottom:none;}
.stat-cell .n{font-size:16px;font-weight:700;color:#1a1a1a;}
.stat-cell .l{font-size:10px;color:#9ca3af;margin-top:2px;}
.online-bar{padding:8px 12px;display:flex;align-items:center;gap:6px;border-top:1px solid #f3f4f6;}
.online-dot{width:6px;height:6px;border-radius:50%;background:#22c55e;animation:blink 1.5s infinite;flex-shrink:0;}
.online-text{font-size:11px;color:#374151;font-weight:500;}

/* 이벤트 박스 */
.event-box{background:#fff;border:1px solid #e5e7eb;border-radius:6px;overflow:hidden;}
.event-box-header{padding:9px 12px;border-bottom:1px solid #f3f4f6;font-size:12px;font-weight:700;display:flex;align-items:center;justify-content:space-between;}
.event-more{font-size:11px;color:#9ca3af;cursor:pointer;}
.event-item{display:flex;gap:8px;padding:8px 12px;border-bottom:1px solid #f9fafb;cursor:pointer;}
.event-item:last-child{border-bottom:none;}
.event-item:hover{background:#f9fafb;}
.event-date-badge{min-width:34px;height:34px;border-radius:4px;background:#1f2937;display:flex;flex-direction:column;align-items:center;justify-content:center;flex-shrink:0;}
.event-date-badge .m{font-size:9px;color:#9ca3af;font-weight:500;}
.event-date-badge .d{font-size:13px;font-weight:700;color:#fff;line-height:1;}
.event-info .ename{font-size:11px;font-weight:600;color:#1a1a1a;line-height:1.3;}
.event-info .esub{font-size:10px;color:#9ca3af;margin-top:2px;}
.event-info .etag{display:inline-block;margin-top:3px;padding:1px 6px;background:#f3f4f6;border-radius:2px;font-size:10px;color:#6b7280;}

/* 카테고리 랭킹 */
.rank-box{background:#fff;border:1px solid #e5e7eb;border-radius:6px;overflow:hidden;}
.rank-box-header{padding:9px 12px;border-bottom:1px solid #f3f4f6;font-size:12px;font-weight:700;}
.rank-item{display:flex;align-items:center;gap:8px;padding:7px 12px;border-bottom:1px solid #f9fafb;cursor:pointer;}
.rank-item:last-child{border-bottom:none;}
.rank-item:hover{background:#f9fafb;}
.ri-rank{font-size:12px;font-weight:700;color:#9ca3af;width:16px;text-align:center;flex-shrink:0;}
.ri-rank.top{color:#FFCB2B;}
.ri-icon{width:22px;height:22px;border-radius:3px;display:flex;align-items:center;justify-content:center;font-size:13px;flex-shrink:0;}
.ri-name{font-size:12px;color:#1a1a1a;flex:1;font-weight:500;}
.ri-count{font-size:10px;color:#9ca3af;}

/* 광고/배너 영역 */
.side-banner{background:linear-gradient(135deg,#1f2937,#374151);border-radius:6px;padding:14px 12px;text-align:center;}
.sb-title{font-size:12px;font-weight:700;color:#fff;margin-bottom:4px;}
.sb-sub{font-size:10px;color:#9ca3af;margin-bottom:10px;line-height:1.4;}
.sb-btn{width:100%;padding:8px;background:#FFCB2B;border:none;border-radius:4px;font-size:11px;font-weight:700;cursor:pointer;font-family:'Noto Sans KR',sans-serif;color:#1a1a1a;}

/* ── 푸터 ── */
.footer{background:#fff;border-top:1px solid #e5e7eb;margin-top:24px;padding:20px;text-align:center;}
.footer-inner{max-width:1240px;margin:0 auto;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:12px;}
.footer-logo{font-size:14px;font-weight:700;color:#1a1a1a;}
.footer-links{display:flex;gap:16px;}
.footer-links a{font-size:11px;color:#9ca3af;text-decoration:none;}
.footer-links a:hover{color:#1a1a1a;}
.footer-badges{display:flex;gap:8px;}
.footer-badge{padding:3px 10px;border:1px solid #e5e7eb;border-radius:3px;font-size:10px;color:#6b7280;display:flex;align-items:center;gap:4px;}
.footer-copy{font-size:10px;color:#9ca3af;}
</style>
</head>
<body>

<!-- 글로벌 최상단 바 -->
<div class="global-bar">
  <a href="#">MY DUCK 홈</a>
  <span class="sep">|</span>
  <a href="#">공지사항</a>
  <span class="sep">|</span>
  <a href="#">이용약관</a>
  <span class="sep">|</span>
  <a href="#">개인정보처리방침</a>
  <div class="global-bar-right">
    <a href="#">로그인</a>
    <span class="sep">|</span>
    <a href="#">회원가입</a>
    <button class="gb-btn accent">글쓰기</button>
  </div>
</div>

<!-- 서비스 헤더 -->
<div class="service-header">
  <div class="service-logo">
    <!-- Duck SVG -->
    <svg class="duck-svg" viewBox="0 0 30 30" fill="none">
      <circle cx="15" cy="15" r="15" fill="#FFF3C0"/>
      <ellipse cx="15" cy="19" rx="8" ry="6.5" fill="#FFCB2B"/>
      <circle cx="15" cy="11" r="6" fill="#FFCB2B"/>
      <circle cx="17" cy="9.5" r="1.5" fill="#1a1a1a"/>
      <circle cx="17.4" cy="9.1" r=".5" fill="#fff"/>
      <path d="M19 11.5 Q21 11 21 12.5 Q21 14 19 13.5Z" fill="#FF8A3D"/>
      <ellipse cx="11" cy="19" rx="3.5" ry="2" fill="#FFB800" transform="rotate(-15 11 19)"/>
      <circle cx="15.5" cy="12" r="1.5" fill="rgba(255,138,61,.3)"/>
    </svg>
    <div>
      <div class="logo-wordmark">MY DUCK</div>
      <div class="logo-sub">슬기로운 덕질 커뮤니티</div>
    </div>
  </div>
  <div class="service-search">
    <input type="text" placeholder="카페 내 게시글, 댓글 검색">
    <button>검색</button>
  </div>
  <div class="service-header-right">
    <button class="header-icon-btn"><span class="ico">🔔</span>알림</button>
    <button class="header-icon-btn"><span class="ico">💬</span>쪽지</button>
    <button class="header-icon-btn"><span class="ico">👤</span>내정보</button>
    <button class="write-btn">✏️ 글쓰기</button>
  </div>
</div>

<!-- 카페 네비게이션 -->
<div class="cafe-nav">
  <div class="cafe-nav-inner">
    <div class="cafe-nav-tab active">전체글</div>
    <div class="cafe-nav-tab">공지사항</div>
    <div class="cafe-nav-tab">자유게시판</div>
    <div class="cafe-nav-tab">🎮 게이밍</div>
    <div class="cafe-nav-tab">🎌 애니메이션</div>
    <div class="cafe-nav-tab">🎤 아이돌</div>
    <div class="cafe-nav-tab">🎨 팬아트</div>
    <div class="cafe-nav-tab">🛍️ 굿즈마켓</div>
    <div class="cafe-nav-tab">📅 이벤트</div>
    <div class="cafe-nav-tab">🏠 공식 브랜드 룸</div>
  </div>
</div>

<!-- AI 알림바 -->
<div class="ai-notice">
  <div class="ai-notice-inner">
    <div class="ai-dot"></div>
    <div class="ai-notice-text">🛡️ AI 실시간 필터링 가동 중 &nbsp;|&nbsp; 오늘 <span class="ai-count">3,847건</span> 유해 콘텐츠 차단 완료 &nbsp;|&nbsp; AI 정확도 <span class="ai-count">99.2%</span></div>
    <div class="ai-notice-right">MY DUCK AI Security v4.2 &nbsp;✓</div>
  </div>
</div>

<!-- 메인 3단 레이아웃 -->
<div class="main-wrap">

  <!-- ═══ 왼쪽 사이드바 ═══ -->
  <div class="left-col">

    <!-- 카페 프로필 -->
    <div class="cafe-profile">
      <div class="cafe-profile-banner">
        <svg width="188" height="72" viewBox="0 0 188 72" fill="none">
          <text x="18" y="34" font-size="28" opacity=".15">🦆</text>
          <text x="60" y="28" font-size="18" font-weight="900" fill="white" font-family="Noto Sans KR,sans-serif" opacity=".9">MY DUCK</text>
          <text x="60" y="44" font-size="10" fill="rgba(255,255,255,.5)" font-family="Noto Sans KR,sans-serif">슬기로운 덕질을 위하여</text>
          <!-- mini duck illustration -->
          <circle cx="28" cy="38" r="14" fill="#FFCB2B" opacity=".8"/>
          <circle cx="28" cy="29" r="9" fill="#FFCB2B" opacity=".8"/>
          <path d="M34 31 Q38 30 38 33 Q38 36 34 35Z" fill="#FF8A3D" opacity=".8"/>
          <circle cx="31" cy="27.5" r="2" fill="#1a1a1a" opacity=".8"/>
        </svg>
      </div>
      <div class="cafe-profile-body">
        <div class="cafe-name">🦆 MY DUCK</div>
        <div class="cafe-slogan">AI 청정 팬 커뮤니티</div>
        <div class="cafe-stats-row">
          <div class="cafe-stat"><div class="n">284K</div><div class="l">회원</div></div>
          <div class="cafe-stat"><div class="n" style="color:#22c55e;">3,847</div><div class="l">접속 중</div></div>
          <div class="cafe-stat"><div class="n">5.2K</div><div class="l">오늘 글</div></div>
          <div class="cafe-stat"><div class="n">48K</div><div class="l">누적 이벤트</div></div>
        </div>
        <button class="cafe-join-btn">+ 카페 가입하기</button>
      </div>
    </div>

    <!-- 메뉴 -->
    <div class="left-menu-box">
      <div class="lmb-title">📋 전체 메뉴</div>

      <div class="menu-item active">
        <div class="mi-icon" style="background:#fffbeb;">📝</div>
        <div class="mi-name">전체 글 보기</div>
        <div class="mi-count">전체</div>
      </div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#fee2e2;">📢</div>
        <div class="mi-name">공지사항</div>
      </div>

      <div class="menu-section-label">📁 자유게시판</div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#f3f4f6;">💬</div>
        <div class="mi-name">자유게시판</div>
        <div class="mi-count">1.2K</div>
      </div>

      <div class="menu-section-label">🏠 공식 IP 브랜드 룸</div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#dbeafe;">🎮</div>
        <div class="mi-name">Nintendo Room</div>
        <div class="mi-count">2.1K</div>
      </div>
      <div class="menu-sub"><span class="ms-name">└ 포켓몬</span><span class="ms-count">980</span></div>

      <div class="menu-section-label">🎌 애니메이션</div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#fff7ed;">🏴‍☠️</div>
        <div class="mi-name">원피스</div>
        <div class="mi-count">4.2K</div>
      </div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#fff0f0;">🍥</div>
        <div class="mi-name">나루토</div>
        <div class="mi-count">3.1K</div>
      </div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#f5f3ff;">⚔️</div>
        <div class="mi-name">블리치</div>
        <div class="mi-count">1.9K</div>
      </div>

      <div class="menu-section-label">🎤 아이돌 엔터테인먼트</div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#fef9c3;">🟡</div>
        <div class="mi-name">YG Entertainment</div>
        <div class="mi-count">2.7K</div>
      </div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#f0fdf4;">🟢</div>
        <div class="mi-name">JYP Entertainment</div>
        <div class="mi-count">3.4K</div>
      </div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#eff6ff;">🔵</div>
        <div class="mi-name">BIGHIT MUSIC</div>
        <div class="mi-count">5.8K</div>
      </div>

      <div class="menu-section-label">🎨 기타</div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#f0fdf4;">🎨</div>
        <div class="mi-name">팬아트</div>
        <div class="mi-count">2.0K</div>
      </div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#fef3c7;">🛍️</div>
        <div class="mi-name">굿즈마켓</div>
        <div class="mi-count">1.5K</div>
      </div>
      <div class="menu-item">
        <div class="mi-icon" style="background:#fce7f3;">📅</div>
        <div class="mi-name">이벤트</div>
        <div class="mi-count">892</div>
      </div>
    </div>

    <!-- AI 위젯 -->
    <div class="ai-widget">
      <div class="ai-widget-header">
        <div>
          <div class="t">🛡️ AI 청정 지수</div>
          <div class="s">MY DUCK AI Security</div>
        </div>
      </div>
      <div class="ai-widget-body">
        <div class="ai-stat-row"><span class="ai-stat-label">✅ 오늘 차단</span><span class="ai-stat-val" style="color:#dc2626;">3,847건</span></div>
        <div class="ai-stat-row"><span class="ai-stat-label">🎯 탐지 정확도</span><span class="ai-stat-val" style="color:#16a34a;">99.2%</span></div>
        <div class="ai-bar-wrap"><div class="ai-bar" style="width:99.2%;"></div></div>
        <div class="ai-stat-row"><span class="ai-stat-label">😊 커뮤니티 만족도</span><span class="ai-stat-val" style="color:#FFCB2B;">4.9 ★</span></div>
        <div class="ai-stat-row"><span class="ai-stat-label">🔒 청정 게시글 비율</span><span class="ai-stat-val" style="color:#2563eb;">97.8%</span></div>
        <div class="ai-bar-wrap"><div class="ai-bar" style="width:97.8%;background:linear-gradient(90deg,#3b82f6,#2563eb);"></div></div>
      </div>
    </div>

    <!-- 일정 위젯 -->
    <div class="schedule-widget">
      <div class="sw-header">🤖 AI 덕질 일정 관리</div>
      <div class="sw-body">
        <div class="sw-item">
          <div class="sw-date today">오늘</div>
          <div class="sw-info"><div class="name">원피스 1120화 방영</div><div class="sub">애니메이션</div></div>
        </div>
        <div class="sw-item">
          <div class="sw-date soon">D-3</div>
          <div class="sw-info"><div class="name">BTS 새 앨범 발매</div><div class="sub">BIGHIT MUSIC</div></div>
        </div>
        <div class="sw-item">
          <div class="sw-date">D-7</div>
          <div class="sw-info"><div class="name">포켓몬 팬미팅</div><div class="sub">서울 공식 행사</div></div>
        </div>
        <div class="sw-item">
          <div class="sw-date">D-10</div>
          <div class="sw-info"><div class="name">MY DUCK 페스타</div><div class="sub">온오프라인 병행</div></div>
        </div>
        <div class="sw-item">
          <div class="sw-date">D-17</div>
          <div class="sw-info"><div class="name">블리치 신작 개봉</div><div class="sub">애니메이션</div></div>
        </div>
      </div>
    </div>

  </div>

  <!-- ═══ 중앙 피드 ═══ -->
  <div class="center-col">

    <!-- 히어로 배너 -->
    <div class="hero-banner">
      <div class="banner-text-area">
        <div class="banner-badge">🛡️ AI 청정 커뮤니티 인증</div>
        <div class="banner-title">덕질의 세계,<br><em>더 안전하게</em></div>
        <div class="banner-sub">AI 실시간 필터링으로 독성 없는 순수 팬 문화</div>
        <div class="banner-btns">
          <button class="banner-btn-p">카페 가입하기</button>
          <button class="banner-btn-s">브랜드 룸 보기</button>
        </div>
      </div>
      <!-- 캐릭터 SVG -->
      <div class="banner-chars">
        <svg width="100%" height="180" viewBox="0 0 600 180" fill="none" preserveAspectRatio="xMaxYMax meet">
          <!-- glow -->
          <ellipse cx="120" cy="170" rx="50" ry="8" fill="rgba(255,203,43,.2)"/>
          <ellipse cx="260" cy="170" rx="45" ry="7" fill="rgba(124,58,237,.2)"/>
          <ellipse cx="390" cy="170" rx="45" ry="7" fill="rgba(29,78,216,.2)"/>
          <ellipse cx="510" cy="170" rx="45" ry="7" fill="rgba(236,72,153,.2)"/>

          <!-- Duck -->
          <ellipse cx="120" cy="142" rx="32" ry="28" fill="#FFCB2B"/>
          <circle cx="120" cy="104" r="24" fill="#FFCB2B"/>
          <!-- cap -->
          <ellipse cx="120" cy="83" rx="26" ry="6" fill="#FF8A3D"/>
          <rect x="100" y="70" width="40" height="14" rx="7" fill="#FF8A3D"/>
          <!-- eyes -->
          <circle cx="112" cy="101" r="5" fill="#fff"/><circle cx="113" cy="101" r="3" fill="#1a1a1a"/><circle cx="113.8" cy="99.8" r="1" fill="#fff"/>
          <circle cx="128" cy="101" r="5" fill="#fff"/><circle cx="129" cy="101" r="3" fill="#1a1a1a"/><circle cx="129.8" cy="99.8" r="1" fill="#fff"/>
          <!-- beak -->
          <path d="M116 110 Q122 106 130 110 Q130 116 122 116 Q116 116 116 110Z" fill="#FF8A3D"/>
          <!-- blush -->
          <circle cx="106" cy="106" r="5" fill="rgba(255,138,61,.3)"/>
          <circle cx="134" cy="106" r="5" fill="rgba(255,138,61,.3)"/>
          <!-- wings -->
          <ellipse cx="88" cy="145" rx="14" ry="8" fill="#FFB800" transform="rotate(-20 88 145)"/>
          <ellipse cx="152" cy="138" rx="14" ry="8" fill="#FFB800" transform="rotate(25 152 138)"/>
          <!-- feet -->
          <ellipse cx="112" cy="168" rx="9" ry="4" fill="#FF8A3D"/>
          <ellipse cx="128" cy="168" rx="9" ry="4" fill="#FF8A3D"/>
          <text x="88" y="180" font-size="9" fill="rgba(255,255,255,.6)" font-family="Noto Sans KR">마이덕</text>

          <!-- Fantasy Adventurer -->
          <path d="M225 140 Q208 155 210 168 Q225 175 255 175 Q272 165 270 155 Z" fill="#5b21b6"/>
          <rect x="222" y="136" width="44" height="60" rx="8" fill="#7c3aed"/>
          <ellipse cx="220" cy="138" rx="10" ry="7" fill="#8b5cf6"/>
          <ellipse cx="266" cy="138" rx="10" ry="7" fill="#8b5cf6"/>
          <circle cx="243" cy="108" r="22" fill="#fbbf24"/>
          <path d="M222 100 Q226 84 243 81 Q260 84 264 100" fill="#1a1a1a"/>
          <circle cx="235" cy="108" r="4" fill="#fff"/><circle cx="236" cy="108" r="2.5" fill="#1a1a1a"/>
          <circle cx="251" cy="108" r="4" fill="#fff"/><circle cx="252" cy="108" r="2.5" fill="#1a1a1a"/>
          <line x1="231" y1="101" x2="239" y2="103" stroke="#1a1a1a" stroke-width="2" stroke-linecap="round"/>
          <line x1="247" y1="103" x2="255" y2="101" stroke="#1a1a1a" stroke-width="2" stroke-linecap="round"/>
          <path d="M238 116 Q243 120 248 116" stroke="#1a1a1a" stroke-width="1.5" fill="none"/>
          <rect x="268" y="122" width="4" height="52" rx="2" fill="#94a3b8"/>
          <rect x="265" y="130" width="10" height="3" rx="1.5" fill="#6b7280"/>
          <text x="213" y="180" font-size="9" fill="rgba(255,255,255,.6)" font-family="Noto Sans KR">판타지 모험가</text>

          <!-- Anime Character -->
          <rect x="362" y="138" width="50" height="62" rx="8" fill="#dbeafe"/>
          <rect x="362" y="138" width="18" height="62" rx="6" fill="#1d4ed8"/>
          <rect x="394" y="138" width="18" height="62" rx="6" fill="#1d4ed8"/>
          <path d="M387 138 L381 155 L387 168 L393 155Z" fill="#ef4444"/>
          <circle cx="387" cy="106" r="22" fill="#fde68a"/>
          <path d="M365 98 Q369 82 387 79 Q405 82 409 98" fill="#f97316"/>
          <path d="M363 101 Q359 90 364 84 Q361 95 366 101Z" fill="#f97316"/>
          <path d="M411 101 Q415 90 410 84 Q413 95 409 101Z" fill="#f97316"/>
          <ellipse cx="379" cy="105" rx="6" ry="8" fill="#fff"/>
          <ellipse cx="379" cy="106" rx="4" ry="6" fill="#1e40af"/>
          <ellipse cx="379" cy="107" rx="2.5" ry="4" fill="#1a1a1a"/>
          <ellipse cx="377.8" cy="103.8" rx="1.3" ry="1.5" fill="#fff"/>
          <ellipse cx="395" cy="105" rx="6" ry="8" fill="#fff"/>
          <ellipse cx="395" cy="106" rx="4" ry="6" fill="#1e40af"/>
          <ellipse cx="395" cy="107" rx="2.5" ry="4" fill="#1a1a1a"/>
          <ellipse cx="393.8" cy="103.8" rx="1.3" ry="1.5" fill="#fff"/>
          <circle cx="371" cy="113" r="5" fill="rgba(252,165,165,.5)"/>
          <circle cx="403" cy="113" r="5" fill="rgba(252,165,165,.5)"/>
          <path d="M381 118 Q387 123 393 118" stroke="#1a1a1a" stroke-width="1.5" fill="none" stroke-linecap="round"/>
          <text x="355" y="180" font-size="9" fill="rgba(255,255,255,.6)" font-family="Noto Sans KR">애니 캐릭터</text>

          <!-- Idol -->
          <path d="M478 140 Q464 150 462 168 Q478 177 528 168 Q527 150 508 140Z" fill="#ec4899"/>
          <rect x="478" y="138" width="38" height="66" rx="10" fill="#f472b6"/>
          <circle cx="493" cy="153" r="1.8" fill="#fde68a" opacity=".9"/>
          <circle cx="504" cy="160" r="1.5" fill="#fde68a" opacity=".9"/>
          <path d="M490 147 L491.5 151 L496 151 L492.5 153.5 L494 158 L490 155.5 L486 158 L487.5 153.5 L484 151 L488.5 151Z" fill="#fde68a" opacity=".7"/>
          <circle cx="493" cy="106" r="22" fill="#fddcb5"/>
          <path d="M472 112 Q470 89 493 84 Q516 89 514 112" fill="#9333ea"/>
          <path d="M470 115 Q462 100 467 88 Q469 104 473 115Z" fill="#9333ea"/>
          <path d="M516 115 Q524 100 519 88 Q517 104 513 115Z" fill="#9333ea"/>
          <circle cx="477" cy="88" r="4" fill="#fde68a"/>
          <ellipse cx="484" cy="106" rx="6" ry="7" fill="#fff"/>
          <ellipse cx="484" cy="107" rx="3.5" ry="5" fill="#9333ea"/>
          <ellipse cx="484" cy="108" rx="2.5" ry="3.5" fill="#1a1a1a"/>
          <ellipse cx="482.8" cy="104.5" rx="1.2" ry="1.4" fill="#fff"/>
          <ellipse cx="502" cy="106" rx="6" ry="7" fill="#fff"/>
          <ellipse cx="502" cy="107" rx="3.5" ry="5" fill="#9333ea"/>
          <ellipse cx="502" cy="108" rx="2.5" ry="3.5" fill="#1a1a1a"/>
          <ellipse cx="500.8" cy="104.5" rx="1.2" ry="1.4" fill="#fff"/>
          <path d="M487 118 Q493 122 499 118" stroke="#be185d" stroke-width="1.5" fill="none" stroke-linecap="round"/>
          <circle cx="475" cy="113" r="5" fill="rgba(236,72,153,.3)"/>
          <circle cx="511" cy="113" r="5" fill="rgba(236,72,153,.3)"/>
          <rect x="512" y="126" width="4" height="32" rx="2" fill="#9ca3af"/>
          <circle cx="514" cy="126" r="5.5" fill="#4b5563"/>
          <circle cx="514" cy="126" r="3.5" fill="#1f2937"/>
          <text x="462" y="180" font-size="9" fill="rgba(255,255,255,.6)" font-family="Noto Sans KR">뮤직 아이돌</text>

          <!-- sparkles -->
          <text x="185" y="70" font-size="12" opacity=".6">✦</text>
          <text x="310" y="58" font-size="8" opacity=".5">✦</text>
          <text x="440" y="65" font-size="10" opacity=".5">✦</text>
          <text x="558" y="72" font-size="12" opacity=".5">✦</text>
        </svg>
      </div>
    </div>

    <!-- 공식 브랜드 룸 칩 -->
    <div class="brand-row">
      <div class="brand-row-title">🏠 공식 IP 브랜드 룸 &nbsp;<span style="color:#d1fae5;background:#d1fae5;width:1px;display:inline-block;height:10px;margin:0 2px;vertical-align:middle;"></span></div>
      <div class="brand-chips">
        <div class="brand-chip"><div class="bci" style="background:#dbeafe;">🎮</div>닌텐도<span class="new">N</span></div>
        <div class="brand-chip"><div class="bci" style="background:#fef3c7;">⚡</div>포켓몬</div>
        <div class="brand-chip"><div class="bci" style="background:#fff7ed;">🏴‍☠️</div>원피스</div>
        <div class="brand-chip"><div class="bci" style="background:#fff0f0;">🍥</div>나루토</div>
        <div class="brand-chip"><div class="bci" style="background:#f5f3ff;">⚔️</div>블리치</div>
        <div class="brand-chip"><div class="bci" style="background:#fef9c3;">🎤</div>YG</div>
        <div class="brand-chip"><div class="bci" style="background:#f0fdf4;">🎵</div>JYP</div>
        <div class="brand-chip"><div class="bci" style="background:#eff6ff;">🎶</div>BIGHIT<span class="new">N</span></div>
        <div class="brand-chip"><div class="bci" style="background:#fce7f3;">🌸</div>SM</div>
      </div>
    </div>

    <!-- 인기글 박스 -->
    <div class="hot-box">
      <div class="hot-box-header">
        <div class="hot-box-title">🔥 AI 청정 인기 게시글 TOP 7</div>
        <div class="hot-box-more">전체보기 ›</div>
      </div>
      <div class="hot-row"><div class="hot-rank rank-1">1</div><span class="pr-cat cat-official" style="flex-shrink:0;font-size:10px;padding:1px 6px;">닌텐도</span><div class="hot-row-title">새로운 업데이트 및 유저 소통방 - Switch2 발표 현장 반응 총정리!</div><div class="hot-row-likes">❤️ 4.2K</div></div>
      <div class="hot-row"><div class="hot-rank rank-2">2</div><span class="pr-cat cat-anime" style="flex-shrink:0;font-size:10px;padding:1px 6px;">원피스</span><div class="hot-row-title">1120화 방영 기념 청정 토크 - 기어5 재등장 논의</div><div class="hot-row-likes">❤️ 3.8K</div></div>
      <div class="hot-row"><div class="hot-rank rank-3">3</div><span class="pr-cat cat-anime" style="flex-shrink:0;font-size:10px;padding:1px 6px;">나루토</span><div class="hot-row-title">명대사 월드컵 결승전 🔥 나루토 vs 사스케 투표 진행 중!</div><div class="hot-row-likes">❤️ 2.9K</div></div>
      <div class="hot-row"><div class="hot-rank rank-n">4</div><span class="pr-cat cat-idol" style="flex-shrink:0;font-size:10px;padding:1px 6px;">아이돌</span><div class="hot-row-title">실시간 유해 비방 차단 완료 ✅ 안전한 팬 응원방</div><div class="hot-row-likes">❤️ 2.1K</div></div>
      <div class="hot-row"><div class="hot-rank rank-n">5</div><span class="pr-cat cat-info" style="flex-shrink:0;font-size:10px;padding:1px 6px;">정보</span><div class="hot-row-title">AI 일정 관리로 이번 달 덕질 스케줄 한눈에 보기</div><div class="hot-row-likes">❤️ 1.7K</div></div>
      <div class="hot-row"><div class="hot-rank rank-n">6</div><span class="pr-cat cat-event" style="flex-shrink:0;font-size:10px;padding:1px 6px;">이벤트</span><div class="hot-row-title">굿즈 상생 스토어 한정판 구매 인증 🛍️ 이번 주 마감!</div><div class="hot-row-likes">❤️ 1.4K</div></div>
      <div class="hot-row"><div class="hot-rank rank-n">7</div><span class="pr-cat cat-game" style="flex-shrink:0;font-size:10px;padding:1px 6px;">게이밍</span><div class="hot-row-title">포켓몬 스칼렛 바이올렛 2 루머 모음 - 공식 확인된 것만</div><div class="hot-row-likes">❤️ 1.1K</div></div>
    </div>

    <!-- 게시판 테이블 -->
    <div class="board-tabs">
      <div class="board-tab-left">
        <div class="board-tab active">전체글</div>
        <div class="board-tab">공지</div>
        <div class="board-tab">자유게시판</div>
        <div class="board-tab">🎌 애니</div>
        <div class="board-tab">🎤 아이돌</div>
        <div class="board-tab">🎮 게이밍</div>
      </div>
      <button class="board-write">✏️ 글쓰기</button>
    </div>

    <div class="post-table">
      <div class="post-table-head">
        <div class="pth">분류</div>
        <div class="pth">제목</div>
        <div class="pth">작성자</div>
        <div class="pth">날짜</div>
        <div class="pth" style="text-align:right;">조회</div>
      </div>

      <!-- 공지 -->
      <div class="post-row notice">
        <div><span class="pr-cat cat-notice">공지</span></div>
        <div class="pr-title-wrap"><span class="pr-title">[필독] MY DUCK 커뮤니티 이용 규칙 및 AI 청정 가이드라인 안내</span></div>
        <div class="pr-author">운영팀</div>
        <div class="pr-date">06.01</div>
        <div class="pr-views">32.1K</div>
      </div>
      <div class="post-row notice">
        <div><span class="pr-cat cat-notice">공지</span></div>
        <div class="pr-title-wrap"><span class="pr-title">[안내] 6월 공식 브랜드 룸 이벤트 일정 총정리 🎉</span></div>
        <div class="pr-author">운영팀</div>
        <div class="pr-date">06.03</div>
        <div class="pr-views">18.4K</div>
      </div>

      <!-- 일반 글 -->
      <div class="post-row">
        <div><span class="pr-cat cat-official">닌텐도</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">Nintendo Switch 2 공식 발표 🎮 유저 소통 이벤트 사전 신청 안내</span>
          <span class="pr-new">N</span>
          <span class="pr-ai">🛡️</span>
        </div>
        <div class="pr-author">Nintendo_KR</div>
        <div class="pr-date">2시간 전</div>
        <div class="pr-views">18.4K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-anime">원피스</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">원피스 1120화 방영 기념 🏴‍☠️ 기어5 재등장 청정 토크 &lt;스포 없음&gt;</span>
          <span class="pr-new">N</span>
          <span class="pr-ai">🛡️</span>
          <span class="pr-img-ico">🖼️</span>
        </div>
        <div class="pr-author">루피짱팬</div>
        <div class="pr-date">5시간 전</div>
        <div class="pr-views">14.2K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-anime">나루토</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">명대사 월드컵 결승전 🔥 나루토 vs 사스케 — 지금 바로 투표하세요!</span>
          <span class="pr-ai">🛡️</span>
        </div>
        <div class="pr-author">나루토팬클럽</div>
        <div class="pr-date">5시간 전</div>
        <div class="pr-views">22.1K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-idol">아이돌</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">✅ 이번 주 유해 비방 847건 차단 완료 — 안심하고 응원하세요 🎉</span>
          <span class="pr-ai">🛡️</span>
        </div>
        <div class="pr-author">아이돌응원단장</div>
        <div class="pr-date">6시간 전</div>
        <div class="pr-views">9.7K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-info">정보</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">AI 일정 관리 기능으로 이번 달 덕질 스케줄 공유 (6월 이벤트 총정리)</span>
          <span class="pr-ai">🛡️</span>
          <span class="pr-img-ico">🖼️</span>
        </div>
        <div class="pr-author">덕질스케줄러</div>
        <div class="pr-date">8시간 전</div>
        <div class="pr-views">7.3K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-event">이벤트</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">굿즈 상생 스토어 한정판 구매 인증 모음 🛍️ 이번 주 일요일 마감!</span>
          <span class="pr-img-ico">🖼️</span>
          <span class="pr-ai">🛡️</span>
        </div>
        <div class="pr-author">굿즈헌터</div>
        <div class="pr-date">11시간 전</div>
        <div class="pr-views">5.2K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-game">게이밍</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">포켓몬 스칼렛 바이올렛 후속작 루머 모음 — 공식 확인된 정보만 정리</span>
          <span class="pr-ai">🛡️</span>
        </div>
        <div class="pr-author">포켓마스터</div>
        <div class="pr-date">13시간 전</div>
        <div class="pr-views">6.8K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-anime">블리치</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">천년혈전 완결 후기 — 이치고 결말에 대한 솔직한 감상 (스포 포함)</span>
          <span class="pr-ai">🛡️</span>
        </div>
        <div class="pr-author">소울리퍼</div>
        <div class="pr-date">1일 전</div>
        <div class="pr-views">4.1K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-idol">아이돌</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">BTS 새 앨범 트랙리스트 공개 💜 D-3 카운트다운 응원글</span>
          <span class="pr-new">N</span>
          <span class="pr-ai">🛡️</span>
        </div>
        <div class="pr-author">ARMY0704</div>
        <div class="pr-date">1일 전</div>
        <div class="pr-views">11.2K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-free">자유</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">여러분이 처음 덕질 시작하게 된 계기가 뭔가요? 😊 모아봐요</span>
          <span class="pr-ai">🛡️</span>
        </div>
        <div class="pr-author">청정덕후</div>
        <div class="pr-date">1일 전</div>
        <div class="pr-views">3.4K</div>
      </div>

      <div class="post-row">
        <div><span class="pr-cat cat-game">게이밍</span></div>
        <div class="pr-title-wrap">
          <span class="pr-title">닌텐도 오닐라인 6월 무료 게임 목록 — 마리오카트 추가 확인</span>
          <span class="pr-ai">🛡️</span>
          <span class="pr-img-ico">🖼️</span>
        </div>
        <div class="pr-author">게임정보봇</div>
        <div class="pr-date">2일 전</div>
        <div class="pr-views">8.9K</div>
      </div>

    </div>

    <!-- 페이지네이션 -->
    <div class="pagination">
      <button class="pg-btn">«</button>
      <button class="pg-btn">‹</button>
      <button class="pg-btn active">1</button>
      <button class="pg-btn">2</button>
      <button class="pg-btn">3</button>
      <button class="pg-btn">4</button>
      <button class="pg-btn">5</button>
      <button class="pg-btn">›</button>
      <button class="pg-btn">»</button>
    </div>

  </div>

  <!-- ═══ 오른쪽 사이드바 ═══ -->
  <div class="right-col">

    <!-- 커뮤니티 통계 -->
    <div class="stats-box">
      <div class="stats-box-header">📊 커뮤니티 현황</div>
      <div class="stats-grid">
        <div class="stat-cell"><div class="n" style="color:#f97316;">284K</div><div class="l">전체 회원</div></div>
        <div class="stat-cell"><div class="n" style="color:#22c55e;">5.2K</div><div class="l">오늘 게시글</div></div>
        <div class="stat-cell"><div class="n" style="color:#3b82f6;">3.8M</div><div class="l">누적 게시글</div></div>
        <div class="stat-cell"><div class="n" style="color:#a855f7;">156개</div><div class="l">브랜드 룸</div></div>
      </div>
      <div class="online-bar">
        <div class="online-dot"></div>
        <div class="online-text">지금 <strong>3,847명</strong> 접속 중</div>
      </div>
    </div>

    <!-- 이번 달 이벤트 -->
    <div class="event-box">
      <div class="event-box-header">
        📅 이벤트 캘린더
        <span class="event-more">전체보기 ›</span>
      </div>
      <div class="event-item">
        <div class="event-date-badge"><div class="m">6월</div><div class="d">7</div></div>
        <div class="event-info">
          <div class="ename">포켓몬 팬미팅 행사</div>
          <div class="esub">서울 공식 홀</div>
          <span class="etag">닌텐도</span>
        </div>
      </div>
      <div class="event-item">
        <div class="event-date-badge"><div class="m">6월</div><div class="d">10</div></div>
        <div class="event-info">
          <div class="ename">BTS 새 앨범 발매일</div>
          <div class="esub">BIGHIT MUSIC</div>
          <span class="etag">아이돌</span>
        </div>
      </div>
      <div class="event-item">
        <div class="event-date-badge"><div class="m">6월</div><div class="d">14</div></div>
        <div class="event-info">
          <div class="ename">원피스 1주년 팝업</div>
          <div class="esub">홍대 팝업스토어</div>
          <span class="etag">애니</span>
        </div>
      </div>
      <div class="event-item">
        <div class="event-date-badge"><div class="m">6월</div><div class="d">21</div></div>
        <div class="event-info">
          <div class="ename">K-POP 팬 굿즈마켓</div>
          <div class="esub">COEX 이벤트홀</div>
          <span class="etag">이벤트</span>
        </div>
      </div>
      <div class="event-item">
        <div class="event-date-badge"><div class="m">6월</div><div class="d">28</div></div>
        <div class="event-info">
          <div class="ename">MY DUCK 커뮤니티 페스타</div>
          <div class="esub">온오프라인 병행</div>
          <span class="etag">커뮤니티</span>
        </div>
      </div>
    </div>

    <!-- 카테고리 랭킹 -->
    <div class="rank-box">
      <div class="rank-box-header">🏆 카테고리 인기 순위</div>
      <div class="rank-item"><div class="ri-rank top">1</div><div class="ri-icon" style="background:#eff6ff;">🔵</div><div class="ri-name">BIGHIT MUSIC</div><div class="ri-count">5.8K</div></div>
      <div class="rank-item"><div class="ri-rank top">2</div><div class="ri-icon" style="background:#fff7ed;">🏴‍☠️</div><div class="ri-name">원피스</div><div class="ri-count">4.2K</div></div>
      <div class="rank-item"><div class="ri-rank top">3</div><div class="ri-icon" style="background:#fff0f0;">🍥</div><div class="ri-name">나루토</div><div class="ri-count">3.1K</div></div>
      <div class="rank-item"><div class="ri-rank">4</div><div class="ri-icon" style="background:#f0fdf4;">🟢</div><div class="ri-name">JYP Entertainment</div><div class="ri-count">3.4K</div></div>
      <div class="rank-item"><div class="ri-rank">5</div><div class="ri-icon" style="background:#fef9c3;">🟡</div><div class="ri-name">YG Entertainment</div><div class="ri-count">2.7K</div></div>
      <div class="rank-item"><div class="ri-rank">6</div><div class="ri-icon" style="background:#dbeafe;">🎮</div><div class="ri-name">Nintendo Room</div><div class="ri-count">2.1K</div></div>
      <div class="rank-item"><div class="ri-rank">7</div><div class="ri-icon" style="background:#f0fdf4;">🎨</div><div class="ri-name">팬아트</div><div class="ri-count">2.0K</div></div>
    </div>

    <!-- 홍보 배너 -->
    <div class="side-banner">
      <div class="sb-title">🦆 MY DUCK PRO</div>
      <div class="sb-sub">AI 일정 알림, 전용 뱃지, 브랜드 룸 우선 입장 혜택을 누리세요.</div>
      <button class="sb-btn">PRO 멤버십 알아보기</button>
    </div>

  </div>

</div>

<!-- 푸터 -->
<div class="footer">
  <div class="footer-inner">
    <div class="footer-logo">🦆 MY DUCK</div>
    <div class="footer-links">
      <a href="#">회사 소개</a>
      <a href="#">이용약관</a>
      <a href="#">개인정보처리방침</a>
      <a href="#">고객센터</a>
      <a href="#">광고 문의</a>
    </div>
    <div class="footer-badges">
      <div class="footer-badge">⚡ Powered by Flutter</div>
      <div class="footer-badge">🛡️ AI Security v4.2</div>
      <div class="footer-badge">✅ 청정 커뮤니티 인증</div>
    </div>
    <div class="footer-copy">© 2026 MY DUCK Inc. All rights reserved.</div>
  </div>
</div>

</body>
</html>
HTMLEOF
echo "done"
