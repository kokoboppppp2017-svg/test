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
            --bg: #f8f9fc; --accent: #2763d6; --text: #0f172a; --muted: #6b7280;
            --card: #fff; --radius: 12px; --shadow: 0 8px 25px rgba(15, 23, 42, 0.05);
        }
        * { box-sizing: border-box; margin: 0; padding: 0; }
        html { scroll-behavior: smooth; }
        body {
            font-family: "Pretendard", sans-serif;
            background: var(--bg);
            color: var(--text);
            overflow-x: hidden; /* 모바일 가로 스크롤 원천 방지 */
            word-break: keep-all;
        }
        .container {
            width: 100%;
            max-width: 1024px;
            margin: 0 auto;
            padding: 0 20px;
        }
        h2 { font-size: 22px; font-weight: 800; margin-bottom: 16px; text-align: center; }
        section { padding: 32px 0; }

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
        .hero-sub { color: var(--muted); font-size: 15px; max-width: 400px; }

        /* 프로필 이미지 슬라이더 */
        .slider-container {
            width: 60%;
            max-width: 220px;
            aspect-ratio: 3/4;
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
        }
        .slider-wrapper {
            display: flex;
            width: 200%; /* 이미지 2장이므로 200% */
            height: 100%;
            animation: slide 10s infinite ease-in-out;
        }
        .profile-img { width: 50%; height: 100%; object-fit: cover; }
        @keyframes slide {
            0%, 45% { transform: translateX(0%); } /* 4.5초 대기 */
            50%, 95% { transform: translateX(-50%); } /* 0.5초 이동, 4.5초 대기 */
            100% { transform: translateX(0%); }
        }

        /* --- 2. 나의 강점 (Strengths) --- */
        .strengths-grid { display: grid; gap: 12px; }
        .strength-card {
            background: var(--card);
            padding: 20px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            text-align: center;
        }
        .strength-card h3 { font-size: 16px; margin-bottom: 6px; }
        .strength-card p { font-size: 14px; color: var(--muted); line-height: 1.5; }

        /* --- 3. 주요 성과 및 경력 --- */
        .career-grid { display: grid; gap: 24px; }
        .achievement-card, .career-card {
            background: var(--card);
            padding: 20px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
        }
        .card-title { font-weight: 800; margin-bottom: 12px; }
        .achievement-list li, .career-list li {
            list-style: none;
            padding-left: 1.2em;
            text-indent: -1.2em;
            font-size: 15px;
            color: var(--muted);
        }
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
        .gallery-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
        .gallery-item { border-radius: var(--radius); overflow: hidden; aspect-ratio: 3/4; }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; }

        /* --- PC (데스크탑) 스타일 --- */
        @media (min-width: 768px) {
            section { padding: 48px 0; }
            h2 { font-size: 28px; margin-bottom: 24px; }
            /* PC 첫 화면: 가로 배치 */
            .hero-row { flex-direction: row; text-align: left; gap: 40px; }
            .hero-text { order: -1; } /* 텍스트를 왼쪽으로 */
            .slider-container { width: 100%; max-width: 300px; }
            .hero-title { font-size: 2.8rem; }
            .strengths-grid { grid-template-columns: repeat(3, 1fr); gap: 16px; }
            .career-grid { grid-template-columns: repeat(2, 1fr); gap: 16px; }
            .videos-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; overflow-x: visible; }
            .vcard { flex-basis: auto; }
            .gallery-grid { grid-template-columns: repeat(4, 1fr); gap: 16px; }
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
        </nav>
    </div>
</header>

<main>
    <!-- 1. 첫 화면 -->
    <section class="hero container">
        <div class="hero-row">
            <div class="slider-container">
                <div class="slider-wrapper">
                    <!-- [교체] 프로필 사진 2장 (3:4 비율) -->
                    <img src="profile1.jpg" alt="프로필 사진 1" class="profile-img" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=Profile+1'">
                    <img src="profile2.jpg" alt="프로필 사진 2" class="profile-img" onerror="this.src='https://via.placeholder.com/600x800/dbeafe/333?text=Profile+2'">
                </div>
            </div>
            <div class="hero-text">
                <!-- [교체] 이름과 문구 -->
                <div class="hero-name">쇼호스트 OOO</div>
                <div class="hero-title">시청자를 구매자로
바꾸는 한 시간</div>
                <div class="hero-sub">상품의 가치를 정확히 꿰뚫고, 데이터에 기반한 소구점으로 매출을 만듭니다.</div>
            </div>
        </div>
    </section>

    <!-- 2. 나의 강점 -->
    <section id="strengths" class="container">
        <h2>나의 강점</h2>
        <div class="strengths-grid">
            <!-- [교체] 강점 3가지 -->
            <div class="strength-card">
                <h3>높은 구매 전환율</h3>
                <p>평균 구매 전환율 15% 이상 달성 경험 다수. 시청자의 구매 심리를 자극하는 스피치에 자신 있습니다.</p>
            </div>
            <div class="strength-card">
                <h3>꼼꼼한 상품 분석</h3>
                <p>방송 전 상품 스터디는 기본. 직접 사용하며 장단점을 파악하고, 고객의 입장에서 궁금할 점을 먼저 해결합니다.</p>
            </div>
            <div class="strength-card">
                <h3>기획/연출 역량</h3>
                <p>단순 진행을 넘어, 방송 컨셉 기획과 현장 연출에 적극적으로 참여하여 완성도 높은 콘텐츠를 만듭니다.</p>
            </div>
        </div>
    </section>

    <!-- 3. 주요 성과 및 경력 -->
    <section id="career" class="container">
        <div class="career-grid">
            <div class="achievement-card">
                <h3 class="card-title">주요 성과</h3>
                <!-- [교체] 실제 성과 -->
                <ul class="achievement-list">
                    <li>N사 뷰티 브랜드 런칭 방송, 목표 매출 320% 달성</li>
                    <li>S사 리빙 브랜드 라이브, 동시 시청자 10만 명 돌파</li>
                    <li>F사 패션 브랜드 시즌오프 방송, 1시간 내 완판 기록</li>
                </ul>
            </div>
            <div class="career-card">
                <h3 class="card-title">주요 경력</h3>
                <!-- [교체] 실제 경력 -->
                <ul class="career-list">
                    <li><strong>2023 - 현재</strong> 네이버 쇼핑라이브 (뷰티/패션)</li>
                    <li><strong>2021 - 2023</strong> OOO MCN (라이브 커머스팀)</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- 4. 레퍼런스 영상 -->
    <section id="videos" class="container">
        <h2>레퍼런스 영상</h2>
        <div class="videos-row">
            <!-- [교체] 실제 영상 주소의 ID 부분만 교체하세요 -->
            <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/123456?rel=0" allowfullscreen></iframe></div>
                <div class="vcard-title">뷰티 브랜드 라이브</div>
            </div>
            <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/123457?rel=0" allowfullscreen></iframe></div>
                <div class="vcard-title">패션 브랜드 런칭</div>
            </div>
            <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/123458?rel=0" allowfullscreen></iframe></div>
                <div class="vcard-title">리빙 제품 시연</div>
            </div>
             <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/123459?rel=0" allowfullscreen></iframe></div>
                <div class="vcard-title">가전 제품 소개</div>
            </div>
        </div>
    </section>

    <!-- 5. 갤러리 -->
    <section id="gallery" class="container" style="padding-bottom: 48px;">
        <h2>갤러리</h2>
        <div class="gallery-grid">
            <!-- [교체] 갤러리 이미지 (3:4 비율) -->
            <div class="gallery-item"><img src="gallery1.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=1'"></div>
            <div class="gallery-item"><img src="gallery2.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=2'"></div>
            <div class="gallery-item"><img src="gallery3.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=3'"></div>
            <div class="gallery-item"><img src="gallery4.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=4'"></div>
            <div class="gallery-item"><img src="gallery5.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=5'"></div>
            <div class="gallery-item"><img src="gallery6.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=6'"></div>
            <div class="gallery-item"><img src="gallery7.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=7'"></div>
            <div class="gallery-item"><img src="gallery8.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=8'"></div>
            <div class="gallery-item"><img src="gallery9.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=9'"></div>
        </div>
    </section>
</main>

</body>
</html>
