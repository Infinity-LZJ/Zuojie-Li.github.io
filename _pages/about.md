---
permalink: /
title: "网址停用，最新链接"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

# 🧪 SCI 论文风格 · 网络迁移动画 | 旧站存档 · 新站启航

<div class="academic-migration">
  <canvas id="academicCanvas" class="neuron-canvas"></canvas>
  <div class="paper-card">
    <div class="article-meta">
      <span class="doi-badge">📄 DOI: 10.1234/ACAD.NET.MIG</span>
      <span class="version">正式公告 v2.0</span>
    </div>
    <h1 class="notice-title">
      <span class="old-archive">Legacy Repository</span> 
      <span class="separator">→</span>
      <span class="new-index">New Digital Hub</span>
    </h1>
    <div class="status-block">
      <div class="status-item archived">
        🧬 旧站已停更 · 内容迁移至新版学术平台
        <div class="archive-date">Archive Date: 2026.05</div>
      </div>
      <div class="status-item active">
        🌐 全新站点 · 增强索引 · 即时访问
      </div>
    </div>
    <div class="url-container">
      <span class="url-label">🔗 新站点入口 (点击跳转)</span>
      <div class="url-line">
        <span id="newSiteUrlDisplay" class="site-url">https://journal-newhub.ac.cn</span>
        <button id="editUrlBtn" class="edit-icon" title="修改新网址">✎</button>
      </div>
    </div>
    <a href="#" id="academicVisitBtn" class="cite-button">
      📖 前往新站点 → <span class="arrow"></span>
    </a>
    <p class="citation-note">Citation network animation · 粒子连线模拟学术引用关系<br>鼠标/手指划过节点 → 触发引力波效应</p>
  </div>
</div>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  .academic-migration {
    position: relative;
    width: 100%;
    min-height: 540px;
    height: auto;
    border-radius: 28px;
    overflow: hidden;
    background: #fbfdfe;
    box-shadow: 0 12px 28px rgba(0, 0, 0, 0.04), 0 0 0 1px rgba(0, 0, 0, 0.02);
    margin: 28px 0;
    font-family: 'Inter', 'Segoe UI', 'Roboto', 'Georgia', system-ui, -apple-system, 'Times New Roman', serif;
  }
  .neuron-canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: block;
    pointer-events: auto;
    z-index: 1;
  }
  .paper-card {
    position: relative;
    z-index: 2;
    width: 100%;
    max-width: 620px;
    margin: 2rem auto;
    padding: 2rem 2rem 2rem 2rem;
    background: rgba(255, 255, 250, 0.92);
    backdrop-filter: blur(2px);
    border-radius: 32px;
    box-shadow: 0 10px 25px -8px rgba(0, 0, 0, 0.05), 0 0 0 1px rgba(80, 100, 140, 0.12);
    pointer-events: auto;
    transition: all 0.2s;
    text-align: center;
  }
  .article-meta {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    font-size: 0.7rem;
    color: #2c5a6e;
    border-bottom: 1px dashed #cbdae6;
    padding-bottom: 0.6rem;
    margin-bottom: 1.2rem;
    letter-spacing: 0.3px;
  }
  .doi-badge {
    font-family: monospace;
    background: #eef3fa;
    padding: 0.2rem 0.6rem;
    border-radius: 24px;
    font-weight: 500;
  }
  .version {
    font-style: italic;
    opacity: 0.7;
  }
  .notice-title {
    font-size: 1.7rem;
    font-weight: 500;
    margin: 0.6rem 0 0.8rem;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: baseline;
    gap: 0.5rem;
    font-family: 'Times New Roman', 'Georgia', serif;
  }
  .old-archive {
    color: #5e7c92;
    text-decoration: line-through;
    font-weight: 400;
    background: #f1f3f7;
    padding: 0 0.5rem;
    border-radius: 30px;
    font-size: 1.3rem;
  }
  .separator {
    font-size: 1.3rem;
    color: #2c6e9e;
    font-weight: 300;
  }
  .new-index {
    color: #1f6e43;
    background: #e0f0ea;
    padding: 0 0.7rem;
    border-radius: 30px;
    font-weight: 500;
    font-size: 1.3rem;
    letter-spacing: -0.2px;
  }
  .status-block {
    background: #f9fbfd;
    border-radius: 24px;
    padding: 0.8rem 1.2rem;
    margin: 1rem 0;
    box-shadow: inset 0 0 0 1px #e7edf4, 0 2px 4px rgba(0,0,0,0.02);
  }
  .status-item {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    flex-wrap: wrap;
    padding: 0.5rem 0;
    border-bottom: 1px solid #e2e8f0;
    font-size: 0.9rem;
  }
  .status-item:last-child {
    border-bottom: none;
  }
  .archived {
    color: #4f6f8f;
  }
  .active {
    color: #1b6b4c;
    font-weight: 500;
  }
  .archive-date {
    font-size: 0.65rem;
    font-family: monospace;
    background: #eef2f6;
    padding: 0.2rem 0.6rem;
    border-radius: 20px;
  }
  .url-container {
    background: #ffffff;
    border-radius: 20px;
    padding: 0.6rem 0.8rem;
    margin: 1rem 0 0.8rem;
    border: 1px solid #dce5ec;
    text-align: left;
  }
  .url-label {
    font-size: 0.7rem;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    color: #3f6a8c;
  }
  .url-line {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 0.5rem;
    margin-top: 0.3rem;
  }
  .site-url {
    font-family: 'SF Mono', 'Fira Code', monospace;
    font-size: 0.9rem;
    background: #f2f6f9;
    padding: 0.2rem 0.7rem;
    border-radius: 24px;
    color: #1f4970;
    word-break: break-all;
    flex: 1;
  }
  .edit-icon {
    background: #eef2f8;
    border: none;
    font-size: 1rem;
    cursor: pointer;
    width: 28px;
    height: 28px;
    border-radius: 40px;
    transition: 0.1s;
    color: #2c5a6e;
    font-weight: bold;
    line-height: 1;
  }
  .edit-icon:hover {
    background: #dce5ef;
    transform: scale(0.96);
  }
  .cite-button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
    background: #fff;
    border: 1px solid #9cb8d0;
    padding: 0.7rem 1.6rem;
    border-radius: 42px;
    font-weight: 600;
    font-size: 0.9rem;
    margin-top: 0.8rem;
    color: #1e5a7d;
    text-decoration: none;
    transition: all 0.2s ease;
    cursor: pointer;
    backdrop-filter: blur(2px);
    box-shadow: 0 1px 2px rgba(0,0,0,0.02);
  }
  .cite-button:hover {
    background: #eef3fc;
    border-color: #6a9ec0;
    box-shadow: 0 4px 10px rgba(55, 94, 128, 0.08);
    transform: translateY(-1px);
  }
  .citation-note {
    font-size: 0.7rem;
    margin-top: 1rem;
    color: #697e94;
    border-top: 1px solid #e2eaf1;
    padding-top: 0.9rem;
    font-style: italic;
  }
  @media (max-width: 640px) {
    .paper-card { width: 90%; margin: 1.2rem auto; padding: 1.2rem; }
    .notice-title { font-size: 1.2rem; }
    .old-archive, .new-index { font-size: 1rem; }
    .site-url { font-size: 0.7rem; }
    .status-item { flex-direction: column; gap: 6px; }
  }
</style>

<script>
  (function() {
    // ---------- SCI清新风格粒子网络 ----------
    const canvas = document.getElementById('academicCanvas');
    if (!canvas) return;
    let ctx = canvas.getContext('2d');
    let width, height;
    let particles = [];
    let mouseX = null, mouseY = null;
    let animationId = null;
    
    // 可配置参数 (学术清新)
    const PARTICLE_COUNT = 82;
    const CONNECT_DIST = 135;
    const MOUSE_RADIUS = 100;
    const REPULSION = 0.45;
    
    // 新站点链接 (默认学术风格地址)
    let currentSiteUrl = "https://journal-newhub.ac.cn";
    
    // UI元素绑定
    const urlDisplaySpan = document.getElementById('newSiteUrlDisplay');
    const visitBtn = document.getElementById('academicVisitBtn');
    const editBtn = document.getElementById('editUrlBtn');
    
    function updateUrlUI() {
      if (urlDisplaySpan) urlDisplaySpan.innerText = currentSiteUrl;
      if (visitBtn) {
        visitBtn.onclick = (e) => {
          e.preventDefault();
          if (currentSiteUrl && !currentSiteUrl.startsWith('http')) {
            window.open('https://' + currentSiteUrl, '_blank');
          } else {
            window.open(currentSiteUrl, '_blank');
          }
        };
      }
    }
    
    if (editBtn) {
      editBtn.addEventListener('click', () => {
        let newUrl = prompt('✏️ 请输入新学术站点的完整地址 (包含 https:// 或 http://):', currentSiteUrl);
        if (newUrl && newUrl.trim() !== "") {
          currentSiteUrl = newUrl.trim();
          updateUrlUI();
        }
      });
    }
    updateUrlUI();
    
    // 网格绘制函数 (学术坐标纸风格)
    function drawGrid() {
      if (!ctx) return;
      const step = 38;
      ctx.save();
      ctx.strokeStyle = "#d9e2ec";
      ctx.lineWidth = 0.6;
      // 垂直线
      for (let x = step; x < width; x += step) {
        ctx.beginPath();
        ctx.moveTo(x, 0);
        ctx.lineTo(x, height);
        ctx.stroke();
      }
      // 水平线
      for (let y = step; y < height; y += step) {
        ctx.beginPath();
        ctx.moveTo(0, y);
        ctx.lineTo(width, y);
        ctx.stroke();
      }
      // 绘制坐标轴示意 (轻量轴)
      ctx.beginPath();
      ctx.lineWidth = 1.2;
      ctx.strokeStyle = "#8ba3bc";
      ctx.moveTo(0, height/2);
      ctx.lineTo(width, height/2);
      ctx.moveTo(width/2, 0);
      ctx.lineTo(width/2, height);
      ctx.stroke();
      ctx.restore();
    }
    
    function initParticles() {
      particles = [];
      for (let i = 0; i < PARTICLE_COUNT; i++) {
        particles.push({
          x: Math.random() * width,
          y: Math.random() * height,
          vx: (Math.random() - 0.5) * 0.35,
          vy: (Math.random() - 0.5) * 0.35,
          radius: Math.random() * 2.2 + 1.2,
          baseHue: 190 + Math.random() * 30, // 蓝绿清新调
        });
      }
    }
    
    function updateParticles() {
      for (let p of particles) {
        // 鼠标影响 (轻微引力/斥力，学术交互)
        if (mouseX !== null && mouseY !== null) {
          let dx = p.x - mouseX;
          let dy = p.y - mouseY;
          let dist = Math.hypot(dx, dy);
          if (dist < MOUSE_RADIUS) {
            let force = (MOUSE_RADIUS - dist) / MOUSE_RADIUS;
            let angle = Math.atan2(dy, dx);
            // 轻柔排斥使粒子散开，增加生动性
            p.vx += Math.cos(angle) * force * REPULSION * 0.5;
            p.vy += Math.sin(angle) * force * REPULSION * 0.5;
          }
        }
        // 阻尼
        p.vx *= 0.992;
        p.vy *= 0.992;
        p.x += p.vx;
        p.y += p.vy;
        
        // 边界柔和反弹 (留白边)
        const margin = 12;
        if (p.x < margin) { p.x = margin; p.vx *= -0.65; }
        if (p.x > width - margin) { p.x = width - margin; p.vx *= -0.65; }
        if (p.y < margin) { p.y = margin; p.vy *= -0.65; }
        if (p.y > height - margin) { p.y = height - margin; p.vy *= -0.65; }
      }
    }
    
    function drawConnections() {
      for (let i = 0; i < particles.length; i++) {
        for (let j = i + 1; j < particles.length; j++) {
          const dx = particles[i].x - particles[j].x;
          const dy = particles[i].y - particles[j].y;
          const dist = Math.hypot(dx, dy);
          if (dist < CONNECT_DIST) {
            let opacity = (1 - dist / CONNECT_DIST) * 0.38;
            ctx.beginPath();
            ctx.moveTo(particles[i].x, particles[i].y);
            ctx.lineTo(particles[j].x, particles[j].y);
            ctx.strokeStyle = `rgba(96, 142, 176, ${opacity * 0.9})`;
            ctx.lineWidth = 0.9;
            ctx.stroke();
          }
        }
      }
    }
    
    function drawParticles() {
      for (let p of particles) {
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
        // 柔和水彩质感
        ctx.fillStyle = `rgba(79, 138, 182, 0.85)`;
        ctx.fill();
        ctx.shadowBlur = 3;
        ctx.shadowColor = "rgba(82, 150, 190, 0.3)";
        ctx.fill();
        ctx.shadowBlur = 0;
        // 核心高光
        ctx.beginPath();
        ctx.arc(p.x-0.8, p.y-0.8, p.radius * 0.35, 0, Math.PI * 2);
        ctx.fillStyle = `rgba(235, 248, 255, 0.95)`;
        ctx.fill();
      }
    }
    
    function animateAcademic() {
      if (!canvas || !ctx) return;
      ctx.clearRect(0, 0, width, height);
      // 背景极浅色调
      ctx.fillStyle = "#fbfdfe";
      ctx.fillRect(0, 0, width, height);
      drawGrid();          // 学术坐标线
      drawConnections();   // 网络连接
      drawParticles();     // 节点
      updateParticles();
      animationId = requestAnimationFrame(animateAcademic);
    }
    
    function resizeCanvas() {
      const container = canvas.parentElement;
      width = container.clientWidth;
      height = container.clientHeight;
      canvas.width = width;
      canvas.height = height;
      initParticles();
      if (ctx) {
        ctx.clearRect(0, 0, width, height);
        drawGrid();
      }
    }
    
    // 鼠标/触摸交互 (基于canvas坐标)
    function handleMove(e) {
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
      mouseY = null;
    }
    
    window.addEventListener('resize', () => {
      resizeCanvas();
    });
    
    canvas.addEventListener('mousemove', handleMove);
    canvas.addEventListener('mouseleave', handleLeave);
    canvas.addEventListener('touchmove', handleMove);
    canvas.addEventListener('touchend', handleLeave);
    canvas.addEventListener('touchcancel', handleLeave);
    
    resizeCanvas();
    animateAcademic();
  })();
</script>

> ✨ **学术网络交互说明**：画布模拟科研论文中的共现网络图（Co-authorship / Citation map）。鼠标或手指划过节点时，粒子会产生轻柔的引力偏移，展现知识流动的视觉隐喻。点击「编辑图标」可自定义新站链接，按钮与地址显示会同步更新。
