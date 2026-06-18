# EnferTal
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Enfertal — Guía de la salud mental completa</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:wght@300;500;700&family=Inter:wght@400;500&display=swap" rel="stylesheet">
<link rel="icon" type="image/x-icon" href="img/e.png">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #cfe0b7;
    --bg2: #cfe0b7;
    --text: #1C1C1A;
    --muted: #6B6860;
    --accent: #3B6D11;
    --accent2: #533A89;
    --border: rgba(28,28,26,0.12);
    --card: #FFFFFF;
    --pill-bg: #EAF3DE;
    --pill-txt: #27500A;
  }

  body {
    font-family: 'Inter', sans-serif;
    background: var(--bg);
    color: var(--text);
    line-height: 1.7;
  }

  /* HERO */
  .hero {
    background: var(--text);
    color: #F7F5F0;
    padding: 5rem 2rem 4rem;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute;
    inset: 0;
    background: radial-gradient(ellipse 60% 80% at 50% 0%, #3B6D11 0%, transparent 70%);
    opacity: 0.4;
  }
  .hero-eyebrow {
    font-family: 'Inter', sans-serif;
    font-size: 12px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: #C0DD97;
    margin-bottom: 1.2rem;
    position: relative;
  }
  .hero h1 {
    font-family: 'Fraunces', serif;
    font-weight: 700;
    font-size: clamp(2.4rem, 6vw, 4.5rem);
    line-height: 1.1;
    margin-bottom: 1.2rem;
    position: relative;
  }
  .hero h1 em { font-style: italic; color: #C0DD97; }
  .hero-desc {
    font-size: 1.05rem;
    color: #B4B2A9;
    max-width: 560px;
    margin: 0 auto 2.5rem;
    position: relative;
  }
  .hero-tags {
    display: flex; flex-wrap: wrap; gap: 8px; justify-content: center;
    position: relative;
  }
  .hero-tag {
    background: rgba(255,255,255,0.1);
    border: 1px solid rgba(255,255,255,0.2);
    border-radius: 100px;
    padding: 5px 14px;
    font-size: 13px;
    color: #D3D1C7;
    cursor: pointer;
    text-decoration: none;
    transition: background .2s;
  }
  .hero-tag:hover { background: rgba(255,255,255,0.2); }

  /* NAV PILLS */
  .nav-bar {
    background: var(--bg2);
    border-bottom: 1px solid var(--border);
    padding: 0.75rem 2rem;
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    justify-content: center;
    position: sticky;
    top: 0;
    z-index: 100;
  }
  .nav-pill {
    font-size: 13px;
    padding: 5px 14px;
    border-radius: 100px;
    border: 1px solid var(--border);
    background: transparent;
    color: var(--muted);
    cursor: pointer;
    text-decoration: none;
    transition: all .2s;
    white-space: nowrap;
  }
  .nav-pill:hover { background: var(--pill-bg); color: var(--pill-txt); border-color: #639922; }

  /* LAYOUT */
  .container { max-width: 900px; margin: 0 auto; padding: 0 2rem; }
  .section { padding: 4rem 0; background: var(--bg2); }
  .section + .section { border-top: 1px solid var(--border); }

  .section-label {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.14em;
    color: var(--muted);
    margin-bottom: 0.4rem;
  }
  .section-title {
    font-family: 'Fraunces', serif;
    font-weight: 500;
    font-size: 2rem;
    margin-bottom: 2.5rem;
    line-height: 1.2;
  }

  /* DISEASE CARD */
  .disease-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    overflow: hidden;
    margin-bottom: 2.5rem;
  }
  .disease-header {
    display: flex;
    align-items: flex-start;
    gap: 1.25rem;
    padding: 1.5rem 1.5rem 0;
  }
  .disease-icon {
    width: 60px;
    height: 60px;
    border-radius: 12px;
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 28px;
  }
  .disease-meta { flex: 1; }
  .disease-name {
    font-family: 'Fraunces', serif;
    font-size: 1.4rem;
    font-weight: 500;
    line-height: 1.2;
    margin-bottom: 0.2rem;
  }
  .disease-cat {
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    padding: 3px 10px;
    border-radius: 100px;
    display: inline-block;
    margin-bottom: 0.6rem;
  }
  .disease-desc { font-size: 0.95rem; color: var(--muted); line-height: 1.6; }
  .disease-body {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 0;
    margin-top: 1.5rem;
    border-top: 1px solid var(--border);
  }
  .disease-col {
    padding: 1.25rem 1.5rem;
    font-size: 0.88rem;
  }
  .disease-col + .disease-col { border-left: 1px solid var(--border); }
  .disease-col-label {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    color: var(--muted);
    margin-bottom: 0.6rem;
  }
  .disease-col ul { list-style: none; }
  .disease-col li { padding: 3px 0; display: flex; gap: 6px; align-items: flex-start; }
  .disease-col li::before { content: '—'; color: var(--muted); flex-shrink: 0; font-size: 0.8rem; margin-top: 2px; }

  /* COLOR THEMES PER CATEGORY */
  .theme-mood .disease-icon { background: #FAECE7; }
  .theme-mood .disease-cat { background: #FAECE7; color: #4A1B0C; }
  .theme-anxiety .disease-icon { background: #EEEDFE; }
  .theme-anxiety .disease-cat { background: #EEEDFE; color: #26215C; }
  .theme-psychotic .disease-icon { background: #E6F1FB; }
  .theme-psychotic .disease-cat { background: #E6F1FB; color: #042C53; }
  .theme-personality .disease-icon { background: #FBEAF0; }
  .theme-personality .disease-cat { background: #FBEAF0; color: #4B1528; }
  .theme-eating .disease-icon { background: #EAF3DE; }
  .theme-eating .disease-cat { background: #EAF3DE; color: #173404; }
  .theme-neuro .disease-icon { background: #FAEEDA; }
  .theme-neuro .disease-cat { background: #FAEEDA; color: #412402; }
  .theme-trauma .disease-icon { background: #E1F5EE; }
  .theme-trauma .disease-cat { background: #E1F5EE; color: #04342C; }

  /* HELP BOXES */
  .help-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1rem;
  }
  .help-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.25rem;
  }
  .help-icon {
    font-size: 1.6rem;
    margin-bottom: 0.75rem;
    display: block;
  }
  .help-title { font-weight: 500; font-size: 0.95rem; margin-bottom: 0.4rem; }
  .help-text { font-size: 0.85rem; color: var(--muted); line-height: 1.5; }

  /* TRIVIA */
  .trivia-section { padding: 4rem 0; }
  .trivia-disease-title {
    font-family: 'Fraunces', serif;
    font-size: 1.5rem;
    font-weight: 500;
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .trivia-block { margin-bottom: 3rem; }
  .q-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1.25rem;
    margin-bottom: 0.75rem;
  }
  .q-text {
    font-size: 0.92rem;
    font-weight: 500;
    margin-bottom: 0.75rem;
  }
  .q-options {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6px;
  }
  .q-opt {
    font-size: 0.83rem;
    padding: 7px 12px;
    border-radius: 8px;
    border: 1px solid var(--border);
    background: var(--card);
    cursor: pointer;
    text-align: left;
    color: var(--text);
    transition: all .15s;
  }
  .q-opt:hover { border-color: #639922; background: #F1F6EA; }
  .q-opt.correct { background: #EAF3DE; border-color: #3B6D11; color: #173404; }
  .q-opt.wrong { background: #FCEBEB; border-color: #A32D2D; color: #501313; }
  .q-opt.reveal { background: #EAF3DE; border-color: #3B6D11; color: #173404; opacity: 0.7; }
  .q-feedback {
    font-size: 0.8rem;
    margin-top: 8px;
    padding: 6px 10px;
    border-radius: 6px;
    display: none;
  }
  .q-feedback.show { display: block; }
  .q-feedback.ok { background: #EAF3DE; color: #27500A; }
  .q-feedback.bad { background: #FCEBEB; color: #791F1F; }

  /* SCORE */
  .trivia-score {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 1rem 1.5rem;
    margin-bottom: 2rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 0.9rem;
  }
  .score-num { font-size: 1.3rem; font-weight: 500; color: var(--accent); }
  .block-score {
    margin-top: 1rem;
    font-size: 0.95rem;
    font-weight: 500;
    color: var(--accent);
  }

  /* FOOTER */
  footer {
    background: var(--text);
    color: #888780;
    text-align: center;
    padding: 2rem;
    font-size: 0.82rem;
  }
  footer a { color: #C0DD97; }

  /* CLASSIFICATION INTRO */
  .class-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 1rem;
    margin-bottom: 3rem;
  }
  .class-item {
    padding: 1rem;
    border-radius: 12px;
    border: 1px solid var(--border);
    text-align: center;
  }
  .class-item-icon { font-size: 1.8rem; margin-bottom: 0.5rem; }
  .class-item-name { font-weight: 500; font-size: 0.9rem; margin-bottom: 0.2rem; }
  .class-item-desc { font-size: 0.78rem; color: var(--muted); }

  @media (max-width: 640px) {
    .disease-body { grid-template-columns: 1fr; }
    .disease-col + .disease-col { border-left: none; border-top: 1px solid var(--border); }
    .q-options { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>

<!-- HERO -->
<section class="hero">
  <p class="hero-eyebrow">Guía de Salud Mental</p>
  <h1>Comprender la <em>mente</em><br>para cuidarla mejor</h1>
  <p class="hero-desc">Una guía clara sobre las principales enfermedades mentales: qué son, cómo se manifiestan y cómo podemos acompañar a quienes las viven.</p>
  <div class="hero-tags">
    <a class="hero-tag" href="#clasificacion">Clasificación</a>
    <a class="hero-tag" href="#enfermedades">Enfermedades</a>
    <a class="hero-tag" href="#como-ayudar">Cómo ayudar</a>
    <a class="hero-tag" href="#trivia">Trivia</a>
  </div>
</section>

<!-- NAV -->
<nav class="nav-bar">
  <a class="nav-pill" href="#clasificacion">Clasificación</a>
  <a class="nav-pill" href="#depresion">Depresión</a>
  <a class="nav-pill" href="#bipolar">Bipolar</a>
  <a class="nav-pill" href="#ansiedad">Ansiedad</a>
  <a class="nav-pill" href="#toc">TOC</a>
  <a class="nav-pill" href="#esquizofrenia">Esquizofrenia</a>
  <a class="nav-pill" href="#tdah">TDAH</a>
  <a class="nav-pill" href="#trastornos-alimentarios">T. Alimentarios</a>
  <a class="nav-pill" href="#ptsd">PTSD</a>
  <a class="nav-pill" href="#como-ayudar">Cómo ayudar</a>
  <a class="nav-pill" href="#trivia">Trivia</a>
</nav>

<!-- CLASIFICACIÓN -->
<section class="section" id="clasificacion">
  <div class="container">
    <p class="section-label">Punto de partida</p>
    <h2 class="section-title">Clasificación de las enfermedades mentales</h2>
    <p style="color:var(--muted); margin-bottom:2rem; max-width:680px;">Las enfermedades mentales se agrupan en categorías según sus características clínicas. Los sistemas de referencia internacionales son el <strong>DSM-5</strong> (Manual Diagnóstico de la APA) y la <strong>CIE-11</strong> (OMS). A continuación, las principales categorías que veremos en esta guía.</p>
    <div class="class-grid">
      <div class="class-item" style="background:#FAECE7; border-color:#F0997B;">
        <div class="class-item-icon">🌧️</div>
        <div class="class-item-name">Trastornos del estado de ánimo</div>
        <div class="class-item-desc">Depresión, Trastorno Bipolar</div>
      </div>
      <div class="class-item" style="background:#EEEDFE; border-color:#AFA9EC;">
        <div class="class-item-icon">😰</div>
        <div class="class-item-name">Trastornos de ansiedad</div>
        <div class="class-item-desc">TAG, Fobias, TOC, Pánico</div>
      </div>
      <div class="class-item" style="background:#E6F1FB; border-color:#85B7EB;">
        <div class="class-item-icon">🔮</div>
        <div class="class-item-name">Trastornos psicóticos</div>
        <div class="class-item-desc">Esquizofrenia, Psicosis</div>
      </div>
      <div class="class-item" style="background:#FBEAF0; border-color:#ED93B1;">
        <div class="class-item-icon">🪞</div>
        <div class="class-item-name">Trastornos de personalidad</div>
        <div class="class-item-desc">TLP, Narcisista, Antisocial</div>
      </div>
      <div class="class-item" style="background:#EAF3DE; border-color:#97C459;">
        <div class="class-item-icon">🍽️</div>
        <div class="class-item-name">Trastornos alimentarios</div>
        <div class="class-item-desc">Anorexia, Bulimia, BED</div>
      </div>
      <div class="class-item" style="background:#FAEEDA; border-color:#EF9F27;">
        <div class="class-item-icon">⚡</div>
        <div class="class-item-name">Trastornos del neurodesarrollo</div>
        <div class="class-item-desc">TDAH, Autismo</div>
      </div>
      <div class="class-item" style="background:#E1F5EE; border-color:#5DCAA5;">
        <div class="class-item-icon">💥</div>
        <div class="class-item-name">Trastornos relacionados con trauma</div>
        <div class="class-item-desc">PTSD, Estrés agudo</div>
      </div>
    </div>
  </div>
</section>

<!-- ENFERMEDADES -->
<section class="section" id="enfermedades">
  <div class="container">
    <p class="section-label">Descripción detallada</p>
    <h2 class="section-title">Enfermedades mentales</h2>

    <!-- DEPRESION -->
    <div class="disease-card theme-mood" id="depresion">
      <div class="disease-header">
        <div class="disease-icon">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="60" height="60" rx="12" fill="#FAECE7"/>
            <circle cx="30" cy="28" r="14" stroke="#D85A30" stroke-width="2"/>
            <path d="M23 36 Q30 30 37 36" stroke="#D85A30" stroke-width="2" stroke-linecap="round" fill="none"/>
            <circle cx="25" cy="26" r="2" fill="#D85A30"/>
            <circle cx="35" cy="26" r="2" fill="#D85A30"/>
            <path d="M18 14 L22 18M42 14 L38 18" stroke="#D85A30" stroke-width="1.5" stroke-linecap="round"/>
            <path d="M30 10 L30 6" stroke="#D85A30" stroke-width="1.5" stroke-linecap="round"/>
          </svg>
        </div>
        <div class="disease-meta">
          <div class="disease-cat">Trastorno del estado de ánimo</div>
          <div class="disease-name">Depresión mayor</div>
          <div class="disease-desc">Trastorno caracterizado por una tristeza profunda y persistente, pérdida de interés y reducción de la energía que afecta la capacidad de llevar una vida cotidiana. Es una de las enfermedades más prevalentes a nivel mundial: afecta a más de 280 millones de personas.</div>
        </div>
      </div>
      <div class="disease-body">
        <div class="disease-col">
          <div class="disease-col-label">Actitudes y síntomas</div>
          <ul>
            <li>Tristeza persistente sin causa aparente</li>
            <li>Aislamiento social progresivo</li>
            <li>Pérdida de interés en actividades que antes disfrutaba</li>
            <li>Fatiga crónica, incluso al despertar</li>
            <li>Cambios en apetito o peso</li>
            <li>Dificultad para concentrarse o tomar decisiones</li>
            <li>Pensamientos de inutilidad o culpa excesiva</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo reconocerla</div>
          <ul>
            <li>Dura más de dos semanas seguidas</li>
            <li>Interfiere con trabajo, relaciones y vida diaria</li>
            <li>La persona no puede "animarse" con esfuerzo propio</li>
            <li>Puede haber llanto sin razón clara</li>
            <li>Cambios en el sueño (insomnio o hipersomnia)</li>
            <li>Hablar de vacío o desesperanza</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo ayudar</div>
          <ul>
            <li>Escuchar sin juzgar ni dar consejos no pedidos</li>
            <li>No decir "anímate" o "piensa positivo"</li>
            <li>Acompañar en actividades cotidianas</li>
            <li>Ayudar a buscar ayuda profesional</li>
            <li>Mantener el contacto aunque no responda</li>
            <li>Informarse sobre la enfermedad</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- BIPOLAR -->
    <div class="disease-card theme-mood" id="bipolar">
      <div class="disease-header">
        <div class="disease-icon">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="60" height="60" rx="12" fill="#FAECE7"/>
            <path d="M12 38 L20 20 L28 34 L36 16 L44 30 L48 24" stroke="#D85A30" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" fill="none"/>
            <circle cx="20" cy="20" r="3" fill="#D85A30"/>
            <circle cx="36" cy="16" r="3" fill="#D85A30"/>
            <circle cx="28" cy="34" r="3" fill="#F0997B"/>
            <circle cx="44" cy="30" r="3" fill="#F0997B"/>
            <path d="M12 30 H48" stroke="#D85A30" stroke-width="1" stroke-dasharray="3 3" opacity="0.5"/>
          </svg>
        </div>
        <div class="disease-meta">
          <div class="disease-cat">Trastorno del estado de ánimo</div>
          <div class="disease-name">Trastorno bipolar</div>
          <div class="disease-desc">Caracterizado por episodios alternantes de manía (estado de euforia extrema, energía desbordante) y depresión. No es "cambios de humor" normales: los episodios pueden durar días, semanas o meses y afectan profundamente el comportamiento y las decisiones.</div>
        </div>
      </div>
      <div class="disease-body">
        <div class="disease-col">
          <div class="disease-col-label">Actitudes y síntomas</div>
          <ul>
            <li>Episodios de grandiosidad o euforia intensa</li>
            <li>Reducción de la necesidad de dormir (manía)</li>
            <li>Habla rápida, pensamiento acelerado</li>
            <li>Decisiones impulsivas, gastos excesivos</li>
            <li>Alternancia con períodos de depresión profunda</li>
            <li>Irritabilidad extrema en episodio maníaco</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo reconocerlo</div>
          <ul>
            <li>Los cambios de estado son cíclicos y extremos</li>
            <li>La euforia no se explica por algo externo</li>
            <li>La persona puede no reconocer que está mal</li>
            <li>Historial de comportamiento de riesgo en episodios</li>
            <li>Interrupciones laborales y relacionales recurrentes</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo ayudar</div>
          <ul>
            <li>No confrontar en episodio maníaco agudo</li>
            <li>Ayudar a mantener rutinas estables</li>
            <li>Apoyar la adherencia al tratamiento</li>
            <li>Aprender a reconocer señales de alerta temprana</li>
            <li>Establecer un plan de acción de emergencia juntos</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ANSIEDAD -->
    <div class="disease-card theme-anxiety" id="ansiedad">
      <div class="disease-header">
        <div class="disease-icon">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="60" height="60" rx="12" fill="#EEEDFE"/>
            <circle cx="30" cy="30" r="14" stroke="#7F77DD" stroke-width="2"/>
            <circle cx="30" cy="30" r="9" stroke="#7F77DD" stroke-width="1.5" stroke-dasharray="2 2"/>
            <path d="M30 16 L30 20M30 40 L30 44M16 30 L20 30M40 30 L44 30" stroke="#7F77DD" stroke-width="2" stroke-linecap="round"/>
            <circle cx="30" cy="30" r="3" fill="#7F77DD"/>
            <path d="M24 24 L28 28M36 36 L32 32M36 24 L32 28M24 36 L28 32" stroke="#AFA9EC" stroke-width="1.5" stroke-linecap="round"/>
          </svg>
        </div>
        <div class="disease-meta">
          <div class="disease-cat">Trastorno de ansiedad</div>
          <div class="disease-name">Trastorno de ansiedad generalizada</div>
          <div class="disease-desc">Preocupación excesiva, persistente y difícil de controlar sobre múltiples situaciones cotidianas. Va mucho más allá del nerviosismo normal y se acompaña de síntomas físicos. El TAG afecta a 1 de cada 14 personas a lo largo de su vida.</div>
        </div>
      </div>
      <div class="disease-body">
        <div class="disease-col">
          <div class="disease-col-label">Actitudes y síntomas</div>
          <ul>
            <li>Preocupación constante e incontrolable</li>
            <li>Dificultad para relajarse o "desconectar"</li>
            <li>Irritabilidad, tensión muscular</li>
            <li>Insomnio o sueño no reparador</li>
            <li>Dolores de cabeza, palpitaciones, sudoración</li>
            <li>Anticipación catastrófica ante situaciones comunes</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo reconocerla</div>
          <ul>
            <li>La persona sabe que se preocupa demasiado pero no puede parar</li>
            <li>Síntomas físicos sin causa médica clara</li>
            <li>Evita situaciones que generan preocupación</li>
            <li>Busca reassurance constantemente</li>
            <li>La ansiedad dura al menos 6 meses</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo ayudar</div>
          <ul>
            <li>Validar sin minimizar ("entiendo que lo sentís así")</li>
            <li>No decir "no hay nada que temer"</li>
            <li>Practicar técnicas de respiración juntos</li>
            <li>Ayudar a romper el ciclo de evitación gradualmente</li>
            <li>Fomentar la consulta con psicólogo/psiquiatra</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- TOC -->
    <div class="disease-card theme-anxiety" id="toc">
      <div class="disease-header">
        <div class="disease-icon">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="60" height="60" rx="12" fill="#EEEDFE"/>
            <path d="M20 30 C20 22 26 16 30 16 C34 16 40 22 40 30 C40 38 34 44 30 44 C26 44 20 38 20 30Z" stroke="#7F77DD" stroke-width="2" fill="none"/>
            <path d="M25 30 C25 26 27 23 30 23 C33 23 35 26 35 30 C35 34 33 37 30 37 C27 37 25 34 25 30Z" stroke="#7F77DD" stroke-width="1.5" fill="none"/>
            <circle cx="30" cy="30" r="3" fill="#7F77DD"/>
            <path d="M14 16 L18 20M46 16 L42 20M14 44 L18 40M46 44 L42 40" stroke="#AFA9EC" stroke-width="1.5" stroke-linecap="round"/>
          </svg>
        </div>
        <div class="disease-meta">
          <div class="disease-cat">Trastorno obsesivo-compulsivo</div>
          <div class="disease-name">TOC — Trastorno Obsesivo-Compulsivo</div>
          <div class="disease-desc">Ciclo de pensamientos intrusivos no deseados (obsesiones) que generan angustia, y comportamientos repetitivos (compulsiones) realizados para aliviarla. El alivio es temporal, lo que perpetúa el ciclo. No es "ser muy ordenado": es una condición que puede consumir horas del día.</div>
        </div>
      </div>
      <div class="disease-body">
        <div class="disease-col">
          <div class="disease-col-label">Actitudes y síntomas</div>
          <ul>
            <li>Pensamientos intrusivos repetitivos y perturbadores</li>
            <li>Rituales para reducir la angustia (lavarse, contar, ordenar)</li>
            <li>Necesidad de verificar repetidamente</li>
            <li>Miedo irracional a causar daño o contaminarse</li>
            <li>Angustia si no se realiza el ritual</li>
            <li>Consciencia de que el ritual es irracional pero incapacidad de parar</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo reconocerlo</div>
          <ul>
            <li>Los rituales consumen más de 1 hora al día</li>
            <li>Interfieren con actividades normales</li>
            <li>La persona siente vergüenza y lo oculta</li>
            <li>Puede haber temas específicos de obsesión (gérmenes, simetría, daño)</li>
            <li>Evitación de situaciones que detonan obsesiones</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo ayudar</div>
          <ul>
            <li>No participar en los rituales (les da alivio momentáneo pero refuerza el ciclo)</li>
            <li>No ridiculizar los miedos</li>
            <li>Buscar apoyo en terapia especializada (TCC, ERP)</li>
            <li>Celebrar pequeños avances en resistir compulsiones</li>
            <li>Tener paciencia: la recuperación es gradual</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- ESQUIZOFRENIA -->
    <div class="disease-card theme-psychotic" id="esquizofrenia">
      <div class="disease-header">
        <div class="disease-icon">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="60" height="60" rx="12" fill="#E6F1FB"/>
            <circle cx="30" cy="28" r="13" stroke="#378ADD" stroke-width="2" fill="none"/>
            <path d="M25 28 Q28 22 30 28 Q32 34 35 28" stroke="#378ADD" stroke-width="2" stroke-linecap="round" fill="none"/>
            <circle cx="25" cy="24" r="2" fill="#378ADD"/>
            <circle cx="35" cy="24" r="2" fill="#378ADD"/>
            <path d="M22 45 L24 38M38 45 L36 38M30 41 L30 38" stroke="#378ADD" stroke-width="1.5" stroke-linecap="round"/>
            <circle cx="22" cy="46" r="2" fill="#85B7EB"/>
            <circle cx="30" cy="46" r="2" fill="#85B7EB"/>
            <circle cx="38" cy="46" r="2" fill="#85B7EB"/>
          </svg>
        </div>
        <div class="disease-meta">
          <div class="disease-cat">Trastorno psicótico</div>
          <div class="disease-name">Esquizofrenia</div>
          <div class="disease-desc">Trastorno crónico que altera la percepción de la realidad. Incluye síntomas positivos (alucinaciones, delirios), síntomas negativos (aplanamiento emocional, alogia) y síntomas cognitivos. No implica "personalidad múltiple". Con tratamiento adecuado, muchas personas llevan vidas plenas.</div>
        </div>
      </div>
      <div class="disease-body">
        <div class="disease-col">
          <div class="disease-col-label">Actitudes y síntomas</div>
          <ul>
            <li>Alucinaciones (oír voces, ver cosas)</li>
            <li>Delirios (creencias falsas irrefutables)</li>
            <li>Desorganización del pensamiento y habla</li>
            <li>Retraimiento social y falta de motivación</li>
            <li>Expresión emocional reducida</li>
            <li>Dificultad para planificar y ejecutar tareas</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo reconocerla</div>
          <ul>
            <li>La persona reacciona a estímulos que otros no perciben</li>
            <li>Discurso desorganizado o incoherente</li>
            <li>Creencias muy inusuales que mantiene con convicción</li>
            <li>Cambio drástico en comportamiento y funcionamiento</li>
            <li>Inicio frecuente en adolescencia o adultez temprana</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo ayudar</div>
          <ul>
            <li>No discutir ni reforzar los delirios</li>
            <li>Mantener un entorno tranquilo y predecible</li>
            <li>Apoyar activamente la continuidad del tratamiento</li>
            <li>Educarse sobre la enfermedad (psicoeducación familiar)</li>
            <li>Celebrar logros pequeños del día a día</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- TDAH -->
    <div class="disease-card theme-neuro" id="tdah">
      <div class="disease-header">
        <div class="disease-icon">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="60" height="60" rx="12" fill="#FAEEDA"/>
            <path d="M16 20 L30 14 L44 20 L44 32 C44 40 30 48 30 48 C30 48 16 40 16 32 Z" stroke="#BA7517" stroke-width="2" fill="none"/>
            <path d="M23 30 L27 34 L37 24" stroke="#BA7517" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
            <circle cx="30" cy="20" r="3" fill="#EF9F27" opacity="0.6"/>
            <path d="M12 10 L15 13M48 10 L45 13M10 32 L14 30M50 32 L46 30" stroke="#EF9F27" stroke-width="1.5" stroke-linecap="round" opacity="0.7"/>
          </svg>
        </div>
        <div class="disease-meta">
          <div class="disease-cat">Trastorno del neurodesarrollo</div>
          <div class="disease-name">TDAH — Trastorno por Déficit de Atención e Hiperactividad</div>
          <div class="disease-desc">Patrón persistente de inatención y/o hiperactividad-impulsividad que interfiere con el funcionamiento. No es falta de disciplina ni de inteligencia: el cerebro con TDAH regula la atención de manera diferente. Afecta a niños y adultos, y puede tener presentaciones muy diversas.</div>
        </div>
      </div>
      <div class="disease-body">
        <div class="disease-col">
          <div class="disease-col-label">Actitudes y síntomas</div>
          <ul>
            <li>Dificultad para sostener la atención en tareas</li>
            <li>Olvidos frecuentes en actividades cotidianas</li>
            <li>Impulsividad: actuar antes de pensar</li>
            <li>Hiperactividad (en niños: no poder quedarse quieto)</li>
            <li>Hiperfoco en actividades de interés</li>
            <li>Desorganización y dificultad para planificar</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo reconocerlo</div>
          <ul>
            <li>Síntomas presentes desde la infancia</li>
            <li>Aparecen en más de un contexto (casa, escuela, trabajo)</li>
            <li>No es pereza: hay esfuerzo real sin resultado proporcional</li>
            <li>Sensación de estar "a punto de explotar" por dentro</li>
            <li>Dificultad para iniciar tareas aunque se quiera hacerlas</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo ayudar</div>
          <ul>
            <li>No interpretar la distracción como desinterés o descuido</li>
            <li>Usar recordatorios visuales y listas</li>
            <li>Dividir las tareas en pasos pequeños</li>
            <li>Celebrar cuando completan algo</li>
            <li>Apoyo en evaluación y tratamiento (terapia + medicación si corresponde)</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- TRASTORNOS ALIMENTARIOS -->
    <div class="disease-card theme-eating" id="trastornos-alimentarios">
      <div class="disease-header">
        <div class="disease-icon">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="60" height="60" rx="12" fill="#EAF3DE"/>
            <circle cx="30" cy="30" r="14" stroke="#3B6D11" stroke-width="2" fill="none"/>
            <path d="M22 30 C22 26 26 22 30 22 C34 22 38 26 38 30" stroke="#3B6D11" stroke-width="2" stroke-linecap="round" fill="none"/>
            <path d="M24 34 Q30 38 36 34" stroke="#3B6D11" stroke-width="2" stroke-linecap="round" fill="none"/>
            <path d="M30 16 L30 12M14 30 L10 30M30 44 L30 48M46 30 L50 30" stroke="#639922" stroke-width="1.5" stroke-linecap="round" opacity="0.7"/>
          </svg>
        </div>
        <div class="disease-meta">
          <div class="disease-cat">Trastorno alimentario</div>
          <div class="disease-name">Trastornos de la conducta alimentaria</div>
          <div class="disease-desc">Grupo de condiciones que incluyen anorexia nerviosa, bulimia nerviosa y el trastorno por atracón, caracterizadas por comportamientos alimentarios perturbados y una relación disfuncional con el propio cuerpo. Son enfermedades mentales serias con alta morbilidad.</div>
        </div>
      </div>
      <div class="disease-body">
        <div class="disease-col">
          <div class="disease-col-label">Actitudes y síntomas</div>
          <ul>
            <li>Preocupación obsesiva por el peso y la figura</li>
            <li>Restricción severa de alimentos (anorexia)</li>
            <li>Episodios de atracones seguidos de purgas (bulimia)</li>
            <li>Rituales en torno a la comida</li>
            <li>Imagen corporal distorsionada</li>
            <li>Miedo intenso a ganar peso</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo reconocerlos</div>
          <ul>
            <li>Evasión de comidas o excusas para no comer</li>
            <li>Ir al baño inmediatamente después de comer</li>
            <li>Pérdida o ganancia de peso drástica</li>
            <li>Comentarios negativos constantes sobre el propio cuerpo</li>
            <li>Ropa muy holgada para ocultar el cuerpo</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo ayudar</div>
          <ul>
            <li>No hablar del peso ni del cuerpo de la persona</li>
            <li>No forzar a comer ni vigilar las comidas</li>
            <li>Expresar preocupación desde el afecto, no la crítica</li>
            <li>Buscar ayuda especializada (equipo interdisciplinario)</li>
            <li>No reforzar conductas de control del peso</li>
          </ul>
        </div>
      </div>
    </div>

    <!-- PTSD -->
    <div class="disease-card theme-trauma" id="ptsd">
      <div class="disease-header">
        <div class="disease-icon">
          <svg width="60" height="60" viewBox="0 0 60 60" fill="none" xmlns="http://www.w3.org/2000/svg">
            <rect width="60" height="60" rx="12" fill="#E1F5EE"/>
            <path d="M30 14 L30 32" stroke="#0F6E56" stroke-width="2.5" stroke-linecap="round"/>
            <circle cx="30" cy="38" r="3" fill="#0F6E56"/>
            <circle cx="30" cy="30" r="16" stroke="#1D9E75" stroke-width="2" fill="none"/>
            <path d="M20 16 Q30 10 40 16" stroke="#5DCAA5" stroke-width="1.5" stroke-linecap="round" fill="none" opacity="0.7"/>
            <path d="M16 28 Q10 30 16 32" stroke="#5DCAA5" stroke-width="1.5" stroke-linecap="round" fill="none" opacity="0.7"/>
            <path d="M44 28 Q50 30 44 32" stroke="#5DCAA5" stroke-width="1.5" stroke-linecap="round" fill="none" opacity="0.7"/>
          </svg>
        </div>
        <div class="disease-meta">
          <div class="disease-cat">Trastorno relacionado con trauma</div>
          <div class="disease-name">TEPT — Trastorno de Estrés Postraumático</div>
          <div class="disease-desc">Respuesta prolongada a un evento traumático intenso. La persona revive el trauma, lo evita y experimenta cambios negativos en pensamientos y estado de alerta. No es una señal de debilidad: cualquier persona puede desarrollarlo. Es una respuesta del sistema nervioso ante una amenaza abrumadora.</div>
        </div>
      </div>
      <div class="disease-body">
        <div class="disease-col">
          <div class="disease-col-label">Actitudes y síntomas</div>
          <ul>
            <li>Flashbacks y recuerdos intrusivos del trauma</li>
            <li>Pesadillas recurrentes</li>
            <li>Estado de alerta constante (hipervigilancia)</li>
            <li>Evitación de lugares, personas o situaciones relacionadas</li>
            <li>Entumecimiento emocional</li>
            <li>Irritabilidad y reacciones de sobresalto exageradas</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo reconocerlo</div>
          <ul>
            <li>Inicio tras un evento traumático (accidente, violencia, etc.)</li>
            <li>Los síntomas duran más de un mes</li>
            <li>La persona "se va" emocionalmente o se paraliza</li>
            <li>Reacciones desproporcionadas a estímulos cotidianos</li>
            <li>Dificultad para hablar sobre el trauma</li>
          </ul>
        </div>
        <div class="disease-col">
          <div class="disease-col-label">Cómo ayudar</div>
          <ul>
            <li>No obligar a revivir ni contar el trauma</li>
            <li>Respetar los tiempos y límites de la persona</li>
            <li>Crear un entorno predecible y seguro</li>
            <li>Aprender técnicas de grounding para acompañar en crisis</li>
            <li>Apoyar el acceso a terapia especializada (EMDR, TCC)</li>
          </ul>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- COMO AYUDAR GENERAL -->
<section class="section" id="como-ayudar" style="background:var(--bg2);">
  <div class="container">
    <p class="section-label">Para todos los casos</p>
    <h2 class="section-title">Cómo acompañar a alguien con una enfermedad mental</h2>
    <div class="help-grid">
      <div class="help-card">
        <span class="help-icon">👂</span>
        <div class="help-title">Escuchá sin juzgar</div>
        <div class="help-text">A veces lo más poderoso es simplemente estar presente. No hay que tener respuestas. Escuchar sin minimizar ni comparar es el primer paso.</div>
      </div>
      <div class="help-card">
        <span class="help-icon">📚</span>
        <div class="help-title">Informate</div>
        <div class="help-text">Leer sobre la condición de la persona te ayuda a entender que ciertos comportamientos son síntomas, no elecciones. El conocimiento reduce el miedo y los prejuicios.</div>
      </div>
      <div class="help-card">
        <span class="help-icon">🩺</span>
        <div class="help-title">Acompañá en la búsqueda de ayuda</div>
        <div class="help-text">Muchas personas evitan buscar ayuda por vergüenza o miedo. Ofrecer acompañarlas a la primera consulta puede marcar la diferencia.</div>
      </div>
      <div class="help-card">
        <span class="help-icon">🔋</span>
        <div class="help-title">Cuidate vos también</div>
        <div class="help-text">Acompañar a alguien con una enfermedad mental puede ser agotador. Buscar apoyo para uno mismo no es egoísmo: es necesario para poder ayudar de manera sostenida.</div>
      </div>
      <div class="help-card">
        <span class="help-icon">🚫</span>
        <div class="help-title">Evitá estas frases</div>
        <div class="help-text">"Anímate", "todo está en tu cabeza", "tenés que ser más fuerte", "yo también me siento así". Estas frases, aunque bienintencionadas, pueden ser dañinas.</div>
      </div>
      <div class="help-card">
        <span class="help-icon">💚</span>
        <div class="help-title">Mantené el contacto</div>
        <div class="help-text">Muchas personas se aíslan durante los episodios. Un mensaje simple ("pienso en vos, no tenés que responder") puede ser un ancla importante.</div>
      </div>
      <div class="help-card">
        <span class="help-icon">🆘</span>
        <div class="help-title">En caso de crisis</div>
        <div class="help-text">Si hay riesgo inmediato para la persona, contactar servicios de emergencia. En Argentina: SAME 107, Línea de Salud Mental 0800-999-0091 (gratuita, 24h).</div>
      </div>
      <div class="help-card">
        <span class="help-icon">⚠️</span>
        <div class="help-title">No diagnosticar</div>
        <div class="help-text">Solo profesionales de la salud mental pueden diagnosticar. Tu rol es acompañar y facilitar el acceso a atención, no etiquetar ni tratar.</div>
      </div>
    </div>
  </div>
</section>

<!-- TRIVIA -->
<section class="trivia-section" id="trivia">
  <div class="container">
    <p class="section-label">Pone a prueba tus conocimientos</p>
    <h2 class="section-title">Trivia de salud mental</h2>
    <p style="color:var(--muted); margin-bottom:2.5rem;">10 preguntas por cada enfermedad. Hacé clic en la respuesta para ver si acertaste.</p>

    <div id="global-score" class="trivia-score">
      <span>Respuestas correctas totales</span>
      <span class="score-num" id="score-display">0 / 0</span>
    </div>

    <div id="trivia-container"></div>
  </div>
</section>

<footer>
  <p>Esta guía tiene fines informativos y educativos. No reemplaza el diagnóstico ni el tratamiento profesional.</p>
  <p style="margin-top:6px;">Ante cualquier consulta, contactá a un profesional de salud mental. <a href="https://www.who.int/es/news-room/fact-sheets/detail/mental-disorders" target="_blank">OMS — Más información</a></p>
</footer>

<script>
const triviaData = [
  {
    enfermedad: "Depresión mayor",
    emoji: "🌧️",
    preguntas: [
      { q: "¿Cuánto tiempo deben durar los síntomas para diagnosticar una depresión mayor?", opts: ["1 semana", "Al menos 2 semanas", "6 meses", "1 día"], resp: 1 },
      { q: "¿Cuántas personas en el mundo sufren depresión según la OMS?", opts: ["50 millones", "100 millones", "280 millones", "500 millones"], resp: 2 },
      { q: "¿Cuál de estas frases es útil para alguien con depresión?", opts: ["¡Anímate!", "Yo también me siento así a veces", "Estoy aquí si querés hablar", "Piensa en positivo"], resp: 2 },
      { q: "La depresión es causada únicamente por...", opts: ["Problemas personales", "Debilidad de carácter", "Una combinación de factores biológicos, psicológicos y sociales", "Solo por herencia genética"], resp: 2 },
      { q: "¿Cuál es un síntoma típico de la depresión mayor?", opts: ["Exceso de energía", "Anhedonia (pérdida de placer)", "Hiperactividad", "Euforia"], resp: 1 },
      { q: "¿Qué tipo de profesional puede recetar medicación para la depresión?", opts: ["Psicólogo", "Psiquiatra", "Trabajador social", "Enfermero"], resp: 1 },
      { q: "La depresión posparto afecta exclusivamente a...", opts: ["Las madres", "Los padres", "Puede afectar a cualquier persona que acaba de tener un hijo", "Solo a mujeres mayores de 30"], resp: 2 },
      { q: "¿Cuál NO es un síntoma de la depresión?", opts: ["Insomnio", "Fatiga", "Alucinaciones frecuentes", "Falta de concentración"], resp: 2 },
      { q: "El tratamiento más efectivo para la depresión moderada-grave es:", opts: ["Solo psicoterapia", "Solo medicación", "Combinación de psicoterapia y medicación", "Hacer ejercicio solo"], resp: 2 },
      { q: "¿La depresión es lo mismo que la tristeza normal?", opts: ["Sí, son exactamente iguales", "No, la depresión es persistente e interfiere con la vida diaria", "Sí, solo difieren en intensidad", "No, la tristeza no existe"], resp: 1 }
    ]
  },
  {
    enfermedad: "Trastorno Bipolar",
    emoji: "📈",
    preguntas: [
      { q: "¿Qué caracteriza al trastorno bipolar?", opts: ["Solo episodios de tristeza", "Episodios alternantes de manía y depresión", "Cambios de humor normales y cotidianos", "Solo episodios de euforia"], resp: 1 },
      { q: "Durante un episodio maníaco, ¿cuál es un síntoma común?", opts: ["Mucho sueño", "Necesidad reducida de dormir", "Aislamiento social", "Tristeza profunda"], resp: 1 },
      { q: "El trastorno bipolar tipo I se diferencia del II en que...", opts: ["El tipo I solo tiene depresión", "El tipo I incluye episodios maníacos completos; el II solo hipomanía", "No hay diferencia", "El tipo II es más grave"], resp: 1 },
      { q: "¿A qué edad suele aparecer el trastorno bipolar?", opts: ["Infancia temprana (2-5 años)", "Principalmente en adolescencia y adultez temprana", "Solo después de los 50 años", "Exclusivamente en la tercera edad"], resp: 1 },
      { q: "¿Cuál es el tratamiento de referencia para el trastorno bipolar?", opts: ["Solo psicoterapia", "Estabilizadores del ánimo más psicoterapia", "Solo antidepresivos", "Ningún tratamiento es eficaz"], resp: 1 },
      { q: "¿Qué porcentaje aproximado de la población mundial tiene trastorno bipolar?", opts: ["0.1%", "1-3%", "10%", "25%"], resp: 1 },
      { q: "¿Cuál de estas actitudes NO es útil con alguien en episodio maníaco?", opts: ["Mantener calma", "Confrontar sus ideas con argumentos largos", "Reducir estímulos", "Contactar al psiquiatra"], resp: 1 },
      { q: "El litio se usa en el trastorno bipolar como:", opts: ["Antidepresivo específico", "Estabilizador del ánimo", "Somnífero", "Antipsicótico"], resp: 1 },
      { q: "El trastorno bipolar puede confundirse fácilmente con:", opts: ["Diabetes tipo 2", "TDAH o depresión unipolar", "Hipertensión", "Asma"], resp: 1 },
      { q: "¿Es posible tener una vida plena con trastorno bipolar?", opts: ["No, es una condena de por vida", "Sí, con tratamiento adecuado y apoyo, muchas personas lo logran", "Solo si nunca se tiene un episodio", "Solo en casos leves"], resp: 1 }
    ]
  },
  {
    enfermedad: "Trastorno de Ansiedad Generalizada",
    emoji: "😰",
    preguntas: [
      { q: "¿Cuánto tiempo deben persistir los síntomas para diagnosticar TAG?", opts: ["2 semanas", "1 mes", "Al menos 6 meses", "1 año"], resp: 2 },
      { q: "¿Cuál es una característica clave del TAG?", opts: ["Preocupación controlable y específica", "Preocupación excesiva e incontrolable por múltiples situaciones", "Miedo solo a situaciones sociales", "Episodios de pánico frecuentes"], resp: 1 },
      { q: "La ansiedad generalizada se diferencia del estrés cotidiano en que:", opts: ["Son exactamente lo mismo", "La ansiedad del TAG es desproporcionada e interfiere con la vida", "El estrés dura más tiempo", "No hay diferencia clínica"], resp: 1 },
      { q: "¿Cuál de estos síntomas físicos es típico del TAG?", opts: ["Euforia", "Tensión muscular crónica y dolores de cabeza", "Hiperactividad", "Pérdida de memoria total"], resp: 1 },
      { q: "¿Qué terapia psicológica ha demostrado más evidencia para el TAG?", opts: ["Psicoanálisis clásico de 5 sesiones", "Terapia cognitivo-conductual (TCC)", "Hipnosis únicamente", "Arteterapia exclusivamente"], resp: 1 },
      { q: "Una persona con TAG típicamente:", opts: ["Solo se preocupa en momentos puntuales", "Sabe que se preocupa demasiado pero no puede parar", "No reconoce su ansiedad", "Solo tiene síntomas físicos, sin preocupaciones mentales"], resp: 1 },
      { q: "¿Cuál de estas respuestas es útil ante alguien con ansiedad?", opts: ["'No hay nada de qué preocuparse'", "'Tu preocupación no tiene sentido'", "'Entiendo que lo sentís así, estoy acá'", "'Ya sé que exagerás'"], resp: 2 },
      { q: "¿La ansiedad puede tener síntomas físicos reales, aunque no haya enfermedad orgánica?", opts: ["No, los síntomas siempre son psicológicos únicamente", "Sí, la ansiedad puede causar síntomas físicos muy reales", "Solo en casos muy graves", "Solo en niños"], resp: 1 },
      { q: "¿Cuál es una estrategia de autoayuda con evidencia para la ansiedad?", opts: ["Evitar todas las situaciones que generan ansiedad", "Respiración diafragmática y mindfulness", "Aislarse hasta que pase", "Consumir café para activarse"], resp: 1 },
      { q: "El TAG afecta aproximadamente a qué porcentaje de la población adulta?", opts: ["Menos del 0.5%", "Entre el 3 y 5%", "Más del 20%", "Solo al 0.1%"], resp: 1 }
    ]
  },
  {
    enfermedad: "TOC",
    emoji: "🔄",
    preguntas: [
      { q: "¿Qué significa TOC?", opts: ["Trastorno Obsesivo Conductual", "Trastorno Obsesivo-Compulsivo", "Trastorno de Orientación Cognitiva", "Tendencia Obsesiva al Control"], resp: 1 },
      { q: "En el TOC, las compulsiones son:", opts: ["Pensamientos intrusivos no deseados", "Comportamientos repetitivos para reducir la angustia de las obsesiones", "Alucinaciones visuales", "Episodios de mania"], resp: 1 },
      { q: "Una persona con TOC típicamente:", opts: ["Disfruta de sus rituales", "Sabe que sus rituales son irracionales pero no puede evitarlos", "No tiene consciencia de su problema", "Solo tiene obsesiones sin compulsiones"], resp: 1 },
      { q: "¿Cuánto tiempo deben ocupar las obsesiones/compulsiones para ser diagnósticamente significativas?", opts: ["Menos de 15 minutos por día", "Más de 1 hora por día", "Solo en situaciones de estrés", "Permanentemente, sin interrupciones"], resp: 1 },
      { q: "¿Cuál es el tratamiento más efectivo para el TOC?", opts: ["Solo medicación", "Terapia de exposición y prevención de respuesta (ERP) con o sin medicación", "Hipnosis", "Reposo absoluto"], resp: 1 },
      { q: "Decir 'soy muy TOC' cuando a alguien le gusta el orden es:", opts: ["Una descripción clínicamente precisa", "Incorrecto: el TOC es una condición discapacitante, no sinónimo de ser ordenado", "Un diagnóstico válido", "Lo mismo que tener TOC clínico"], resp: 1 },
      { q: "¿Cuál NO es un tema común de obsesión en el TOC?", opts: ["Contaminación y gérmenes", "Simetría y orden exacto", "Preferencias por la música clásica", "Miedo a causar daño a otros"], resp: 2 },
      { q: "¿Qué se recomienda que familiares NO hagan en el TOC?", opts: ["Apoyar emocionalmente", "Acompañar la búsqueda de tratamiento", "Participar en los rituales del familiar con TOC", "Informarse sobre la condición"], resp: 2 },
      { q: "El TOC suele comenzar en:", opts: ["Exclusivamente en la adultez tardía", "Infancia, adolescencia o adultez temprana", "Solo después de un trauma", "Solo en personas mayores de 60"], resp: 1 },
      { q: "¿El TOC está relacionado con la esquizofrenia?", opts: ["Sí, son la misma enfermedad", "No, son trastornos distintos aunque ambos pueden tener pensamientos intrusivos", "Sí, siempre coexisten", "No existen diferencias entre ellos"], resp: 1 }
    ]
  },
  {
    enfermedad: "Esquizofrenia",
    emoji: "🔮",
    preguntas: [
      { q: "La esquizofrenia implica que la persona tiene 'personalidad múltiple'", opts: ["Verdadero", "Falso: eso es el trastorno disociativo de identidad; son condiciones distintas", "Solo en casos graves", "Solo en adolescentes"], resp: 1 },
      { q: "¿Cuáles son los síntomas 'positivos' de la esquizofrenia?", opts: ["Síntomas agradables para el paciente", "Alucinaciones y delirios (algo que se agrega al comportamiento)", "Aplanamiento emocional y alogia", "Síntomas que responden bien al tratamiento"], resp: 1 },
      { q: "Los síntomas 'negativos' de la esquizofrenia incluyen:", opts: ["Alucinaciones y voces", "Aplanamiento emocional, alogia y abulia", "Episodios maníacos", "Rituales obsesivos"], resp: 1 },
      { q: "¿A qué edad suele aparecer la esquizofrenia?", opts: ["Exclusivamente en la infancia (0-10 años)", "Adolescencia tardía y adultez temprana, generalmente entre los 16 y 30 años", "Solo después de los 60", "Exclusivamente después de los 45"], resp: 1 },
      { q: "¿Con el tratamiento adecuado, qué puede esperar una persona con esquizofrenia?", opts: ["Nunca mejorar", "Llevar una vida plena y funcional en muchos casos", "Solo reducir síntomas mínimamente", "Curarse sin medicación"], resp: 1 },
      { q: "¿Cuál es la principal intervención para la esquizofrenia?", opts: ["Solo psicoterapia sin medicación", "Antipsicóticos más rehabilitación psicosocial", "Hospitalización permanente", "Solo cambios en el estilo de vida"], resp: 1 },
      { q: "¿Las personas con esquizofrenia son más violentas que la población general?", opts: ["Sí, siempre son peligrosas", "No; la gran mayoría no son violentas y son más víctimas que perpetradores", "Solo si no toman medicación", "Siempre cuando tienen alucinaciones"], resp: 1 },
      { q: "¿Qué son los delirios en la esquizofrenia?", opts: ["Mentiras deliberadas del paciente", "Creencias falsas irrefutables que no se corresponden con la realidad compartida", "Recuerdos traumáticos del pasado", "Alucinaciones visuales únicamente"], resp: 1 },
      { q: "¿Cuál es la prevalencia aproximada de la esquizofrenia?", opts: ["Afecta al 10% de la población", "Aproximadamente al 1% de la población mundial", "Solo 1 persona en un millón", "Al 5% de todos los adultos"], resp: 1 },
      { q: "Ante un familiar con delirios, la actitud más útil es:", opts: ["Discutir hasta que acepte la realidad", "No reforzar el delirio, mantenerse calmado y buscar apoyo profesional", "Seguirle la corriente completamente", "Ignorarlo siempre"], resp: 1 }
    ]
  },
  {
    enfermedad: "TDAH",
    emoji: "⚡",
    preguntas: [
      { q: "TDAH significa:", opts: ["Trastorno de Déficit de Atención e Hiperactividad", "Trastorno de Distracción y Actividad Hipnótica", "Trastorno Disociativo de Alta Hiperactividad", "Tendencia al Déficit de Acción y Habla"], resp: 0 },
      { q: "¿El TDAH solo existe en niños?", opts: ["Sí, desaparece siempre en la adultez", "No, muchos adultos tienen TDAH y puede persistir toda la vida", "Solo existe en varones", "Solo en niños menores de 5 años"], resp: 1 },
      { q: "El TDAH es causado por:", opts: ["Mala crianza o falta de disciplina", "Una combinación de factores genéticos y neurobiológicos", "Comer demasiado azúcar", "El uso excesivo de pantallas"], resp: 1 },
      { q: "¿Cuál es un signo de TDAH que a menudo se malinterpreta?", opts: ["Hiperfoco: concentración intensa en actividades de interés", "Ser muy organizado", "Tener siempre mucha energía", "No dormir nunca"], resp: 0 },
      { q: "¿El TDAH afecta solo a la atención o también a otras áreas?", opts: ["Solo a la atención", "Afecta la regulación emocional, la función ejecutiva y las relaciones sociales", "Solo al comportamiento en clase", "Solo al sueño"], resp: 1 },
      { q: "¿Qué tipo de intervención tiene mayor evidencia para el TDAH?", opts: ["Solo medicación estimulante", "Solo terapia conductual", "Combinación de medicación y terapia conductual según el caso", "Solo dieta sin gluten"], resp: 2 },
      { q: "Una persona con TDAH que no termina tareas probablemente:", opts: ["Es perezosa por elección", "Tiene dificultades reales de autorregulación e inicio de tareas", "No tiene interés en nada", "Simplemente no intenta esforzarse"], resp: 1 },
      { q: "¿El TDAH puede coexistir con otras condiciones?", opts: ["No, es siempre una condición aislada", "Sí, frecuentemente coexiste con ansiedad, depresión, TOC u otras condiciones", "Solo coexiste con el autismo", "Solo en adultos mayores"], resp: 1 },
      { q: "¿Cuál de estas estrategias ayuda a alguien con TDAH?", opts: ["Darle instrucciones largas y complejas de una vez", "Dividir las tareas en pasos pequeños con recordatorios visuales", "Pedirle que haga más esfuerzo de voluntad", "Ignorar sus dificultades para que las supere solo"], resp: 1 },
      { q: "El TDAH se diagnostica con:", opts: ["Solo una resonancia magnética", "Evaluación clínica integral (entrevista, escalas, historial de desarrollo)", "Un análisis de sangre específico", "Un solo test de cociente intelectual"], resp: 1 }
    ]
  },
  {
    enfermedad: "Trastornos Alimentarios",
    emoji: "🍽️",
    preguntas: [
      { q: "¿Los trastornos alimentarios afectan únicamente a mujeres jóvenes?", opts: ["Sí, solo a adolescentes mujeres", "No, afectan a todas las edades y géneros, aunque hay mayor prevalencia en mujeres", "Solo a personas con sobrepeso", "Solo en países desarrollados"], resp: 1 },
      { q: "La anorexia nerviosa se caracteriza por:", opts: ["Atracones frecuentes sin purga", "Restricción severa de alimentos e imagen corporal distorsionada", "Comer en exceso sin preocupación", "Solo pérdida de peso leve"], resp: 1 },
      { q: "La bulimia nerviosa implica:", opts: ["Solo restricción de alimentos", "Episodios de atracones seguidos de conductas compensatorias (purga, ejercicio excesivo)", "Solo preocupación por el peso sin conductas", "Pérdida de apetito total"], resp: 1 },
      { q: "¿Los trastornos alimentarios son solo un problema de vanidad?", opts: ["Sí, son una elección estética", "No, son enfermedades mentales serias con factores biológicos, psicológicos y sociales", "Solo buscan llamar la atención", "Son solo una fase adolescente"], resp: 1 },
      { q: "¿Cuál es la tasa de mortalidad de la anorexia nerviosa comparada con otros trastornos mentales?", opts: ["Es similar a la media", "Es una de las más altas entre los trastornos mentales", "Es prácticamente cero", "Solo afecta a la calidad de vida, no a la vida"], resp: 1 },
      { q: "Ante sospecha de un trastorno alimentario, ¿qué NO deberías decir?", opts: ["'Estoy preocupado/a por vos'", "'¿Hay algo en lo que pueda ayudarte?'", "'Te ves muy delgada/o, por lo menos estás linda/o'", "'Quiero que hables con alguien de confianza'"], resp: 2 },
      { q: "¿Qué tipo de equipo suele tratar los trastornos alimentarios?", opts: ["Solo el médico clínico", "Un equipo interdisciplinario: psiquiatra, psicólogo, nutricionista y médico", "Solo el nutricionista", "Solo el psicólogo"], resp: 1 },
      { q: "El trastorno por atracón (BED) se diferencia de la bulimia en que:", opts: ["No existen diferencias", "En el BED no hay conductas compensatorias regulares después del atracón", "En el BED siempre hay purga", "El BED solo ocurre en personas con sobrepeso"], resp: 1 },
      { q: "¿Qué factor aumenta el riesgo de desarrollar un trastorno alimentario?", opts: ["Tener acceso a mucha comida sana", "Cultura de dieta, comparación social y presión estética", "Practicar deporte moderado", "Tener un peso estable"], resp: 1 },
      { q: "La imagen corporal distorsionada significa:", opts: ["No mirarse al espejo", "Ver el propio cuerpo de manera muy diferente a como realmente es", "Tener una imagen mental perfecta de uno mismo", "No recordar la propia apariencia"], resp: 1 }
    ]
  },
  {
    enfermedad: "TEPT",
    emoji: "💥",
    preguntas: [
      { q: "TEPT significa:", opts: ["Trastorno de Estrés Postraumático", "Trastorno de Energía Persistente y Temporal", "Tendencia de Estrés Post-Terapeútico", "Trastorno Emocional Psicológico Transitorio"], resp: 0 },
      { q: "Un flashback en el TEPT es:", opts: ["Un recuerdo agradable del pasado", "Una re-experimentación involuntaria e intensa del trauma como si estuviera ocurriendo ahora", "Una alucinación sin relación con el pasado", "Un sueño lúcido"], resp: 1 },
      { q: "¿Solo los veteranos de guerra pueden desarrollar TEPT?", opts: ["Sí, es exclusivo del combate militar", "No, cualquier persona que experimente o sea testigo de un evento traumático puede desarrollarlo", "Solo personas con antecedentes de problemas mentales", "Solo adultos mayores de 40"], resp: 1 },
      { q: "¿Qué significa la hipervigilancia en el TEPT?", opts: ["Estar muy pendiente de las noticias", "Estado de alerta constante, como si el peligro pudiera aparecer en cualquier momento", "Dormir mucho para recuperarse", "Vigilar a los demás constantemente"], resp: 1 },
      { q: "Desarrollar TEPT después de un trauma es señal de:", opts: ["Debilidad de carácter", "Una respuesta normal del sistema nervioso ante una situación abrumadora", "Fingir síntomas", "Falta de voluntad para superar el evento"], resp: 1 },
      { q: "¿Cuál de estas terapias tiene mayor evidencia para el TEPT?", opts: ["Hablar del trauma en grupo sin estructura", "EMDR y terapia cognitivo-conductual centrada en el trauma", "Evitar cualquier mención del trauma para siempre", "Solo medicación sin terapia"], resp: 1 },
      { q: "¿Cuánto tiempo después del trauma se puede diagnosticar TEPT?", opts: ["Al día siguiente del evento", "Los síntomas deben persistir más de un mes", "Solo después de 2 años", "Inmediatamente si el trauma fue grave"], resp: 1 },
      { q: "¿Qué significa 'grounding' en el contexto del TEPT?", opts: ["Técnicas para conectarse con el presente y salir del estado de flashback", "Hospitalización de la persona", "Medicación de emergencia", "Relatar el trauma en detalle"], resp: 0 },
      { q: "Ante alguien con TEPT en un estado de flashback, lo más útil es:", opts: ["Tocarla físicamente de inmediato sin avisar", "Hablar con voz calmada, orientarla al presente, preguntar antes de tocar", "Hablar en voz alta sobre el trauma para que lo procese", "Dejarla sola para que se calme"], resp: 1 },
      { q: "¿El TEPT puede afectar la memoria?", opts: ["No, la memoria siempre permanece intacta", "Sí, puede causar lagunas de memoria del trauma o recuerdos fragmentados e intrusivos", "Solo la memoria de largo plazo", "Solo la memoria de corto plazo sin relación al trauma"], resp: 1 }
    ]
  }
];

let totalCorrect = 0;
let totalAnswered = 0;
const blockStats = triviaData.map(b => ({ correct: 0, answered: 0, total: b.preguntas.length }));

function updateBlockScore(blockIndex) {
  const stats = blockStats[blockIndex];
  const percent = stats.total ? Math.round((stats.correct / stats.total) * 100) : 0;
  const scoreEl = document.getElementById(`block-score-${blockIndex}`);
  if (scoreEl) {
    scoreEl.textContent = `Aciertos: ${stats.correct} / ${stats.total} (${percent}%)`;
  }
}

function renderTrivia() {
  const container = document.getElementById('trivia-container');
  triviaData.forEach((bloque, bi) => {
    const div = document.createElement('div');
    div.className = 'trivia-block';
    div.innerHTML = `<div class="trivia-disease-title">${bloque.emoji} ${bloque.enfermedad}</div>`;
    bloque.preguntas.forEach((p, qi) => {
      const qId = `q_${bi}_${qi}`;
      const card = document.createElement('div');
      card.className = 'q-card';
      const optsHtml = p.opts.map((o, oi) =>
        `<button class="q-opt" onclick="checkAnswer('${qId}', ${oi}, ${p.resp})">${o}</button>`
      ).join('');
      card.innerHTML = `
        <div class="q-text">${qi + 1}. ${p.q}</div>
        <div class="q-options" id="opts_${qId}">${optsHtml}</div>
        <div class="q-feedback" id="fb_${qId}"></div>
      `;
      div.appendChild(card);
    });
    const blockScore = document.createElement('div');
    blockScore.className = 'block-score';
    blockScore.id = `block-score-${bi}`;
    blockScore.textContent = `Aciertos: 0 / ${bloque.preguntas.length} (0%)`;
    div.appendChild(blockScore);
    container.appendChild(div);
  });
}

function checkAnswer(qId, chosen, correct) {
  const optsEl = document.getElementById('opts_' + qId);
  if (optsEl.dataset.answered) return;
  optsEl.dataset.answered = '1';
  const opts = optsEl.querySelectorAll('.q-opt');
  opts.forEach((btn, i) => {
    if (i === correct) btn.classList.add('correct');
    else if (i === chosen && chosen !== correct) btn.classList.add('wrong');
    else if (i !== chosen) btn.classList.add('reveal');
    btn.disabled = true;
  });
  const fb = document.getElementById('fb_' + qId);
  totalAnswered++;
  const blockIndex = Number(qId.split('_')[1]);
  const block = blockStats[blockIndex];
  block.answered++;
  if (chosen === correct) {
    totalCorrect++;
    block.correct++;
    fb.className = 'q-feedback show ok';
    fb.textContent = '✓ ¡Correcto!';
  } else {
    fb.className = 'q-feedback show bad';
    fb.textContent = '✗ Incorrecto. La respuesta correcta está resaltada en verde.';
  }
  updateBlockScore(blockIndex);
  document.getElementById('score-display').textContent = `${totalCorrect} / ${totalAnswered}`;
}

renderTrivia();
</script>
</body>
</html>
