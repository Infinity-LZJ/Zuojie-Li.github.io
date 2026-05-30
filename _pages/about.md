---
permalink: /
title: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
<div class="nature-cover">
  <canvas id="natureCanvas" class="nature-bg"></canvas>
  <div class="cover-overlay">
    <!-- 模拟期刊刊头 -->
    <div class="journal-header">
      <span class="nature-logo">NATURE ACADEMIC</span>
      <span class="issue">访问网址迁移特刊 | 2026</span>
    </div>

    <!-- ✨ 新增：居中提示横幅 -->
    <div class="center-notice">
      <span class="notice-icon">✨</span> 网址停用，最新链接 <span class="notice-icon">✨</span>
    </div>

    <!-- 主视觉标题区 -->
    <div class="title-block">
      <h1 class="main-title">
        <span class="legacy">LEGACY REPOSITORY</span><br>
        <span class="transition-symbol">⟶</span><br>
        <span class="newhub">NEW DIGITAL HUB</span>
      </h1>
      <div class="status-line">
        <span class="badge-archived">● 旧站已停更</span>
        <span class="badge-active">● 新站已上线</span>
      </div>
      <div class="doi-message">
        <span class="doi-label">正式迁移公告 | DOI: 10.1038/s41586-026-00000-1</span>
      </div>
    </div>

    <!-- 新站点卡片（仿论文摘要框） -->
    <div class="site-card">
      <div class="card-inner">
        <div class="card-label">▸ 永久访问地址 ◂</div>
        <div class="new-site-url" id="natureNewUrl">https://zuojie-li.github.io</div>
        <div class="button-group">
          <a href="https://zuojie-li.github.io" id="natureVisitBtn" class="primary-btn" target="_blank" rel="noopener noreferrer">访问新站点 →</a>
          <button id="natureEditBtn" class="edit-btn">永远相信 · 美好的事情即将发生</button>
        </div>
        <p class="footer-note"></p>
      </div>
    </div>

    <!-- 底部期刊信息栏 -->
    <div class="footer-bar">
      <span>Springer Publishers Limited 2026</span>
      <span>|</span>
      <span>图像: 动态共现网络 © Zuojie_Li</span>
    </div>
  </div>
</div>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  .nature-cover {
    position: relative;
    width: 100%;
    min-height: 760px;
    background: #fefef7;
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 0 20px 35px -12px rgba(0, 0, 0, 0.1), 0 0 0 1px rgba(0, 0, 0, 0.05);
    margin: 32px 0;
    font-family: 'Helvetica Neue', 'Inter', 'Arial', system-ui, sans-serif;
  }
  .nature-bg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: block;
    pointer-events: auto;
    z-index: 1;
  }
  .cover-overlay {
    position: relative;
    z-index: 2;
    width: 100%;
    min-height: 760px;
    background: rgba(254, 254, 247, 0.82);
    backdrop-filter: blur(2px);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 2rem 2rem 1.2rem 2rem;
    pointer-events: none;
  }
  .journal-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    border-bottom: 2px solid #000;
    padding-bottom: 0.6rem;
    margin-bottom: 1rem;
    pointer-events: none;
  }
  .nature-logo {
    font-size: 1.9rem;
    font-weight: 700;
    letter-spacing: 1px;
    font-family: 'Times New Roman', serif;
    color: #000;
  }
  .issue {
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: #3a3a3a;
    font-weight: 500;
  }

  /* ✨ 居中提示样式 */
  .center-notice {
    text-align: center;
    font-size: 1.5rem;
    font-weight: 600;
    letter-spacing: 2px;
    background: linear-gradient(135deg, #f5e6d3, #fff0e0);
    padding: 0.6rem 1rem;
    margin: 0.5rem auto 0.5rem auto;
    border-radius: 60px;
    width: fit-content;
    max-width: 90%;
    border: 1px solid #e2c7a3;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.03);
    pointer-events: none;
    color: #b45f2b;
    font-family: 'Times New Roman', serif;
  }
  .notice-icon {
    font-size: 1.4rem;
    margin: 0 10px;
  }

  .title-block {
    text-align: center;
    margin: 0.8rem 0 1.2rem;
    pointer-events: none;
  }
  .main-title {
    font-family: 'Times New Roman', 'Georgia', serif;
    font-size: 2.8rem;
    font-weight: 600;
    line-height: 1.3;
    margin-bottom: 1rem;
  }
  .legacy {
    color: #7f8c8d;
    text-decoration: line-through;
    background: #eceff1;
    padding: 0 0.2rem;
    display: inline-block;
  }
  .transition-symbol {
    font-size: 2rem;
    font-weight: 300;
    color: #2c6e9e;
    margin: 0.2rem 0;
  }
  .newhub {
    color: #1e7f5e;
    background: #e0f0ea;
    padding: 0 0.2rem;
    display: inline-block;
  }
  .status-line {
    display: flex;
    justify-content: center;
    gap: 2rem;
    margin-top: 0.8rem;
    font-size: 0.9rem;
    font-weight: 500;
  }
  .badge-archived {
    color: #b44;
  }
  .badge-active {
    color: #2a7f6e;
  }
  .doi-message {
    margin-top: 1rem;
    font-size: 0.7rem;
    font-family: monospace;
    letter-spacing: 0.3px;
    background: #f0f3f5;
    display: inline-block;
    padding: 0.2rem 1rem;
    border-radius: 40px;
    backdrop-filter: blur(2px);
  }
  .site-card {
    max-width: 520px;
    margin: 0.5rem auto 1rem;
    background: rgba(255, 255, 250, 0.96);
    border-radius: 28px;
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05), 0 0 0 1px #dce5ec;
    padding: 1.3rem 1.8rem;
    pointer-events: auto;
    backdrop-filter: blur(0);
    transition: 0.1s;
  }
  .card-inner {
    text-align: center;
  }
  .card-label {
    font-size: 0.7rem;
    letter-spacing: 2px;
    font-weight: 500;
    color: #2c6e9e;
    margin-bottom: 12px;
  }
  .new-site-url {
    font-family: 'SF Mono', 'Fira Code', monospace;
    font-size: 0.95rem;
    background: #f2f6f9;
    padding: 0.5rem 0.8rem;
    border-radius: 32px;
    color: #145c8a;
    word-break: break-all;
    margin-bottom: 18px;
    border: 1px solid #e2e8f0;
  }
  .button-group {
    display: flex;
    gap: 14px;
    justify-content: center;
    flex-wrap: wrap;
  }
  .primary-btn, .edit-btn {
    border: none;
    padding: 8px 24px;
    font-size: 0.85rem;
    font-weight: 600;
    border-radius: 36px;
    cursor: pointer;
    transition: 0.15s;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 4px;
  }
  .primary-btn {
    background: #1e3b4f;
    color: white;
    box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  }
  .primary-btn:hover {
    background: #0f2c3c;
    transform: translateY(-1px);
  }
  .edit-btn {
    background: #edf2f7;
    color: #2d4a6e;
    border: 1px solid #cad2db;
  }
  .edit-btn:hover {
    background: #e2e8f0;
  }
  .footer-note {
    font-size: 0.65rem;
    color: #6b7b8c;
    margin-top: 20px;
    border-top: 1px solid #eef2f5;
    padding-top: 12px;
    font-style: italic;
  }
  .footer-bar {
    display: flex;
    justify-content: center;
    gap: 1rem;
    font-size: 0.6rem;
    color: #5a6e7c;
    border-top: 1px solid #dadfe5;
    padding-top: 1rem;
    margin-top: 0.5rem;
    pointer-events: none;
  }
  @media (max-width: 620px) {
    .cover-overlay { padding: 1rem; min-height: 720px; }
    .main-title { font-size: 1.8rem; }
    .site-card { margin: 0.5rem; padding: 1rem; }
    .new-site-url { font-size: 0.7rem; }
    .journal-header { margin-bottom: 0.8rem; }
    .nature-logo { font-size: 1.5rem; }
    .center-notice { font-size: 1.1rem; padding: 0.3rem 0.8rem; }
    .notice-icon { font-size: 1rem; margin: 0 5px; }
  }
</style>

<script>
  (function() {
    // ---------- 粒子网络（完全保留）----------
    const canvas = document.getElementById('natureCanvas');
    if (!canvas) return;
    let ctx = canvas.getContext('2d');
    let width, height;
    let particles = [];
    let mouseX = null, mouseY = null;
    let animFrame;
    
    const PARTICLE_COUNT = 105;
    const CONNECTION_DIST = 135;
    const MOUSE_RADIUS = 110;
    const REPULSION = 0.5;
    
    let currentUrl = "https://zuojie-li.github.io";
    const urlSpan = document.getElementById('natureNewUrl');
    const visitBtn = document.getElementById('natureVisitBtn');
    const editBtn = document.getElementById('natureEditBtn');
    
    function updateUrlUI() {
      if (urlSpan) urlSpan.innerText = currentUrl;
      if (visitBtn) visitBtn.href = currentUrl;
    }
    if (editBtn) {
      editBtn.addEventListener('click', () => {
        let newLink = prompt('✏️ 编辑新站点链接 (包含 https://)', currentUrl);
        if (newLink && newLink.trim() !== "") {
          currentUrl = newLink.trim();
          updateUrlUI();
        }
      });
    }
    updateUrlUI();
    
    function initParticles() {
      particles = [];
      for (let i = 0; i < PARTICLE_COUNT; i++) {
        particles.push({
          x: Math.random() * width,
          y: Math.random() * height,
          vx: (Math.random() - 0.5) * 0.4,
          vy: (Math.random() - 0.5) * 0.4,
          radius: Math.random() * 2.6 + 1.0,
          color: `hsla(${195 + Math.random() * 30}, 55%, 62%, 0.7)`
        });
      }
    }
    
    function drawGrid() {
      ctx.save();
      ctx.strokeStyle = "#e2e8f0";
      ctx.lineWidth = 0.5;
      const step = 42;
      for (let x = step; x < width; x += step) {
        ctx.beginPath();
        ctx.moveTo(x, 0);
        ctx.lineTo(x, height);
        ctx.stroke();
      }
      for (let y = step; y < height; y += step) {
        ctx.beginPath();
        ctx.moveTo(0, y);
        ctx.lineTo(width, y);
        ctx.stroke();
      }
      ctx.fillStyle = "#cbdbe6";
      for (let x = step/2; x < width; x += step) {
        for (let y = step/2; y < height; y += step) {
          ctx.beginPath();
          ctx.arc(x, y, 1.2, 0, Math.PI*2);
          ctx.fill();
        }
      }
      ctx.restore();
    }
    
    function updateParticles() {
      for (let p of particles) {
        if (mouseX !== null && mouseY !== null) {
          let dx = p.x - mouseX;
          let dy = p.y - mouseY;
          let dist = Math.hypot(dx, dy);
          if (dist < MOUSE_RADIUS) {
            let force = (MOUSE_RADIUS - dist) / MOUSE_RADIUS;
            let angle = Math.atan2(dy, dx);
            p.vx += Math.cos(angle) * force * REPULSION * 0.45;
            p.vy += Math.sin(angle) * force * REPULSION * 0.45;
          }
        }
        p.vx *= 0.99;
        p.vy *= 0.99;
        p.x += p.vx;
        p.y += p.vy;
        const margin = 15;
        if (p.x < margin) { p.x = margin; p.vx *= -0.6; }
        if (p.x > width - margin) { p.x = width - margin; p.vx *= -0.6; }
        if (p.y < margin) { p.y = margin; p.vy *= -0.6; }
        if (p.y > height - margin) { p.y = height - margin; p.vy *= -0.6; }
      }
    }
    
    function drawConnections() {
      for (let i = 0; i < particles.length; i++) {
        for (let j = i+1; j < particles.length; j++) {
          const dx = particles[i].x - particles[j].x;
          const dy = particles[i].y - particles[j].y;
          const dist = Math.hypot(dx, dy);
          if (dist < CONNECTION_DIST) {
            let opacity = (1 - dist / CONNECTION_DIST) * 0.45;
            ctx.beginPath();
            ctx.moveTo(particles[i].x, particles[i].y);
            ctx.lineTo(particles[j].x, particles[j].y);
            ctx.strokeStyle = `rgba(76, 138, 174, ${opacity * 0.9})`;
            ctx.lineWidth = 0.9;
            ctx.stroke();
          }
        }
      }
    }
    
    function drawParticles() {
      for (let p of particles) {
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.radius, 0, Math.PI*2);
        ctx.fillStyle = p.color || "#568db3";
        ctx.fill();
        ctx.shadowBlur = 3;
        ctx.shadowColor = "rgba(86, 141, 179, 0.3)";
        ctx.fill();
        ctx.shadowBlur = 0;
        ctx.beginPath();
        ctx.arc(p.x-0.8, p.y-0.8, p.radius*0.3, 0, Math.PI*2);
        ctx.fillStyle = "rgba(255, 255, 245, 0.9)";
        ctx.fill();
      }
    }
    
    function animate() {
      if (!ctx) return;
      ctx.clearRect(0, 0, width, height);
      ctx.fillStyle = "#fefef7";
      ctx.fillRect(0, 0, width, height);
      drawGrid();
      drawConnections();
      drawParticles();
      updateParticles();
      animFrame = requestAnimationFrame(animate);
    }
    
    function resizeCanvas() {
      const container = canvas.parentElement;
      width = container.clientWidth;
      height = container.clientHeight;
      canvas.width = width;
      canvas.height = height;
      initParticles();
    }
    
    function handleMouseMove(e) {
      const rect = canvas.getBoundingClientRect();
      const scaleX = canvas.width / rect.width;
      const scaleY = canvas.height / rect.height;
      let clientX, clientY;
      if (e.touches) {
        if (e.touches.length) {
          clientX = e.touches[0].clientX;
          clientY = e.touches[0].clientY;
        } else {
          mouseX = null;
          return;
        }
      } else {
        clientX = e.clientX;
        clientY = e.clientY;
      }
      if (clientX >= rect.left && clientX <= rect.right && clientY >= rect.top && clientY <= rect.bottom) {
        mouseX = (clientX - rect.left) * scaleX;
        mouseY = (clientY - rect.top) * scaleY;
      } else {
        mouseX = null;
      }
    }
    
    function handleLeave() {
      mouseX = null;
    }
    
    window.addEventListener('resize', () => { resizeCanvas(); });
    canvas.addEventListener('mousemove', handleMouseMove);
    canvas.addEventListener('mouseleave', handleLeave);
    canvas.addEventListener('touchmove', handleMouseMove);
    canvas.addEventListener('touchend', handleLeave);
    canvas.addEventListener('touchcancel', handleLeave);
    
    resizeCanvas();
    animate();
  })();
</script>


