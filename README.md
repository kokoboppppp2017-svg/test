<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>쇼호스트 김쇼호 | 포트폴리오</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css">
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+KR:wght@600&display=swap" rel="stylesheet">
<style>

        /* ===========================
           ROOT & RESET
        =========================== */
      :root {
    --bg-primary: #FAFAF8;
    --bg-secondary: #F5F0EB;
    --bg-card: #FFFFFF;
    --text-primary: #1A1A1A;
    --text-secondary: #5A5A5A;
    --text-muted: #9A9A9A;
    --rose-gold: #C9956C;
    --burgundy: #8B2E4A;
    --accent: #C9956C;
    --border: #E8E0D8;
    --shadow: rgba(139, 46, 74, 0.08);

    /* 아래가 핵심! 빠져있던 변수들 */
    --bg: #FAFAF8;
    --bg2: #F5F0EB;
    --card: #FFFFFF;
    --text: #1A1A1A;
    --muted: #5A5A5A;
    --muted2: #9A9A9A;
    --accent2: #8B2E4A;
    --kakao: #FEE500;
    --radius: 16px;
    --radius-sm: 10px;
}

        * { box-sizing: border-box; margin: 0; padding: 0; }
        html { scroll-behavior: smooth; }

        body {
            font-family: "Pretendard", sans-serif;
            background: var(--bg);
            color: var(--text);
            overflow-x: hidden;
            word-break: keep-all;
        }

        .container {
            width: 100%;
            max-width: 1024px;
            margin: 0 auto;
            padding: 0 20px;
        }

        section { padding: 64px 0; }

        .section-label {
            display: inline-block;
            font-size: 11px;
            font-weight: 800;
            letter-spacing: 0.18em;
            text-transform: uppercase;
            color: var(--accent2);
            background: rgba(192, 132, 252, 0.1);
            border: 1px solid rgba(192, 132, 252, 0.2);
            padding: 4px 12px;
            border-radius: 99px;
            margin-bottom: 14px;
        }

        h2 {
            font-size: 24px;
            font-weight: 900;
            line-height: 1.25;
            margin-bottom: 8px;
        }

        .section-sub {
            font-size: 14px;
            color: var(--muted);
            line-height: 1.7;
            margin-bottom: 32px;
        }


        /* ===========================
           HEADER
        =========================== */
        header {
            position: sticky;
            top: 0;
            z-index: 200;
            background: rgba(250, 250, 248, 0.92);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(139, 46, 74, 0.12);
        }

        .header-inner {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 56px;
            gap: 32px;
        }

        .nav a {
            text-decoration: none;
            color: var(--muted);
            font-size: 14px;
            font-weight: 600;
            letter-spacing: 0.02em;
            transition: color 0.2s;
            padding: 4px 0;
            position: relative;
        }

        .nav a::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent);
            border-radius: 2px;
            transition: width 0.25s;
        }

        .nav a:hover { color: var(--text); }
        .nav a:hover::after { width: 100%; }

        .nav {
            display: flex;
            gap: 28px;
        }


        /* ===========================
           HERO
        =========================== */
        .hero {
    padding-top: 48px;
    padding-bottom: 64px;
    position: relative;
    overflow: hidden;
    background: linear-gradient(160deg, #FAFAF8 0%, #F5EDE6 50%, #F0E4DC 100%); /* 이 줄 추가 */
}
        /* 배경 그라디언트 오브 */
        .hero::before {
            content: '';
            position: absolute;
            top: -120px;
            left: 50%;
            transform: translateX(-50%);
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(201,149,108,0.12) 0%, transparent 70%);
            pointer-events: none;
        }
        .hero-inner {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 36px;
            position: relative;
        }

        /* 슬라이더 */
        .slider-wrap {
    width: 70%;
    max-width: 300px;    /* 이 줄 추가 */
    aspect-ratio: 3/4;
    border-radius: 20px;
    overflow: hidden;
    position: relative;
    box-shadow: 0 0 0 1px rgba(124,92,252,0.3),
                0 24px 60px rgba(0,0,0,0.5);
    flex-shrink: 0;
}
        .slider-track {
            display: flex;
            width: 200%;
            height: 100%;
            animation: heroSlide 10s infinite ease-in-out;
        }

        .slider-track img {
            width: 50%;
            height: 100%;
            object-fit: cover;
        }

        @keyframes heroSlide {
            0%, 42%   { transform: translateX(0); }
            50%, 92%  { transform: translateX(-50%); }
            100%      { transform: translateX(0); }
        }

        /* 텍스트 영역 */
        .hero-text {
            text-align: center;
        }

        .hero-role {
            font-size: 12px;
            font-weight: 700;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            color: var(--accent2);
            margin-bottom: 12px;
        }

        .hero-name {
            font-size: clamp(2.8rem, 10vw, 4.5rem);
            font-weight: 900;
            line-height: 1;
            letter-spacing: -0.02em;
           background: linear-gradient(90deg, #8B2E4A 0%, #C9956C 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 16px;
            font-family: 'Noto Serif KR', serif;
        }

        .hero-tagline {
            font-size: 15px;
            color: var(--muted);
            line-height: 1.7;
            max-width: 360px;
            margin: 0 auto 24px;
        }

        .hero-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            justify-content: center;
        }

        .badge {
            background: rgba(124,92,252,0.12);
            border: 1px solid rgba(124,92,252,0.25);
            color: var(--accent2);
            padding: 5px 13px;
            border-radius: 99px;
            font-size: 12px;
            font-weight: 700;
        }


        /* ===========================
           STATS (강점 대체)
        =========================== */
        #strengths {
            background: var(--bg2);
            border-top: 1px solid rgba(255,255,255,0.05);
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        .stats-header { text-align: center; margin-bottom: 36px; }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 12px;
        }

        .stat-card {
            background: var(--card);
            border: 1px solid rgba(255,255,255,0.06);
            border-radius: var(--radius);
            padding: 20px;
            text-align: center;
            position: relative;
            overflow: hidden;
            transition: transform 0.2s, border-color 0.2s;
        }

        .stat-card::before {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0;
            height: 2px;
            background: linear-gradient(90deg, var(--accent), var(--accent2));
            opacity: 0;
            transition: opacity 0.2s;
        }

        .stat-card:hover { transform: translateY(-3px); border-color: rgba(124,92,252,0.3); }
        .stat-card:hover::before { opacity: 1; }

        .stat-number {
            font-size: 2rem;
            font-weight: 900;
            background: linear-gradient(135deg, #fff, var(--accent2));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1;
            margin-bottom: 6px;
        }

        .stat-unit {
            font-size: 1rem;
        }

        .stat-label {
            font-size: 12px;
            font-weight: 700;
            color: var(--muted);
            margin-bottom: 4px;
        }

        .stat-desc {
            font-size: 11px;
            color: var(--muted2);
            line-height: 1.5;
        }

        /* 넓은 카드 (한 줄 전체) */
        .stat-card.wide {
            grid-column: 1 / -1;
            display: flex;
            align-items: center;
            gap: 20px;
            text-align: left;
            padding: 20px 24px;
        }

        .stat-card.wide .stat-number {
            font-size: 2.2rem;
            flex-shrink: 0;
        }

        .stat-card.wide .stat-body {}


        /* ===========================
           CAREER
        =========================== */
        #career { }

        .career-header { text-align: center; margin-bottom: 32px; }

        .career-grid {
            display: grid;
            gap: 12px;
        }

        .career-block {
            background: var(--card);
            border: 1px solid rgba(255,255,255,0.06);
            border-radius: var(--radius);
            padding: 22px;
        }

        .career-block-title {
            font-size: 11px;
            font-weight: 800;
            letter-spacing: 0.15em;
            text-transform: uppercase;
            color: var(--accent2);
            margin-bottom: 16px;
        }

        .career-list li {
            list-style: none;
            display: flex;
            gap: 14px;
            padding: 12px 0;
            border-bottom: 1px solid rgba(255,255,255,0.05);
            align-items: flex-start;
        }

        .career-list li:last-child { border-bottom: none; padding-bottom: 0; }
        .career-list li:first-child { padding-top: 0; }

        .career-year {
            font-size: 12px;
            font-weight: 700;
            color: var(--accent2);
            white-space: nowrap;
            margin-top: 2px;
            min-width: 80px;
        }

        .career-desc strong {
            display: block;
            font-size: 14px;
            font-weight: 700;
            margin-bottom: 2px;
        }

        .career-desc span {
            font-size: 12px;
            color: var(--muted);
        }

        .achieve-list li {
            list-style: none;
            display: flex;
            align-items: flex-start;
            gap: 10px;
            padding: 10px 0;
            border-bottom: 1px solid rgba(255,255,255,0.05);
            font-size: 14px;
            line-height: 1.5;
            color: var(--muted);
        }

        .achieve-list li:last-child { border-bottom: none; padding-bottom: 0; }
        .achieve-list li:first-child { padding-top: 0; }

        .achieve-list li::before {
            content: '✦';
            color: var(--accent2);
            font-size: 10px;
            margin-top: 4px;
            flex-shrink: 0;
        }


        /* ===========================
           VIDEOS
        =========================== */
        #videos { background: var(--bg2); }

        .videos-header { text-align: center; margin-bottom: 28px; }

        /* 모바일: 가로 스크롤 */
        .videos-scroll {
            display: flex;
            gap: 12px;
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            padding-bottom: 12px;
            -webkit-overflow-scrolling: touch;
            scrollbar-width: none;
        }

        .videos-scroll::-webkit-scrollbar { display: none; }

        .vcard {
    flex: 0 0 65vw;
    max-width: 240px;    /* 280px → 240px */
    scroll-snap-align: start;
    border-radius: var(--radius);
    overflow: hidden;
    background: var(--card);
    border: 1px solid rgba(255,255,255,0.06);
    box-shadow: 0 8px 30px rgba(0,0,0,0.4);
}
        /* 9:16 비율 (네이버 쇼핑라이브 세로형) */
        .video-frame {
            position: relative;
            width: 100%;
            aspect-ratio: 9 / 16;
            background: #000;
        }

        .video-frame iframe {
            position: absolute;
            inset: 0;
            width: 100%;
            height: 100%;
            border: 0;
        }

        .vcard-info {
            padding: 12px 14px;
        }

        .vcard-category {
            font-size: 10px;
            font-weight: 700;
            letter-spacing: 0.12em;
            color: var(--accent2);
            text-transform: uppercase;
            margin-bottom: 4px;
        }

        .vcard-title {
            font-size: 13px;
            font-weight: 700;
            color: var(--text);
        }


        /* ===========================
           GALLERY
        =========================== */
        #gallery { }

        .gallery-header { text-align: center; margin-bottom: 24px; }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 8px;
        }

        .gallery-item {
            border-radius: var(--radius-sm);
            overflow: hidden;
            aspect-ratio: 3/4;
            background: var(--card);
            position: relative;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s;
            display: block;
        }

        .gallery-item:hover img { transform: scale(1.05); }

        /* 첫 번째 아이템을 크게 */
  /* 첫 번째 아이템을 크게 */
.gallery-item:first-child {
    grid-column: 1 / -1;
    aspect-ratio: 4/3;
}

/* 마지막 아이템 모바일에서만 꽉 채우기 */
@media (max-width: 768px) {
    .gallery-item:last-child {
        grid-column: 1 / -1;
        aspect-ratio: 4/3;
    }
}
        /* ===========================
           CONTACT  (완전 새 디자인)
        =========================== */
        #contact {
            background: var(--bg2);
            border-top: 1px solid rgba(255,255,255,0.05);
            padding-bottom: 80px;
        }

        .contact-header { text-align: center; margin-bottom: 36px; }

        .contact-wrap {
    display: flex;
    flex-direction: column;
    gap: 12px;
    max-width: 600px;
    margin: 0 auto;
}
        /* 큰 CTA 카카오 버튼 */
        .contact-cta {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            gap: 12px;
            background: linear-gradient(135deg, #FDF6F0, #F5EDE6);
border: 1px solid rgba(139, 46, 74, 0.15);
            padding: 24px;
        }

        .contact-cta-text p {
            font-size: 18px;
            font-weight: 900;
            margin-bottom: 4px;
        }

        .contact-cta-text span {
            font-size: 13px;
            color: var(--muted);
        }

        .btn-kakao {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: var(--kakao);
            color: #191919;
            text-decoration: none;
            font-weight: 800;
            font-size: 14px;
            padding: 13px 20px;
            border-radius: var(--radius-sm);
            width: 100%;
            justify-content: center;
            transition: opacity 0.2s, transform 0.15s;
        }

        .btn-kakao:hover { opacity: 0.9; transform: translateY(-1px); }

        .btn-kakao svg {
            width: 20px;
            height: 20px;
            flex-shrink: 0;
        }

        /* 이메일 카드 */
        .contact-email {
            display: flex;
            align-items: center;
            gap: 14px;
            background: var(--card);
            border: 1px solid rgba(255,255,255,0.06);
            border-radius: var(--radius);
            padding: 18px 20px;
            text-decoration: none;
            transition: border-color 0.2s, transform 0.15s;
        }

        .contact-email:hover {
            border-color: rgba(124,92,252,0.35);
            transform: translateY(-2px);
        }

        .contact-email-icon {
            width: 40px;
            height: 40px;
            border-radius: 10px;
            background: rgba(124,92,252,0.12);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .contact-email-icon svg {
            width: 20px;
            height: 20px;
            color: var(--accent2);
        }

        .contact-email-text strong {
            display: block;
            font-size: 13px;
            font-weight: 700;
            color: var(--text);
        }

        .contact-email-text span {
            font-size: 12px;
            color: var(--muted);
        }

        .contact-email-arrow {
            margin-left: auto;
            color: var(--muted2);
        }

        /* SNS 2개 나란히 */
        .contact-sns-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
        }

        .sns-card {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            background: var(--card);
            border: 1px solid rgba(255,255,255,0.06);
            border-radius: var(--radius);
            padding: 20px 16px;
            text-decoration: none;
            transition: border-color 0.2s, transform 0.15s;
        }

        .sns-card:hover {
            transform: translateY(-3px);
        }

        .sns-card.instagram:hover { border-color: rgba(225,48,108,0.4); }
        .sns-card.youtube:hover { border-color: rgba(255,0,0,0.4); }

        .sns-icon {
            width: 44px;
            height: 44px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .sns-icon.ig { background: linear-gradient(135deg, #f9ce34, #ee2a7b, #6228d7); }
        .sns-icon.yt { background: #ff0000; }

        .sns-icon svg {
            width: 24px;
            height: 24px;
            fill: white;
        }

        .sns-card-label {
            font-size: 13px;
            font-weight: 800;
            color: var(--text);
        }

        .sns-card-sub {
            font-size: 11px;
            color: var(--muted);
        }


        /* ===========================
           FOOTER
        =========================== */
footer {
    text-align: center;
    padding: 24px 20px;
    background: #F5F0EB;        /* ← 이 줄 추가! */
    border-top: 1px solid rgba(139, 46, 74, 0.12);
    font-size: 12px;
    color: var(--muted2);
}


        /* ===========================
           PC (768px+)
        =========================== */
        @media (min-width: 768px) {
            section { padding: 96px 0; }

            h2 { font-size: 32px; }

            /* Hero PC */
            .hero-inner {
                flex-direction: row;
                align-items: center;
                gap: 60px;
            }

            .hero-text {
                text-align: left;
                flex: 1;
            }

            .hero-badges { justify-content: flex-start; }
            .hero-tagline { margin: 0 0 24px; }

            .slider-wrap {
    width: 260px;
    order: 2;
    max-width: none;
}
            /* Stats PC */
            .stats-grid {
                grid-template-columns: repeat(4, 1fr);
            }

            .stat-card.wide {
                grid-column: auto;
                flex-direction: column;
                text-align: center;
                gap: 8px;
            }

            /* Career PC */
            .career-grid {
                grid-template-columns: 1fr 1fr;
            }

            /* Videos PC: 그리드 */
            .videos-scroll {
                display: grid;
                grid-template-columns: repeat(4, 1fr);
                overflow-x: visible;
                padding-bottom: 0;
            }

            .vcard {
                flex: none;
                max-width: none;
            }

            /* Gallery PC */
            .gallery-grid {
                grid-template-columns: repeat(4, 1fr);
            }

            .gallery-item:first-child {
                grid-column: auto;
                aspect-ratio: 3/4;
            }

            /* Contact PC */
            .contact-cta {
                flex-direction: row;
                align-items: center;
            }

            .contact-cta-text { flex: 1; }
            .btn-kakao { width: auto; white-space: nowrap; }
        }

    </style>
</head>
<body>

<!-- ======================== HEADER ======================== -->
<header>
    <div class="container header-inner">
        <nav class="nav">
            <a href="#strengths">강점</a>
            <a href="#career">경력</a>
            <a href="#videos">레퍼런스</a>
            <a href="#gallery">갤러리</a>
            <a href="#contact">연락처</a>
        </nav>
    </div>
</header>

<main>

<!-- ======================== HERO ======================== -->
<section class="hero container">
    <div class="hero-inner">

        <div class="slider-wrap">
            <div class="slider-track">
                <img
                    src="profile1.jpg"
                    alt="프로필 사진 1"
                    onerror="this.src='https://placehold.co/600x800/1a1a26/7c5cfc?text=Photo+1'"
                >
                <img
                    src="profile3.jpg"
                    alt="프로필 사진 2"
                    onerror="this.src='https://placehold.co/600x800/1a1a26/c084fc?text=Photo+2'"
                >
            </div>
        </div>

        <div class="hero-text">
            <div class="hero-role">Show Host · Live Commerce</div>
            <div class="hero-name">김쇼호</div>
            <p class="hero-tagline">
                시청자를 구매자로 바꾸는<br>
                한 마디를 압니다.
            </p>
            <div class="hero-badges">
                <span class="badge"># 높은 전환율</span>
                <span class="badge"># 꼼꼼한 상품 분석</span>
                <span class="badge"># 기획 · 연출</span>
                <span class="badge"># 네이버 쇼핑라이브</span>
            </div>
        </div>

    </div>
</section>

<!-- ======================== STRENGTHS (숫자 카드) ======================== -->
<section id="strengths">
    <div class="container">
        <div class="stats-header">
            <div class="section-label">Numbers</div>
            <h2>숫자로 말합니다</h2>
            <p class="section-sub">추상적인 말 대신, 실제 방송에서 만들어낸 결과입니다.</p>
        </div>

        <div class="stats-grid">

            <div class="stat-card">
                <div class="stat-number">15<span class="stat-unit">%+</span></div>
                <div class="stat-label">평균 구매 전환율</div>
                <div class="stat-desc">업계 평균 대비<br>2배 이상 달성</div>
            </div>

            <div class="stat-card">
                <div class="stat-number">320<span class="stat-unit">%</span></div>
                <div class="stat-label">목표 매출 달성</div>
                <div class="stat-desc">N사 뷰티 런칭 방송<br>역대 최고 기록</div>
            </div>

            <div class="stat-card">
                <div class="stat-number">10<span class="stat-unit">만</span></div>
                <div class="stat-label">동시 시청자</div>
                <div class="stat-desc">S사 리빙 라이브<br>단일 방송 달성</div>
            </div>

            <div class="stat-card">
                <div class="stat-number">3<span class="stat-unit">년+</span></div>
                <div class="stat-label">라이브 커머스 경력</div>
                <div class="stat-desc">뷰티 · 패션 · 리빙<br>전 카테고리 경험</div>
            </div>

        </div>
    </div>
</section>

<!-- ======================== CAREER ======================== -->
<section id="career">
    <div class="container">
        <div class="career-header">
            <div class="section-label">Career</div>
            <h2>경력 및 주요 성과</h2>
        </div>

        <div class="career-grid">

            <div class="career-block">
                <div class="career-block-title">Experience</div>
                <ul class="career-list">
                    <li>
                        <div class="career-year">2023 – 현재</div>
                        <div class="career-desc">
                            <strong>네이버 쇼핑라이브</strong>
                            <span>뷰티 · 패션 카테고리 전담 호스트</span>
                        </div>
                    </li>
                    <li>
                        <div class="career-year">2021 – 2023</div>
                        <div class="career-desc">
                            <strong>김쇼호 MCN 라이브 커머스팀</strong>
                            <span>소속 호스트 · 콘텐츠 기획 참여</span>
                        </div>
                    </li>
                    <li>
                        <div class="career-year">2020 – 2021</div>
                        <div class="career-desc">
                            <strong>김쇼호 쇼핑몰 자사 라이브</strong>
                            <span>라이브 커머스 진행 첫 데뷔</span>
                        </div>
                    </li>
                </ul>
            </div>

            <div class="career-block">
                <div class="career-block-title">Achievement</div>
                <ul class="achieve-list">
                    <li>N사 뷰티 브랜드 런칭 방송, 목표 매출 320% 달성</li>
                    <li>S사 리빙 라이브, 동시 시청자 10만 명 돌파</li>
                    <li>F사 패션 시즌오프 방송, 1시간 내 전 상품 완판</li>
                    <li>월 평균 구매 전환율 15% 이상 꾸준히 유지</li>
                    <li>방송 전 직접 상품 사용 후 리뷰 루틴 정착</li>
                </ul>
            </div>

        </div>
    </div>
</section>

<!-- ======================== VIDEOS ======================== -->
<section id="videos">
    <div class="container">
        <div class="videos-header">
            <div class="section-label">Reference</div>
            <h2>레퍼런스 영상</h2>
            <p class="section-sub">실제 방송 화면을 확인해보세요.</p>
        </div>

        <div class="videos-scroll">

            <div class="vcard">
                <div class="video-frame">
                    <iframe
                        src="https://www.youtube.com/embed/VIDEO_ID_1?rel=0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                        allowfullscreen
                    ></iframe>
                </div>
                <div class="vcard-info">
                    <div class="vcard-category">Beauty</div>
                    <div class="vcard-title">뷰티 브랜드 런칭 라이브</div>
                </div>
            </div>

            <div class="vcard">
                <div class="video-frame">
                    <iframe
                        src="https://www.youtube.com/embed/VIDEO_ID_2?rel=0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                        allowfullscreen
                    ></iframe>
                </div>
                <div class="vcard-info">
                    <div class="vcard-category">Fashion</div>
                    <div class="vcard-title">패션 브랜드 시즌 런칭</div>
                </div>
            </div>

            <div class="vcard">
                <div class="video-frame">
                    <iframe
                        src="https://www.youtube.com/embed/VIDEO_ID_3?rel=0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                        allowfullscreen
                    ></iframe>
                </div>
                <div class="vcard-info">
                    <div class="vcard-category">Living</div>
                    <div class="vcard-title">리빙 제품 심층 시연</div>
                </div>
            </div>

            <div class="vcard">
                <div class="video-frame">
                    <iframe
                        src="https://www.youtube.com/embed/VIDEO_ID_4?rel=0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                        allowfullscreen
                    ></iframe>
                </div>
                <div class="vcard-info">
                    <div class="vcard-category">Digital</div>
                    <div class="vcard-title">가전 제품 완전 분석</div>
                </div>
            </div>

        </div>
    </div>
</section>

<!-- ======================== GALLERY ======================== -->
<section id="gallery">
    <div class="container">
        <div class="gallery-header">
            <div class="section-label">Gallery</div>
            <h2>갤러리</h2>
        </div>

        <div class="gallery-grid">
            <div class="gallery-item">
                <img src="gallery1.jpg" alt="갤러리" onerror="this.src='https://placehold.co/800x600/1a1a26/7c5cfc?text=1'">
            </div>
            <div class="gallery-item">
                <img src="gallery2.jpg" alt="갤러리" onerror="this.src='https://placehold.co/600x800/1a1a26/c084fc?text=2'">
            </div>
            <div class="gallery-item">
                <img src="gallery3.jpg" alt="갤러리" onerror="this.src='https://placehold.co/600x800/1a1a26/7c5cfc?text=3'">
            </div>
            <div class="gallery-item">
                <img src="gallery4.jpg" alt="갤러리" onerror="this.src='https://placehold.co/600x800/1a1a26/c084fc?text=4'">
            </div>
            <div class="gallery-item">
                <img src="gallery5.jpg" alt="갤러리" onerror="this.src='https://placehold.co/600x800/1a1a26/7c5cfc?text=5'">
            </div>
            <div class="gallery-item">
                <img src="gallery6.jpg" alt="갤러리" onerror="this.src='https://placehold.co/600x800/1a1a26/c084fc?text=6'">
            </div>
            <div class="gallery-item">
                <img src="gallery7.jpg" alt="갤러리" onerror="this.src='https://placehold.co/600x800/1a1a26/7c5cfc?text=7'">
            </div>
            <div class="gallery-item">
                <img src="gallery8.jpg" alt="갤러리" onerror="this.src='https://placehold.co/600x800/1a1a26/c084fc?text=8'">
            </div>
        </div>
    </div>
</section>

<!-- ======================== CONTACT ======================== -->
<section id="contact">
    <div class="container">
        <div class="contact-header">
            <div class="section-label">Contact</div>
            <h2>함께 하실<br>브랜드를 기다립니다</h2>
<p class="section-sub">편하신 방법으로 언제든 연락 주세요.</p>
        </div>

        <div class="contact-wrap">

            <!-- 카카오 CTA -->
            <div class="contact-cta">
                <div class="contact-cta-text">
                    <p>가장 빠른 응답 보장 ⚡</p>
                    <span>평일 기준 2시간 내 답변 드립니다</span>
                </div>
                <a href="https://open.kakao.com/YOUR_LINK" class="btn-kakao" target="_blank">
                    <!-- 카카오 로고 심플 버전 -->
                    <svg viewBox="0 0 24 24" fill="currentColor">
                        <path d="M12 3C6.48 3 2 6.48 2 10.8c0 2.7 1.56 5.1 3.93 6.6L5 21l4.08-2.13C10.32 19.28 11.16 19.44 12 19.44c5.52 0 10-3.48 10-7.8S17.52 3 12 3z"/>
                    </svg>
                    카카오톡 오픈채팅으로 문의하기
                </a>
            </div>

            <!-- 이메일 -->
            <a href="mailto:your-email@example.com" class="contact-email">
                <div class="contact-email-icon">
                    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <rect x="2" y="4" width="20" height="16" rx="2"/>
                        <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7"/>
                    </svg>
                </div>
                <div class="contact-email-text">
                    <strong>your-email@example.com</strong>
                    <span>이메일로 협업 제안하기</span>
                </div>
                <div class="contact-email-arrow">
                    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                        <path d="M5 12h14M12 5l7 7-7 7"/>
                    </svg>
                </div>
            </a>

            <!-- SNS 2열 -->
            <div class="contact-sns-row">

                <a href="https://instagram.com/YOUR_ID" class="sns-card instagram" target="_blank">
                    <div class="sns-icon ig">
                        <svg viewBox="0 0 24 24">
                            <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 1 0 0 12.324 6.162 6.162 0 0 0 0-12.324zM12 16a4 4 0 1 1 0-8 4 4 0 0 1 0 8zm6.406-11.845a1.44 1.44 0 1 0 0 2.881 1.44 1.44 0 0 0 0-2.881z"/>
                        </svg>
                    </div>
                    <div class="sns-card-label">Instagram</div>
                    <div class="sns-card-sub">@your_id</div>
                </a>

                <a href="https://youtube.com/@YOUR_CHANNEL" class="sns-card youtube" target="_blank">
                    <div class="sns-icon yt">
                        <svg viewBox="0 0 24 24">
                            <path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
                        </svg>
                    </div>
                    <div class="sns-card-label">YouTube</div>
                    <div class="sns-card-sub">영상 포트폴리오</div>
                </a>

            </div>
        </div>
    </div>
</section>

</main>

<footer>
    <p>© 2025 김쇼호. All rights reserved.</p>
</footer>

</body>
</html>
