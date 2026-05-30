---
permalink: /
title: "网址停用，最新链接"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

# 🌐 网络迁移动画 · 旧站停更 · 新站启航

<div class="migration-stage">
  <canvas id="networkCanvas" class="network-bg"></canvas>
  <div class="announcement-card">
    <div class="badge">📢 重要迁移通知</div>
    <h1 class="old-site">旧站已停更 <span class="strike">(原地址失效)</span></h1>
    <div class="new-site-glow">
      ✨ 新站上线 ✨
      <div class="new-url" id="newSiteUrl">https://your-new-website.com</div>
    </div>
    <a href="#" id="visitBtn" class="glow-button">🚀 前往新站点 →</a>
    <p class="hint">轻点按钮跳转新世界 · 页面粒子网络为动态交互背景</p>
  </div>
</div>

<style>
  .migration-stage {
    position: relative;
    width: 100%;
    height: 560px;
    border-radius: 32px;
    overflow: hidden;
    background: radial-gradient(circle at 30% 10%, #0a0f2a, #03050b);
    box-shadow: 0 25px 45px rgba(0,0,0,0.5), inset 0 0 2px rgba(255,255,255,0.1);
    margin: 24px 0;
    font-family: 'Segoe UI', 'Poppins', system-ui, -apple-system, 'Inter', sans-serif;
  }
  .network-bg {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: block;
    pointer-events: auto;  /* 让canvas接收鼠标/触摸事件，用于粒子互动 */
    z-index: 1;
  }
  .announcement-card {
    position: relative;
    z-index: 2;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    backdrop-filter: blur(3px);
    pointer-events: none;   /* 让卡片大部分区域穿透，鼠标事件交给canvas，但按钮单独恢复 */
  }
  .badge {
    background: rgba(255,255,240,0.15);
    backdrop-filter: blur(8px);
    padding: 6px 18px;
    border-radius: 60px;
    font-size: 0.85rem;
    letter-spacing: 1px;
    font-weight: 500;
    color: #b9f3ff;
    border: 1px solid rgba(0,255,255,0.3);
    margin-bottom: 20px;
    display: inline-block;
    pointer-events: none;
  }
  .old-site {
    font-size: 2rem;
    font-weight: 600;
    margin: 0 0 8px 0;
    color: #cfdee9;
    text-shadow: 0 2px 5px rgba(0,0,0,0.3);
    pointer-events: none;
  }
  .strike {
    text-decoration: line-through;
    opacity: 0.7;
    font-size: 1rem;
    background: rgba(220,60,50,0.3);
    padding: 2px 10px;
    border-radius: 20px;
    margin-left: 12px;
  }
  .new-site-glow {
    background: linear-gradient(135deg, #0f212e, #001d2d);
    padding: 12px 28px;
    border-radius: 60px;
    margin: 16px 0 20px;
    font-weight: 700;
    font-size: 1.5rem;
    border: 1px solid rgba(0, 255, 255, 0.6);
    box-shadow: 0 0 18px rgba(0, 200, 255, 0.3);
    backdrop-filter: blur(5px);
    pointer-events: none;
    color: white;
  }
  .new-url {
    font-size: 1.2rem;
    font-family: monospace;
    letter-spacing: 1px;
    background: #00000066;
    padding: 6px 16px;
    border-radius: 40px;
    margin-top: 10px;
    word-break: break-all;
    font-weight: 500;
    color: #7efff0;
    border: 1px dashed cyan;
    pointer-events: none;
  }
  .glow-button {
    pointer-events: auto;
    background: linear-gradient(95deg, #00c6fb, #005bea);
    border: none;
    padding: 12px 32px;
    font-size: 1.2rem;
    font-weight: bold;
    border-radius: 48px;
    color: white;
    cursor: pointer;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 10px;
    box-shadow: 0 8px 20px rgba(0,160,255,0.3);
    transition: 0.2s ease;
    margin-top: 18px;
    backdrop-filter: blur(4px);
    border: 1px solid rgba(255,255,255,0.3);
  }
  .glow-button:hover {
    transform: scale(1.02);
    background: linear-gradient(95deg, #2ad4ff, #0077ea);
    box-shadow: 0 0 18px #00a6ff;
    letter-spacing: 1px;
  }
  .hint {
    font-size: 0.75rem;
    margin-top: 24px;
    opacity: 0.7;
    color: #acd7ff;
    background: rgba(0,0,0,0.3);
    padding: 4px 12px;
    border-radius: 40px;
    pointer-events: none;
  }
  @media (max-width: 600px) {
    .migration-stage { height: 520px; }
    .old-site { font-size: 1.4rem; }
    .new-site-glow { font-size: 1.1rem; padding: 8px 20px;}
    .new-url { font-size: 0.85rem; }
    .glow-button { padding: 8px 20px; font-size: 1rem;}
  }
</style>

<script>
  (function() {
    // ---- 粒子网络动画 ----
    const canvas = document.getElementById('networkCanvas');
    let ctx = canvas.getContext('2d');
    let width, height;
    let particles = [];
    const PARTICLE_COUNT = 130;
    let mouseX = null, mouseY = null;
    let isTouching = false;

    // 新站点链接 (用户可自行修改)
    const NEW_SITE_LINK = "https://your-new-website.com";  // 修改成真实新站地址

    function setupCanvas() {
      const rect = canvas.parentElement.getBoundingClientRect();
      width = canvas.parentElement.clientWidth;
      height = canvas.parentElement.clientHeight;
      canvas.width = width;
      canvas.height = height;
      initParticles();
    }

    function initParticles() {
      particles = [];
      for (let i = 0; i < PARTICLE_COUNT; i++) {
        particles.push({
          x: Math.random() * width,
          y: Math.random() * height,
          vx: (Math.random() - 0.5) * 0.8,
          vy: (Math.random() - 0.5) * 0.8,
          radius: Math.random() * 2.8 + 1.2,
        });
      }
    }

    function updateParticles() {
      for (let p of particles) {
        // 鼠标互动 (斥力效果 增强科技网络交互感)
        if (mouseX !== null && mouseY !== null) {
          let dx = p.x - mouseX;
          let dy = p.y - mouseY;
          let dist = Math.hypot(dx, dy);
          let force = 0;
          if (dist < 90) {
            force = (90 - dist) / 90 * 0.8;
            let angle = Math.atan2(dy, dx);
            p.vx += Math.cos(angle) * force * 0.35;
            p.vy += Math.sin(angle) * force * 0.35;
          }
        }
        // 速度阻尼与边界反弹 (带轻微摩擦)
        p.vx *= 0.99;
        p.vy *= 0.99;
        p.x += p.vx;
        p.y += p.vy;
        // 边缘弹性 + 轻微边界回推(留边)
        if (p.x < 5) { p.x = 5; p.vx *= -0.7; }
        if (p.x > width - 5) { p.x = width - 5; p.vx *= -0.7; }
        if (p.y < 5) { p.y = 5; p.vy *= -0.7; }
        if (p.y > height - 5) { p.y = height - 5; p.vy *= -0.7; }
      }
    }

    function drawNetwork() {
      if (!ctx) return;
      ctx.clearRect(0, 0, width, height);
      
      // 绘制半透明光晕背景 (深邃科技感)
      ctx.fillStyle = "#03050b";
      ctx.fillRect(0, 0, width, height);
      
      // 画连接线 (网络)
      for (let i = 0; i < particles.length; i++) {
        for (let j = i + 1; j < particles.length; j++) {
          const dx = particles[i].x - particles[j].x;
          const dy = particles[i].y - particles[j].y;
          const distance = Math.hypot(dx, dy);
          if (distance < 110) {
            let opacity = (1 - distance / 110) * 0.5;
            ctx.beginPath();
            ctx.moveTo(particles[i].x, particles[i].y);
            ctx.lineTo(particles[j].x, particles[j].y);
            ctx.strokeStyle = `rgba(80, 210, 255, ${opacity * 0.8})`;
            ctx.lineWidth = 1.2;
            ctx.stroke();
          }
        }
      }
      
      // 绘制粒子 (光点)
      for (let p of particles) {
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.radius, 0, Math.PI * 2);
        // 动态发光色
        const gradient = ctx.createRadialGradient(p.x-1, p.y-1, 1, p.x, p.y, p.radius*2);
        gradient.addColorStop(0, '#b5f0ff');
        gradient.addColorStop(1, '#2b9eff');
        ctx.fillStyle = gradient;
        ctx.fill();
        ctx.shadowBlur = 6;
        ctx.shadowColor = "#0af";
        ctx.fill();
        ctx.shadowBlur = 0;
      }
      // 额外绘制几簇光晕 (科技氛围)
      for (let p of particles.slice(0, 40)) {
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.radius * 1.6, 0, Math.PI * 2);
        ctx.fillStyle = 'rgba(0, 180, 255, 0.2)';
        ctx.fill();
      }
    }

    function animate() {
      if (!canvas.isConnected) return;
      updateParticles();
      drawNetwork();
      requestAnimationFrame(animate);
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
          isTouching = true;
        } else {
          mouseX = null;
          mouseY = null;
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
        mouseY = null;
      }
    }

    function handleMouseLeave() {
      mouseX = null;
      mouseY = null;
      isTouching = false;
    }

    function resizeObserver() {
      setupCanvas();
    }

    window.addEventListener('resize', () => {
      setupCanvas();
    });
    
    canvas.addEventListener('mousemove', handleMouseMove);
    canvas.addEventListener('mouseleave', handleMouseLeave);
    canvas.addEventListener('touchmove', handleMouseMove);
    canvas.addEventListener('touchend', () => { mouseX = null; mouseY = null; });
    canvas.addEventListener('touchcancel', () => { mouseX = null; mouseY = null; });
    
    setupCanvas();
    animate();

    // 新站点按钮交互 (动态读取新站点url)
    const newUrlSpan = document.getElementById('newSiteUrl');
    const visitBtn = document.getElementById('visitBtn');
    if (newUrlSpan) {
      newUrlSpan.innerText = NEW_SITE_LINK;
    }
    if (visitBtn) {
      visitBtn.addEventListener('click', (e) => {
        e.preventDefault();
        // 跳转到新站点（可替换真实地址）
        window.open(NEW_SITE_LINK, '_blank');
      });
    }
    // 允许用户随时双击卡片修改新站点url (便捷演示)
    const cardDiv = document.querySelector('.announcement-card');
    if (cardDiv) {
      cardDiv.addEventListener('dblclick', (e) => {
        if(e.target === visitBtn || visitBtn.contains(e.target)) return;
        let newLink = prompt('🔗 设置你的新网站完整地址 (包含https://):', NEW_SITE_LINK);
        if(newLink && newLink.trim() !== "") {
          window.NEW_SITE_LINK_OVERRIDE = newLink;
          document.getElementById('newSiteUrl').innerText = newLink;
          visitBtn.onclick = (ev) => { ev.preventDefault(); window.open(newLink, '_blank'); };
        }
      });
    }
    // 保证初始链接变量用于点击
    visitBtn.onclick = (e) => {
      e.preventDefault();
      window.open(NEW_SITE_LINK, '_blank');
    };
  })();
</script>

> 🔧 **小贴士**：双击卡片区域可实时修改新网站链接，粒子网络会随鼠标/手指移动产生动态波纹感，传达“旧站迁移 · 新域启航”的网络脉动。



