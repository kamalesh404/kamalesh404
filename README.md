<style>
  @keyframes gradient-shift {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }
  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
  }
  @keyframes glow-pulse {
    0%, 100% { box-shadow: 0 0 15px rgba(207,106,62,0.3); }
    50% { box-shadow: 0 0 30px rgba(207,106,62,0.6), 0 0 60px rgba(207,106,62,0.2); }
  }
  @keyframes border-dance {
    0% { border-color: #cf6a3e; }
    25% { border-color: #e89a70; }
    50% { border-color: #cf6a3e; }
    75% { border-color: #e2a070; }
    100% { border-color: #cf6a3e; }
  }
  @keyframes slide-in-left {
    from { opacity: 0; transform: translateX(-40px); }
    to { opacity: 1; transform: translateX(0); }
  }
  @keyframes slide-in-right {
    from { opacity: 0; transform: translateX(40px); }
    to { opacity: 1; transform: translateX(0); }
  }
  @keyframes slide-in-up {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes fade-in {
    from { opacity: 0; }
    to { opacity: 1; }
  }
  @keyframes scale-in {
    from { opacity: 0; transform: scale(0.8); }
    to { opacity: 1; transform: scale(1); }
  }
  @keyframes spin-slow {
    from { transform: rotate(0deg); }
    to { transform: rotate(360deg); }
  }
  @keyframes dash {
    to { stroke-dashoffset: 0; }
  }
  @keyframes shimmer {
    0% { background-position: -200% 0; }
    100% { background-position: 200% 0; }
  }
  @keyframes blob-morph {
    0%, 100% { border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%; }
    25% { border-radius: 30% 60% 70% 40% / 50% 60% 30% 60%; }
    50% { border-radius: 50% 60% 30% 60% / 30% 50% 70% 60%; }
    75% { border-radius: 60% 30% 60% 40% / 60% 40% 30% 70%; }
  }
  .profile-card {
    animation: slide-in-up 0.8s cubic-bezier(0.16, 1, 0.3, 1) both, glow-pulse 3s ease-in-out infinite 1s;
    border: 1px solid rgba(207,106,62,0.3);
    border-radius: 16px;
    padding: 30px;
    background: linear-gradient(135deg, rgba(27,21,18,0.95), rgba(36,28,23,0.95));
    position: relative;
    overflow: hidden;
  }
  .profile-card::before {
    content: '';
    position: absolute;
    top: -2px; left: -2px; right: -2px; bottom: -2px;
    background: linear-gradient(45deg, #cf6a3e, #e89a70, #cf6a3e, #e2a070, #cf6a3e);
    background-size: 400% 400%;
    animation: gradient-shift 4s ease infinite;
    border-radius: 17px;
    z-index: -1;
  }
  .profile-card::after {
    content: '';
    position: absolute;
    inset: 2px;
    background: linear-gradient(135deg, rgba(27,21,18,0.98), rgba(36,28,23,0.98));
    border-radius: 14px;
    z-index: -1;
  }
  .section-title {
    animation: slide-in-left 0.6s cubic-bezier(0.16, 1, 0.3, 1) both;
    border-left: 3px solid #cf6a3e;
    padding-left: 14px;
    margin: 40px 0 20px;
    color: #f4ede3;
    font-family: 'Segoe UI', system-ui, sans-serif;
  }
  .project-card {
    transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
    border: 1px solid rgba(207,106,62,0.15);
    border-radius: 12px;
    padding: 20px;
    background: rgba(27,21,18,0.6);
    position: relative;
    overflow: hidden;
  }
  .project-card:hover {
    transform: translateY(-4px);
    border-color: rgba(207,106,62,0.5);
    box-shadow: 0 8px 32px rgba(207,106,62,0.15);
  }
  .project-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, #cf6a3e, transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .project-card:hover::before { opacity: 1; }
  .skill-badge {
    display: inline-block;
    padding: 5px 12px;
    border-radius: 8px;
    font-size: 12px;
    font-weight: 600;
    margin: 3px;
    border: 1px solid rgba(207,106,62,0.2);
    background: rgba(207,106,62,0.08);
    color: #e89a70;
    transition: all 0.2s;
  }
  .skill-badge:hover {
    background: rgba(207,106,62,0.2);
    border-color: rgba(207,106,62,0.5);
    transform: translateY(-2px);
  }
  .live-dot {
    display: inline-block;
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #00c853;
    margin-right: 6px;
    animation: glow-pulse 2s ease-in-out infinite;
  }
  .blob {
    animation: blob-morph 8s ease-in-out infinite;
    background: linear-gradient(135deg, rgba(207,106,62,0.15), rgba(232,154,112,0.1));
    filter: blur(40px);
  }
  .stagger-1 { animation-delay: 0.1s; }
  .stagger-2 { animation-delay: 0.2s; }
  .stagger-3 { animation-delay: 0.3s; }
  .stagger-4 { animation-delay: 0.4s; }
  .stagger-5 { animation-delay: 0.5s; }
  .stagger-6 { animation-delay: 0.6s; }
  .tech-tag {
    display: inline-block;
    padding: 3px 10px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 500;
    margin: 2px;
    background: rgba(207,106,62,0.1);
    color: #e89a70;
    border: 1px solid rgba(207,106,62,0.15);
  }
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, rgba(207,106,62,0.4), transparent);
    margin: 40px 0;
  }
  a { text-decoration: none; }
</style>

<div align="center">

<!-- ====== ANIMATED BLOB BACKGROUND ====== -->
<div style="position:relative;width:100%;overflow:hidden;">

<!-- ====== HERO SECTION ====== -->
<div style="animation: scale-in 0.8s cubic-bezier(0.16,1,0.3,1) both; padding: 40px 0 20px;">

<!-- Animated rotating ring around avatar -->
<div style="position:relative;display:inline-block;width:130px;height:130px;">
  <div style="position:absolute;inset:-4px;border-radius:50%;background:conic-gradient(from 0deg,#cf6a3e,#e89a70,#cf6a3e,#e2a070,#cf6a3e);animation:spin-slow 4s linear infinite;"></div>
  <div style="position:absolute;inset:0;border-radius:50%;background:#1b1512;"></div>
  <img src="https://avatars.githubusercontent.com/u/kamalesh4044" width="120" height="120" style="position:absolute;top:5px;left:5px;border-radius:50%;object-fit:cover;" alt="Kamalesh" />
</div>

<h1 style="margin-top:16px;font-family:'Segoe UI',system-ui,sans-serif;">
  <span style="animation:slide-in-up 0.6s 0.2s cubic-bezier(0.16,1,0.3,1) both;display:block;font-size:40px;font-weight:800;background:linear-gradient(135deg,#cf6a3e,#e89a70,#cf6a3e);background-size:200% auto;animation:gradient-shift 3s ease infinite,slide-in-up 0.6s 0.2s cubic-bezier(0.16,1,0.3,1) both;color:transparent;-webkit-background-clip:text;background-clip:text;letter-spacing:-1px;">
    Kamalesh Kumar A.
  </span>
</h1>

<p style="animation:fade-in 0.8s 0.4s cubic-bezier(0.16,1,0.3,1) both;color:#e89a70;font-size:18px;font-weight:600;margin:8px 0 4px;">
  Software Developer &middot; Full-Stack Engineer &middot; AI/ML Explorer
</p>

<p style="animation:fade-in 0.8s 0.5s both;color:#8B8B8B;font-size:14px;max-width:500px;margin:0 auto 20px;line-height:1.6;">
  Building high-performance web apps, real-time multiplayer systems, and intelligent AI experiences.
  <br/>Constantly exploring the bleeding edge of technology.
</p>

<!-- Animated status badge -->
<div style="animation:fade-in 0.8s 0.6s both;display:inline-flex;align-items:center;gap:8px;padding:6px 18px;border-radius:20px;background:rgba(207,106,62,0.1);border:1px solid rgba(207,106,62,0.3);color:#e89a70;font-size:13px;font-weight:600;">
  <span class="live-dot"></span>
  Available for opportunities
</div>

</div>
</div>

<!-- ====== PROFILE VIEWS + FOLLOWERS ====== -->
<div style="animation:fade-in 0.8s 0.7s both;margin: 24px 0;">
  <img src="https://komarev.com/ghpvc/?username=kamalesh4044&label=Profile%20Views&color=cf6a3e&style=flat-square&label_color=1b1512" />
  &nbsp;
  <img src="https://img.shields.io/github/followers/kamalesh4044?label=Followers&style=flat-square&color=cf6a3e&label_color=1b1512" />
  &nbsp;
  <img src="https://img.shields.io/github/stars/kamalesh4044?label=Total%20Stars&style=flat-square&color=cf6a3e&label_color=1b1512" />
</div>

<!-- ====== CONNECT LINKS ====== -->
<div style="animation:slide-in-up 0.6s 0.8s both;margin: 16px 0;">
  <a href="https://kamalesh4044.github.io/PORTFOLIO/">
    <img src="https://img.shields.io/badge/Portfolio-CF6A3E?style=for-the-badge&logo=vercel&logoColor=white&labelColor=1b1512" />
  </a>
  <a href="https://www.linkedin.com/in/kamalesh-kumar-a-308a89332/">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:kamalesh404e@gmail.com">
    <img src="https://img.shields.io/badge/Email-CF6A3E?style=for-the-badge&logo=gmail&logoColor=white&labelColor=1b1512" />
  </a>
</div>

</div>

<div class="divider"></div>

<!-- ====== ABOUT ====== -->
<h2 class="section-title" style="font-size:22px;">About Me</h2>

<div style="animation:slide-in-up 0.6s 0.2s both;max-width:750px;line-height:1.7;color:#b0b0b0;font-size:15px;">
I'm a <strong style="color:#e89a70;">Computer Science student</strong> and builder at heart. My world revolves around
<em>real-time multiplayer systems</em>, <em>AI-powered applications</em>, and <em>creative web experiences</em>.
I don't just write code — I architect <strong style="color:#f4ede3;">performant, elegant products</strong> that ship and scale.

From training <strong style="color:#f4ede3;">security-focused LLMs with QLoRA</strong> to building
<strong style="color:#f4ede3;">browser-based FPS games with 100+ concurrent players</strong>,
I thrive at the intersection of systems engineering and creative technology.
</div>

<!-- ====== INTERESTS / WHAT I DO ====== -->
<div style="animation:fade-in 0.8s 0.4s both;margin:20px 0;display:flex;flex-wrap:wrap;gap:8px;justify-content:center;">
  <span class="skill-badge">Full-Stack Development</span>
  <span class="skill-badge">Real-Time Networking</span>
  <span class="skill-badge">AI / Machine Learning</span>
  <span class="skill-badge">Game Development</span>
  <span class="skill-badge">Systems Engineering</span>
  <span class="skill-badge">Cloud & DevOps</span>
  <span class="skill-badge">Android / Kotlin</span>
  <span class="skill-badge">Bluetooth Security</span>
</div>

<div class="divider"></div>

<!-- ====== TECH STACK ====== -->
<h2 class="section-title" style="font-size:22px;">Tech Stack</h2>

<div style="animation:slide-in-up 0.6s 0.2s both;">

<h3 style="color:#cf6a3e;font-size:14px;letter-spacing:2px;text-transform:uppercase;margin-bottom:8px;font-family:monospace;">Languages</h3>
<p align="center">
  <img src="https://skillicons.dev/icons?i=c,cpp,cs,java,python,js,ts,html,css,php,ruby,go,rust" height="44" style="animation:float 3s ease-in-out infinite;" />
</p>

<h3 style="color:#cf6a3e;font-size:14px;letter-spacing:2px;text-transform:uppercase;margin:20px 0 8px;font-family:monospace;">Frameworks & Databases</h3>
<p align="center">
  <img src="https://skillicons.dev/icons?i=nodejs,express,react,nextjs,vue,angular,mysql,mongodb,postgres,firebase" height="44" style="animation:float 3s ease-in-out infinite 0.3s;" />
</p>

<h3 style="color:#cf6a3e;font-size:14px;letter-spacing:2px;text-transform:uppercase;margin:20px 0 8px;font-family:monospace;">DevOps & Tools</h3>
<p align="center">
  <img src="https://skillicons.dev/icons?i=git,github,docker,aws,linux,ubuntu,windows,bash,powershell,vscode,visualstudio,figma" height="44" style="animation:float 3s ease-in-out infinite 0.6s;" />
</p>

</div>

<div class="divider"></div>

<!-- ====== FEATURED PROJECTS ====== -->
<h2 class="section-title" style="font-size:22px;">Featured Projects</h2>

<!-- Project 1: SkillWarz FPS -->
<div class="project-card stagger-1" style="animation:slide-in-up 0.6s 0.1s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> SkillWarz FPS
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Real-time multiplayer first-person shooter with server-authoritative gameplay, low-latency WebSocket sync, live matchmaking, and weapon physics — all running in the browser.
  </p>
  <span class="tech-tag">JavaScript</span>
  <span class="tech-tag">Node.js</span>
  <span class="tech-tag">WebSocket</span>
  <span class="tech-tag">Three.js</span>
  <br/><br/>
  <a href="https://multiplayer-fps-game.onrender.com"><img src="https://img.shields.io/badge/PLAY_LIVE-CF6A3E?style=flat-square&labelColor=1b1512" /></a>
  <a href="https://github.com/kamalesh4044/multiplayer-fps-game"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/multiplayer-fps-game?style=social" />
</td>
</tr></table>
</div>

<!-- Project 2: Velocity.io -->
<div class="project-card stagger-2" style="animation:slide-in-up 0.6s 0.2s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> Velocity.io
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    High-performance competitive multiplayer browser FPS built with Three.js, Rapier3D physics engine, and Socket.io. Pushes browser networking to the absolute limit.
  </p>
  <span class="tech-tag">JavaScript</span>
  <span class="tech-tag">Three.js</span>
  <span class="tech-tag">Rapier3D</span>
  <span class="tech-tag">Socket.io</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/velocity.io"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/velocity.io?style=social" />
</td>
</tr></table>
</div>

<!-- Project 3: Void Runner -->
<div class="project-card stagger-3" style="animation:slide-in-up 0.6s 0.3s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> Void Runner
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Endless procedural runner deployed on Vercel — instant browser play with zero install, fully responsive 3D rendering, and procedural terrain generation.
  </p>
  <span class="tech-tag">JavaScript</span>
  <span class="tech-tag">Three.js</span>
  <span class="tech-tag">Vercel</span>
  <br/><br/>
  <a href="https://void-runner-seven.vercel.app"><img src="https://img.shields.io/badge/PLAY_LIVE-CF6A3E?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
</td>
</tr></table>
</div>

<!-- Project 4: SmartVisionGuard -->
<div class="project-card stagger-4" style="animation:slide-in-up 0.6s 0.4s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> SmartVisionGuard
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Real-time AI safety vision system — detects missing hard hats, zone intrusions &amp; spills using YOLO11. Streams annotated video + alerts to a live dashboard via FastAPI.
  </p>
  <span class="tech-tag">Python</span>
  <span class="tech-tag">YOLO11</span>
  <span class="tech-tag">FastAPI</span>
  <span class="tech-tag">OpenCV</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/SmartVisionGuard"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/SmartVisionGuard?style=social" />
</td>
</tr></table>
</div>

<!-- Project 5: SecForge -->
<div class="project-card stagger-5" style="animation:slide-in-up 0.6s 0.5s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> SecForge
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Fine-tune a security-focused coding LLM with QLoRA — prepare, train, merge, chat, evaluate, and serve it locally. No cloud lock-in. Full pipeline from data to deployment.
  </p>
  <span class="tech-tag">Python</span>
  <span class="tech-tag">QLoRA</span>
  <span class="tech-tag">Transformers</span>
  <span class="tech-tag">PEFT</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/secforge"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/secforge?style=social" />
</td>
</tr></table>
</div>

<!-- Project 6: ByteBrain -->
<div class="project-card stagger-6" style="animation:slide-in-up 0.6s 0.6s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> ByteBrain
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    100% private, in-browser AI Study Companion. Runs powerful LLMs directly on your local PC — no API keys, no server costs, total data privacy. Fully client-side inference.
  </p>
  <span class="tech-tag">TypeScript</span>
  <span class="tech-tag">WebLLM</span>
  <span class="tech-tag">Privacy-First</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/ByteBrain"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/ByteBrain?style=social" />
</td>
</tr></table>
</div>

<!-- Project 7: BLE-Advertise -->
<div class="project-card stagger-1" style="animation:slide-in-up 0.6s 0.7s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> BLE-Advertise
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Advertise fake BLE devices from Android to trigger Fast Pair, AirPods, Samsung &amp; Swift Pair pairing popups on nearby phones. Bluetooth security research tool.
  </p>
  <span class="tech-tag">Kotlin</span>
  <span class="tech-tag">Android</span>
  <span class="tech-tag">Bluetooth</span>
  <span class="tech-tag">Security</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/BLE-Advertise"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/BLE-Advertise?style=social" />
</td>
</tr></table>
</div>

<!-- Project 8: EvoDot -->
<div class="project-card stagger-2" style="animation:slide-in-up 0.6s 0.8s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> EvoDot
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Evolutionary algorithm experiment — populations adapt, mutate, and survive inside a living, real-time ecosystem built in Godot 4 with multiplayer capabilities.
  </p>
  <span class="tech-tag">GDScript</span>
  <span class="tech-tag">Godot 4</span>
  <span class="tech-tag">Multiplayer</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/evodot"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/evodot?style=social" />
</td>
</tr></table>
</div>

<!-- Project 9: Madras Drift -->
<div class="project-card stagger-3" style="animation:slide-in-up 0.6s 0.9s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> Madras Drift
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Open-world third-person driving and exploration game. Pushing mobile and web rendering boundaries with smooth real-time 3D graphics in Godot.
  </p>
  <span class="tech-tag">GDScript</span>
  <span class="tech-tag">Godot Engine</span>
  <span class="tech-tag">Open World</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/Madras-Drift"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/Madras-Drift?style=social" />
</td>
</tr></table>
</div>

<!-- Project 10: Jarvis Agent -->
<div class="project-card stagger-4" style="animation:slide-in-up 0.6s 1.0s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> Jarvis Agent
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Intelligent, modular Python automation assistant with autonomous planning, PC control, voice interaction, and long-term memory. Your personal AI agent.
  </p>
  <span class="tech-tag">Python</span>
  <span class="tech-tag">AI Agent</span>
  <span class="tech-tag">Voice</span>
  <span class="tech-tag">Automation</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/jarvis-agent"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/jarvis-agent?style=social" />
</td>
</tr></table>
</div>

<!-- Project 11: CrowdSafe AI -->
<div class="project-card stagger-5" style="animation:slide-in-up 0.6s 1.1s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> CrowdSafe AI
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    AI-powered real-time crowd monitoring system — detects people, tracks movement, and predicts dangerous stampedes using computer vision and deep learning.
  </p>
  <span class="tech-tag">Python</span>
  <span class="tech-tag">Computer Vision</span>
  <span class="tech-tag">Deep Learning</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/crowd_detection"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/crowd_detection?style=social" />
</td>
</tr></table>
</div>

<!-- Project 12: Project IGI -->
<div class="project-card stagger-6" style="animation:slide-in-up 0.6s 1.2s both;margin-bottom:16px;">
<table width="100%"><tr>
<td width="70%" valign="top">
  <h3 style="color:#f4ede3;margin:0 0 6px;font-size:17px;">
    <span style="color:#cf6a3e;">&#9654;</span> Project IGI
  </h3>
  <p style="color:#999;font-size:13px;line-height:1.5;margin:0 0 10px;">
    Recreation of the classic PROJECT: IGI — a tactical first-person shooter remake built with modern web technologies and 3D rendering.
  </p>
  <span class="tech-tag">TypeScript</span>
  <span class="tech-tag">WebGL</span>
  <span class="tech-tag">3D Rendering</span>
  <br/><br/>
  <a href="https://github.com/kamalesh4044/project_IGI"><img src="https://img.shields.io/badge/SOURCE-555?style=flat-square&labelColor=1b1512" /></a>
</td>
<td width="30%" align="right" valign="top">
  <img src="https://img.shields.io/github/stars/kamalesh4044/project_IGI?style=social" />
</td>
</tr></table>
</div>

<!-- More Projects Link -->
<div style="text-align:center;margin:24px 0;">
  <a href="https://github.com/kamalesh4044?tab=repositories">
    <img src="https://img.shields.io/badge/VIEW_ALL_36_REPOSITORIES-CF6A3E?style=for-the-badge&labelColor=1b1512" />
  </a>
</div>

<div class="divider"></div>

<!-- ====== MORE PROJECTS GRID ====== -->
<h2 class="section-title" style="font-size:22px;">More Creations</h2>

<div style="display:grid;grid-template-columns:repeat(3,1fr);gap:12px;animation:fade-in 0.8s 0.3s both;">

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">Social Media</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">Real-time social network with messaging</p>
  <span class="tech-tag">JavaScript</span>
  <span class="tech-tag">WebSocket</span>
</div>

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">AudioBridge</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">Cross-platform audio bridge system</p>
  <span class="tech-tag">Kotlin</span>
</div>

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">Gyrocam</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">Pro camera app with IMU metadata</p>
  <span class="tech-tag">Kotlin</span>
</div>

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">Ai Predictive Analytics</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">ML-powered predictive data analytics</p>
  <span class="tech-tag">Python</span>
</div>

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">RAG Chatbot</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">Retrieval-augmented generation chatbot</p>
  <span class="tech-tag">Python</span>
</div>

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">Weather Fusion</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">Beautiful weather data visualization</p>
  <span class="tech-tag">HTML</span>
</div>

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">AI Terminal Chat</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">Streaming terminal AI with sessions</p>
  <span class="tech-tag">TypeScript</span>
</div>

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">EvoDot Web</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">Browser client for EvoDot multiplayer</p>
  <span class="tech-tag">JavaScript</span>
</div>

<div class="project-card" style="text-align:center;padding:16px;">
  <h4 style="color:#e89a70;margin:0 0 4px;font-size:14px;">PC Auto</h4>
  <p style="color:#777;font-size:11px;margin:0 0 8px;">PC automation and scripting toolkit</p>
  <span class="tech-tag">Python</span>
</div>

</div>

<div class="divider"></div>

<!-- ====== GITHUB STATS ====== -->
<h2 class="section-title" style="font-size:22px;">GitHub Analytics</h2>

<div style="animation:slide-in-up 0.6s 0.2s both;display:flex;flex-wrap:wrap;gap:16px;justify-content:center;">
  <img src="https://github-readme-stats.vercel.app/api?username=kamalesh4044&show_icons=true&bg_color=1b1512&title_color=cf6a3e&text_color=b0b0b0&icon_color=cf6a3e&border_color=cf6a3e&hide_border=false&count_private=true" width="48%" style="border-radius:12px;border:1px solid rgba(207,106,62,0.2);" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=kamalesh4044&layout=compact&bg_color=1b1512&title_color=cf6a3e&text_color=b0b0b0&border_color=cf6a3e&hide_border=false" width="48%" style="border-radius:12px;border:1px solid rgba(207,106,62,0.2);" />
</div>

<!-- Activity Graph -->
<div style="animation:fade-in 1s 0.4s both;margin-top:16px;">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=kamalesh4044&bg_color=1b1512&color=cf6a3e&line=e89a70&point=f4ede3&area=true&hide_border=true" width="100%" style="border-radius:12px;border:1px solid rgba(207,106,62,0.2);" />
</div>

<div class="divider"></div>

<!-- ====== CONTRIBUTION SNAKE ====== -->
<h2 class="section-title" style="font-size:22px;">Contribution Snake</h2>

<div style="animation:scale-in 0.8s 0.2s both;">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/kamalesh4044/kamalesh4044/output/github-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/kamalesh4044/kamalesh4044/output/github-snake.svg" />
    <img alt="github-snake" src="https://raw.githubusercontent.com/kamalesh4044/kamalesh4044/output/github-snake-dark.svg" width="100%" style="border-radius:12px;" />
  </picture>
</div>

<div class="divider"></div>

<!-- ====== FOOTER ====== -->
<div align="center" style="animation:fade-in 1s both;padding:20px 0;">

<p style="color:#666;font-size:13px;margin-bottom:12px;">
  <em>"Building things that feel alive — one commit at a time."</em>
</p>

<!-- Animated social links -->
<div style="margin:16px 0;">
  <a href="https://github.com/kamalesh4044">
    <img src="https://img.shields.io/badge/GitHub-1b1512?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/kamalesh-kumar-a-308a89332/">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:kamalesh404e@gmail.com">
    <img src="https://img.shields.io/badge/Email-CF6A3E?style=for-the-badge&logo=gmail&logoColor=white&labelColor=1b1512" />
  </a>
  <a href="https://kamalesh4044.github.io/PORTFOLIO/">
    <img src="https://img.shields.io/badge/Portfolio-CF6A3E?style=for-the-badge&logo=vercel&logoColor=white&labelColor=1b1512" />
  </a>
</div>

<!-- Animated footer bar -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1b1512,30:cf6a3e,70:e89a70,100:1b1512&height=80&section=footer&text=KAMAlesh_KUMAR_A&fontSize=18&fontColor=f4ede3&fontAlignY=50&animation=fadeIn" width="100%" />

</div>
