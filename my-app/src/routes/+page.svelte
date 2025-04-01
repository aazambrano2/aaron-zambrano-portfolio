<script>
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';
  
    let visible = false;
    onMount(() => {
      visible = true;
    });
  </script>
  
  <svelte:head>
    <title>Aaron Zambrano - Portfolio</title>
  </svelte:head>
  
  {#if visible}
    <section class="hero" transition:fade>
      <div class="container">
        <!-- <img src={`https://i.imgur.com/wWo6Yft.jpeg`}/> -->
        <h1>Hello, I'm Aaron Zambrano</h1>
        <p> A Software Engineer helping you provide efficent and agile soulitons </p>
        <a href="#contact" class="btn">Get in Touch</a>
      </div>
    </section>
  
    <section id="projects" class="section projects" transition:fade>
      <div class="container">
        <h2 class="section-title">My Projects</h2>
        <div class="project-grid">
          {#each [1, 2, 3] as project}
            <div class="project-card">
              <img src={`https://picsum.photos/seed/${project}/400/300`} alt="Project {project}" />
              <div class="project-info">
                <h3>Project {project}</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis nec condimentum quam.</p>
              </div>
            </div>
          {/each}
        </div>
      </div>
    </section>
  
    <section id="about" class="section about" transition:fade>
      <div class="container">
        <h2 class="section-title">About Me</h2>
        <div class="about-content">
          <p>I'm a passionate developer and Software Engineer with a keen eye for design. I love creating intuitive and beautiful experiences that solve real-world problems.</p>
          <div class="skills">
            {#each ['Git', 'Flutter', 'React','HTML', 'CSS', 'JavaScript', 'Svelte', 'Node.js', 'Python', 'MongoDB', 'Java', 'GCP', "OCI", 'Firebase', 'Azure', 'MySQL'] as skill}
              <span class="skill-tag">{skill}</span>
            {/each}
          </div>
        </div>
      </div>
    </section>
  
    <section id="contact" class="section contact" transition:fade>
      <div class="container">
        <h2 class="section-title">Get in Touch</h2>
        <form class="contact-form">
          <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" required>
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" required>
          </div>
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" rows="4" required></textarea>
          </div>
          <button type="submit" class="btn">Send Message</button>
        </form>
      </div>
    </section>
  {/if}
  
  <style>
    .hero {
      background-color: #f5f5f7;
      padding: 120px 0 80px;
      text-align: center;
    }
  
    .hero h1 {
      font-size: 48px;
      font-weight: 600;
      margin-bottom: 16px;
    }
  
    .hero p {
      font-size: 24px;
      color: var(--color-secondary);
      margin-bottom: 32px;
    }
  
    .project-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 32px;
    }
  
    .project-card {
      background-color: white;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }
  
    .project-card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }
  
    .project-info {
      padding: 24px;
    }
  
    .project-info h3 {
      font-size: 24px;
      margin-bottom: 8px;
    }
  
    .about-content {
      max-width: 800px;
      margin: 0 auto;
      text-align: center;
    }
  
    .skills {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px;
      margin-top: 24px;
    }
  
    .skill-tag {
      background-color: #f5f5f7;
      color: var(--color-text);
      padding: 8px 16px;
      border-radius: 980px;
      font-size: 14px;
    }
  
    .contact-form {
      max-width: 500px;
      margin: 0 auto;
    }
  
    .form-group {
      margin-bottom: 24px;
    }
  
    .form-group label {
      display: block;
      margin-bottom: 8px;
    }
  
    .form-group input,
    .form-group textarea {
      width: 100%;
      padding: 12px;
      border: 1px solid #d2d2d7;
      border-radius: 8px;
      font-size: 16px;
    }
  
    .form-group textarea {
      resize: vertical;
    }
  </style>
  
  