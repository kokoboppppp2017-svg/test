# test
쇼호스트 포트폴리오 Type.1
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- 수정 필요: 브라우저 탭에 표시될 제목입니다. -->
    <title>쇼호스트 [이름] 포트폴리오</title>
    <style>
        /* 기본 스타일 */
        body {
            font-family: 'Helvetica Neue', Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
        }
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
        }
        h1, h2, h3 {
            color: #222;
        }
        h1 {
            font-size: 3em;
            margin-bottom: 0;
        }
        h2 {
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
            margin-top: 40px;
        }
        section {
            margin-bottom: 40px;
        }
        a {
            color: #007BFF;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }

        /* 헤더 & 이미지 슬라이더 */
        header {
            text-align: center;
            padding: 40px 0;
            background: linear-gradient(to right, #6a11cb, #2575fc);
            color: white;
        }
        header h1 {
            color: white;
        }
        .header-title {
            font-size: 1.5em;
            font-weight: 300;
            margin-top: 10px;
        }
        .slider-container {
            width: 100%;
            max-width: 800px;
            height: 400px; /* 슬라이더 높이 조절 */
            position: relative;
            overflow: hidden;
            margin: 20px auto 0;
            border-radius: 10px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        .slider-image {
            width: 100%;
            height: 100%;
            object-fit: cover; /* 이미지가 잘리지 않고 꽉 차게 */
            position: absolute;
            opacity: 0;
            transition: opacity 1s ease-in-out;
        }
        .slider-image.active {
            opacity: 1;
        }

        /* 경력 */
        .career-list {
            list-style: none;
            padding: 0;
        }
        .career-list li {
            margin-bottom: 15px;
            padding-left: 20px;
            border-left: 3px solid #007BFF;
        }
        .career-list strong {
            display: block;
            font-size: 1.1em;
        }

        /* 레퍼런스 영상 */
        .video-container {
            position: relative;
            padding-bottom: 56.25%; /* 16:9 비율 */
            height: 0;
            overflow: hidden;
            max-width: 100%;
            background: #000;
            margin-bottom: 20px;
        }
        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        
        /* SNS 링크 */
        .social-links {
            text-align: center;
            padding: 20px 0;
        }
        .social-links a {
            margin: 0 15px;
            font-size: 1.2em;
            font-weight: bold;
        }

        /* 갤러리 */
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
        }
        .gallery-grid img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }
        .gallery-grid img:hover {
            transform: scale(1.05);
        }

        /* 연락처 */
        .contact {
            text-align: center;
            background-color: #333;
            color: white;
            padding: 40px 20px;
        }
        .contact h2 {
            color: white;
            border: none;
        }
        .contact a {
            color: #fff;
            font-size: 1.2em;
            font-weight: bold;
            border: 2px solid white;
            padding: 10px 20px;
            border-radius: 5px;
            transition: background-color 0.3s, color 0.3s;
        }
        .contact a:hover {
            background-color: white;
            color: #333;
            text-decoration: none;
        }
    </style>
</head>
<body>

    <header>
        <!-- 수정 필요: 당신의 이름 -->
        <h1>김쇼호</h1>
        <!-- 수정 필요: 당신을 나타내는 멋진 타이틀 또는 캐치프레이즈 -->
        <p class="header-title">"단 1분 만에 시청자의 마음을 훔치는 마법사"</p>
        
        <div class="slider-container">
            <!-- 수정 필요: images 폴더에 있는 당신의 사진 파일명으로 변경 (총 3장) -->
            <img src="https://via.placeholder.com/800x400/007BFF/FFFFFF?text=Profile+Image+1" class="slider-image active" alt="프로필 사진 1">
            <img src="https://via.placeholder.com/800x400/28A745/FFFFFF?text=Profile+Image+2" class="slider-image" alt="프로필 사진 2">
            <img src="https://via.placeholder.com/800x400/DC3545/FFFFFF?text=Profile+Image+3" class="slider-image" alt="프로필 사진 3">
        </div>
    </header>

    <main class="container">
        <section id="about">
            <h2>About Me: 저를 소개합니다</h2>
            <!-- 수정 필요: 자신을 소개하는 글을 자유롭게 작성하세요. -->
            <p>
                안녕하세요! 시청자와의 완벽한 케미스트리를 자랑하는 쇼호스트 김쇼호입니다. 
                저는 단순히 제품을 판매하는 것을 넘어, 시청자와 함께 웃고 공감하며 즐거운 쇼핑 경험을 만드는 일에 가장 큰 보람을 느낍니다. 
                저의 긍정적인 에너지와 신뢰감 있는 목소리로 최고의 결과를 만들어내겠습니다.
            </p>
            <h3>성과 및 하이라이트</h3>
            <ul>
                <!-- 수정 필요: 당신의 주요 성과를 목록으로 작성하세요. -->
                <li>2025년 OOO 홈쇼핑 뷰티 카테고리 매출 1위 달성</li>
                <li>유튜브 라이브 커머스 동시 접속자 1만 명 기록</li>
                <li>2024년 대한민국 커머스 대상 '라이징 스타상' 수상</li>
            </ul>
        </section>

        <section id="career">
            <h2>Career: 걸어온 길</h2>
            <ul class="career-list">
                <!-- 수정 필요: 당신의 경력을 최신순으로 작성하세요. 이 항목을 복사해서 여러 개 추가할 수 있습니다. -->
                <li>
                    <strong>2023 - 현재: OOO 홈쇼핑</strong>
                    패션/뷰티 전문 쇼호스트
                </li>
                <li>
                    <strong>2021 - 2023: ABC 라이브 커머스</strong>
                    IT/가전 전문 쇼호스트
                </li>
                <li>
                    <strong>2020: 쇼호스트 아카데미</strong>
                    전문가 과정 수료
                </li>
            </ul>
        </section>

        <section id="videos">
            <h2>Reference Videos: 레퍼런스 영상</h2>
            <!-- 수정 필요: 유튜브 영상의 '공유' -> '퍼가기'에서 src="..." 부분만 복사하여 아래에 붙여넣으세요. -->
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </section>

        <section id="social">
            <h2>Social Links: 저를 더 알아보세요</h2>
            <div class="social-links">
                <!-- 수정 필요: 당신의 유튜브, 인스타그램 등 SNS 주소로 변경하세요. -->
                <a href="https://www.youtube.com" target="_blank">YouTube</a>
                <a href="https://www.instagram.com" target="_blank">Instagram</a>
            </div>
        </section>

        <section id="gallery">
            <h2>Gallery: 생생한 활동 모습</h2>
            <div class="gallery-grid">
                <!-- 수정 필요: images 폴더에 있는 당신의 활동 사진 파일명으로 변경하세요. 원하는 만큼 img 태그를 추가/삭제할 수 있습니다. -->
                <img src="https://via.placeholder.com/300x300/6f42c1/ffffff?text=Activity+1" alt="활동 사진 1">
                <img src="https://via.placeholder.com/300x300/fd7e14/ffffff?text=Activity+2" alt="활동 사진 2">
                <img src="https://via.placeholder.com/300x300/20c997/ffffff?text=Activity+3" alt="활동 사진 3">
                <img src="https://via.placeholder.com/300x300/e83e8c/ffffff?text=Activity+4" alt="활동 사진 4">
                <img src="https://via.placeholder.com/300x300/17a2b8/ffffff?text=Activity+5" alt="활동 사진 5">
                <img src="https://via.placeholder.com/300x300/ffc107/ffffff?text=Activity+6" alt="활동 사진 6">
            </div>
        </section>
    </main>

    <footer class="contact" id="contact">
        <h2>Contact Me</h2>
        <p>함께 최고의 결과를 만들고 싶으시다면, 아래 버튼을 눌러 저에게 연락주세요.</p>
        <!-- 수정 필요: 당신의 이메일 주소로 변경하세요. -->
        <a href="mailto:youremail@example.com">이메일 보내기</a>
    </footer>

    <script>
        // 이미지 슬라이더 로직
        document.addEventListener('DOMContentLoaded', function() {
            const images = document.querySelectorAll('.slider-image');
            let currentImageIndex = 0;

            function showNextImage() {
                images[currentImageIndex].classList.remove('active');
                currentImageIndex = (currentImageIndex + 1) % images.length;
                images[currentImageIndex].classList.add('active');
            }

            setInterval(showNextImage, 3000); // 3초마다 이미지 변경
        });
    </script>

</body>
</html>
