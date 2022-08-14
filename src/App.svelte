<script>
  import Typewriter from "./lib/Typewriter.svelte";
  import DiGithubBadge from 'svelte-icons/di/DiGithubBadge.svelte'
  import FaFileAlt from 'svelte-icons/fa/FaFileAlt.svelte'
  import FaProjectDiagram from "svelte-icons/fa/FaProjectDiagram.svelte";
import FaLinkedin from "svelte-icons/fa/FaLinkedin.svelte";
  
  const logos = {
    
  };
</script>

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
  <a class="icon gh-icon" href="#">
    <DiGithubBadge />
  </a>
  <a class="icon resume-icon" href="#">
    <FaFileAlt />
  </a>
  <a class="icon project-icon" href="#">
    <FaProjectDiagram />
  </a>
  <a class="icon in-icon" href="#">
    <FaLinkedin />
  </a>
</div>

<style>
  .my-text {
    text-align: center;
    margin: 10% 0 2% 0;
  }
  .description {
    height: 19px;
  }
  .title {
    height: 39px;
  }

  .logo-icons {
    margin: 0 25%;
    display: flex;
    justify-content: space-around;
  }
  .icon {
    height: 100px;
    margin: 0;
    color: white;
  }
  .gh-icon {
    position: relative;
    bottom: 20px;
    height: 140px;
  }
</style>
