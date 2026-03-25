# test
쇼호스트 포트폴리오 Type.1
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>쇼호스트 포트폴리오</title>
<style>
  /* 모바일 우선 기본 스타일 */
  :root{
    --text:#222;
    --muted:#666;
    --accent:#7aa2ff;
    --bg1:#f7f6ff; /* pastel base */
    --bg2:#fffaf6; /* alternate pastel */
    --card:#ffffff;
    --radius:12px;
  }
  *{box-sizing:border-box}
  body{
    margin:0;
    font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Noto Sans KR","Apple SD Gothic Neo",Arial;
    color:var(--text);
    background: linear-gradient(180deg,var(--bg1),var(--bg2));
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
    line-height:1.45;
  }
  a{color:var(--accent); text-decoration:none}
  .container{padding:16px; max-width:1100px; margin:0 auto}

  /* Header */
  header{
    padding:18px 16px 8px;
    text-align:center;
  }
  .name{
    font-size:1.6rem;
    font-weight:700;
    margin:0;
    letter-spacing:-0.02em;
  }
  .tagline{
    margin-top:6px;
    font-size:0.98rem;
    color:var(--muted);
  }

  /* 이미지 슬라이더 (간단 자동재생) */
  .slider{
    margin:14px auto;
    width:100%;
    max-width:900px;
    height:260px;
    border-radius:var(--radius);
    overflow:hidden;
    box-shadow:0 8px 20px rgba(20,20,30,0.06);
    position:relative;
    background:linear-gradient(135deg, rgba(255,255,255,0.6), rgba(255,255,255,0.4));
  }
  .slide-img{
    position:absolute;
    inset:0;
    width:100%;
    height:100%;
    object-fit:cover;
    opacity:0;
    transition:opacity .9s ease;
  }
  .slide-img.active{opacity:1}

  /* 섹션 기본 */
  section{margin-top:18px}
  h2{font-size:1.05rem; margin:0 0 10px 0}
  p{margin:0 0 10px 0}

  /* About 카드 */
  .card{
    background:var(--card);
    border-radius:var(--radius);
    padding:14px;
    box-shadow:0 6px 18px rgba(15,20,30,0.04);
  }

  /* Career list */
  .career-list{padding:0; margin:0; list-style:none}
  .career-item{padding:10px 0; border-left:3px solid rgba(122,162,255,0.25); margin-left:8px}
  .career-item strong{display:block; font-weight:600}

  /* Reference videos: 모바일 우선: 가로 스크롤 컨테이너 (2개 visible) */
  .videos-viewport{
    width:100%;
    overflow:hidden;
  }
  .videos-row{
    display:flex;
    gap:12px;
    padding:8px 6px;
    overflow-x:auto;
    scroll-snap-type:x mandatory;
    -webkit-overflow-scrolling:touch;
  }
  .video-card{
    flex:0 0 calc(50% - 12px); /* 모바일에서 한 화면에 2개 */
    scroll-snap-align:center;
    background:var(--card);
    border-radius:10px;
    overflow:hidden;
    box-shadow:0 6px 18px rgba(15,20,30,0.04);
  }
  .video-card .video-wrap{
    position:relative;
    width:100%;
    /* 세로형 영상에 맞춘 높이: 16:9보다 더 세로형을 위한 기본 */
    padding-top:160%; /* 세로 비디오(예: 9:16)을 가정해 높게 잡음 */
    background:#000;
  }
  .video-card iframe{
    position:absolute;
    top:0; left:0;
    width:100%; height:100%;
    border:0;
  }
  .videos-controls{
    display:flex; justify-content:flex-end; gap:8px; margin-top:8px;
  }

  /* Gallery - 좀 더 생동감 있게 카드형 그리드 */
  .gallery-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:10px;
  }
  .gallery-item{
    background:linear-gradient(180deg, rgba(255,255,255,0.8), rgba(250,250,255,1));
    border-radius:10px;
    overflow:hidden;
    box-shadow:0 6px 18px rgba(15,20,30,0.04);
  }
  .gallery-item img{
    width:100%; height:220px; object-fit:cover; display:block;
    transition:transform .35s ease;
  }
  .gallery-item:hover img{transform:scale(1.04)}

  /* Contact footer */
  .contact{
    margin-top:18px;
    padding:18px;
    border-radius:12px;
    background:linear-gradient(90deg,#fff,#fafcff);
    text-align:center;
  }
  .contact a{
    display:inline-block;
    margin-top:10px;
    padding:10px 16px;
    border-radius:8px;
    background:var(--accent); color:#fff; font-weight:600;
  }

  /* Desktop / larger screens */
  @media(min-width:900px){
    header{padding:28px 0}
    .name{font-size:2.2rem}
    .tagline{font-size:1.05rem}
    .slider{height:380px}
    .card{padding:20px}

    /* Videos: desktop shows 4 at once in a grid */
    .videos-row{
      display:grid;
      grid-template-columns:repeat(4,1fr);
      gap:16px;
      overflow:visible;
      padding:0;
    }
    .video-card{flex:1; padding:0}
    .video-card .video-wrap{padding-top:150%} /* 데스크탑에서 세로비디오 비율 조정 가능 */

    /* gallery: 3 or 4 column */
    .gallery-grid{grid-template-columns:repeat(3,1fr); gap:14px}
    .gallery-item img{height:160px}
  }

  @media(min-width:1200px){
    .slider{height:440px}
    .gallery-grid{grid-template-columns:repeat(4,1fr)}
    .gallery-item img{height:180px}
  }

  /* small polish: hide scrollbars for iOS/Android nicer look */
  .videos-row::-webkit-scrollbar{height:8px}
  .videos-row::-webkit-scrollbar-thumb{background:rgba(0,0,0,0.12); border-radius:8px}
</style>
</head>
<body>
  <div class="container">
    <header>
      <!-- 수정: 이름 -->
      <h1 class="name">김쇼호</h1>
      <!-- 수정: 캐치프레이즈 -->
      <div class="tagline">"1분 만에 마음을 사로잡는 라이브 커머스 크리에이터"</div>

      <div class="slider" aria-hidden="false">
        <!-- 교체: 실제 프로필 이미지 URL 또는 로컬 경로로 바꾸세요 -->
        <img class="slide-img active" src="https://via.placeholder.com/1200x800/ffd6e8/30203a?text=Profile+1" alt="프로필1">
        <img class="slide-img" src="https://via.placeholder.com/1200x800/d6f6ff/30203a?text=Profile+2" alt="프로필2">
        <img class="slide-img" src="https://via.placeholder.com/1200x800/e9ffd6/30203a?text=Profile+3" alt="프로필3">
      </div>
    </header>

    <main>
      <section id="about" class="card">
        <h2>About Me</h2>
        <p>안녕하세요! 시청자 공감형 쇼호스트 김쇼호입니다. 밝은 에너지와 설득력 있는 스토리텔링으로 판매 전환을 만듭니다.</p>
        <h3 style="margin-top:10px; font-size:0.95rem">Highlights</h3>
        <ul style="padding-left:18px; margin:8px 0 0 0; color:var(--muted)">
          <li>2025 OOO 홈쇼핑 뷰티 카테고리 매출 1위</li>
          <li>유튜브 라이브 최고 동시접속 1만명</li>
          <li>2024 대한민국 커머스 대상 수상</li>
        </ul>
      </section>

      <section id="career" style="margin-top:12px">
        <h2>Career</h2>
        <div class="card">
          <ul class="career-list">
            <li class="career-item"><strong>2023 - 현재: OOO 홈쇼핑</strong> 패션/뷰티 전문 쇼호스트</li>
            <li class="career-item"><strong>2021 - 2023: ABC 라이브</strong> IT/가전 라이브 진행</li>
            <li class="career-item"><strong>2020: 쇼호스트 아카데미</strong> 전문가 과정 수료</li>
          </ul>
        </div>
      </section>

      <section id="videos" style="margin-top:12px">
        <h2>Reference Videos</h2>
        <div class="videos-viewport">
          <div class="videos-row" id="videosRow">
            <!-- 수정: 유튜브 세로(포트레이트) 영상 4개. iframe src를 자신의 영상으로 교체하세요. -->
            <div class="video-card">
              <div class="video-wrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_1?rel=0&playsinline=1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
            </div>
            <div class="video-card">
              <div class="video-wrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_2?rel=0&playsinline=1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
            </div>
            <div class="video-card">
              <div class="video-wrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_3?rel=0&playsinline=1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
            </div>
            <div class="video-card">
              <div class="video-wrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_4?rel=0&playsinline=1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
            </div>
          </div>
        </div>
      </section>

      <section id="social" style="margin-top:12px">
        <h2>Social</h2>
        <div class="card" style="display:flex; gap:10px; justify-content:center; flex-wrap:wrap">
          <!-- 수정: 링크 교체 -->
          <a href="https://www.youtube.com" target="_blank" style="padding:8px 12px; border-radius:8px; background:#fff;">YouTube</a>
          <a href="https://www.instagram.com" target="_blank" style="padding:8px 12px; border-radius:8px; background:#fff;">Instagram</a>
        </div>
      </section>

      <section id="gallery" style="margin-top:12px">
        <h2>Gallery</h2>
        <div class="gallery-grid" id="galleryGrid">
          <!-- 수정: 실제 활동 사진으로 교체 -->
          <div class="gallery-item"><img src="https://via.placeholder.com/800x600/ffd6e8/222?text=Activity+1" alt=""></div>
          <div class="gallery-item"><img src="https://via.placeholder.com/800x600/d6f6ff/222?text=Activity+2" alt=""></div>
          <div class="gallery-item"><img src="https://via.placeholder.com/800x600/e9ffd6/222?text=Activity+3" alt=""></div>
          <div class="gallery-item"><img src="https://via.placeholder.com/800x600/fff1d6/222?text=Activity+4" alt=""></div>
          <div class="gallery-item"><img src="https://via.placeholder.com/800x600/f0e6ff/222?text=Activity+5" alt=""></div>
        </div>
      </section>

      <section id="contact" style="margin-top:14px">
        <div class="contact">
          <h2>Contact Me</h2>
          <p style="color:var(--muted)">함께 일해보고 싶으시면 편하게 연락주세요.</p>
          <!-- 수정: 메일 주소 교체 -->
          <a href="mailto:youremail@example.com">이메일 보내기</a>
        </div>
      </section>
    </main>
  </div>

<script>
  // 이미지 슬라이더 (간단)
  (function(){
    const imgs = document.querySelectorAll('.slide-img');
    let idx = 0;
    if(!imgs.length) return;
    setInterval(()=>{
      imgs[idx].classList.remove('active');
      idx = (idx+1)%imgs.length;
      imgs[idx].classList.add('active');
    }, 3500);
  })();

  // 가로 스크롤에서 터치/드래그로 깔끔하게 스와이프 되게끔(선택적)
  (function(){
    const slider = document.getElementById('videosRow');
    if(!slider) return;
    let pos = {startX:0, scrollLeft:0, isDown:false};
    slider.addEventListener('pointerdown', (e)=>{
      pos.isDown=true;
      pos.startX = e.clientX;
      pos.scrollLeft = slider.scrollLeft;
      slider.style.cursor='grabbing';
    });
    slider.addEventListener('pointerup', ()=>{ pos.isDown=false; slider.style.cursor=''; });
    slider.addEventListener('pointerleave', ()=>{ pos.isDown=false; slider.style.cursor=''; });
    slider.addEventListener('pointermove', (e)=>{
      if(!pos.isDown) return;
      const dx = e.clientX - pos.startX;
      slider.scrollLeft = pos.scrollLeft - dx;
    });
  })();
</script>
</body>
</html>
