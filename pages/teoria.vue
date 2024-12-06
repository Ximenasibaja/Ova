<template>
    <div class="theory-page">
      <div class="background-overlay"></div>
      <div class="theory-content">
        <div class="section hero">
          <h1 class="title">Teoría de la Revolución Rusa</h1>
          <h2 class="subtitle">1917: El Año que Transformó el Mundo</h2>
        </div>
  
        <div class="section context">
          <div class="context-description">
            <p>
              La Revolución Rusa de 1917 no fue simplemente un evento político, 
              sino un tsunami social que redefinió el panorama mundial, 
              desmantelando siglos de monarquía zarista y sembrando las semillas 
              de un nuevo orden ideológico que marcaría el siglo XX.
            </p>
          </div>
        </div>
  
        <div class="section key-aspects">
          <div class="aspect-grid">
            <div class="aspect-card">
              <div class="aspect-icon">🕰️</div>
              <h3>Contexto Histórico</h3>
              <p>
                Rusia a inicios del siglo XX era un imperio con enormes 
                desigualdades sociales, un campesinado oprimido y una 
                industrialización incipiente bajo el régimen zarista de Nicolás II.
              </p>
            </div>
  
            <div class="aspect-card">
              <div class="aspect-icon">⚔️</div>
              <h3>Causas Principales</h3>
              <p>
                Combinación explosiva de hambrunas, pérdidas en la Primera Guerra Mundial, 
                descontento social extremo y un proletariado cada vez más consciente 
                de su potencial revolucionario.
              </p>
            </div>
  
            <div class="aspect-card">
              <div class="aspect-icon">🚩</div>
              <h3>Etapas Revolucionarias</h3>
              <p>
                Dos momentos cruciales: 
                • Revolución de Febrero: Derrocamiento del Zar 
                • Revolución de Octubre: Toma del poder por los Bolcheviques
              </p>
            </div>
          </div>
        </div>
  
        <div class="section leaders">
          <h2>Protagonistas de la Revolución</h2>
          <div class="leaders-grid">
            <div class="leader-card">
             
              <h3>Vladimir Lenin</h3>
              <p>Líder ideológico. Arquitecto de la Revolución Bolchevique.</p>
            </div>
            <div class="leader-card">
              
              <h3>Leon Trotsky</h3>
              <p>Estratega militar. Organizador del Ejército Rojo.</p>
            </div>
            <div class="leader-card">
              
              <h3>Joseph Stalin</h3>
              <p>Secretario General. Posterior líder de la Unión Soviética.</p>
            </div>
          </div>
        </div>
  
        <div class="section consequences">
          <h2>Consecuencias Globales</h2>
          <ul>
            <li>Fin del Imperio Ruso y nacimiento de la Unión Soviética
              <p><span>Fin del zarismo:</span> La Revolución de Febrero de 1917 puso fin al régimen autocrático del zar Nicolás II, último gobernante de la dinastía Romanov, que había liderado Rusia por más de 300 años.
Caos y transición: Tras la abdicación del zar, se instauró un gobierno provisional que fue derrocado por los bolcheviques en la Revolución de Octubre de 1917, liderada por Lenin. <br><span>Creación de la URSS:</span> En 1922, tras una sangrienta guerra civil, se fundó la Unión de Repúblicas Socialistas Soviéticas (URSS), una federación comunista que agrupaba varias repúblicas bajo un régimen socialista centralizado, marcando el inicio de una nueva era en la historia de Rusia.</br>
</p>
            </li>
            <li>Expansión global del ideario comunista
              <p><span>Internacionalización del comunismo:</span>  La Revolución Rusa inspiró a movimientos comunistas y socialistas en todo el mundo, al demostrar que era posible derrocar un sistema capitalista y establecer un gobierno proletario. <br><span>Comintern:</span> En 1919, se fundó la Tercera Internacional Comunista (Comintern), una organización que buscaba coordinar y apoyar movimientos revolucionarios globales.</br>
</p>
            </li>
            <li>Reconfiguración de las relaciones internacionales
              <p><span>Surgimiento de una nueva potencia:</span>  La URSS se consolidó como una potencia global, proponiendo una alternativa al modelo capitalista y colonial dominante hasta entonces. <br><span>Política de bloques: </span> La ideología comunista promovida por la URSS desafió a las potencias occidentales, principalmente a Estados Unidos y Europa occidental, creando una rivalidad ideológica que definiría la política mundial durante décadas.</br>
              </p>
            </li>
            <li>Inicio de la Guerra Fría
              <p><span>Rivalidad ideológica: </span>   Tras la Segunda Guerra Mundial, las tensiones entre la URSS y Estados Unidos, ambos vencedores del conflicto pero con ideologías opuestas, escalaron en una confrontación global que no incluyó enfrentamientos militares directos, pero sí conflictos indirectos como la Guerra de Corea y la Guerra de Vietnam. <br><span>Carrera armamentista y espacial </span>  La Guerra Fría implicó una competencia por la supremacía militar y tecnológica, llevando a la proliferación nuclear y a hitos como la llegada del hombre a la Luna.
              </br>
              </p>
            </li>
            <li>Transformación de los movimientos sociales mundiales
              <p><span>Refuerzo de las luchas obreras:  </span>   El éxito de la Revolución Rusa impulsó las demandas de derechos laborales y sociales en Europa y América, dando lugar a reformas como jornadas laborales más cortas y mejores condiciones para los trabajadores. <br><span>Movimientos feministas:</span> La URSS implementó políticas progresistas en términos de género, como el derecho al voto y la participación de las mujeres en la fuerza laboral, inspirando movimientos feministas en otras partes del mundo.
              </p>
            </li>
          </ul>
        </div>
  
        <div class="navigation">
          <NuxtLink to="/examen" class="btn-primary">
            Evalúa tu Conocimiento
            <span class="arrow">→</span>
          </NuxtLink>
        </div>
      </div>
    </div>
  </template>
  
  <style scoped>
  span {
    color: #ff3333;
  }
  .theory-page {
    position: relative;
    min-height: 100vh;
    background: linear-gradient(135deg, #1a1a1a 0%, #4a0f0f 100%);
    color: #ffffff;
    overflow: hidden;
  }
  
  .background-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: 
      radial-gradient(circle at 20% 30%, rgba(255,255,255,0.1) 0%, transparent 20%),
      radial-gradient(circle at 80% 70%, rgba(255,255,255,0.1) 0%, transparent 20%);
    animation: backgroundMovement 10s infinite alternate;
  }
  
  @keyframes backgroundMovement {
    from { transform: scale(1); }
    to { transform: scale(1.1); }
  }
  
  .theory-content {
    position: relative;
    max-width: 1200px;
    margin: 0 auto;
    padding: 40px 20px;
  }
  
  .section {
    margin-bottom: 60px;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeInUp 1s ease forwards;
  }
  
  .hero .title {
    font-size: 3.5rem;
    color: #ff3333;
    text-shadow: 0 0 15px rgba(255,51,51,0.5);
    margin-bottom: 20px;
  }
  
  .hero .subtitle {
    font-size: 1.8rem;
    color: #ffcccc;
  }
  
  .aspect-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
  }
  
  .aspect-card {
    background: rgba(255,255,255,0.1);
    padding: 25px;
    border-radius: 10px;
    backdrop-filter: blur(10px);
    transition: transform 0.3s ease;
  }
  
  .aspect-card:hover {
    transform: scale(1.05);
  }
  
  .aspect-icon {
    font-size: 3rem;
    margin-bottom: 15px;
  }
  
  .leaders-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
  }
  
  .leader-card {
    text-align: center;
    background: rgba(255,255,255,0.1);
    padding: 20px;
    border-radius: 15px;
  }
  
  .leader-image {
    width: 200px;
    height: 200px;
    border-radius: 50%;
    object-fit: cover;
    margin-bottom: 15px;
  }
  
  .consequences ul {
    list-style-type: none;
    padding: 0;
  }
  
  .consequences li {
    position: relative;
    padding-left: 30px;
    margin-bottom: 15px;
  }
  
  .consequences li::before {
    content: '✊';
    position: absolute;
    left: 0;
  }
  
  .navigation {
    text-align: center;
  }
  
  .btn-primary {
    display: inline-flex;
    align-items: center;
    padding: 15px 40px;
    background: linear-gradient(45deg, #ff3333, #ff6666);
    color: white;
    text-decoration: none;
    border-radius: 30px;
    transition: all 0.3s ease;
  }
  
  .btn-primary:hover {
    transform: scale(1.1);
    box-shadow: 0 0 20px rgba(255,51,51,0.5);
  }
  
  .arrow {
    margin-left: 10px;
  }
  
  @keyframes fadeInUp {
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  @media (max-width: 768px) {
    .aspect-grid,
    .leaders-grid {
      grid-template-columns: 1fr;
    }
  
    .hero .title {
      font-size: 2.5rem;
    }
  }
  </style>
  