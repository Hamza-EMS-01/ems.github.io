<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Camille Dupont – Resume</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --dark:    #1e2a35;
    --dark2:   #2c3e50;
    --mid:     #3d5166;
    --accent:  #7fb3c8;
    --accent2: #a8c8d8;
    --white:   #ffffff;
    --bg:      #f0f3f5;
    --text:    #2c3e50;
    --muted:   #607080;
    --left-w:  300px;
  }

  @page { size: A4; margin: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: #d0d8e0;
    display: flex;
    justify-content: center;
    align-items: flex-start;
    min-height: 100vh;
    padding: 40px 20px;
  }

  .page {
    width: 794px;
    min-height: 1123px;
    background: var(--bg);
    display: flex;
    box-shadow: 0 20px 60px rgba(0,0,0,0.3);
    position: relative;
    overflow: hidden;
  }

  /* ── LEFT SIDEBAR ── */
  .sidebar {
    width: var(--left-w);
    min-width: var(--left-w);
    background: var(--dark);
    color: var(--white);
    padding: 40px 26px 40px;
    display: flex;
    flex-direction: column;
    gap: 0;
    position: relative;
  }

  .sidebar::after {
    content: '';
    position: absolute;
    top: 0; right: -1px;
    width: 2px; height: 100%;
    background: linear-gradient(to bottom, var(--accent), transparent 60%);
  }

  /* name block */
  .name-block {
    text-align: center;
    padding-bottom: 28px;
    border-bottom: 1px solid rgba(127,179,200,0.25);
    margin-bottom: 28px;
  }

  .name-block .first {
    font-family: 'Playfair Display', serif;
    font-size: 30px;
    font-weight: 400;
    letter-spacing: 3px;
    color: var(--white);
    line-height: 1.1;
  }

  .name-block .last {
    font-family: 'Playfair Display', serif;
    font-size: 30px;
    font-weight: 700;
    letter-spacing: 3px;
    color: var(--accent);
    line-height: 1.1;
  }

  .name-block .title {
    font-size: 10.5px;
    font-weight: 300;
    letter-spacing: 2.5px;
    text-transform: uppercase;
    color: var(--accent2);
    margin-top: 10px;
  }

  /* left section */
  .l-section { margin-bottom: 24px; }

  .l-section-title {
    font-size: 9px;
    font-weight: 600;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    border-bottom: 1px solid rgba(127,179,200,0.3);
    padding-bottom: 6px;
    margin-bottom: 14px;
  }

  /* contact */
  .contact-item {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    margin-bottom: 9px;
    font-size: 11.5px;
    color: rgba(255,255,255,0.8);
    font-weight: 300;
  }

  .contact-item .icon {
    color: var(--accent);
    font-size: 12px;
    flex-shrink: 0;
    margin-top: 1px;
  }

  /* skills */
  .skill-group-label {
    font-size: 9px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--accent2);
    font-weight: 600;
    margin: 12px 0 8px;
  }

  .skill-item { margin-bottom: 9px; }

  .skill-label {
    font-size: 11px;
    color: rgba(255,255,255,0.85);
    font-weight: 400;
    margin-bottom: 4px;
  }

  .skill-dots {
    display: flex;
    gap: 5px;
  }

  .dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: rgba(127,179,200,0.2);
    border: 1px solid rgba(127,179,200,0.5);
    transition: background 0.2s;
  }

  .dot.filled {
    background: var(--accent);
    border-color: var(--accent);
  }

  /* edu */
  .edu-item { margin-bottom: 13px; }
  .edu-degree { font-size: 12px; font-weight: 500; color: var(--white); }
  .edu-school { font-size: 11px; color: var(--accent2); font-style: italic; margin-top: 2px; }
  .edu-note   { font-size: 10.5px; color: rgba(255,255,255,0.5); margin-top: 2px; }

  /* lang */
  .lang-item { margin-bottom: 10px; }
  .lang-name  { font-size: 12px; font-weight: 500; color: var(--white); }
  .lang-note  { font-size: 11px; color: var(--accent2); margin-top: 2px; }

  /* interests */
  .interest-list {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .interest-tag {
    font-size: 11px;
    color: rgba(255,255,255,0.75);
    background: rgba(127,179,200,0.12);
    border: 1px solid rgba(127,179,200,0.25);
    border-radius: 20px;
    padding: 3px 10px;
  }

  /* ── RIGHT MAIN ── */
  .main {
    flex: 1;
    padding: 40px 32px 40px 34px;
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  /* right section */
  .r-section { margin-bottom: 26px; }

  .r-section-title {
    font-size: 9px;
    font-weight: 600;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--dark2);
    border-bottom: 2px solid var(--dark2);
    padding-bottom: 6px;
    margin-bottom: 14px;
  }

  /* about */
  .about-text {
    font-size: 12.5px;
    color: var(--muted);
    line-height: 1.7;
    font-weight: 300;
  }

  /* experience */
  .exp-entry { margin-bottom: 18px; }

  .exp-title {
    font-size: 13.5px;
    font-weight: 600;
    color: var(--dark);
    margin-bottom: 3px;
  }

  .exp-meta {
    font-size: 11.5px;
    margin-bottom: 7px;
    display: flex;
    align-items: center;
    gap: 8px;
    flex-wrap: wrap;
  }

  .exp-company { font-weight: 600; color: var(--mid); }

  .exp-period {
    font-style: italic;
    color: var(--accent);
    font-size: 11px;
    background: rgba(127,179,200,0.12);
    border: 1px solid rgba(127,179,200,0.3);
    border-radius: 20px;
    padding: 1px 9px;
  }

  .exp-bullet {
    font-size: 11.5px;
    color: var(--muted);
    padding-left: 14px;
    margin-bottom: 4px;
    position: relative;
    line-height: 1.5;
    font-weight: 300;
  }

  .exp-bullet::before {
    content: '';
    position: absolute;
    left: 2px;
    top: 7px;
    width: 5px;
    height: 5px;
    border-radius: 50%;
    background: var(--accent);
  }

  /* projects */
  .project-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
  }

  .project-card {
    background: white;
    border-radius: 8px;
    padding: 14px 16px;
    border-left: 3px solid var(--accent);
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
  }

  .project-name  { font-size: 13px; font-weight: 600; color: var(--dark); margin-bottom: 4px; }
  .project-stack { font-size: 10.5px; color: var(--accent); font-style: italic; margin-bottom: 6px; }
  .project-desc  { font-size: 11px; color: var(--muted); line-height: 1.55; font-weight: 300; }

  /* divider */
  .exp-divider {
    height: 1px;
    background: rgba(0,0,0,0.06);
    margin: 14px 0;
  }

  /* print */
  @media print {
    body { padding: 0; background: none; }
    .page { box-shadow: none; width: 100%; min-height: auto; }
  }
</style>
</head>
<body>
<div class="page">

  <!-- ════ SIDEBAR ════ -->
  <aside class="sidebar">

    <div class="name-block">
      <div class="first">Camille</div>
      <div class="last">DUPONT</div>
      <div class="title">Full-Stack Web Developer</div>
    </div>

    <!-- Contact -->
    <div class="l-section">
      <div class="l-section-title">Contact</div>
      <div class="contact-item"><span class="icon">✉</span> candidat@exemple.com</div>
      <div class="contact-item"><span class="icon">in</span> linkedin.com/in/yourprofile</div>
      <div class="contact-item"><span class="icon">⌥</span> github.com/yourusername</div>
      <div class="contact-item"><span class="icon">⌖</span> Paris, France</div>
    </div>

    <!-- Skills -->
    <div class="l-section">
      <div class="l-section-title">Compétences</div>

      <div class="skill-group-label">Front-End</div>
      <div class="skill-item">
        <div class="skill-label">ReactJS / VueJS / Nuxt.js</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-label">TypeScript / JavaScript</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-label">HTML5 / CSS3</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot"></div>
        </div>
      </div>

      <div class="skill-group-label">Back-End</div>
      <div class="skill-item">
        <div class="skill-label">Node.js / Express.js</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-label">PHP · Symfony / Laravel</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot"></div>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-label">Python / Django</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot"></div>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-label">GraphQL / REST APIs</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div>
        </div>
      </div>

      <div class="skill-group-label">DevOps & Cloud</div>
      <div class="skill-item">
        <div class="skill-label">AWS / Firebase</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot"></div><div class="dot"></div>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-label">GitLab CI/CD</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot"></div>
        </div>
      </div>
      <div class="skill-item">
        <div class="skill-label">Docker</div>
        <div class="skill-dots">
          <div class="dot filled"></div><div class="dot filled"></div><div class="dot filled"></div><div class="dot"></div><div class="dot"></div>
        </div>
      </div>
    </div>

    <!-- Education -->
    <div class="l-section">
      <div class="l-section-title">Formation</div>
      <div class="edu-item">
        <div class="edu-degree">Diplôme Ingénieur Informatique</div>
        <div class="edu-school">EFREI Paris · 2016 – 2019</div>
        <div class="edu-note">Spécialisation Data Science</div>
      </div>
      <div class="edu-item">
        <div class="edu-degree">DUT Informatique</div>
        <div class="edu-school">IUT d'Orsay · 2015 – 2016</div>
      </div>
      <div class="edu-item">
        <div class="edu-degree">Baccalauréat Scientifique</div>
        <div class="edu-school">Lycée Janson de Sailly · 2015</div>
        <div class="edu-note">Mention Bien</div>
      </div>
    </div>

    <!-- Languages -->
    <div class="l-section">
      <div class="l-section-title">Langues</div>
      <div class="lang-item">
        <div class="lang-name">Anglais – C1</div>
        <div class="lang-note">Stage 6 mois au Royaume-Uni</div>
      </div>
      <div class="lang-item">
        <div class="lang-name">Espagnol – B1</div>
        <div class="lang-note">Niveau conversationnel</div>
      </div>
    </div>

    <!-- Interests -->
    <div class="l-section">
      <div class="l-section-title">Intérêts</div>
      <div class="interest-list">
        <span class="interest-tag">🏓 Tennis de table</span>
        <span class="interest-tag">📚 Lecture</span>
        <span class="interest-tag">🎬 Cinéma</span>
        <span class="interest-tag">✏️ Dessin</span>
      </div>
    </div>

  </aside>

  <!-- ════ MAIN ════ -->
  <main class="main">

    <!-- About -->
    <div class="r-section">
      <div class="r-section-title">À propos</div>
      <p class="about-text">
        Développeur full-stack passionné, diplômé ingénieur en informatique à l'EFREI Paris. Fort d'expériences au sein de grands groupes — Instagram, Thales, Sopra Steria — je conçois des architectures back-end robustes et des interfaces front-end modernes et fluides. Je recherche une opportunité pour contribuer à des projets web ou mobile innovants, alliant excellence technique et créativité.
      </p>
    </div>

    <!-- Experience -->
    <div class="r-section">
      <div class="r-section-title">Expériences</div>

      <div class="exp-entry">
        <div class="exp-title">Développeur Back-End — PHP &amp; Node.js</div>
        <div class="exp-meta">
          <span class="exp-company">Sopra Steria, Paris</span>
          <span class="exp-period">2021 – 2022</span>
        </div>
        <div class="exp-bullet">APIs PHP sécurisées avec Symfony et Laravel (secteur défense)</div>
        <div class="exp-bullet">Requêtes SQL avancées et ElasticSearch sur grands volumes de données</div>
        <div class="exp-bullet">Endpoints Express.js sécurisés avec considérations cybersécurité</div>
        <div class="exp-bullet">Intégration de services AWS en Node.js pour améliorer la scalabilité</div>
      </div>

      <div class="exp-divider"></div>

      <div class="exp-entry">
        <div class="exp-title">Développeur Back-End — Python</div>
        <div class="exp-meta">
          <span class="exp-company">Thales, Grenoble</span>
          <span class="exp-period">2020 – 2021</span>
        </div>
        <div class="exp-bullet">Conception et implémentation d'endpoints GraphQL</div>
        <div class="exp-bullet">Optimisation de traitement massif de documents sur base NoSQL</div>
        <div class="exp-bullet">96 % des tâches sprint livrées dans les délais, validées en peer review</div>
      </div>

      <div class="exp-divider"></div>

      <div class="exp-entry">
        <div class="exp-title">Développeur Front-End — ReactJS</div>
        <div class="exp-meta">
          <span class="exp-company">Instagram, Paris</span>
          <span class="exp-period">2019</span>
        </div>
        <div class="exp-bullet">Tests unitaires automatisés sur composants clés du module messaging</div>
        <div class="exp-bullet">Refactoring de composants ReactJS en TypeScript</div>
        <div class="exp-bullet">Mise à jour des dépendances et résolution des problèmes de compatibilité</div>
      </div>
    </div>

    <!-- Projects -->
    <div class="r-section">
      <div class="r-section-title">Projets</div>
      <div class="project-grid">
        <div class="project-card">
          <div class="project-name">Plateforme Web Full-Stack</div>
          <div class="project-stack">React · Node.js · MongoDB · Docker</div>
          <div class="project-desc">Plateforme scalable de gestion et visualisation de données, déployée avec containerisation et architecture API moderne.</div>
        </div>
        <div class="project-card">
          <div class="project-name">Dashboard Data Analytics</div>
          <div class="project-stack">Vue.js · Django · PostgreSQL</div>
          <div class="project-desc">Dashboard analytique agrégeant de grands datasets avec visualisations interactives et rapports automatisés.</div>
        </div>
      </div>
    </div>

  </main>

</div>
</body>
</html>
