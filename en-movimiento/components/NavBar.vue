<template>
    <nav class="navbar">
      <div class="logo">
        Revolución Rusa
      </div>
      <ul class="nav-links">
        <li>
          <NuxtLink to="/" exact-active-class="active-link ">Inicio</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/teoria" exact-active-class="active-link ">Teoría</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/examen" exact-active-class="active-link link">Examen</NuxtLink>
        </li>
      </ul>
    </nav>
  </template>
  
  <style scoped>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: linear-gradient(45deg, #b31217, #e52d27);
    padding: 10px 20px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 10;
  }
  
  .logo {
    font-size: 1.5rem;
    font-weight: bold;
    color: white;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
  }
  
  .nav-links {
    display: flex;
    list-style: none;
    gap: 20px;
    
  }
  
  .nav-links a {
    color: white;
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s ease;
    
  }
  
  .nav-links a:hover {
    color: #ffe100;
  }
  
  .active-link {
    border-bottom: 2px solid #ffe100;
   
  }
  .link {
    margin-right: 30px
  }
  </style>
  