<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[당신 이름] | 쇼호스트 포트폴리오</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css">
    <style>
        /* --- 기본 및 리셋 --- */
        :root {
            --bg: #f8f9fc; --accent: #2763d6; --accent-light: #eef5ff; --text: #0f172a; --muted: #6b7280;
            --card: #fff; --radius: 12px; --shadow: 0 8px 25px rgba(15, 23, 42, 0.05);
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
        h2 { font-size: 22px; font-weight: 800; margin-bottom: 12px; text-align: center; }
        section { padding: 50px 0; }

        /* --- 헤더 --- */
        header {
            position: sticky; top: 0; z-index: 100;
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(5px);
            border-bottom: 1px solid #eef2f7;
        }
        .header-inner { display: flex; align-items: center; justify-content: space-between; height: 60px; }
        .logo { font-weight: 900; }
        .nav { display: flex; gap: 20px; font-weight: 700; font-size: 15px; }
        .nav a { text-decoration: none; color: var(--text); }

        /* --- 1. 첫 화면 (Hero) --- */
        .hero { padding-top: 24px; }
        .hero-row { display: flex; flex-direction: column; align-items: center; text-align: center; gap: 20px; }
        .hero-name { font-size: 18px; font-weight: 800; color: var(--accent); }
        .hero-title { font-size: 2rem; font-weight: 900; line-height: 1.2; margin: 4px 0 8px; }
        .hero-sub { color: var(--muted); font-size: 15px; max-width: 400px; margin-bottom: 16px; }
        .badges { display: flex; justify-content: center; flex-wrap: wrap; gap: 8px; }
        .badge { background: var(--accent-light); color: var(--accent); padding: 6px 12px; border-radius: 99px; font-weight: 700; font-size: 13px; }

        .slider-container { width: 70%; max-width: 260px; aspect-ratio: 3/4; border-radius: var(--radius); overflow: hidden; box-shadow: var(--shadow); }
        .slider-wrapper { display: flex; width: 200%; height: 100%; animation: slide 10s infinite ease-in-out; }
        .profile-img { width: 50%; height: 100%; object-fit: cover; }
        @keyframes slide {
            0%, 45% { transform: translateX(0%); } 50%, 95% { transform: translateX(-50%); } 100% { transform: translateX(0%); }
        }

        /* --- 2. 나의 강점 (Strengths) --- */
        .section-subtitle { text-align: center; color: var(--muted); margin-top: -8px; margin-bottom: 24px; font-size: 15px; }
        .strengths-grid { display: grid; gap: 12px; }
        .strength-card { background: var(--card); padding: 20px; border-radius: var(--radius); box-shadow: var(--shadow); text-align: center; }
        .strength-card h3 { font-size: 16px; margin-bottom: 6px; }
        .strength-card p { font-size: 14px; color: var(--muted); line-height: 1.5; }

        /* --- 3. 주요 성과 및 경력 --- */
        .career-grid { display: grid; gap: 24px; }
        .achievement-card, .career-card { background: var(--card); padding: 20px; border-radius: var(--radius); box-shadow: var(--shadow); }
        .card-title { font-weight: 800; margin-bottom: 12px; }
        .achievement-list li, .career-list li { list-style: none; padding-left: 1.2em; text-indent: -1.2em; font-size: 15px; color: var(--muted); }
        .achievement-list li::before { content: '🏆'; margin-right: 0.5em; }
        .career-list li { margin-bottom: 8px; }
        .career-list strong { color: var(--text); font-weight: 700; }

        /* --- 4. 레퍼런스 영상 --- */
        .videos-row { display: flex; gap: 12px; overflow-x: auto; padding: 4px 0 12px; scroll-snap-type: x mandatory; }
        .vcard { flex: 0 0 45%; scroll-snap-align: start; border-radius: var(--radius); overflow: hidden; background: var(--card); box-shadow: var(--shadow); }
        .video-frame { position: relative; width: 100%; aspect-ratio: 4/5; background: #111; }
        .video-frame iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }
        .vcard-title { padding: 8px; font-size: 12px; font-weight: 700; text-align: center; }

        /* --- 5. 갤러리 --- */
        .gallery-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; }
        .gallery-item { border-radius: var(--radius); overflow: hidden; aspect-ratio: 3/4; }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; }
        
        /* --- 6. 연락처 (Contact) --- */
        .contact-card {
            background: var(--card);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            padding: 24px;
            display: flex;
            flex-direction: column;
            gap: 24px;
        }
        .contact-main-title { font-size: 18px; font-weight: 800; }
        .contact-main-sub { font-size: 14px; color: var(--muted); margin-top: 4px; }
        .contact-button {
            display: block; width: 100%; padding: 14px;
            background: var(--accent); color: white;
            text-align: center; text-decoration: none;
            font-weight: 700; border-radius: 8px;
        }
        .email-link { display: block; text-align: center; color: var(--muted); font-size: 14px; font-weight: 600; text-decoration: none; margin-top: 12px; }
        .sns-links a {
            display: flex; align-items: center; gap: 12px;
            background: var(--accent-light); padding: 12px;
            border-radius: 8px; text-decoration: none; color: var(--text);
            margin-bottom: 10px;
        }
        .sns-links svg { width: 24px; height: 24px; }
        .sns-text-box strong { display: block; font-size: 15px; font-weight: 700; }
        .sns-text-box span { font-size: 13px; color: var(--muted); }

        /* --- PC (데스크탑) 스타일 --- */
        @media (min-width: 768px) {
            section { padding: 80px 0; }
            h2 { font-size: 28px; margin-bottom: 12px; }
            .hero-row { flex-direction: row; text-align: left; gap: 40px; }
            .hero-text { order: -1; }
            .badges { justify-content: flex-start; }
            .slider-container { width: 100%; max-width: 300px; }
            .hero-title { font-size: 2.8rem; }
            .strengths-grid { grid-template-columns: repeat(3, 1fr); gap: 16px; }
            .career-grid { grid-template-columns: repeat(2, 1fr); gap: 16px; }
            .videos-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; overflow-x: visible; }
            .vcard { flex-basis: auto; }
            .gallery-grid { grid-template-columns: repeat(4, 1fr); }
            .contact-card { flex-direction: row; align-items: center; padding: 40px; }
            .contact-main { flex: 1; }
            .sns-links { flex: 1; }
        }
    </style>
</head>
<body>

<header>
    <div class="container header-inner">
        <div class="logo">[YOUR NAME]</div>
        <nav class="nav">
            <a href="#strengths">강점</a>
            <a href="#videos">레퍼런스</a>
            <a href="#gallery">갤러리</a>
            <a href="#contact">연락처</a>
        </nav>
    </div>
</header>

<main>
    <!-- 1. 첫 화면 -->
    <section class="hero container">
        <div class="hero-row">
            <div class="slider-container">
                <div class="slider-wrapper">
                    <img src="profile1.jpg" alt="프로필 사진 1" class="profile-img" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=Profile+1'">
                    <img src="profile2.jpg" alt="프로필 사진 2" class="profile-img" onerror="this.src='https://via.placeholder.com/600x800/dbeafe/333?text=Profile+2'">
                </div>
            </div>
            <div class="hero-text">
                <div class="hero-name">쇼호스트 OOO</div>
                <div class="hero-title">시청자를 구매자로
바꾸는 한 시간</div>
                <div class="hero-sub">상품의 가치를 정확히 꿰뚫고, 데이터에 기반한 소구점으로 매출을 만듭니다.</div>
                <div class="badges">
                    <div class="badge">#높은전환율</div> <div class="badge">#꼼꼼한상품분석</div> <div class="badge">#기획/연출역량</div>
                </div>
            </div>
        </div>
    </section>

    <!-- 2. 나의 강점 -->
    <section id="strengths" class="container">
        <h2>저는 이런 점이 다릅니다</h2>
        <p class="section-subtitle">단순한 진행을 넘어, 방송의 성공을 위해 이 3가지를 약속합니다.</p>
        <div class="strengths-grid">
            <div class="strength-card"><h3>높은 구매 전환율</h3><p>평균 구매 전환율 15% 이상 달성 경험 다수. 시청자의 구매 심리를 자극하는 스피치에 자신 있습니다.</p></div>
            <div class="strength-card"><h3>꼼꼼한 상품 분석</h3><p>방송 전 상품 스터디는 기본. 직접 사용하며 장단점을 파악하고, 고객의 입장에서 궁금할 점을 먼저 해결합니다.</p></div>
            <div class="strength-card"><h3>기획/연출 역량</h3><p>단순 진행을 넘어, 방송 컨셉 기획과 현장 연출에 적극적으로 참여하여 완성도 높은 콘텐츠를 만듭니다.</p></div>
        </div>
    </section>

    <!-- 3. 주요 성과 및 경력 -->
    <section id="career" class="container">
        <div class="career-grid">
            <div class="achievement-card"><h3 class="card-title">주요 성과</h3><ul class="achievement-list"><li>N사 뷰티 브랜드 런칭 방송, 목표 매출 320% 달성</li><li>S사 리빙 브랜드 라이브, 동시 시청자 10만 명 돌파</li><li>F사 패션 브랜드 시즌오프 방송, 1시간 내 완판 기록</li></ul></div>
            <div class="career-card"><h3 class="card-title">주요 경력</h3><ul class="career-list"><li><strong>2023 - 현재</strong> 네이버 쇼핑라이브 (뷰티/패션)</li><li><strong>2021 - 2023</strong> OOO MCN (라이브 커머스팀)</li></ul></div>
        </div>
    </section>

    <!-- 4. 레퍼런스 영상 -->
    <section id="videos" class="container">
        <h2>레퍼런스 영상</h2>
        <div class="videos-row">
            <div class="vcard"><div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/123456?rel=0" allowfullscreen></iframe></div><div class="vcard-title">뷰티 브랜드 라이브</div></div>
            <div class="vcard"><div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/123457?rel=0" allowfullscreen></iframe></div><div class="vcard-title">패션 브랜드 런칭</div></div>
            <div class="vcard"><div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/123458?rel=0" allowfullscreen></iframe></div><div class="vcard-title">리빙 제품 시연</div></div>
            <div class="vcard"><div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/123459?rel=0" allowfullscreen></iframe></div><div class="vcard-title">가전 제품 소개</div></div>
        </div>
    </section>

    <!-- 5. 갤러리 -->
    <section id="gallery" class="container">
        <h2>갤러리</h2>
        <div class="gallery-grid">
            <div class="gallery-item"><img src="gallery1.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=1'"></div>
            <div class="gallery-item"><img src="gallery2.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=2'"></div>
            <div class="gallery-item"><img src="gallery3.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=3'"></div>
            <div class="gallery-item"><img src="gallery4.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=4'"></div>
            <div class="gallery-item"><img src="gallery5.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=5'"></div>
            <div class="gallery-item"><img src="gallery6.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=6'"></div>
            <div class="gallery-item"><img src="gallery7.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=7'"></div>
            <div class="gallery-item"><img src="gallery8.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=8'"></div>
        </div>
    </section>

    <!-- 6. 연락처 -->
    <section id="contact" class="container" style="padding-bottom: 80px;">
        <h2>최고의 방송, 함께 만들 준비가 되었습니다</h2>
        <p class="section-subtitle">새로운 기회와 설레는 협업 제안을 기다립니다.</p>
        <div class="contact-card">
            <div class="contact-main">
                <div class="contact-main-title">가장 빠른 방법으로 연락 주세요</div>
                <p class="contact-main-sub">브랜드의 가치를 높이는, 설레는 협업 제안을 기다립니다.</p>
                <a href="#" class="contact-button" style="margin-top: 16px;">[카카오톡 오픈채팅으로 문의하기]</a>
                <a href="mailto:your-email@example.com" class="email-link">[your-email@example.com]</a>
            </div>
            <div class="sns-links">
                <a href="#">
                    <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 2.882a10.553 10.553 0 0 0-3.535.645 10.23 10.23 0 0 0-2.88 1.624A10.152 10.152 0 0 0 3.53 7.97a10.53 10.53 0 0 0-.646 3.535c0 .4.02.793.057 1.178.037.386.08.768.13 1.14.33 2.51 1.25 4.71 2.82 6.35a10.16 10.16 0 0 0 6.34 2.82c.37.05.75.09 1.14.13.38.03.77.05 1.17.05.4 0 .79-.02 1.18-.05a10.53 10.53 0 0 0 3.53-.64 10.23 10.23 0 0 0 2.88-1.62 10.15 10.15 0 0 0 2.05-2.88c.45-1.12.64-2.32.64-3.53s-.19-2.4-.64-3.53a10.15 10.15 0 0 0-2.05-2.88 10.23 10.23 0 0 0-2.88-1.62A10.53 10.53 0 0 0 13.18 2.94 10.59 10.59 0 0 0 12 2.882Zm4.87 5.4a1.27 1.27 0 1 1 0 2.54 1.27 1.27 0 0 1 0-2.54ZM12 7.21a4.79 4.79 0 1 1 0 9.58 4.79 4.79 0 0 1 0-9.58Z" fill="#E1306C"/><path d="M12 8.94a3.06 3.06 0 1 0 0 6.12 3.06 3.06 0 0 0 0-6.12Z" fill="#E1306C"/></svg>
                    <div class="sns-text-box"><strong>Instagram</strong><span>사진 포트폴리오</span></div>
                </a>
                <a href="#">
                     <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 2.88c-5.13 0-9.28 4.16-9.28 9.29 0 5.13 4.15 9.28 9.28 9.28 5.12 0 9.28-4.15 9.28-9.28C21.28 7.04 17.12 2.88 12 2.88Zm-1.8 11.8V8.47l5.44 3.1-5.44 3.11Z" fill="#FF0000"/></svg>
                    <div class="sns-text-box"><strong>YouTube</strong><span>영상 포트폴리오</span></div>
                </a>
            </div>
        </div>
    </section>
</main>

</body>
</html>
