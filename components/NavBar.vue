<template>
  <nav class="navbar" :class="{ 'navbar-scrolled': isScrolled }">
    <div class="logo-container">
      <div class="hammer-sickle">☭</div>
      <div class="logo">
        <span class="logo-text">Revolución</span>
        <span class="logo-text-accent">Rusa</span>
      </div>
    </div>

    <ul class="nav-links">
      <li v-for="(link, index) in links" :key="index">
        <NuxtLink 
          :to="link.path" 
          exact-active-class="active-link"
          class="nav-link"
        >
          {{ link.name }}
          <span class="link-decoration"></span>
          <div class="star-container">
            <span class="star">★</span>
          </div>
        </NuxtLink>
      </li>
    </ul>

    <div class="menu-toggle" @click="toggleMenu" :class="{ 'active': isMenuOpen }">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </nav>

  <!-- Menú móvil -->
  <div class="mobile-menu" :class="{ 'active': isMenuOpen }">
    <NuxtLink 
      v-for="(link, index) in links" 
      :key="index"
      :to="link.path" 
      exact-active-class="active-link"
      class="mobile-link"
      @click="closeMenu"
    >
      {{ link.name }}
    </NuxtLink>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

const links = [
  { name: 'Inicio', path: '/' },
  { name: 'Teoría', path: '/teoria' },
  { name: 'Examen', path: '/examen' }
];

const isScrolled = ref(false);
const isMenuOpen = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
};

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};

const closeMenu = () => {
  isMenuOpen.value = false;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: linear-gradient(135deg, #8b0000 0%, #b31217 50%, #dc143c 100%);
  padding: 1rem 2rem;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  transition: all 0.3s ease;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
}

.navbar-scrolled {
  padding: 0.5rem 2rem;
  background: rgba(139, 0, 0, 0.95);
  backdrop-filter: blur(10px);
}

.logo-container {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.hammer-sickle {
  font-size: 2rem;
  color: #ffe100;
  animation: rotate 10s infinite linear;
}

@keyframes rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

.logo {
  display: flex;
  flex-direction: column;
  line-height: 1.2;
}

.logo-text {
  font-size: 1.2rem;
  font-weight: 700;
  color: white;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.logo-text-accent {
  font-size: 1.4rem;
  font-weight: 800;
  color: #ffe100;
  text-transform: uppercase;
  letter-spacing: 2px;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: 0;
  padding: 0;
  margin-right: 50px;
}

.nav-link {
  position: relative;
  color: white;
  text-decoration: none;
  font-weight: 500;
  font-size: 1.1rem;
  padding: 0.5rem 1rem;
  transition: all 0.3s ease;
}

.nav-link:hover {
  color: #ffe100;
}

.link-decoration {
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 100%;
  height: 2px;
  background: #ffe100;
  transform: scaleX(0);
  transition: transform 0.3s ease;
  transform-origin: right;
}

.nav-link:hover .link-decoration {
  transform: scaleX(1);
  transform-origin: left;
}

.active-link {
  color: #ffe100 !important;
}

.active-link .link-decoration {
  transform: scaleX(1);
}

.star-container {
  position: absolute;
  top: -10px;
  right: -10px;
  opacity: 0;
  transition: all 0.3s ease;
}

.star {
  color: #ffe100;
  font-size: 1.2rem;
}

.active-link .star-container {
  opacity: 1;
  animation: starPulse 2s infinite;
}

@keyframes starPulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.2); }
  100% { transform: scale(1); }
}

/* Menú móvil */
.menu-toggle {
  display: none;
  flex-direction: column;
  gap: 6px;
  cursor: pointer;
  padding: 5px;
}

.menu-toggle span {
  display: block;
  width: 25px;
  height: 3px;
  background-color: white;
  transition: all 0.3s ease;
}

.menu-toggle.active span:nth-child(1) {
  transform: rotate(45deg) translate(8px, 6px);
}

.menu-toggle.active span:nth-child(2) {
  opacity: 0;
}

.menu-toggle.active span:nth-child(3) {
  transform: rotate(-45deg) translate(8px, -6px);
}

.mobile-menu {
  display: none;
  position: fixed;
  top: 70px;
  left: 0;
  width: 100%;
  background: rgba(139, 0, 0, 0.95);
  padding: 1rem;
  transform: translateY(-100%);
  transition: transform 0.3s ease;
  z-index: 999;
}

.mobile-menu.active {
  transform: translateY(0);
}

.mobile-link {
  display: block;
  color: white;
  text-decoration: none;
  padding: 1rem;
  text-align: center;
  transition: all 0.3s ease;
}

.mobile-link:hover {
  background: rgba(255, 225, 0, 0.1);
  color: #ffe100;
}

/* Responsive */
@media (max-width: 768px) {
  .nav-links {
    display: none;
  }

  .menu-toggle {
    display: flex;
  }

  .mobile-menu {
    display: block;
  }
}

/* Animaciones adicionales */
.navbar {
  animation: slideDown 0.5s ease;
}

@keyframes slideDown {
  from {
    transform: translateY(-100%);
  }
  to {
    transform: translateY(0);
  }
}

/* Efecto de hover en el logo */
.logo-container:hover .hammer-sickle {
  animation: shake 0.5s ease;
}

@keyframes shake {
  0%, 100% { transform: rotate(0deg); }
  25% { transform: rotate(-10deg); }
  75% { transform: rotate(10deg); }
}
</style>