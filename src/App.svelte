<script>
  import Typewriter from "./lib/Typewriter.svelte";
  import DiGithubBadge from 'svelte-icons/di/DiGithubBadge.svelte'
  import FaFileAlt from 'svelte-icons/fa/FaFileAlt.svelte'
import FaLinkedin from "svelte-icons/fa/FaLinkedin.svelte";
import Projects from "./lib/Projects.svelte";
import ParticleAnim from "./lib/ParticleAnim.svelte";
  
  const logos = {
    
  };
</script>

<div class="pages">
  <div class="page intro">
    <ParticleAnim />
    <div class="my-text">
      <h1 class="title"><Typewriter text={'Bailey Chittle'} eraseText={false}/></h1>
      <p class="description"><Typewriter texts={[
        "Software engineer",
        "Currently employed to write efficient C++ for ultrasonic systems",
        `"The more you know, the more you realize you know nothing" -Socrates`,
        "I have experience in web development and project management",
        "while(isAlive) {eat();code();sleep();}",
        "My CSS is !important",
        `$("#Github").click();`,
      ]}/></p>
    </div>

    <div class="logo-icons">
      <a class="icon gh-icon" href="https://github.com/bachittle">
        <DiGithubBadge />
      </a>
      <a class="icon in-icon" href="https://linkedin.com/in/bailey-chittle">
        <FaLinkedin />
      </a>
      <a class="icon resume-icon" href="#">
        <FaFileAlt />
      </a>
    </div>
  </div>
  <div class="page">
    <div class="projects">
      <Projects />
    </div>
  </div>
</div>

<style>
  /* pages resemble 2 cards. Side by side horizontally when wide, otherwise side by side vertically. */
  .pages {
    display: flex;
  }
  .page {
    width: 50%;
    height: 100vh;
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
  
  @media (max-width: 820px) {
    .pages {
      display: flex;
      flex-direction: column;
    }
    .page {
      width: 100%;
      height: 100vh;
      display: flex;
      justify-content: center;
      flex-direction: column;
    }
  }
  
  /* intro displays name, description, and logos */
  .intro {
    text-align: center;
  }
  .title {
    height: 39px;
  }
  .description {
    height: 19px;
    margin: 3em 4em;
  }

  .logo-icons {
    margin: 0 10% 0 5%;
    display: flex;
    justify-content: space-around;
  }
  .icon {
    height: 100px;
    margin: 0 1em;
    color: white;
  }
  .gh-icon {
    position: relative;
    bottom: 15px;
    left: 15px;
    height: 140px;
  }
  
  /* projects shows list of projects I worked on. Javascript list has data. Data is rendered via an each block */
  .projects {
    background-color: #1e1f2e;
    padding: 2em 2em;
    margin: 0 0;
  }
  
</style>
