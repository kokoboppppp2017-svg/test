<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>[당신 이름] | 포트폴리오</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.css">
<style>
:root{
  --bg:#f8f9fc; --accent:#2763d6; --text:#0f172a; --muted:#6b7280;
  --card:#fff; --radius:12px; --gap:12px; --shadow:0 10px 30px rgba(15,23,42,0.06);
}
*{box-sizing:border-box} html{scroll-behavior:smooth}
body{margin:0;font-family:"Pretendard",system-ui,-apple-system,Segoe UI,Roboto,"Noto Sans KR";background:var(--bg);color:var(--text)}
.container{max-width:1100px;margin:0 auto;padding:0 16px}

/* Header */
header{position:sticky;top:0;background:rgba(255,255,255,0.95);backdrop-filter:blur(6px);border-bottom:1px solid #eef2f7;z-index:1000}
.header-inner{height:64px;display:flex;align-items:center;justify-content:space-between;padding:0 8px}
.logo{font-weight:900}

/* HERO: PC/모바일 레이아웃 분기 */
.hero{padding:28px 0}
.hero-row{display:flex;gap:20px;align-items:flex-start;justify-content:space-between}
.hero-text{flex:1;min-width:0}
.hero-name{font-size:20px;font-weight:800;color:var(--accent);margin-bottom:6px}
.hero-title{font-size:clamp(1.5rem,5vw,2.2rem);font-weight:900;line-height:1.08;margin-bottom:8px}
.hero-sub{color:var(--muted);font-size:15px;margin-bottom:12px}
.badges{display:flex;flex-wrap:wrap;gap:8px}
.badge{background:#eef5ff;color:var(--accent);padding:6px 10px;border-radius:999px;font-weight:800;font-size:13px}

/* profile box (오른쪽 고정 폭, 모바일에서도 오른쪽에 유지) */
.profile-box{flex:0 0 200px;max-width:200px;border-radius:14px;overflow:hidden;background:var(--card);box-shadow:var(--shadow)}
.profile-img{width:100%;height:auto;display:block;aspect-ratio:3/4;object-fit:cover}

/* Strengths */
.str-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px;margin:18px 0}

/* VIDEOS
   - 모바일: 2개 보이도록 .vcard 폭 50% (gap 보정)
   - aspect-ratio 9/16 for vertical video
*/
.videos{padding:14px 0}
.videos-row{display:flex;gap:12px;overflow-x:auto;padding-bottom:8px;scroll-snap-type:x mandatory;-webkit-overflow-scrolling:touch}
.vcard{flex:0 0 calc(50% - 6px);scroll-snap-align:center;background:var(--card);border-radius:12px;overflow:hidden;box-shadow:var(--shadow);display:flex;flex-direction:column}
.video-frame{width:100%;aspect-ratio:9/16;background:#000;position:relative}
.video-frame iframe{position:absolute;inset:0;width:100%;height:100%;border:0}
.vcard-title{padding:10px;font-weight:800;font-size:14px;color:var(--text);background:transparent}

/* 데스크탑: grid 4열 */
@media(min-width:1024px){
  .hero-row{align-items:center}
  .profile-box{flex:0 0 320px;max-width:320px}
  .videos-row{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;overflow:visible;padding:0}
  .vcard{flex:none}
}

/* 작은 화면에서도 텍스트 왼쪽, 사진 오른쪽 유지
   단 아주 좁으면 내부 간격 줄임(가로 스크롤 없이 두개 보임 보장)
*/
@media(max-width:420px){
  .profile-box{flex:0 0 36%;max-width:36%}
  .hero-title{font-size:1.4rem}
  .vcard{flex:0 0 calc(50% - 6px)}
}
</style>
</head>
<body>
<header>
  <div class="container header-inner">
    <div class="logo">[HYERIN]</div>
    <nav style="display:flex;gap:12px;">
      <a href="#strengths">소개</a><a href="#videos">레퍼런스</a><a href="#gallery">갤러리</a><a href="#contact">연락처</a>
    </nav>
  </div>
</header>

<main class="container">
  <!-- HERO -->
  <section class="hero" id="hero">
    <div class="hero-row">
      <div class="hero-text">
        <div class="hero-name">쇼호스트 혜린 (HYERIN)</div> <!-- [교체] -->
        <div class="hero-title">1분 만에 시청자를 구매자로 바꿉니다</div> <!-- [교체] -->
        <div class="hero-sub">콘텐츠 기획·진행·판매까지. 결정이 쉬워지는 전달을 설계합니다.</div>

        <div class="badges" aria-hidden="false">
          <div class="badge">#라이브커머스</div>
          <div class="badge">#뷰티전문</div>
          <div class="badge">#전환중심</div>
        </div>
      </div>

      <div class="profile-box" aria-hidden="false">
        <img class="profile-img" src="profile1.jpg" alt="프로필" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=Profile'">
      </div>
    </div>
  </section>

  <!-- Strengths (간단) -->
  <section id="strengths">
    <div class="str-grid" style="margin-bottom:18px">
      <div style="background:var(--card);padding:14px;border-radius:10px;box-shadow:var(--shadow)">
        <div style="font-weight:800;margin-bottom:6px">검증된 판매 실력</div>
        <div style="color:var(--muted)">캠페인 목표 달성 경험 다수</div>
      </div>
      <div style="background:var(--card);padding:14px;border-radius:10px;box-shadow:var(--shadow)">
        <div style="font-weight:800;margin-bottom:6px">기획·촬영·진행</div>
        <div style="color:var(--muted)">콘텐츠 기획부터 실행까지 원스톱</div>
      </div>
      <div style="background:var(--card);padding:14px;border-radius:10px;box-shadow:var(--shadow)">
        <div style="font-weight:800;margin-bottom:6px">카테고리 전문성</div>
        <div style="color:var(--muted)">뷰티·패션 중심 다수 협업 경험</div>
      </div>
    </div>
  </section>

  <!-- VIDEOS: 모바일에서 2개 보이고 가로 슬라이드 가능 -->
  <section id="videos" aria-label="레퍼런스 영상">
    <h3 style="font-size:18px;margin:6px 0">레퍼런스 영상</h3>
    <div class="videos-row" id="videosRow">
      <!-- [교체] VIDEO_ID_1 등과 titles -->
      <div class="vcard">
        <div class="video-frame"><iframe src="https://www.youtube.com/embed/VIDEO_ID_1?rel=0&playsinline=1" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>
        <div class="vcard-title" data-title>OOO 브랜드 라이브</div>
      </div>
      <div class="vcard">
        <div class="video-frame"><iframe src="https://www.youtube.com/embed/VIDEO_ID_2?rel=0&playsinline=1" allowfullscreen></iframe></div>
        <div class="vcard-title" data-title>ABC 가전 런칭</div>
      </div>
      <div class="vcard">
        <div class="video-frame"><iframe src="https://www.youtube.com/embed/VIDEO_ID_3?rel=0&playsinline=1" allowfullscreen></iframe></div>
        <div class="vcard-title" data-title>패션 하울</div>
      </div>
      <div class="vcard">
        <div class="video-frame"><iframe src="https://www.youtube.com/embed/VIDEO_ID_4?rel=0&playsinline=1" allowfullscreen></iframe></div>
        <div class="vcard-title" data-title>팝업 스케치</div>
      </div>
    </div>
  </section>

  <!-- Gallery 8 items (3:4) -->
  <section id="gallery" style="margin-top:18px">
    <h3 style="font-size:18px;margin:6px 0">갤러리</h3>
    <div style="display:grid;grid-template-columns:repeat(2,1fr);gap:12px">
      <div style="aspect-ratio:3/4;background:var(--card);border-radius:10px;overflow:hidden"><img src="gallery1.jpg" alt="" style="width:100%;height:100%;object-fit:cover" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=1'"></div>
      <div style="aspect-ratio:3/4;background:var(--card);border-radius:10px;overflow:hidden"><img src="gallery2.jpg" alt="" style="width:100%;height:100%;object-fit:cover" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=2'"></div>
      <div style="aspect-ratio:3/4;background:var(--card);border-radius:10px;overflow:hidden"><img src="gallery3.jpg" alt="" style="width:100%;height:100%;object-fit:cover" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=3'"></div>
      <div style="aspect-ratio:3/4;background:var(--card);border-radius:10px;overflow:hidden"><img src="gallery4.jpg" alt="" style="width:100%;height:100%;object-fit:cover" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=4'"></div>
      <div style="aspect-ratio:3/4;background:var(--card);border-radius:10px;overflow:hidden"><img src="gallery5.jpg" alt="" style="width:100%;height:100%;object-fit:cover" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=5'"></div>
      <div style="aspect-ratio:3/4;background:var(--card);border-radius:10px;overflow:hidden"><img src="gallery6.jpg" alt="" style="width:100%;height:100%;object-fit:cover" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=6'"></div>
      <div style="aspect-ratio:3/4;background:var(--card);border-radius:10px;overflow:hidden"><img src="gallery7.jpg" alt="" style="width:100%;height:100%;object-fit:cover" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=7'"></div>
      <div style="aspect-ratio:3/4;background:var(--card);border-radius:10px;overflow:hidden"><img src="gallery8.jpg" alt="" style="width:100%;height:100%;object-fit:cover" onerror="this.src='https://via.placeholder.com/600x800/eaeffa/333?text=8'"></div>
    </div>
  </section>

  <!-- Contact -->
  <section id="contact" style="margin:28px 0 60px">
    <div style="background:var(--card);padding:20px;border-radius:12px;box-shadow:var(--shadow);text-align:center">
      <div style="font-weight:900;margin-bottom:8px">프로젝트 문의</div>
      <div style="color:var(--muted);margin-bottom:12px">카카오 오픈채팅 또는 이메일로 연락주세요.</div>
      <div style="display:flex;gap:10px;justify-content:center;flex-wrap:wrap">
        <a href="https://open.kakao.com/o/YOUR_LINK" style="background:#fee500;padding:10px 14px;border-radius:10px;font-weight:800;color:#3b1b1b">오픈채팅</a>
        <a href="resume.pdf" download style="border:2px solid #eef2f7;padding:10px 14px;border-radius:10px;font-weight:800">이력서 다운로드</a>
      </div>
    </div>
  </section>
</main>

<script>
/* 안전: 카드 타이틀은 textContent로만 대체 (예: 서버에서 값 넣을 때 사용) */
function setVideoTitle(index, title){
  const cards = document.querySelectorAll('.vcard-title[data-title]');
  if(cards[index]) cards[index].textContent = title;
}

/* 모바일 가로 드래그 (터치/포인터) */
(function(){
  const slider = document.getElementById('videosRow');
  if(!slider) return;
  let isDown=false, startX, scrollLeft;
  slider.addEventListener('pointerdown', e=>{ isDown=true; startX=e.clientX; scrollLeft=slider.scrollLeft; slider.setPointerCapture(e.pointerId); });
  slider.addEventListener('pointerup', e=>{ isDown=false; try{ slider.releasePointerCapture(e.pointerId);}catch{} });
  slider.addEventListener('pointerleave', ()=>{ isDown=false; });
  slider.addEventListener('pointermove', e=>{ if(!isDown) return; e.preventDefault(); const dx = e.clientX - startX; slider.scrollLeft = scrollLeft - dx; });
})();
</script>
</body>
</html>
