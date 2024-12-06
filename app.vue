<template>
  <div>
    <NavBar />
    <NuxtPage />
  </div>
  <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" >
<link href="https://fonts.googleapis.com/css2?family=Bitter:ital,wght@0,100..900;1,100..900&family=Faculty+Glyphic&family=Funnel+Display:wght@300..800&family=Libre+Bodoni:ital,wght@0,400..700;1,400..700&family=Outfit:wght@100..900&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Titillium+Web:ital,wght@0,200;0,300;0,400;0,600;0,700;0,900;1,200;1,300;1,400;1,600;1,700&display=swap" rel="stylesheet">
  <footer class="footer">
    <div class="footer-content">
      <div class="footer-left">
        <img 
          class="footer-image" 
          src="https://th.bing.com/th/id/R.0cee4c4e109e44560fe5dcc2b6cf01fb?rik=boK9Vp1Gr6rJ1A&pid=ImgRaw&r=0" 
          alt="Logo del OVA"
        />
        <div class="social-icons">
          <a href="#" class="social-icon">📱</a>
          <a href="#" class="social-icon">📧</a>
          <a href="#" class="social-icon">📘</a>
        </div>
      </div>
      <div class="footer-center">
        <h3 class="footer-title">OVA Revolución Rusa</h3>
        <div class="footer-text">
          <p>
            &copy; 2024 La Gran Revolución: Un Viaje por la Historia Soviética
          </p>
          <p>
            "Пролетарии всех стран, соединяйтесь!"<br>
            (¡Proletarios de todos los países, uníos!)
          </p>
          <p class="creator">
            Creado con pasión por: Ximena Sibaja
          </p>
        </div>
      </div>
      <div class="footer-right">
        <div class="quick-links">
          <h4>Enlaces Rápidos</h4>
          <ul>
            <li><a href="#">Inicio</a></li>
            <li><a href="#">Cronología</a></li>
            <li><a href="#">Personajes</a></li>
            <li><a href="#">Recursos</a></li>
          </ul>
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <p>Este sitio web fue creado con fines educativos. El contenido está protegido bajo licencia Creative Commons.</p>
    </div>
  </footer>
</template>

<style>
*{
  font-family: "Outfit";
}
body {
  font-family: 'Roboto', sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.footer {
  background: linear-gradient(to right, #8b0000, #4a0404);
  color: #f1f1f1;
  padding: 40px 0 20px;
  position: relative;
  border-top: 3px solid #ffd700;
  font-family: "Outfit"
}

.footer::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(to right, #ffd700, #8b0000, #ffd700);
}

.footer-content {
  display: flex;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;

}

.footer-left, .footer-center, .footer-right {
  flex: 1;
  padding: 0 20px;
}

.footer-image {
  width: 100px;
  height: auto;
  border-radius: 50%;
  border: 3px solid #ffd700;
  margin-bottom: 20px;
  transition: transform 0.3s ease;
}

.footer-image:hover {
  transform: scale(1.1);
}

.social-icons {
  display: flex;
  gap: 15px;
  margin-top: 15px;
}

.social-icon {
  color: #f1f1f1;
  text-decoration: none;
  font-size: 1.5rem;
  transition: transform 0.3s ease;
}

.social-icon:hover {
  transform: scale(1.2);
}

.footer-title {
  font-family: 'Playfair Display', serif;
  color: #ffd700;
  font-size: 1.8rem;
  margin-bottom: 20px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.footer-text {
  line-height: 1.8;
  font-size: 1rem;
}

.creator {
  color: #ffd700;
  font-style: italic;
  margin-top: 15px;
}

.quick-links h4 {
  color: #ffd700;
  margin-bottom: 15px;
  font-family: 'Playfair Display', serif;
}

.quick-links ul {
  list-style: none;
  padding: 0;
}

.quick-links li {
  margin-bottom: 10px;
}

.quick-links a {
  color: #f1f1f1;
  text-decoration: none;
  transition: color 0.3s ease;
}

.quick-links a:hover {
  color: #ffd700;
}

.footer-bottom {
  text-align: center;
  margin-top: 30px;
  padding-top: 20px;
  border-top: 1px solid rgba(255, 215, 0, 0.3);
  font-size: 0.9rem;
  color: #ccc;
}

@media (max-width: 768px) {
  .footer-content {
    flex-direction: column;
    text-align: center;
  }
  
  .footer-left, .footer-center, .footer-right {
    margin-bottom: 30px;
  }
  
  .social-icons {
    justify-content: center;
  }
  
  .quick-links {
    display: none;
  }
}
</style>