# test
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>[당신 이름] | 쇼호스트 포트폴리오</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css">
<style>
:root{
  --bg:#fbfafc; --accent:#8aaedb; --text:#0f172a; --muted:#64748b;
  --kakao:#fee500; --card:#fff; --radius:14px;
}
*{box-sizing:border-box} html{scroll-behavior:smooth}
body{margin:0;font-family:"Pretendard",system-ui,-apple-system,Segoe UI,Roboto,"Noto Sans KR";background:var(--bg);color:var(--text);-webkit-font-smoothing:antialiased}
a{color:inherit;text-decoration:none}
.container{max-width:1150px;margin:0 auto;padding:0 16px}

/* Header */
header{position:sticky;top:0;z-index:1100;background:rgba(255,255,255,0.95);backdrop-filter:blur(6px);border-bottom:1px solid rgba(15,23,42,0.06)}
.nav-inner{display:flex;align-items:center;justify-content:space-between;padding:12px 16px}
.logo{font-weight:900;font-size:18px}
.nav{display:flex;gap:18px;font-weight:800}
.nav a{padding:8px 6px;border-radius:8px;color:var(--text)}
.nav a:hover{background:rgba(138,174,219,0.12);color:var(--accent)}
@media(max-width:900px){.nav{gap:10px;font-size:14px} }

/* Hero */
.hero{display:flex;flex-direction:column;gap:18px;padding:20px 0;align-items:stretch}
.hero-row{display:flex;flex-direction:column;gap:16px;align-items:stretch}
.title-wrap{display:flex;flex-direction:column;gap:6px}
.name{font-size:20px;font-weight:900}
.tagline{font-weight:900;font-size:26px;line-height:1.03}
.subtitle{color:var(--muted);font-weight:600;font-size:15px}

/* Profile 3:4 */
.profile-wrap{width:100%;max-width:420px;border-radius:16px;overflow:hidden;box-shadow:0 10px 30px rgba(10,20,30,0.06);background:linear-gradient(180deg,#fff,#fbfbff);margin-left:auto}
.profile-img{width:100%;height:0;padding-top:133.3333%;position:relative}
.profile-img img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;opacity:0;transition:opacity .9s}
.profile-img img.active{opacity:1}

/* About */
.about{padding:0}
.about h2{font-size:16px;margin:12px 0 8px}
.about p{color:var(--muted);font-size:15px;line-height:1.6}

/* Videos */
.videos-viewport{margin-top:18px;overflow:hidden}
.videos-row{
  display:flex;
  gap:12px;
  padding:10px 6px;
  overflow-x:auto;
  scroll-snap-type:x mandatory;
  -webkit-overflow-scrolling:touch;
  align-items:flex-start;
}
/* 모바일: 한 화면에 2개 보이도록 폭 설정 */
.vcard{
  flex:0 0 calc(50% - 12px); /* 모바일에서 2개 보임 */
  background:var(--card);
  border-radius:12px;
  overflow:hidden;
  scroll-snap-align:center;
  box-shadow:0 6px 18px rgba(10,20,30,0.05);
}
.vwrap{position:relative;padding-top:177.7778%} /* 세로형 영상 넉넉하게 확보 */
.vcard iframe{position:absolute;inset:0;width:100%;height:100%;border:0}

/* Gallery */
.gallery{margin-top:18px;display:grid;grid-template-columns:repeat(2,1fr);gap:10px}
.gallery-item{border-radius:12px;overflow:hidden;box-shadow:0 8px 20px rgba(10,20,30,0.04)}
.gallery-item img{width:100%;height:220px;object-fit:cover;display:block;transition:transform .35s}
.gallery-item:hover img{transform:scale(1.04)}

/* Contact */
.contact{margin-top:18px;padding:18px;border-radius:18px;background:linear-gradient(90deg,#fff,#fcfcff);box-shadow:0 12px 30px rgba(10,20,30,0.04);display:grid;grid-template-columns:1fr;gap:12px;align-items:center}
.contact .title{font-size:20px;font-weight:900}
.contact .desc{color:var(--muted);font-weight:600}
.contact .btn-row{display:flex;gap:12px;flex-wrap:wrap}
.btn-kakao{background:var(--kakao);color:#3c1e1e;padding:14px 18px;border-radius:12px;font-weight:900;border:none;display:inline-flex;align-items:center;gap:10px}
.btn-pdf{padding:12px 16px;border-radius:12px;border:2px dashed #e6e9ef;background:#f8fafc;color:var(--text);font-weight:800}
.email-line{margin-top:8px;color:var(--muted);font-weight:700}

/* Desktop */
@media(min-width:900px){
  .hero{padding:36px 0}
  .hero-row{flex-direction:row;align-items:flex-start;gap:28px}
  .title-wrap{flex:1}
  .profile-wrap{flex:0 0 360px;max-width:360px}
  .tagline{font-size:34px;text-align:left}
  .subtitle{text-align:left}
  .videos-row{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;overflow:visible;padding:0}
  .vcard{flex:none}
  .vwrap{padding-top:150%}
  .gallery{grid-template-columns:repeat(4,1fr);gap:14px}
  .contact{grid-template-columns:1.2fr 1fr;align-items:center}
}

/* small scrollbar styling */
.videos-row::-webkit-scrollbar{height:8px}
.videos-row::-webkit-scrollbar-thumb{background:rgba(0,0,0,0.12);border-radius:8px}
</style>
</head>
<body>
<header>
  <div class="container nav-inner">
    <div class="logo">[당신 이름]</div>
    <nav class="nav" aria-label="메인 내비게이션">
      <a href="#about">소개</a>
      <a href="#results">성과</a>
      <a href="#videos">레퍼런스</a>
      <a href="#gallery">갤러리</a>
      <a href="#contact">연락처</a>
    </nav>
  </div>
</header>

<main class="container">
  <section class="hero" id="top">
    <div class="hero-row">
      <div class="title-wrap">
        <div class="name">[당신 이름]</div>
        <div class="tagline">"1분 만에 마음을 사로잡는 라이브 커머스 크리에이터"</div>
        <div class="subtitle">콘텐츠·진행·설득까지, 매출로 연결되는 진행을 설계합니다.</div>

        <div class="about" id="about">
          <h2>About Me</h2>
          <p>안녕하세요. 시청자 공감형 쇼호스트 [이름]입니다. 밝은 에너지와 신뢰감 있는 전달로 제품의 가치를 명확히 전달합니다.</p>

          <h3 style="margin-top:12px">Highlights</h3>
          <ul style="color:var(--muted);padding-left:18px;margin-top:8px">
            <li>2025 OOO 홈쇼핑 뷰티 카테고리 매출 1위</li>
            <li>유튜브 라이브 최고 동시접속 1만명</li>
            <li>2024 대한민국 커머스 대상 수상</li>
          </ul>
        </div>
      </div>

      <div class="profile-wrap" aria-hidden="false">
        <div class="profile-img" id="profileSlider">
          <img src="profile1.jpg" alt="프로필1" class="active" onerror="this.src='https://via.placeholder.com/600x800?text=Profile+1'">
          <img src="profile2.jpg" alt="프로필2" onerror="this.src='https://via.placeholder.com/600x800?text=Profile+2'">
          <img src="profile3.jpg" alt="프로필3" onerror="this.src='https://via.placeholder.com/600x800?text=Profile+3'">
        </div>
      </div>
    </div>
  </section>

  <section id="results" style="margin-top:6px">
    <h2 style="font-size:18px;margin-bottom:8px">성과</h2>
    <div style="color:var(--muted)">카테고리별 매출 성장 사례 및 팝업스토어 성과 등 (구체 수치 삽입)</div>
  </section>

  <section id="videos">
    <h2 style="font-size:18px;margin-top:18px">Reference Videos</h2>
    <div class="videos-viewport">
      <div class="videos-row" id="videosRow">
        <!-- 본인 유튜브 embed ID로 교체 -->
        <div class="vcard"><div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_1?rel=0&playsinline=1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div></div>
        <div class="vcard"><div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_2?rel=0&playsinline=1" allowfullscreen></iframe></div></div>
        <div class="vcard"><div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_3?rel=0&playsinline=1" allowfullscreen></iframe></div></div>
        <div class="vcard"><div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_4?rel=0&playsinline=1" allowfullscreen></iframe></div></div>
      </div>
    </div>
  </section>

  <section id="gallery">
    <h2 style="font-size:18px;margin-top:18px">Gallery</h2>
    <div class="gallery" aria-label="활동 사진">
      <div class="gallery-item"><img src="act1.jpg" alt="활동1" onerror="this.src='https://via.placeholder.com/400x600'"></div>
      <div class="gallery-item"><img src="act2.jpg" alt="활동2" onerror="this.src='https://via.placeholder.com/400x600'"></div>
      <div class="gallery-item"><img src="act3.jpg" alt="활동3" onerror="this.src='https://via.placeholder.com/400x600'"></div>
      <div class="gallery-item"><img src="act4.jpg" alt="활동4" onerror="this.src='https://via.placeholder.com/400x600'"></div>
    </div>
  </section>

  <section id="contact">
    <h2 style="font-size:18px;margin-top:18px">Contact</h2>
    <div class="contact">
      <div>
        <div class="title">오픈카톡이 가장 빠릅니다</div>
        <div class="desc">브랜드의 가치를 높이는 협업 제안을 기다립니다.</div>
      </div>

      <div class="btn-row">
        <a class="btn-kakao" href="https://open.kakao.com/o/YOUR_LINK" target="_blank">카톡 문의하기</a>
        <a class="btn-pdf" href="resume.pdf" download>이력서(PDF) 다운로드</a>
      </div>

      <div class="email-line">youremail@example.com</div>
    </div>
  </section>
</main>

<script>
/* profile slider auto */
(function(){
  const imgs = document.querySelectorAll('#profileSlider img');
  let i=0;
  if(!imgs.length) return;
  setInterval(()=>{
    imgs[i].classList.remove('active');
    i=(i+1)%imgs.length;
    imgs[i].classList.add('active');
  },3500);
})();

/* horizontal drag for videos row (mobile swipe) */
(function(){
  const slider = document.getElementById('videosRow');
  if(!slider) return;
  let down=false,startX,scrollLeft;
  slider.addEventListener('pointerdown', e=>{ down=true; startX=e.clientX; scrollLeft=slider.scrollLeft; slider.setPointerCapture(e.pointerId); });
  slider.addEventListener('pointerup', e=>{ down=false; try{ slider.releasePointerCapture(e.pointerId);}catch{} });
  slider.addEventListener('pointerleave', e=>{ down=false; });
  slider.addEventListener('pointermove', e=>{ if(!down) return; const dx = e.clientX - startX; slider.scrollLeft = scrollLeft - dx; });
})();
</script>
</body>
</html>
