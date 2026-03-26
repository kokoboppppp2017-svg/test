<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>김쇼호스트 | Show Host Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #FAFAF8;
            --bg-secondary: #F5F0EB;
            --bg-card: #FFFFFF;
            --text-primary: #1A1A1A;
            --text-secondary: #5A5A5A;
            --text-muted: #9A9A9A;
            --rose-gold: #C9956C;
            --burgundy: #8B2E4A;
            --accent: #D4A88A;
            --border: #E8E0D8;
            --shadow: rgba(139, 46, 74, 0.08);
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Apple SD Gothic Neo', 'Noto Sans KR', sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.6;
        }

        /* ── HEADER ── */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            padding: 20px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(250, 250, 248, 0.85);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--border);
        }

        .logo {
            font-size: 1.1rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--rose-gold), var(--burgundy));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: 0.05em;
        }

        nav a {
            color: var(--text-secondary);
            text-decoration: none;
            margin-left: 32px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: color 0.3s;
            letter-spacing: 0.03em;
        }

        nav a:hover {
            color: var(--burgundy);
        }

        /* ── HERO ── */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 120px 40px 80px;
            position: relative;
            overflow: hidden;
            background: linear-gradient(160deg, #FAFAF8 0%, #F5EDE6 50%, #F0E4DC 100%);
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 600px;
            height: 600px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(201,149,108,0.12) 0%, transparent 70%);
            top: -100px;
            right: -100px;
        }

        .hero::after {
            content: '';
            position: absolute;
            width: 400px;
            height: 400px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(139,46,74,0.08) 0%, transparent 70%);
            bottom: -50px;
            left: -50px;
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        .hero-badge {
            display: inline-block;
            padding: 8px 20px;
            border: 1px solid var(--rose-gold);
            border-radius: 50px;
            font-size: 0.8rem;
            color: var(--rose-gold);
            letter-spacing: 0.15em;
            text-transform: uppercase;
            margin-bottom: 32px;
            background: rgba(201, 149, 108, 0.06);
        }

        .hero h1 {
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 16px;
            background: linear-gradient(135deg, #C9956C 0%, #8B2E4A 50%, #C9956C 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            background-size: 200% auto;
            animation: shimmer 4s linear infinite;
        }

        @keyframes shimmer {
            0% { background-position: 0% center; }
            100% { background-position: 200% center; }
        }

        .hero-subtitle {
            font-size: clamp(1rem, 2.5vw, 1.3rem);
            color: var(--text-secondary);
            margin-bottom: 12px;
            font-weight: 400;
            letter-spacing: 0.05em;
        }

        .hero-desc {
            font-size: 0.95rem;
            color: var(--text-muted);
            margin-bottom: 48px;
            max-width: 480px;
            margin-left: auto;
            margin-right: auto;
        }

        .hero-buttons {
            display: flex;
            gap: 16px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary {
            padding: 14px 36px;
            background: linear-gradient(135deg, var(--rose-gold), var(--burgundy));
            color: white;
            border: none;
            border-radius: 50px;
            font-size: 0.95rem;
            font-weight: 600;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s;
            box-shadow: 0 4px 20px rgba(139, 46, 74, 0.25);
            letter-spacing: 0.03em;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 30px rgba(139, 46, 74, 0.35);
        }

        .btn-secondary {
            padding: 14px 36px;
            background: transparent;
            color: var(--burgundy);
            border: 1.5px solid var(--rose-gold);
            border-radius: 50px;
            font-size: 0.95rem;
            font-weight: 600;
            cursor: pointer;
            text-decoration: none;
            transition: all 0.3s;
            letter-spacing: 0.03em;
        }

        .btn-secondary:hover {
            background: rgba(201, 149, 108, 0.08);
            transform: translateY(-2px);
        }

        /* ── SECTIONS ── */
        section {
            padding: 100px 40px;
            max-width: 1100px;
            margin: 0 auto;
        }

        .section-label {
            font-size: 0.75rem;
            letter-spacing: 0.2em;
            text-transform: uppercase;
            color: var(--rose-gold);
            font-weight: 600;
            margin-bottom: 12px;
        }

        .section-title {
            font-size: clamp(1.8rem, 4vw, 2.8rem);
            font-weight: 800;
            color: var(--text-primary);
            margin-bottom: 16px;
            line-height: 1.2;
        }

        .section-title span {
            background: linear-gradient(135deg, var(--rose-gold), var(--burgundy));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section-desc {
            color: var(--text-secondary);
            font-size: 1rem;
            margin-bottom: 60px;
            max-width: 560px;
        }

        /* ── ABOUT ── */
        .about-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .about-image-placeholder {
            aspect-ratio: 3/4;
            border-radius: 24px;
            background: linear-gradient(160deg, var(--bg-secondary), #EDD8CC);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            border: 1px solid var(--border);
            box-shadow: 0 8px 40px var(--shadow);
            position: relative;
            overflow: hidden;
        }

        .about-image-placeholder::after {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(160deg, rgba(201,149,108,0.1), rgba(139,46,74,0.05));
        }

        .about-text h3 {
            font-size: 1.8rem;
            font-weight: 800;
            margin-bottom: 20px;
            color: var(--text-primary);
        }

        .about-text p {
            color: var(--text-secondary);
            margin-bottom: 16px;
            font-size: 0.97rem;
            line-height: 1.8;
        }

        .tag-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 28px;
        }

        .tag {
            padding: 6px 16px;
            background: rgba(201, 149, 108, 0.1);
            border: 1px solid rgba(201, 149, 108, 0.3);
            border-radius: 50px;
            font-size: 0.82rem;
            color: var(--burgundy);
            font-weight: 500;
        }

        /* ── NUMBERS ── */
        .numbers-section {
            background: linear-gradient(135deg, var(--bg-secondary), #EDD8CC);
            border-radius: 32px;
            padding: 80px 60px;
            max-width: 1100px;
            margin: 0 auto;
            border: 1px solid var(--border);
            box-shadow: 0 8px 40px var(--shadow);
        }

        .numbers-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 40px;
            margin-top: 50px;
        }

        .number-card {
            text-align: center;
            padding: 32px 20px;
            background: var(--bg-card);
            border-radius: 20px;
            border: 1px solid var(--border);
            box-shadow: 0 4px 20px var(--shadow);
            transition: transform 0.3s;
        }

        .number-card:hover {
            transform: translateY(-4px);
        }

        .number-value {
            font-size: 2.8rem;
            font-weight: 800;
            background: linear-gradient(135deg, var(--rose-gold), var(--burgundy));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1;
            margin-bottom: 10px;
        }

        .number-label {
            font-size: 0.85rem;
            color: var(--text-secondary);
            font-weight: 500;
            line-height: 1.4;
        }

        /* ── CAREER ── */
        .career-list {
            display: flex;
            flex-direction: column;
            gap: 24px;
        }

        .career-item {
            display: grid;
            grid-template-columns: 140px 1fr;
            gap: 32px;
            padding: 32px;
            background: var(--bg-card);
            border-radius: 20px;
            border: 1px solid var(--border);
            box-shadow: 0 2px 16px var(--shadow);
            transition: all 0.3s;
        }

        .career-item:hover {
            border-color: var(--rose-gold);
            box-shadow: 0 8px 32px var(--shadow);
            transform: translateX(4px);
        }

        .career-period {
            font-size: 0.82rem;
            color: var(--rose-gold);
            font-weight: 600;
            letter-spacing: 0.05em;
            padding-top: 4px;
        }

        .career-company {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 6px;
        }

        .career-role {
            font-size: 0.88rem;
            color: var(--rose-gold);
            margin-bottom: 10px;
            font-weight: 500;
        }

        .career-desc {
            font-size: 0.88rem;
            color: var(--text-secondary);
            line-height: 1.6;
        }

        /* ── VIDEOS ── */
        .videos-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 24px;
        }

        .video-card {
            background: var(--bg-card);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid var(--border);
            box-shadow: 0 4px 20px var(--shadow);
            transition: all 0.3s;
        }

        .video-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 16px 40px rgba(139, 46, 74, 0.15);
        }

        .video-wrapper {
            position: relative;
            padding-bottom: 177.78%;
            height: 0;
            overflow: hidden;
        }

        .video-wrapper iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        .video-info {
            padding: 20px;
        }

        .video-platform {
            font-size: 0.72rem;
            letter-spacing: 0.15em;
            text-transform: uppercase;
            color: var(--rose-gold);
            font-weight: 600;
            margin-bottom: 6px;
        }

        .video-title {
            font-size: 0.92rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 6px;
            line-height: 1.4;
        }

        .video-meta {
            font-size: 0.8rem;
            color: var(--text-muted);
        }

        /* ── CONTACT ── */
        .contact-wrapper {
            background: linear-gradient(135deg, var(--bg-secondary), #EDD8CC);
            border-radius: 32px;
            padding: 80px 60px;
            max-width: 1100px;
            margin: 0 auto;
            border: 1px solid var(--border);
            box-shadow: 0 8px 40px var(--shadow);
        }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 32px;
            margin-top: 50px;
        }

        .contact-card {
            background: var(--bg-card);
            border-radius: 20px;
            padding: 36px 32px;
            border: 1px solid var(--border);
            box-shadow: 0 4px 20px var(--shadow);
            transition: all 0.3s;
            text-decoration: none;
            color: inherit;
            display: block;
        }

        .contact-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 40px rgba(139, 46, 74, 0.15);
            border-color: var(--rose-gold);
        }

        .contact-card.kakao {
            grid-column: 1 / -1;
            display: flex;
            align-items: center;
            gap: 28px;
            background: linear-gradient(135deg, #FEE500, #FFD700);
            border-color: #FEE500;
        }

        .kakao-icon {
            font-size: 3rem;
            flex-shrink: 0;
        }

        .kakao-text h3 {
            font-size: 1.2rem;
            font-weight: 800;
            color: #3A1D1D;
            margin-bottom: 6px;
        }

        .kakao-text p {
            font-size: 0.88rem;
            color: #5A3A3A;
        }

        .kakao-text .kakao-cta {
            margin-top: 12px;
            display: inline-block;
            padding: 8px 20px;
            background: #3A1D1D;
            color: #FEE500;
            border-radius: 50px;
            font-size: 0.82rem;
            font-weight: 700;
            letter-spacing: 0.03em;
        }

        .contact-icon {
            font-size: 2rem;
            margin-bottom: 16px;
        }

        .contact-card h3 {
            font-size: 1rem;
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 6px;
        }

        .contact-card p {
            font-size: 0.85rem;
            color: var(--text-secondary);
            line-height: 1.5;
        }

        .contact-card .contact-link {
            margin-top: 12px;
            font-size: 0.82rem;
            color: var(--rose-gold);
            font-weight: 600;
        }

        /* ── FOOTER ── */
        footer {
            text-align: center;
            padding: 48px 40px;
            border-top: 1px solid var(--border);
            color: var(--text-muted);
            font-size: 0.85rem;
            background: var(--bg-secondary);
        }

        footer span {
            background: linear-gradient(135deg, var(--rose-gold), var(--burgundy));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: 600;
        }

        /* ── DIVIDER ── */
        .section-divider {
            width: 100%;
            height: 1px;
            background: linear-gradient(90deg, transparent, var(--border), transparent);
            margin: 0 auto;
            max-width: 1100px;
        }

        /* ── SCROLL ANIMATION ── */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.7s ease, transform 0.7s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* ── RESPONSIVE ── */
        @media (max-width: 768px) {
            header {
                padding: 16px 20px;
            }

            nav a {
                margin-left: 16px;
                font-size: 0.82rem;
            }

            section {
                padding: 70px 20px;
            }

            .about-grid {
                grid-template-columns: 1fr;
                gap: 40px;
            }

            .numbers-section {
                padding: 50px 24px;
            }

            .numbers-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 16px;
            }

            .career-item {
                grid-template-columns: 1fr;
                gap: 8px;
            }

            .videos-grid {
                grid-template-columns: 1fr;
                max-width: 360px;
                margin: 0 auto;
            }

            .contact-wrapper {
                padding: 50px 24px;
            }

            .contact-grid {
                grid-template-columns: 1fr;
            }

            .contact-card.kakao {
                grid-column: 1;
                flex-direction: column;
                text-align: center;
            }
        }
    </style>
</head>
<body>

<!-- HEADER -->
<header>
    <div class="logo">YOUR NAME</div>
    <nav>
        <a href="#about">About</a>
        <a href="#numbers">Numbers</a>
        <a href="#career">Career</a>
        <a href="#videos">Videos</a>
        <a href="#contact">Contact</a>
    </nav>
</header>

<!-- HERO -->
<section class="hero" id="home">
    <div class="hero-content">
        <div class="hero-badge">✦ Show Host Portfolio</div>
        <h1>홍길동</h1>
        <p class="hero-subtitle">라이브커머스 · TV홈쇼핑 · 브랜드행사</p>
        <p class="hero-desc">
            숫자로 증명하는 성과, 진심으로 전하는 이야기<br>
            시청자의 마음을 움직이는 쇼호스트입니다
        </p>
        <div class="hero-buttons">
            <a href="#contact" class="btn-primary">📩 협업 문의하기</a>
            <a href="#videos" class="btn-secondary">🎬 영상 보러가기</a>
        </div>
    </div>
</section>

<!-- ABOUT -->
<section id="about" class="fade-in">
    <div class="about-grid">
        <div class="about-image-placeholder">
            📸
        </div>
        <div class="about-text">
            <div class="section-label">About Me</div>
            <h3>안녕하세요,<br>쇼호스트 <span style="background: linear-gradient(135deg, #C9956C, #8B2E4A); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">홍길동</span>입니다</h3>
            <p>
                TV홈쇼핑과 라이브커머스를 넘나드는 
                멀티 플랫폼 쇼호스트입니다.
            </p>
            <p>
                단순한 상품 소개를 넘어, 브랜드의 가치를 
                시청자에게 진심으로 전달하는 것을 가장 중요하게 생각합니다.
            </p>
            <p>
                뷰티, 패션, 리빙, 식품까지 폭넓은 카테고리 경험을 바탕으로
                각 브랜드에 최적화된 세일즈 커뮤니케이션을 제공합니다.
            </p>
            <div class="tag-list">
                <span class="tag">라이브커머스</span>
                <span class="tag">TV홈쇼핑</span>
                <span class="tag">네이버쇼핑라이브</span>
                <span class="tag">브랜드행사 MC</span>
                <span class="tag">뷰티</span>
                <span class="tag">패션</span>
                <span class="tag">리빙</span>
                <span class="tag">식품</span>
            </div>
        </div>
    </div>
</section>

<div class="section-divider"></div>

<!-- NUMBERS -->
<div class="numbers-section fade-in" id="numbers">
    <div class="section-label">Numbers</div>
    <div class="section-title">숫자로 증명합니다</div>
    <div class="section-desc">
        실제 방송 데이터를 기반으로 한 검증된 성과입니다
    </div>
    <div class="numbers-grid">
        <div class="number-card">
            <div class="number-value">320<span style="font-size:1.6rem">%</span></div>
            <div class="number-label">월 판매 목표 달성률<br><span style="color:#9A9A9A; font-size:0.78rem">2024년 최고 기록</span></div>
        </div>
        <div class="number-card">
            <div class="number-value">15<span style="font-size:1.6rem">%+</span></div>
            <div class="number-label">평균 구매전환율<br><span style="color:#9A9A9A; font-size:0.78rem">업계 평균 대비 2배</span></div>
        </div>
        <div class="number-card">
            <div class="number-value">200<span style="font-size:1.6rem">+</span></div>
            <div class="number-label">누적 방송 횟수<br><span style="color:#9A9A9A; font-size:0.78rem">TV · 라이브 통합</span></div>
        </div>
        <div class="number-card">
            <div class="number-value">50<span style="font-size:1.6rem">+</span></div>
            <div class="number-label">협업 브랜드 수<br><span style="color:#9A9A9A; font-size:0.78rem">다양한 카테고리</span></div>
        </div>
    </div>
</div>

<div class="section-divider" style="margin-top: 100px;"></div>

<!-- CAREER -->
<section id="career" class="fade-in">
    <div class="section-label">Career</div>
    <div class="section-title">경력 <span>히스토리</span></div>
    <div class="section-desc">
        다양한 플랫폼에서 쌓아온 실전 경험입니다
    </div>
    <div class="career-list">
        <div class="career-item">
            <div class="career-period">2022 — 현재</div>
            <div>
                <div class="career-company">네이버 쇼핑라이브</div>
                <div class="career-role">라이브커머스 쇼호스트</div>
                <div class="career-desc">뷰티/패션/리빙 카테고리 전담 진행. 월 평균 판매액 XX억 달성. 구매전환율 업계 평균 2배 이상 유지</div>
            </div>
        </div>
        <div class="career-item">
            <div class="career-period">2020 — 2022</div>
            <div>
                <div class="career-company">○○ 홈쇼핑</div>
                <div class="career-role">TV홈쇼핑 쇼호스트</div>
                <div class="career-desc">식품/건강식품/리빙 전담. 단일 방송 최고 매출 XX억 달성. 신규 쇼호스트 중 최단기간 메인 진행자 발탁</div>
            </div>
        </div>
        <div class="career-item">
            <div class="career-period">2019 — 2020</div>
            <div>
                <div class="career-company">○○ 에이전시</div>
                <div class="career-role">브랜드 행사 MC / 쇼호스트</div>
                <div class="career-desc">뷰티/패션 브랜드 팝업스토어, 론칭 행사 MC. 연간 XX개 브랜드 행사 진행</div>
            </div>
        </div>
    </div>
</section>

<div class="section-divider"></div>

<!-- VIDEOS -->
<section id="videos" class="fade-in">
    <div class="section-label">Videos</div>
    <div class="section-title">방송 <span>레퍼런스</span></div>
    <div class="section-desc">
        실제 방송에서 확인하는 진행 스타일과 세일즈 커뮤니케이션
    </div>
    <div class="videos-grid">
        <div class="video-card">
            <div class="video-wrapper">
                <iframe
                    src="https://www.youtube.com/embed/VIDEO_ID_1"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen>
                </iframe>
            </div>
            <div class="video-info">
                <div class="video-platform">📺 네이버 쇼핑라이브</div>
                <div class="video-title">○○ 브랜드 뷰티 라이브</div>
                <div class="video-meta">조회수 XX만 · 판매액 XX억</div>
            </div>
        </div>
        <div class="video-card">
            <div class="video-wrapper">
                <iframe
                    src="https://www.youtube.com/embed/VIDEO_ID_2"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen>
                </iframe>
            </div>
            <div class="video-info">
                <div class="video-platform">📺 TV 홈쇼핑</div>
                <div class="video-title">○○ 브랜드 패션 방송</div>
                <div class="video-meta">방송 매출 XX억 달성</div>
            </div>
        </div>
        <div class="video-card">
            <div class="video-wrapper">
                <iframe
                    src="https://www.youtube.com/embed/VIDEO_ID_3"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen>
                </iframe>
            </div>
            <div class="video-info">
                <div class="video-platform">🎤 브랜드 행사</div>
                <div class="video-title">○○ 브랜드 론칭 행사</div>
                <div class="video-meta">참석자 XX명 · ○○년 ○월</div>
            </div>
        </div>
    </div>
</section>

<div class="section-divider"></div>

<!-- CONTACT -->
<div class="contact-wrapper fade-in" id="contact">
    <div class="section-label">Contact</div>
    <div class="section-title">함께 <span>만들어요</span></div>
    <div class="section-desc">
        방송 출연 · 브랜드 협업 · 행사 MC 문의를 기다립니다
    </div>
    <div class="contact-grid">
        <a href="https://open.kakao.com/YOUR_LINK" target="_blank" class="contact-card kakao">
            <div class="kakao-icon">💬</div>
            <div class="kakao-text">
                <h3>카카오톡 오픈채팅으로 빠르게 문의하세요</h3>
                <p>협업 제안, 출연 문의, 견적 상담 — 가장 빠르게 답변 드립니다</p>
                <span class="kakao-cta">카카오톡 오픈채팅 바로가기 →</span>
            </div>
        </a>
        <a href="mailto:your@email.com" class="contact-card">
            <div class="contact-icon">📧</div>
            <h3>이메일</h3>
            <p>공식 제안서, 계약 관련 문의는 이메일로 보내주세요</p>
            <div class="contact-link">your@email.com →</div>
        </a>
        <a href="https://instagram.com/YOUR_ID" target="_blank" class="contact-card">
            <div class="contact-icon">📸</div>
            <h3>인스타그램</h3>
            <p>일상과 방송 현장을 함께 공유해요</p>
            <div class="contact-link">@instagram_id →</div>
        </a>
        <a href="https://youtube.com/@YOUR_CHANNEL" target="_blank" class="contact-card">
            <div class="contact-icon">▶️</div>
            <h3>유튜브 채널</h3>
            <p>방송 하이라이트와 비하인드 영상을 확인하세요</p>
            <div class="contact-link">유튜브 채널 바로가기 →</div>
        </a>
    </div>
</div>

<!-- FOOTER -->
<footer>
    <p>© 2025 <span>홍길동</span> · Show Host Portfolio</p>
    <p style="margin-top: 8px; font-size: 0.78rem;">Made with ♥ for GitHub Pages</p>
</footer>

<script>
    // Scroll Fade-in
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, { threshold: 0.1 });

    document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

    // Number Counter Animation
    function animateCounter(el, target, suffix = '') {
        let start = 0;
        const duration = 2000;
        const step = (timestamp) => {
            if (!start) start = timestamp;
            const progress = Math.min((timestamp - start) / duration, 1);
            const eased = 1 - Math.pow(1 - progress, 3);
            el.textContent = Math.floor(eased * target) + suffix;
            if (progress < 1) requestAnimationFrame(step);
        };
        requestAnimationFrame(step);
    }

    const numbersObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                const cards = entry.target.querySelectorAll('.number-value');
                const data = [
                    { value: 320, suffix: '%' },
                    { value: 15, suffix: '%+' },
                    { value: 200, suffix: '+' },
                    { value: 50, suffix: '+' }
                ];
                cards.forEach((card, i) => {
                    animateCounter(card, data[i].value, data[i].suffix);
                });
                numbersObserver.unobserve(entry.target);
            }
        });
    }, { threshold: 0.3 });

    const numbersSection = document.querySelector('.numbers-grid');
    if (numbersSection) numbersObserver.observe(numbersSection);
</script>

</body>
</html>
