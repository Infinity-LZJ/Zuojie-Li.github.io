---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Basic
======
* Born: December 1996​
* party: Member of the Communist Party of China
* Workplace: Postdoc. Key Laboratory of Radiopharmaceuticals / Beam Technology of the Ministry of Education, Beijing Normal University

Education
======
* Ph.D in BeiJing Normal University, 2025
* M.S. in LiaoCheng Univeristy,  2022
* B.S. in LiaoCheng University, 2019

Work experience
======
* China Resources Snow Breweries，2017.10-2017.11
 
* Hengrui Pharmaceutical​，2018.12-2019.01
 
* NHU Pharmaceutical，2019.02-2019.07
  
Skills
======
* Computer-Aided Drug Design
  * Homology Modeling 
  * Design Optimization for Structures
  * Molecular Dynamics Simulation

* ​Antineoplastic Drugs​​ 
  * Target screening
  * Bioactivity Assessment
  * Mechanistic Study

* Radiopharmaceutical Drugs
  * PET
  * SPECT

Publications (1st. author)
======
* J Med Chem, 2025, 68(21), 23620-23631.
* J Med Chem, 2024, 67(24), 21644-21670.
* J Med Chem, 2024, 67(23), 21617-21628.
* J Med Chem, 2021, 64(24), 17920-17935.
* Mol Pharm, 2024, 21(10), 5305-5314.
* Mini Rew Med Chem, 2025, 25(17), 1321-1333.
* Dalton Trans, 2022, 51(33), 12604-12619.
* Dalton Trans, 2021, 50(1), 362-375.
* Monatsh Chem, 2020, 151(3), 353-367.
* J Liaocheng Univ, 2020, 33(5), 97-103. 

Awards
======
* The First-Class Award for Excellent Graduate Research at Liaocheng University
* The First Prize for Poster Presentation at the 4th Graduate Academic Conference of the College of Chemistry, Beijing Normal University
* The Excellent Poster Award at the 17th National Academic Conference on Radiopharmaceuticals and Labeled Compounds，Xian
* Atomic High-Tech Scholarship for Ph.D. Candidates

About Me
======
<div style="
    font-size: 1.2rem;
    font-weight: bold;
    background: linear-gradient(90deg, 
        #ff6b6b,  /* 柔和红 */
        #ffa726,  /* 柔和橙 */
        #ffd93d,  /* 柔和黄 */
        #4cd964,  /* 柔和绿 */
        #5ac8fa,  /* 柔和蓝 */
        #af52de,  /* 柔和紫 */
        #ff6b6b   /* 回到柔和红 */
    );
    background-size: 200% 100%;
    animation: softRainbow 10s ease-in-out infinite;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-align: left;
    padding: 20px;
    font-family: 'Helvetica Neue', sans-serif;
    text-shadow: 0 0 15px rgba(255, 255, 255, 0.3);
">
    Be true to yourself, and respect others.
</div>

<style>
@keyframes softRainbow {
    0%, 100% {
        background-position: 0% 50%;
    }
    50% {
        background-position: 100% 50%;
    }
}
</style>

<div id="stars-animation" style="
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 150px;
    z-index: 998;
    pointer-events: none;
    background: linear-gradient(to top, rgba(0,0,0,0.1), transparent);
">
    <!-- 星星将通过JS动态生成 -->
</div>

<script>
function createStars() {
    const container = document.getElementById('stars-animation');
    const starCount = 20;
    
    for (let i = 0; i < starCount; i++) {
        const star = document.createElement('div');
        const size = Math.random() * 15 + 5;
        const left = Math.random() * 100;
        const top = Math.random() * 150;
        const duration = Math.random() * 2 + 1;
        const delay = Math.random() * 3;
        
        star.style.cssText = `
            position: absolute;
            width: ${size}px;
            height: ${size}px;
            background: radial-gradient(circle, #fff 30%, #ffeb3b 70%);
            border-radius: 50%;
            left: ${left}%;
            top: ${top}px;
            animation: twinkle ${duration}s ease-in-out infinite ${delay}s;
            filter: drop-shadow(0 0 5px #ffeb3b);
        `;
        
        container.appendChild(star);
    }
}

// 页面加载后创建星星
if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', createStars);
} else {
    createStars();
}
</script>
