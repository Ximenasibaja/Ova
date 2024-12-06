<template>
    <div class="home-page">
      <div class="stars"></div>
      <div class="content-container">
        <h1 class="title">La Revolución Rusa</h1>
        <h2 class="subtitle">1917 - Un momento que cambió la historia</h2>
  
        <div class="description">
          <p>
            Embárcate en un viaje histórico a través de uno de los acontecimientos más 
            significativos del siglo XX. Descubre los eventos que transformaron una nación
            y cambiaron el curso de la historia mundial.
          </p>
        </div>
        <div class="video-container">
        <video class="video" controls src="/components/WhatsApp Video 2024-11-21 at 3.32.09 PM.mp4"></video>
      </div>
  
        <div class="features">
          <div class="feature">
            <span class="icon">📚</span>
            <p>Teoría Histórica</p>
          </div>
          <div class="feature">
            <span class="icon">⚔️</span>
            <p>Eventos Clave</p>
          </div>
          <div class="feature">
            <span class="icon">✍️</span>
            <p>Evaluación Interactiva</p>
          </div>
        </div>
  
        <div class="nav-buttons">
          <NuxtLink to="/teoria" class="btn">
            Comenzar el Viaje
            <span class="arrow">→</span>
          </NuxtLink>
        </div>
      </div>
    </div>
  </template>
  
  <style scoped>
  body,html {
    margin: 0;
  padding: 0;
  box-sizing: border-box;
  }
  .home-page {
    min-height: 100vh;
    position: relative;
    overflow: hidden;
    background: linear-gradient(135deg, #1a1a1a 0%, #4a0f0f 100%);
    color: #ffffff;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;

  }
  
  .stars {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: radial-gradient(2px 2px at 20px 30px, #ffffff, rgba(0,0,0,0)),
                      radial-gradient(2px 2px at 40px 70px, #ffffff, rgba(0,0,0,0)),
                      radial-gradient(2px 2px at 50px 160px, #ffffff, rgba(0,0,0,0)),
                      radial-gradient(2px 2px at 90px 40px, #ffffff, rgba(0,0,0,0)),
                      radial-gradient(2px 2px at 130px 80px, #ffffff, rgba(0,0,0,0));
    background-size: 200px 200px;
    animation: shine 4s linear infinite;
  }
  
  @keyframes shine {
    from {
      transform: translateY(0);
    }
    to {
      transform: translateY(-100px);
    }
  }
  
  .content-container {
    position: relative;
    max-width: 1200px;
    margin: 0 auto;
    padding: 60px 20px;
    text-align: center;
    animation: fadeIn 2s ease;
    flex: 1;
  }
  
  .title {
    font-size: 4rem;
    font-weight: bold;
    color: #ff3333;
    text-shadow: 0 0 10px rgba(255, 51, 51, 0.5);
    margin-bottom: 20px;
    animation: titleSlide 1s ease-out;
  }
  
  .subtitle {
    font-size: 1.8rem;
    color: #ffcccc;
    margin-bottom: 40px;
    animation: subtitleSlide 1s ease-out 0.3s backwards;
  }
  
  .description {
    max-width: 800px;
    margin: 0 auto 50px;
    font-size: 1.2rem;
    line-height: 1.6;
    color: #ffffff;
    animation: fadeIn 1s ease-out 0.6s backwards;
  }
  
  .features {
    display: flex;
    justify-content: center;
    gap: 40px;
    margin-bottom: 50px;
    animation: fadeIn 1s ease-out 0.9s backwards;
  }
  
  .feature {
    background: rgba(255, 255, 255, 0.1);
    padding: 20px;
    border-radius: 10px;
    backdrop-filter: blur(5px);
    transition: transform 0.3s ease;
  }
  
  .feature:hover {
    transform: translateY(-5px);
  }
  
  .icon {
    font-size: 2rem;
    margin-bottom: 10px;
    display: block;
  }
  
  .btn {
    display: inline-flex;
    align-items: center;
    padding: 15px 40px;
    font-size: 1.2rem;
    color: #ffffff;
    background: linear-gradient(45deg, #ff3333, #ff6666);
    border: none;
    border-radius: 30px;
    text-decoration: none;
    transition: all 0.3s ease;
    animation: buttonPulse 2s infinite;
  }
  
  .btn:hover {
    transform: scale(1.05);
    box-shadow: 0 0 20px rgba(255, 51, 51, 0.5);
  }
  
  .arrow {
    margin-left: 10px;
    transition: transform 0.3s ease;
  }
  
  .btn:hover .arrow {
    transform: translateX(5px);
  }
  
  @keyframes fadeIn {
    from {
      opacity: 0;
      transform: translateY(20px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  @keyframes titleSlide {
    from {
      opacity: 0;
      transform: translateX(-100px);
    }
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
  
  @keyframes subtitleSlide {
    from {
      opacity: 0;
      transform: translateX(100px);
    }
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
  
  @keyframes buttonPulse {
    0% {
      box-shadow: 0 0 0 0 rgba(255, 51, 51, 0.4);
    }
    70% {
      box-shadow: 0 0 0 10px rgba(255, 51, 51, 0);
    }
    100% {
      box-shadow: 0 0 0 0 rgba(255, 51, 51, 0);
    }
  }
  
  @media (max-width: 768px) {
    .title {
      font-size: 3rem;
    }
  
    .subtitle {
      font-size: 1.4rem;
    }
  
    .features {
      flex-direction: column;
      gap: 20px;
    }
  }
  .video-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
  margin-bottom: 20px
}

/* Video */
.video {
  width: 80%;
  max-width: 800px;
  border: 2px solid white;
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
}
  </style>
  