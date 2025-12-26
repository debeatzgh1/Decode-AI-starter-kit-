
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Digital Hub</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
  margin:0;
  font-family:system-ui,-apple-system,BlinkMacSystemFont,sans-serif;
  background:#f8fafc;
  color:#0f172a;
}

/* ===== HERO ===== */
.hero{
  background:linear-gradient(135deg,#020617,#0f172a);
  color:#fff;
  padding:50px 20px;
  text-align:center;
}
.hero h1{font-size:2.2rem;margin-bottom:10px}
.hero p{max-width:780px;margin:auto;opacity:.9}

/* ===== GRID ===== */
.container{
  max-width:1200px;
  margin:auto;
  padding:40px 20px;
}
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:24px;
}

/* ===== CARD ===== */
.card{
  background:#fff;
  border-radius:18px;
  box-shadow:0 10px 30px rgba(0,0,0,.08);
  overflow:hidden;
  position:relative;
  transition:.3s;
}
.card:hover{transform:translateY(-6px)}
.card img{
  width:100%;
  height:160px;
  object-fit:cover;
}
.card-body{padding:22px}
.card-body h3{margin:0 0 10px}
.card-body p{color:#475569;font-size:.95rem}

/* ===== BADGE ===== */
.badge{
  position:absolute;
  top:12px;
  left:12px;
  background:#2563eb;
  color:#fff;
  font-size:11px;
  padding:5px 10px;
  border-radius:999px;
  font-weight:700;
}

/* ===== BUTTONS ===== */
.actions{
  display:flex;
  gap:12px;
  margin-top:16px;
}
.btn{
  flex:1;
  padding:10px;
  border-radius:10px;
  font-weight:700;
  text-decoration:none;
  text-align:center;
}
.primary{background:#2563eb;color:#fff}
.outline{border:1px solid #2563eb;color:#2563eb}

/* ===== MODAL ===== */
#iframe-modal{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.6);
  z-index:9999;
}
.modal-content{
  width:95%;
  height:90%;
  margin:3% auto;
  background:#fff;
  border-radius:16px;
  overflow:hidden;
  position:relative;
}
.modal-fullscreen .modal-content{
  width:100%;
  height:100%;
  margin:0;
  border-radius:0;
}
#iframe-view{
  width:100%;
  height:100%;
  border:none;
}

/* ===== MODAL CONTROLS ===== */
.close-btn, .fs-btn{
  position:absolute;
  top:10px;
  background:rgba(0,0,0,.75);
  color:#fff;
  padding:6px 10px;
  border-radius:8px;
  cursor:pointer;
  z-index:10;
}
.close-btn{right:14px;font-size:22px}
.fs-btn{left:14px;font-size:14px}
</style>
</head>

<body>

<!-- HERO -->
<section class="hero">
  <h1>Digital Hub</h1>
  <p>
    A modern digital platform built to help creators, students, entrepreneurs,
    and professionals explore AI tools, business resources, quizzes, and smart
    online solutions — all in one connected experience.
  </p>
</section>

<!-- CONTENT -->
<section class="container">
  <div class="grid">

    <!-- CARD 1 -->
    <div class="card">
      <span class="badge">NEW</span>
      <img src="https://source.unsplash.com/featured/?ai,technology" alt="">
      <div class="card-body">
        <h3>AI & Digital Blog</h3>
        <p>
          Read practical guides on Artificial Intelligence, productivity tools,
          digital workflows, and modern tech insights for creators.
        </p>
        <div class="actions">
          <a href="https://debeatzgh2.blogspot.com/" class="btn primary">Read Articles</a>
          <a href="https://debeatzgh.wordpress.com/build-with-ai-2/" class="btn outline">Open Blog</a>
        </div>
      </div>
    </div>

    <!-- CARD 2 -->
    <div class="card">
      <span class="badge">FEATURED</span>
      <img src="https://source.unsplash.com/featured/?business,quiz" alt="">
      <div class="card-body">
        <h3>Online Business Quiz</h3>
        <p>
          Test your business knowledge, discover strengths, and get instant feedback
          through an interactive quiz experience.
        </p>
        <div class="actions">
          <a href="https://debeatzgh1.blogspot.com/2025/12/online-business-quiz-widget.html" class="btn primary">Take Quiz</a>
          <a href="https://debeatzgh1.blogspot.com/2025/12/online-business-quiz-widget.html" class="btn outline">Learn More</a>
        </div>
      </div>
    </div>

    <!-- CARD 3 -->
    <div class="card">
      <span class="badge">POPULAR</span>
      <img src="https://source.unsplash.com/featured/?startup,digital" alt="">
      <div class="card-body">
        <h3>DebeatzGH Sales Platform</h3>
        <p>
          Explore AI tools, smart earning ideas, digital resources, templates,
          and productivity solutions curated for online growth.
        </p>
        <div class="actions">
          <a href="https://debeatzgh1.github.io/sales" class="btn primary">Explore Platform</a>
          <a href="https://debeatzgh.wordpress.com/build-with-ai-2/" class="btn outline">View Updates</a>
        </div>
      </div>
    </div>

    <!-- CARD 4 -->
    <div class="card">
      <span class="badge">GUIDE</span>
      <img src="https://source.unsplash.com/featured/?sidehustle,work" alt="">
      <div class="card-body">
        <h3>Side Hustle Starter Kit</h3>
        <p>
          A beginner-friendly roadmap with practical side-hustle ideas,
          AI-powered tools, and digital income strategies.
        </p>
        <div class="actions">
          <a href="https://debeatzgh1.github.io/Side-hustle-starter-kit-/" class="btn primary">View Kit</a>
          <a href="https://debeatzgh1.github.io/Side-hustle-starter-kit-/" class="btn outline">Get Started</a>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- IFRAME MODAL -->
<div id="iframe-modal">
  <div class="modal-content">
    <div class="fs-btn">⛶</div>
    <div class="close-btn">&times;</div>
    <iframe id="iframe-view" loading="lazy"></iframe>
  </div>
</div>

<script>
const INTERNAL_DOMAINS = [
  "blogspot.com",
  "debeatzgh.wordpress.com",
  "debeatzgh1.github.io",
  "msha.ke/debeatzgh"
];

const modal = document.getElementById("iframe-modal");
const iframe = document.getElementById("iframe-view");
const fsBtn = document.querySelector(".fs-btn");
const closeBtn = document.querySelector(".close-btn");

function isInternal(url){
  return INTERNAL_DOMAINS.some(d => url.includes(d));
}

function openIframe(url){
  iframe.src = url;
  modal.style.display = "block";
}

function closeIframe(){
  iframe.src = "";
  modal.style.display = "none";
  modal.classList.remove("modal-fullscreen");
}

document.querySelectorAll("a").forEach(a=>{
  a.addEventListener("click",e=>{
    const url = a.href;
    if(!url) return;
    e.preventDefault();
    isInternal(url)
      ? openIframe(url)
      : window.open(url,"_blank","noopener,noreferrer");
  });
});

fsBtn.onclick = () => modal.classList.toggle("modal-fullscreen");
closeBtn.onclick = closeIframe;
modal.onclick = e => { if(e.target === modal) closeIframe(); };
</script>

</body>
</html>
