<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>[당신 이름] | 쇼호스트 포트폴리오</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css">
<link href="https://cdn.jsdelivr.net/npm/remixicon@4.2.0/fonts/remixicon.css" rel="stylesheet"/>
<style>
:root{
  --bg:#f8f9fc; --accent:#6c8ee3; --text:#0f172a; --muted:#64748b;
  --kakao:#fee500; --card:#fff; --radius:16px; --shadow: 0 8px 25px rgba(0,0,0,0.05);
}
*{box-sizing:border-box} html{scroll-behavior:smooth}
body{margin:0;font-family:"Pretendard",sans-serif;background:var(--bg);color:var(--text);-webkit-font-smoothing:antialiased}
a{color:inherit;text-decoration:none}
.container{max-width:1100px;margin:0 auto;padding:0 20px}
h2.section-title{font-size:22px;font-weight:900;text-align:center;margin-bottom:24px}

/* Header */
header{position:sticky;top:0;z-index:1100;background:rgba(255,255,255,0.85);backdrop-filter:blur(8px);border-bottom:1px solid #eef2f7}
.nav-inner{display:flex;align-items:center;justify-content:space-between;height:60px}
.logo{font-weight:900;font-size:20px}
.nav{display:none;gap:24px;font-weight:700}
@media(min-width:768px){.nav{display:flex}}

/* Hero (Hook) - 모바일에서도 좌우 배치 유지 */
.hero{padding:32px 0}
.hero-grid{display:flex;align-items:center;gap:20px}
.hero-text{flex:1.2;min-width:0}
.hero-image{flex:1;min-width:0}
.hero-text .name{font-weight:800;font-size:16px;color:var(--accent)}
.hero-text .tagline{font-size:clamp(1.7rem, 6vw, 2.5rem);font-weight:900;margin:8px 0;line-height:1.2;letter-spacing:-0.03em}
.hero-text .subtitle{font-size:clamp(0.9rem, 2.5vw, 1rem);color:var(--muted);font-weight:500}
.profile-wrap{width:100%;border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);aspect-ratio:3/4}
.profile-img{width:100%;height:100%;object-fit:cover}

/* Strengths (Why Me?) */
.strengths{padding:48px 0}
.strengths-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:20px}
.strength-card{background:var(--card);padding:24px;border-radius:var(--radius);box-shadow:var(--shadow);text-align:center}
.strength-card .icon{font-size:2.5rem;color:var(--accent);margin-bottom:12px}
.strength-card h3{margin:0 0 8px;font-size:18px}
.strength-card p{color:var(--muted);font-size:15px;line-height:1.6;margin:0}

/* Videos (Proof) */
.videos{padding:32px 0}
.videos-viewport{margin:0 -20px;position:relative}
.videos-row{display:flex;gap:16px;padding:12px 20px;overflow-x:auto;scroll-snap-type:x mandatory;-webkit-overflow-scrolling:touch}
.vcard{flex:0 0 60%;scroll-snap-align:center;background:var(--card);border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow)}
.vwrap{position:relative;padding-top:177.77%;background:#111}
.vcard iframe{position:absolute;inset:0;width:100%;height:100%;border:0}
.vcard-title{font-weight:700;padding:12px;font-size:15px}
@media(min-width:768px){.vcard{flex:0 0 40%}}
@media(min-width:1024px){.videos-row{display:grid;grid-template-columns:repeat(4,1fr);overflow:visible;padding:12px 0}.vcard{flex:auto}}

/* Gallery */
.gallery{padding:32px 0}
.gallery-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.gallery-item{border-radius:var(--radius);overflow:hidden;aspect-ratio:3/4;box-shadow:var(--shadow)}
.gallery-item img{width:100%;height:100%;object-fit:cover;transition:transform .3s}
.gallery-item:hover img{transform:scale(1.05)}
@media(min-width:768px){.gallery-grid{grid-template-columns:repeat(4,1fr);gap:20px}}

/* Contact */
.contact{padding:48px 0}
.contact-box{background:var(--card);border-radius:24px;box-shadow:var(--shadow);padding:32px;text-align:center}
.contact-box .title{font-size:20px;font-weight:900}
.contact-box .desc{color:var(--muted);font-weight:500;margin:8px 0 24px}
.contact-box .btn-row{display:flex;flex-direction:column;gap:12px;max-width:300px;margin:0 auto}
.btn-kakao{background:var(--kakao);color:#3c1e1e;padding:14px;border-radius:12px;font-weight:800;display:flex;align-items:center;justify-content:center;gap:8px}
.btn-pdf{border:2px solid #eef2f7;background:#f8f9fc;color:var(--text);padding:14px;border-radius:12px;font-weight:800;display:flex;align-items:center;justify-content:center;gap:8px}
@media(min-width:768px){.contact-box .btn-row{flex-direction:row}}

/* Scrollbar Style */
.videos-row::-webkit-scrollbar{height:8px}
.videos-row::-webkit-scrollbar-thumb{background:rgba(0,0,0,0.15);border-radius:8px}
</style>
</head>
<body>
<header>
  <div class="container nav-inner">
    <!-- [교체] 당신의 이름 또는 로고 -->
    <div class="logo">HYERIN</div>
    <nav class="nav" aria-label="메인 내비게이션">
      <a href="#strengths">소개</a>
      <a href="#videos">레퍼런스</a>
      <a href="#gallery">갤러리</a>
      <a href="#contact">연락처</a>
    </nav>
  </div>
</header>

<main>
  <section class="hero container" id="hero">
    <div class="hero-grid">
      <div class="hero-text">
        <!-- [교체] 당신의 이름 -->
        <div class="name">쇼호스트 OOO</div>
        <!-- [교체] 당신의 핵심 캐치프레이즈 -->
        <div class="tagline">1분 만에 시청자를
구매자로 바꿉니다</div>
        <div class="subtitle">콘텐츠 기획부터 라이브 진행, 판매까지. 매출로 증명합니다.</div>
      </div>
      <div class="hero-image">
        <div class="profile-wrap">
          <!-- [교체] 당신의 프로필 사진 파일명 -->
          <img src="profile1.jpg" alt="프로필 사진" class="profile-img" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=Profile'">
        </div>
      </div>
    </div>
  </section>

  <section class="strengths container" id="strengths">
    <h2 class="section-title">왜 OOO와 함께해야 할까요?</h2>
    <div class="strengths-grid">
      <div class="strength-card">
        <div class="icon"><i class="ri-line-chart-line"></i></div>
        <h3>검증된 판매 실력</h3>
        <p>숫자가 증명합니다. 2024년 뷰티 카테고리 라이브 방송 평균 전환율 15% 달성. 목표 매출을 현실로 만듭니다.</p>
      </div>
      <div class="strength-card">
        <div class="icon"><i class="ri-vidicon-line"></i></div>
        <h3>기획부터 진행까지 All-in-One</h3>
        <p>콘텐츠 기획, 대본, 진행까지 한번에. 브랜드의 매력을 극대화하는 라이브 방송을 직접 설계하고 실행합니다.</p>
      </div>
      <div class="strength-card">
        <div class="icon"><i class="ri-sparkling-2-line"></i></div>
        <h3>뷰티 & 패션 전문성</h3>
        <p>100개 이상의 브랜드 협업 경험. 최신 트렌드를 꿰뚫는 깊이 있는 분석으로 고객의 마음을 사로잡습니다.</p>
      </div>
    </div>
  </section>

  <section class="videos" id="videos">
    <div class="container"><h2 class="section-title">레퍼런스 영상</h2></div>
    <div class="videos-viewport">
      <div class="videos-row" id="videosRow">
        <!-- [교체] 유튜브 영상 ID (주소창의 v= 뒤 코드)와 제목 -->
        <div class="vcard">
          <div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_1?rel=0&playsinline=1" allowfullscreen></iframe></div>
          <div class="vcard-title"><OOO 브랜드> 뷰티 라이브</div>
        </div>
        <div class="vcard">
          <div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_2?rel=0&playsinline=1" allowfullscreen></iframe></div>
          <div class="vcard-title"><ABC 가전> 신제품 런칭쇼</div>
        </div>
        <div class="vcard">
          <div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_3?rel=0&playsinline=1" allowfullscreen></iframe></div>
          <div class="vcard-title"><개인 채널> 패션 하울</div>
        </div>
        <div class="vcard">
          <div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_4?rel=0&playsinline=1" allowfullscreen></iframe></div>
          <div class="vcard-title"><D-Brand> 팝업스토어 현장 스케치</div>
        </div>
      </div>
    </div>
  </section>

  <section class="gallery container" id="gallery">
    <h2 class="section-title">갤러리</h2>
    <div class="gallery-grid">
      <!-- [교체] 8장의 갤러리 이미지 파일명 -->
      <div class="gallery-item"><img src="gallery1.jpg" alt="갤러리 이미지 1" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=1'"></div>
      <div class="gallery-item"><img src="gallery2.jpg" alt="갤러리 이미지 2" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=2'"></div>
      <div class="gallery-item"><img src="gallery3.jpg" alt="갤러리 이미지 3" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=3'"></div>
      <div class="gallery-item"><img src="gallery4.jpg" alt="갤러리 이미지 4" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=4'"></div>
      <div class="gallery-item"><img src="gallery5.jpg" alt="갤러리 이미지 5" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=5'"></div>
      <div class="gallery-item"><img src="gallery6.jpg" alt="갤러리 이미지 6" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=6'"></div>
      <div class="gallery-item"><img src="gallery7.jpg" alt="갤러리 이미지 7" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=7'"></div>
      <div class="gallery-item"><img src="gallery8.jpg" alt="갤러리 이미지 8" onerror="this.src='https://via.placeholder.com/600x800/e0e7ff/333?text=8'"></div>
    </div>
  </section>

  <section class="contact container" id="contact">
    <div class="contact-box">
      <div class="title">함께 매출을 만들 준비되셨나요?</div>
      <div class="desc">프로젝트, 콜라보, 채용 문의는 아래로 편하게 연락 주세요.</div>
      <div class="btn-row">
        <!-- [교체] 당신의 카카오톡 오픈채팅 링크 -->
        <a class="btn-kakao" href="https://open.kakao.com/o/YOUR_LINK" target="_blank"><i class="ri-kakao-talk-fill"></i>오픈채팅으로 문의하기</a>
        <!-- [교체] 당신의 이력서 PDF 파일명 -->
        <a class="btn-pdf" href="resume.pdf" download><i class="ri-download-2-line"></i>이력서(PDF) 다운로드</a>
      </div>
    </div>
  </section>
</main>

<script>
/* 가로 스크롤 터치 드래그 지원 (모바일용) */
(function(){
  const slider = document.getElementById('videosRow');
  if(!slider) return;
  let isDown=false, startX, scrollLeft;
  slider.addEventListener('pointerdown', e=>{ isDown=true; slider.style.cursor='grabbing'; startX=e.pageX-slider.offsetLeft; scrollLeft=slider.scrollLeft; });
  slider.addEventListener('pointerleave', ()=>{ isDown=false; slider.style.cursor='grab'; });
  slider.addEventListener('pointerup', ()=>{ isDown=false; slider.style.cursor='grab'; });
  slider.addEventListener('pointermove', e=>{ if(!isDown) return; e.preventDefault(); const x=e.pageX-slider.offsetLeft; const walk=(x-startX)*2; slider.scrollLeft=scrollLeft-walk; });
})();
</script>
</body>
</html>
