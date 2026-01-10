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

<!doctype html>

<style>
/* ❤️ Heartbeat Animation */
@keyframes heartbeat {
  0% { transform: scale(1); }
  30% { transform: scale(1.1); }
  50% { transform: scale(1); }
  70% { transform: scale(1.15); }
  100% { transform: scale(1); }
}

/* 🔘 Floating Button (TOP RIGHT – SMALL) */
.floating-btn {
  position: fixed;
  top: 14px;
  right: 14px; /* ✅ moved to top-right */
  z-index: 9999;
  animation: heartbeat 1.8s infinite;
}

.floating-btn a {
  background: #1e90ff;
  color: #fff;
  padding: 6px 9px;
  border-radius: 14px;
  font-size: 11px;
  font-weight: 600;
  text-decoration: none;
  box-shadow: 0 2px 6px rgba(0,0,0,0.25);
}

/* 🪟 Modal Overlay */
#iframe-modal {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.7);
  backdrop-filter: blur(4px);
  z-index: 99999;
}

/* 📦 Modal Box */
.modal-box {
  position: relative;
  margin: 2% auto;
  width: 98%;
  height: 100%;
  background: #fff;
  border-radius: 16px;
  overflow: hidden;
}

/* 🧭 Toolbar */
.modal-toolbar {
  position: absolute;
  top: 8px;
  left: 10px;
  right: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 10;
}

.modal-toolbar button {
  background: #111;
  color: #fff;
  border: none;
  padding: 7px 10px;
  border-radius: 8px;
  font-size: 12px;
  cursor: pointer;
}

#modal-iframe {
  width: 100%;
  height: 107%;
  border: none;
}
</style>

<script>
document.addEventListener("DOMContentLoaded", function () {

  /* 🌐 Pages */
  const pages = [
    "https://debeatzgh1.github.io/sales/"
  ];

  let index = 0;
  let autoPopup = true;

  /* 🔘 Floating Button */
  const floatBtn = document.createElement("div");
  floatBtn.className = "floating-btn";
  floatBtn.innerHTML = `<a href="#">Blogs</a>`;
  document.body.appendChild(floatBtn);

  /* 🪟 Modal */
  const modal = document.createElement("div");
  modal.id = "iframe-modal";
  modal.innerHTML = `
    <div class="modal-box">
      <div class="modal-toolbar">
        <div>
          <button id="prevBtn">◀ Prev</button>
          <button id="nextBtn">Next ▶</button>
        </div>
        <button id="closeBtn">✖</button>
      </div>

      <iframe
        id="modal-iframe"
        loading="lazy"
        sandbox="allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox allow-forms"
        allow="autoplay; encrypted-media; picture-in-picture"
        referrerpolicy="no-referrer-when-downgrade">
      </iframe>
    </div>
  `;
  document.body.appendChild(modal);

  const iframe = document.getElementById("modal-iframe");

  function openModal() {
    iframe.src = pages[index];
    modal.style.display = "block";
  }

  function closeModal() {
    modal.style.display = "none";
    iframe.src = "";
    autoPopup = false;
  }

  /* 🔘 Button Click */
  floatBtn.onclick = function (e) {
    e.preventDefault();
    openModal();
  };

  /* ⏭ Navigation */
  document.getElementById("nextBtn").onclick = function () {
    index = (index + 1) % pages.length;
    openModal();
  };

  document.getElementById("prevBtn").onclick = function () {
    index = (index - 1 + pages.length) % pages.length;
    openModal();
  };

  /* ❌ Close */
  document.getElementById("closeBtn").onclick = closeModal;
  modal.onclick = e => e.target === modal && closeModal();

  /* ⏱ Auto open */
  setInterval(function () {
    if (autoPopup && modal.style.display !== "block") {
      openModal();
    }
  }, 6000);

});
</script>
</!doctype>
