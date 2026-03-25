<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[당신 이름] | 쇼호스트 포트폴리오</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css">
    <style>
        :root {
            --bg: #f8f9fc; --accent: #2763d6; --text: #0f172a; --muted: #6b7280;
            --card: #fff; --radius: 12px; --shadow: 0 8px 25px rgba(15, 23, 42, 0.05);
        }
        html { scroll-behavior: smooth; }
        body {
            margin: 0;
            font-family: "Pretendard", sans-serif;
            background: var(--bg);
            color: var(--text);
            word-break: keep-all;
        }
        .container {
            max-width: 1024px;
            margin: 0 auto;
            padding: 0 20px;
        }
        h2 { font-size: 20px; font-weight: 800; margin: 32px 0 12px; }

        /* --- 모바일 기본 스타일 (Mobile First) --- */
        header {
            position: sticky; top: 0; background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(5px); border-bottom: 1px solid #eef2f7; z-index: 100;
        }
        .header-inner { display: flex; align-items: center; justify-content: space-between; height: 60px; }
        .logo { font-weight: 900; }
        .nav { display: flex; gap: 20px; font-weight: 700; font-size: 15px; }

        /* 첫 화면: 모바일에서는 무조건 세로 배치 */
        .hero { padding: 24px 0; }
        .hero-row {
            display: flex;
            flex-direction: column; /* 세로 배치 */
            align-items: center;
            text-align: center;
            gap: 16px;
        }
        .profile-box {
            width: 50%;
            max-width: 180px;
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            order: -1; /* 모바일에서 사진을 위로 올림 */
        }
        .profile-img { display: block; width: 100%; aspect-ratio: 3/4; object-fit: cover; }
        .hero-name { font-size: 18px; font-weight: 800; color: var(--accent); }
        .hero-title { font-size: 1.8rem; font-weight: 900; line-height: 1.2; margin: 4px 0 8px; }
        .hero-sub { color: var(--muted); font-size: 15px; margin-bottom: 16px; }
        .badges { display: flex; justify-content: center; flex-wrap: wrap; gap: 8px; }
        .badge { background: #eef5ff; color: var(--accent); padding: 6px 12px; border-radius: 99px; font-weight: 700; font-size: 13px; }

        /* 레퍼런스 영상 */
        .videos-row { display: flex; gap: 12px; overflow-x: auto; padding: 4px 0 12px; scroll-snap-type: x mandatory; }
        .vcard {
            flex: 0 0 35%; /* 모바일에서 더 작게 보이도록 조정 */
            scroll-snap-align: start;
            border-radius: var(--radius);
            overflow: hidden;
            background: var(--card);
            box-shadow: var(--shadow);
        }
        .video-frame { position: relative; width: 100%; aspect-ratio: 4/5; background: #111; }
        .video-frame iframe { position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0; }
        .vcard-title { padding: 8px; font-size: 12px; font-weight: 700; text-align: center; }

        /* 갤러리 */
        .gallery-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
        .gallery-item { border-radius: var(--radius); overflow: hidden; aspect-ratio: 3/4; }
        .gallery-item img { width: 100%; height: 100%; object-fit: cover; }

        /* --- PC (데스크탑) 스타일 --- */
        @media (min-width: 768px) {
            .container { padding: 0 40px; }
            /* PC에서는 다시 가로로 배치 */
            .hero-row {
                flex-direction: row;
                text-align: left;
                gap: 40px;
                justify-content: space-between;
            }
            .profile-box { order: 1; width: 100%; max-width: 300px; }
            .badges { justify-content: flex-start; }
            .hero-title { font-size: 2.5rem; }

            /* PC에서는 영상 크기를 다시 키움 */
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
            <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allowfullscreen></iframe></div>
                <div class="vcard-title">브랜드 라이브</div>
            </div>
            <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allowfullscreen></iframe></div>
                <div class="vcard-title">제품 런칭쇼</div>
            </div>
            <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allowfullscreen></iframe></div>
                <div class="vcard-title">기획 방송</div>
            </div>
             <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allowfullscreen></iframe></div>
                <div class="vcard-title">패션 하울</div>
            </div>
             <div class="vcard">
                <div class="video-frame"><iframe src="https://shoppinglive.naver.com/embed/YOUR_VIDEO_ID" allowfullscreen></iframe></div>
                <div class="vcard-title">소형 가전</div>
            </div>
        </div>
    </section>

    <section id="gallery" style="margin-bottom: 48px;">
        <h2>갤러리</h2>
        <div class="gallery-grid">
            <div class="gallery-item"><img src="gallery1.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=1'"></div>
            <div class="gallery-item"><img src="gallery2.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=2'"></div>
            <div class="gallery-item"><img src="gallery3.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=3'"></div>
            <div class="gallery-item"><img src="gallery4.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=4'"></div>
            <div class="gallery-item"><img src="gallery5.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=5'"></div>
            <div class="gallery-item"><img src="gallery6.jpg" alt="갤러리 이미지" onerror="this.src='https://via.placeholder.com/300x400/e0e7ff/333?text=6'"></div>
        </div>
    </section>
</main>

</body>
</html>
