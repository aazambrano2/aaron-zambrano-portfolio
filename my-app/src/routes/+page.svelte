<script>
    import { onMount } from 'svelte';
    import { fade } from 'svelte/transition';
  
    let visible = false;
    onMount(() => {
      visible = true;
    });

    const githubUrl = "https://github.com/aazambrano2";
    const linkedinUrl = "https://www.linkedin.com/in/aaron-zambrano-b35487170/";

    const projects = [
      {
      id: 1,
      name: "Can Bus Visualizer",
      description: "Capstone Project for my senior project where I work with a team of 8 to deliver a software application that is able to visualize CAN Networks of vehicles using REACT and Python technologies.",
      imageUrl: "https://canlogger1000.csselectronics.com/img/CAN-bus-intro-tutorial-controller-area-network.svg",
      url: "https://github.com/sw2team4/CS4311_CANBusVisualizer_Team4"
    },
    {
      id: 2,
      name: "MinerFit",
      description: "The fitness system web application offers a personalized experience to those who would like to have a flexible, seamless fitness journey without disruptions.",
      imageUrl: "https://upload.wikimedia.org/wikipedia/en/thumb/0/06/UTEP_Miners_logo.svg/1200px-UTEP_Miners_logo.svg.png",
      url: "https://github.com/aazambrano2/MinerFit?tab=readme-ov-file"
    },
    {
      id: 3,
      name: "Community Support Network",
      description: "A new platform designed to connect individuals and organizations in need of community services with donors..",
      imageUrl: "https://cdn.gamma.app/j0r5wuiqvpddthl/43a73e4c8eb546b09f6824f933600567/original/image.png",
      url: "https://gamma.app/docs/Community-Support-Network-p61hn50i97ufubk?mode=doc"
    }
  ];
  </script>
  
  <svelte:head>
    <title>Aaron Zambrano - Portfolio</title>
  </svelte:head>
  
  {#if visible}
    <section class="hero" transition:fade>
      <div class="container">
        <h1>Hello, I'm Aaron Zambrano</h1>
        <p> A Software Engineer helping you provide efficent and agile soulitons </p>
        <a href="#contact" class="btn">Get in Touch</a>
      </div>
    </section>
  
    <section id="projects" class="section projects" transition:fade>
      <div class="container">
        <h2 class="section-title">My Projects</h2>
        <div class="project-grid">
          {#each projects as project}
            <a href= {project.url} class="project-card" style= "text-decoration: none; color: inherit;">
              <img src={project.imageUrl} alt="Project {project.name}" />
              <div class="project-info">
                <h3>{project.name}</h3>
                <p>{project.description}</p>
              </div>
            </a>
          {/each}
        </div>
      </div>
    </section>
  
    <section id="about" class="section about" transition:fade>
      <div class="container">
        <h2 class="section-title">About Me</h2>
        <div class = "image-wrapper">
          <img src={`https://i.imgur.com/wWo6Yft.jpeg`} class ="me-image"/>
        </div>
        <div class="about-content">
          <p>I'm a passionate developer and Software Engineer with a keen eye for design. I love creating intuitive and beautiful experiences that solve real-world problems.</p>
          <a href="https://drive.google.com/file/d/10Jz36uCiK5oJzD1UL-d8jXUxZJbwbyhV/view?usp=sharing" class="btn">See My Resume</a>
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
        <!-- <form class="contact-form">
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
        </form> -->
      </div>
      <div class ="social-wrapper">
        <div class="social-buttons">
              <a href={githubUrl} target="_blank" rel="noopener" class="social-button">
                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub" />
                GitHub
              </a>
              <a href={linkedinUrl} target="_blank" rel="noopener" class="social-button">
                <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" alt="LinkedIn" />
                LinkedIn
              </a>
            </div>
      </div>
    </section>
    
  {/if}
  
  <style>
    .image-wrapper {
    display: flex;
    justify-content: center; 
    }

    .me-image{
      width: 500px;
      height: auto;
    }

    .hero {
      background-color: #f5f5f7;
      background-size: contain;
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
      transition: border-color 0.3s ease;
      cursor: pointer;
    }

    .project-card:hover{
      transform: scale(1.05) translateY(-5px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.3);
      filter: brightness(1.1);
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

    .social-wrapper {
    display: flex;
    justify-content: center;
    margin-top: 2rem;
    }

    .social-buttons {
    display: flex;
    gap: 1rem;
    margin-top: 1rem;
    }

  .social-button {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    text-decoration: none;
    background-color: #f0f0f0;
    border-radius: 8px;
    padding: 0.5rem 1rem;
    transition: background-color 0.2s ease, transform 0.2s ease;
    color: #000;
    font-weight: bold;
  }

  .social-button img {
    width: 24px;
    height: 24px;
  }

  .social-button:hover {
    background-color: #e0e0e0;
    transform: translateY(-2px);
  }


    
  </style>
  
  