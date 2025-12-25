<style>
/* 🌟 Fade Slide Animation */
@keyframes fadeSlideUp {
  0% { opacity: 0; transform: translateX(-50%) translateY(20px); }
  100% { opacity: 1; transform: translateX(-50%) translateY(0); }
}

/* ❤️ Heartbeat Animation */
@keyframes heartbeat {
  0% { transform: translateX(-50%) scale(1); }
  25% { transform: translateX(-50%) scale(1.08); }
  50% { transform: translateX(-50%) scale(1); }
  75% { transform: translateX(-50%) scale(1.08); }
  100% { transform: translateX(-50%) scale(1); }
}

/* Floating Buttons */
.floating-btn-group {
  position: fixed;
  bottom: 18px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 12px;
  z-index: 9999;
  animation: heartbeat 2.5s infinite ease-in-out,
             fadeSlideUp 0.6s ease-out forwards;
}

/* Iframe Modal */
#iframe-modal {
  display: none;
  position: fixed;
  inset: 0;
  z-index: 9999;
  background: rgba(0,0,0,0.6);
  backdrop-filter: blur(4px);
}

.modal-content {
  position: relative;
  margin: 2% auto;
  background: #fff;
  border-radius: 16px;
  width: 95%;
  height: 90%;
  box-shadow: 0 8px 24px rgba(0,0,0,0.3);
  overflow: hidden;
}

#modal-iframe {
  width: 100%;
  height: 105%;
  border: none;
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 18px;
  font-size: 30px;
  cursor: pointer;
  z-index: 10;
}
.close-btn:hover { color: #e11d48; }
</style>

<script>
document.addEventListener("DOMContentLoaded", () => {

  /* Floating Button Group */
  const btnGroup = document.createElement("div");
  btnGroup.className = "floating-btn-group";

  const buttons = [
    { text: "📌 Blog", bg: "#16a34a", url: "https://debeatzgh2.blogspot.com/" },
    { text: "💡 Ideas", bg: "#c026d3", url: "https://debeatzgh.wordpress.com/" }
  ];

  /* Modal */
  const modal = document.createElement("div");
  modal.id = "iframe-modal";
  modal.innerHTML = `
    <div class="modal-content">
      <span class="close-btn">&times;</span>
      <iframe id="modal-iframe" loading="lazy"></iframe>
    </div>`;
  document.body.appendChild(modal);

  /* Buttons */
  buttons.forEach(btn => {
    const a = document.createElement("a");
    a.href = "#";
    a.textContent = btn.text;
    Object.assign(a.style, {
      background: btn.bg,
      color: "#fff",
      padding: "12px 20px",
      borderRadius: "30px",
      fontWeight: "700",
      textDecoration: "none",
      boxShadow: "0 4px 10px rgba(0,0,0,0.25)"
    });

    a.onclick = e => {
      e.preventDefault();
      document.getElementById("modal-iframe").src = btn.url;
      modal.style.display = "block";
    };

    btnGroup.appendChild(a);
  });

  document.body.appendChild(btnGroup);

  /* Close Modal */
  document.addEventListener("click", e => {
    if (e.target.classList.contains("close-btn") || e.target === modal) {
      modal.style.display = "none";
      document.getElementById("modal-iframe").src = "";
    }
  });
});
</script>
