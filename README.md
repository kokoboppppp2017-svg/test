<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>[당신 이름] | 포트폴리오</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css">
<link href="https://cdn.jsdelivr.net/npm/remixicon@4.2.0/fonts/remixicon.css" rel="stylesheet"/>
<style>
:root{
  --bg:#f8f9fc; --accent:#4f78d1; --text:#0f172a; --muted:#6b7280;
  --kakao:#fee500; --card:#fff; --radius:14px; --gap:12px; --shadow:0 10px 30px rgba(15,23,42,0.06);
}
*{box-sizing:border-box} html{scroll-behavior:smooth}
body{margin:0;font-family:"Pretendard",system-ui,-apple-system,Segoe UI,Roboto,"Noto Sans KR";background:var(--bg);color:var(--text);-webkit-font-smoothing:antialiased}
.container{max-width:1100px;margin:0 auto;padding:0 18px}

/* Header */
header{position:sticky;top:0;z-index:1100;background:rgba(255,255,255,0.9);backdrop-filter:blur(6px);border-bottom:1px solid #eef2f7}
.nav-inner{display:flex;align-items:center;justify-content:space-between;height:64px;padding:0 6px}
.logo{font-weight:900;font-size:18px}
.nav{display:none;gap:20px;font-weight:700}
@media(min-width:768px){.nav{display:flex}}

/* Hero: 텍스트 왼쪽, 사진 오른쪽 (모바일 유지) */
.hero{padding:28px 0}
.hero-row{display:flex;align-items:center;gap:20px}
.hero-text{flex:1;min-width:0}
.hero-name{font-size:22px;font-weight:800;color:var(--accent);margin-bottom:6px}
.hero-title{font-size:clamp(1.6rem,5.5vw,2.2rem);font-weight:900;line-height:1.08;margin-bottom:10px}
.hero-sub{color:var(--muted);font-size:15px;margin-bottom:12px}

/* keyword badges */
.badges{display:flex;flex-wrap:wrap;gap:8px}
.badge{background:#eef5ff;color:var(--accent);padding:8px 12px;border-radius:999px;font-weight:800;font-size:13px;box-shadow:0 6px 16px rgba(79,120,209,0.06)}

/* profile 3:4 box */
.profile-box{flex:0 0 320px;max-width:320px;border-radius:16px;overflow:hidden;background:var(--card);box-shadow:var(--shadow);height:auto}
.profile-img{width:100%;display:block;aspect-ratio:3/4;object-fit:cover}

/* strengths */
.strengths{padding:36px 0}
.str-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:16px}
.str-card{background:var(--card);padding:18px;border-radius:12px;box-shadow:var(--shadow);text-align:center}
.str-icon{font-size:28px;color:var(--accent);margin-bottom:8px}
.str-title{font-weight:800;margin-bottom:6px}
.str-desc{color:var(--muted);font-size:14px}

/* Videos: 모바일에서 2개 보이도록 카드 폭 설정 */
/* 영상은 9:16 고정. card-padding은 gap만큼 고려 */
.videos{padding:20px 0}
.videos-row{display:flex;gap:12px;padding:12px 0;overflow-x:auto;scroll-snap-type:x mandatory;-webkit-overflow-scrolling:touch}
.vcard{flex:0 0 calc(50% - 6px); scroll-snap-align:center; background:var(--card); border-radius:12px; overflow:hidden; box-shadow:var(--shadow)}
/* 9:16 비율을 위한 패딩-top (height/width = 16/9 -> padding-top = (16/9)*100% = 177.77%), but since iframe is vertical we want 16:9 reversed: set aspect-ratio 9/16 */
.vwrap{position:relative;width:100%;aspect-ratio:9/16;background:#000}
.vcard iframe{position:absolute;inset:0;width:100%;height:100%;border:0}
.vcard-title{padding:10px 12px;font-weight:800;font-size:14px;color:var(--text);background:transparent}

/* 데스크탑: 4열 그리드 */
@media(min-width:1024px){
  .videos-row{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;overflow:visible;padding:0}
  .vcard{flex:none}
  .vwrap{aspect-ratio:9/16}
}

/* Gallery 3:4 vertical items, 8 items */
.gallery{padding:28px 0}
.gallery-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}
.gallery-item{background:var(--card);border-radius:12px;overflow:hidden;aspect-ratio:3/4;box-shadow:var(--shadow)}
.gallery-item img{width:100%;height:100%;object-fit:cover;display:block}
@media(min-width:768px){.gallery-grid{grid-template-columns:repeat(4,1fr);gap:18px}}

/* Contact */
.contact{padding:36px 0}
.contact-box{background:var(--card);padding:24px;border-radius:12px;box-shadow:var(--shadow);text-align:center}
.btn-row{display:flex;flex-direction:column;gap:10px;align-items:center}
.btn-kakao{background:var(--kakao);color:#3b1b1b;padding:12px 18px;border-radius:10px;font-weight:800}
.btn-pdf{border:2px solid #eef2f7;padding:12px 18px;border-radius:10px;font-weight:800;background:#fff}
@media(min-width:768px){.btn-row{flex-direction:row;justify-content:center}}

/* Scrollbar */
.videos-row::-webkit-scrollbar{height:8px}
.videos-row::-webkit-scrollbar-thumb{background:rgba(0,0,0,0.12);border-radius:8px}
</style>
</head>
<body>
<header>
  <div class="container nav-inner">
    <div class="logo">[HYERIN]</div>
    <nav class="nav">
      <a href="#strengths">소개</a>
      <a href="#videos">레퍼런스</a>
      <a href="#gallery">갤러리</a>
      <a href="#contact">연락처</a>
    </nav>
  </div>
</header>

<main class="container">
  <!-- HERO -->
  <section class="hero">
    <div class="hero-row">
      <div class="hero-text">
        <div class="hero-name">쇼호스트 혜린 (HYERIN)</div> <!-- [교체] 실제 이름 -->
        <div class="hero-title">1분 만에 시청자를 구매자로 바꿉니다</div> <!-- [교체] 캐치프레이즈 -->
        <div class="hero-sub">콘텐츠 기획·진행·판매까지 한 번에. 결정이 쉬워지는 전달을 설계합니다.</div>

        <div class="badges" aria-hidden="false">
          <!-- [교체] 원하는 키워드 3~5개로 변경 가능 -->
          <div class="badge">#라이브커머스</div>
          <div class="badge">#뷰티전문</div>
          <div class="badge">#전환중심</div>
          <div class="badge">#올인원</div>
        </div>
      </div>

      <div class="profile-box" aria-hidden="false">
        <!-- [교체] 프로필 이미지 파일명 -->
        <img class="profile-img" src="profile1.jpg" alt="프로필" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=Profile'">
      </div>
    </div>
  </section>

  <!-- Strengths -->
  <section id="strengths" class="strengths">
    <div class="str-grid">
      <div class="str-card">
        <div class="str-icon"><i class="ri-line-chart-line"></i></div>
        <div class="str-title">검증된 판매 실력</div>
        <div class="str-desc">라이브 평균 전환율 및 실매출 증명. 캠페인 목표 달성 경험 다수.</div>
      </div>
      <div class="str-card">
        <div class="str-icon"><i class="ri-vidicon-line"></i></div>
        <div class="str-title">기획·촬영·진행</div>
        <div class="str-desc">콘텐츠 기획부터 진행까지 일괄 진행하여 브랜드 메시지를 명확히 전달합니다.</div>
      </div>
      <div class="str-card">
        <div class="str-icon"><i class="ri-sparkling-2-line"></i></div>
        <div class="str-title">뷰티·패션 전문성</div>
        <div class="str-desc">카테고리 전문 지식으로 소비자 니즈를 정확히 공략합니다.</div>
      </div>
    </div>
  </section>

  <!-- Videos (9:16, mobile two per view) -->
  <section id="videos" class="videos" aria-label="레퍼런스 영상">
    <h2 style="font-size:20px;margin:6px 0 12px">레퍼런스 영상</h2>
    <div class="videos-row" id="videosRow">
      <!-- vcard: 9:16 vertical videos. [교체] VIDEO_ID_x 및 titles -->
      <div class="vcard">
        <div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_1?rel=0&playsinline=1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
        <div class="vcard-title"> <OOO 브랜드> 뷰티 라이브</div>
      </div>
      <div class="vcard">
        <div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_2?rel=0&playsinline=1" allowfullscreen></iframe></div>
        <div class="vcard-title"> <ABC 가전> 신제품 런칭</div>
      </div>
      <div class="vcard">
        <div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_3?rel=0&playsinline=1" allowfullscreen></iframe></div>
        <div class="vcard-title"> <개인 채널> 패션 하울</div>
      </div>
      <div class="vcard">
        <div class="vwrap"><iframe src="https://www.youtube.com/embed/VIDEO_ID_4?rel=0&playsinline=1" allowfullscreen></iframe></div>
        <div class="vcard-title"> <D-Brand> 팝업 스케치</div>
      </div>
    </div>
  </section>

  <!-- Gallery 8 items, 3:4 -->
  <section id="gallery" class="gallery">
    <h2 style="font-size:20px;margin:6px 0 12px">갤러리</h2>
    <div class="gallery-grid">
      <div class="gallery-item"><img src="gallery1.jpg" alt="갤러리1" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=1'"></div>
      <div class="gallery-item"><img src="gallery2.jpg" alt="갤러리2" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=2'"></div>
      <div class="gallery-item"><img src="gallery3.jpg" alt="갤러리3" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=3'"></div>
      <div class="gallery-item"><img src="gallery4.jpg" alt="갤러리4" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=4'"></div>
      <div class="gallery-item"><img src="gallery5.jpg" alt="갤러리5" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=5'"></div>
      <div class="gallery-item"><img src="gallery6.jpg" alt="갤러리6" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=6'"></div>
      <div class="gallery-item"><img src="gallery7.jpg" alt="갤러리7" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=7'"></div>
      <div class="gallery-item"><img src="gallery8.jpg" alt="갤러리8" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=8'"></div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" class="contact">
    <div class="contact-box">
      <div style="font-weight:900;font-size:18px;margin-bottom:6px">함께 매출을 만들 준비되셨나요?</div>
      <div style="color:var(--muted);margin-bottom:14px">프로젝트 / 콜라보 / 채용 문의 환영합니다.</div>
      <div class="btn-row">
        <a class="btn-kakao" href="https://open.kakao.com/o/YOUR_LINK" target="_blank">오픈채팅 문의</a>
        <a class="btn-pdf" href="resume.pdf" download>이력서(PDF) 다운로드</a>
      </div>
    </div>
  </section>
</main>

<script>
/* Videos horizontal drag for mobile & prevent innerHTML leakage */
(function(){
  const slider = document.getElementById('videosRow');
  if(!slider) return;
  let down=false,startX,scrollLeft;
  slider.addEventListener('pointerdown', e=>{ down=true; startX=e.clientX; scrollLeft=slider.scrollLeft; slider.setPointerCapture(e.pointerId); });
  slider.addEventListener('pointerup', e=>{ down=false; try{ slider.releasePointerCapture(e.pointerId);}catch{} });
  slider.addEventListener('pointerleave', ()=>{ down=false; });
  slider.addEventListener('pointermove', e=>{ if(!down) return; const dx = e.clientX - startX; slider.scrollLeft = scrollLeft - dx; });
})();

/* Accessibility: ensure card titles are text-only (no raw HTML injection if filled dynamically) */
/* When replacing titles dynamically, use textContent not innerHTML */
</script>
</body>
</html>
