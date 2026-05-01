<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=DM+Sans:wght@300;400;500&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --ocean: #1D9E75;
    --ocean-light: #E1F5EE;
    --ocean-deep: #085041;
    --forest: #639922;
    --forest-light: #EAF3DE;
    --forest-deep: #27500A;
    --sand: #FAC775;
    --text-dark: #2C2C2A;
    --text-mid: #5F5E5A;
    --text-light: #888780;
  }

  body {
    font-family: 'DM Sans', sans-serif;
    color: var(--text-dark);
    background: #fff;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: sticky; top: 0; z-index: 100;
    background: rgba(255,255,255,0.95);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid #E1F5EE;
    display: flex; align-items: center; justify-content: space-between;
    padding: 0.75rem 2rem;
  }
  .nav-logo { font-family: 'Playfair Display', serif; font-size: 1.2rem; color: var(--ocean-deep); }
  .nav-logo span { color: var(--forest); }
  .nav-links { display: flex; gap: 1.5rem; list-style: none; }
  .nav-links a { text-decoration: none; font-size: 0.85rem; font-weight: 400; color: var(--text-mid); transition: color 0.2s; cursor: pointer; }
  .nav-links a:hover { color: var(--ocean); }

  /* HERO */
  .hero {
    min-height: 100vh;
    background: linear-gradient(160deg, #04342C 0%, #0F6E56 40%, #1D9E75 75%, #9FE1CB 100%);
    display: flex; flex-direction: column; justify-content: center;
    padding: 6rem 3rem 4rem;
    position: relative; overflow: hidden;
  }
  .hero-bg-circle {
    position: absolute; border-radius: 50%;
    border: 1px solid rgba(255,255,255,0.1);
    pointer-events: none;
  }
  .hero-eyebrow {
    font-size: 0.75rem; letter-spacing: 0.2em; text-transform: uppercase;
    color: #9FE1CB; margin-bottom: 1.5rem; font-weight: 400;
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2.8rem, 6vw, 5rem);
    color: #fff; line-height: 1.1; max-width: 720px;
    margin-bottom: 1.5rem;
  }
  .hero h1 em { font-style: italic; color: var(--sand); }
  .hero-sub {
    font-size: 1.1rem; color: rgba(255,255,255,0.75); max-width: 520px;
    line-height: 1.7; margin-bottom: 3rem;
  }
  .hero-cta {
    display: inline-flex; gap: 1rem; flex-wrap: wrap;
  }
  .btn-primary {
    background: #fff; color: var(--ocean-deep);
    padding: 0.8rem 1.8rem; border-radius: 50px;
    font-family: 'DM Sans', sans-serif; font-weight: 500; font-size: 0.9rem;
    cursor: pointer; border: none; transition: transform 0.2s, box-shadow 0.2s;
  }
  .btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 20px rgba(0,0,0,0.15); }
  .btn-outline {
    background: transparent; color: #fff;
    padding: 0.8rem 1.8rem; border-radius: 50px;
    font-family: 'DM Sans', sans-serif; font-weight: 400; font-size: 0.9rem;
    cursor: pointer; border: 1.5px solid rgba(255,255,255,0.5); transition: border-color 0.2s;
  }
  .btn-outline:hover { border-color: #fff; }
  .hero-scroll { margin-top: 5rem; color: rgba(255,255,255,0.4); font-size: 0.8rem; letter-spacing: 0.1em; text-transform: uppercase; }

  /* SECTION LAYOUTS */
  section { padding: 5rem 3rem; }
  .section-label {
    font-size: 0.72rem; letter-spacing: 0.18em; text-transform: uppercase;
    color: var(--ocean); font-weight: 500; margin-bottom: 0.75rem;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 3vw, 2.6rem); line-height: 1.2; margin-bottom: 1.2rem;
  }
  .section-intro { font-size: 1rem; color: var(--text-mid); max-width: 600px; line-height: 1.75; }

  /* WHAT IS — SPLIT */
  .what-is { background: #fff; }
  .split-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3rem; align-items: start; margin-top: 3.5rem; }
  .curriculum-card {
    border-radius: 20px; overflow: hidden; position: relative;
  }
  .card-header { padding: 2rem 2rem 1.5rem; position: relative; }
  .card-header.blue { background: linear-gradient(135deg, #085041, #1D9E75); }
  .card-header.green { background: linear-gradient(135deg, #27500A, #639922); }
  .card-tag {
    display: inline-block; font-size: 0.7rem; letter-spacing: 0.15em; text-transform: uppercase;
    padding: 0.3rem 0.8rem; border-radius: 50px;
    margin-bottom: 1rem;
  }
  .card-tag.blue { background: rgba(255,255,255,0.2); color: #9FE1CB; }
  .card-tag.green { background: rgba(255,255,255,0.2); color: #C0DD97; }
  .card-header h3 { font-family: 'Playfair Display', serif; font-size: 1.8rem; color: #fff; line-height: 1.2; }
  .card-header p { font-size: 0.9rem; color: rgba(255,255,255,0.75); margin-top: 0.5rem; line-height: 1.6; }
  .card-icon { font-size: 2.5rem; margin-bottom: 0.75rem; }
  .card-body { padding: 1.75rem 2rem; border: 1px solid #E1F5EE; border-top: none; border-radius: 0 0 20px 20px; background: #fff; }
  .card-body h4 { font-size: 0.8rem; letter-spacing: 0.12em; text-transform: uppercase; color: var(--text-light); margin-bottom: 1rem; }
  .key-concept { display: flex; gap: 0.75rem; margin-bottom: 0.85rem; align-items: flex-start; }
  .concept-dot { width: 8px; height: 8px; border-radius: 50%; flex-shrink: 0; margin-top: 5px; }
  .concept-dot.blue { background: var(--ocean); }
  .concept-dot.green { background: var(--forest); }
  .key-concept p { font-size: 0.9rem; line-height: 1.55; color: var(--text-dark); }
  .key-concept strong { font-weight: 500; }

  /* HISTORY TIMELINE */
  .history { background: var(--forest-light); }
  .timeline { margin-top: 3rem; position: relative; }
  .timeline::before { content: ''; position: absolute; left: 110px; top: 0; bottom: 0; width: 1px; background: #C0DD97; }
  .timeline-item { display: flex; gap: 2rem; margin-bottom: 2.5rem; align-items: flex-start; }
  .timeline-year { width: 80px; font-family: 'Playfair Display', serif; font-size: 1.4rem; color: var(--forest-deep); flex-shrink: 0; text-align: right; padding-top: 2px; }
  .timeline-dot { width: 14px; height: 14px; border-radius: 50%; border: 2px solid var(--forest); background: #fff; flex-shrink: 0; margin-top: 5px; }
  .timeline-dot.ocean { border-color: var(--ocean); }
  .timeline-content { flex: 1; }
  .timeline-content h4 { font-weight: 500; font-size: 0.95rem; margin-bottom: 0.3rem; }
  .timeline-content p { font-size: 0.875rem; color: var(--text-mid); line-height: 1.6; }
  .timeline-badge { display: inline-block; font-size: 0.65rem; padding: 0.2rem 0.6rem; border-radius: 50px; text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 0.4rem; }
  .timeline-badge.b { background: var(--ocean-light); color: var(--ocean-deep); }
  .timeline-badge.g { background: var(--forest-light); color: var(--forest-deep); border: 1px solid #C0DD97; }

  /* REAL CASES */
  .real-cases { background: #fff; }
  .cases-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 3rem; }
  .case-card { border-radius: 16px; overflow: hidden; border: 1px solid #E1F5EE; }
  .case-img { height: 120px; display: flex; align-items: center; justify-content: center; font-size: 3rem; }
  .case-img.c1 { background: linear-gradient(135deg, #E1F5EE, #9FE1CB); }
  .case-img.c2 { background: linear-gradient(135deg, #EAF3DE, #C0DD97); }
  .case-img.c3 { background: linear-gradient(135deg, #FAEEDA, #FAC775); }
  .case-img.c4 { background: linear-gradient(135deg, #E6F1FB, #B5D4F4); }
  .case-img.c5 { background: linear-gradient(135deg, #E1F5EE, #5DCAA5); }
  .case-img.c6 { background: linear-gradient(135deg, #EAF3DE, #97C459); }
  .case-body { padding: 1.25rem; }
  .case-origin { font-size: 0.7rem; text-transform: uppercase; letter-spacing: 0.12em; color: var(--text-light); margin-bottom: 0.5rem; }
  .case-body h4 { font-weight: 500; font-size: 0.92rem; margin-bottom: 0.4rem; line-height: 1.4; }
  .case-body p { font-size: 0.82rem; color: var(--text-mid); line-height: 1.55; }

  /* DATA STATS */
  .stats-band { background: var(--ocean-deep); padding: 3rem; }
  .stats-inner { display: grid; grid-template-columns: repeat(4, 1fr); gap: 2rem; text-align: center; }
  .stat-num { font-family: 'Playfair Display', serif; font-size: 2.8rem; color: #9FE1CB; line-height: 1; margin-bottom: 0.4rem; }
  .stat-label { font-size: 0.82rem; color: rgba(255,255,255,0.65); line-height: 1.4; }

  /* INDONESIA ANALYSIS */
  .indonesia { background: #FAFAF8; }
  .analysis-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 2.5rem; margin-top: 3rem; }
  .analysis-block { background: #fff; border-radius: 16px; padding: 1.75rem; border: 1px solid #E5E4E0; }
  .analysis-block h4 { font-family: 'Playfair Display', serif; font-size: 1.15rem; margin-bottom: 1rem; }
  .analysis-block p { font-size: 0.88rem; color: var(--text-mid); line-height: 1.7; margin-bottom: 0.75rem; }
  .pill { display: inline-flex; align-items: center; gap: 0.4rem; padding: 0.3rem 0.75rem; border-radius: 50px; font-size: 0.75rem; margin: 0.2rem; }
  .pill.green { background: var(--forest-light); color: var(--forest-deep); }
  .pill.blue { background: var(--ocean-light); color: var(--ocean-deep); }
  .pills-row { margin-top: 0.75rem; display: flex; flex-wrap: wrap; gap: 0.3rem; }
  .align-chart { margin-top: 1.25rem; }
  .align-row { display: flex; align-items: center; gap: 0.75rem; margin-bottom: 0.6rem; }
  .align-label { font-size: 0.8rem; width: 130px; flex-shrink: 0; color: var(--text-mid); }
  .align-bar-wrap { flex: 1; background: #F1EFE8; border-radius: 50px; height: 8px; }
  .align-bar { height: 8px; border-radius: 50px; }
  .align-pct { font-size: 0.75rem; width: 35px; text-align: right; color: var(--text-mid); }

  /* IMPLEMENTATION */
  .implementation { background: #fff; }
  .impl-tabs { display: flex; gap: 0.5rem; margin: 2rem 0 2.5rem; border-bottom: 1px solid #E5E4E0; padding-bottom: 0; }
  .impl-tab { padding: 0.6rem 1.2rem; border-radius: 8px 8px 0 0; font-size: 0.88rem; cursor: pointer; border: none; background: transparent; color: var(--text-mid); font-family: 'DM Sans', sans-serif; transition: all 0.2s; border-bottom: 2px solid transparent; }
  .impl-tab.active { color: var(--ocean-deep); border-bottom-color: var(--ocean); font-weight: 500; }
  .impl-tab:hover:not(.active) { color: var(--text-dark); background: var(--forest-light); }
  .impl-panel { display: none; }
  .impl-panel.active { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; }
  .lesson-step { display: flex; gap: 1rem; margin-bottom: 1.25rem; align-items: flex-start; }
  .step-num { width: 28px; height: 28px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 0.78rem; font-weight: 500; flex-shrink: 0; }
  .step-num.o { background: var(--ocean-light); color: var(--ocean-deep); }
  .step-num.g { background: var(--forest-light); color: var(--forest-deep); }
  .step-text h5 { font-weight: 500; font-size: 0.9rem; margin-bottom: 0.2rem; }
  .step-text p { font-size: 0.83rem; color: var(--text-mid); line-height: 1.55; }
  .impl-info { background: var(--forest-light); border-radius: 16px; padding: 1.75rem; }
  .impl-info h4 { font-family: 'Playfair Display', serif; font-size: 1.1rem; margin-bottom: 1rem; color: var(--forest-deep); }
  .impl-info p { font-size: 0.87rem; line-height: 1.65; color: var(--text-mid); margin-bottom: 0.75rem; }
  .action-item { display: flex; gap: 0.6rem; margin-bottom: 0.6rem; align-items: flex-start; }
  .action-icon { font-size: 1rem; flex-shrink: 0; }
  .action-text { font-size: 0.85rem; line-height: 1.5; }

  /* LESSON PLAN SHOWCASE */
  .lesson-plan { background: linear-gradient(160deg, #04342C, #0F6E56); padding: 5rem 3rem; }
  .lesson-plan .section-label { color: #9FE1CB; }
  .lesson-plan .section-title { color: #fff; }
  .lp-grid { display: grid; grid-template-columns: 1fr 2fr; gap: 3rem; margin-top: 3rem; align-items: start; }
  .lp-meta { background: rgba(255,255,255,0.08); border-radius: 16px; padding: 1.75rem; }
  .lp-meta h4 { color: #9FE1CB; font-size: 0.75rem; text-transform: uppercase; letter-spacing: 0.12em; margin-bottom: 1rem; }
  .lp-row { display: flex; justify-content: space-between; padding: 0.6rem 0; border-bottom: 1px solid rgba(255,255,255,0.08); font-size: 0.85rem; }
  .lp-row:last-child { border-bottom: none; }
  .lp-row span:first-child { color: rgba(255,255,255,0.55); }
  .lp-row span:last-child { color: #fff; font-weight: 400; }
  .lp-phases { }
  .phase-card { background: rgba(255,255,255,0.08); border-radius: 12px; padding: 1.25rem 1.5rem; margin-bottom: 0.75rem; display: flex; gap: 1.25rem; align-items: flex-start; }
  .phase-time { font-size: 0.75rem; color: #9FE1CB; white-space: nowrap; padding-top: 2px; }
  .phase-content h5 { color: #fff; font-weight: 500; font-size: 0.92rem; margin-bottom: 0.25rem; }
  .phase-content p { color: rgba(255,255,255,0.6); font-size: 0.83rem; line-height: 1.5; }

  /* CALL TO ACTION */
  .cta-section { background: var(--forest-light); text-align: center; padding: 5rem 3rem; }
  .cta-section .section-title { max-width: 550px; margin: 0 auto 1.5rem; }
  .cta-section p { max-width: 480px; margin: 0 auto 2.5rem; font-size: 0.95rem; color: var(--text-mid); line-height: 1.7; }
  .cta-actions { display: flex; gap: 1rem; justify-content: center; flex-wrap: wrap; }
  .btn-cta-primary { background: var(--ocean-deep); color: #fff; padding: 0.85rem 2rem; border-radius: 50px; font-size: 0.9rem; cursor: pointer; border: none; font-family: 'DM Sans', sans-serif; font-weight: 500; transition: transform 0.2s; }
  .btn-cta-primary:hover { transform: translateY(-2px); }
  .btn-cta-sec { background: transparent; color: var(--ocean-deep); padding: 0.85rem 2rem; border-radius: 50px; font-size: 0.9rem; cursor: pointer; border: 1.5px solid var(--ocean); font-family: 'DM Sans', sans-serif; transition: background 0.2s; }
  .btn-cta-sec:hover { background: var(--ocean-light); }

  /* FOOTER */
  footer { background: var(--text-dark); padding: 2.5rem 3rem; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1rem; }
  footer p { font-size: 0.8rem; color: rgba(255,255,255,0.4); }
  footer .foot-logo { font-family: 'Playfair Display', serif; color: rgba(255,255,255,0.7); font-size: 1rem; }
  footer .foot-logo span { color: #9FE1CB; }

  /* WHY IMPORTANT */
  .why { background: var(--ocean-light); }
  .why-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin-top: 3rem; }
  .why-card { background: #fff; border-radius: 16px; padding: 1.75rem; }
  .why-num { font-family: 'Playfair Display', serif; font-size: 3rem; color: #E1F5EE; line-height: 1; margin-bottom: 0.5rem; }
  .why-card h4 { font-weight: 500; font-size: 0.95rem; margin-bottom: 0.5rem; }
  .why-card p { font-size: 0.85rem; color: var(--text-mid); line-height: 1.65; }

  @media (max-width: 700px) {
    .split-grid, .cases-grid, .analysis-grid, .impl-panel.active, .lp-grid, .why-grid, .stats-inner { grid-template-columns: 1fr; }
    .hero h1 { font-size: 2.2rem; }
    section { padding: 3rem 1.5rem; }
    .timeline::before { left: 80px; }
  }
</style>

<nav>
  <div class="nav-logo">Blue <span>&</span> Green Curriculum</div>
  <ul class="nav-links">
    <li><a onclick="scrollTo('#what')">What is it</a></li>
    <li><a onclick="scrollTo('#cases')">Real Cases</a></li>
    <li><a onclick="scrollTo('#indonesia')">Indonesia</a></li>
    <li><a onclick="scrollTo('#impl')">Implementation</a></li>
    <li><a onclick="scrollTo('#action')">Take Action</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="top">
  <div class="hero-bg-circle" style="width:600px;height:600px;top:-200px;right:-150px;"></div>
  <div class="hero-bg-circle" style="width:300px;height:300px;bottom:100px;right:100px;"></div>
  <p class="hero-eyebrow">A Campaign for Sustainable Education</p>
  <h1>Education that <em>Breathes</em> with the Planet</h1>
  <p class="hero-sub">Blue and Green Curriculum reimagines education by placing ocean literacy and ecological sustainability at its heart — preparing learners to become guardians of the Earth.</p>
  <div class="hero-cta">
    <button class="btn-primary" onclick="document.getElementById('what').scrollIntoView({behavior:'smooth'})">Explore the Curricula</button>
    <button class="btn-outline" onclick="document.getElementById('impl').scrollIntoView({behavior:'smooth'})">See Implementation</button>
  </div>
  <p class="hero-scroll">↓ Scroll to explore</p>
</section>

<!-- WHAT IS -->
<section class="what-is" id="what">
  <p class="section-label">Understanding the Curricula</p>
  <h2 class="section-title">What Are Blue & Green Curricula?</h2>
  <p class="section-intro">Two interconnected educational frameworks designed to embed environmental literacy into the very DNA of schooling — from ocean ecosystems to forest conservation.</p>

  <div class="split-grid">
    <!-- BLUE -->
    <div class="curriculum-card">
      <div class="card-header blue">
        <div class="card-icon">🌊</div>
        <span class="card-tag blue">Blue Curriculum</span>
        <h3>Ocean-Centered Learning</h3>
        <p>An educational approach that integrates ocean literacy, marine ecology, and blue economy principles into teaching and learning across all subjects.</p>
      </div>
      <div class="card-body">
        <h4>Core Concepts</h4>
        <div class="key-concept">
          <div class="concept-dot blue"></div>
          <p><strong>Ocean Literacy:</strong> Understanding the ocean's influence on climate, weather, and all living organisms on Earth.</p>
        </div>
        <div class="key-concept">
          <div class="concept-dot blue"></div>
          <p><strong>Marine Biodiversity:</strong> Appreciating and protecting the richness of life beneath the sea, from coral reefs to deep-sea ecosystems.</p>
        </div>
        <div class="key-concept">
          <div class="concept-dot blue"></div>
          <p><strong>Blue Economy:</strong> Sustainable use of ocean resources for economic growth while preserving ocean health.</p>
        </div>
        <div class="key-concept">
          <div class="concept-dot blue"></div>
          <p><strong>Climate Connection:</strong> Recognizing how oceans regulate global temperature and absorb CO₂.</p>
        </div>
      </div>
    </div>
    <!-- GREEN -->
    <div class="curriculum-card">
      <div class="card-header green">
        <div class="card-icon">🌿</div>
        <span class="card-tag green">Green / Greening Curriculum</span>
        <h3>Ecology-Rooted Education</h3>
        <p>A curriculum framework that weaves environmental sustainability, ecological thinking, and Education for Sustainable Development (ESD) throughout all learning areas.</p>
      </div>
      <div class="card-body">
        <h4>Core Concepts</h4>
        <div class="key-concept">
          <div class="concept-dot green"></div>
          <p><strong>ESD Integration:</strong> Education for Sustainable Development embedded across science, social studies, arts, and beyond.</p>
        </div>
        <div class="key-concept">
          <div class="concept-dot green"></div>
          <p><strong>Ecological Thinking:</strong> Developing systems-level understanding of how natural and human systems are interconnected.</p>
        </div>
        <div class="key-concept">
          <div class="concept-dot green"></div>
          <p><strong>Action Competence:</strong> Building students' capacity to act meaningfully on environmental and social challenges.</p>
        </div>
        <div class="key-concept">
          <div class="concept-dot green"></div>
          <p><strong>Sustainable Schools:</strong> Transforming school environments, practices, and culture toward sustainability.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- WHY IMPORTANT -->
<section class="why">
  <p class="section-label">Why It Matters</p>
  <h2 class="section-title">Why These Curricula Are Vital Today</h2>
  <div class="why-grid">
    <div class="why-card">
      <div class="why-num">01</div>
      <h4>Addressing a Planetary Emergency</h4>
      <p>Climate change, biodiversity loss, and ocean degradation are accelerating. Education is the most powerful long-term intervention we have to change the trajectory.</p>
    </div>
    <div class="why-card">
      <div class="why-num">02</div>
      <h4>Building Future-Ready Citizens</h4>
      <p>Students who understand ecological systems are better equipped for careers in a green economy and more capable of making informed democratic decisions about sustainability.</p>
    </div>
    <div class="why-card">
      <div class="why-num">03</div>
      <h4>Making Learning Meaningful</h4>
      <p>Connecting curriculum to real-world environmental challenges gives students a sense of purpose, relevance, and intrinsic motivation that traditional schooling often lacks.</p>
    </div>
  </div>
</section>

<!-- HISTORY -->
<section class="history">
  <p class="section-label">Historical Development</p>
  <h2 class="section-title">How These Frameworks Evolved</h2>
  <div class="timeline">
    <div class="timeline-item">
      <div class="timeline-year">1972</div>
      <div class="timeline-dot g"></div>
      <div class="timeline-content">
        <span class="timeline-badge g">Green</span>
        <h4>Stockholm Conference — Birth of Environmental Education</h4>
        <p>The UN Conference on the Human Environment marked the first major global recognition that education must address environmental issues, laying seeds for green curriculum.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-year">1987</div>
      <div class="timeline-dot g"></div>
      <div class="timeline-content">
        <span class="timeline-badge g">Green</span>
        <h4>Brundtland Report — Sustainable Development Defined</h4>
        <p>"Our Common Future" formally defined sustainable development and pushed for its integration into education systems worldwide.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-year">1998</div>
      <div class="timeline-dot b"></div>
      <div class="timeline-content">
        <span class="timeline-badge b">Blue</span>
        <h4>Ocean Literacy Framework Emerges</h4>
        <p>Scientists and educators began formalizing "ocean literacy" as a distinct educational goal, establishing the seven principles that define ocean-aware citizens.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-year">2005</div>
      <div class="timeline-dot g"></div>
      <div class="timeline-content">
        <span class="timeline-badge g">Green</span>
        <h4>UNESCO Decade for ESD Launched</h4>
        <p>The UN declared 2005–2014 the Decade of Education for Sustainable Development, accelerating the integration of ESD into national curricula globally.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-year">2015</div>
      <div class="timeline-dot b"></div>
      <div class="timeline-content">
        <span class="timeline-badge b">Blue</span>
        <h4>SDG 14 — Life Below Water</h4>
        <p>The UN Sustainable Development Goals explicitly included ocean conservation (SDG 14), pushing education systems to adopt Blue Curriculum elements.</p>
      </div>
    </div>
    <div class="timeline-item">
      <div class="timeline-year">2019</div>
      <div class="timeline-dot b"></div>
      <div class="timeline-content">
        <span class="timeline-badge b">Blue</span>
        <h4>UN Ocean Decade Preparation</h4>
        <p>Preparations began for the UN Decade of Ocean Science (2021–2030), embedding ocean education as a priority in science curricula worldwide, including Indonesia.</p>
      </div>
    </div>
  </div>
</section>

<!-- STATS BAND -->
<div class="stats-band" id="cases">
  <div class="stats-inner">
    <div>
      <div class="stat-num">70%</div>
      <div class="stat-label">of Earth's surface is covered by ocean</div>
    </div>
    <div>
      <div class="stat-num">281K</div>
      <div class="stat-label">hectares of Indonesian forest lost in 2024 alone</div>
    </div>
    <div>
      <div class="stat-num">1M+</div>
      <div class="stat-label">marine species at risk from plastic pollution</div>
    </div>
    <div>
      <div class="stat-num">17</div>
      <div class="stat-label">UN SDGs connected to Blue & Green education</div>
    </div>
  </div>
</div>

<!-- REAL CASES -->
<section class="real-cases">
  <p class="section-label">Real Cases & Issues</p>
  <h2 class="section-title">What's Happening in the World & Indonesia</h2>
  <p class="section-intro">These curricula are not abstract ideals — they respond to urgent, documented crises unfolding across the globe and right here at home.</p>

  <div class="cases-grid">
    <div class="case-card">
      <div class="case-img c1">🪸</div>
      <div class="case-body">
        <div class="case-origin">🌏 Global</div>
        <h4>Coral Reef Bleaching Crisis</h4>
        <p>Over 50% of the world's coral reefs have been lost since 1950 due to ocean warming and acidification. The Great Barrier Reef recorded its worst bleaching event in 2024. Blue Curriculum directly teaches ocean health and coral ecology.</p>
      </div>
    </div>
    <div class="case-card">
      <div class="case-img c2">🌳</div>
      <div class="case-body">
        <div class="case-origin">🇮🇩 Indonesia</div>
        <h4>Deforestation in Kalimantan & Papua</h4>
        <p>Indonesia lost 281,575 hectares of forest in 2024 (Jatam, 2024), driven by palm oil expansion, mining, and food estate projects. Green Curriculum builds awareness of deforestation's cascading effects on biodiversity and communities.</p>
      </div>
    </div>
    <div class="case-card">
      <div class="case-img c3">🌊</div>
      <div class="case-body">
        <div class="case-origin">🇮🇩 Indonesia</div>
        <h4>Marine Plastic Pollution</h4>
        <p>Indonesia is the world's second-largest contributor to ocean plastic pollution. Rivers carry waste into seas affecting local fishermen, marine biodiversity, and coastal tourism — a critical issue for ocean literacy education.</p>
      </div>
    </div>
    <div class="case-card">
      <div class="case-img c4">🌍</div>
      <div class="case-body">
        <div class="case-origin">🌏 Global</div>
        <h4>ESD in Singapore & Finland</h4>
        <p>Singapore integrates environmental stewardship into national curriculum through the "Eco-Stewardship Programme." Finland's curriculum mandates cross-subject sustainability competencies — models for Green Curriculum implementation.</p>
      </div>
    </div>
    <div class="case-card">
      <div class="case-img c5">🐠</div>
      <div class="case-body">
        <div class="case-origin">🇮🇩 Indonesia</div>
        <h4>Overfishing in Indonesian Waters</h4>
        <p>Indonesian coastal communities face declining fish stocks due to illegal, unreported fishing practices. Blue Curriculum can build local ocean stewardship from school age, reconnecting fishing communities to sustainable practices.</p>
      </div>
    </div>
    <div class="case-card">
      <div class="case-img c6">🌱</div>
      <div class="case-body">
        <div class="case-origin">🌏 Global</div>
        <h4>UNESCO Green Schools Movement</h4>
        <p>UNESCO's "Greening Education Partnership" (2022) calls for countries to embed sustainability in all curricula by 2030. 145 countries have pledged to transform their education systems — Indonesia is among them.</p>
      </div>
    </div>
  </div>
</section>

<!-- INDONESIA ANALYSIS -->
<section class="indonesia" id="indonesia">
  <p class="section-label">Indonesian Curriculum Analysis</p>
  <h2 class="section-title">How Indonesia's Curriculum Connects</h2>
  <p class="section-intro">Indonesia's Kurikulum Merdeka (2022) and its science content show promising alignment — and significant opportunities — for Blue and Green Curriculum integration.</p>

  <div class="analysis-grid">
    <div class="analysis-block">
      <h4>Policy-Level Alignment</h4>
      <p>Kurikulum Merdeka (Free Learning Curriculum) introduced the Profil Pelajar Pancasila — six student character values including <em>berkebinekaan global</em> (global diversity) and <em>beriman & bertakwa</em> (faith & responsibility), which implicitly support environmental stewardship.</p>
      <p>The curriculum framework mandates Projek Penguatan Profil Pelajar Pancasila (P5) — project-based learning that schools can theme around environmental sustainability, directly aligning with Green Curriculum principles.</p>
      <div class="pills-row">
        <span class="pill green">P5 Projects</span>
        <span class="pill green">Profil Pelajar Pancasila</span>
        <span class="pill blue">Merdeka Belajar</span>
        <span class="pill green">ESD Policy</span>
      </div>
    </div>
    <div class="analysis-block">
      <h4>Science Content Alignment</h4>
      <p>Indonesia's Grade 7–9 IPA (Science) curriculum includes topics on ecosystems, biodiversity, climate, and the water cycle — all directly relevant to Blue and Green Curriculum. However, marine-specific content remains limited.</p>
      <p>The alignment is moderate: ecology and environmental impact are covered, but ocean literacy, blue economy, and ESD competency development are not systematically embedded.</p>
      <div class="align-chart">
        <div class="align-row">
          <span class="align-label">Ecology & Biodiversity</span>
          <div class="align-bar-wrap"><div class="align-bar" style="width:80%;background:var(--forest);"></div></div>
          <span class="align-pct">80%</span>
        </div>
        <div class="align-row">
          <span class="align-label">Climate & Environment</span>
          <div class="align-bar-wrap"><div class="align-bar" style="width:65%;background:var(--forest);"></div></div>
          <span class="align-pct">65%</span>
        </div>
        <div class="align-row">
          <span class="align-label">Ocean Literacy</span>
          <div class="align-bar-wrap"><div class="align-bar" style="width:30%;background:var(--ocean);"></div></div>
          <span class="align-pct">30%</span>
        </div>
        <div class="align-row">
          <span class="align-label">ESD Competencies</span>
          <div class="align-bar-wrap"><div class="align-bar" style="width:45%;background:var(--ocean);"></div></div>
          <span class="align-pct">45%</span>
        </div>
        <div class="align-row">
          <span class="align-label">Blue Economy</span>
          <div class="align-bar-wrap"><div class="align-bar" style="width:20%;background:var(--ocean);"></div></div>
          <span class="align-pct">20%</span>
        </div>
      </div>
    </div>
    <div class="analysis-block" style="grid-column: 1 / -1;">
      <h4>Gaps & Opportunities in Indonesian Education</h4>
      <p>While Kurikulum Merdeka creates space for sustainability through P5 projects and flexible learning, the <strong>explicit integration</strong> of Blue and Green Curriculum principles remains teacher-dependent and inconsistent. Key gaps include: (1) No national ocean literacy standards, (2) ESD competencies are implicit rather than assessed, (3) Local ecological contexts are underutilized as teaching resources. These gaps represent opportunities for curriculum reform — particularly in a nation of 17,000+ islands with the world's second-longest coastline.</p>
    </div>
  </div>
</section>

<!-- LESSON PLAN SHOWCASE -->
<section class="lesson-plan">
  <p class="section-label">Implementation Example</p>
  <h2 class="section-title" style="color:#fff;">A Green Curriculum Lesson in Action</h2>
  <p class="section-intro" style="color:rgba(255,255,255,0.7);">This ESD-oriented lesson plan demonstrates how Green Curriculum principles come alive in a Grade 8 Biology class on Deforestation.</p>

  <div class="lp-grid">
    <div>
      <div class="lp-meta">
        <h4>Lesson Overview</h4>
        <div class="lp-row"><span>Subject</span><span>Biology (IPA)</span></div>
        <div class="lp-row"><span>Grade</span><span>VIII / Grade 8</span></div>
        <div class="lp-row"><span>Topic</span><span>Deforestation</span></div>
        <div class="lp-row"><span>Duration</span><span>150 minutes</span></div>
        <div class="lp-row"><span>Model</span><span>ESD Problem-based Learning</span></div>
        <div class="lp-row"><span>SDG Alignment</span><span>SDG 13 — Climate Action</span></div>
      </div>
      <div class="lp-meta" style="margin-top:1rem;">
        <h4>ESD Competencies Developed</h4>
        <div class="lp-row"><span>Critical Thinking</span><span>✓</span></div>
        <div class="lp-row"><span>Collaboration</span><span>✓</span></div>
        <div class="lp-row"><span>Self-awareness</span><span>✓</span></div>
        <div class="lp-row"><span>Problem-solving</span><span>✓</span></div>
      </div>
    </div>
    <div class="lp-phases">
      <div class="phase-card">
        <div class="phase-time">5 min</div>
        <div class="phase-content"><h5>Introduction</h5><p>Teacher opens with motivation, states learning objectives, and divides students into collaborative groups of 4–5.</p></div>
      </div>
      <div class="phase-card">
        <div class="phase-time">5 min</div>
        <div class="phase-content"><h5>Problem Identification</h5><p>Real deforestation data (281,575 ha, 2024) and local news presented. Open-ended triggering questions posed to students.</p></div>
      </div>
      <div class="phase-card">
        <div class="phase-time">5 min</div>
        <div class="phase-content"><h5>Problem Formulation</h5><p>Students brainstorm causes: palm oil expansion, mining, food estate projects, illegal logging. Worksheets distributed.</p></div>
      </div>
      <div class="phase-card">
        <div class="phase-time">15 min</div>
        <div class="phase-content"><h5>Planning the Investigation</h5><p>Students design their research method: neighborhood observations, community interviews, news collection, photo documentation.</p></div>
      </div>
      <div class="phase-card">
        <div class="phase-time">45 min</div>
        <div class="phase-content"><h5>Conducting the Investigation</h5><p>Field work: students gather evidence through observations, interviews with residents, teachers, or village officials.</p></div>
      </div>
      <div class="phase-card">
        <div class="phase-time">15 min</div>
        <div class="phase-content"><h5>Analysis & Conclusions</h5><p>Students analyze cause-effect relationships, compare findings with data, draw evidence-based conclusions.</p></div>
      </div>
      <div class="phase-card">
        <div class="phase-time">60 min</div>
        <div class="phase-content"><h5>Implementation & Action</h5><p>Students design real solutions: tree-planting campaigns, educational posters, community advocacy plans.</p></div>
      </div>
      <div class="phase-card">
        <div class="phase-time">5 min</div>
        <div class="phase-content"><h5>Reflection & Closing</h5><p>Students share learning, reflect on perspective changes, and present findings to the class.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- IMPLEMENTATION TABS -->
<section class="implementation" id="impl">
  <p class="section-label">Implementation in Educational Context</p>
  <h2 class="section-title">How to Bring It Into the Classroom</h2>
  <div class="impl-tabs">
    <button class="impl-tab active" onclick="switchTab('teachers')">For Teachers</button>
    <button class="impl-tab" onclick="switchTab('students')">For Students</button>
    <button class="impl-tab" onclick="switchTab('citizens')">For Citizens</button>
  </div>
  <div class="impl-panel active" id="tab-teachers">
    <div>
      <div class="lesson-step">
        <div class="step-num o">1</div>
        <div class="step-text"><h5>Use Real Local Data</h5><p>Anchor lessons in real environmental data from your region — deforestation rates, local river quality, coastal erosion. Students connect more deeply when issues are nearby.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num o">2</div>
        <div class="step-text"><h5>Apply Problem-Based Learning (PBL)</h5><p>Structure lessons around authentic environmental problems using ESD-oriented PBL. Guide students from problem identification through investigation to real action proposals.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num o">3</div>
        <div class="step-text"><h5>Integrate Across Subjects</h5><p>Collaborate with colleagues to weave Blue/Green themes across Biology, Geography, Bahasa Indonesia, and Arts. Sustainability is cross-disciplinary by nature.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num o">4</div>
        <div class="step-text"><h5>Design P5 Projects</h5><p>Leverage Kurikulum Merdeka's P5 project framework to create semester-long environmental sustainability projects that develop ESD competencies.</p></div>
      </div>
    </div>
    <div class="impl-info">
      <h4>Blue Curriculum Subject Integration</h4>
      <p>Teaching coastal erosion in Geography? Add ocean literacy. Teaching photosynthesis in Biology? Connect it to ocean CO₂ absorption. Teaching economic systems? Introduce the blue economy concept.</p>
      <p>Even simple additions — a deforestation map in a social studies lesson, a pH test of local water in chemistry — begin greening the curriculum without a complete redesign.</p>
      <div class="action-item"><span class="action-icon">📍</span><span class="action-text">Visit a local river, mangrove, or coastal area as a learning site</span></div>
      <div class="action-item"><span class="action-icon">📊</span><span class="action-text">Use KLHK and BPS data for real Indonesian environmental statistics</span></div>
      <div class="action-item"><span class="action-icon">🌱</span><span class="action-text">Start a school garden or composting program as a living lab</span></div>
    </div>
  </div>
  <div class="impl-panel" id="tab-students">
    <div>
      <div class="lesson-step">
        <div class="step-num g">1</div>
        <div class="step-text"><h5>Conduct Local Environmental Audits</h5><p>Walk your neighborhood and document environmental issues: illegal dumping, deforested areas, plastic in drains. Create a data-driven local report.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num g">2</div>
        <div class="step-text"><h5>Interview Community Members</h5><p>Talk to local fishermen, farmers, or elders about environmental changes they've witnessed over decades. Oral histories are powerful data.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num g">3</div>
        <div class="step-text"><h5>Design Real Solutions</h5><p>Don't just identify problems — create action plans. Organize a beach cleanup, plant trees at school, design educational posters for your community.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num g">4</div>
        <div class="step-text"><h5>Use Social Media for Advocacy</h5><p>Share findings through school social media. Awareness is the first step toward community action on environmental issues.</p></div>
      </div>
    </div>
    <div class="impl-info">
      <h4>Student Action Projects</h4>
      <p>Small actions compound into real change. The most powerful thing students can do is move from passive learning to active citizenship in their local environment.</p>
      <div class="action-item"><span class="action-icon">🌊</span><span class="action-text">Adopt a stretch of local river or beach for monthly cleanups</span></div>
      <div class="action-item"><span class="action-icon">🌳</span><span class="action-text">Launch a school tree-planting initiative — start with 10 seedlings</span></div>
      <div class="action-item"><span class="action-icon">📢</span><span class="action-text">Present environmental findings to local government or community leaders</span></div>
      <div class="action-item"><span class="action-icon">🎨</span><span class="action-text">Create murals or installations communicating sustainability messages</span></div>
    </div>
  </div>
  <div class="impl-panel" id="tab-citizens">
    <div>
      <div class="lesson-step">
        <div class="step-num g">1</div>
        <div class="step-text"><h5>Support Environmental Education</h5><p>Advocate for Blue and Green Curriculum in your local school's P5 project themes. Engage with school committees to prioritize sustainability projects.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num g">2</div>
        <div class="step-text"><h5>Reduce Household Ocean Impact</h5><p>Manage plastic waste, use eco-friendly cleaning products, and avoid single-use plastics — especially in coastal communities where waste enters oceans directly.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num g">3</div>
        <div class="step-text"><h5>Engage Local Government</h5><p>Attend musrenbang (community planning) sessions and advocate for green city policies: mangrove restoration, sustainable land use, and waste management.</p></div>
      </div>
      <div class="lesson-step">
        <div class="step-num g">4</div>
        <div class="step-text"><h5>Be a Lifelong Learner</h5><p>Follow organizations like WWF Indonesia, Yayasan Terumbu Karang Indonesia (TERANGI), and KLHK for updates on marine and forest conservation in your region.</p></div>
      </div>
    </div>
    <div class="impl-info">
      <h4>Community Roles in Green Education</h4>
      <p>Schools alone cannot create the next generation of environmental stewards. Communities, families, and local leaders all play a role in embedding ecological values into everyday life.</p>
      <div class="action-item"><span class="action-icon">🏘️</span><span class="action-text">Start a neighborhood composting or urban garden collective</span></div>
      <div class="action-item"><span class="action-icon">🐠</span><span class="action-text">Support local fisheries cooperatives practicing sustainable fishing</span></div>
      <div class="action-item"><span class="action-icon">📚</span><span class="action-text">Donate environmental books or resources to local school libraries</span></div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta-section" id="action">
  <p class="section-label">Take Action</p>
  <h2 class="section-title">The Future Is Green — and Blue</h2>
  <p>Education is not preparation for life — it is life itself. By embracing Blue and Green Curricula, we give every learner the knowledge, values, and agency to shape a sustainable world.</p>
  <div class="cta-actions">
    <button class="btn-cta-primary" onclick="sendPrompt('Tell me more about how to implement Blue Curriculum in Indonesian schools')">Learn More About Implementation ↗</button>
    <button class="btn-cta-sec" onclick="sendPrompt('What are some ESD lesson plan ideas for Indonesian science teachers?')">Get Lesson Plan Ideas ↗</button>
  </div>
</section>

<footer>
  <div class="foot-logo">Blue <span>&</span> Green Curriculum</div>
  <p>A midterm campaign project — International Science Curricula & Analysis 2026</p>
  <p>Sources: UNESCO, KLHK, Jatam, NOAA, SDG Reports</p>
</footer>

<script>
function scrollTo(id) {
  const el = document.querySelector(id);
  if (el) el.scrollIntoView({behavior: 'smooth'});
}

function switchTab(name) {
  document.querySelectorAll('.impl-tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.impl-panel').forEach(p => p.classList.remove('active'));
  event.target.classList.add('active');
  document.getElementById('tab-' + name).classList.add('active');
}
</script>
