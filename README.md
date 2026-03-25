<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <!-- 1. 화면 최적화: viewport를 표준으로 설정하여 축소 문제를 원천적으로 방지합니다. -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[당신 이름] | 쇼호스트 포트폴리오</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css">
    <style>
        :root {
            --bg: #f8f9fc; --accent: #2763d6; --text: #0f172a; --muted: #6b7280;
            --card: #fff; --radius: 12px; --shadow: 0 8px 25px rgba(15, 23, 42, 0.05);
        }
        /* 기본 스타일 및 화면 최적화 보조 */
        html { scroll-behavior: smooth; }
        body {
            margin: 0;
            font-family: "Pretendard", sans-serif;
            background: var(--bg);
            color: var(--text);
            /* 가로 스크롤이 생기는 것을 원천 방지 */
            overflow-x: hidden;
        }
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 16px;
        }
        h2 { font-size: 20px; margin: 24px 0 12px; }

        /* 헤더 */
        header { position: sticky; top: 0; background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(5px); border-bottom: 1px solid #eef2f7; z-index: 100; }
        .header-inner { display: flex; align-items: center; justify-content: space-between; height: 60px; }
        .logo { font-weight: 900; }
        .nav { display: flex; gap: 16px; font-weight: 700; font-size: 15px; }

        /* 히어로 (프로필) 섹션 */
        .hero { padding: 24px 0; }
        .hero-row { display: flex; align-items: center; gap: 16px; }
        .hero-text { flex: 1; min-width: 0; }
        .hero-name { font-size: 18px; font-weight: 800; color: var(--accent); margin-bottom: 4px; }
        .hero-title { font-size: clamp(1.5rem, 5vw, 2rem); font-weight: 900; line-height: 1.1; margin: 0 0 8px; }
        .hero-sub { color: var(--muted); font-size: 14px; margin-bottom: 12px; }
        .badges { display: flex; flex-wrap: wrap; gap: 6px; }
        .badge { background: #eef5ff; color: var(--accent); padding: 5px 10px; border-radius: 99px; font-weight: 700; font-size: 12px; }

        /* 프로필 이미지 박스: 화면 너비에 따라 유연하게 조절 */
        .profile-box {
            flex-shrink: 0;
            width: 35%; /* 고정 너비 대신 % 사용 */
            max-width: 150px; /* 너무 커지지 않도록 최대 너비 제한 */
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
        }
        .profile-img { display: block; width: 100%; aspect-ratio: 3/4; object-fit: cover; }

        /* 2. 레퍼런스 영상 크기 축소 */
        .videos-row {
            display: flex;
            gap: 10px; /* 영상 간 간격 */
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            padding-bottom: 10px; /* 스크롤바를 위한 여백 */
        }
        .vcard {
            /* 모바일에서 3개가 보이도록 flex-basis를 33.33%로 설정 */
            flex: 0 0 calc(33.333% - 7px);
            scroll-snap-align: start;
            background: var(--card);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
        }
        .video-frame {
            position: relative;
            width: 100%;
            /* 세로 비율을 덜 길쭉한 3:4로 변경 */
            aspect-ratio: 3/4;
            background: #111;
        }
        .video-frame iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }
        .vcard-title { padding: 8px; font-size: 12px; font-weight: 700; text-align: center; }

        /* 갤러리 */
        .gallery-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
        .gallery-item { border-radius: var(--radius); overflow: hidden; aspect-ratio: 3/4; }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; }

        /* PC (데스크탑) 화면에서는 다르게 보이도록 설정 */
        @media (min-width: 768px) {
            .profile-box { max-width: 280px; }
            .videos-row { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; overflow-x: visible; }
            .gallery-grid { grid-template-columns: repeat(4, 1fr); gap: 16px; }
        }
    </style>
</head>
<body>

<header>
    <div class="container header-inner">
        <div class="logo">[YOUR NAME]</div>
        <nav class="nav">
            <a href="#videos">레퍼런스</a>
            <a href="#gallery">갤러리</a>
        </nav>
    </div>
</header>

<main class="container">
    <section class="hero">
        <div class="hero-row">
            <div class="hero-text">
                <div class="hero-name">쇼호스트 OOO</div>
                <div class="hero-title">구매를 만드는
라이브 커머스</div>
                <div class="hero-sub">기획부터 판매까지, 매출로 증명합니다.</div>
                <div class="badges">
                    <div class="badge">#뷰티전문</div>
                    <div class="badge">#라이브커머스</div>
                    <div class="badge">#올인원</div>
                </div>
            </div>
            <div class="profile-box">
                <img src="profile.jpg" alt="프로필 사진" class="profile-img" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=Profile'">
            </div>
        </div>
    </section>

    <section id="videos">
        <h2>레퍼런스 영상</h2>
        <div class="videos-row">
            <!-- 네이버 쇼핑라이브 등 iframe 형태의 영상 소스를 여기에 넣으세요 -->
            <div class="vcard">
                <div class="video-frame">
                    <iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allow="autoplay; encrypted-media" allowfullscreen></iframe>
                </div>
                <div class="vcard-title">브랜드 라이브</div>
            </div>
            <div class="vcard">
                <div class="video-frame">
                    <iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allow="autoplay; encrypted-media" allowfullscreen></iframe>
                </div>
                <div class="vcard-title">제품 런칭쇼</div>
            </div>
            <div class="vcard">
                <div class="video-frame">
                    <iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allow="autoplay; encrypted-media" allowfullscreen></iframe>
                </div>
                <div class="vcard-title">기획 방송</div>
            </div>
             <div class="vcard">
                <div class="video-frame">
                    <iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allow="autoplay; encrypted-media" allowfullscreen></iframe>
                </div>
                <div class="vcard-title">패션 하울</div>
            </div>
        </div>
    </section>

    <section id="gallery" style="margin-top: 24px;">
        <h2>갤러리</h2>
        <div class="gallery-grid">
            <!-- 3:4 비율의 갤러리 이미지 8개 -->
            <div class="gallery-item"><img src="gallery1.jpg" alt="갤러리 이미지 1" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=1'"></div>
            <div class="gallery-item"><img src="gallery2.jpg" alt="갤러리 이미지 2" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=2'"></div>
            <div class="gallery-item"><img src="gallery3.jpg" alt="갤러리 이미지 3" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=3'"></div>
            <div class="gallery-item"><img src="gallery4.jpg" alt="갤러리 이미지 4" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=4'"></div>
            <div class="gallery-item"><img src="gallery5.jpg" alt="갤러리 이미지 5" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=5'"></div>
            <div class="gallery-item"><img src="gallery6.jpg" alt="갤러리 이미지 6" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=6'"></div>
            <div class="gallery-item"><img src="gallery7.jpg" alt="갤러리 이미지 7" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=7'"></div>
            <div class="gallery-item"><img src="gallery8.jpg" alt="갤러리 이미지 8" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=8'"></div>
        </div>
    </section>
</main>

</body>
</html>
