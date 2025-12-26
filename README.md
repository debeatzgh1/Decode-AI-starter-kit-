
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Decode AI – Digital Hub</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
:root{
  --primary:#2563eb;
  --dark:#020617;
  --muted:#475569;
}
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
  padding:70px 20px;
  text-align:center;
}
.hero h1{font-size:2.6rem;margin-bottom:12px}
.hero p{max-width:820px;margin:auto;opacity:.9}

/* ===== CONTAINER ===== */
.container{
  max-width:1000px;
  margin:auto;
  padding:50px 20px;
}

/* ===== GRID ===== */
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
  gap:26px;
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
  height:180px;
  object-fit:cover;
}
.card-body{padding:24px}
.card-body h3{margin:0 0 10px}
.card-body p{color:var(--muted);font-size:.95rem}

/* ===== BUTTON OVERLAY ===== */
.overlay-btn{
  position:absolute;
  inset:0;
  display:flex;
  align-items:center;
  justify-content:center;
  background:rgba(2,6,23,.55);
  opacity:0;
  transition:.3s;
}
.card:hover .overlay-btn{opacity:1}
.overlay-btn span{
  background:var(--primary);
  color:#fff;
  padding:12px 22px;
  border-radius:30px;
  font-weight:700;
}

/* ===== SECTION TITLE ===== */
.section-title{
  font-size:1.9rem;
  margin-bottom:14px;
}
.section-desc{
  color:var(--muted);
  max-width:780px;
  margin-bottom:30px;
}

/* ===== POSTS ===== */
.posts{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
  gap:20px;
}
.post{
  background:#fff;
  border-radius:14px;
  padding:18px;
  box-shadow:0 6px 20px rgba(0,0,0,.07);
}
.post h4{margin:0 0 8px}
.post p{font-size:.9rem;color:var(--muted)}

/* ===== MODAL ===== */
#iframe-modal{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.65);
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
#iframe-view{width:100%;height:100%;border:none}

/* ===== CONTROLS ===== */
.close-btn,.fs-btn{
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
  <h1>Decoding Artificial Intelligence</h1>
  <p>
    A professional digital hub by DebeatzGH exploring AI concepts, real-world use cases,
    tools, insights, and future-ready knowledge for creators, students, and entrepreneurs.
  </p>
</section>

<!-- MAIN PLATFORMS -->
<section class="container">
  <h2 class="section-title">Explore the Platforms</h2>
  <p class="section-desc">
    Access curated AI articles, blog resources, digital tools, and creator links —
    all connected through an immersive iframe experience.
  </p>

  <div class="grid">

    <!-- WORDPRESS -->
    <div class="card" data-url="https://debeatzgh.wordpress.com/build-with-ai-2/">
      <!-- 🔁 REPLACE IMAGE WITH YOUR WORDPRESS UPLOAD -->
      <img src="https://images.unsplash.com/photo-1677442136019-21780ecad995" alt="">
      <div class="card-body">
        <h3>Build With AI (WordPress)</h3>
        <p>
          In-depth articles, guides, and tutorials on building smarter systems
          using artificial intelligence.
        </p>
      </div>
      <div class="overlay-btn"><span>Open in Viewer</span></div>
    </div>

    <!-- BLOGSPOT -->
    <div class="card" data-url="https://debeatzgh2.blogspot.com/p/blog-page_9.html">
      <img src="https://images.unsplash.com/photo-1555949963-aa79dcee981c" alt="">
      <div class="card-body">
        <h3>AI Knowledge Blog</h3>
        <p>
          Practical AI learning content, explanations, and thought leadership
          focused on decoding complex ideas.
        </p>
      </div>
      <div class="overlay-btn"><span>Read Articles</span></div>
    </div>

    <!-- MILKSHAKE -->
    <div class="card" data-url="https://msha.ke/debeatzgh">
      <img src="https://images.unsplash.com/photo-1553877522-43269d4ea984" alt="">
      <div class="card-body">
        <h3>Creator & Tools Hub</h3>
        <p>
          Access all DebeatzGH tools, apps, links, resources, and creator platforms
          from one central hub.
        </p>
      </div>
      <div class="overlay-btn"><span>Explore Hub</span></div>
    </div>

  </div>
</section>

<!-- SAMPLE POSTS -->
<section class="container">
  <h2 class="section-title">Featured Topics: Decoding AI</h2>
  <p class="section-desc">
    Sample content designed to spark curiosity, learning, and engagement around
    Artificial Intelligence.
  </p>

  <div class="posts">
    <div class="post"><h4>1. What AI Really Is (Beyond the Hype)</h4><p>Understanding intelligence, algorithms, and learning systems.</p></div>
    <div class="post"><h4>2. Machine Learning Explained Simply</h4><p>How machines learn from data without explicit programming.</p></div>
    <div class="post"><h4>3. Neural Networks & The Human Brain</h4><p>Why deep learning mimics biological thinking.</p></div>
    <div class="post"><h4>4. AI in Everyday Life</h4><p>From recommendations to voice assistants.</p></div>
    <div class="post"><h4>5. AI for Content Creators</h4><p>Writing, design, video, and productivity tools.</p></div>
    <div class="post"><h4>6. Ethics & Bias in AI</h4><p>Fairness, accountability, and responsibility.</p></div>
    <div class="post"><h4>7. AI in Business Growth</h4><p>Automation, analytics, and smarter decisions.</p></div>
    <div class="post"><h4>8. Prompt Engineering Basics</h4><p>How to talk to AI effectively.</p></div>
    <div class="post"><h4>9. AI vs Human Creativity</h4><p>Collaboration, not replacement.</p></div>
    <div class="post"><h4>10. The Future of Artificial Intelligence</h4><p>What comes next and how to prepare.</p></div>
  </div>
</section>

<!-- MODAL -->
<div id="iframe-modal">
  <div class="modal-content">
    <div class="fs-btn">⛶</div>
    <div class="close-btn">&times;</div>
    <iframe id="iframe-view" loading="lazy"></iframe>
  </div>
</div>

<script>
const INTERNAL_DOMAINS = [
  "debeatzgh.wordpress.com",
  "blogspot.com",
  "msha.ke/debeatzgh"
];

const modal = document.getElementById("iframe-modal");
const iframe = document.getElementById("iframe-view");

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

document.querySelectorAll(".card").forEach(card=>{
  card.addEventListener("click",()=>{
    const url = card.dataset.url;
    isInternal(url)
      ? openIframe(url)
      : window.open(url,"_blank","noopener,noreferrer");
  });
});

document.querySelector(".fs-btn").onclick =
  ()=> modal.classList.toggle("modal-fullscreen");

document.querySelector(".close-btn").onclick = closeIframe;
modal.onclick = e => { if(e.target === modal) closeIframe(); };
</script>

</body>
</html>
