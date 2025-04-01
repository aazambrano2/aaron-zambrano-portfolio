<script>
    import "../app.css";
  </script>
  
  <div class="layout">
    <header class="header">
      <nav class="container">
        <ul class="nav-list">
          <li><a href="/" class="nav-link">Home</a></li>
          <li><a href="#projects" class="nav-link">Projects</a></li>
          <li><a href="#about" class="nav-link">About</a></li>
          <li><a href="#contact" class="nav-link">Contact</a></li>
        </ul>
      </nav>
    </header>
  
    <main>
      <slot />
    </main>
  
    <footer class="footer">
      <div class="container">
        <p>&copy; {new Date().getFullYear()} Aaron Zambrano. All rights reserved.</p>
      </div>
    </footer>
  </div>
  
  <style>
    .layout {
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }
  
    .header {
      background-color: rgba(255, 255, 255, 0.8);
      backdrop-filter: blur(20px);
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      z-index: 1000;
    }
  
    .nav-list {
      display: flex;
      justify-content: center;
      list-style-type: none;
      padding: 0;
    }
  
    .nav-link {
      color: var(--color-text);
      text-decoration: none;
      padding: 20px;
      display: inline-block;
      transition: color 0.3s ease;
    }
  
    .nav-link:hover {
      color: var(--color-primary);
    }
  
    main {
      flex-grow: 1;
    }
  
    .footer {
      background-color: #f5f5f7;
      padding: 20px 0;
      text-align: center;
    }
  </style>
  
  