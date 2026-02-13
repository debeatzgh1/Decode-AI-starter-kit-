
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        :root {
            --nav-glass: rgba(13, 17, 23, 0.85);
            --nav-border: rgba(255, 255, 255, 0.1);
            --color-guide: #00f2fe; /* Cyan */
            --color-home: #70ff03;  /* Green */
            --color-social: #ff007a; /* Pink */
            --color-top: #ffffff;   /* White */
        }

        .side-nav {
            position: fixed;
            top: 50%;
            transform: translateY(-50%);
            z-index: 9999;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .nav-left { left: 0; }
        .nav-right { right: 0; }

        .nav-item {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 48px;
            height: 48px;
            background: var(--nav-glass);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid var(--nav-border);
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }

        .nav-left .nav-item { border-radius: 0 10px 10px 0; border-left: none; }
        .nav-right .nav-item { border-radius: 10px 0 0 10px; border-right: none; }

        .item-guide { color: var(--color-guide); }
        .item-social { color: var(--color-social); }
        .item-home { color: var(--color-home); }
        .item-top { color: var(--color-top); opacity: 0; visibility: hidden; transition: 0.5s; }
        .item-top.visible { opacity: 1; visibility: visible; }

        .shake-anim { animation: timely-shake 0.5s ease-in-out; }
        @keyframes timely-shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(4px); }
            50% { transform: translateX(-4px); }
        }

        .nav-item:hover { width: 60px; }
        .item-guide:hover { background: var(--color-guide); color: #000; }
        .item-social:hover { background: var(--color-social); color: #fff; }
        .item-home:hover { background: var(--color-home); color: #000; }
        .item-top:hover { background: #fff; color: #000; }

        .nav-item::after {
            content: attr(data-label);
            position: absolute;
            font-size: 9px;
            font-weight: 900;
            white-space: nowrap;
            opacity: 0;
            transition: 0.3s;
        }
        .nav-left .nav-item::after { left: 65px; color: inherit; }
        .nav-right .nav-item::after { right: 65px; color: inherit; }
        .nav-item:hover::after { opacity: 1; }

        svg { width: 22px; height: 22px; pointer-events: none; }
    </style>
</head>
<body>

    <div class="side-nav nav-left">
        <a href="https://debeatzgh1.github.io/Digital-Creator-s-Essential-Guides-Tools/" target="_blank" class="nav-item item-guide shake-trigger" data-label="Essential Guides">
            <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path></svg>
        </a>
        <a href="https://debeatzgh1.github.io/The-Ultimate-Guide-to-Side-Hustle/" target="_blank" class="nav-item item-social shake-trigger" data-label="Side Hustle">
            <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 1 1-7.6-10.4 8.38 8.38 0 0 1 3.9 1.1L21 3z"></path></svg>
        </a>
    </div>

    <div class="side-nav nav-right">
        <a href="https://debeatzgh1.github.io/Decode-AI-starter-kit-/" target="_blank" class="nav-item item-home shake-trigger" data-label="AI Starter Kit">
            <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline></svg>
        </a>
        <div onclick="scrollToTop()" class="nav-item item-top" id="backToTop" data-label="Back To Top">
            <svg viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="18 15 12 9 6 15"></polyline></svg>
        </div>
    </div>

    <script>
        function startShaking() {
            const icons = document.querySelectorAll('.shake-trigger');
            setInterval(() => {
                icons.forEach((icon, index) => {
                    setTimeout(() => {
                        icon.classList.add('shake-anim');
                        setTimeout(() => icon.classList.remove('shake-anim'), 500);
                    }, index * 200);
                });
            }, 6000);
        }

        const topBtn = document.getElementById('backToTop');
        window.onscroll = function() {
            if (document.body.scrollTop > 300 || document.documentElement.scrollTop > 300) {
                topBtn.classList.add('visible');
            } else {
                topBtn.classList.remove('visible');
            }
        };

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        window.onload = startShaking;
    </script>

</body>
</html>


<html lang="en">
<head>
    <style>
        :root {
            --nav-glass: rgba(13, 17, 23, 0.85);
            --nav-border: rgba(255, 255, 255, 0.1);
            --color-guide: #00f2fe; /* Cyan */
            --color-home: #70ff03;  /* Green */
            --color-social: #ff007a; /* Pink */
            --color-top: #ffffff;   /* White */
        }

        .side-nav {
            position: fixed;
            top: 50%;
            transform: translateY(-50%);
            z-index: 9999;
            display: flex;
            flex-direction: column;
            gap: 10px; /* Tightened gap */
        }

        .nav-left { left: 0; }
        .nav-right { right: 0; }

        .nav-item {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 48px;
            height: 48px;
            background: var(--nav-glass);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid var(--nav-border);
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            text-decoration: none;
            position: relative;
            overflow: hidden;
        }

        .nav-left .nav-item { border-radius: 0 10px 10px 0; border-left: none; }
        .nav-right .nav-item { border-radius: 10px 0 0 10px; border-right: none; }

        /* Specific Item Colors */
        .item-guide { color: var(--color-guide); }
        .item-social { color: var(--color-social); }
        .item-home { color: var(--color-home); }
        .item-top { color: var(--color-top); opacity: 0; visibility: hidden; transition: 0.5s; }
        .item-top.visible { opacity: 1; visibility: visible; }

        /* Shake Animation */
        .shake-anim { animation: timely-shake 0.5s ease-in-out; }
        @keyframes timely-shake {
            0%, 100% { transform: translateX(0); }
            25% { transform: translateX(4px); }
            50% { transform: translateX(-4px); }
        }

        /* Hover Glows */
        .nav-item:hover { width: 60px; }
        .item-guide:hover { background: var(--color-guide); color: #000; }
        .item-social:hover { background: var(--color-social); color: #fff; }
        .item-home:hover { background: var(--color-home); color: #000; }
        .item-top:hover { background: #fff; color: #000; }

        /* Tooltip Labels */
        .nav-item::after {
            content: attr(data-label);
            position: absolute;
            font-size: 9px;
            font-weight: 900;
            white-space: nowrap;
            opacity: 0;
            transition: 0.3s;
        }
        .nav-left .nav-item::after { left: 65px; color: inherit; }
        .nav-right .nav-item::after { right: 65px; color: inherit; }
        .nav-item:hover::after { opacity: 1; }

        svg { width: 22px; height: 22px; pointer-events: none; }
    </style>
</head>
<body>

    <div class="side-nav nav-left">
        <a href="https://debeatzgh1.github.io/Digital-Creator-s-Essential-Guides-Tools/" target="_blank" class="nav-item item-guide shake-trigger" data-label="Essential Guides">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path></svg>
        </a>
        <a href="https://t.me/your_telegram" target="_blank" class="nav-item item-social shake-trigger" data-label="Join Community">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 1 1-7.6-10.4 8.38 8.38 0 0 1 3.9 1.1L21 3z"></path></svg>
        </a>
    </div>

    <div class="side-nav nav-right">
        <a href="https://debeatzgh1.github.io/Home-/" target="_blank" class="nav-item item-home shake-trigger" data-label="Home Dashboard">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"></path><polyline points="9 22 9 12 15 12 15 22"></polyline></svg>
        </a>
        <div onclick="scrollToTop()" class="nav-item item-top" id="backToTop" data-label="Back To Top">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="18 15 12 9 6 15"></polyline></svg>
        </div>
    </div>

    <script>
        // 1. Shaking Logic
        function startShaking() {
            const icons = document.querySelectorAll('.shake-trigger');
            setInterval(() => {
                icons.forEach((icon, index) => {
                    setTimeout(() => {
                        icon.classList.add('shake-anim');
                        setTimeout(() => icon.classList.remove('shake-anim'), 500);
                    }, index * 200);
                });
            }, 6000); // Shakes every 6 seconds
        }

        // 2. Back to Top Logic
        const topBtn = document.getElementById('backToTop');
        window.onscroll = function() {
            if (document.body.scrollTop > 300 || document.documentElement.scrollTop > 300) {
                topBtn.classList.add('visible');
            } else {
                topBtn.classList.remove('visible');
            }
        };

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        window.onload = startShaking;
    </script>
</body>
</html>

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Debeatzgh Multi-Tab Launcher</title>

<link href="https://cdn.jsdelivr.net/npm/tailwindcss@3.4.1/dist/tailwind.min.css" rel="stylesheet">

<style>
.modal-bg{
  display:none;
  position:fixed;
  inset:0;
  background:rgba(0,0,0,.7);
  backdrop-filter:blur(6px);
  z-index:9999;
}
.modal-box{
  width:96%;
  height:94%;
  background:#fff;
  border-radius:18px;
  overflow:hidden;
  display:flex;
  flex-direction:column;
}

.tabs{
  display:flex;
  gap:6px;
  padding:10px;
  background:#0f172a;
}
.tab{
  padding:8px 14px;
  border-radius:10px;
  font-size:13px;
  font-weight:700;
  color:#cbd5f5;
  cursor:pointer;
}
.tab.active{
  background:#2563eb;
  color:#fff;
}

.controls{
  display:flex;
  gap:8px;
  padding:8px 10px;
  background:#020617;
}
.ctrl-btn{
  background:rgba(255,255,255,.15);
  color:#fff;
  padding:6px 12px;
  border-radius:8px;
  font-size:12px;
  font-weight:700;
  cursor:pointer;
}

iframe{
  flex:1;
  width:100%;
  border:none;
}
</style>
</head>

<body class="bg-gray-100">

<header class="text-center py-10">
  <h1 class="text-3xl font-bold">AI & Knowledge Hub</h1>
  <p class="text-gray-600 mt-2 max-w-xl mx-auto">
    Open trusted platforms in one distraction-free workspace.
  </p>
</header>

<!-- LAUNCHER CARDS -->
<div class="max-w-6xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-6 px-6">

  <div class="bg-white rounded-xl shadow p-6">
    <h3 class="text-xl font-bold mb-2">Build With AI</h3>
    <p class="text-sm text-gray-600 mb-4">WordPress AI deep-dives & guides</p>
    <button onclick="openLauncher('wordpress')"
      class="w-full bg-blue-600 text-white py-3 rounded-xl font-bold">
      Open
    </button>
  </div>

  <div class="bg-white rounded-xl shadow p-6">
    <h3 class="text-xl font-bold mb-2">AI Knowledge Blog</h3>
    <p class="text-sm text-gray-600 mb-4">Beginner-friendly Blogger content</p>
    <button onclick="openLauncher('blogger')"
      class="w-full bg-emerald-600 text-white py-3 rounded-xl font-bold">
      Open
    </button>
  </div>

</div>

<!-- MODAL -->
<div class="modal-bg" id="modal">
  <div class="modal-box" id="modalBox">

    <!-- TABS -->
    <div class="tabs">
      <div class="tab active" data-tab="wordpress">WordPress</div>
      <div class="tab" data-tab="blogger">Blogger</div>
      <div class="tab" data-tab="signin">Sign In</div>
      <div class="tab" data-tab="about">About</div>
    </div>

    <!-- CONTROLS -->
    <div class="controls">
      <div class="ctrl-btn" onclick="goBack()">⟵ Back</div>
      <div class="ctrl-btn" onclick="goForward()">⟶ Forward</div>
      <div class="ctrl-btn" onclick="toggleFS()">⛶ Fullscreen</div>
      <div class="ctrl-btn" onclick="closeLauncher()">✕ Close</div>
    </div>

    <!-- IFRAME -->
    <iframe id="frame"></iframe>

  </div>
</div>

<script>
const modal = document.getElementById("modal");
const frame = document.getElementById("frame");
const tabs = document.querySelectorAll(".tab");

/* ===== URL MAP (FIXED) ===== */
const URLS = {
  wordpress: "https://debeatzgh.wordpress.com/build-with-ai-2/",
  blogger: "https://debeatzgh2.blogspot.com/",
  signin: "https://docs.google.com/forms/d/e/1FAIpQLSdXCPUz1JBq0W8MHN9VOE0p6cnp5Wtr74Ox2gqLLyzKi0UwKA/viewform",
  about: "https://form.jotform.com/241335470278053"
};

/* ===== HISTORY ===== */
let historyStack = [];
let historyIndex = -1;

function load(url){
  frame.src = url;
  if(historyStack[historyIndex] !== url){
    historyStack = historyStack.slice(0, historyIndex + 1);
    historyStack.push(url);
    historyIndex++;
  }
}

/* ===== OPEN ===== */
function openLauncher(tab){
  modal.style.display = "flex";
  switchTab(tab);
}

/* ===== CLOSE ===== */
function closeLauncher(){
  modal.style.display = "none";
  frame.src = "";
  historyStack = [];
  historyIndex = -1;
  if(document.fullscreenElement) document.exitFullscreen();
}

/* ===== SWITCH TAB (FIXED) ===== */
tabs.forEach(tabEl => {
  tabEl.addEventListener("click", () => {
    switchTab(tabEl.dataset.tab);
  });
});

function switchTab(tab){
  tabs.forEach(t => t.classList.remove("active"));
  document.querySelector(`.tab[data-tab="${tab}"]`).classList.add("active");
  load(URLS[tab]);
}

/* ===== NAVIGATION ===== */
function goBack(){
  if(historyIndex > 0){
    historyIndex--;
    frame.src = historyStack[historyIndex];
  }
}
function goForward(){
  if(historyIndex < historyStack.length - 1){
    historyIndex++;
    frame.src = historyStack[historyIndex];
  }
}

/* ===== FULLSCREEN ===== */
function toggleFS(){
  const el = document.getElementById("modalBox");
  if(!document.fullscreenElement) el.requestFullscreen();
  else document.exitFullscreen();
}
</script>

</body>
</html>

