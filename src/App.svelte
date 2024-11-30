<script>
    import { wrap } from "svelte-spa-router/wrap";
    import Router from "svelte-spa-router";
    import Contactos from './views/Contactos.svelte';
    import Productos from './views/Productos.svelte';
  
    const routes = {
      "/": wrap({ component: Contactos }), // Página principal
      "/productos": wrap({ component: Productos }),
      "/informes": wrap({ component: Informes }),
    };
  </script>
  
  <style>
    .nav {
      display: flex;
      justify-content: center;
      gap: 16px;
      margin: 20px 0;
    }
  
    .nav a {
      padding: 10px 20px;
      font-size: 1rem;
      border: none;
      border-radius: 8px;
      text-decoration: none;
      background-color: #f3f5f8;
      color: #333;
    }
  
    .nav a.active {
      background-color: #4a90e2;
      color: white;
    }
  
    .content {
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px;
    }
  </style>
  
  <!-- Barra de navegación -->
  <div class="nav">
    <a href="/" class:active={$location === "/"}>Contactos</a>
    <a href="/productos" class:active={$location === "/productos"}>Productos</a>
    <a href="/informes" class:active={$location === "/informes"}>Informes</a>
  </div>
  
  <!-- Contenido de la página -->
  <div class="content">
    <Router {routes} />
  </div>
  